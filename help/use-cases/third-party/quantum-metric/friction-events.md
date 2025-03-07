---
title: Ajout d’événements de frottement de mesure quantique à Customer Journey Analytics
description: Ajoutez des profondeurs aux informations dans Customer Journey Analytics à l’aide d’événements de friction collectés dans Quantum Metric.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: e6a77e75963fb43041c0533a28a9563a3849b8b0
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 0%

---

# Ajout d’événements de frottement de mesure quantique à Customer Journey Analytics

Quantum Metric collecte les événements de friction tels que la lenteur de chargement des pages, les erreurs de chargement des pages, les clics de rage, etc. Ces événements peuvent être transmis dans Customer Journey Analytics en tant qu’événements complémentaires dans le parcours utilisateur. Grâce à ces données combinées, vous pouvez mieux comprendre l’impact de la friction sur les mesures en aval.

Ce cas d’utilisation a deux exigences :

* Vous devez avoir droit au package **Dev Ops** de Quantum Metric.
* Vous devez utiliser les balises dans la collecte de données Adobe Experience Platform.

## Étape 1 : capturer des événements de friction à l’aide de l’extension de balise Quantum Metric

L’équipe du CSM de Quantum Metric peut vous aider à déterminer les éléments de schéma à ajouter et vous indiquer comment modifier votre implémentation afin de collecter les données souhaitées en vue de les utiliser dans Customer Journey Analytics. Pour plus d’informations, contactez votre responsable du succès client pour Quantum Metric.

En fin de compte, vous souhaiterez commencer à suivre le nom de l’événement de friction dans un champ.

## Étape 2 : confirmer les champs du jeu de données inclus

Vérifiez que les jeux de données de votre connexion possèdent désormais l’ID de session de mesure quantique dans le jeu de données souhaité.

## Étape 3 : ajouter une ou plusieurs dimensions et mesures à la vue de données dans Customer Journey Analytics

Modifiez la vue de données existante pour ajouter l’ID de session en tant que dimension disponible dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Vues de données]** dans le menu supérieur.
1. Sélectionnez la vue de données existante souhaitée.
1. Recherchez la liste du champ d’événement de frottement de mesure quantique sur la gauche, puis faites-la glisser vers la zone des mesures au centre.
1. Dans le volet de droite, définissez le paramètre [Inclure/Exclure les valeurs](/help/data-views/component-settings/include-exclude-values.md) sur les événements de frottement que vous souhaitez suivre. Vous pouvez ajouter plusieurs événements de friction à la même mesure pour les combiner. Vous pouvez également faire glisser une autre copie du champ Événements de friction vers la zone des mesures pour effectuer le suivi d’autres événements de friction sous la forme d’une mesure distincte.
1. Une fois toutes les dimensions et mesures souhaitées créées, cliquez sur **[!UICONTROL Enregistrer]**.

## Étape 4 : utiliser la dimension et les mesures avec le reste de vos données dans Analysis Workspace

Grâce aux données d’événement de friction de mesure quantique collectées avec le reste de vos données visiteur, vous pouvez les utiliser exactement comme vous le feriez pour toute autre dimension ou mesure dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Workspace]** dans le menu supérieur.
1. Sélectionnez un projet existant ou créez-en un.
1. Créez un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Faites glisser les dimensions et mesures de votre choix vers la zone de travail Workspace pour les analyser.

Les idées d’analyse possibles sont les suivantes :

* Données d’événement de friction de tendance au fil du temps
* Dans une visualisation des abandons ou des entonnoirs, ajoutez des événements Customer Journey Analytics comme certaines étapes et des événements de frottement de mesure quantique comme d’autres. Ce rapport vous permet de voir où les visiteurs rencontrent le plus souvent des problèmes.
* Créez et appliquez un filtre pour les visiteurs qui subissent des événements de friction afin d’effectuer une analyse plus approfondie
