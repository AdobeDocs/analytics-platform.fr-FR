---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# Créer une mesure de participation

Cet article explique comment créer une mesure de participation. Une mesure de participation indique comment les valeurs individuelles d’une dimension (comme Pages vues, Canal marketing) contribuent aux sessions qui contiennent une mesure spécifique (par exemple, Commandes) ou y participent.

Ce type d’informations peut s’avérer utile pour n’importe quel propriétaire de contenu.

>[!NOTE]
>
>Les mesures avec d’autres modèles d’attribution, tels que Participation, peuvent également être créées par les administrateurs dans le cadre d’une [vue de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). Pour plus d’informations, voir [Paramètres du composant d’attribution](../../../data-views/component-settings/attribution.md) .<br/>L’exemple ci-dessous montre comment créer une mesure de participation pour tout utilisateur ayant accès au créateur de mesures calculées dans Workspace.


1. Commencez à créer une mesure, comme décrit dans [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Dans le créateur de mesures calculées, nommez la mesure `Participation` ou un nom similaire.
1. Faites glisser une mesure contenant un événement de succès, par exemple [!DNL Orders], dans le canevas [!UICONTROL Définition].
1. Sélectionnez ![Gear](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) pour la mesure.
1. Dans la fenêtre contextuelle qui s’affiche, sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que par défaut]** pour définir le [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement sur **[!UICONTROL Participation]** et sélectionnez **[!UICONTROL Session]** pour la [!UICONTROL fenêtre de recherche en amont]. Sélectionnez **[!UICONTROL Appliquer]** pour confirmer.

   Dans la zone Définition, la mesure sélectionnée est mise à jour en ajoutant **(Partipation|Session)** à son nom.

   ![Fenêtre contextuelle de modèle d’attribution de colonne affichant Participation sélectionné en tant que modèle et Session sélectionnée pour la fenêtre rétroactive.](assets/participation-setup.png)



1. Sélectionnez [!UICONTROL **Enregistrer**] pour enregistrer la mesure.
1. Utilisez la mesure calculée dans votre rapport. Par exemple, utilisez la mesure [!DNL Orders (Session Participation)] calculée (telle que définie à l’étape 5) dans un rapport pour indiquer quel niveau de client a contribué aux sessions qui contenaient une commande ou y a participé.

   ![Tableau à structure libre présentant le niveau de client et les commandes.](assets/participation-pages-customer-tier.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise, comme décrit dans la section [Partager les mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
