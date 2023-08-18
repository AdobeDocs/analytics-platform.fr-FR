---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 21bcc23b37372fc96347228b8b40fa970bb09bb5
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 75%

---

# Notes de mise à jour actuelles d’Adobe Customer Journey Analytics (août 2023)

**Dernière mise à jour** : 9 août 2023

Ces notes de mise à jour portent sur la période du 9 août au 13 septembre 2023. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Améliorations apportées à Report Builder** | <ul><li>Vous pouvez télécharger une tâche planifiée à partir de l’onglet Classeurs , la nommer, l’enregistrer et la partager. [En savoir plus](/help/report-builder/schedule-reportbuilder.md)</li><li>La date de début en tant que dimension permet de faire apparaître la date de début du bloc de données en tant que dimension dans la sortie du bloc de données. [En savoir plus](/help/report-builder/create-a-data-block.md) </li></ul> | S.O. | 17 août 2023 |
| **Conversion des devises** | Le Parcours client ajoute la possibilité de prendre en charge plusieurs devises. Vous pouvez convertir une devise dans une autre devise dans les paramètres des vues de données. [En savoir plus](/help/data-views/component-settings/format.md) | S.O. | 31 août 2023 |
| **Prise en charge des classifications A4T dans Analytics Source Connector.** | Nous ajoutons un ID de corrélation pour faciliter l’association des données de classification pour les activités Adobe Target et les événements d’expérience. | S.O. | 31 août 2023 |
| **Gestionnaire des activités de rapport** | Fournit aux administrateurs une visibilité détaillée de la consommation des rapports pour chaque connexion, ce qui permet aux administrateurs de diagnostiquer facilement les problèmes de capacité, puis de les résoudre pendant les heures de pointe de la création de rapports. | S.O. | 6 septembre 2023 |
| **Accès PowerBI et Tableau aux vues de données Customer Journey Analytics** | Le connecteur SQL Adobe Customer Journey Analytics offre l’accès SQL aux vues de données que vous avez définies dans Customer Journey Analytics. Les ingénieurs et analystes de données rompus à Power BI, Tableau ou d’autres outils de Business Intelligence peuvent désormais créer des rapports et des tableaux de bord qui reposent sur les mêmes vues de données que les utilisateurs et utilisatrices de Customer Journey Analytics utilisent pour leurs projets Analysis Workspace. [En savoir plus](/help/data-views/sql-connector.md) | S.O. | 13 septembre 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-309141 ; AN-319198 ; AN-324576 ; AN-324939 ; AN-325138 ; AN-325554

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Modifications apportées à la façon dont Customer Journey Analytics traite les données** | 22 juin 2023 | Nous avons récemment modifié la façon dont nous traitons les données dans Customer Journey Analytics.<ul><li>Toutes les données d’événement datant de moins de 24 heures sont diffusées en continu.</li><li>Toutes les données d’événement de plus de 24 heures (même si elles se trouvent dans le même lot que les données plus récentes) sont considérées comme un renvoi et seront ingérées avec une priorité inférieure.</li></ul> |

{style="table-layout:auto"}

## Avis de fin de vie

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les API Adobe Analytics et Customer Journey Analytics et les clients et clientes Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
