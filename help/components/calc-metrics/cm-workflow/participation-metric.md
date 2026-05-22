---
description: Découvrez comment créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
TQID: https://experienceleague.adobe.com/no7rAZUl25LTEPqwRyC7vY4XcottzPGRq-DCAR5ez54
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 9%

---

# Mesures de participation

Les mesures de participation sont utilisées pour quantifier la manière dont les valeurs individuelles d’une dimension (telles que les Pages vues) contribuent à une mesure spécifique ou participent à des sessions qui contiennent une mesure spécifique (telles que les Commandes).

>[!NOTE]
>
>L’administration peut créer des mesures avec des modèles d’attribution autres que ceux par défaut, tels que Participation, dans le cadre d’une [vue de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/data-views). Voir [ Paramètres des composants : attribution](../../../data-views/component-settings/attribution.md) pour plus d’informations.

Les étapes ci-dessous montrent comment tout utilisateur disposant de l’autorisation [Créer une mesure calculée](/help/technotes//access-control.md#user-level-access) peut créer une mesure de participation.

1. [Créez une mesure calculée](cm-workflow.md) puis, dans le [créateur de mesures calculées](cm-build-metrics.md), nommez la mesure `Participation` ou une méthode similaire.
1. Faites glisser une mesure contenant un événement de succès, par exemple [!DNL Orders], dans la zone [!UICONTROL **[!UICONTROL Définition]**].
1. Sélectionnez ![Engrenage](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) pour la mesure.
1. Dans la fenêtre contextuelle qui s’affiche, sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]** pour définir le [modèle d’attribution](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) de cet événement sur **[!UICONTROL Participation]** et sélectionnez **[!UICONTROL Session]** pour le [!UICONTROL Conteneur]. Sélectionnez **[!UICONTROL Appliquer]** pour confirmer.


   ![Fenêtre contextuelle de modèle d’attribution de colonne affichant la participation sélectionnée en tant que modèle et la session sélectionnée pour l’intervalle de recherche en amont.](assets/participation-setup.png)

   **(Participation|Session)** est ajouté au nom du composant de mesure.



1. Sélectionnez [!UICONTROL **Enregistrer**] pour enregistrer la mesure.
1. Utilisez la mesure calculée dans votre rapport. Par exemple, utilisez la mesure [!DNL Orders (Session Participation)] calculée dans un rapport pour indiquer le niveau client qui a contribué aux sessions contenant une commande ou qui y a participé.

   ![Tableau à structure libre présentant le niveau client et les commandes.](assets/participation-pages-customer-tier.png)
