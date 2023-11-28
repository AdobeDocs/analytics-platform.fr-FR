---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 6%

---

# Création d’une mesure de participation

Cet article explique comment créer une mesure de participation. Une mesure de participation indique comment les valeurs individuelles d’une dimension (comme Pages vues, Canal marketing) contribuent aux sessions qui contiennent une mesure spécifique (par exemple, Commandes) ou y participent.

Ce type d’informations peut s’avérer utile pour n’importe quel propriétaire de contenu.

>[!NOTE]
>
>Les mesures avec d’autres modèles d’attribution, tels que Participation, peuvent également être créées par les administrateurs dans le cadre d’une [vue des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr). Voir [Paramètres du composant d’attribution](../../../data-views/component-settings/attribution.md) pour plus d’informations.<br/>L’exemple ci-dessous illustre la manière dont une mesure de participation peut être créée par n’importe quel utilisateur ayant accès au créateur de mesures calculées dans Workspace.


1. Commencez à créer une mesure, comme décrit dans la section [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Dans le créateur de mesures calculées, nommez la mesure. `Participation` ou quelque chose de similaire.
1. Faites glisser une mesure contenant un événement de succès, par exemple [!DNL Orders], dans le [!UICONTROL Définition] canevas.
1. Sélectionner ![Gear](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) pour la mesure.
1. Dans la fenêtre contextuelle qui s’affiche, sélectionnez **[!UICONTROL Utilisation d’un modèle d’attribution autre que celui par défaut]** pour définir la variable [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement à **[!UICONTROL Participation]** et sélectionnez **[!UICONTROL Session]** pour le [!UICONTROL Intervalle de recherche en amont]. Sélectionner **[!UICONTROL Appliquer]** pour confirmer.

   Dans la zone Définition, la mesure sélectionnée est mise à jour en ajoutant  **(Partipation|Session)** à son nom.

   ![Fenêtre contextuelle de modèle d’attribution de colonne présentant Participation sélectionné comme modèle et Session sélectionnée pour la fenêtre rétroactive.](assets/participation-setup.png)



1. Sélectionner [!UICONTROL **Enregistrer**] pour enregistrer la mesure.
1. Utilisez la mesure calculée dans votre rapport. Par exemple, utilisez le [!DNL Orders (Session Participation)] mesure (comme défini à l’étape 5) d’un rapport afin d’indiquer le niveau de client qui a contribué aux sessions qui contenaient une commande ou y a participé.

   ![Tableau à structure libre présentant les niveaux client et les commandes.](assets/participation-pages-customer-tier.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise, comme décrit dans la section [Partage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
