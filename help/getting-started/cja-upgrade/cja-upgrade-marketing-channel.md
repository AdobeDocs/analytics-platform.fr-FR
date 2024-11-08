---
title: Création d’un champ dérivé de canal marketing pour Customer Journey Analytics
description: Découvrez comment créer un champ dérivé de canal marketing pour Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1e4c14334da54a5a6e4a0f36b3538c6e4d1a0b6f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 5%

---

# Création d’un champ dérivé de canal marketing pour Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Lors de l’utilisation du connecteur source Analytics, les données des canaux marketing sont transmises dans Customer Journey Analytics par le biais de ce connecteur. Les règles de canal marketing sont toujours configurées dans la version standard d’Adobe Analytics et certaines règles ne sont pas prises en charge. Pour plus d’informations, voir [Utilisation des dimensions de canal marketing](/help/use-cases/aa-data/marketing-channels.md).

Pour utiliser les canaux marketing dans Customer Journey Analytics lors de l’utilisation du SDK Web Experience Platform, vous pouvez utiliser des champs dérivés dans une vue de données afin de recréer les mêmes canaux marketing et règles de traitement pour Customer Journey Analytics.

1. Dans Customer Journey Analytics, sélectionnez la vue de données dans laquelle vous souhaitez ajouter des canaux marketing.

1. Dans la vue de données, sélectionnez l’onglet **[!UICONTROL Composants]** .

1. Sélectionnez **[!UICONTROL Créer un champ dérivé]** dans le rail de gauche.

1. Dans la boîte de dialogue **[!UICONTROL Créer un champ dérivé]**, sélectionnez **[!UICONTROL Modèles de fonction]** dans le menu déroulant.

   ![ Créer des modèles de fonction de champ dérivé ](assets/derived-field-create.png)

1. Faites glisser le modèle **[!UICONTROL Canaux marketing]** sur la zone de travail vierge.

1. Personnalisez la logique pour chaque canal marketing afin de vous assurer qu’elle correspond à la logique que vous utilisez pour identifier chaque canal dans votre environnement Adobe Analytics.

   Vous pouvez modifier les noms des canaux de sortie ou ajouter une logique pour identifier d’autres canaux spécifiques à votre organisation.

1. Dans la colonne de droite, indiquez un nom et une description pour le canal marketing.

1. Sélectionnez **[!UICONTROL Enregistrer]**.

   Votre nouveau champ dérivé est ajouté au conteneur Champs dérivés > , dans le cadre des champs Schéma du rail gauche de votre vue de données.

