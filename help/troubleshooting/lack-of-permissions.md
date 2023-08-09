---
title: Absence d’autorisations
description: Découvrez comment résoudre les problèmes liés à l’absence d’autorisations
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 1905e37b76843a7622af4e874a2d74aceff55384
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# Absence d’autorisations

Le Customer Journey Analytics ne fonctionne pas correctement lorsque certaines autorisations Adobe Experience Platform ne sont pas en place.

Par exemple, après avoir créé une [Connexion](../connections/overview.md) et [Vue des données](../data-views/data-views.md), le message d’erreur suivant peut s’afficher dans la variable [Composants](/help/data-views/create-dataview.md#components) section :


>[!BEGINSHADEBOX]

*[!UICONTROL Une erreur s’est produite et nous n’avons pas pu charger les champs de schéma. Veuillez réessayer.]*

>[!ENDSHADEBOX]


Pour corriger cette erreur, vous devez disposer de droits d’administrateur système ou produit pour une organisation disposant d’un produit Experience Platform. Voir [Présentation du contrôle d’accès](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) pour plus d’informations.

1. Accédez à l’interface utilisateur d’Adobe Experience Platform.

1. Sélectionner **[!UICONTROL Autorisations]** dans le rail de gauche.

1. Sélectionner **[!UICONTROL Rôles]**.

1. Accédez au rôle approprié.

1. Sélectionner ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** pour modifier le rôle.

1. Assurez-vous que **[!UICONTROL Gestion des stratégies d’utilisation des données]** et **[!UICONTROL Affichage des stratégies d’utilisation des données]** sont ajoutés au **[!UICONTROL Gouvernance des données]** conteneur.

1. Sélectionner **[!UICONTROL Enregistrer]** pour enregistrer les modifications.


