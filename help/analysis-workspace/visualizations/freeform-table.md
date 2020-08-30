---
title: Tableau à structure libre
description: En savoir plus sur les tableaux à structure libre et le créateur de tableaux à structure libre
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 100%

---


# Tableau à structure libre

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Dans Analysis Workspace, un tableau à structure libre n’est pas simplement un tableau de données, mais également une visualisation interactive. Vous pouvez faire glisser et déposer un ensemble de [composants](/help/components/overview.md) dans les lignes et les colonnes afin de créer un tableau personnalisé pour votre analyse. À mesure que chaque composant est déposé, le tableau est mis à jour en temps réel afin que vous puissiez effectuer une analyse rapide.

Vous pouvez personnaliser le tableau de différentes manières :

* **Lignes**
   * Chaque ligne de dimension peut afficher jusqu’à 400 lignes avant la pagination. Vous pouvez afficher davantage de lignes sur un seul écran en réglant la [densité d’affichage](/help/analysis-workspace/build-workspace-project/view-density.md) du projet.
   * Les lignes peuvent être ventilées par composants supplémentaires. Pour ventiler plusieurs lignes à la fois, sélectionnez simplement plusieurs lignes, puis faites glisser le composant suivant sur les lignes sélectionnées. En savoir plus sur la [ventilation](/help/components/dimensions/t-breakdown-fa.md).
   * Les lignes peuvent être [filtrées](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md) pour n’afficher que certains éléments. D’autres paramètres sont disponibles dans les [Paramètres des lignes](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md).

* **Colonnes**
   * Les composants peuvent être empilés dans des colonnes afin de créer des mesures segmentées, des analyses sur plusieurs onglets, etc.
   * La vue de chaque colonne peut être ajustée dans les [Paramètres des colonnes](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md).
   * Plusieurs actions sont disponibles dans le [menu contextuel (clic droit)](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Ce menu propose différentes actions selon que vous cliquez sur l’en-tête, les lignes ou les colonnes du tableau.

## Créateur de tableau à structure libre

Si vous préférez d’abord ajouter plusieurs composants à votre tableau, puis effectuer le rendu des données, vous pouvez activer le Créateur de tableau à structure libre. Une fois le créateur de tableau activé, vous pouvez faire glisser et déposer de nombreuses dimensions, ventilations, mesures et segments afin de créer des tableaux qui répondent à des problématiques plus complexes. Les données ne sont pas mises à jour à la volée, elles le sont une fois que vous avez cliqué sur **[!UICONTROL Créer]**.

Le Créateur de tableau est une option qui vous permet de gagner du temps lorsque vous avez une question complexe et que vous avez une idée du tableau à construire pour y répondre. Le créateur de tableau offre d’autres avantages :

* Organisez le tableau dans le format exact dont vous avez besoin, sans avoir à attendre le rendu de chaque action.
* Exécutez rapidement jusqu’à 4 niveaux de ventilation.
* Définissez les paramètres Ligne et Ventilation pour chaque ligne de tableau et colonne de dimension.
* Réalisez une **[!UICONTROL Ventilation par position]** pour chaque niveau du tableau par défaut (dans les tableaux à structure libre classiques, la valeur par défaut est **[!UICONTROL Ventilation par élément]**).
* Organisez manuellement les lignes statiques dans le tableau. Par exemple, si vous souhaitez que les lignes de mesure apparaissent dans un certain ordre.
* Prévisualisez le format de votre tableau avant de générer des données réelles.

Découvrez le Créateur de tableau à structure libre en action [ici](https://youtu.be/GUMWiJAmMGI).

## Exportation des données de tableau à structure libre

Les données d’un tableau à structure libre peuvent être copiées depuis Analysis Workspace de plusieurs manières :

* Cliquez avec le bouton droit sur l’en-tête du tableau et sélectionnez **[!UICONTROL Copier dans le Presse-papiers]**. Le tableau complet (visible) est alors exporté.
* Mettez en surbrillance des cellules spécifiques du tableau, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Copier dans le Presse-papiers]** ou utilisez le raccourci Ctrl + C.
* **[!UICONTROL Projet > Télécharger CSV]**. Cette opération exporte tous les tableaux visibles du projet au format CSV.
