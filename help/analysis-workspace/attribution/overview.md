---
title: Présentation de l’Attribution
description: concept d’attribution du crédit d’un événement de réussite à plusieurs valeurs de dimension.
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 50%

---


# Présentation de l’Attribution

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

L’attribution permet aux analystes de personnaliser la manière dont les valeurs de dimension obtiennent du crédit pour les événements de réussite. Par exemple :

1. Un visiteur de votre site clique sur un lien de recherche payante pointant vers l’une de vos pages de produits. Ajoutez le produit au panier, mais ne l’achetez pas.
2. Le lendemain, ils voient une publication sur les réseaux sociaux de l’un de leurs amis, cliquent sur le lien, puis terminent l’achat.

Dans certains rapports, il est possible que la commande soit attribuée à la recherche payante. Dans d’autres rapports, il est possible que l’ordre soit attribué à Social. L’attribution vous permet de contrôler cet aspect du rapports. Il est disponible pour toutes les organisations sur Adobe Ultimate, Prime, Select et Foundation. Si vous ne savez pas quel type de contrat vous avez avec Adobe, contactez le gestionnaire de compte de votre entreprise.

## Valeur du QI d’attribution

Un parcours client donné n’est pas linéaire et est souvent imprévisible. Chaque client a son propre rythme. Il lui arrive souvent de revenir sur ses pas, de s’arrêter, de redémarrer ou d’adopter un autre comportement non linéaire. En raison de ces actions organiques, il est difficile de connaître l’impact des efforts marketing tout au long du parcours client. Cela complique également les efforts visant à relier plusieurs canaux de données.

![Problème d’Attribution IQ](assets/attribution_iq_problem.png)

Adobe Analytics améliore l’attribution en vous permettant de :

* définir l’attribution à des médias autres que ceux achetés : tout canal, dimension, mesure ou événement peut être appliqué aux modèles (par exemple, recherche interne) et pas seulement aux campagnes marketing ;
* utiliser la comparaison illimitée de modèles d’attribution : comparez dynamiquement autant de modèles que vous le souhaitez ;
* éviter les changements de mise en œuvre : avec le traitement de la période de rapport et les sessions contextuelles, le contexte du parcours client peut être intégré et appliqué lors de l’exécution ;
* construire la session qui correspond le mieux à votre scénario d’attribution ;
* ventiler l’attribution par segments : comparez facilement la performance de vos canaux marketing sur n’importe quel segment important (par exemple, les nouveaux clients par rapport aux clients réguliers, le produit X par rapport au produit Y, le niveau de fidélité ou la valeur vie client (CLV)) ;
* inspecter le croisement des canaux et l’analyse multi-touch : utilisation des histogrammes et diagrammes de Venn ainsi que des résultats de l’attribution des tendances ;
* analyser visuellement des séquences marketing importantes : explorez les chemins d’accès qui ont mené à la conversion sur le plan visuel par le biais de visualisations à plusieurs nœuds de flux et d’abandons ;
* créer des mesures calculées : utilisez n’importe quel nombre de méthodes d’attribution.

## Fonctionnalités

Attribution IQ propose les fonctionnalités suivantes :

* [Panneau](../c-panels/attribution.md)Attribution : Prenez n’importe quelle dimension et mesure et comparez-la rapidement avec différents modèles d’attribution.
* [Appliquer l’attribution à une mesure](../build-workspace-project/column-row-settings/column-settings.md): Utilisez une attribution autre que l’attribution par défaut sur une mesure d’un projet.
* [Appliquer l’attribution à une ventilation](/help/components/dimensions/t-breakdown-fa.md): Utilisez une attribution autre que l’attribution par défaut sur une ventilation.
* [Comparer les modèles](/help/components/apply-create-metrics.md)d’attribution : Découvrez rapidement comment différents modèles d’attribution se comparent pour une mesure.
