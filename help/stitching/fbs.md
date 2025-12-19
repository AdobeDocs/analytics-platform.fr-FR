---
title: Rapprochement basé sur les champs
description: Explication du concept et du fonctionnement du groupement basé sur les champs
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 90a285fcd96866974087c53d402e85b4a2d83ccf
workflow-type: tm+mt
source-wordcount: '1713'
ht-degree: 10%

---

# Rapprochement basé sur les champs

Dans l’assemblage basé sur les champs, vous spécifiez un jeu de données d’événement ainsi que l’identifiant persistant (cookie) et l’identifiant de personne pour ce jeu de données. Le groupement basé sur les champs ajoute une nouvelle colonne d’ID groupé au jeu de données d’événement et met à jour cet ID groupé en fonction des lignes qui possèdent un ID de personne pour cet ID persistant spécifique. <br/>Vous pouvez utiliser l’assemblage basé sur les champs lors de l’utilisation de Customer Journey Analytics en tant que solution autonome (vous n’avez pas accès au service d’identités Experience Platform et au graphique d’identités associé). Ou, lorsque vous ne souhaitez pas utiliser le graphique d’identité disponible.

![Rapprochement basé sur les champs](/help/stitching/assets/fbs.png)


## IdentityMap

L’assemblage basé sur les champs prend en charge l’utilisation du groupe de champs [`identityMap`](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#identity) dans les scénarios suivants :

- Utilisation de l’identité principale dans les espaces de noms d’`identityMap` pour définir l’ID persistant :
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


- Utilisation de `identityMap`’espace de noms pour définir l’ID persistant ou l’ID de personne, ou les deux :
   - Si plusieurs valeurs d’ID persistant ou d’ID de personne sont trouvées dans un espace de noms `identityMap`, la première valeur disponible au niveau lexicographique est utilisée.
   - Les espaces de noms pour l’ID persistant et l’ID de personne doivent s’exclure mutuellement.

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

## Fonctionnement de l’assemblage basé sur les champs

L’assemblage effectue au moins deux passages aux données d’un jeu de données donné.

- **Assemblage en direct** : tente d’assembler chaque accès (événement) au fur et à mesure qu’il arrive. Les accès des appareils qui sont *nouveaux* au jeu de données (ne se sont jamais authentifiés) ne sont généralement pas regroupés à ce niveau. Les accès provenant d’appareils déjà reconnus sont immédiatement regroupés.

- **Groupement des relectures** : *relit* les données en fonction d’identifiants uniques (ID de personne). C’est à cette étape que les accès provenant d’appareils auparavant inconnus (identifiants persistants) sont regroupés (en identifiants de personne). La relecture est déterminée par deux paramètres : **fréquence** et **intervalle de recherche en amont**. Adobe propose les combinaisons de paramètres suivantes :
   - **Recherche en amont quotidienne à une fréquence quotidienne** : les données sont relues tous les jours avec un intervalle de recherche en amont de 24 heures. Cette option présente l’avantage que les relectures sont beaucoup plus fréquentes, mais les profils non authentifiés doivent s’authentifier le jour même de leur visite sur votre site.
   - **Recherche en amont hebdomadaire à une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont hebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la prochaine relecture hebdomadaire.
   - **Recherche en amont bihebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont bihebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins de deux semaines ne sont pas retraitées avant la prochaine relecture hebdomadaire.
   - **Recherche en amont mensuelle à une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont mensuel (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’un mois ne sont pas retraitées avant la prochaine relecture hebdomadaire.

- **Confidentialité** : lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée, tout regroupement de cette identité entre des événements non authentifiés doit être annulé.

  >[!IMPORTANT]
  >
  >Le processus de désassemblage, dans le cadre des demandes d’accès à des informations personnelles, change début 2025. Le processus de désassemblage actuel réassemble les événements à l’aide de la dernière version des identités connues. Cette réaffectation d&#39;événements à une autre identité pourrait avoir des conséquences juridiques indésirables. Pour résoudre ces problèmes, à partir de 2025, le nouveau processus d’assemblage met à jour les événements qui font l’objet de la demande d’accès à des informations personnelles avec l’identifiant persistant.
  > 


Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un profil doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois qu’un appareil est reconnu, il est assemblé en direct à partir de ce moment.

### Étape 1 : Assemblage dynamique

L’assemblage en direct tente d’assembler chaque événement lors de la collecte sur des appareils et des canaux connus.

+++ Détails

Prenons l’exemple suivant, où Robert enregistre différents événements dans le cadre d’un jeu de données d’événement.

*Données telles qu’elles s’affichaient le jour de leur collecte :*

| Événement | Date et heure | ID persistant (ID de cookie) | ID de personne | ID groupé (après le groupement dynamique) |
|---|---|---|---|---|
| 1 | 12/05/2023 12:01 | `246` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 12/05/2023 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 12/05/2023 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 4 | 12/05/2023 12:04 | `246` | - | **`Bob`** |
| 5 | 12/05/2023 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 12/05/2023 12:06 | `246` | - | **`Bob`** |
| 7 | 12/05/2023 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 12/05/2023 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 12/05/2023 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 12/05/2023 12:02 | `81911` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 12/05/2023 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 12 | 12/05/2023 12:12 | `81911` | - | **`Bob`** |
| | | appareils **3** | | **4 personnes**:<br/>`246`, `Bob`, `3579`, `81911` |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes. Les événements non authentifiés sur les appareils reconnus sont assemblés en direct.

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements, à l’exception des événements 1, 8, 9 et 10, sont assemblés en direct (ils utilisent tous l’identifiant `Bob`). L’assemblage en direct « résout » l’identifiant assemblé pour les événements 4, 6 et 12.

Les données différées (données dont l’horodatage date de plus de 24 heures) sont traitées selon le principe du « meilleur effort », tout en donnant la priorité à l’assemblage des données actuelles pour une qualité maximale.

+++ 

### Étape 2 : assemblage de lectures

À intervalles réguliers (une fois par semaine ou une fois par jour, selon l’intervalle de recherche en amont choisi), le groupement de relecture recalcule les données historiques en fonction des appareils qu’il reconnaît désormais. Si un appareil envoie initialement des données alors qu’il n’est pas authentifié, puis se connecte, le groupement de relecture lie ces événements non authentifiés à la bonne personne.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Événement | Date et heure | ID persistant (ID de cookie) | ID de personne | ID groupé (après le groupement dynamique) | ID groupé (après relecture) |
|---|---|---|---|---|---|
| 1 | 12/05/2023 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 12/05/2023 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 3 | 12/05/2023 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 12/05/2023 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 12/05/2023 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 12/05/2023 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 12/05/2023 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 12/05/2023 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 12/05/2023 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 12/05/2023 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 12/05/2023 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 12 | 12/05/2023 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | appareils **3** | | **4 personnes**:<br/>`246`, `Bob`, `3579`, `81911` | **2 personnes**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, les événements 1 et 10 sont assemblés à la suite de la relecture, laissant uniquement les événements 8 et 9 désassemblés. Et réduire la mesure Personnes (cumulative) à 2.

+++ 

### Étape 3 : demande d&#39;accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, l’ID regroupé est supprimé dans tous les enregistrements pour l’utilisateur faisant l’objet de la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet d’une demande d’accès à des informations personnelles pour Bob sur les données après leur traitement. Les lignes où Bob est authentifié sont supprimées (2, 3, 5, 7 et 11) ainsi que la suppression de Bob en tant qu’ID de personne pour d’autres lignes.

*Les mêmes données après une demande d’accès à des informations personnelles pour Bob :*

| Événement | Date et heure | ID persistant (ID de cookie) | ID de personne | ID groupé (après le groupement dynamique) | ID groupé (après relecture) | ID de personne | ID groupé (après demande d’accès à des informations personnelles) |
|---|---|---|---|---|---|---|---|
| 1 | 12/05/2023 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 12/05/2023 12:02 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 12/05/2023 12:03 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 12/05/2023 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 12/05/2023 12:05 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 12/05/2023 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 12/05/2023 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 12/05/2023 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 12/05/2023 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 12/05/2023 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 12/05/2023 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 12/05/2023 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | appareils **3** | | **4 people**:<br/>246, `Bob`, `3579`, `81911` | **2 personnes**:<br/>Bob, `3579` |  | **3 personnes**:<br/>`246`, `3579`, `81911` |

+++ 

## Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Le jeu de données d’événement dans Adobe Experience Platform auquel vous souhaitez appliquer un groupement doit comporter deux colonnes permettant d’identifier les profils :

   - Un **identifiant persistant**, un identifiant disponible sur chaque ligne. Il peut s’agir, par exemple, d’un identifiant visiteur généré par une bibliothèque Adobe Analytics AppMeasurement ou d’un ECID généré par Adobe Experience Platform Identity Service.
   - Un **ID de personne**, un identifiant disponible uniquement sur certaines lignes. Par exemple, un nom d’utilisateur ou une adresse e-mail haché une fois qu’un profil s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant de votre choix. Le groupement prend en compte ce champ pour contenir les informations de l’ID de personne réel. Pour de meilleurs résultats d’assemblage, un ID de personne doit être envoyé dans les événements du jeu de données au moins une fois pour chaque ID persistant. Si vous prévoyez d’inclure ce jeu de données dans une connexion Customer Journey Analytics, il est préférable que les autres jeux de données aient également un identifiant commun similaire.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Les fonctionnalités de recomposition actuelles sont limitées à une seule étape (identifiant persistant en identifiant de personne). La recréation en plusieurs étapes (par exemple, l’ID persistant vers un ID de personne, puis vers un autre ID de personne) n’est pas prise en charge.
- Si un appareil est partagé par plusieurs personnes et que le nombre total de transitions entre les utilisateurs dépasse 50 000, Customer Journey Analytics cesse d’assembler les données de cet appareil.
- Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
- Le groupement est sensible à la casse. Pour les jeux de données générés par le biais du connecteur source Analytics, Adobe recommande de vérifier les règles VISTA ou les règles de traitement qui s’appliquent au champ d’ID de personne. Cette révision permet de s’assurer qu’aucune de ces règles n’introduit de nouvelles formes du même ID. Par exemple, vous devez vous assurer qu’aucune règle VISTA ou de traitement n’introduit de minuscules dans le champ d’ID de personne sur une partie seulement des événements.
- L’assemblage ne combine ni ne concatène les champs.
- Le champ ID de personne doit contenir un seul type d’ID (identifiants provenant d’un seul espace de noms). Par exemple, le champ ID de personne ne doit pas contenir de combinaison d’ID de connexion et d’ID d’e-mail.
- Si plusieurs événements se produisent avec le même horodatage pour le même ID persistant, mais avec des valeurs différentes dans le champ ID de personne , l’assemblage sélectionne l’ID par ordre alphabétique. Ainsi, si l’ID persistant A comporte deux événements avec le même horodatage et que l’un des événements spécifie Bob et que l’autre spécifie Ann, l’assemblage sélectionne Ann.
- Faites attention aux scénarios où les ID de personne contiennent des valeurs d’espace réservé, par exemple `Undefined`. Voir la [FAQ](faq.md) pour plus d’informations.
- Vous ne pouvez pas utiliser le même espace de noms à la fois pour l’ID persistant et l’ID de personne. Les espaces de noms doivent s’exclure mutuellement.
