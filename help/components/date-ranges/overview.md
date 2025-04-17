---
title: Présentation des périodes
description: Découvrez les périodes et comment les utiliser dans le compte rendu des performances.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: ht
source-wordcount: '532'
ht-degree: 100%

---

# Présentation des périodes

Dans un projet Workspace, vous utilisez généralement le [calendrier dans un panneau](/help/analysis-workspace/c-panels/panels.md#calendar) pour spécifier la période des visualisations dans ce panneau.

Les composants de période vous permettent de définir et de remplacer les paramètres de calendrier du panneau.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Utilisation de périodes

Vous pouvez utiliser un composant de période pour redéfinir le calendrier du panneau.

Vous pouvez également utiliser une période dans un tableau à structure libre en tant que mesure ou dimension.

![Utilisation de période](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Mesure**. Par exemple, pour comparer une dimension pour deux mois différents pour une mesure spécifique.
- **Dimension**. Pour comparer une mesure sur différents éléments de dimension pour la dimension de période.

>[!NOTE]
>
>Lorsque vous utilisez des périodes dans un tableau à structure libre, elles remplacent le calendrier spécifié pour le panneau auquel appartient le tableau à structure libre.
>

Vous utilisez une période comme vous [utiliseriez n’importe quel composant](/help/components/overview.md#analysis-workspace-components). Vous faites glisser la période à partir du panneau du composant ![Calendrier](/help/assets/icons/Calendar.svg) **[!UICONTROL Périodes]** et déposez le composant sur :

- **[!UICONTROL Calendrier]** : vous ![Basculer](/help/assets/icons/Switch.svg) **[!UICONTROL Remplacez]** la configuration actuelle du calendrier par la période.
- **En-tête de colonne de mesure** : vous ![Basculer](/help/assets/icons/Switch.svg) **[!UICONTROL Remplacez]** la mesure, ![Ajouter](/help/assets/icons/Add.svg)**[!UICONTROL Ajoutez ]**la période en tant que mesure ou ![Filtrer](/help/assets/icons/Filter.svg)**[!UICONTROL  Filtrez ]**la mesure à l’aide du composant de période.
- **En-tête de colonne Dimension** : vous ![Basculer](/help/assets/icons/Switch.svg) **[!UICONTROL Remplacez]** les dimensions actuelles. La nouvelle dimension s’intitule désormais **[!UICONTROL Périodes]**. Une fois que la dimension est Périodes, vous pouvez ![Ajouter](/help/assets/icons/Add.svg)**[!UICONTROL Ajouter ]**des périodes supplémentaires en tant qu’éléments de dimension.
- **Élément de dimension** : vous effectuez une ![Répartition](/help/assets/icons/Breakdown.svg) **[!UICONTROL Répartition]** de l’élément de dimension spécifique par période.

Vous pouvez également ajouter une colonne de période directement dans une visualisation de tableau à structure libre :

1. Dans une colonne de mesure, sélectionnez dans le menu contextuel :

   - **[!UICONTROL Ajoutez une colonne de période]**. Vous pouvez choisir entre les options suggérées basées sur le calendrier actuel ou créer une [période personnalisée](#custom-date-ranges).
   - **[!UICONTROL Comparez des périodes]**. Vous pouvez choisir entre une option suggérée basée sur le calendrier actuel ou créer une [période personnalisée](#custom-date-ranges).

1. Selon votre sélection, d’autres colonnes de périodes sont ajoutées au tableau à structure libre.

## Périodes par défaut

Analysis Workspace propose un certain nombre de périodes par défaut.


| Jour | Semaine | Mois | Trimestre | Année |
|---|---|---|---|---|
| Today | Cette semaine | Ce mois-ci | Ce trimestre | Cette année |
| Hier | Cette semaine (sauf aujourd’hui) | Ce mois (sauf aujourd’hui) | Ce trimestre (sauf aujourd’hui) | Cette année (sauf aujourd’hui) |
| 2 jours auparavant | 2 semaines auparavant | 2 mois auparavant |   |  |
| 3 jours auparavant | 3 semaines auparavant | 3 mois auparavant |  | |
| 7 derniers jours | Semaine dernière | Mois dernier | Dernier trimestre | Année dernière |
| 14 derniers jours | 2 dernières semaines complètes | 2 derniers mois complets | 4 derniers trimestres complets | |
| 30 derniers jours | 3 dernières semaines complètes | 3 derniers mois complets | | |
| 60 derniers jours | 4 dernières semaines complètes | 6 derniers mois complets | | |
| 90 derniers jours | 12 dernières semaines complètes | 12 derniers mois complets | | |
| 7 derniers jours complets | 52 dernières semaines complètes | 13 derniers mois complets | | |
| 14 derniers jours complets | | | | |
| 30 derniers jours complets | | | | |
| 90 derniers jours complets | | | | |

<table style="table-layout:fixed">

## Périodes personnalisées

Vous pouvez créer vos propres périodes personnalisées. Consultez [Créer une période](/help/components/date-ranges/create.md) pour connaître les différentes options disponibles pour créer des périodes. Vous pouvez ensuite créer, modifier et enregistrer des périodes dans le [créateur de périodes](create.md#date-range-builder).

Utilisez le [gestionnaire de périodes](manage.md) pour gérer les périodes.
