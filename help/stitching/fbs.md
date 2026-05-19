---
title: Groupement basé sur les champs
description: Explique le concept et le fonctionnement du groupement basé sur les champs.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
TQID: https://experienceleague.adobe.com/xqNEj5V-fQTo-8j5S9Ad-5ZezRjjr8kdt2Xmx0U8xDI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d682e1e729402bff7a3f6e3625402f57deee21ad
workflow-type: tm+mt
source-wordcount: 1902
ht-degree: 82%

---

# Regroupement basé sur les champs

Dans le groupement basé sur les champs, vous spécifiez un jeu de données d’événement ainsi que l’identifiant persistant (cookie) et l’identifiant de personne pour ce jeu de données. L’assemblage basé sur les champs tente de rendre les informations de l’ID de personne disponibles pour l’analyse des données Customer Journey Analytics, pour tout événement anonyme provenant d’un ID persistant spécifique.  Ces informations sont récupérées à partir des lignes qui possèdent un ID de personne pour cet ID persistant spécifique.

Si les informations de l’ID de personne ne peuvent pas être récupérées pour un événement, l’ID persistant est utilisé à la place pour cet événement *désassemblé*. Par conséquent, dans une [vue de données](/help/data-views/data-views.md) associée à une [connexion](/help/connections/overview.md) qui contient le jeu de données activé pour le groupement, le composant ID de personne contient soit la valeur de l’ID de personne, soit la valeur de l’ID persistant au niveau de l’événement.

Vous pouvez utiliser l’assemblage basé sur les champs lors de l’utilisation de Customer Journey Analytics en tant que solution autonome (vous n’avez pas accès au service d’identités d’Experience Platform et au graphique d’identités associé). Ou lorsque vous ne souhaitez pas utiliser le graphique d’identité disponible.

![Regroupement basé sur les champs](/help/stitching/assets/fbs.png)


## IdentityMap

