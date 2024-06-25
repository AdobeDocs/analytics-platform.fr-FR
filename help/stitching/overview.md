---
title: Présentation de l’assemblage
description: Présentation du groupement.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 83e568d686a541bb6472a33dc0a7400cf6e8de2a
workflow-type: tm+mt
source-wordcount: '3712'
ht-degree: 12%

---

# Groupement

{{select-package}}

Le groupement d’identités (ou simplement le groupement) est une puissante fonctionnalité qui accroît la capacité d’un jeu de données d’événement à l’analyse cross-canal. L’analyse cross-canal est un cas d’utilisation principal que Customer Journey Analytics peut traiter, ce qui vous permet de combiner et d’exécuter des rapports de manière transparente sur plusieurs jeux de données de différents canaux, en fonction d’un identifiant commun (ID de personne).

Lorsque vous combinez des jeux de données avec des identifiants de personne similaires, l’attribution est transférée sur plusieurs appareils et canaux. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur rencontre un problème avec sa commande, puis appelle votre équipe du service client pour l’aider à résoudre ce problème. Avec l’analyse cross-canal, vous pouvez attribuer des événements du centre d’appel à la publicité sur laquelle ils ont cliqué à l’origine.

Malheureusement, tous les jeux de données basés sur un événement qui font partie de votre connexion en Customer Journey Analytics ne sont pas suffisamment renseignés avec des données pour prendre en charge cette attribution prête à l’emploi. En particulier, les jeux de données d’expérience web ou mobiles ne disposent souvent pas d’informations d’identification de personne réelles sur tous les événements.

L’assemblage permet de recomposer les identités dans les lignes d’un jeu de données, en s’assurant que l’ID de personne (ID assemblé) est disponible sur chaque événement. L’assemblage examine les données utilisateur des sessions authentifiées et non authentifiées afin de déterminer la valeur d’ID transitoire commun (ID de personne) qui peut être utilisée comme ID assemblé. Cette recomposition permet de résoudre des enregistrements disparates sur un seul identifiant assemblé à analyser au niveau de la personne, plutôt qu’au niveau de l’appareil ou du cookie.

Customer Journey Analytics prend en charge deux types de groupement : le groupement basé sur les champs et le groupement basé sur les graphiques.

## Conditions préalables

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables, vous risquez de ne pas pouvoir effectuer correctement l’analyse cross-canal.

Avant d’utiliser le groupement, assurez-vous que votre organisation est préparée avec les éléments suivants :

- L’assemblage comprend la fusion de données utilisateur authentifiées et non authentifiées. Veillez à respecter les lois et réglementations en vigueur, y compris l’obtention des autorisations nécessaires de l’utilisateur final, avant d’activer le groupement sur un jeu de données d’événement. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations.

