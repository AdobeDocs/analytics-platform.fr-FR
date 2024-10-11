---
title: Transfert de ressources
description: Découvrez comment transférer des composants d’un utilisateur à un autre
hide: true
hidefromtoc: true
source-git-commit: 1a0422144b795be7f129b13208e93f8d3645a8e7
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---


# Transfert de ressources

L’outil de transfert de ressources vous permet de transférer la propriété des ressources à d’autres utilisateurs. Assets peut inclure des composants tels que des projets, des filtres, des périodes, des mesures calculées, des annotations, des alertes et des projets planifiés.

Assets est souvent lié à un propriétaire individuel et, dans certains cas, comme les filtres et les mesures calculées, ne peuvent pas être modifiés ni partagés, même par les administrateurs. Lorsque les utilisateurs quittent l’organisation ou que leur rôle change, il peut s’avérer nécessaire de transférer la propriété de ces ressources à d’autres utilisateurs afin d’assurer la continuité et un accès approprié.

## Autorisations

Le transfert de ressources nécessite des autorisations d’administrateur de produit pour Customer Journey Analytics.

## Transfert de ressources

1. Dans CJA, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Transfert de ressources]**.

   ![Élément de menu Transfert de ressources](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Dans la boîte de dialogue **[!UICONTROL Users]**, recherchez et sélectionnez l’utilisateur à partir duquel vous souhaitez transférer des ressources.

   >[!IMPORTANT]
   >
   >Vous pouvez uniquement effectuer un transfert 1:1 d’un utilisateur à un autre. Les transferts de type &quot;un à plusieurs&quot; ou &quot;plusieurs à un&quot; ne sont pas pris en charge.


1. Une fois que vous avez sélectionné un utilisateur, l’option Transférer les ressources s’affiche en bas de l’écran.

   ![option de menu](/help/tools/asset-transfer/assets/after-selection.png)

1. Cliquez sur **[!UICONTROL Transférer les ressources]**.

1. Sur l’écran **[!UICONTROL Transférer les ressources]**, sélectionnez tout d’abord le destinataire auquel vous souhaitez transférer des ressources.

1. Examinez maintenant chaque dossier de composants dans le volet de navigation de gauche pour sélectionner des composants individuels ou toutes les ressources d’un dossier à transférer.

   Notez que le transfert de ressources d’un administrateur vers un non-administrateur ne met pas à niveau le destinataire vers un administrateur.

1. Pour sélectionner _toutes les_ ressources dans un dossier, cochez la case en regard de **[!UICONTROL Nom]** en haut du tableau.

   ![sélectionner les ressources à transférer](/help/tools/asset-transfer/assets/select-assets.png)

1. Cliquez sur **[!UICONTROL Transférer]** en haut à droite après avoir effectué toutes vos sélections.

1. Cliquez sur **[!UICONTROL Confirmer]** lorsque le message de confirmation s’affiche.

   >[!IMPORTANT]
   >
   >Ne fermez pas l&#39;écran lors du transfert pour éviter l&#39;avortement du processus. Cela garantit une expérience de transfert fluide.

## Transfert de ressources lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics

L’un des principaux cas d’utilisation pour le transfert de ressources se produit lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

La fonction [Migration des composants](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) d’Adobe Analytics vous permet de migrer les projets détenus par l’administrateur vers d’autres administrateurs. Tous les composants qui composent ces projets sont ensuite recréés dans Customer Journey Analytics et l’administrateur du destinataire possède tous ces composants, quel que soit le propriétaire de ces composants.

Cet outil de transfert de ressources permet par la suite aux administrateurs de réaffecter des composants à leurs propriétaires légitimes.

## Exporter dans un fichier CSV

Vous pouvez exporter une liste des ressources transférées d’un utilisateur à un autre vers un fichier .csv.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->