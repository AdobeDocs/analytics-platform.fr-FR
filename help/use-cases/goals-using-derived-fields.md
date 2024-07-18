---
title: Utiliser des champs dérivés pour créer des rapports sur les objectifs
description: Découvrez comment utiliser les champs dérivés pour créer des rapports sur les objectifs (cibles) de vos projets Workspace.
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

Ce cas pratique décrit comment utiliser la puissance des champs dérivés pour définir des objectifs pour une dimension spécifique, puis utiliser ces objectifs dans votre projet Workspace.

Si vous ne connaissez pas les champs dérivés, reportez-vous au [tutoriel](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html) et à la [documentation](../data-views/derived-fields/derived-fields.md) pour une introduction.


## Définition des objectifs

Pour définir des objectifs, créez un champ dérivé dans lequel vous définissez explicitement des valeurs numériques personnalisées, directement ou indirectement, à l’aide des valeurs issues de règles antérieures à votre définition de champ dérivé.


### Objectifs mensuels des commandes de certificat cadeau

Vous souhaitez définir explicitement des objectifs pour vos commandes de certificats-cadeaux pour une période de quatre mois, allant de juillet 2023 à octobre 2023. Pour ce faire :

1. Créez un champ dérivé avec le nom `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Définissez des valeurs statiques, à l’aide d’une RÈGLE CASE WHEN, pour chaque mois, en définissant une **[!UICONTROL valeur numérique personnalisée]**. Voir la règle Objectifs de produit mensuels ci-dessous.

   ![Objectifs de produit mensuels](assets/goals-derived-field-product-goals-1.png)


### Objectifs de recettes des canaux marketing

Vous souhaitez définir un objectif de recettes mensuel pour chacun de vos canaux marketing. Pour ce faire :

1. Créez un nouveau champ dérivé à l’aide du [ modèle de fonction de canaux marketing ](/help/data-views/derived-fields/derived-fields.md#marketing-channels) avec le nom `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Définissez toutes les règles pour identifier correctement chacun des canaux marketing en fonction d’une combinaison de règles URL PARSE et CASE WHEN . Par exemple :

   ![Définition des règles pour le champ dérivé du canal marketing](assets/goals-derived-field-marketing-channel-1.png)

1. Définissez explicitement des valeurs statiques, représentant les objectifs de recettes mensuelles, pour les canaux marketing spécifiques dans un CAS final, en définissant une **[!UICONTROL valeur numérique personnalisée]**. Voir la règle [!DNL Monthly Goal] ci-dessous.

   ![Objectifs mensuels](assets/goals-derived-field-marketing-channel-2.png)



## Utilisation des objectifs

Pour utiliser des objectifs dans votre projet Workspace, vous utilisez la fonctionnalité de mesure calculée pour &quot;normaliser&quot; le champ dérivé sur sa valeur statique d’origine. Cette normalisation est nécessaire car les valeurs statiques que vous définissez pour les champs dérivés définissant des objectifs sont incrémentées avec chaque événement.

### Objectifs mensuels des commandes de certificat cadeau

1. Créez un champ de mesure calculée nommé `Monthly Gift Certificate Orders Goal`, défini comme suit :

   ![Objectif de commande](assets/calculated-metric-ordersgoals.png)

1. Vous pouvez créer des champs calculés supplémentaires, par exemple `% of Monthly Gift Certificate Orders Goal`, pour afficher la progression réelle par rapport aux objectifs, par exemple :

   ![Pourcentage de l’objectif des commandes](assets/calculated-metric-ordersgoalspercent.png)

Vous pouvez utiliser ces mesures calculées pour générer des rapports sur l’avancement dans les tableaux à structure libre et les visualisations. Par exemple :

![Tableau à structure libre présentant les objectifs de recettes marketing](assets/freeform-table-product-order-goals.png)


### Objectifs de recettes des canaux marketing

1. Créez un champ de mesure calculée nommé `Marketing Channel Revenue Goal`, défini comme suit :

   ![Objectif de chiffre d’affaires](assets/calculated-metric-revenuegoals.png)

1. Vous pouvez créer des champs calculés supplémentaires, par exemple `% of Marketing Channel Revenue Goal`, pour afficher la progression réelle par rapport aux objectifs, par exemple :

   ![Pourcentage de l’objectif du chiffre d’affaires](assets/calculated-metric-revenuegoalspercent.png)

Vous pouvez utiliser ces mesures calculées pour générer des rapports sur l’avancement dans les tableaux à structure libre et les visualisations. Par exemple :

![Tableau à structure libre présentant les objectifs de recettes marketing](assets/freeform-table-marketing-channel-revenue-goals.png)
