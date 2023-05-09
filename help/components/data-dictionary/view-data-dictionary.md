---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Afficher le dictionnaire de données
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: d431e781eb18eb3f4904094972c218a9e80980d9
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 55%

---

# Afficher des informations sur les composants dans le dictionnaire de données

Le dictionnaire de données vous permet d’afficher des informations sur un composant, notamment sa description, des composants similaires, les autres composants fréquemment utilisés avec lui, etc.

Pour afficher des informations sur un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez afficher.

1. Sélectionnez l’icône [!UICONTROL **Dictionnaire de données**] dans le rail gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![data-dictionary.png.](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assurez-vous que la vue de données contenant le composant que vous souhaitez afficher est sélectionnée dans le menu déroulant. Par défaut, la vue de données dans laquelle vous vous trouvez est affichée.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à afficher.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Dimensions** ![Icône Dimension](assets/dimension-icon.png) sont orange, **Segments** ![Icône Segment](assets/segment-icon.png) sont bleues, **Périodes** ![Icône Période](assets/date-range-icon.png) sont violets et **Mesures** ![Icône Mesure](assets/default-metric-icon.png) sont vertes. Icône Adobe ![Icône Adobe](assets/default-calc-metric-icon.png) indique soit un modèle de mesure calculée, soit un modèle de segment, et l’icône du calculateur ![Icône Calcul](assets/calculated-metric-icon-created.png) indique une mesure calculée qui a été créée par un administrateur Analytics de votre entreprise.

{{dd-filter-criteria}}

1. (Facultatif) Sélectionnez le **Tri** icon ![Icône Tri des composants](assets/component-sort-icon.png), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

   {{components-sort-options}}

1. Dans la liste des composants, sélectionnez le composant à afficher.

   Les informations suivantes sur le composant s’affichent :

   {{dd-component-information}}

1. (Facultatif) Faites glisser un composant du dictionnaire de données vers Analysis Workspace.
