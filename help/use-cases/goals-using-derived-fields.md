---
title: Utiliser des champs dérivés pour créer des rapports sur les objectifs
description: Découvrez comment utiliser les champs dérivés pour créer des rapports sur les objectifs (cibles) dans vos projets Workspace.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 6%

---

# Utiliser des champs dérivés pour créer des rapports sur les objectifs

Ce cas d’utilisation décrit comment utiliser la puissance des champs dérivés pour définir des objectifs pour une dimension spécifique, puis utiliser ces objectifs dans votre projet Workspace.

Si vous ne connaissez pas les champs dérivés, reportez-vous aux sections [tutoriel](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html) et [documentation](../data-views/derived-fields/derived-fields.md) pour une introduction.


## Définir les objectifs

Pour définir des objectifs, créez un champ dérivé dans lequel vous définissez explicitement des valeurs numériques personnalisées, directement ou indirectement, à l’aide des valeurs issues de règles antérieures dans votre définition de champ dérivé.


### Objectifs mensuels des commandes de certificats-cadeaux

Vous souhaitez définir explicitement des objectifs pour vos commandes de certificats-cadeaux pour une période de quatre mois, allant de juillet 2023 à octobre 2023. Pour ce faire :

1. Créez un champ dérivé portant le nom `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Définissez des valeurs statiques, à l’aide d’une RÈGLE CASE WHEN, pour chaque mois, en définissant une **[!UICONTROL valeur numérique personnalisée]**. Consultez la règle Objectifs mensuels du produit ci-dessous.

   ![ Objectifs mensuels du produit ](assets/goals-derived-field-product-goals-1.png)


### Objectifs de chiffre d’affaires des canaux marketing

Vous souhaitez définir un objectif de chiffre d’affaires mensuel pour chacun de vos canaux marketing. Pour ce faire :

1. Créez un champ dérivé, à l’aide du modèle de fonction [Canaux marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) avec le nom `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Définissez toutes les règles pour identifier correctement chacun des canaux marketing en fonction d’une combinaison de règles ANALYSE D’URL et CASSE QUAND . Par exemple :

   ![Définition de règles pour le champ dérivé du canal marketing](assets/goals-derived-field-marketing-channel-1.png)

1. Définissez explicitement des valeurs statiques, représentant les objectifs de chiffre d’affaires mensuels, pour les canaux marketing spécifiques dans une règle CASE WHEN finale, en définissant une **[!UICONTROL valeur numérique personnalisée]**. Voir la règle de [!DNL Monthly Goal] ci-dessous.

   ![ Objectifs mensuels ](assets/goals-derived-field-marketing-channel-2.png)



## Utiliser les objectifs

Pour utiliser des objectifs dans votre projet Workspace, vous utilisez la fonctionnalité de mesure calculée afin de « normaliser » le champ dérivé à sa valeur statique d’origine. Cette normalisation est nécessaire, car les valeurs statiques que vous définissez pour les champs dérivés définissant les objectifs sont incrémentées avec chaque événement.

### Objectifs mensuels des commandes de certificats-cadeaux

1. Créez un champ de mesure calculée nommé `Monthly Gift Certificate Orders Goal`, défini comme suit :

   ![Objectif des commandes](assets/calculated-metric-ordersgoals.png)

1. Vous pouvez créer d’autres champs calculés, par exemple `% of Monthly Gift Certificate Orders Goal`, pour afficher la progression réelle par rapport aux objectifs, par exemple :

   ![Pourcentage objectif commandes](assets/calculated-metric-ordersgoalspercent.png)

Vous pouvez utiliser ces mesures calculées pour créer des rapports sur la progression dans les tableaux à structure libre et les visualisations. Par exemple :

![Tableau à structure libre présentant les objectifs de revenus marketing](assets/freeform-table-product-order-goals.png)


### Objectifs de chiffre d’affaires des canaux marketing

1. Créez un champ de mesure calculée nommé `Marketing Channel Revenue Goal`, défini comme suit :

   ![Objectif de chiffre d’affaires](assets/calculated-metric-revenuegoals.png)

1. Vous pouvez créer d’autres champs calculés, par exemple `% of Marketing Channel Revenue Goal`, pour afficher la progression réelle par rapport aux objectifs, par exemple :

   ![Pourcentage d’objectif de chiffre d’affaires](assets/calculated-metric-revenuegoalspercent.png)

Vous pouvez utiliser ces mesures calculées pour créer des rapports sur la progression dans les tableaux à structure libre et les visualisations. Par exemple :

![Tableau à structure libre présentant les objectifs de revenus marketing](assets/freeform-table-marketing-channel-revenue-goals.png)
