---
title: Absence d’autorisations
description: Découvrez comment résoudre les problèmes liés à l’absence d’autorisations.
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
    internal-label: Access control
  - id: cbc7b6aa-4963-4ebf-9bb9-963336957623
    internal-label: Troubleshooting
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 94%
---
# Absence d’autorisations

Customer Journey Analytics ne fonctionne pas correctement lorsque certaines autorisations Adobe Experience Platform ne sont pas en place.

Par exemple, après avoir créé une [Connexion](../connections/overview.md) et une [Vue des données](../data-views/data-views.md), le message d’erreur suivant peut s’afficher dans la section [Composants](/help/data-views/create-dataview.md#components) :


>[!BEGINSHADEBOX]

*[!UICONTROL Un problème est survenu lors de la récupération des politiques DULE. Vérifiez les autorisations, les politiques ou les libellés du compte. Message : interdit.]*

>[!ENDSHADEBOX]


1. Vérifiez que vous disposez du contrôle d’accès approprié :

   * Vous devez disposer de privilèges d’administration système ou de produit pour une organisation ayant un produit Experience Platform. Pour plus d’informations, consultez la [vue d’ensemble du contrôle d’accès](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home#platform-permissions).

   * Vous devez être un utilisateur ou une utilisatrice du profil de produit AEP-Default-All-Users. Demandez à votre équipe d’administration si vous ne disposez pas des autorisations nécessaires pour vous ajouter à ce profil. Voir [Hiérarchie et workflow du contrôle d’accès](https://experienceleague.adobe.com/fr/docs/experience-platform/access-control/home#access-control-hierarchy-and-workflow) pour plus d’informations.


1. Accédez à l’interface d’utilisation d’Adobe Experience Platform.

1. Sélectionnez **[!UICONTROL Autorisations]** dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Rôles]**.

1. Accédez au rôle approprié.

1. Sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifier]** pour modifier le rôle.

1. Assurez-vous que les options **[!UICONTROL Gérer des politiques d’utilisation des données]** et **[!UICONTROL Afficher des politiques d’utilisation des données]** sont ajoutées au conteneur **[!UICONTROL Gouvernance des données]**.

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les modifications.
