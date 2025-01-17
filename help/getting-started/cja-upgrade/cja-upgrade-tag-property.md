---
title: Création d’une propriété de balise et ajout de l’extension Web SDK
description: Découvrez comment créer une propriété de balise et ajouter l’extension Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: cb6a439def7bf0fab1768fdd1c7d909b76b995d6
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 24%

---

# Créer une balise pour votre propriété

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Vous pouvez utiliser la fonction Balises de Adobe Experience Platform pour implémenter du code sur votre site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

Les informations suivantes décrivent comment créer une balise pour votre propriété. Pour plus d’informations, consultez la [Configuration de l’extension de balise Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) de la documentation de l’Experience Platform. Le SDK Web inclut le service d’ID [!UICONTROL Adobe Experience Cloud] de manière native, de sorte que vous n’avez pas besoin d’ajouter l’extension du service d’ID à votre balise.

Une propriété est essentiellement un conteneur que vous remplissez avec des extensions, des règles, des éléments de données et des bibliothèques lorsque vous déployez des balises sur votre site. De nombreuses personnes créent une propriété pour chaque site web (ou groupe de sites étroitement liés) où elles souhaitent déployer le même ensemble de balises. Pour plus d’informations sur les propriétés, voir [Properties](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) dans la documentation sur la collecte de données Experience Platform.

Pour créer une balise pour votre propriété :

1. Connectez-vous à experience.adobe.com à l’aide de vos informations d’identification Adobe ID.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.

1. Sélectionnez **[!UICONTROL Nouvelle propriété]**.

   Nommez la balise, sélectionnez **[!UICONTROL Web]** et saisissez un nom de domaine. Sélectionnez **[!UICONTROL Enregistrer]** pour continuer.

   ![Créer une propriété](assets/create-property.png)

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
