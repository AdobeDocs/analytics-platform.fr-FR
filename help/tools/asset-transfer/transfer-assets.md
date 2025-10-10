---
title: Transférer les ressources
description: Découvrez comment transférer des composants d’une personne à l’autre.
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 98%

---

# Transférer les ressources

L’outil de transfert de ressources vous permet de transférer la propriété des ressources à d’autres utilisateurs et utilisatrices. Les ressources peuvent inclure des composants tels que des projets, des segments, des périodes, des mesures calculées, des annotations, des alertes et des projets planifiés.

Les ressources sont souvent liées à une personne propriétaire individuelle et, dans certains cas, comme les segments et les mesures calculées, ne peuvent pas être modifiées ni partagées, même par les administrateurs et administratrices. Lorsque les utilisateurs et utilisatrices quittent l’organisation ou que leur rôle change, il peut s’avérer nécessaire de transférer la propriété de ces ressources à d’autres utilisateurs et utilisatrices afin d’assurer la continuité et un accès approprié.

## Autorisations

Le transfert de ressources nécessite l’autorisation de l’administrateur ou l’administratrice de produit pour Customer Journey Analytics.

## Transférer les ressources

1. Dans CJA, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Transfert de ressources]**.

   ![Élément de menu Transfert de ressources](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Dans la boîte de dialogue **[!UICONTROL Utilisateurs et utilisatrices]**, recherchez et sélectionnez la personne à partir de laquelle vous souhaitez transférer des ressources.

   >[!IMPORTANT]
   >
   >Vous pouvez uniquement effectuer un transfert 1:1 d’un utilisateur à un autre. Les transferts d’une personne à plusieurs, et inversement, ne sont pas pris en charge.


1. Une fois que vous avez sélectionné un utilisateur ou une utilisatrice, l’option Transférer les ressources s’affiche en bas de l’écran.

   ![Option du menu Transférer les ressources](/help/tools/asset-transfer/assets/after-selection.png)

1. Cliquez sur **[!UICONTROL Transférer les ressources]**.

1. Sur l’écran **[!UICONTROL Transférer les ressources]**, sélectionnez d’abord la personne destinataire à laquelle vous souhaitez transférer des ressources.

1. Passez maintenant en revue chaque dossier de composant dans le volet de navigation de gauche pour sélectionner des composants individuels ou toutes les ressources d’un dossier à transférer.

   >[!NOTE]
   >
   >Le transfert de ressources d’une personne administratrice vers une personne non-administratrice ne fait pas passer la personne destinataire au statut de personne administratrice.


   >[!NOTE]
   >
   >    Lors du transfert de ressources qui font référence à d’autres composants (par exemple, des projets qui font référence à d’autres segments et mesures calculées), les composants qui ne sont pas détenus par la personne propriétaire actuelle du projet ne seront partagés qu’avec la personne destinataire. La propriété de tous les autres composants sera transférée à la personne destinataire.

1. Pour sélectionner _toutes_ les ressources d’un dossier, cochez la case en regard de **[!UICONTROL Nom]** dans la partie supérieure du tableau.

   ![sélectionner les ressources à transférer](/help/tools/asset-transfer/assets/select-assets.png)

1. Cliquez sur **[!UICONTROL Transférer]** en haut à droite après avoir effectué toutes vos sélections.

1. Cliquez sur **[!UICONTROL Confirmer]** lorsque le message de confirmation s’affiche.

   >[!IMPORTANT]
   >
   >Ne fermez pas l’écran pendant le transfert pour éviter l’interruption du processus.
   >Cela garantit une expérience de transfert fluide.

## Résultats du transfert

Un transfert peut avoir trois conséquences :

- **Transfert réussi** : « Ressources transférées. »

- **Réussite partielle** : « Certaines ressources ont été transférées. »

- **Échec du transfert** : « Échec du transfert des ressources. Réessayez. »

### Raisons potentielles de l’échec du transfert de ressources

- Services dépendants à l’origine des échecs : le transfert de ressources interagit avec un service différent pour chaque type de composant (par exemple, problèmes réseau, problèmes de service en aval), ce qui peut entraîner un échec partiel ou complet, ou des échecs intermittents.

- Composant manquant ou transféré par une autre personne administratrice : un composant a été supprimé par une autre personne ou transféré par une autre personne administratrice à quelqu’un d’autre, alors qu’une tâche de transfert de ressources était toujours en cours.

- Le corps POST de l’API ne se remplit pas correctement : un composant peut ne pas être envoyé dans le corps POST de l’API lorsque plusieurs types de composants sont sélectionnés.

- Utilisateur ou utilisatrice inexistant : l’utilisateur ou l’utilisatrice a été supprimé lors du transfert ou n’est pas valide pour une autre raison. Si l’utilisateur ou l’utilisatrice n’est pas valide avant le début du transfert, l’outil l’intercepte et ne traite pas le traitement. Si l’utilisateur ou l’utilisatrice a été supprimé en cours de transfert, cela peut entraîner des échecs partiels.

- Échec de connexion/réseau : la connexion s’interrompt au cours du transfert. Tous les lots de traitements de transfert déjà transmis au serveur principal sont toujours traités jusqu’à la fin, mais l’utilisateur ou l’utilisatrice ne voit pas le message de résultat du transfert avec un résumé de ce qui a réussi et de ce qui a échoué.

- Fermeture de l’onglet du navigateur en cours de transfert : pour les transferts très volumineux, si l’onglet du navigateur est fermé ou si vous quittez la page en cours de transfert, seules les requêtes réseau effectuées avant la fermeture de l’onglet ou le changement de page transféreront correctement les ressources. Si la personne revient sur la page, elle ne reçoit pas le message de statut de la réponse indiquant quelles ressources ont été transférées et lesquelles ne l’ont pas été.

## Transférer des ressources pendant la mise à niveau d’Adobe Analytics vers Customer Journey Analytics

L’un des principaux cas d’utilisation du transfert de ressources concerne la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

La fonctionnalité [Migration des composants &#x200B;](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/component-migration) d’Adobe Analytics vous permet de migrer les projets détenus appartenant à des administrateurs et administratrices vers d’autres administrateurs et administratrices. Tous les composants qui constituent ces projets sont ensuite recréés dans Customer Journey Analytics et l’administrateur ou l’administratrice destinataire possède tous ces composants, quelle que soit la personne qui les a créés.

Cet outil de transfert de ressources permet par la suite aux administrateurs et administratrices de réaffecter des composants à leurs propriétaires légitimes, qu’il s’agisse ou non d’administrateurs ou d’administratrices.

>[!IMPORTANT]
>
>Bien que vous puissiez transférer des composants à l’aide de cet outil, vous devez, en tant qu’administrateur ou administratrice, vous assurer que la personne destinataire a accès aux vues de données requises pour afficher ou utiliser ces composants. Vous pouvez afficher et attribuer des autorisations dans l’[Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html).

## Exporter dans un fichier CSV

L’option **[!UICONTROL Exporter au format CSV]** permet uniquement aux administrateurs et administratrices de télécharger une liste d’utilisateurs et d’utilisatrices affichée dans un fichier .csv. Elle ne leur permet pas d’exporter une liste des ressources transférées vers un fichier .csv.

## Utilisateurs et utilisatrices inactifs

Tous les utilisateurs et utilisatrices précédemment supprimés apparaissent sous une seule entrée « Utilisateurs et utilisatrices inactifs », ainsi que tous leurs composants orphelins. Ces composants peuvent être transférés à une nouvelle personne destinataire. Cette fonctionnalité sera disponible en janvier.

![Utilisateurs et utilisatrices inactifs apparaissant dans l’interface d’utilisation de transfert de ressources](assets/inactive-users.png)

