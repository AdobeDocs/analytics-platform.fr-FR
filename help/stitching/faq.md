---
title: Questions fréquentes sur le regroupement
description: Découvrez les questions fréquentes sur le groupement.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 332c9240399e429d971855ab1aa685bd4d07b86e
workflow-type: tm+mt
source-wordcount: '2149'
ht-degree: 84%

---

# Questions fréquentes

Voici quelques questions fréquentes à propos de l’assemblage :

## Déplacement entre les canaux

+++ De quelle manière puis-je utiliser le regroupement pour voir comment les gens passent d’un canal à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et créez un projet Workspace vierge.
2. Cliquez sur l’onglet **[!UICONTROL ** Visualisations **]** à gauche, puis faites glisser une visualisation **[!UICONTROL ** Flux **]** dans la zone de travail à droite.
3. Cliquez sur l’onglet **[!UICONTROL ** Composants **]** à gauche, puis faites glisser la dimension **[!UICONTROL ** Identifiant de jeu de données **]** dans l’emplacement central intitulé **[!UICONTROL ** Dimension ou élément **]**.
4. Ce rapport de flux est interactif. Pour étendre les flux aux pages suivantes ou précédentes, sélectionnez l’une des valeurs. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension Identifiant du jeu de données, vous pouvez utiliser un jeu de données de recherche.

+++

## Relecture

+++ Jusqu’à quelle date antérieure les profils sont-ils relus lors d’un assemblage ?

La période de relecture dépend de la fréquence souhaitée de relecture des données. Par exemple, si vous configurez l’assemblage de manière à relire les données une fois par semaine, la période de relecture est de sept jours. Si vous configurez l’assemblage pour qu’il relise les données tous les jours, la période de relecture des données est d’un jour.

+++

## Appareils partagés

+++ Comment les appareils partagés sont-ils gérés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’identifiant de personne a priorité sur l’identifiant persistant. Ainsi, les appareils partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même appareil).

Voir le cas d’utilisation [Appareils partagés](/help/use-cases/stitching/shared-devices.md) pour plus d’informations.

+++

## Nombreux identifiants persistants

+++ Comment l’assemblage gère-t-il les situations où une seule personne possède un grand nombre d’identifiants persistants ?

Dans certains cas, une personne individuelle peut être associée à un grand nombre d’identifiants persistants. Par exemple, un individu efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Pour le regroupement basé sur les champs, le nombre d’identifiants persistants n’a pas d’importance par rapport à l’identifiant de personne. Un seul utilisateur ou une seule utilisatrice peut appartenir à n’importe quel nombre d’appareils sans que cela n’ait d’incidence sur la capacité de Customer Journey Analytics à effectuer l’assemblage entre les appareils.

Pour le groupement basé sur les graphiques, une seule personne peut avoir de nombreux identifiants persistants dans le graphique d’identités. L’assemblage basé sur un graphique utilise l’identifiant persistant en fonction de l’espace de noms spécifié. S’il existe d’autres identifiants persistants pour le même espace de noms, le premier identifiant persistant lexicographique est utilisé.

+++

## Processus de regroupement

+++ Une fois que j’ai contacté mon équipe Adobe en charge des comptes pour obtenir les informations souhaitées, combien de temps faut-il pour que le jeu de données recomposées soit disponible ?

Le regroupement en direct est disponible environ une semaine après l’activation de la fonction de regroupement par Adobe. La disponibilité du renvoi dépend de la quantité de données existantes. Les petits jeux de données (moins d’un million d’événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard d’événements par jour) peuvent prendre une semaine ou plus.

+++

## Analyse entre appareils et analyse cross-canal

+++ Quelle est la différence entre l’analyse entre appareils (une fonctionnalité classique d’Analytics) et l’analyse cross-canal ?

L’[analyse entre appareils](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview) est une fonctionnalité classique, spécifique à Adobe Analytics qui vous permet de comprendre le comportement des personnes sur plusieurs périphériques. Elle offre deux workflows pour lier les données de l’appareil : le regroupement basé sur les champs et le graphique d’appareil.

