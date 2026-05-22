---
title: Notes de mise à jour préliminaires de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour préliminaires de Customer Journey Analytics
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 80%

---

# Notes de mise à jour préliminaires d’Adobe Customer Journey Analytics

>[!IMPORTANT]
>
>Ce document est conçu comme un **aperçu** des notes de mise à jour du mois en cours. Les éléments de version peuvent faire l’objet de modifications et peuvent être ajoutés ou supprimés dans la version finale.

Ces notes de mise à jour portent sur la période du 2 juin 2025 au 15 juillet 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités.

Reportez-vous à la documentation suivante pour les notes de mise à jour de Adobe Experience Platform et de ses autres applications :

* [Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/fr/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [Composition d’audiences fédérées](https://experienceleague.adobe.com/fr/docs/federated-audience-composition/using/release-notes?lang=en)
* [Collaboration Real-Time CDP](https://experienceleague.adobe.com/fr/docs/real-time-cdp-collaboration/using/latest?lang=en)

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Le panneau de gauche d’Analysis Workspace ne s’ouvre plus et se ferme lorsque la souris le survole.** | Le panneau de gauche d’Analysis Workspace permet d’ajouter des éléments tels que des composants, des panneaux et des visualisations à votre projet. L’option permettant d’ouvrir temporairement le panneau de gauche en pointant sur l’une des icônes tout à gauche n’est plus disponible. Il vous suffit désormais de cliquer sur l’une de ces icônes pour que le panneau reste ouvert, puis de cliquer sur la même icône pour le fermer. |  | 2 juin 2025 <p>(Version initialement prévue pour le 29 mai 2025)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition permet aux entreprises B2B d’aligner leurs équipes marketing, commerciale et produits en fournissant des informations de compte exploitables qui stimulent l’augmentation des revenus. Le compte étant placé au centre du modèle de données, toutes les analyses se concentrent sur le parcours de compte. L’ajout d’une nouvelle couche d’entités (comptes, opportunités et groupes d’achat) en plus des événements basés sur les personnes et le temps, crée une vue d’ensemble complète du cycle de vie du marketing et des revenus B2B. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 juin 2025 |
| **Prise en charge des destinations sécurisées dans Report Builder** | De nouvelles destinations d’export ont été ajoutées au module complémentaire Report Builder. Les destinations suivantes de stockage dans le cloud sont prises en charge : <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 18 juin 2025 |
| **Nouvelle expérience de prévisualisation** | Le panneau de prévisualisation, utilisé pour prévisualiser les segments, les mesures calculées, etc., utilise désormais une visualisation par barres horizontales au lieu d’une visualisation en anneau. |  | 18 juin 2025 |
| **Boîte de dialogue Modèle d’attribution modifié** | Vous pouvez désormais définir le conteneur et la période séparément dans la boîte de dialogue du modèle d’attribution. |  | 18 juin 2025 |
| **Carte de la connexion** | Une nouvelle [interface de mappage des connexions](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection#connection-map) est disponible pour afficher visuellement votre configuration de connexion. |  | 18 juin 2025 |
| **Ajouter et afficher des commentaires dans les projets Analysis Workspace** | Une nouvelle [fonctionnalité de commentaires](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) dans Analysis Workspace vous permet de partager des informations et de poser des questions dans le cadre d’un projet Analysis Workspace. Celle-ci peut optimiser les discussions sur les données, en maintenant les conversations dans le contexte spécifique des données concernées. Vous pouvez : <ul><li>Commenter tout projet Analysis Workspace auquel vous avez accès</li><li>Commenter un élément spécifique d’une visualisation ou écrire des commentaires généraux sur un projet</li><li>Mentionner d’autres utilisateurs et utilisatrices pour les informer de vos commentaires</li><li>Gérer des commentaires existants (modifier, épingler, résoudre, etc.)</li></ul>Les administrateurs et les administratrices Customer Journey Analytics peuvent [désactiver les commentaires au niveau de l’organisation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Les propriétaires de projet peuvent [désactiver les commentaires au niveau du projet](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | 25 juin 2025 <p>(Version initialement prévue pour le 29 mai 2025)</p> |
