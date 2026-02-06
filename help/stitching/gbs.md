---
title: Assemblage basé sur les graphiques
description: Explique le concept et le fonctionnement du groupement basé sur les graphiques.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: b5afcfe2cac8aa12d7f4d0cf98658149707123e3
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 4%

---

# Rapprochement basé sur les graphiques

Dans le groupement basé sur les graphiques, vous spécifiez un jeu de données d’événement, l’identifiant persistant (cookie) de ce jeu de données et l’espace de noms d’identifiant de personne souhaité à partir du graphique d’identité. Le groupement basé sur les graphiques tente de rendre les informations d’ID de personne disponibles pour l’analyse des données Customer Journey Analytics sur n’importe quel événement. L’ID persistant est utilisé pour interroger le graphique d’identité à partir d’Experience Platform Identity Service afin d’obtenir l’ID de personne à partir de l’espace de noms spécifié.

Si les informations de l’ID de personne ne peuvent pas être récupérées pour un événement, l’ID persistant est utilisé à la place pour cet événement *désassemblé*. Par conséquent, dans une [vue de données](/help/data-views/data-views.md) associée à une [connexion](/help/connections/overview.md) qui contient le jeu de données activé pour le groupement, le composant de vue de données ID de personne contient la valeur de l’ID de personne ou la valeur de l’ID persistant au niveau de l’événement.


![Assemblage basé sur les graphiques](/help/stitching/assets/gbs.png)

## IdentityMap

