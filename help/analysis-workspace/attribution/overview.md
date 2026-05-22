---
title: Vue d’ensemble d’attribution
description: Découvrez le concept d’attribution du crédit d’un événement de succès à plusieurs éléments de dimension.
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
TQID: https://experienceleague.adobe.com/ncY8TuwUb3duwfK3n8u69eyXWUDzI5OMF-AACOoDmIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 453
ht-degree: 96%

---

# Présentation d’Attribution

Attribution permet aux analystes de personnaliser la manière dont les éléments de dimension obtiennent du crédit pour les événements de succès. Par exemple :

1. Une personne qui visite votre site clique sur un lien de référencement payant vers l’une de vos pages produits. La personne ajoute le produit au panier, mais ne l’achète pas.
2. Le lendemain, elle voit une publication d’un ami ou d’une amie sur les médias sociaux, elle clique sur le lien, puis effectue l’achat.

Dans certains rapports, vous voudrez peut-être attribuer la commande au référencement payant. Dans d’autres rapports, vous voudrez peut-être attribuer la commande à Social. Attribution vous permet de contrôler cet aspect des rapports. Toutes les entreprises disposant d’Adobe Analytics Ultimate, Prime, Select ou Foundation peuvent en bénéficier. Si vous vous demandez quel type de contrat vous avez conclu avec Adobe, contactez l’équipe Adobe en charge des comptes de votre entreprise.

## Valeur d’attribution

Un parcours client donné n’est pas linéaire et est souvent imprévisible. Chaque client a son propre rythme. Il lui arrive souvent de revenir sur ses pas, de s’arrêter, de redémarrer ou d’adopter un autre comportement non linéaire. En raison de ces actions organiques, il est difficile de connaître l’impact des efforts marketing tout au long du parcours client. Cela complique également les efforts visant à relier plusieurs canaux de données.

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

Adobe Analytics améliore l’attribution en vous permettant d’effectuer les tâches suivantes :

* Définir l’attribution à des médias autres que ceux achetés : tout élément (dimension, mesure, canal ou événement) peut être appliqué aux modèles (par exemple, recherche interne) et pas seulement aux campagnes marketing.
* Utilisez la comparaison illimitée de modèles d’attribution : comparez dynamiquement autant de modèles que vous le souhaitez.
* éviter les changements de mise en œuvre : avec le traitement de la période de rapport et les sessions contextuelles, le contexte du parcours client peut être intégré et appliqué lors de l’exécution ;
* construire la session qui correspond le mieux à votre scénario d’attribution ;
* Ventiler l’attribution par segments : comparez facilement les performances de vos canaux marketing sur n’importe quel segment important (par exemple, la nouvelle clientèle par rapport à la clientèle régulière, le produit X par rapport au produit Y, le niveau de fidélité ou la valeur vie client (CLV)).
* inspecter le croisement des canaux et l’analyse multi-touch : utilisation des histogrammes et diagrammes de Venn ainsi que des résultats de l’attribution des tendances ;
* analyser visuellement des séquences marketing importantes : explorez les chemins d’accès qui ont mené à la conversion sur le plan visuel par le biais de visualisations à plusieurs nœuds de flux et d’abandons ;
* créer des mesures calculées : utilisez n’importe quel nombre de méthodes d’attribution.

## Fonctionnalités

Attribution propose les fonctionnalités suivantes :

* [Panneau Attribution](/help/analysis-workspace/c-panels/attribution.md) : comparez rapidement les dimensions et les mesures avec différents modèles d’attribution.
* [Appliquer l’attribution à une mesure](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) : utilisez une attribution autre que celle par défaut sur une mesure d’un projet.
* [Appliquer l’attribution à une répartition](/help/components/dimensions/t-breakdown-fa.md#apply-attribution-models-to-breakdowns) : utilisez une attribution autre que celle par défaut sur une répartition.
* [Comparer des modèles d’attribution](/help/components/apply-create-metrics.md#compare-metrics-with-different-attribution-models) : comparez rapidement les différents modèles d’attribution pour n’importe quelle mesure.

## Vidéos


<!--  
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in Freeform tables](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

<!-- 
Attribution IQ 
>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in calculated metrics](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/attribution-iq-in-calculated-metrics){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilisation du panneau Attribution](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/panels/build-the-attribution-panel){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


<!-- 
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding side-by-side comparisons of Attribution models](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/adding-side-by-side-comparisons-of-attribution-iq-models){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