L’analyse cross-canal est un cas d’utilisation spécifique à Customer Journey Analytics qui vous permet de comprendre le comportement des personnes à la fois sur les appareils et les canaux. Elle assemble l’ID de personne d’un jeu de données, ce qui permet de combiner facilement ce jeu de données avec d’autres. Cette fonctionnalité s’exécute de la même manière que l’assemblage basé sur les champs de l’analyse entre appareils, avec cependant une implémentation distincte en raison de l’architecture des données qui diffère entre la version classique d’Analytics et Customer Journey Analytics. Pour plus d’informations, voir [Assemblage](overview.md) et le cas d’utilisation [Analyse cross-canal](../use-cases/cross-channel/cross-channel.md).

+++

## Confidentialité

+++ Comment l’assemblage gère-t-il les demandes d’accès à des informations personnelles ?

Adobe gère les demandes d’accès à des informations personnelles conformément aux lois locales et internationales. Adobe propose [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/fr/docs/experience-platform/privacy/home) pour soumettre des demandes d’accès et de suppression de données. Ces demandes s’appliquent aussi bien aux jeux de données originaux qu’aux jeux de données recomposés.

>[!IMPORTANT]
>
>Le processus de dégroupement, dans le cadre des demandes d’accès à des informations personnelles , change début 2025. Le processus de dégroupement actuel regroupe les événements à l’aide de la dernière version des identités connues. Cette réaffectation d’événements à une autre identité pourrait avoir des conséquences juridiques indésirables. Pour résoudre ces problèmes, à partir de 2025, le nouveau processus de dégroupement met à jour les événements qui font l’objet de la demande d’accès à des informations personnelles avec l’identifiant persistant.
> 

À titre d’illustration, imaginez les données suivantes pour les identités et les événements avant et après l’assemblage.

| Mappage d’identité | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ECID | Bob | CustId |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Jeu de données d’événements | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| | 2 | ts1 | 123 | ECID | Bob | CustId |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Jeu de données assemblé | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne | identifiant obtenu | espace de noms assemblé |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | Bob | CustId |
| | 2 | ts1 | 123 | ECID | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |


**Processus actuel pour les demandes d’accès à des informations personnelles**

Lorsqu’une demande d’accès à des informations personnelles est reçue pour le client avec le CustID Bob, les lignes comportant des entrées barrées sont supprimées. Les autres événements sont assemblés à l’aide du mappage d’identités. Par exemple, le premier identifiant assemblé dans le jeu de données assemblé est mis à jour en tant qu’**Alex**.

| Mappage d’identité | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Jeu de données d’événements | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Jeu de données assemblé | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne | identifiant obtenu | espace de noms assemblé |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |


**Nouveau processus pour les demandes d&#39;accès à des informations personnelles**

Lorsqu’une demande d’accès à des informations personnelles est reçue pour le client avec le CustID Bob, les lignes comportant des entrées barrées sont supprimées. Les autres événements sont regroupés à l’aide de l’identifiant persistant. Par exemple, le premier identifiant assemblé dans le jeu de données assemblé est mis à jour en tant que **123**.

| Mappage d’identité | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ECID | Alex | CustId |


| Jeu de données d’événements | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId |


| Jeu de données assemblé | ID | date et heure | ID persistant | espace de nom persistant | ID de personne | espace de nom de personne | identifiant obtenu | espace de noms assemblé |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **123** | ECID |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ECID | Alex | CustId | Alex | CustId |

+++

## Valeurs d’identifiants persistants vides

+++ Que se passe-t-il si le champ de lʼidentifiant persistant dʼun ou de plusieurs événements est vide ?

Si le champ d’identifiant persistant est vide sur un événement d’un jeu de données assemblé , l’identifiant obtenu pour cet événement est déterminé de l’une des deux façons suivantes :

* Si le champ ID de personne n’est pas vide, Customer Journey Analytics utilise la valeur de l’ID de personne comme ID obtenu.
* Si le champ ID de personne est vide, Customer Journey Analytics laisse également vide l’ID obtenu. Dans ce cas, l’ID persistant, l’ID de personne et l’ID obtenu sont tous vides pour l’événement. Ces types d’événements sont ignorés de toute connexion Customer Journey Analytics utilisant le jeu de données assemblé là où l’ID obtenu a été choisi comme ID de personne.

