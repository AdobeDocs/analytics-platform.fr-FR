---
title: Créer une propriété de balise et ajouter l’extension SDK web
description: Découvrir comment créer une propriété de balise et ajouter l’extension SDK web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
autotag-review: '2026-05-19T08:18:58.656Z'
TQID: 'https://experienceleague.adobe.com/8Wld534ijt7cmJnlbq4cB7tURTb8hch99Z6FIrhzAcQ'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 100%

---

# Ajouter l’extension SDK web à votre balise {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Ajouter l’extension SDK web Adobe Experience Platform à votre propriété de balise"
>abstract="Ajoutez l’extension SDK web Adobe Experience Platform à votre propriété de balise. L’ajout de l’extension SDK web à votre propriété de balise est simplifié et ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Utilisez la fonction Balises d’Adobe Experience Platform pour implémenter du code sur le site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

Les informations suivantes décrivent comment ajouter l’extension SDK web à votre balise. Pour plus d’informations, consultez [Configuration de l’extension de balise SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) de la documentation d’Experience Platform. Le SDK web inclut le [!UICONTROL service Adobe Experience Cloud ID] de manière native, de sorte que vous n’avez pas besoin d’ajouter l’extension du service d’ID à votre balise.

Après avoir [créé une balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), vous devez la configurer avec l’extension SDK web Adobe Experience Platform. Vous pouvez ainsi envoyer des données à Adobe Experience Platform (par le biais de votre train de données).

Pour ajouter l’extension SDK web à votre balise, procédez comme suit :

1. Connectez-vous à experiencecloud.adobe.com à l’aide de vos identifiants Adobe ID.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.

1. Sélectionnez la balise que vous venez de créer dans la liste de [!UICONTROL Propriétés de balise] pour l’ouvrir.

1. Sélectionnez **[!UICONTROL Extensions]** dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Catalogue]** dans la barre supérieure.

1. Recherchez ou accédez à l’**[!UICONTROL extension SDK web Adobe Experience Platform]**, puis sélectionnez **[!UICONTROL Installer]** pour l’installer.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Sélectionnez la sandbox et le flux de données créé précédemment pour l’[!UICONTROL Environnement de production], (facultatif) l’[!UICONTROL Environnement d’évaluation] et l’[!UICONTROL Environnement de développement].

   ![Configuration de l’extension du SDK Web AEP](assets/aepwebsk-extension-datastreams.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

{{upgrade-final-step}}
