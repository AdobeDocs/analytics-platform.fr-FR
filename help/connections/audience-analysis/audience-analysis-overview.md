---
title: Présentation de l’analyse de l’audience
description: Découvrez comment analyser les audiences de RTCDP dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
source-git-commit: e59bb52d5e9d79ba72036d5a00ed8abc69dcf735
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 3%

---

# Présentation de l’analyse de l’audience

>[!NOTE]
>
>Comprenez la différence entre l’analyse de l’audience et la publication d’audience :
>
>* **Analyse de l’audience** : vous permet d’ingérer des données d’appartenance à une audience à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics.
>* **Publication d’audiences** : permet de créer et de publier des audiences découvertes dans Customer Journey Analytics sur Adobe Experience Platform pour le ciblage et la personnalisation des clients. Pour plus d’informations sur la publication d’audiences, voir [Présentation de la publication d’audiences](/help/components/audiences/audiences-overview.md).

L’analyse de l’audience vous permet d’ingérer des données d’appartenance à une audience à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics. Les audiences deviennent disponibles en tant que nouvelles dimensions à utiliser dans Analysis Workspace.

Le diagramme suivant et le tableau associé présentent une représentation de haut niveau de la manière dont une configuration d’analyse de l’audience dans Customer Journey Analytics rend les données d’audience Experience Platform disponibles dans Analysis Workspace :

![Présentation de l’analyse de l’audience](assets/audience-analysis-overview.png)

| Nombre | Fonctionnalité | Fonction |
|---------|----------|---------|
| 1 | Configuration de l’analyse de l’audience | Interface de configuration de Customer Journey Analytics utilisée pour configurer l’analyse de l’audience. |
| 2 | Sandbox | Doit contenir le jeu de données de profil que vous souhaitez ajouter à votre connexion. |
| 3 | Jeu de données de profil | Doit inclure les données d’audience Experience Platform que vous souhaitez analyser. Ce jeu de données de profil est ajouté à la connexion que vous sélectionnez. |
| 4 | Politique de fusion | Politique de fusion associée aux audiences Experience Platform que vous souhaitez analyser. |
| 5 | Données de profil | Données de profil associées à la politique de fusion que vous sélectionnez. Ces données sont disponibles dans les jeux de données Experience Platform. |
| 6 | Nouveau jeu de données de recherche | Fournit des noms conviviaux pour les nouvelles dimensions d’audience créées. <p>Le jeu de données de recherche est automatiquement créé et ajouté à la connexion, ainsi que le jeu de données de profil que vous sélectionnez.</p> |
| 7 | Connexion | La connexion à laquelle vous souhaitez ajouter le jeu de données de profil que vous sélectionnez. |
| 8 | Nouvelles dimensions d’audience | Nouvelles dimensions d’audience<!--and metrics?--> qui représentent les audiences Experience Platform incluses dans le jeu de données de profil que vous avez sélectionné et qui sont disponibles pour la création de rapports dans Analysis Workspace. Ces dimensions sont automatiquement créées. |
| 9 | Vues des données | Vues de données sélectionnées associées à votre connexion. Il s’agit des vues de données que vous souhaitez utiliser lors de l’analyse des données d’audience Experience Platform dans Analysis Workspace. Ces vues de données sont automatiquement configurées avec les données d’audience Experience Platform pour la création de rapports. |

## Configuration de l’analyse de l’audience

Lorsque vous configurez l’analyse de l’audience, vous sélectionnez le sandbox et la politique de fusion associés aux audiences Experience Platform que vous souhaitez analyser. Customer Journey Analytics crée un jeu de données de recherche, puis ajoute automatiquement le jeu de données de recherche et le jeu de données de profil à la connexion que vous choisissez.

>[!IMPORTANT]
>
>Les données d’audience sont retraitées et générées chaque nuit, ce qui rend les données d’audience exactes pour analyse uniquement pour la journée précédente (« hier »).
>
>Les audiences sont disponibles dans les vues de données Customer Journey Analytics le lendemain de la création de la configuration de l’analyse de l’audience.

Pour plus d’informations, voir [Configuration de l’analyse de l’audience](/help/connections/audience-analysis/audience-analysis-configure.md).

## Gestion des configurations d’analyse d’audience

Vous pouvez gérer les configurations d’analyse des audiences après leur création. Vous pouvez afficher, modifier et supprimer des configurations.

Pour plus d’informations sur la gestion des configurations d’analyse d’audience existantes, voir [Gérer les configurations d’analyse d’audience](/help/connections/audience-analysis/audience-analysis-manage.md).

## Analyse des données d’audience dans Customer Journey Analytics

Grâce aux données d’audience disponibles dans Customer Journey Analytics, vous pouvez obtenir des informations exploitables sur le comportement des membres de l’audience sur divers canaux.

Vous pouvez, par exemple, suivre le comportement de clients individuels qui ont été inclus dans la même promotion par e-mail. Avec l’audience disponible dans Customer Journey Analytics, vous pouvez voir les types d’informations suivants sur chaque membre de l’audience :

* Clics publicitaires de l’e-mail au site qui ont finalement abouti à un achat

* Membres de l’audience qui ont finalement effectué un achat en magasin

Pour plus d’informations, voir [Analyse des audiences Experience Platform dans Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

## Rôle d’analyse d’audience et exigences d’autorisation

Les rôles Customer Journey Analytics suivants et les autorisations Experience Platform sont requis pour l’analyse de l’audience :

| Fonctionnalité | Exigences de rôle ou d’autorisation pour Customer Journey Analytics | Exigences d’autorisation pour Experience Platform |
|---------|----------|----------|
| [Créer des configurations d’analyse d’audience](/help/connections/audience-analysis/audience-analysis-configure.md) | Administrateur système | <ul><li>Jeux de données : autorisations de lecture</li><li>Schémas : lecture, écriture</li><li>Espaces de noms d’identité : lecture</li></ul> |
| [Affichage des dimensions d’analyse d’audience dans la vue de données](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | Administrateur de profil de produit pour le profil de produit auquel la vue de données est affectée <p>Pour plus d’informations, voir [Contrôle d’accès](/help/technotes/access-control.md).</p> | S.O. |
| Utilisation des dimensions d’analyse d’audience dans Analysis Workspace | Accès à une vue de données dans laquelle les dimensions d’analyse d’audience ont été ajoutées | S.O. |

## Limites de l’analyse de l’audience

Tenez compte des limites suivantes lors de la [configuration de l’analyse de l’audience](/help/connections/audience-analysis/audience-analysis-configure.md) :

* Un seul sandbox peut prendre en charge jusqu’à 100 configurations d’analyse d’audience.

* Une connexion ne peut être associée qu’à une seule configuration d’analyse d’audience.








