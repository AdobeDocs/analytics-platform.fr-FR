---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Affichage des informations sur les composants
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 73%

---

# Affichage des informations sur les composants

Le dictionnaire de données vous permet d’afficher des informations sur un composant, notamment sa description, des composants similaires, les autres composants fréquemment utilisés avec lui, etc.

Pour afficher des informations sur un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez afficher.

1. Sélectionnez l’icône [!UICONTROL **Dictionnaire de données**] dans le panneau de gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![ Fenêtre du dictionnaire de données présentant les filtres rapides pour les Dimensions, les mesures, les segments et les plages de dates ](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assurez-vous que la vue de données contenant le composant que vous souhaitez afficher est sélectionnée dans le menu déroulant. Par défaut, la vue de données dans laquelle vous vous trouvez est affichée.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à afficher.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Les Dimensions** ![Icône de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sont orange, **Filtres** ![Icône de segment](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sont bleue, **Plages de dates** ![Icône de plage de dates](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) est violette et **Mesures** ![Icône de mesure](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)} est verte. L’icône Adobe ![icône Adobe](assets/default-calc-metric-icon.png) indique soit un modèle de mesure calculée, soit un modèle de filtre. L’icône du calculateur ![icône Calculateur](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indique une mesure calculée qui a été créée par un administrateur ou une administratrice Analytics de votre entreprise.

{{dd-filter-criteria}}

1. (Facultatif) Sélectionnez l’icône **Trier** ![icône Trier les composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

   {{components-sort-options}}

1. Dans la liste des composants, sélectionnez le composant à afficher.

   Les informations suivantes sur le composant s’affichent :

   {{dd-component-information}}

1. (Facultatif) Faites glisser un composant du dictionnaire de données vers Analysis Workspace.
