---
title: Créer un schéma XDM pour le connecteur source Analytics
description: Découvrez comment créer un schéma XDM pour le connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 8%

---

# Créer un schéma XDM pour le connecteur source Analytics

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

1. Si vous ne disposez pas déjà d’un connecteur source Analytics, [créez le connecteur source Analytics et mappez les champs à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Ou

   Si vous disposez déjà d’un connecteur source Analytics, [mappez les champs du connecteur source vers votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Ajouter le jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Créer un schéma XDM pour le connecteur source Analytics

Vous devez avoir déjà [créé un nouveau schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) pour que votre mise en oeuvre de SDK Web Experience Platform l’utilise avec Customer Journey Analytics. Ce schéma doit contenir tous les groupes de champs pour les champs sur lesquels vous prévoyez de collecter des données.

Vous devez maintenant utiliser les mêmes groupes de champs de votre schéma SDK Web et les ajouter à un nouveau schéma que vous pouvez utiliser avec le connecteur source Analytics.

Ce schéma pour le connecteur source Analytics doit contenir :

* Tous les groupes de champs (y compris les groupes de champs personnalisés que vous avez créés) qui sont inclus dans votre schéma personnalisé que vous avez créé pour votre mise en oeuvre du SDK Web. (Tous les champs personnalisés qui ne font pas partie d’un groupe de champs par défaut doivent avoir été ajoutés à votre schéma SDK Web dans le cadre d’un groupe de champs personnalisé.)

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
