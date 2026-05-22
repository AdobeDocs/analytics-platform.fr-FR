---
title: Ajout de données de mesure quantique à Customer Journey Analytics
description: Utilisez Quantum Metric pour la collecte de données relatives aux parcours et comportements des utilisateurs, puis optimisez CJA à partir de ces données collectées afin d’obtenir des informations plus riches.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
TQID: https://experienceleague.adobe.com/LLrYpPlbagFAIeuD9TMgA3E8lrcUrMxMSWLC-8SiiIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 942cc774812d4a6b3b7f45df837ff9277e8f9b46
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 4%

---

# Ajout de données de mesure quantique à Customer Journey Analytics

>[!IMPORTANT]
>
>Le connecteur source de mesure quantique n’est pas encore disponible.

CJA déverrouille le contrôle de la période de rapport sur les données AEM, l’analyse séquentielle des données, l’attribution enrichie et d’autres rapports avancés.  QM peut être envoyé à AEP à l’aide du connecteur source QM ou de l’extension Balises de mesures quantiques.

## Étape 1 : Créer un connecteur source Quantum Metric

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à  > [!UICONTROL Connexions] > [!UICONTROL Sources].
1. Ajoutez le connecteur source Quantum Metric et suivez les invites jusqu’à la fin.

Voir [Connecteurs source &#x200B;](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/home) pour plus d’informations.

## Étape 2 : création d’une connexion dans Customer Journey Analytics

La création d’un connecteur source pour les données de mesure quantique crée automatiquement un jeu de données dans Adobe Experience Platform. Ajoutez ce jeu de données à une [connexion](/help/connections/overview.md) nouvelle ou existante dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics et sélectionnez **[!UICONTROL Connexions]**, éventuellement à partir de **[!UICONTROL Gestion des données]** dans le menu supérieur.
1. Attribuez un nom à la connexion et ajoutez le jeu de données Mesure quantique à la connexion.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>Bien que vous puissiez ajouter des données de mesure quantique à la même connexion que le reste de vos données Customer Journey Analytics, ces données ne peuvent pas être regroupées sans un ID de personne commun entre les deux jeux de données. Si ce comportement est souhaité, Adobe recommande d’utiliser l’extension [Tag](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) au lieu du connecteur source.

## Étape 3 : création d’une vue de données dans Customer Journey Analytics

Créez une [vue de données](/help/data-views/data-views.md) pour configurer les paramètres de dimension et de mesure.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics et sélectionnez **[!UICONTROL Vues de données]**, éventuellement à partir de **[!UICONTROL Gestion des données]** dans le menu supérieur.
1. Sélectionnez la vue de données souhaitée ou créez une vue de données.
1. Recherchez les dimensions et mesures de mesure quantique souhaitées dans la liste des champs de schéma à droite, puis faites-les glisser vers la zone des dimensions et mesures au centre.
1. Utilisez le volet de droite pour configurer chaque dimension et mesure souhaitée.

## Étape 4 : commencer à créer des rapports et à analyser dans Customer Journey Analytics

Maintenant que les données sont disponibles dans Customer Journey Analytics, vous pouvez commencer à créer des rapports sur les données.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Workspace]** dans le menu supérieur.
1. Sélectionnez un projet existant ou créez-en un.
1. Faites glisser toute dimension ou mesure de mesure quantique souhaitée vers la zone de travail de Workspace pour analyser les données.
