---
title: Mettre en œuvre la balise de chargeur pour l’extension SDK Web
description: Découvrez comment implémenter la balise de chargement pour l’extension Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: cb6a439def7bf0fab1768fdd1c7d909b76b995d6
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 36%

---

# Mettre en œuvre la balise de chargeur pour l’extension SDK Web

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Vous devez installer la balise sur le site web dont vous souhaitez effectuer le suivi, ce qui implique de placer le code dans la balise d’en-tête du modèle du site web.

Le processus suivant décrit comment obtenir le code qui fait référence à votre balise. Pour plus d’informations, consultez les [guides d’implémentation pour les balises et le transfert d’événement](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) dans la documentation de l’Experience Platform.

Obtenir le code qui fait référence à la balise :

1. Connectez-vous à experience.adobe.com à l’aide de vos informations d’identification Adobe ID.

1. Dans Adobe Experience Platform, accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.

1. Sur la page **[!UICONTROL Propriétés de la balise]**, sélectionnez la balise que vous venez de créer dans la liste de propriétés pour l’ouvrir.

1. Sélectionnez **[!UICONTROL Environnements]** dans le rail de gauche.

1. Dans la liste des environnements, sélectionnez le bouton d’installation (boîte) approprié.

   Dans la boîte de dialogue [!UICONTROL Instructions d’installation Web], sélectionnez le bouton Copier en regard du code de script qui doit se présenter comme suit :

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Environnement](assets/environment.png)

1. Sélectionnez **[!UICONTROL Fermer]**.

   Au lieu du code de l’environnement de développement, vous auriez pu sélectionner un autre environnement (évaluation, production) en fonction du stade auquel vous vous trouvez dans le processus de déploiement du SDK Web Adobe Experience Platform.

   Consultez [Environnements](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=fr) pour plus d’informations.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