L’assemblage basé sur les champs prend en charge l’utilisation du [`identityMap`groupe de champs](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#identity) dans les scénarios suivants :

- Utilisation de l’identité principale dans les espaces de noms `identityMap` pour définir l’identifiant persistant :
   - Si plusieurs identités principales sont trouvées dans différents espaces de noms, les identités des espaces de noms sont triées par ordre lexicographique et la première identité est sélectionnée.
   - Si plusieurs identités principales sont trouvées dans un seul espace de noms, la première identité principale lexicographique disponible est sélectionnée.

  Dans l’exemple ci-dessous, les espaces de noms et les identités génèrent une liste d’identités principales triées, et en fin de compte l’identité sélectionnée.

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


- Utilisation de l’espace de noms `identityMap` pour définir l’identifiant persistant ou l’identifiant de personne, ou les deux :
   - Si plusieurs valeurs d’identifiant persistant ou d’identifiant de personne sont présentes dans un espace de noms `identityMap`, la première valeur lexicographique disponible est utilisée.
   - Les espaces de noms pour l’identifiant persistant et l’identifiant de personne doivent être mutuellement exclusifs.

  Dans l’exemple ci-dessous, vous avez sélectionné ECID comme espace de noms à utiliser. Cette sélection génère une liste d’identités triées, et en fin de compte l’identité sélectionnée.

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

Le groupement effectue au moins deux passages sur les données d’un jeu de données spécifique.

- **Assemblage en direct** : tente d’assembler chaque accès (événement) au fur et à mesure qu’ils se produisent. Les accès à partir d’appareils considérés comme *nouveaux* dans le jeu de données (qui ne se sont jamais authentifiés) ne sont généralement pas assemblés à ce niveau. Les accès à partir d’appareils reconnus sont assemblés immédiatement.

- **Relecture d’assemblage** : *relit* les données en fonction d’identifiants uniques (identifiants de personnes). C’est à cette étape que les accès provenant d’appareils auparavant inconnus (identifiants persistants) sont assemblés (en identifiants de personne). Deux paramètres déterminent la relecture : **fréquence** et **intervalle de recherche en amont**. Adobe propose les combinaisons suivantes de ces paramètres :
   - **Recherche en amont quotidienne à une fréquence quotidienne** : les données sont relues chaque jour avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les profils non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   - **Recherche en amont hebdomadaire à une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont hebdomadaire (voir [options](overview.md#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins strict. Toutefois, les données dégroupées datant de moins d’une semaine ne sont pas retraitées avant la relecture hebdomadaire suivante.
   - **Recherche en amont bihebdomadaire à une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont bihebdomadaire (voir [options](overview.md#)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins strict. Toutefois, les données dégroupées datant de moins de deux semaines ne sont pas retraitées avant la relecture hebdomadaire suivante.
   - **Recherche en amont mensuelle à une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont mensuel (voir [options](overview.md#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins strict. Toutefois, les données dégroupées datant de moins d’un mois ne sont pas retraitées avant la relecture hebdomadaire suivante.

- **Confidentialité** : lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée, tout groupement de cette identité entre des événements non authentifiés doit être annulé.

  >[!IMPORTANT]
  >
  >Le processus de dégroupement, dans le cadre des demandes d’accès à des informations personnelles , change début 2025. Le processus de dégroupement actuel regroupe les événements à l’aide de la dernière version des identités connues. Cette réaffectation d’événements à une autre identité pourrait avoir des conséquences juridiques indésirables. Pour résoudre ces problèmes, à partir de 2025, le nouveau processus de dégroupement met à jour les événements qui font l’objet de la demande d’accès à des informations personnelles avec l’identifiant persistant.
  > 


Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un profil doit être authentifié dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois qu’un appareil est reconnu, il fait partie du groupement en direct à partir de ce moment.

### Étape 1 : groupement en direct

Le groupement en direct vise à associer chaque événement, dès sa collecte, aux appareils et canaux connus.

+++ Détails

Prenons l’exemple suivant, où Bob enregistre différents événements dans le cadre d’un jeu de données d’événement.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Événement | Date et heure | ID persistant (ID de cookie) | ID de personne | ID résultant (après assemblage dynamique) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 12/05/2023 12:02 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 appareils** | | **4 personnes** :<br/>`246`, `Bob`, `3579`, `81911` |

Les événements authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes. Les événements non authentifiés sur les appareils reconnus sont groupés en direct.

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements, à l’exception des événements 1, 8, 9 et 10, sont groupés en direct (ils utilisent tous l’identifiant `Bob`). L’assemblage en direct « résout » l’identifiant obtenu pour les événements 4, 6 et 12.

Les données différées (données dont la date et l’heure datent de plus de 24 heures) sont traitées selon le principe du « meilleur effort », tout en donnant la priorité au groupement des données actuelles pour une qualité maximale.

+++ 

### Étape 2 : relecture du groupement

À intervalles réguliers (une fois par semaine ou une fois par jour selon la période de recherche arrière choisie), la relecture du groupement recalcule les données historiques en fonction des appareils reconnus sur le moment. Si un appareil envoie initialement des données alors qu’il n’est pas authentifié et se connecte ensuite, la relecture du groupement lie ces événements non authentifiés à la bonne personne.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Événement | Date et heure | ID persistant (ID de cookie) | ID de personne | ID résultant (après assemblage dynamique) | Identifiant obtenu (après relecture) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 12/05/2023 12:02 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Flèche vers le haut](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) | `Bob` ![Flèche vers le haut](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 appareils** | | **4 personnes** :<br/>`246`, `Bob`, `3579`, `81911` | **2 personnes** :<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, les événements 1 et 10 sont groupés à la suite de la relecture, laissant uniquement les événements 8 et 9 dégroupés, et réduisant ainsi la mesure Personnes (cumulative) à 2.

+++ 

### Étape 3 : demande d’accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, toute information d’identifiant définie par le processus de groupement sur la valeur d’ID de personne est mise à jour dans tous les enregistrements vers une valeur d’ID persistant pour l’utilisateur faisant l’objet de la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet d’une demande d’accès à des informations personnelles pour Bob sur les données après leur traitement. Les lignes où Bob est authentifié sont supprimées (2, 3, 5, 7 et 11). Bob est supprimé en tant qu’ID de personne pour d’autres lignes.

*Les mêmes données après une demande d’accès à des informations personnelles pour Bob :*

| Événement | Date et heure | ID persistant (ID de cookie) | ID de personne | ID résultant (après assemblage dynamique) | Identifiant obtenu (après relecture) | ID de personne | Identifiant obtenu (après demande d’accès à des informations personnelles) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 12/05/2023 12:02 | `246` | Bob ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![Cercle - Suppression](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) | `Bob` | ![Cercle - Suppression](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) | `Bob` | ![Cercle - Suppression](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![Cercle - Suppression](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flèche vers la droite](/help/assets/icons/ArrowRight.svg) | `Bob` ![Flèche vers le bas](/help/assets/icons/ArrowDown.svg) | `Bob` ![Flèche vers le haut](/help/assets/icons/ArrowUp.svg) | ![Cercle - Suppression](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 appareils** | | **4 personnes**:<br/>246, `Bob`, `3579`, `81911` | **2 personnes** :<br/>Bob, `3579` |  | **3 personnes** :<br/>`246`, `3579`, `81911` |

+++ 

## Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Le jeu de données d’événement dans Adobe Experience Platform auquel appliquer un groupement doit comporter deux colonnes permettant d’identifier les profils :

   - Un **identifiant persistant**, un identifiant présent sur chaque ligne. Il peut s’agir, par exemple, d’un identifiant visiteur généré par une bibliothèque Adobe Analytics AppMeasurement ou d’un ECID généré par Adobe Experience Platform Identity Service.
   - Un **identifiant de personne**, un identifiant présent sur certaines lignes seulement. Par exemple, un nom d’utilisatation ou une adresse e-mail chiffré(e) une fois qu’une personne s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant de votre choix. Le mécanisme de groupement considère que ce champ contient l’identifiant réel de la personne. Pour obtenir les meilleurs résultats de groupement, un identifiant de personne doit être transmis dans les événements du jeu de données au moins une fois pour chaque identifiant persistant. Si vous prévoyez d’inclure ce jeu de données dans une connexion Customer Journey Analytics, il est préférable que les autres jeux de données aient également un identifiant commun similaire.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Restrictions

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Les capacités de recomposition de données actuelles sont limitées à une étape (identifiant persistant à identifiant de personne). La réassociation de données sur plusieurs étapes (par exemple, un identifiant persistant à un identifiant transitoire, puis à un autre identifiant transitoire) n’est pas prise en charge.
- Si plusieurs personnes partagent un appareil et que le nombre total de transitions entre les utilisateurs dépasse 50 000, Customer Journey Analytics cesse d’assembler les données de cet appareil.
- Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
- Le groupement est sensible à la casse. Pour les jeux de données générés par le biais du connecteur source Analytics, Adobe recommande de vérifier les règles VISTA ou les règles de traitement qui s’appliquent au champ d’ID de personne. Cette vérification garantit qu’aucune de ces règles n’introduit de nouvelles formes du même identifiant. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans le champ ID de personne sur une partie seulement des événements.
- Le groupement ne combine ni ne concatène les champs.
- Le champ ID de personne doit contenir un seul type dʼidentifiant (c.-à-d. des identifiants dʼun seul espace de noms). Par exemple, le champ ID de personne ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
- Si plusieurs événements se produisent à la même date et heure pour le même ID persistant, mais avec des valeurs différentes dans le champ ID de personne, le groupement sélectionne l’ID en fonction de lʼordre alphabétique. Ainsi, si lʼID persistant A a deux événements à la même date et à la même heure et que lʼun des événements mentionne Bob et lʼautre Anne, le groupement basé sélectionne Anne.
- Faites attention aux scénarios où les ID de personne contiennent des valeurs d’espace réservé, par exemple `Undefined`. Pour plus d’informations, consultez la [FAQ](faq.md).
- Vous ne pouvez pas utiliser le même espace de noms pour l’ID persistant et l’ID de personne. Les espaces de noms doivent s’exclure mutuellement.