Le groupement basé sur les graphiques prend en charge l’utilisation du groupe de champs [`identityMap`](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#identity) dans les scénarios suivants :

- Utilisation de l’identité principale dans les espaces de noms d’`identityMap` pour définir l’ID persistant :
   - Si plusieurs identités principales sont trouvées dans différents espaces de noms, les identités des espaces de noms sont triées par ordre lexicographique et la première identité est sélectionnée.
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

  Dans l’exemple ci-dessous, vous avez sélectionné ECID comme espace de noms à utiliser. Cette sélection entraîne une liste d’identités triées, et finalement l’identité sélectionnée.

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

- **Assemblage en direct** : tente d’assembler chaque accès (événement) au fur et à mesure qu’il arrive, à l’aide de l’identifiant persistant pour rechercher l’identifiant de personne pour l’espace de noms sélectionné en interrogeant le graphique d’identité. Si l’ID de personne est disponible à partir de la recherche, il est immédiatement regroupé.

- **Groupement de relecture** : *relit* les données en fonction des identités mises à jour à partir du graphique d’identités. À cette étape, les accès provenant d’appareils inconnus précédemment (identifiants persistants) sont regroupés, car le graphique d’identité a résolu l’identité d’un espace de noms. Deux paramètres déterminent la relecture : **fréquence** et **intervalle de recherche en amont**. Adobe propose les combinaisons de paramètres suivantes :
   - **Recherche en amont quotidienne à une fréquence quotidienne** : les données sont relues tous les jours avec un intervalle de recherche en amont de 24 heures. Cette option présente l’avantage que les relectures sont beaucoup plus fréquentes, mais les profils non authentifiés doivent s’authentifier le jour même de leur visite sur votre site.
   - **Recherche en amont hebdomadaire à une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont hebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la prochaine relecture hebdomadaire.
   - **Recherche en amont bihebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont bihebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins de deux semaines ne sont pas retraitées avant la prochaine relecture hebdomadaire.
   - **Recherche en amont mensuelle à une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont mensuel (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’un mois ne sont pas retraitées avant la prochaine relecture hebdomadaire.

- **Confidentialité** : lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée du jeu de données source, tout regroupement de cette identité sur des événements non authentifiés doit être annulé. En outre, l’identité doit être supprimée du graphique d’identités afin d’éviter tout groupement futur basé sur les graphiques pour cette identité spécifique.

  >[!IMPORTANT]
  >
  >Le processus de désassemblage, dans le cadre des demandes d’accès à des informations personnelles, change début 2025. Le processus de désassemblage actuel réassemble les événements à l’aide de la dernière version des identités connues. Cette réaffectation d&#39;événements à une autre identité pourrait avoir des conséquences juridiques indésirables. Pour résoudre ces problèmes, à partir de 2025, le nouveau processus d’assemblage met à jour les événements qui font l’objet de la demande d’accès à des informations personnelles avec l’identifiant persistant.
  > 

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un profil doit être authentifié dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois qu’un appareil est reconnu, il est assemblé en direct à partir de ce moment.

Tenez compte des deux mises à jour du graphique d’identités suivantes au fil du temps pour le visiteur A (avec l’ID persistant `246`) et le visiteur B (avec l’ID persistant `3579`), et de la manière dont ces mises à jour affectent les étapes du groupement basé sur les graphiques.

![Graphique d’identités 3579](assets/identity-graphs.svg)

Vous pouvez afficher un graphique d’identités au fil du temps pour un profil spécifique à l’aide de la [visionneuse de graphiques d’identités](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/identity-graph-viewer). Consultez également la section [Logique de liaison du service d’identités](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/identity-linking-logic) pour mieux comprendre la logique utilisée lors de la liaison d’identités.

### Étape 1 : Assemblage dynamique

L’assemblage en direct tente d’assembler chaque événement, lors de la collecte, aux informations connues à ce moment du graphique d’identité.

+++ Détails

| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID résultant (après assemblage dynamique) |
|--:|---|---|---|---|
| 1 | 12/05/2023 11:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) *non défini* | `246` |
| 2 | 12/05/2023 14:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 12/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 12/05/2023 17:00 | `3579` | `3579` ![Branche1](/help/assets/icons/Branch1.svg) *non défini* | `3579` |
| 5 | 12/05/2023 19:00 | `3579` | `3579` ![Branche1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 13/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 13/05/2023 16:30 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Vous pouvez voir comment l’identifiant obtenu est résolu pour chaque événement. Selon la durée, l’identifiant persistant et la recherche du graphique d’identité pour l’espace de noms d’ID de personne spécifié.
Lorsque la recherche est résolue sur plusieurs identifiants résultants (comme pour l’événement 7), le premier identifiant lexicographique renvoyé par le graphique d’identité est sélectionné (`a.b@yahoo.co.uk` dans l’exemple).

+++

### Étape 2 : assemblage de lectures

À intervalles réguliers (en fonction de l’intervalle de recherche en amont choisi), le groupement de relecture recalcule les données historiques en fonction de la version la plus récente du graphique d’identité au moment de l’intervalle.

+++ Détails

Avec un groupement de relecture se produisant au 13/05/2023 16:30, avec une configuration d’intervalle de recherche en amont de 24 heures, certains événements de l’exemple sont regroupés à nouveau (indiqué par ![Relecture](/help/assets/icons/Replay.svg)).

| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID résultant <br/>(après assemblage dynamique) | ID résultant <br/>(après relecture 24 heures) |
|---|---|---|---|---|---|
| 2 | 12/05/2023 14:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 12/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Relire](/help/assets/icons/Replay.svg) 4 | 12/05/2023 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Relire](/help/assets/icons/Replay.svg) 5 | 12/05/2023 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Relire](/help/assets/icons/Replay.svg) 6 | 13/05/2023 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](/help/assets/icons/Replay.svg) 7 | 13/05/2023 16:30 | `246` | `246` ![Branch1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Branch1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Avec le groupement de relecture qui se produit au 13/05/2023 16:30, avec une configuration d’intervalle de recherche en amont de 7 jours, tous les événements de l’exemple sont regroupés à nouveau.


| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID résultant <br/>(après assemblage dynamique) | ID résultant <br/>(après relecture 7 jours) |
|---|---|---|---|---|---|
| ![Relire](/help/assets/icons/Replay.svg) 1 | 12/05/2023 11:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) *non défini* | `246` | `a.b@yahoo.co.uk` |
| ![Relire](/help/assets/icons/Replay.svg) 2 | 12/05/2023 14:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](/help/assets/icons/Replay.svg) 3 | 12/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](/help/assets/icons/Replay.svg) 4 | 12/05/2023 17:00 | `3579` | `3579` ![Branche1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Relire](/help/assets/icons/Replay.svg) 5 | 12/05/2023 19:00 | `3579` | `3579` ![Branche1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Relire](/help/assets/icons/Replay.svg) 6 | 13/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Relire](/help/assets/icons/Replay.svg) 7 | 13/05/2023 16:30 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Étape 3 : demande d&#39;accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, l’ID obtenu est supprimé dans tous les enregistrements pour l’utilisateur faisant l’objet de la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet qu’une demande d’accès à des informations personnelles (par exemple, au 2023-05-13 18:00) a sur les exemples d’événements.

