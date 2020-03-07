---
title: Principes de base de Workspace
description: Décrit comment extraire des rapports de base dans Workspace
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# Principes de base de Workspace

Si vous n’êtes pas encore familiarisé avec l’outil Workspace, voici quelques conseils pour commencer.

Workspace est le principal outil d’Adobe pour prendre des décisions basées sur les données exploitables pour votre entreprise. La visualisation la plus courante, le tableau à structure libre, vous permet de créer facilement des rapports personnalisés à l’aide de dimensions, de mesures, de segments et de périodes.

## Extraction d’un rapport de classement de base dans Workspace

Un rapport de classement affiche une vue totale agrégée de chaque valeur de dimension, en indiquant d’abord les valeurs les plus élevées. Ces types de rapports sont utiles pour identifier les composants de votre site les plus efficaces, tels que les pages qui génèrent le plus de trafic ou les produits les plus vendus.

1. Vérifiez que vous êtes connecté à [analytics.adobe.com](https://analytics.adobe.com).
1. Dans la barre de navigation supérieure, cliquez sur **[!UICONTROL Workspace]**.
1. Cliquez sur **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. Sur la gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de périodes. Recherchez la dimension Pages (de couleur orange), puis faites-la glisser sur la zone de travail qui indique « Déposer la dimension ici ».
1. Un rapport présentant les principales pages de ce mois est visible. Analysis Workspace a automatiquement renseigné la mesure [Occurrences](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) dans le rapport.
1. Recherchez la mesure Visites (de couleur verte) et faites-la glisser **sur** ou **en regard** de l’en-tête de la mesure Occurrences (évitez de la placer au-dessus de la mesure). Si vous faites glisser la mesure Visites au-dessus de la mesure Occurrences, elle est remplacée dans les rapports. Si vous faites glisser la mesure Visites en regard de la mesure Occurrences, les deux mesures s’affichent côte à côte.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Extraire un rapport de tendance de base dans Workspace

Un rapport de tendance affiche une vue de dépassement de délai à l’aide de la période sélectionnée. Ces types de rapports sont utiles pour identifier les tendances dans le temps et peuvent servir à évaluer l’issue positive ou négative des décisions professionnelles. Vous pouvez, par exemple, examiner un rapport de pages vues avec des tendances au fil du temps pour voir si un site repensé a contribué à augmenter ou à diminuer le trafic.

1. Vérifiez que vous êtes connecté à [analytics.adobe.com](https://analytics.adobe.com).
1. Dans la barre de navigation supérieure, cliquez sur **[!UICONTROL Workspace]**.
1. Cliquez sur **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. Sur la gauche, vous devriez voir une liste de dimensions, de mesures, de segments et de périodes. Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. Évitez de la déposer dans l’espace réservé aux dimensions (au moins pour cet exercice).
1. Notez que si la suite de rapports contient des données, vous devriez voir un rapport de pages vues de base avec des tendances pour le mois en cours. Analysis Workspace insère automatiquement la période « Jour » afin que vous puissiez afficher la tendance des pages vues pour le mois en cours.
1. Recherchez la période Semaine (de couleur violette) dans la liste des composants de périodes sur la gauche. Cliquez sur le titre de la période pour développer et afficher tous les composants de la période ou utilisez la barre de recherche.
1. Faites glisser la période Semaine au-dessus de l’en-tête de la période Jour sur la zone de travail afin de la remplacer.
1. Notez que votre rapport de tendance est désormais agrégé par semaine plutôt que par jour.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Tester l’outil

 Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition.

Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou sur cmd+Z (Mac) pour annuler la dernière action effectuée. You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## Résolution des problèmes

### Lorsque je fais glisser une mesure sur l’écran, un message indique « Données incorrectes ».

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

### Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée à proprement dit, seulement des zéros.

Si vous êtes parvenu à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :

* Vérifiez deux fois la suite de rapports et assurez-vous qu’elle contient des données.
* Si vous utilisez un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la période dans le coin supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site web et utilisez Debugger pour vérifier que la collecte des données s’effectue.

## Ressources supplémentaires

Notez que les ressources suivantes peuvent faire référence à l’utilisation de Workspace dans le produit Adobe Analytics traditionnel, et non dans les analyses de parcours du client.

* Publications du blog :
   * [Empowering Organizations with Smarter Analysis](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (Doter les entreprises d’outils nécessaires grâce à Smarter Analysis, en anglais)
   * [Espace de travail  : La sauce secrète devient plus savoureuse](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Why You Should Be Using Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/) (Pour quelles raisons devriez-vous utiliser Analysis Workspace, en anglais)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/) (5 conseils pour optimiser votre productivité avec Analysis Workspace, en anglais)

## Étapes suivantes

Il y a beaucoup de directions pour approfondir votre compréhension de Workspace. Voici quelques principes de base recommandés par Adobe :

### Pour les utilisateurs finaux qui souhaitent approfondir leurs connaissances sur l’utilisation de Workspace

* [Détails sur l’interface utilisateur de Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html) : maintenant que vous avez créé un rapport de base, familiarisez-vous avec le reste de l’interface.
* [Visualisations dans Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) : les tableaux à structure libre ne sont qu’un type de visualisation dans Analysis Workspace. Découvrez comment utiliser d’autres visualisations, comme des graphiques en courbes, des graphiques en barres et des cartes géographiques.
* [Dimensions dans Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html) : apprenez-en plus sur les dimensions et leur utilisation dans d’autres cas que les rapports de classement.
* [Mesures dans Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) : apprenez-en plus sur les mesures et leur utilisation dans d’autres parties des tableaux à structure libre.
* [Introduction à la segmentation](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) : apprenez-en plus sur les segments et extrayez un rapport de base à l’aide d’un segment.
* [Périodes dans Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) : apprenez-en plus sur les dates relatives et roulantes, et utilisez-les dans les projets Workspace.
* [Partage de projets dans Workspace : montrez à votre collègue l’incroyable projet Workspace que vous avez créé.](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### Pour les analystes et les administrateurs qui souhaitent améliorer la qualité de Workspace au sein de leur entreprise

* [Autorisations d’Analysis Workspace](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) : attribuez des autorisations d’utilisateur à Workspace via Adobe Admin Console.
* [Modèles dans Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) : créez des modèles pour que vos collègues puissent commencer avec un espace de projet adapté à leurs besoins.
* [Traitement de Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html) : créez un projet qui limite les composants disponibles, en rendant Workspace plus accessible aux personnes moins familières avec l’outil.
