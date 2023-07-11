---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour du Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e9d2bfb4f4c4aa3ac96d0300e537376a1ef7821a
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 39%

---

# Notes de mise à jour actuelles d’Adobe Customer Journey Analytics (juillet 2023)

**Dernière mise à jour** : 10 juillet 2023

Les versions d’Adobe Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Un nouveau type de projet qui permet aux équipes produit de répondre rapidement à leurs besoins de données de manière autonome afin de pouvoir prendre plus de décisions basées sur les données. Il repose sur les workflows de connexion et de vue de données existants dans Customer Journey Analytics. Aucune modification de mise en oeuvre ou de configuration n’est nécessaire. [En savoir plus](/help/guided-analysis/overview.md)<p>Product Analytics est un module complémentaire payant pour Customer Journey Analytics. Si votre entreprise souhaite recevoir les privilèges d’accès pour utiliser cette fonctionnalité, contactez votre équipe de compte d’Adobe. | S.O. | 17 juillet 2023 |
| **Champs dérivés** | Il s’agit de la version initiale des champs dérivés. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. Vous pouvez définir plus précisément le champ dérivé en tant que composant (mesure ou dimension) dans les vues de données, puis utiliser le champ dérivé en tant que composant dans Workspace.<p>Cette version prend en charge un modèle de canaux marketing et les fonctions suivantes :</p><ul><li>Concaténer</li><li>Cas si</li><li>Chercher et remplacer</li><li>Recherche</li><li>Analyse de l’URL</li></ul> <p>[En savoir plus](/help/data-views/derived-fields/derived-fields.md)</p> | 10 mai 2023 | 2 août 2023 |
| **Prise en charge étendue de la recherche pour les données de profil et de recherche** | Permet d’ajouter des jeux de données en tant que recherches de champs dans les jeux de données Profile ou Lookup. Auparavant, seuls les jeux de données Event étaient pris en charge. [En savoir plus] | 21 juin 2023 | 12 juillet 2023 |
| **Améliorations apportées aux Reports Builder** | <ul><li>Filtrer à partir de la cellule pour plusieurs blocs de données. Vous pouvez modifier les filtres sur plusieurs blocs de données à partir d’une cellule. Utilisez une cellule prédéfinie, affectez-la à plusieurs blocs de données et mettez à jour les données en fonction des filtres définis dans la cellule. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Affichez et masquez les en-têtes de lignes et de colonnes. Vous pouvez afficher ou masquer les en-têtes de tableau de bloc de données ou les en-têtes de ligne et de colonne pour reformater le tableau et aligner les blocs de données dans un rapport. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | S.O. | 19 juillet 2023 |
| **Recherches géographiques Experience Edge** | Adobe Experience Edge ajoute un service de recherche géographique qui fournit des données géographiques unifiées à tous les utilisateurs d’Experience Edge (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Medium Analytics, Adobe Experience Platform, etc.). | S.O. | 26 juillet 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

## Avis importants à l’intention des administrateurs de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Modifications apportées à la manière dont Customer Journey Analytics traite les données** | 22 juin 2023 | Nous avons récemment modifié la manière dont nous traitons les données en Customer Journey Analytics.<ul><li>Toutes les données d’événement avec un horodatage datant de moins de 24 heures sont diffusées en continu.</li><li>Toutes les données d’événement dont l’horodatage remonte à plus de 24 heures (même si elles se trouvent dans le même lot que les données plus récentes) sont considérées comme un renvoi et seront ingérées avec une priorité inférieure.</li></ul> |

{style="table-layout:auto"}

## Avis de fin de vie

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe IO** | 11 mai 2023 | L’API Adobe Analytics, l’API Customer Journey Analytics et les clients Livestream qui utilisent les informations d’identification JWT d’Adobe IO doivent migrer vers les informations d’identification OAuth serveur à serveur d’Adobe IO par **1er janvier 2025**. Adobe IO n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Ressources connexes

* [Notes de mise à jour précédentes du Customer Journey Analytics pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
