---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Modifier les entrées de composant
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 64%

---

# Modifier les entrées de composant

Les administrateurs et administratrices de Customer Journey Analytics peuvent modifier les entrées de composant dans le dictionnaire de données pour une vue de données donnée. Toutes les modifications apportées sont visibles par tous les utilisateurs de la vue de données.

Pour modifier un composant dans le dictionnaire de données :

1. Accédez au projet Analysis Workspace qui contient le composant que vous souhaitez modifier.

1. Sélectionnez l’icône **Dictionnaire de données** dans le panneau de boutons d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![Vue d’administration du dictionnaire de données affichant l’intégrité du dictionnaire](assets/data-dictionary-admin.png)

1. Assurez-vous que la vue de données appropriée est sélectionnée dans le menu déroulant. Par défaut, la vue de données dans laquelle vous vous trouvez déjà s’affiche.

1. (Facultatif) Dans le champ de recherche, commencez à saisir le nom du composant à modifier.

   Le type de composant peut être identifié à la fois par couleur et par icône. **Les dimensions** ![icône Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sont orange, **les segments** ![icône Segment](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sont bleus, **les périodes** ![icône Période](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sont violettes et **les mesures** ![icône Mesure](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sont vertes. L’icône Adobe indique soit un modèle de mesure calculée, soit un modèle de segment. L’icône du calculateur ![icône Calculateur](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indique une mesure calculée qui a été créée par un administrateur ou une administratrice Analytics de votre entreprise.

1. (Facultatif) Sélectionnez l’icône **Filtre** ![icône Filtre du dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), puis sélectionnez l’une des options de segment suivantes pour segmenter la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme approuvés par l’administration. |
   | [!UICONTROL **Favoris**] | Affichez uniquement les composants figurant dans votre liste de favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, consultez la section [Présentation des composants](/help/components/overview.md). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des dimensions. (Cette option est également disponible dans l’onglet [!UICONTROL **Segments rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. (Cette option est également disponible dans l’onglet [!UICONTROL **Segments rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Segments**] | Afficher uniquement les composants qui sont des segments. (Cette option est également disponible dans l’onglet [!UICONTROL **Segments rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. (Cette option est également disponible dans l’onglet [!UICONTROL **Segments rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Tout afficher**] | Permet d’afficher tous les composants. Cette option est réservée à l’administration. |
   | [!UICONTROL **Non approuvé**] | Permet de n’afficher que les composants qui n’ont pas encore été marqués comme approuvés par l’administration. Cette option est utile pour l’administration pour identifier les composants qui doivent être examinés et approuvés. Cette option est réservée à l’administration. |
   | [!UICONTROL **Description manquante**] | Afficher uniquement les composants qui n’ont pas encore de description dans le champ de description. Cette option est réservée à l’administration. |
   | [!UICONTROL **Afficher les doublons**] | Afficher uniquement les composants portant le même nom ou la même description qu’un autre composant de la vue de données sélectionnée. Cela inclut les composants que vous créez, ainsi que ceux fournis par Adobe. Les noms ou descriptions doivent correspondre exactement pour apparaître comme des doublons. Cette option est réservée à l’administration. |
   | [!UICONTROL **Aucune donnée récente**] | Afficher uniquement les composants qui n’ont collecté aucune donnée au cours des 90 derniers jours. Cette option est réservée à l’administration. |
   | [!UICONTROL **Création Adobe**] <!-- I don't see this option--> | Afficher uniquement les composants créés par Adobe. Les composants créés par l’administration ou une autre personne de votre organisation ne s’affichent pas. |

   {style="table-layout:auto"}

1. (Facultatif) Sélectionnez l’icône **Trier** ![Icône Trier les composants](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), puis sélectionnez l’une des options de segment suivantes pour trier la liste des composants :

{{components-sort-options}}

1. Dans la liste des composants, sélectionnez le composant à modifier.

1. Sélectionnez l’icône **Modifier** ![icône Modifier le dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) en regard du nom du composant.

1. Modifiez l’une des informations suivantes sur le composant :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administration.</p><p>Un bouton [!UICONTROL **Désapprouver**] apparaît pour l’administration. Si vous sélectionnez cette option, le composant est marqué comme « Non approuvé » pour les utilisateurs et utilisatrices.</p> |
   | [!UICONTROL **Non approuvé**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administration.</p><p>Un bouton dédié permet à l’administration d’[!UICONTROL **Approuver**] le composant. Celui-ci est alors marqué comme « Approuvé » pour les utilisateurs et utilisatrices.</p> |
   | [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administration Analytics, comme décrit dans la section [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md)). |
   | [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants peuvent s’afficher parmi les 5 types de composants principaux : mesure, mesure calculée, Dimension, segment et période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous êtes en droit de consulter s’affichent.</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Avant de procéder à la sélection des composants visibles par les utilisateurs et utilisatrices, appliquez le segment **Tout afficher** afin de vous assurer de voir tous les composants, non partagés avec vous, qui ont pu être ajoutés par un autre administrateur ou une autre administratrice.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **Similaire à**] | <p>Permet d’afficher les composants dotés de noms similaires au composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants peuvent s’afficher parmi les 5 types de composants principaux : mesure, mesure calculée, Dimension, segment et période.</p><p>Seuls les composants que vous êtes autorisé à consulter s’affichent.</p><p>Tous les composants en double de votre vue de données s’afficheront ici. L’administration d’Analytics doit identifier et supprimer tous les composants en double, comme décrit dans la section [Surveiller l’intégrité du dictionnaire de données](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Avant de procéder à la sélection des composants visibles par les utilisateurs et utilisatrices, appliquez le segment **Tout afficher** afin de vous assurer de voir tous les composants, non partagés avec vous, qui ont pu être ajoutés par un autre administrateur ou une autre administratrice.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**Remarque :** actuellement, la section **Similaire à** comprend uniquement les composants que vous créez, et non ceux fournis par Adobe. Les composants fournis par Adobe seront ajoutés dans une version ultérieure.</p> |
   | [!UICONTROL **Compatibilité des produits**] | Indique où, dans Customer Journey Analytics, cette mesure calculée peut être utilisée. <p>Les valeurs possibles sont les suivantes :</p><ul><li>[!UICONTROL **Partout dans Customer Journey Analytics**] : la mesure calculée peut être utilisée dans l’ensemble de Customer Journey Analytics, y compris dans Analysis Workspace, Report Builder, etc.</li><li>[!UICONTROL **Partout dans Customer Journey Analytics (à l’exclusion de l’expérimentation)**] : la mesure calculée peut être utilisée dans tout Customer Journey Analytics, sauf dans le panneau Expérimentation.</li> <p>Pour plus d’informations sur les critères qui déterminent si une mesure calculée peut être utilisée avec l’expérimentation, voir [Utiliser des mesures calculées dans le panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) dans [panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Balises**] | Affiche toutes les balises associées au composant. L’administration peut ajouter des balises lors de la modification du composant. |
   | [!UICONTROL **Type de composant**] | Indique le type du composant : dimension, mesure, segment ou période. |
   | [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur ou de l’utilisatrice ayant créé le composant. |
   | [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
   | [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lorsque vous affichez des segments, des mesures, des mesures calculées et des périodes. |

   {style="table-layout:auto"}

1. Cliquez sur l’icône **Enregistrer** ![icône Enregistrer le dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) pour enregistrer vos modifications.
