---
title: Absence d’autorisations
description: Découvrez comment résoudre les problèmes liés à l’absence d’autorisations.
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# Absence d’autorisations

Customer Journey Analytics ne fonctionne pas correctement lorsque certaines autorisations Adobe Experience Platform ne sont pas en place.

Par exemple, après avoir créé une [Connexion](../connections/overview.md) et une [Vue des données](../data-views/data-views.md), le message d’erreur suivant peut s’afficher dans la section [Composants](/help/data-views/create-dataview.md#components) :


>[!BEGINSHADEBOX]

*[!UICONTROL Un problème s’est produit lors de la récupération des politiques DULE. Vérifiez les autorisations, les politiques et les libellés du compte. Message : interdit.]*

>[!ENDSHADEBOX]


1. Vérifiez que vous disposez du contrôle d’accès approprié :

   * Vous devez avoir des droits d’administration système ou produit pour une organisation disposant d’un produit Experience Platform. Pour plus d’informations, consultez la [vue d’ensemble du contrôle d’accès](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home#platform-permissions).

   * Vous devez être un utilisateur ou une utilisatrice du profil de produit AEP-Default-All-Users. Demandez à votre équipe d’administration si vous ne disposez pas des autorisations nécessaires pour vous ajouter à ce profil. Voir [Hiérarchie et workflow du contrôle d’accès](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home#access-control-hierarchy-and-workflow) pour plus d’informations.


1. Accédez à l’interface d’utilisation d’Adobe Experience Platform.

1. Sélectionnez **[!UICONTROL Autorisations]** dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Rôles]**.

1. Accédez au rôle approprié.

1. Sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** pour modifier le rôle.

1. Assurez-vous que les options **[!UICONTROL Gérer des politiques d’utilisation des données]** et **[!UICONTROL Afficher des politiques d’utilisation des données]** sont ajoutées au conteneur **[!UICONTROL Gouvernance des données]**.

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les modifications.
