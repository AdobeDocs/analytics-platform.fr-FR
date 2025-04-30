---
title: Vue d’ensemble des connexions Customer Journey Analytics
description: Découvrez les connexions dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 10%

---

# Présentation des connexions

Les connexions permettent aux administrateurs et administratrices de produit Customer Journey Analytics d’établir des connexions avec différentes sources de données [!DNL  Experience Platform], telles que les jeux de données d’événement, de recherche, de profil et de résumé. Ces connexions permettent l’intégration des données d’une connexion à une vue de données dérivée. Les connexions sont la base de Customer Journey Analytics et sont créées à partir de jeux de données sources [!DNL Experience Platform].

>[!IMPORTANT]
>
>Vous pouvez combiner plusieurs jeux de données [!DNL Experience Platform] en une seule connexion.


## Workflow Connexions

![Workflow Connexions](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

À un niveau élevé, le workflow Connexions vous permet d’effectuer les opérations suivantes :

| Interface | Description |
|:---:|---|
| ➊ | [Gérez vos connexions et l’utilisation globale](manage-connections.md) de Customer Journey Analytics à partir du gestionnaire de connexions. |
| ➋ | [Inspectez les détails d’une connexion](manage-connections.md#connection-details) tels que les enregistrements de jeux de données ingérés, ignorés ou supprimés. |
| ➌ | [Créez ou modifiez la configuration d’une connexion](create-connection.md#create-or-edit-a-connection) comme une fenêtre de données dynamique, le sandbox à utiliser, les jeux de données qui font partie de la connexion, etc. |
| ➍ | [Ajouter des jeux de données à une connexion](create-connection.md#add-datasets). Votre connexion doit comporter au moins un événement ou un jeu de données de résumé, mais peut contenir divers jeux de données d’événement, de profil, de recherche et de résumé. |
| ➎ | [Configurez les paramètres](create-connection.md#dataset-settings) pour les jeux de données que vous ajoutez. Vous pouvez déterminer comment lier différents jeux de données en fonction d’un identifiant commun basé sur une personne ou un compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}. |
| ➏ | [Modifier les paramètres d’un jeu de données existant](create-connection.md#edit-a-dataset). Vous pouvez toujours revoir les paramètres du jeu de données ultérieurement. |



## Contrôle d’accès

L&#39;accès à la gestion des connexions doit être limité à un groupe de gestion principal. Les configurations de connexion ont des implications contractuelles concernant les attributions de volume pour les données importées dans Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Contrôle d’accès](/help/technotes/access-control.md).