- Importez les données souhaitées dans Adobe Experience Platform :

   - Pour les données Adobe Analytics, voir [Utilisation des données de suite de rapports Adobe Analytics dans Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Pour d’autres types de données, consultez [Créer un schéma](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) et [Ingérer des données](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) dans la documentation d’Adobe Experience Platform.

Vous bénéficiez d’une analyse cross-canal si vous combinez un ou plusieurs de vos jeux de données assemblés à d’autres jeux de données, tels que les données du centre d’appels, dans le cadre de la définition de votre connexion de Customer Journey Analytics. Cette configuration de connexion suppose que ces autres jeux de données contiennent déjà un ID de personne sur chaque ligne, similaire à l’ID associé.


## Limites

>[!IMPORTANT]
>
>- Pas de prise en charge de l’utilisation de `identityMap` comme identifiant persistant. Vous devez définir un identifiant spécifique dans le jeu de données (par exemple, `ECID`) comme identifiant persistant.
>
>- Appliquez également toute modification que vous apportez au schéma du jeu de données d’événement source au nouveau schéma du jeu de données assemblé, sinon il rompt le jeu de données assemblé.
>
>- Si vous supprimez le jeu de données source, le jeu de données assemblé cesse le traitement et est supprimé par le système.
>
>- Les libellés d’utilisation des données ne sont pas propagés automatiquement au schéma de jeu de données assemblé. Si des libellés d’utilisation des données sont appliqués au schéma du jeu de données source, vous devez appliquer ces libellés manuellement au schéma du jeu de données assemblé. Voir [Gestion des libellés d’utilisation des données dans Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) pour plus d’informations.

L’assemblage est une fonctionnalité innovante et robuste, mais son utilisation est limitée.

- Seuls les jeux de données dʼévénement sont pris en charge. D’autres jeux de données, tels que les jeux de données de recherche, ne sont pas pris en charge.
- L’assemblage ne transforme pas le champ utilisé pour le groupement d’aucune manière. L’assemblage utilise la valeur du champ spécifié telle qu’elle existe dans le jeu de données désassemblé dans le lac de données.
- Le processus dʼassemblage est sensible à la casse. Par exemple, si le mot &quot;Bob&quot; apparaît parfois dans le champ et que le mot &quot;BOB&quot; apparaît, ces ID sont traités comme deux personnes distinctes.

Assurez-vous de ne pas confondre le groupement avec :

- La fusion de plusieurs jeux de données. L’assemblage s’applique à un seul jeu de données. La fusion des jeux de données se produit suite à la configuration d’une connexion de Customer Journey Analytics et à la sélection du même ID de personne dans les jeux de données sélectionnés de la connexion.

- La jointure de deux jeux de données. Dans Customer Journey Analytics, une jointure est souvent utilisée pour les recherches ou les classifications dans Analysis Workspace. Bien que l’assemblage utilise la fonctionnalité de jointure, le processus lui-même implique plus que des jointures.


## Groupement basé sur les champs

Vous spécifiez un jeu de données d’événement ainsi que l’identifiant persistant (cookie) et l’identifiant transitoire (ID de personne) pour ce jeu de données. Le groupement basé sur les champs crée une nouvelle colonne d’identifiant assemblé dans le nouveau jeu de données assemblé et met à jour cette colonne d’identifiant assemblé en fonction des lignes ayant un identifiant transitoire pour cet identifiant persistant spécifique. <br/>Vous pouvez utiliser l’assemblage basé sur les champs lors de l’utilisation de Customer Journey Analytics comme solution autonome (sans accès au service Identity Experience Platform et au graphique d’identités associé). Ou, lorsque vous ne souhaitez pas utiliser le graphique d’identités disponible.

![Groupement basé sur les champs](/help/stitching/assets/fbs.png)

### Fonctionnement du groupement basé sur les champs

L’assemblage effectue au moins deux transmissions de données dans un jeu de données donné.

- **Groupement en direct**: tente de grouper chaque accès (événement) au fur et à mesure. Les accès provenant des appareils &quot;nouveaux&quot; au jeu de données (qui ne sont jamais authentifiés) ne sont généralement pas regroupés à ce niveau. Les accès provenant d’appareils déjà reconnus sont immédiatement regroupés.

- **Groupement de relecture**: &quot;relit&quot; les données en fonction des identifiants uniques (identifiants transitoires) appris. Cette étape est l’endroit où les accès provenant d’appareils précédemment inconnus (identifiants persistants) sont regroupés (en identifiants transitoires). Adobe offre deux intervalles de relecture :
   - **Qualité**: les données sont relues chaque jour avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   - **Hebdomadaire**: les données sont lues une fois par semaine avec l’intervalle de recherche en amont sélectionné (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la relecture hebdomadaire suivante.

- **Privacy**: lorsque des demandes liées à la confidentialité sont reçues, en plus de la suppression de l’identité demandée, tout regroupement de cette identité entre des événements non authentifiés doit être annulé.

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un visiteur doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois reconnu, un appareil est assemblé en direct à partir de ce moment.

#### Étape 1 : assemblage en direct

L’assemblage en direct tente de regrouper chaque événement au moment de la collecte sur des appareils et canaux connus.

+++ Détails

Prenons l’exemple suivant, où Bob enregistre différents événements dans le cadre d’un jeu de données d’événement.

*Données telles qu’elles apparaissent le jour de leur collecte :*

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
| | | **3 périphériques** | | **4 personnes**:<br/>`246`, `Bob`, `3579`, `81911` |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes. Les événements non authentifiés sur les appareils reconnus sont assemblés en direct.

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements, à l’exception des événements 1, 8, 9 et 10, sont assemblés en direct (ils utilisent tous la variable `Bob` ). L’assemblage en direct &quot;résout&quot; l’identifiant assemblé pour les événements 4, 6 et 12.

Les données différées (données avec un horodatage de plus de 24 heures) sont traitées de manière &quot;optimale&quot;, tout en établissant la priorité du regroupement des données actives pour une qualité optimale.

+++

#### Étape 2 : assemblage de lectures

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
| | | **3 périphériques** | | **4 personnes**:<br/>`246`, `Bob`, `3579`, `81911` | **2 personnes**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, les événements 1 et 10 sont assemblés à la suite de la relecture, laissant uniquement les événements 8 et 9 désassemblés. Et réduire la mesure des personnes (cumulée) à 2.

+++

#### Étape 3 : demande d’accès à des informations personnelles

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
| | | **3 périphériques** | | **4 personnes**:<br/>246, `Bob`, `3579`, `81911` | **2 personnes**:<br/>Bob, `3579` |  | **3 personnes**:<br/>`246`, `3579`, `81911` |

+++

### Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Le jeu de données d’événement dans Adobe Experience Platform, auquel vous souhaitez appliquer un groupement, doit comporter deux colonnes qui permettent d’identifier les visiteurs :

   - A **identifiant persistant**, un identifiant disponible sur chaque ligne. Par exemple, un identifiant visiteur généré par une bibliothèque d’AppMeasurements Adobe Analytics ou un ECID généré par le service Adobe Experience Cloud Identity.
   - A **identifiant transitoire**, un identifiant disponible uniquement sur certaines lignes. Par exemple, un nom d’utilisateur ou une adresse e-mail chiffré une fois qu’un visiteur s’authentifie. Vous pouvez utiliser pratiquement n’importe quel identifiant. Le regroupement considère ce champ comme contenir les informations d’identification de la personne. Pour de meilleurs résultats de regroupement, un identifiant transitoire doit être envoyé dans les événements du jeu de données au moins une fois pour chaque identifiant persistant. Si vous prévoyez d’inclure ce jeu de données dans une connexion de Customer Journey Analytics, il est préférable que les autres jeux de données aient également un identifiant commun similaire.

- Les deux colonnes (identifiant persistant et identifiant transitoire) doivent être définies en tant que champ d’identité avec un espace de noms d’identité dans le schéma pour le jeu de données que vous souhaitez assembler. Lors de l’utilisation de la combinaison d’identités dans Real-time Customer Data Platform, à l’aide de la variable [`identityMap` groupe de champs](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), vous devez toujours ajouter des champs d’identité avec un espace de noms d’identité. Cette identification des champs d’identité est requise, car le regroupement de Customer Journey Analytics ne prend pas en charge la variable `identityMap` groupe de champs. Lors de l’ajout d’un champ d’identité dans le schéma, tout en utilisant la variable `identityMap` , ne définissez pas le champ d’identité supplémentaire comme identité principale. La définition d’un champ d’identité supplémentaire comme identité principale interfère avec la variable `identityMap` groupe de champs utilisé pour Real-time Customer Data Platform.

### Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les champs :

- Les capacités de recomposition de données actuelles sont limitées à une étape (identifiant persistant à identifiant transitoire). La recomposition de données à plusieurs étapes (par exemple, un identifiant persistant à un identifiant transitoire, puis à un autre identifiant transitoire) n’est pas prise en charge.
- Si un appareil est partagé par plusieurs personnes et que le nombre total de transitions entre les utilisateurs dépasse 50 000, Customer Journey Analytics cesse de regrouper les données pour cet appareil.
- Les mappages d’identifiants personnalisés utilisés dans votre organisation ne sont pas pris en charge.
- L’assemblage est sensible à la casse. Pour les jeux de données générés par le biais du connecteur source Analytics, Adobe recommande de vérifier les règles VISTA ou les règles de traitement qui s’appliquent au champ d’identifiant transitoire. Cette révision permet de s’assurer qu’aucune de ces règles n’introduit de nouvelles formes du même ID. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans le champ ID temporaire sur une partie seulement des événements.
- L’assemblage ne combine ni ne concatène des champs.
- Le champ d’identifiant transitoire doit contenir un seul type d’identifiant (les identifiants d’un seul espace de noms). Par exemple, le champ ID temporaire ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
- Si plusieurs événements se produisent avec le même horodatage pour le même ID persistant, mais avec des valeurs différentes dans le champ ID transitoire, l’assemblage sélectionne l’ID en fonction de l’ordre alphabétique. Ainsi, si l’ID persistant A comporte deux événements avec le même horodatage et que l’un d’eux spécifie Bob et l’autre spécifie Ann, l’assemblage sélectionne Ann.
- Soyez prudent lorsque les identifiants transitoires contiennent des valeurs d’espace réservé, par exemple : `Undefined`. Voir [FAQ](faq.md) pour plus d’informations.


## Groupement basé sur les graphiques

Vous spécifiez un jeu de données d’événement ainsi que l’identifiant persistant (cookie) et l’espace de noms de l’identifiant transitoire (ID de personne) pour ce jeu de données. Le groupement basé sur des graphiques crée une nouvelle colonne pour l’identifiant assemblé dans le nouveau jeu de données assemblé. Ensuite, utilise l’identifiant persistant pour interroger le graphique d’identités à partir du service d’identité Experience Platform, à l’aide de l’espace de noms spécifié, pour mettre à jour l’identifiant associé.

![Groupement basé sur les graphiques](/help/stitching/assets/gbs.png)

### Fonctionnement du groupement basé sur les graphiques

L’assemblage effectue au moins deux transmissions de données dans un jeu de données donné.

- **Groupement en direct**: tente de grouper chaque accès (événement) au fur et à mesure de son arrivée, à l’aide de l’identifiant persistant pour rechercher l’identifiant transitoire de l’espace de noms sélectionné en interrogeant le graphique d’identités. Si l’identifiant transitoire est disponible à partir de la recherche, cet identifiant transitoire est immédiatement assemblé.

- **Groupement de relecture**: &quot;relit&quot; les données en fonction des identités mises à jour du graphique d’identités. Cette étape est l’endroit où les accès provenant d’appareils précédemment inconnus (ID persistants) sont assemblés lorsque le graphique d’identités a résolu l’identité d’un espace de noms. Adobe offre deux intervalles de relecture :
   - **Qualité**: les données sont relues chaque jour avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   - **Hebdomadaire**: les données sont relues une fois par semaine avec l’intervalle de recherche en amont (voir [options](#options)). Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la relecture hebdomadaire suivante.

- **Privacy**: lorsque des demandes liées à la confidentialité sont reçues, en plus de supprimer l’identité demandée du jeu de données source, tout regroupement de cette identité entre des événements non authentifiés doit être annulé. En outre, l’identité doit être supprimée du graphique d’identités afin d’empêcher de futurs regroupements graphiques pour cette identité spécifique.

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un visiteur doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois reconnu, un appareil est assemblé en direct à partir de ce moment.

Tenez compte des deux graphiques d’identités suivants pour les identifiants persistants `246` et `3579`, comment ces graphiques d’identités sont mis à jour au fil du temps et comment ces mises à jour affectent les étapes du groupement basé sur les graphiques.

![Graphique d’identités 246](assets/identity-graph-246.svg)
![Graphique d’identités 3579](assets/identity-graph-3579.svg)

Vous pouvez afficher un graphique d’identités au fil du temps pour un profil spécifique à l’aide de la variable [Visionneuse de graphique d’identités](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Voir aussi [Logique de liaison d’Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) pour mieux comprendre la logique utilisée lors de la liaison d’identités.

#### Étape 1 : assemblage en direct

L’assemblage en direct tente d’assembler chaque événement, lors de la collecte, à des informations connues à ce moment du graphique d’identités.

+++ Détails

| | Heure | Identifiant persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Identifiant assemblé (après groupement dynamique) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Vous pouvez voir comment l’identifiant assemblé est résolu pour chaque événement. Selon l’heure, l’identifiant persistant et la recherche du graphique d’identités pour l’espace de noms spécifié (en même temps).
Lorsque la recherche correspond à plusieurs identifiants assemblés (comme pour l’événement 7), le premier identifiant lexicographique renvoyé par le graphique d’identités est sélectionné (`a.b@yahoo.co.uk` dans l’exemple).

+++

#### Étape 2 : assemblage de lectures

À intervalles réguliers (selon l’intervalle de recherche en amont sélectionné), l’assemblage de relecture recalcule les données historiques en fonction de la version la plus récente du graphique d’identités, au moment de l’intervalle.

+++ Détails

Avec un assemblage de relecture se produisant à 2023-05-13 16:30, avec une configuration de fenêtre de recherche en amont de 24 heures, certains événements de l’échantillon sont réassemblés (comme indiqué par ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Heure | Identifiant persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Identifiant assemblé<br/>(après groupement dynamique) | Identifiant assemblé<br/>(après la relecture 24 heures) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Avec l’assemblage de relecture se produisant à 2023-05-13 16:30, avec une configuration de période de recherche arrière de 7 jours, tous les événements de l’exemple sont réassemblés.


| | Heure | Identifiant persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Identifiant assemblé<br/>(après groupement dynamique) | Identifiant assemblé<br/>(après relecture pendant 7 jours) |
|---|---|---|---|---|---|
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Réinitialiser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### Étape 3 : demande d’accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, l’identifiant associé est supprimé dans tous les enregistrements pour l’utilisateur concerné par la demande d’accès à des informations personnelles.

+++ Détails

Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet qu’a une demande d’accès à des informations personnelles (par exemple à 2023-05-13 18 h 00) sur les exemples d’événements.

| | Heure | Identifiant persistant<br/>`ECID` | Espace de noms<br/>`Email` ![Graphique](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Identifiant assemblé (après demande d’accès à des informations personnelles) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### Conditions préalables

Les conditions préalables suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Le jeu de données d’événement dans Adobe Experience Platform, auquel vous souhaitez appliquer une combinaison, doit comporter une colonne qui identifie un visiteur sur chaque ligne, la variable **identifiant persistant**. Par exemple, un identifiant visiteur généré par une bibliothèque d’AppMeasurements Adobe Analytics ou un ECID généré par le service Adobe Experience Cloud Identity.
- le graphique d’identités d’Experience Cloud Identity Service doit avoir un espace de noms (par exemple `Email`, ou `Phone`) que vous souhaitez utiliser lors de l’assemblage pour résoudre l’événement **identifiant transitoire**. Voir [Service Experience Platform Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) pour plus d’informations.


### Limites

Les restrictions suivantes s’appliquent spécifiquement au groupement basé sur les graphiques :

- Les horodatages ne sont pas pris en compte lors de l’interrogation de l’identifiant transitoire à l’aide de l’espace de noms spécifié. Il est donc possible qu’un identifiant persistant soit associé à un identifiant transitoire à partir d’un enregistrement dont l’horodatage est antérieur.
- Aucun support d’appareil partagé. Lorsque plusieurs identités sont renvoyées, en interrogant le graphique d’identités à l’aide d’un espace de noms, la première identité lexicographique est utilisée.
- Le renvoi des identités dans le graphique d’identités est limité à trois mois. Vous utiliseriez des identités de renvoi si vous n’utilisez pas d’application Experience Platform, telle que Real-time Customer Data Platform, pour remplir le graphique d’identités.
- La variable [Protections Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) appliquez. Voir, par exemple, les [limites statiques](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Nombre maximal d’identités dans un graphique : 50.
   - Nombre maximal de liens vers une identité pour une ingestion par lots unique : 50.
   - Nombre maximal d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 20.
   - Nombre minimum d’identités dans un enregistrement XDM pour l’ingestion de graphiques : 2.


## Utilisation de l’assemblage

Une fois que votre organisation a atteint toutes les [conditions préalables](#prerequisites) et comprend les [limitations](#limitations) et méthode de groupement spécifique ([champ](#limitations-1) et [graphique](#limitations-2)), vous pouvez suivre ces étapes pour commencer à utiliser le groupement dans Customer Journey Analytics.

### Options

Sélectionnez les options de groupement. Le package du Customer Journey Analytics détermine les options disponibles pour la durée de renvoi initial, l’intervalle de recherche en amont, la fréquence de relecture et le nombre maximal de jeux de données autorisés pour le groupement.

| | Customer Journey Analytics<br/>Sélectionner | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Durée de renvoi groupé une fois | 13 mois | 13 mois | 25 mois |
| Intervalle de recherche en amont et fréquence de relecture | <li>1 jour, tous les jours</li><li>jusqu’à 7 jours, hebdomadaire</li> | <li>1 jour, tous les jours</li><li>jusqu’à 14 jours, hebdomadaire</li> | <li>1 jour, tous les jours</li><li>jusqu’à 30 jours, hebdomadaire</li> |
| Nombre maximal de jeux de données autorisés pour le groupement | 5 | 10 | 15 |

### Demande d’assistance

1. Contactez le service clientèle d’Adobe avec les informations suivantes :

   - Demande d’activation du groupement.
   - Identifiant du jeu de données pour le jeu de données que vous souhaitez recomposer.
   - Nom de colonne (chemin d’identité et espace de noms) de l’identifiant persistant du jeu de données souhaité (l’identifiant qui apparaît sur chaque ligne).
   - Pour le groupement basé sur les champs, nom de colonne de l’identifiant transitoire pour le jeu de données souhaité (l’identifiant de personne, qui agit également comme un lien entre les jeux de données dans le contexte d’une connexion). Pour le groupement basé sur un graphique, l’espace de noms d’identité à utiliser pour l’interrogation du graphique d’identités.
   - Votre préférence en termes de intervalle de recherche en amont et de fréquence de relecture. Consultez votre module de Customer Journey Analytics pour [options](#options) disponible.
   - Nom de la sandbox.


2. Le service clientèle d’Adobe travaille avec le service d’ingénierie d’Adobe pour activer l’assemblage à la réception de votre demande. Une fois activé, un nouveau jeu de données recomposées contenant une nouvelle colonne d’identifiant assemblé s’affiche dans Adobe Experience Platform. Le service clientèle d’Adobe peut fournir l’identifiant du nouveau jeu de données.

3. Lorsque l’Adobe est activé pour la première fois, il fournit un renvoi des données assemblées. Consultez votre module de Customer Journey Analytics pour [option](#options) disponible.

4. Si vous souhaitez utiliser le nouveau jeu de données assemblé dans une analyse cross-canal, vous devez ajouter le nouveau jeu de données assemblé à un [connection](../connections/overview.md) en Customer Journey Analytics. Ajoutez ensuite tout autre jeu de données requis pour l’analyse cross-canal, puis sélectionnez l’identifiant de personne correct pour chaque jeu de données.

5. [Créez une vue de données](/help/data-views/create-dataview.md) basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, vous pouvez exécuter l’analyse des rapports du Customer Journey Analytics sur les canaux et les appareils.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

