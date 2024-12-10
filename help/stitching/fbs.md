---
title: Groupement basé sur les champs
description: Explication du groupement basé sur les champs
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 15%

---

# Groupement basé sur les champs

Dans le groupement basé sur les champs, vous spécifiez un jeu de données d’événement, ainsi que l’identifiant persistant (cookie) et l’identifiant transitoire (ID de personne) pour ce jeu de données. Le groupement basé sur les champs crée une nouvelle colonne d’identifiant assemblé dans le nouveau jeu de données assemblé et met à jour cette colonne d’identifiant assemblé en fonction des lignes ayant un identifiant transitoire pour cet identifiant persistant spécifique. <br/>Vous pouvez utiliser l’assemblage basé sur les champs lors de l’utilisation de Customer Journey Analytics comme solution autonome (sans accès au service Identity Experience Platform et au graphique d’identités associé). Ou, lorsque vous ne souhaitez pas utiliser le graphique d’identités disponible.

![Groupement basé sur les champs](/help/stitching/assets/fbs.png)

## Fonctionnement du groupement basé sur les champs

L’assemblage effectue au moins deux transmissions de données dans un jeu de données donné.

- **Groupement en direct** : tente de grouper chaque accès (événement) au fur et à mesure. Les accès provenant des appareils &quot;nouveaux&quot; au jeu de données (qui ne sont jamais authentifiés) ne sont généralement pas regroupés à ce niveau. Les accès provenant d’appareils déjà reconnus sont immédiatement regroupés.

- **Assemblage en lecture** : &quot;relit&quot; les données en fonction des identifiants uniques (identifiants transitoires) appris. Cette étape est l’endroit où les accès provenant d’appareils précédemment inconnus (identifiants persistants) sont regroupés (en identifiants transitoires). La relecture est déterminée par deux paramètres : **frequency** et **lookback window**. Adobe propose les combinaisons suivantes de ces paramètres :
   - **Recherche en amont quotidienne à une fréquence quotidienne** : les données sont relues chaque jour avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   - **Recherche en amont hebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont hebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la relecture hebdomadaire suivante.
   - **Recherche en amont bihebdomadaire sur une fréquence hebdomadaire** : les données sont relues une fois par semaine avec un intervalle de recherche en amont bihebdomadaire (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins de deux semaines ne sont pas retraitées avant la relecture hebdomadaire suivante.
   - **Recherche en amont mensuelle sur une fréquence hebdomadaire** : les données sont relues chaque semaine avec un intervalle de recherche en amont mensuel (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’un mois ne sont pas retraitées avant la relecture hebdomadaire suivante.

- **Confidentialité** : lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée, tout regroupement de cette identité entre des événements non authentifiés doit être annulé.

  >[!IMPORTANT]
  >
  >Le processus de désassemblage, dans le cadre des demandes d’accès à des informations personnelles, a changé début 2025. Le processus de désassemblage en cours récupère les événements à l’aide de la dernière version des identités connues. Cette réaffectation d&#39;événements à une autre identité peut avoir des conséquences juridiques indésirables. Pour remédier à ces problèmes, à partir de 2025, le nouveau processus de désassemblage met à jour les événements qui sont soumis à la demande d’accès à des informations personnelles avec l’ID persistant.
  > 


Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un visiteur doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois reconnu, un appareil est assemblé en direct à partir de ce moment.

### Étape 1 : assemblage en direct

L’assemblage en direct tente de regrouper chaque événement au moment de la collecte sur des appareils et canaux connus.

+++ Détails

Prenons l’exemple suivant, où Bob enregistre différents événements dans le cadre d’un jeu de données d’événement.

*Données telles qu&#39;elles apparaissent le jour de leur collecte :*

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après groupement dynamique) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 appareils** | | **4 personnes** :<br/>`246`, `Bob`, `3579`, `81911` |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes. Les événements non authentifiés sur les appareils reconnus sont assemblés en direct.

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements, à l’exception des événements 1, 8, 9 et 10, sont assemblés en direct (ils utilisent tous l’identifiant `Bob`). L’assemblage en direct &quot;résout&quot; l’identifiant assemblé pour les événements 4, 6 et 12.

Les données différées (données avec un horodatage de plus de 24 heures) sont traitées de manière &quot;optimale&quot;, tout en établissant la priorité du regroupement des données actives pour une qualité optimale.

+++

### Étape 2 : assemblage de lectures

À intervalles réguliers (une fois par semaine ou une fois par jour, selon l’intervalle de recherche en amont choisi), l’assemblage de relecture recalcule les données historiques en fonction des appareils qu’il reconnaît maintenant. Si un appareil envoie initialement des données alors qu’il n’est pas authentifié, puis se connecte, la réexécution du regroupement lie ces événements non authentifiés à la bonne personne.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après groupement dynamique) | Identifiant assemblé (après relecture) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 appareils** | | **4 personnes** :<br/>`246`, `Bob`, `3579`, `81911` | **2 personnes** :<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, les événements 1 et 10 sont assemblés à la suite de la relecture, laissant uniquement les événements 8 et 9 désassemblés. Et réduire la mesure des personnes (cumulée) à 2.

