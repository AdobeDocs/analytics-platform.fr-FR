---
title: 'Paramètres des composants : résumé du groupe de données'
description: Des détails et sur la manière de configurer des dimensions à partir de jeux de données pour vous assurer que vous pouvez créer des rapports corrects sur les données de résumé.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 25%

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

![Paramètres des composants : résumé du groupe de données](/help/data-views/assets/summary-data-group.png)

Pour créer un regroupement de dimensions :

1. Sélectionnez une dimension.
1. Sélectionnez ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Groupe de données Résumé]**.
1. Activez **[!UICONTROL Créer un regroupement]**.
1. Sélectionnez dans la liste déroulante **[!UICONTROL Dimension]** une dimension que vous souhaitez regrouper avec la dimension sélectionnée à la première étape. Notez que seules les dimensions que vous avez déjà ajoutées à la vue de données sont disponibles dans la liste déroulante.
1. Vous pouvez éventuellement activer l’option **[!UICONTROL Masquer dans les rapports]** pour masquer la dimension groupée des rapports. L’activation de cette option est similaire à la configuration **[!UICONTROL Masquer dans les rapports]** sur la dimension groupée séparément. Voir [Paramètres de composant](overview.md) pour plus d’informations.
1. Si vous le souhaitez, pour ajouter des dimensions supplémentaires au regroupement, sélectionnez ![Ajouter](/help/assets/icons/Add.svg) **[!UICONTROL Ajouter une dimension au groupe]**.<br/>Vous pouvez ajouter jusqu’à neuf dimensions, car un groupe de données de résumé est limité à dix dimensions.

## Paramètres du même composant

Lors du regroupement des dimensions, vous devez vous assurer que les paramètres [!UICONTROL Sous-chaîne], [!UICONTROL Comportement (Minuscules)] et [!UICONTROL Inclure les valeurs d’exclusion], pour chacune des dimensions faisant partie du groupe, sont identiques. Sinon, chaque dimension du groupe peut potentiellement renvoyer différents résultats avant le regroupement.
Par exemple :

1. Vous avez créé un groupe de données de synthèse pour `campaign_code` (partie des données de synthèse) et `tracking_code` (partie des données d’événement).
1. Vous avez appliqué la [!UICONTROL Comportement (Minuscules)] à la `campaign_code`, mais pas à la dimension `tracking_code`.

Les valeurs dans `tracking_code` peuvent potentiellement s’afficher comme différentes de `campaign_code`.

>[!IMPORTANT]
>
>Veillez à regrouper les dimensions à partir d’une seule dimension et à ne pas appliquer de regroupement à partir de plusieurs dimensions. Par exemple, si vous créez un regroupement en ajoutant la dimension `campaign_name` à la dimension `tracking_code` , ne créez pas également de regroupement pour la dimension `campaign_name` .
>
