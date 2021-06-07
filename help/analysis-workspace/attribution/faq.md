---
title: FAQ sur l’Attribution
description: Obtenez des réponses aux questions les plus fréquentes au sujet de l’attribution.
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 85%

---

# FAQ sur l’Attribution

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

**Qu’est-ce que l’élément de ligne « Aucun » lors de l’utilisation de l’attribution ?**

L’élément de ligne « Aucun » est un élement fourre-tout qui représente toutes les conversions survenues sans points de contact dans l’intervalle de recherche en amont. Essayez d’inclure une période plus longue dans votre créneau de rapport.

**Pourquoi est-ce que je vois parfois des dates hors de mon créneau de rapport lors de l’utilisation de modèles d’attribution ?**

Ces dates supplémentaires sont dues à l’intervalle de recherche en amont de rapport de visiteurs. Pour plus d’informations, voir [Données apparaissant hors du créneau de rapport](https://helpx.adobe.com/fr/analytics/kb/data-appearing-outside-reporting-window.html) dans la base de connaissances d’Analytics. Adobe prévoit de filtrer ces rangées supplémentaires dans une prochaine version.

**Quand dois-je utiliser une recherche en amont de l’attribution de visites ou de visiteurs ?**

Le choix d’une recherche en amont de l’attribution dépend de votre cas d’utilisation. Si les conversions prennent généralement plus longtemps qu’une visite unique, une recherche en amont des visiteurs est recommandée. La création d’une vue de données avec une définition de visite plus longue est également une solution potentielle.

**Comment les props et les eVars se comparent-ils lors de l’utilisation de l’attribution ?**

L’attribution est recalculée au moment de l’exécution du rapport. Il n’y a donc aucune différence entre prop et eVar (ou toute autre dimension) pour la modélisation d’attribution. Les props peuvent persister à l’aide de n’importe quel intervalle de recherche en amont ou modèle d’attribution, et les paramètres d’attribution/expiration des eVars sont ignorés.

**Quelles sont les dimensions et les mesures non prises en charge ?**

Le panneau d’attribution prend en charge toutes les dimensions. Voici les mesures non prises en charge :

* Visiteurs uniques
* Visites
* Occurrences
* Pages vues
* Mesures d’A4T
* Mesures de durée de la visite
* Rebonds
* Taux de rebond
* Entrées
* Sorties
* Pages introuvables
* Recherches
* Visites sur une seule page
* Accès unique

**Comment l’attribution fonctionne-t-elle avec les filtres ?**

L’attribution s’exécute toujours avant les filtres et les filtres globaux s’exécutent avant toute autre application de filtres de rapport.
