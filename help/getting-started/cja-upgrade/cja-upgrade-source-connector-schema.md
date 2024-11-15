---
title: Création d’un schéma XDM pour le connecteur source Analytics
description: Découvrez comment créer un schéma XDM pour le connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: aedf7a2ad41b09521938b789dbaf1c193cdb661f
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 1%

---

# Création d’un schéma XDM pour le connecteur source Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

## Comprendre comment le connecteur source Analytics peut importer des données historiques dans Customer Journey Analytics

Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques en Customer Journey Analytics.

Ce processus suppose que vous souhaitiez [créer un schéma XDM lors de la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), car vous souhaitez un schéma rationalisé adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.

Pour utiliser le connecteur source Analytics afin d’importer des données historiques dans Customer Journey Analytics, vous devez :

1. Créez un schéma XDM pour le connecteur source Analytics, comme décrit ci-dessous.

1. [Création des champs de mappage et du connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)

1. [Ajout du jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Création d’un schéma XDM pour le connecteur source Analytics

Vous devez avoir déjà [créé un nouveau schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) pour que votre mise en oeuvre de SDK Web Experience Platform l’utilise avec Customer Journey Analytics. Ce schéma doit contenir tous les groupes de champs pour les champs sur lesquels vous prévoyez de collecter des données.

Outre le schéma XDM que vous avez déjà créé pour votre implémentation du SDK Web, vous devez maintenant créer un deuxième schéma XDM à utiliser avec le connecteur source Analytics pour importer les données historiques dans Customer Journey Analytics.

Ce deuxième schéma doit contenir :

* Tous les groupes de champs (y compris tous les groupes de champs personnalisés) inclus dans le schéma que vous avez créé pour l’implémentation de votre SDK Web. (Tous les champs personnalisés qui ne font pas partie d’un groupe de champs par défaut doivent avoir été ajoutés à votre schéma SDK Web dans le cadre d’un groupe de champs personnalisé.)

* Groupe de champs Modèle ExperienceEvent Adobe Analytics

Pour créer le schéma XDM à utiliser avec le connecteur source Analytics :

1. Dans Adobe Experience Platform, commencez à créer un schéma XDM comme décrit dans [Création d’un schéma XDM à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Ajoutez tous les groupes de champs (y compris les groupes de champs personnalisés) inclus dans le schéma que vous avez créé pour votre implémentation du SDK Web.

1. Une fois l’ajout de ces groupes de champs terminé, ajoutez le groupe de champs Adobe Analytics ExperienceEvent :

   Dans la section **[!UICONTROL Groupes de champs]**, sélectionnez **[!UICONTROL Ajouter]** pour ajouter un groupe de champs supplémentaire.

   ![Ajouter un groupe de champs au schéma](assets/schema-add-field-group.png)

1. Recherchez et sélectionnez le groupe de champs **[!UICONTROL Adobe Analytics ExperienceEvent Template]**.

   ![Ajouter le groupe de champs Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Sélectionnez **[!UICONTROL Ajouter des groupes de champs]**.

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le schéma.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
