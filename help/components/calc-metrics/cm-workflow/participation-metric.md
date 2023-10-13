---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# Créer une mesure « Participation »

Cet article explique comment créer une mesure qui indique comment les valeurs individuelles d’une dimension sélectionnée (telles que Pages vues, Canal marketing, Version de l’application) ont contribué aux sessions qui contenaient une commande ou y ont participé.

Ce type d’informations peut s’avérer utile pour n’importe quel propriétaire de contenu.

>[!NOTE]
>
>Les mesures avec d’autres modèles d’attribution, tels que Participation, peuvent également être créées par les administrateurs dans le cadre d’une [vue des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=fr). L’exemple ci-dessous montre comment ils peuvent être créés par n’importe quel utilisateur ayant accès au créateur de mesures calculées dans Workspace.

1. Commencez à créer une mesure, comme décrit dans la section [Créer des mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Dans le créateur de mesures calculées, nommez la mesure &quot;Participation&quot; ou quelque chose du même type.
1. Faites glisser l’événement de succès « Commandes » vers le canevas Définition.
1. Sélectionner ![Gear](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) pour le [!DNL Orders] mesures.
1. Dans la fenêtre contextuelle qui s’affiche, sélectionnez **[!UICONTROL Utilisation d’un modèle d’attribution autre que celui par défaut]** pour définir la variable [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement à **[!UICONTROL Participation]** et sélectionnez **[!UICONTROL Session]** pour le [!UICONTROL Intervalle de recherche en amont]. Sélectionner **[!UICONTROL Appliquer]** pour confirmer.

   Dans la zone Définition, ![Événement](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Commandes** est mis à jour vers ![Événement](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Commandes (Partipation|Session)**.

   ![](assets/participation-setup.png)



1. Sélectionner [!UICONTROL **Enregistrer**] pour enregistrer la mesure.
1. Utilisez la mesure calculée dans votre rapport. La mesure calculée ci-dessous est utilisée dans un rapport pour indiquer quel niveau de client a contribué aux sessions qui contenaient une commande ou y a participé.

   ![](assets/participation-pages-customer-tier.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise, comme décrit dans la section [Partage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
