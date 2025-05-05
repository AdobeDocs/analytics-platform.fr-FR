---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Mesures de participation

Les mesures de participation sont utilisées pour quantifier la manière dont les valeurs individuelles d’une dimension (comme Pages vues) contribuent aux sessions qui contiennent une mesure spécifique (comme Commandes) ou y participent.

>[!NOTE]
>
>Les administrateurs peuvent créer des mesures avec des modèles d’attribution autres que ceux par défaut, tels que Participation, dans le cadre d’une [vue de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views). Pour plus d’informations, voir [Paramètres du composant d’attribution](../../../data-views/component-settings/attribution.md) .

Les étapes ci-dessous montrent comment tout utilisateur disposant de l’[autorisation Créer une mesure calculée](/help/technotes//access-control.md#user-level-access) peut créer une mesure de participation.

1. [Créez une mesure calculée](cm-workflow.md) et dans le [créateur de mesures calculées](cm-build-metrics.md), nommez la mesure `Participation` ou quelque chose du même type.
1. Faites glisser une mesure contenant un événement de succès, par exemple [!DNL Orders], dans la zone [!UICONTROL **[!UICONTROL Définition]**].
1. Sélectionnez ![Gear](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) pour la mesure.
1. Dans la fenêtre contextuelle qui s’affiche, sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que par défaut]** pour définir le [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement sur **[!UICONTROL Participation]** et sélectionnez **[!UICONTROL Session]** pour la [!UICONTROL fenêtre de recherche en amont]. Sélectionnez **[!UICONTROL Appliquer]** pour confirmer.


   ![Fenêtre contextuelle de modèle d’attribution de colonne affichant Participation sélectionné en tant que modèle et Session sélectionnée pour la fenêtre rétroactive.](assets/participation-setup.png)

   **(Partipation|Session)** est ajouté au nom du composant de mesure.



1. Sélectionnez [!UICONTROL **Enregistrer**] pour enregistrer la mesure.
1. Utilisez la mesure calculée dans votre rapport. Par exemple, utilisez la mesure [!DNL Orders (Session Participation)] calculée dans un rapport pour indiquer quel niveau de client a contribué aux sessions qui contenaient une commande ou y a participé.

   ![Tableau à structure libre présentant le niveau de client et les commandes.](assets/participation-pages-customer-tier.png)