+++


## Valeurs d’identifiants de personne non définies

+++ Que se passe-t-il si le champ dʼidentifiant de personne dans un ou plusieurs événements possède des valeurs génériques, telles que `Undefined` ?

Attention au cas de « réduction de personne », qui se produit lorsqu’un assemblage est appliqué à des données qui utilisent des valeurs génériques pour les identifiants temporaires. Dans l’exemple de tableau ci-dessous, les identifiants de personne non définis provenant d’un jeu de données récupéré à partir d’un système CRM sont renseignés avec la valeur « Non défini », ce qui entraîne une représentation incorrecte des personnes.

| Événement | Date et heure | ID persistant (ID de cookie) | Identifiant temporaire | identifiant obtenu (après relecture) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 12/05/2023 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Non défini | **Non défini** |
| 4 | 2023-05-12 12:04 | 456 | - | **Non défini** |
| 5 | 2023-05-12 12:05 | 789 | Non défini | **Non défini** |
| 6 | 2023-05-12 12:06 | 012 | Non défini | **Non défini** |
| 7 | 2023-05-12 12:07 | 012 | - | **Non défini** |
| 8 | 2023-05-12 12:03 | 789 | Non défini | **Non défini** |
| 9 | 2023-05-12 12:09 | 456 | - | **Non défini** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 appareils** | **2 personnes** :<br/> événements 1, 4, 7, 9, 10 ignorés | **2 personnes** :<br/> Cory, Non authentifiée (réduites à une seule personne) |

+++

## Comparaison des mesures

+++ Quelles sont les différences entre les mesures des jeux de données assemblés Customer Journey Analytics par rapport à celles des jeux de données Customer Journey Analytics non assemblés et celles dʼAdobe Analytics ?

Certaines mesures de Customer Journey Analytics sont similaires à celles d’Analytics, mais dʼautres sont très différentes, en fonction des éléments que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données groupées de Customer Journey Analytics** | **Données non groupées de Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate avec CDA** |
| ----- | ----- | ----- | ----- |
| **Personnes** = nombre d’ID de personne distincts où l’ID obtenu est choisi comme ID de personne. Le nombre de **Personnes** peut être plus ou moins élevé que les **Visiteurs ou visiteuses uniques** dans Adobe Analytics classique, en fonction du résultat du processus de regroupement. | **Personnes** = nombre d’identifiants de personne distincts en fonction de la colonne sélectionnée en tant qu’identifiant de personne. Les **personnes** présentes dans les jeux de données du connecteur de source Analytics sont semblables aux **visiteurs et visiteuses uniques** dans Adobe Analytics classique, si `endUserIDs._experience.aaid.id` est sélectionné en tant qu’identifiant de personne dans Customer Journey Analytics. | **Visiteurs uniques** = nombre dʼidentifiants de visiteur distincts. Le nombre de **Visiteurs uniques** peut être différent du nombre d’**ECID** distincts. | Voir [Personnes](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/people). |
| **Sessions** : définies en fonction des paramètres de session dans la vue de données Customer Journey Analytics. Le processus dʼassemblage peut combiner des sessions individuelles provenant de plusieurs appareils en une seule session. | **Sessions** : défini en fonction des paramètres de session spécifiés dans la vue de données Customer Journey Analytics. | **Visites** : voir [Visites](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/visits). | **Visites** : défini en fonction des paramètres de session réglés dans la [suite de rapports virtuelle CDA](https://experienceleague.adobe.com/en/docs/analytics/components/cda/setup). |
| **Événements** = nombre de lignes dans les données groupées dans Customer Journey Analytics. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Consultez toutefois les questions fréquentes ci-dessus concernant les lignes avec un identifiant persistant vide. | **Événements** = nombre de lignes dans les données non groupées dans Customer Journey Analytics. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Notez toutefois que si des événements possèdent un identifiant de personne vide dans les données non assemblées du lac de données Experience Platform, ces événements ne sont pas inclus dans Customer Journey Analytics. | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences). | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences). |