+++

### Étape 3 : demande d’accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, l’identifiant associé est supprimé dans tous les enregistrements pour l’utilisateur concerné par la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet qu’a une demande d’accès à des informations personnelles pour Bob sur les données après leur traitement. Les lignes où Bob est authentifié sont supprimées (2, 3, 5, 7 et 11), ainsi que la suppression de Bob comme identifiant transitoire pour les autres lignes.

*Les mêmes données après une demande d’accès à des informations personnelles pour Bob :*

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après groupement dynamique) | Identifiant assemblé (après relecture) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après demande d’accès à des informations personnelles) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 appareils** | | **4 personnes** :<br/>246, `Bob`, `3579`, `81911` | **2 personnes** :<br/>Bob, `3579` |  | **3 personnes** :<br/>`246`, `3579`, `81911` |

+++

## Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Le jeu de données d’événement dans Adobe Experience Platform, auquel vous souhaitez appliquer un groupement, doit comporter deux colonnes qui permettent d’identifier les visiteurs :

   - Un **identifiant persistant**, un identifiant disponible sur chaque ligne. Par exemple, un identifiant visiteur généré par une bibliothèque d’AppMeasurements Adobe Analytics ou un ECID généré par le service Adobe Experience Platform Identity.
   - Un **identifiant transitoire**, un identifiant disponible uniquement sur certaines lignes. Par exemple, un nom d’utilisateur ou une adresse e-mail chiffré une fois qu’un visiteur s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant. Le regroupement considère ce champ comme contenir les informations d’identification de la personne. Pour de meilleurs résultats de regroupement, un identifiant transitoire doit être envoyé dans les événements du jeu de données au moins une fois pour chaque identifiant persistant. Si vous prévoyez d’inclure ce jeu de données dans une connexion de Customer Journey Analytics, il est préférable que les autres jeux de données aient également un identifiant commun similaire.

- Les deux colonnes (identifiant persistant et identifiant transitoire) doivent être définies en tant que champ d’identité avec un espace de noms d’identité dans le schéma pour le jeu de données que vous souhaitez assembler. Lors de l’utilisation du groupement d’identités dans Real-time Customer Data Platform, à l’aide du groupe de champs [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), vous devez toujours ajouter des champs d’identité avec un espace de noms d’identité. Cette identification des champs d’identité est requise, car le groupement de Customer Journey Analytics ne prend pas en charge le groupe de champs `identityMap`. Lors de l’ajout d’un champ d’identité dans le schéma, tout en utilisant le groupe de champs `identityMap`, ne définissez pas le champ d’identité supplémentaire comme identité principale. La définition d’un champ d’identité supplémentaire comme identité principale interfère avec le groupe de champs `identityMap` utilisé pour Real-time Customer Data Platform.

## Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Les capacités de recomposition de données actuelles sont limitées à une étape (identifiant persistant à identifiant transitoire). La recomposition de données à plusieurs étapes (par exemple, un identifiant persistant à un identifiant transitoire, puis à un autre identifiant transitoire) n’est pas prise en charge.
- Si un appareil est partagé par plusieurs personnes et que le nombre total de transitions entre les utilisateurs dépasse 50 000, Customer Journey Analytics cesse de regrouper les données pour cet appareil.
- Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
- L’assemblage est sensible à la casse. Pour les jeux de données générés par le biais du connecteur source Analytics, Adobe recommande de vérifier les règles VISTA ou les règles de traitement qui s’appliquent au champ d’identifiant transitoire. Cette révision permet de s’assurer qu’aucune de ces règles n’introduit de nouvelles formes du même ID. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans le champ ID temporaire sur une partie seulement des événements.
- L’assemblage ne combine ni ne concatène des champs.
- Le champ d’identifiant transitoire doit contenir un seul type d’identifiant (les identifiants d’un seul espace de noms). Par exemple, le champ ID temporaire ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
- Si plusieurs événements se produisent avec le même horodatage pour le même ID persistant, mais avec des valeurs différentes dans le champ ID transitoire, l’assemblage sélectionne l’ID en fonction de l’ordre alphabétique. Ainsi, si l’ID persistant A comporte deux événements avec le même horodatage et que l’un d’eux spécifie Bob et l’autre spécifie Ann, l’assemblage sélectionne Ann.
- Soyez prudent lorsque les identifiants transitoires contiennent des valeurs d’espace réservé, par exemple `Undefined`. Pour plus d’informations, consultez la [FAQ](faq.md) .

