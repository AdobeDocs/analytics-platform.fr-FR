---
title: Groupement basé sur les graphiques
description: Explication du groupement basé sur les graphiques
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 7%

---

# Groupement basé sur les graphiques


Dans le groupement basé sur des graphiques, vous spécifiez un jeu de données d’événement, ainsi que l’identifiant persistant (cookie) et l’espace de noms de l’identifiant transitoire (ID de personne) pour ce jeu de données. Le groupement basé sur des graphiques crée une nouvelle colonne pour l’identifiant assemblé dans le nouveau jeu de données assemblé. Ensuite, utilise l’identifiant persistant pour interroger le graphique d’identités à partir du service d’identité Experience Platform, à l’aide de l’espace de noms spécifié, pour mettre à jour l’identifiant associé.

![Groupement basé sur un graphique](/help/stitching/assets/gbs.png)

## Fonctionnement du groupement basé sur les graphiques

L’assemblage effectue au moins deux transmissions de données dans un jeu de données donné.

- **Groupement en direct** : tente de regrouper chaque accès (événement) au fur et à mesure de son apparition, en utilisant l’identifiant persistant pour rechercher l’identifiant transitoire pour l’espace de noms sélectionné en interrogeant le graphique d’identités. Si l’identifiant transitoire est disponible à partir de la recherche, cet identifiant transitoire est immédiatement assemblé.

