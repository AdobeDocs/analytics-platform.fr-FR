---
title: 'Paramètres des composants : attribution'
description: Permet de définir lʼattribution par défaut dʼune mesure.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T07:52:30.794Z'
TQID: 'https://experienceleague.adobe.com/ZsIk0j5B2rxVYSdzeqlzKCAOYMQOwh-p941UbzKXYgM'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5520579-b31f-4df7-9281-f0d9f91e2edcid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 63%

---

# Paramètres des composants : attribution {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Attribution"
>abstract="Configurez le modèle d’attribution par défaut appliqué à une mesure dans les rapports."

<!-- markdownlint-enable MD034 -->


L’attribution vous donne la possibilité de personnaliser la façon dont les éléments de dimension reçoivent du crédit pour les événements de succès.

Par exemple :

1. Une personne sur votre site clique sur un lien de référencement payant vers l’une de vos pages produits. La personne ajoute le produit au panier, mais ne l’achète pas.
2. Le lendemain, elle voit un message d’une personne de son entourage sur les médias sociaux. Elle clique sur le lien, puis effectue l’achat.

Dans certains rapports, vous voudrez peut-être attribuer la commande au référencement payant. Dans d’autres rapports, vous voudrez peut-être attribuer la commande à Social. Attribution vous permet de contrôler cet aspect des rapports.

## Définir un modèle d’attribution de composant

Vous pouvez modifier le modèle d’attribution par défaut d’un composant donné en mettant à jour le paramètre du composant dans la vue de données. Cela remplace le modèle d’attribution du composant chaque fois qu’il est utilisé dans Analysis Workspace.

>[!NOTE]
>
>Tenez compte des points suivants lors de l’activation d’un modèle d’attribution autre que celui par défaut sur une mesure :
>
>* **Lors de l’utilisation de la mesure dans un rapport avec *une seule dimension* :** l’attribution de la mesure remplace le modèle d’attribution défini sur la dimension. Par exemple, une mesure avec une attribution « première touche » remplace une attribution de dimension « le plus récent ».
>
>* **Lors de l’utilisation de la mesure dans un rapport avec *plusieurs dimensions* :** l’attribution de la mesure est appliquée en plus du modèle d’attribution pour chaque dimension. Par exemple, une mesure avec une attribution « Première touche » est appliquée en plus d’une attribution de dimension « Le plus récent ».
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
