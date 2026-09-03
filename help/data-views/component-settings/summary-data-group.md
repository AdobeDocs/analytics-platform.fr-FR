---
title: Paramètres du composant Groupe de données de résumé
description: Détails et procédures de configuration des dimensions à partir de jeux de données pour vous assurer que vous pouvez créer des rapports corrects sur les données de résumé.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
autotag-review: '2026-05-19T09:00:37.763Z'
TQID: 'https://experienceleague.adobe.com/t1TH-tkHBNCfmC8hgk-IntYmYdRrS0enf2YEyRExCo4'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 89%

---

# Paramètres du composant [!UICONTROL Groupe de données de résumé] {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="Groupe de données de résumé"
>abstract="Un groupe de données de résumé crée une association entre toutes les dimensions du regroupement et est utilisé pour combiner les dimensions des jeux de données de résumé avec d’autres dimensions pour la création de rapports."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="Masquage dans les rapports"
>abstract="La sélection de cette option active **[!UICONTROL Masquer le composant dans les rapports]** pour cette dimension, empêchant ainsi l’affichage du composant dans Analysis Workspace et dans les autres outils de création de rapports de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->



Un groupe de données de résumé crée une association entre toutes les dimensions du regroupement et est utilisé pour combiner les dimensions des jeux de données de résumé avec d’autres dimensions pour la création de rapports.

![Paramètres du composant Groupe de données de résumé](/help/data-views/assets/summary-data-group.png)

Pour créer un regroupement de dimensions, procédez comme suit :

1. Sélectionnez une dimension.
1. Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Groupe de données Résumé]**.
1. Activez **[!UICONTROL Créer un regroupement]**.
1. Sélectionnez dans le menu déroulant **** une dimension que vous souhaitez regrouper avec la dimension sélectionnée à la première étape. Notez que seules les dimensions que vous avez déjà ajoutées à la vue de données sont disponibles dans le menu déroulant.
1. Vous pouvez éventuellement activer l’option **[!UICONTROL Masquer dans les rapports]** pour masquer la dimension regroupée des rapports. L’activation de cette option est similaire à la configuration de **[!UICONTROL Masquer dans les rapports]** sur la dimension regroupée séparément. Consultez [Paramètres de composant](overview.md) pour en savoir plus.
1. Si vous le souhaitez, pour ajouter des dimensions supplémentaires au regroupement, sélectionnez ![Ajouter](/help/assets/icons/Add.svg) **[!UICONTROL Ajouter une dimension au groupe]**.<br/>Vous pouvez ajouter jusqu’à neuf dimensions, car un groupe de données de résumé est limité à dix dimensions.

## Paramètres des composants identiques

Lors du regroupement des dimensions, vous devez vous assurer que les paramètres [!UICONTROL Sous-chaîne], [!UICONTROL Comportement (minuscules)] et [!UICONTROL Valeurs d’inclusion/exclusion], pour chacune des dimensions faisant partie du groupe, sont identiques. Sinon, chaque dimension du groupe peut potentiellement renvoyer différents résultats avant le regroupement.
Par exemple :

1. Vous avez créé un groupe de données de résumé pour `campaign_code` (faisant partie des données de résumé) et `tracking_code` (faisant partie des données d’événement).
1. Vous avez appliqué [!UICONTROL Comportement (minuscules)] au `campaign_code`, mais pas à la dimension `tracking_code`.

Les valeurs dans `tracking_code` peuvent potentiellement s’afficher comme différentes du `campaign_code`.

>[!IMPORTANT]
>
>Veillez à regrouper les dimensions à partir d’une seule dimension et à ne pas appliquer de regroupement à partir de plusieurs dimensions. Par exemple, si vous créez un regroupement en ajoutant la dimension `campaign_name` à la dimension `tracking_code`, ne créez pas également de regroupement pour la dimension `campaign_name`.
>
