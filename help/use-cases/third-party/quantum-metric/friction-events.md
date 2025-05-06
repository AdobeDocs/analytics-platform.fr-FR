---
title: Ajout d’événements de frottement de mesure quantique à Customer Journey Analytics
description: Ajoutez des événements de friction collectés par Quantum Metric aux données comportementales de Customer Journey Analytics pour approfondir les informations dans CJA.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 1%

---

# Ajout d’événements de frottement de mesure quantique à Customer Journey Analytics

Quantum Metric collecte les événements de friction tels que la lenteur de chargement des pages, les erreurs de chargement des pages, les clics de rage, etc. Ces événements peuvent être transmis dans Customer Journey Analytics en tant qu’événements complémentaires dans le parcours utilisateur. Grâce à ces données combinées, vous pouvez mieux comprendre l’impact de la friction sur les mesures en aval.

## Conditions préalables :

Ce cas d’utilisation a deux exigences :

* Vous devez avoir droit au package **Dev Ops** de Quantum Metric.
* Vous devez utiliser les balises dans la collecte de données Adobe Experience Platform.

## Étape 1 : créer un champ de schéma pour s’adapter aux événements de frottement de mesure quantique

Ce cas d’utilisation nécessite un champ de schéma dédié vers lequel envoyer des données. Vous pouvez créer ce champ à l’emplacement de votre choix dans votre schéma et le nommer comme vous le souhaitez. Des exemples de valeurs sont fournis si votre organisation n’a pas de préférence en matière de nom ou d’emplacement.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Schémas]**.
1. Sélectionnez le schéma souhaité dans la liste.
1. Sélectionnez l’icône ![Ajouter un champ](/help/assets/icons/AddCircle.svg) en regard de l’objet souhaité. Par exemple, en regard de `Implementation Details`.
1. Sur la droite, saisissez le [!UICONTROL Nom] souhaité. Par exemple : `qmErrorName`.
1. Saisissez le [!UICONTROL Nom d’affichage] souhaité. Par exemple : `Quantum Metric error name`.
1. Sélectionnez le [!UICONTROL Type] en tant que **[!UICONTROL Chaîne]**.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Étape 2 : capturer des événements de friction à l’aide de l’extension de balise Quantum Metric

Voir [Extension Quantum Metric](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) dans le guide des destinations Adobe Experience Platform pour obtenir des instructions sur la configuration de vos balises afin d’inclure des données de mesure quantique. L’utilisation de cette extension transmet plus de lignes dans un jeu de données existant.

Utilisez les balises dans la collecte de données Adobe Experience Platform pour définir manuellement le nom de l’événement de friction afin qu’il puisse être inclus dans l’objet XDM et analysé. Pour ce faire, vous pouvez utiliser le code personnalisé de la règle :

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

Ajoutez ensuite l’élément de données défini dynamiquement à votre objet XDM :

![Capture d’écran du nom de l’erreur de mesure quantique](assets/error-name.png)

## Étape 3 : ajouter une ou plusieurs dimensions et mesures à la vue de données dans Customer Journey Analytics

Modifiez la vue de données existante pour ajouter l’ID de session en tant que dimension disponible dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics et sélectionnez **[!UICONTROL Vues de données]**, éventuellement à partir de **[!UICONTROL Gestion des données]** dans le menu supérieur.
1. Sélectionnez la vue de données existante souhaitée.
1. Recherchez la liste du champ d’événement de frottement de mesure quantique sur la gauche, puis faites-la glisser vers la zone des mesures au centre.
1. Dans le volet de droite, définissez le paramètre [Inclure/Exclure les valeurs](/help/data-views/component-settings/include-exclude-values.md) sur les événements de frottement que vous souhaitez suivre. Vous pouvez ajouter plusieurs événements de friction à la même mesure pour les combiner. Vous pouvez également faire glisser une autre copie du champ Événements de friction vers la zone des mesures pour effectuer le suivi d’autres événements de friction sous la forme d’une mesure distincte.
1. Une fois toutes les dimensions et mesures souhaitées créées, cliquez sur **[!UICONTROL Enregistrer]**.
1. Pour obtenir une liste complète des événements d’erreur, reportez-vous à la documentation de Quantum Metric . Si vous avez des questions supplémentaires, contactez votre représentant du service clientèle de Quantum Metric ou envoyez une demande par le biais du portail [Quantum Metric Customer Request Portal](https://community.quantummetric.com/s/public-support-page).

## Étape 4 : utiliser la dimension et les mesures avec le reste de vos données dans Analysis Workspace

Grâce aux données d’événement de friction de mesure quantique collectées avec le reste de vos données visiteur, vous pouvez les utiliser exactement comme vous le feriez pour toute autre dimension ou mesure dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Workspace]** dans le menu supérieur.
1. Sélectionnez un projet existant ou créez-en un.
1. Créez un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Faites glisser les dimensions et mesures de votre choix vers la zone de travail Workspace pour les analyser.

![Graphique de friction](assets/friction-graph.png)

Les idées d’analyse possibles sont les suivantes :

* Données d’événement de friction de tendance au fil du temps
* Dans une visualisation des abandons ou des entonnoirs, ajoutez des événements Customer Journey Analytics comme certaines étapes et des événements de frottement de mesure quantique comme d’autres. Ce rapport vous permet de voir où les visiteurs rencontrent le plus souvent des problèmes.
* Créez et appliquez un segment pour les visiteurs qui subissent des événements de friction afin d’effectuer une analyse plus approfondie
