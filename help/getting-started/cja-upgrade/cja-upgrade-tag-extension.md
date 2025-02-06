---
title: Création d’une propriété de balise et ajout de l’extension Web SDK
description: Découvrez comment créer une propriété de balise et ajouter l’extension Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 23%

---

# Ajouter l’extension SDK Web à votre balise {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Ajoutez l’extension SDK Web Platform à votre propriété de balise"
>abstract="Ajoutez l’extension Adobe Experience Platform Web SDK à votre propriété de balise. L’ajout de l’extension Web SDK à votre propriété de balise est simplifié et ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Vous pouvez utiliser la fonction Balises de Adobe Experience Platform pour implémenter du code sur votre site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

Les informations suivantes décrivent comment ajouter l’extension Web SDK à votre balise. Pour plus d’informations, consultez la [Configuration de l’extension de balise Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) de la documentation de l’Experience Platform. Le SDK Web inclut le service d’ID [!UICONTROL Adobe Experience Cloud] de manière native, de sorte que vous n’avez pas besoin d’ajouter l’extension du service d’ID à votre balise.

Après avoir [créé une balise](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), vous devez la configurer avec l’extension Adobe Experience Platform Web SDK. Vous pouvez ainsi envoyer des données à Adobe Experience Platform (par le biais de votre flux de données).

Pour ajouter l’extension Web SDK à la balise :

1. Connectez-vous à experience.adobe.com à l’aide de vos informations d’identification Adobe ID.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.

1. Sélectionnez la balise que vous venez de créer dans la liste de [!UICONTROL Propriétés de balise] pour l’ouvrir.

1. Sélectionnez **[!UICONTROL Extensions]** dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Catalogue]** dans la barre supérieure.

1. Recherchez ou accédez à l’extension Adobe Experience Platform Web SDK ****, puis sélectionnez **[!UICONTROL Installer]** pour l’installer.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Sélectionnez la sandbox et le flux de données créé précédemment pour l’[!UICONTROL Environnement de production], (facultatif) l’[!UICONTROL Environnement d’évaluation] et l’[!UICONTROL Environnement de développement].

   ![Configuration de l’extension du SDK Web AEP](assets/aepwebsk-extension-datastreams.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
