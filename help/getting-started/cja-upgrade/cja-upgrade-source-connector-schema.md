---
title: Créer un schéma personnalisé pour le connecteur source Analytics
description: Découvrir comment créer un schéma personnalisé pour le connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
autotag-review: '2026-05-19T08:17:31.632Z'
TQID: 'https://experienceleague.adobe.com/ov6cr-MF9OeH8OU23Km0KdD2l0LirVpVor4nndHpqo8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 587
ht-degree: 100%

---

# Créer un schéma personnalisé pour le connecteur source Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Créer un schéma pour le connecteur source Analytics"
>abstract="Ce schéma est une combinaison du groupe de champs ExperienceEvent Adobe Analytics avec tous les groupes de champs qui constituent le schéma personnalisé de votre organisation. Cela vous permet de mapper les champs utilisés par le connecteur source Analytics au schéma de votre organisation et n’est utilisé que pour les données historiques.<br><br>Bien que technique par nature, la création de ce schéma peut se faire en quelques heures, peut-être plus rapidement si vous savez exactement quels groupes de champs constituent le schéma personnalisé de votre organisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="Créer le connecteur source Analytics pour les données historiques"
>abstract="Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques dans Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Comprendre comment le connecteur source Analytics peut importer des données historiques dans Customer Journey Analytics.

Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques dans Customer Journey Analytics.

Ce processus suppose que vous souhaitez [créer un schéma personnalisé à utiliser avec votre implémentation du SDK web Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), car vous souhaitez un schéma rationalisé et adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.

Pour utiliser le connecteur source Analytics afin d’importer des données historiques dans Customer Journey Analytics, vous devez effectuer ce qui suit :

1. Créez un schéma personnalisé pour le connecteur source Analytics, comme décrit ci-dessous.

1. Si vous ne disposez pas déjà d’un connecteur source Analytics, [créez le connecteur source Analytics et mappez les champs à votre schéma personnalisé](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Ou

   Si vous disposez déjà d’un connecteur source Analytics, [mappez les champs du connecteur source à votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Ajouter le jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Créer un schéma personnalisé pour le connecteur source Analytics

Vous devez avoir déjà [créé un schéma personnalisé](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) pour que votre implémentation du SDK web Experience Platform l’utilise avec Customer Journey Analytics. Ce schéma doit contenir tous les groupes de champs pour les champs sur lesquels vous prévoyez de collecter des données.

Vous devez maintenant utiliser ces mêmes groupes de champs de votre schéma de SDK web et les ajouter à un nouveau schéma que vous pouvez utiliser avec le connecteur source Analytics.

Ce schéma pour le connecteur source Analytics doit contenir les éléments suivants :

* Tous les groupes de champs (y compris les groupes de champs personnalisés que vous avez créés) inclus dans le schéma personnalisé que vous avez créé pour votre implémentation du SDK web. (Tous les champs personnalisés qui ne font pas partie d’un groupe de champs par défaut doivent avoir été ajoutés à votre schéma de SDK web dans le cadre d’un groupe de champs personnalisés.)

* Groupe de champs Modèle ExperienceEvent Adobe Analytics

Pour créer le schéma personnalisé à utiliser avec le connecteur source Analytics, procédez comme suit :

1. Dans Adobe Experience Platform, commencez à créer un schéma personnalisé, comme décrit dans la section [Créer un schéma personnalisé à utiliser avec votre implémentation du SDK web Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Ajoutez tous les groupes de champs (y compris les groupes de champs personnalisés) inclus dans le schéma que vous avez créé pour votre implémentation du SDK web.

1. Une fois que vous avez terminé d’ajouter ces groupes de champs, ajoutez le groupe de champs ExperienceEvent Adobe Analytics :

   Dans la section **[!UICONTROL Groupes de champs]**, sélectionnez **[!UICONTROL Ajouter]** pour ajouter un groupe de champs supplémentaire.

   ![Ajouter un groupe de champs au schéma](assets/schema-add-field-group.png)

1. Recherchez et sélectionnez le groupe de champs **[!UICONTROL Modèle ExperienceEvent Adobe Analytics]**.

   ![Ajouter le groupe de champs ExperienceEvent Adobe Analytics](assets/schema-experienceevent.png)

1. Sélectionnez **[!UICONTROL Ajouter des groupes de champs]**.

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le schéma.

{{upgrade-final-step}}
