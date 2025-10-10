---
title: 'Paramètres des composants : attribution'
description: Permet de définir lʼattribution par défaut dʼune mesure.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 93%

---

# Paramètres des composants : attribution {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Attribution"
>abstract="Configurez le modèle d’attribution par défaut appliqué à une mesure dans les rapports."

<!-- markdownlint-enable MD034 -->


L’attribution vous donne la possibilité de personnaliser la façon dont les éléments de dimension reçoivent du crédit pour les événements de succès.

![Fenêtre Vues de données mettant en surbrillance l’option Définir l’attribution](../assets/attribution-settings.png)

Par exemple :

1. Une personne sur votre site clique sur un lien de référencement payant vers l’une de vos pages produits. La personne ajoute le produit au panier, mais ne l’achète pas.
2. Le lendemain, elle voit un message d’une personne de son entourage sur les médias sociaux. Elle clique sur le lien, puis effectue l’achat.

Dans certains rapports, vous voudrez peut-être attribuer la commande au référencement payant. Dans d’autres rapports, vous voudrez peut-être attribuer la commande à Social. Attribution vous permet de contrôler cet aspect des rapports.

## Définir le modèle d’attribution par défaut d’un composant

Vous pouvez définir un modèle d’attribution par défaut pour une mesure donnée en mettant à jour le paramètre de la mesure dans la vue de données. Cela remplace le modèle d’attribution de la mesure chaque fois qu’il est utilisé dans Analysis Workspace.

>[!NOTE]
>
>Tenez compte des points suivants lors de l’activation de l’attribution sur une mesure :
>
>* **Lors de l’utilisation du composant dans un rapport avec *une seule dimension* :** l’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution différent du modèle par défaut est utilisé.
>
>* **Lors de l’utilisation du composant dans un rapport avec *plusieurs dimensions* :** l’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution différent du modèle par défaut est utilisé.
>
>   Plusieurs dimensions sont disponibles uniquement lors de l’[export de données vers le cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Pour plus d’informations sur l’attribution, consultez [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).

Pour mettre à jour le modèle d’attribution par défaut d’un composant, procédez comme suit :

1. Accédez à la vue de données contenant le composant dont vous souhaitez mettre à jour le modèle d’attribution par défaut.

1. Sélectionnez le composant, puis développez la section **[!UICONTROL Attribution]** sur le côté droit de l’écran.

   ![Fenêtre Vues de données mettant en surbrillance l’option Définir l’attribution](../assets/attribution-settings.png)

1. Sélectionnez [!UICONTROL **Définir l’attribution**], puis sélectionnez l’intervalle [modèle d’attribution](#attribution-models), [conteneur](#container) et [recherche en amont](#lookback-window).



1. Sélectionnez [!UICONTROL **Enregistrer et continuer**].

>[!TIP]
>
>Si votre entreprise exige qu’une mesure comporte plusieurs paramètres d’attribution, vous pouvez effectuer l’une des opérations suivantes :
>
> * Copiez la mesure dans la vue de données avec chaque paramètre d’attribution souhaité. Vous pouvez inclure la même mesure plusieurs fois dans une vue de données, ce qui donne à chaque mesure un paramètre différent. Assurez-vous d’étiqueter correctement chaque mesure afin que les analystes comprennent la différence entre ces mesures lors de la génération des rapports.
>
> * Remplacez la mesure dans Analysis Workspace. Dans les [Paramètres de colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) d’une mesure, sélectionnez **[!UICONTROL Utiliser un modèle d’attribution différent du modèle par défaut]** pour modifier le modèle d’attribution et l’intervalle de recherche en amont de la mesure pour ce rapport spécifique.

## Modèles d’attribution {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modèle"
>abstract="Sélectionnez un modèle d’attribution pour la mesure."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## Conteneur

{{attribution-container}}

## Intervalle de recherche en amont

{{attribution-lookback-window}}

## Exemple

{{attribution-example}}
