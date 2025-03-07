---
title: Création d’une propriété de balise et ajout de l’extension Web SDK
description: Découvrez comment créer une propriété de balise et ajouter l’extension Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 45%

---

# Créer une balise pour votre propriété {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Créer une propriété de balise dans la collecte de données Adobe Experience Platform"
>abstract="L’utilisation de balises est la norme pour la collecte de données. Créez une balise dans l’interface d’Adobe Experience Platform afin de pouvoir mettre à jour les variables de collecte de données à tout moment.<br><br>La création d’une propriété de balise peut être effectuée en plusieurs clics et en quelques minutes seulement."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Vous pouvez utiliser la fonction Balises de Adobe Experience Platform pour implémenter du code sur votre site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

Les informations suivantes décrivent comment créer une balise pour votre propriété. Pour plus d’informations, consultez la [Configuration de l’extension de balise Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) de la documentation d’Experience Platform. Le SDK Web inclut le service d’ID [!UICONTROL Adobe Experience Cloud] de manière native, de sorte que vous n’avez pas besoin d’ajouter l’extension du service d’ID à votre balise.

Une propriété est essentiellement un conteneur que vous remplissez avec des extensions, des règles, des éléments de données et des bibliothèques lorsque vous déployez des balises sur votre site. De nombreuses personnes créent une propriété pour chaque site web (ou groupe de sites étroitement liés) où elles souhaitent déployer le même ensemble de balises. Pour plus d’informations sur les propriétés, voir [Propriétés](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) dans la documentation sur la collecte de données Experience Platform.

Pour créer une balise pour votre propriété :

1. Connectez-vous à experience.adobe.com à l’aide de vos informations d’identification Adobe ID.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.

1. Sélectionnez **[!UICONTROL Nouvelle propriété]**.

   Nommez la balise, sélectionnez **[!UICONTROL Web]** et saisissez un nom de domaine. Sélectionnez **[!UICONTROL Enregistrer]** pour continuer.

   ![Créer une propriété](assets/create-property.png)

{{upgrade-final-step}}