- **Assemblage de relecture** : *lit à nouveau* les données en fonction des identités mises à jour du graphique d’identités. Cette étape est l’endroit où les accès provenant d’appareils précédemment inconnus (ID persistants) sont assemblés lorsque le graphique d’identités a résolu l’identité d’un espace de noms. La relecture est déterminée par deux paramètres : **frequency** et **lookback window**. Adobe propose les combinaisons suivantes de ces paramètres :
   - **Recherche en amont quotidienne à une fréquence quotidienne** : les données sont relues chaque jour avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   - **Recherche en amont hebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont hebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la relecture hebdomadaire suivante.
   - **Recherche en amont bihebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont bihebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins de deux semaines ne sont pas retraitées avant la relecture hebdomadaire suivante.
   - **Recherche en amont mensuelle sur une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont mensuel (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’un mois ne sont pas retraitées avant la relecture hebdomadaire suivante.

- **Confidentialité** : lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée du jeu de données source, tout regroupement de cette identité entre des événements non authentifiés doit être annulé. En outre, l’identité doit être supprimée du graphique d’identités afin d’empêcher de futurs regroupements graphiques pour cette identité spécifique.

  >[!IMPORTANT]
  >
  >Le processus de désassemblage, dans le cadre des demandes d’accès à des informations personnelles, a changé début 2025. Le processus de désassemblage en cours récupère les événements à l’aide de la dernière version des identités connues. Cette réaffectation d&#39;événements à une autre identité peut avoir des conséquences juridiques indésirables. Pour remédier à ces problèmes, à partir de 2025, le nouveau processus de désassemblage met à jour les événements qui sont soumis à la demande d’accès à des informations personnelles avec l’ID persistant.
  > 

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un visiteur doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois reconnu, un appareil est assemblé en direct à partir de ce moment.

Tenez compte des deux graphiques d’identités suivants pour l’identifiant persistant `246` et `3579`, de la manière dont ces graphiques d’identités sont mis à jour au fil du temps et de l’impact de ces mises à jour sur les étapes du groupement basé sur les graphiques.

![Graphique d’identités 246](assets/identity-graph-246.svg)
![Graphique d’identités 3579](assets/identity-graph-3579.svg)

Vous pouvez afficher un graphique d’identités au fil du temps pour un profil spécifique à l’aide de la [visionneuse de graphique d’identités](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Voir aussi [logique de liaison Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) pour une meilleure compréhension de la logique utilisée lors de la liaison d’identités.

### Étape 1 : assemblage en direct

L’assemblage en direct tente d’assembler chaque événement, lors de la collecte, à des informations connues à ce moment du graphique d’identités.

+++ Détails

| | Heure | ID persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Identifiant assemblé (après groupement dynamique) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non défini* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non défini* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Vous pouvez voir comment l’identifiant assemblé est résolu pour chaque événement. Selon l’heure, l’identifiant persistant et la recherche du graphique d’identités pour l’espace de noms spécifié (en même temps).
Lorsque la recherche correspond à plusieurs identifiants assemblés (comme pour l’événement 7), le premier identifiant lexicographique renvoyé par le graphique d’identités est sélectionné (`a.b@yahoo.co.uk` dans l’exemple).

+++

### Étape 2 : assemblage de lectures

À intervalles réguliers (selon l’intervalle de recherche en amont sélectionné), l’assemblage de relecture recalcule les données historiques en fonction de la version la plus récente du graphique d’identités, au moment de l’intervalle.

+++ Détails

Avec un assemblage de relecture se produisant à 2023-05-13 16:30, avec une configuration de fenêtre de recherche arrière de 24 heures, certains événements de l’exemple sont réassemblés (indiqué par ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Heure | ID persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID assemblé<br/> (après groupement en direct) | ID assemblé<br/> (après relecture 24 heures) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Avec l’assemblage de relecture se produisant à 2023-05-13 16:30, avec une configuration de période de recherche arrière de 7 jours, tous les événements de l’exemple sont réassemblés.


| | Heure | ID persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID assemblé<br/> (après groupement en direct) | ID assemblé<br/> (après relecture 7 jours) |
|---|---|---|---|---|---|
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non défini* | `246` | `a.b@yahoo.co.uk` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Étape 3 : demande d’accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, l’identifiant associé est supprimé dans tous les enregistrements pour l’utilisateur concerné par la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet qu’a une demande d’accès à des informations personnelles (par exemple à 2023-05-13 18 h 00) sur les exemples d’événements.

| | Heure | ID persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Identifiant assemblé (après demande d’accès à des informations personnelles) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Le jeu de données d’événement dans Adobe Experience Platform, auquel vous souhaitez appliquer un groupement, doit comporter une colonne qui identifie un visiteur sur chaque ligne, l’ **ID persistant**. Par exemple, un identifiant visiteur généré par une bibliothèque d’AppMeasurements Adobe Analytics ou un ECID généré par le service d’identité Experience Platform.
- L’ID persistant doit également être [défini comme une identité](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) dans le schéma.
- Le graphique d’identités d’Experience Platform Identity Service doit comporter un espace de noms (par exemple `Email` ou `Phone`) que vous souhaitez utiliser lors de l’assemblage pour résoudre l’ **identifiant transitoire**. Pour plus d’informations, voir [Service d’identité Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/home) .

>[!NOTE]
>
>Vous n’avez **pas** besoin d’une licence Real-time Customer Data Platform pour le groupement basé sur les graphiques. Le package **Prime** ou version ultérieure de Customer Journey Analytics inclut les droits Experience Platform Identity Service requis.


## Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Les horodatages ne sont pas pris en compte lors de l’interrogation de l’identifiant transitoire à l’aide de l’espace de noms spécifié. Il est donc possible qu’un identifiant persistant soit associé à un identifiant transitoire à partir d’un enregistrement dont l’horodatage est antérieur.
- Aucun support d’appareil partagé. Lorsque plusieurs identités sont renvoyées, en interrogant le graphique d’identités à l’aide d’un espace de noms, la première identité lexicographique est utilisée.
- Le renvoi des identités dans le graphique d’identités est limité à trois mois. Vous utiliseriez des identités de renvoi si vous n’utilisez pas d’application Experience Platform, telle que Real-time Customer Data Platform, pour remplir le graphique d’identités.
- Les [barrières de sécurité Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) s’appliquent. Voir, par exemple, les [limites statiques](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits) suivantes :
   - Nombre maximal d’identités dans un graphique : 50.
   - Nombre maximal de liens vers une identité pour une ingestion par lots unique : 50.
   - Nombre maximal d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 20.
   - Nombre minimum d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 2.
