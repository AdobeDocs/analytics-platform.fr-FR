---
title: Ajout de données de mesure quantique à Customer Journey Analytics
description: Utilisez Quantum Metric pour la collecte de données relatives aux parcours et comportements des utilisateurs, puis optimisez CJA à partir de ces données collectées afin d’obtenir des informations plus riches.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Ajout de données de mesure quantique à Customer Journey Analytics

>[!IMPORTANT]
>
>Le connecteur source de mesure quantique n’est pas encore disponible.

CJA déverrouille le contrôle de la période de rapport sur les données AEM, l’analyse séquentielle des données, l’attribution enrichie et d’autres rapports avancés.  QM peut être envoyé à AEP à l’aide du connecteur source QM ou de l’extension Balises de mesures quantiques.

## Étape 1 : Créer un connecteur source Quantum Metric

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à [!UICONTROL Experience Platform] > [!UICONTROL Connexions] > [!UICONTROL Sources].
1. Ajoutez le connecteur source Quantum Metric et suivez les invites jusqu’à la fin.

Voir [Connecteurs source Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) pour plus d’informations.

## Étape 2 : création d’une connexion dans Customer Journey Analytics

La création d’un connecteur source pour les données de mesure quantique crée automatiquement un jeu de données dans Adobe Experience Platform. Ajoutez ce jeu de données à une [connexion](/help/connections/overview.md) nouvelle ou existante dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Connexions]** dans le menu supérieur.
1. Attribuez un nom à la connexion et ajoutez le jeu de données Mesure quantique à la connexion.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>Bien que vous puissiez ajouter des données de mesure quantique à la même connexion que le reste de vos données Customer Journey Analytics, ces données ne peuvent pas être regroupées sans un ID de personne commun entre les deux jeux de données. Si ce comportement est souhaité, Adobe recommande d’utiliser l’extension [Tag](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) au lieu du connecteur source.

## Étape 3 : création d’une vue de données dans Customer Journey Analytics

Créez une [vue de données](/help/data-views/data-views.md) pour configurer les paramètres de dimension et de mesure.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Vues de données]** dans le menu supérieur.
1. Sélectionnez la vue de données souhaitée ou créez une vue de données.
1. Recherchez les dimensions et mesures de mesure quantique souhaitées dans la liste des champs de schéma à droite, puis faites-les glisser vers la zone des dimensions et mesures au centre.
1. Utilisez le volet de droite pour configurer chaque dimension et mesure souhaitée.

## Étape 4 : commencer à créer des rapports et à analyser dans Customer Journey Analytics

Maintenant que les données sont disponibles dans Customer Journey Analytics, vous pouvez commencer à créer des rapports sur les données.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Workspace]** dans le menu supérieur.
1. Sélectionnez un projet existant ou créez-en un.
1. Faites glisser toute dimension ou mesure de mesure quantique souhaitée vers la zone de travail de Workspace pour analyser les données.