Dʼautres mesures peuvent être similaires dans Customer Journey Analytics et Adobe Analytics. Par exemple, le nombre total (1-100) dʼ[événements personnalisés](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/custom-events) Adobe Analytics est en principe très similaire dans Adobe Analytics classique et Customer Journey Analytics (à la fois pour les événements assemblés et non assemblés). [Les différences de fonctionnalités](/help/getting-started/aa-vs-cja/cja-aa.md), telles que la déduplication des événements entre Customer Journey Analytics et Adobe Analytics, peuvent entraîner des incohérences entre les deux produits.

+++

## Mappage d’identité

+++ Est-ce que Customer Journey Analytics peut utiliser les champs de mappage d’identité ?

Oui, Customer Journey Analytics peut utiliser les champs de mappage d’identité pour l’assemblage [basé sur les champs](/help/stitching/fbs.md#identitymap) et l’assemblage [basé sur un graphique](/help/stitching/gbs.md#identitymap).

+++

## Basculer vers l’assemblage basé sur un graphique

+++ Les données devront-elles être ingérées à nouveau pour passer d’un assemblage basé sur les champs à un assemblage basé sur un graphique ?

Les données n’ont pas à être réingérées dans Experience Platform. Toutefois, les données doivent être reconfigurées dans Customer Journey Analytics. Procédez comme suit :

1. Configurez le nouveau jeu de données assemblé basé sur un graphique à l’aide de l’assemblage basé sur un graphique.
1. Créez une nouvelle connexion temporaire avec une très petite fenêtre temporelle de données.
1. Configurez le nouveau jeu de données basé sur un graphique dans le cadre de cette connexion temporaire.
1. Vérifiez avec cette nouvelle connexion temporaire si l’assemblage basé sur un graphique fonctionne correctement.
1. Si l’assemblage basé sur un graphique fonctionne comme prévu, demandez un renvoi de données supplémentaire pour le jeu de données basé sur un graphique, puis remplacez le jeu de données basé sur des champs dans votre connexion d’origine par le nouveau jeu de données basé sur un graphique.
1. Supprimez la connexion temporaire.

+++

## Perturbation des rapports

+++ Les rapports existants seront-ils altérés ?

Pas si vous suivez les étapes décrites ci-dessus. Sinon, contactez Adobe Consulting pour obtenir une assistance supplémentaire.

+++

## Activer un jeu de données pour le service d’identités

+++ Comment activer un jeu de données uniquement pour le service d’identités ? 

Assurez-vous qu’un jeu de données est activé pour qu’Identity Service puisse l’utiliser dans le groupement basé sur les graphiques.

Il n’est pas nécessaire d’être titulaire d’une licence pour que Real-Time Customer Data Platform puisse utiliser l’assemblage basé sur un graphique. L’assemblage basé sur un graphique est basé sur un graphique d’identités disponible et non sur des profils clients en temps réel.

Pour vérifier un jeu de données existant et l’activer pour Identity Service uniquement, envoyez une requête `PATCH` au point d’entrée `/datasets` qui utilise uniquement la balise `unifiedIdentity` . Par exemple :

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

Si vous ne disposez pas d’une licence Real-Time CDP, toute utilisation de la balise `unifiedProfile` dans la requête renvoie une erreur.

Consultez [Créer un jeu de données activé pour Profil et Identité](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset) pour plus d’informations.

+++ 


## Valeurs d’espace de noms groupé

+++ Pourquoi les valeurs des espaces de noms groupés ne correspondent-elles pas toujours à la valeur d’espace de noms d’identité que vous pouvez utiliser dans un autre jeu de données dans la connexion CJA ?

Par défaut, les valeurs des espaces de noms assemblés sont en minuscules. Alors, `custEmail` devient `custemail`. Si vous disposez d’un autre jeu de données avec une valeur d’espace de noms d’identité de `custEmail`, les deux valeurs ne correspondent pas. Pour contourner ce comportement dans les rapports, vous pouvez utiliser la fonction de champ dérivé [lowercase()](/help/data-views/derived-fields/derived-fields.md#lowercase) pour correspondre aux valeurs de l’espace de noms d’identité.

+++
