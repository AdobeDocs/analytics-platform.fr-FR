---
title: Groupement basé sur les graphes
description: Explication du groupement basé sur les graphiques
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 98432804b71805c3714423dff577bbf80d5c92d1
workflow-type: tm+mt
source-wordcount: '1540'
ht-degree: 7%

---

# Groupement basé sur les graphes


Dans le groupement basé sur les graphiques, vous spécifiez un jeu de données d’événement, ainsi que l’identifiant persistant (cookie) et l’espace de noms de l’identifiant temporaire (ID de personne) pour ce jeu de données. L’assemblage basé sur des graphiques crée une colonne pour l’ID assemblé dans le nouveau jeu de données assemblé. Elle utilise ensuite l’identifiant persistant pour interroger le graphique d’identités d’Experience Platform Identity Service, à l’aide de l’espace de noms spécifié, afin de mettre à jour l’identifiant assemblé.

![Assemblage basé sur les graphiques](/help/stitching/assets/gbs.png)

## IdentityMap

Le groupement basé sur les graphiques prend en charge l’utilisation du groupe de champs [`identityMap`](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#identity) dans les scénarios suivants :

- Utilisation de l’identité principale dans `identityMap`’espace de noms pour définir l’ID persistant :
   - Si plusieurs identités principales sont trouvées dans différents espaces de noms, les identités des espaces de noms sont triées par ordre lexigraphique et la première identité est sélectionnée.
   - Si plusieurs identités principales sont trouvées dans un seul espace de noms, la première identité principale disponible au niveau lexicographique est sélectionnée.

  Dans l’exemple ci-dessous, les espaces de noms et les identités génèrent une liste d’identités principales triées, et finalement l’identité sélectionnée.

  <table style="table-layout:auto">
     <tr>
       <th>Espaces de noms</th>
       <th>Liste des identités</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Liste des identités triées</th>
      <th>Identité sélectionnée</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- Utilisation de `identityMap` espace de noms pour définir le persistentID :
   - Si plusieurs valeurs pour persistentID sont trouvées dans un espace de noms `identityMap`, la première identité disponible au niveau lexicographique est utilisée.

  Dans l’exemple ci-dessous, les espaces de noms et les identités génèrent une liste d’identités triées pour l’espace de noms sélectionné (ECID), et finalement l’identité sélectionnée.

  <table style="table-layout:auto">
     <tr>
       <th>Espaces de noms</th>
       <th>Liste des identités</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Liste des identités triées</th>
      <th>Identité sélectionnée</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## Fonctionnement de l’assemblage basé sur les graphiques

L’assemblage effectue au moins deux passages aux données d’un jeu de données donné.

- **Assemblage en direct** : tente d’assembler chaque accès (événement) au fur et à mesure qu’il arrive, à l’aide de l’identifiant persistant pour rechercher l’identifiant transitoire de l’espace de noms sélectionné en interrogeant le graphique d’identité. Si l’ID transitoire est disponible à partir de la recherche, il est immédiatement regroupé.

- **Groupement de relecture** : *relit* les données en fonction des identités mises à jour à partir du graphique d’identités. À cette étape, les accès provenant d’appareils inconnus précédemment (identifiants persistants) sont regroupés, car le graphique d’identité a résolu l’identité d’un espace de noms. La relecture est déterminée par deux paramètres : **fréquence** et **intervalle de recherche en amont**. Adobe propose les combinaisons de paramètres suivantes :
   - **Recherche en amont quotidienne à une fréquence quotidienne** : les données sont relues tous les jours avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   - **Recherche en amont hebdomadaire à une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont hebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la prochaine relecture hebdomadaire.
   - **Recherche en amont bihebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont bihebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins de deux semaines ne sont pas retraitées avant la prochaine relecture hebdomadaire.
   - **Recherche en amont mensuelle à une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont mensuel (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’un mois ne sont pas retraitées avant la prochaine relecture hebdomadaire.

- **Confidentialité** : lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée du jeu de données source, tout regroupement de cette identité sur des événements non authentifiés doit être annulé. En outre, l’identité doit être supprimée du graphique d’identités afin d’éviter tout groupement futur basé sur les graphiques pour cette identité spécifique.

  >[!IMPORTANT]
  >
  >Le processus de désassemblage, dans le cadre des demandes d’accès à des informations personnelles, change début 2025. Le processus de désassemblage actuel réassemble les événements à l’aide de la dernière version des identités connues. Cette réaffectation d&#39;événements à une autre identité pourrait avoir des conséquences juridiques indésirables. Pour résoudre ces problèmes, à partir de 2025, le nouveau processus d’assemblage met à jour les événements qui font l’objet de la demande d’accès à des informations personnelles avec l’identifiant persistant.
  > 

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un visiteur doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois qu’un appareil est reconnu, il est assemblé en direct à partir de ce moment.

Tenez compte des deux graphiques d’identités suivants pour la `246` et la `3579` des identifiants persistants, de la manière dont ces graphiques d’identités sont mis à jour au fil du temps et de la manière dont ces mises à jour affectent les étapes du groupement basé sur les graphiques.

![Graphique d’identités 246](assets/identity-graph-246.svg)
![Graphique d’identités 3579](assets/identity-graph-3579.svg)

Vous pouvez afficher un graphique d’identités au fil du temps pour un profil spécifique à l’aide de la [visionneuse de graphiques d’identités](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/identity-graph-viewer). Consultez également la section [Logique de liaison du service d’identités](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/identity-linking-logic) pour mieux comprendre la logique utilisée lors de la liaison d’identités.

### Étape 1 : Assemblage dynamique

L’assemblage en direct tente d’assembler chaque événement, lors de la collecte, aux informations connues à ce moment du graphique d’identité.

+++ Détails

| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID groupé (après le groupement dynamique) |
|--:|---|---|---|---|
| 1 | 12/05/2023 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non défini* | `246` |
| 2 | 12/05/2023 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non défini* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 13/05/2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 13/05/2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Vous pouvez voir comment l’identifiant assemblé est résolu pour chaque événement. En fonction de la durée, de l’identifiant persistant et de la recherche du graphique d’identité pour l’espace de noms spécifié (au même moment).
Lorsque la recherche est résolue sur plusieurs identifiants assemblés (comme pour l’événement 7), le premier identifiant lexicographique renvoyé par le graphique d’identité est sélectionné (`a.b@yahoo.co.uk` dans l’exemple).

+++

### Étape 2 : assemblage de lectures

À intervalles réguliers (en fonction de l’intervalle de recherche en amont choisi), le groupement de relecture recalcule les données historiques en fonction de la version la plus récente du graphique d’identité au moment de l’intervalle.

+++ Détails

Avec un groupement de relecture se produisant au 13/05/2023 à 16 h 30, avec une configuration d’intervalle de recherche en amont de 24 heures, certains événements de l’exemple sont regroupés à nouveau (indiqué par ![Relecture](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID groupé <br/>(après le groupement dynamique) | ID groupé <br/>(après relecture de 24 heures) |
|---|---|---|---|---|---|
| 2 | 12/05/2023 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 13/05/2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 13/05/2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Avec le groupement de relecture qui se produit au 13/05/2023 à 16 h 30, avec une configuration d’intervalle de recherche en amont de 7 jours, tous les événements de l’exemple sont regroupés à nouveau.


| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID groupé <br/>(après le groupement dynamique) | ID groupé <br/>(après relecture 7 jours) |
|---|---|---|---|---|---|
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 12/05/2023 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non défini* | `246` | `a.b@yahoo.co.uk` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 12/05/2023 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 13/05/2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 13/05/2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Étape 3 : demande d&#39;accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, l’ID regroupé est supprimé dans tous les enregistrements pour l’utilisateur faisant l’objet de la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet d’une demande d’accès à des informations personnelles (par exemple, au 2023-05-13 18:00) sur les exemples d’événements.

| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID groupé (après demande d’accès à des informations personnelles) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 12/05/2023 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| 2 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 12/05/2023 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| 3 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| 4 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| 5 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| 6 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 13/05/2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| 7 <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 13/05/2023 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Le jeu de données d’événement dans Adobe Experience Platform auquel vous souhaitez appliquer le groupement doit comporter une colonne qui identifie un visiteur sur chaque ligne, à savoir l’**identifiant persistant**. Il peut s’agir, par exemple, d’un identifiant visiteur généré par une bibliothèque Adobe Analytics AppMeasurement ou d’un ECID généré par Experience Platform Identity Service.
- L’identifiant persistant doit également être [défini en tant qu’identité](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) dans le schéma .
- Le graphique d’identités d’Experience Platform Identity Service doit comporter un espace de noms (par exemple `Email` ou `Phone`) que vous souhaitez utiliser lors du groupement pour résoudre l’**ID transitoire**. Voir [Experience Platform Identity Service](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/home) pour plus d’informations.

>[!NOTE]
>
>Vous n’avez **besoin**’une licence Real-time Customer Data Platform pour le groupement basé sur les graphiques. Le package **Prime** ou version ultérieure de Customer Journey Analytics inclut les droits requis pour Experience Platform Identity Service.


## Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Les dates et heures ne sont pas prises en compte lors de l’interrogation de l’ID temporaire à l’aide de l’espace de noms spécifié. Il est donc possible qu’un identifiant persistant soit associé à un identifiant temporaire d’un enregistrement qui a un horodatage antérieur.
- Dans les scénarios d’appareils partagés, où l’espace de noms du graphique contient plusieurs identités, la première identité lexicographique est utilisée. Si les limites et priorités d’espace de noms sont configurées dans le cadre de la publication des règles de liaison de graphiques, l’identité du dernier utilisateur authentifié est utilisée. Voir [Appareils partagés](/help/use-cases/stitching/shared-devices.md) pour plus d’informations.
- Il existe une limite stricte de trois mois de renvoi d’identités dans le graphique d’identités. Utilisez le remplissage d’identités si vous n’utilisez pas une application Experience Platform, telle que Real-time Customer Data Platform, pour renseigner le graphique d’identité.
- Les mécanismes de sécurisation [Identity Service](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/guardrails) s’appliquent. Voir, par exemple, les [limites statiques](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/guardrails#static-limits) suivantes :
   - Nombre maximal d’identités dans un graphique : 50.
   - Nombre maximal de liens vers une identité pour une ingestion par lots unique : 50.
   - Nombre maximal d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 20.
   - Nombre minimum d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 2.