| | Heure | ID persistant <br/>`ECID` | Espace de noms <br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | Identifiant obtenu (après demande d’accès à des informations personnelles) |
|--:|---|---|---|---|
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 1 | 12/05/2023 11:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 2 | 12/05/2023 14:00 | `246` | `246`![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 3 | 12/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 4 | 12/05/2023 17:00 | `3579` | `3579` ![Branche1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 5 | 12/05/2023 19:00 | `3579` | `3579` ![Branche1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 6 | 13/05/2023 15:00 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 7 | 13/05/2023 16:30 | `246` | `246` ![Branche1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Branche1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Le jeu de données d’événement dans Adobe Experience Platform auquel vous souhaitez appliquer le groupement doit comporter une colonne qui identifie un profil sur chaque ligne, l’**identifiant persistant**. Il peut s’agir, par exemple, d’un identifiant visiteur généré par une bibliothèque Adobe Analytics AppMeasurement ou d’un ECID généré par Experience Platform Identity Service.
- Le graphique d’identités d’Experience Platform Identity Service doit être configuré au niveau de la sandbox, avant d’activer le groupement basé sur les graphiques.
   - Le graphique d’identité doit comporter un espace de noms (par exemple `Email` ou `Phone`) que vous souhaitez utiliser lors du groupement pour résoudre l’ID de personne.
   - Le graphique d’identités doit être renseigné avec des informations d’identités de tous les jeux de données pertinents (de type *événement* ou *profil* et qui contiennent au moins deux espaces de noms utiles avec des valeurs d’identifiant).
   - Tous les jeux de données contenant ces identités pertinentes doivent être [&#x200B; activés pour l’ingestion de données de graphique d’identités](faq.md#enable-a-dataset-for-the-identity-service). Cette activation garantit que les identités entrantes sont ajoutées au graphique au fil du temps à partir de toutes les sources nécessaires.
   - Si vous utilisez déjà le profil de données client en temps réel ou Adobe Journey Optimizer depuis un certain temps, le graphique doit déjà être configuré dans une certaine mesure.<br/>Si le renvoi du groupement historique est également requis pour le jeu de données activé avec le groupement basé sur les graphiques, le graphique doit déjà contenir des identités historiques pour l’ensemble de la période, afin d’obtenir les résultats de groupement souhaités.
- Si vous souhaitez utiliser le groupement basé sur des graphiques et que vous prévoyez que le jeu de données d’événement contribuera au graphique d’identité, vous devez [activer le jeu de données pour le service d’identités](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).
- L’ID persistant et l’ID de personne peuvent être utilisés avec [identityMap](#identitymap). Ou l’identifiant persistant et l’identifiant de personne peuvent être des champs du schéma XDM, auquel cas les champs doivent être [définis comme une identité](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity?lang=en) dans le schéma .

>[!NOTE]
>
>Vous n’avez **besoin**’une licence Real-time Customer Data Platform pour le groupement basé sur les graphiques. Le package **Prime** ou version ultérieure de Customer Journey Analytics inclut les droits requis pour Experience Platform Identity Service.


## Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Les dates et heures ne sont pas prises en compte lors de l’interrogation de l’ID de personne avec l’espace de noms spécifié. Il est donc possible qu’un ID persistant soit associé à un ID de personne provenant d’un enregistrement qui a un horodatage antérieur.
- Dans les scénarios d’appareils partagés, où l’espace de noms du graphique contient plusieurs identités, la première identité lexicographique est utilisée. Si les limites et priorités d’espace de noms sont configurées dans le cadre de la publication des règles de liaison de graphiques, l’identité du dernier utilisateur authentifié est utilisée. Voir [Appareils partagés](/help/use-cases/stitching/shared-devices.md) pour plus d’informations.
- Il existe une limite stricte de trois mois de renvoi d’identités dans le graphique d’identités. Utilisez le remplissage d’identités si vous n’utilisez pas une application Experience Platform, telle que Real-time Customer Data Platform, pour renseigner le graphique d’identité.
- Les mécanismes de sécurisation [Identity Service](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/guardrails) s’appliquent. Voir, par exemple, les [limites statiques](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/guardrails#static-limits) suivantes :
   - Nombre maximal d’identités dans un graphique : 50.
   - Nombre maximal de liens vers une identité pour une ingestion par lots unique : 50.
   - Nombre maximal d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 20.
   - Nombre minimum d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 2.
