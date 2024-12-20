---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Modification des entrées du composant
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 57%

---

# Modification des entrées du composant

Les administrateurs de Customer Journey Analytics peuvent modifier les entrées de composant dans le dictionnaire de données pour une vue de données donnée. Toutes les modifications apportées sont visibles par tous les utilisateurs de la vue de données.

Pour modifier un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez modifier.

1. Sélectionnez l’icône **Dictionnaire de données** dans le panneau des boutons d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![ Vue administrateur du dictionnaire de données affichant l’intégrité du dictionnaire ](assets/data-dictionary-admin.png)

1. Assurez-vous que la vue de données appropriée est sélectionnée dans le menu déroulant. Par défaut, la vue de données dans laquelle vous vous trouvez est affichée.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à modifier.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Les Dimensions** ![Icône de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sont orange, **Filtres** ![Icône de segment](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sont bleue, **Plages de dates** ![Icône de plage de dates](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) est violette et **Mesures** ![Icône de mesure](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)} est verte. L’icône d’Adobe indique soit un modèle de mesure calculée, soit un modèle de filtre, et l’icône de calculateur ![Icône de calculateur](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indique une mesure calculée créée par un administrateur Analytics de votre entreprise.

   {{dd-filter-criteria}}

1. (Facultatif) Sélectionnez l’icône **Trier** ![icône Trier les composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour trier la liste des composants :

{{components-sort-options}}

1. Dans la liste des composants, sélectionnez le composant à modifier.

1. Sélectionnez l’icône **Modifier** ![icône Modifier le dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) en regard du nom du composant.

1. Modifiez l’une des informations suivantes sur le composant :

{{dd-component-information}}

1. Cliquez sur l’icône **Enregistrer** ![icône Enregistrer le dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) pour enregistrer vos modifications.
