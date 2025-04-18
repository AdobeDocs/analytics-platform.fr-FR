---
title: Transfert de ressources
description: Découvrez comment transférer des composants d’un utilisateur à un autre
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# Transfert de ressources

L’outil de transfert de ressources vous permet de transférer la propriété des ressources à d’autres utilisateurs. Assets peut inclure des composants tels que des projets, des segments, des périodes, des mesures calculées, des annotations, des alertes et des projets planifiés.

Les Assets sont souvent liées à un propriétaire individuel et, dans certains cas, comme les segments et les mesures calculées, ne peuvent pas être modifiées ni partagées, même par les administrateurs et administratrices. Lorsque les utilisateurs quittent l’organisation ou que leur rôle change, il peut s’avérer nécessaire de transférer la propriété de ces ressources à d’autres utilisateurs afin d’assurer la continuité et un accès approprié.

## Autorisations

Le transfert de ressources nécessite l’autorisation d’administrateur de produit pour Customer Journey Analytics.

## Transfert de ressources

1. Dans CJA, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Transfert de ressources]**.

   ![Élément de menu Transfert de ressources](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Dans la boîte de dialogue **[!UICONTROL Utilisateurs]**, recherchez et sélectionnez l’utilisateur à partir duquel vous souhaitez transférer des ressources.

   >[!IMPORTANT]
   >
   >Vous pouvez uniquement effectuer un transfert 1:1 d’un utilisateur à un autre. Les transferts de type « un à plusieurs » ou « plusieurs à un » ne sont pas pris en charge.


1. Une fois que vous avez sélectionné un utilisateur, l’option Transférer les ressources s’affiche en bas de l’écran.

   ![option de menu ](/help/tools/asset-transfer/assets/after-selection.png)

1. Cliquez sur **[!UICONTROL Transférer les ressources]**.

1. Sur l’écran **[!UICONTROL Transfert de ressources]**, sélectionnez d’abord le destinataire auquel vous souhaitez transférer des ressources.

1. Passez maintenant en revue chaque dossier de composant dans le volet de navigation de gauche pour sélectionner des composants individuels ou toutes les ressources d’un dossier à transférer.

   >[!NOTE]
   >
   >Le transfert de ressources d’un administrateur vers un non-administrateur ne met pas à niveau le destinataire vers un administrateur.


   >[!NOTE]
   >
   >    Lors du transfert de ressources qui font référence à d’autres composants (par exemple, des projets qui font référence à d’autres segments et mesures calculées), les composants qui ne sont pas détenus par le propriétaire actuel du projet ne seront partagés qu’avec le destinataire. La propriété de tous les autres composants sera transférée au destinataire.

1. Pour sélectionner _toutes_ les ressources d’un dossier, cochez la case en regard de **[!UICONTROL Nom]** dans la partie supérieure du tableau.

   ![sélectionnez les ressources à transférer](/help/tools/asset-transfer/assets/select-assets.png)

1. Cliquez sur **[!UICONTROL Transférer]** en haut à droite après avoir effectué toutes vos sélections.

1. Cliquez sur **[!UICONTROL Confirmer]** lorsque le message de confirmation s’affiche.

   >[!IMPORTANT]
   >
   >Ne fermez pas l&#39;écran pendant le transfert pour éviter l&#39;interruption du processus. Cela garantit une expérience de transfert fluide.

## Résultats du transfert

Un transfert peut avoir trois conséquences :

- **Transfert réussi** : « Assets transféré avec succès. »

- **Succès partiel** : « Certaines ressources ont été transférées avec succès. »

- **Échec du transfert** : « Échec du transfert des ressources. Veuillez réessayer. »

## Transfert de ressources lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics

L’un des principaux cas d’utilisation du transfert de ressources concerne la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

La fonctionnalité [ Migration des composants ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) d’Adobe Analytics vous permet de migrer les projets détenus par l’administrateur vers d’autres administrateurs. Tous les composants qui constituent ces projets sont ensuite recréés dans Customer Journey Analytics et l’administrateur ou l’administratrice du destinataire possède tous ces composants, quelle que soit la personne qui les a créés.

Cet outil de transfert de ressources permet par la suite aux administrateurs de réaffecter des composants à leurs propriétaires légitimes, qu’ils soient administrateurs ou non.

>[!IMPORTANT]
>
>Bien que vous puissiez transférer des composants à l’aide de cet outil, vous devez, en tant qu’administrateur, vous assurer que le destinataire a accès aux vues de données requises pour afficher/utiliser ces composants. Vous pouvez afficher et attribuer des autorisations dans [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html).

## Exporter dans un fichier CSV

L’option **[!UICONTROL Exporter au format CSV]** permet uniquement aux administrateurs de télécharger une liste d’utilisateurs affichée dans un fichier .csv. Il ne leur permet pas d’exporter une liste des ressources transférées vers un fichier .csv.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->
