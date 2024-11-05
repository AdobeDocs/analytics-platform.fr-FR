---
title: Paramètres du composant de groupe de données récapitulatifs
description: Détails et sur la configuration des dimensions des jeux de données pour vous assurer que vous pouvez créer des rapports corrects sur les données de résumé.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: ad446f55855696cf7721f34f779883792b7958fa
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 25%

---

# Paramètres du composant [!UICONTROL Groupe de données de résumé] {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_summarydatagroup"
>title="Groupe de données de résumé"
>abstract="Un groupe de données de résumé crée une association entre toutes les dimensions du regroupement et est utilisé pour combiner les dimensions des jeux de données de résumé avec d’autres dimensions pour la création de rapports."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_summarydatagroup_hideinreporting"
>title="Masquage dans les rapports"
>abstract="La sélection de cette option active **[!UICONTROL Masquer le composant dans les rapports]** pour cette dimension, empêchant ainsi l’affichage du composant dans Analysis Workspace et dans les autres outils de création de rapports de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->



Un groupe de données de résumé crée une association entre toutes les dimensions du regroupement et est utilisé pour combiner les dimensions des jeux de données de résumé avec d’autres dimensions pour la création de rapports.

![Paramètres du composant de groupe de données récapitulatifs](/help/data-views/assets/summary-data-group.png)

Pour créer un groupement de dimensions :

1. Sélectionnez une dimension.
1. Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Groupe de données récapitulatives]**.
1. Activez **[!UICONTROL Créer un regroupement]**.
1. Sélectionnez une dimension dans la liste déroulante **[!UICONTROL Dimension]**, que vous souhaitez regrouper avec la dimension sélectionnée à la première étape. Notez que seules les dimensions que vous avez déjà ajoutées à la vue de données sont disponibles dans la liste déroulante.
1. Vous pouvez éventuellement activer l’option **[!UICONTROL Masquer dans les rapports]** pour masquer la dimension regroupée des rapports. L&#39;activation de cette option est similaire à la configuration séparée de **[!UICONTROL Masquer dans les rapports]** sur la dimension groupée. Voir [Paramètres des composants](overview.md) pour plus d’informations.
1. Si vous le souhaitez, pour ajouter des dimensions supplémentaires au regroupement, sélectionnez ![Ajouter](/help/assets/icons/Add.svg) **[!UICONTROL Ajouter une dimension au groupe]**.<br/>Vous pouvez ajouter jusqu’à neuf dimensions, car un groupe de données récapitulatives est limité à dix dimensions.

## Mêmes paramètres de composant

Lors du regroupement des dimensions, vous devez vous assurer que les paramètres de [!UICONTROL Substring], [!UICONTROL Comportement (minuscule)] et [!UICONTROL Inclure les valeurs d’exclusion], pour chacune des dimensions qui font partie du groupe, sont identiques. Sinon, chaque dimension du groupe peut potentiellement renvoyer des résultats différents avant le regroupement.
Par exemple :

1. Vous avez créé un groupe de données de résumé pour `campaign_code` (partie des données de résumé) et `tracking_code` (partie de vos données d’événement).
1. Vous avez appliqué [!UICONTROL Comportement (minuscule)] à la dimension `campaign_code` mais pas à la dimension `tracking_code`.

Les valeurs de `tracking_code` peuvent éventuellement s’afficher en tant que différentes de `campaign_code`.

>[!IMPORTANT]
>
>Veillez à regrouper les dimensions d’une seule dimension et à ne pas appliquer de regroupement à partir de plusieurs dimensions. Par exemple, si vous créez un groupement en ajoutant la dimension `campaign_name` à la dimension `tracking_code`, ne créez pas non plus de regroupement pour la dimension `campaign_name`.
>
