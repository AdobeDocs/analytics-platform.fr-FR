---
title: Créer une propriété de balise et ajouter l’extension SDK web
description: Découvrir comment créer une propriété de balise et ajouter l’extension SDK web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 100%

---

# Créer une balise pour votre propriété {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Créer une propriété de balise dans la collecte de données Adobe Experience Platform"
>abstract="L’utilisation de balises est la norme type pour la collecte de données. Créez une balise dans l’interface d’Adobe Experience Platform afin de pouvoir mettre à jour les variables de collecte de données à tout moment.<br><br>La création d’une propriété de balise peut être effectuée en plusieurs clics et en quelques minutes seulement."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Utilisez la fonction Balises d’Adobe Experience Platform pour implémenter du code sur le site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

Les informations suivantes décrivent comment créer une balise pour votre propriété. Pour plus d’informations, consultez [Configuration de l’extension de balise SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) de la documentation d’Experience Platform. Le SDK web inclut le [!UICONTROL service Adobe Experience Cloud ID] de manière native, de sorte que vous n’avez pas besoin d’ajouter l’extension du service d’ID à votre balise.

Une propriété est essentiellement un conteneur que vous remplissez avec des extensions, des règles, des éléments de données et des bibliothèques lorsque vous déployez des balises sur votre site. De nombreuses personnes créent une propriété pour chaque site web (ou groupe de sites étroitement liés) où elles souhaitent déployer le même ensemble de balises. Pour plus d’informations sur les propriétés, consultez [Propriétés](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/admin/companies-and-properties) dans la documentation sur la collecte de données Experience Platform.

Pour créer une balise pour votre propriété, procédez comme suit :

1. Connectez-vous à experiencecloud.adobe.com à l’aide de vos identifiants Adobe ID.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.

1. Sélectionnez **[!UICONTROL Nouvelle propriété]**.

   Nommez la balise, sélectionnez **[!UICONTROL Web]** et saisissez un nom de domaine. Sélectionnez **[!UICONTROL Enregistrer]** pour continuer.

   ![Créer une propriété](assets/create-property.png)

{{upgrade-final-step}}
