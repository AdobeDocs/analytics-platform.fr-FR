---
title: Absence d’autorisations
description: Découvrez comment résoudre les problèmes liés à l’absence d’autorisations
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Absence d’autorisations

Le Customer Journey Analytics ne fonctionne pas correctement lorsque certaines autorisations Adobe Experience Platform ne sont pas en place.

Par exemple, après avoir créé une [Connexion](../connections/overview.md) et [Vue des données](../data-views/data-views.md), le message d’erreur suivant peut s’afficher dans la variable [Composants](/help/data-views/create-dataview.md#components) section :


>[!BEGINSHADEBOX]

*[!UICONTROL Une erreur s’est produite lors de la récupération des stratégies DULE. Vérifiez les autorisations, les stratégies ou les étiquettes du compte. Message : interdit.]*

>[!ENDSHADEBOX]


1. Vérifiez que vous disposez du contrôle d’accès approprié :

   * Vous devez disposer de droits d’administrateur système ou produit pour une organisation disposant d’un produit Experience Platform. Voir [Présentation du contrôle d’accès](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) pour plus d’informations.

   * Vous devez être un utilisateur du profil de produit AEP-Default-All-Users . Demandez à votre administrateur si vous ne disposez pas des autorisations nécessaires pour vous ajouter à ce profil. Voir [Hiérarchie du contrôle d’accès et workflow](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#access-control-hierarchy-and-workflow) pour plus d’informations.


1. Accédez à l’interface utilisateur d’Adobe Experience Platform.

1. Sélectionner **[!UICONTROL Autorisations]** dans le rail de gauche.

1. Sélectionner **[!UICONTROL Rôles]**.

1. Accédez au rôle approprié.

1. Sélectionner ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** pour modifier le rôle.

1. Assurez-vous que **[!UICONTROL Gestion des stratégies d’utilisation des données]** et **[!UICONTROL Affichage des stratégies d’utilisation des données]** sont ajoutés au **[!UICONTROL Gouvernance des données]** conteneur.

1. Sélectionner **[!UICONTROL Enregistrer]** pour enregistrer les modifications.
