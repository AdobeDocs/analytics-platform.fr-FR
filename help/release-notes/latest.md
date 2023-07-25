---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e6b2df9ae90ef5663206e768b985749de38e263c
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 100%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (juillet 2023)

**Dernière mise à jour** : 25 juillet 2023

Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics est une nouvelle façon d’interagir avec les données et les informations cross-canal dans Customer Journey Analytics. Grâce à ces nouvelles fonctionnalités, les équipes produit peuvent mettre en libre-service des données et des informations sur leur expérience de produit au moyen de workflows d’analyse guidée. Les équipes peuvent :<ul><li>découvrir les tendances au fil du temps concernant l’interaction client ;</li><li>Suivez la croissance et la fidélisation de la base d’utilisateurs et d’utilisatrices du produit</li><li>Identifiez les zones de friction du produit</li><li>Mesurez l’impact des nouvelles fonctionnalités et de la première utilisation</li><li>Découvrir des segments d’utilisateurs et utilisatrices significatifs à impliquer et à entretenir tout au long de leur parcours avec le produit</li><li>Connectez Analysis Workspace pour une analyse plus approfondie et une collaboration plus étroite avec les analystes</li></ul>Adobe Product Analytics est un module complémentaire payant pour Customer Journey Analytics. Si votre entreprise souhaite être configurée pour utiliser cette fonctionnalité, contactez l’équipe en charge de votre compte Adobe. [En savoir plus](/help/guided-analysis/overview.md) | S.O. | 17 juillet 2023 |
| **Champs dérivés** | Il s’agit de la version initiale des champs dérivés. Un champ dérivé vous permet de définir à la volée des manipulations de données (souvent complexes) par le biais d’un créateur de règles personnalisable. Vous pouvez définir plus précisément le champ dérivé en tant que composant (mesure ou dimension) dans les vues de données, puis utiliser le champ dérivé en tant que composant dans Workspace.<p>Cette version prend en charge un modèle de canaux marketing et les fonctions suivantes :</p><ul><li>Concaténer</li><li>Cas si</li><li>Chercher et remplacer</li><li>Recherche</li><li>Analyse de l’URL</li></ul> <p>[En savoir plus](/help/data-views/derived-fields/derived-fields.md)</p> | 10 mai 2023 | 2 août 2023 |
| **Prise en charge étendue de la recherche de données de profil et de recherche** | Permet d’ajouter des jeux de données en tant que recherches de champs dans les jeux de données Profil ou Recherche. Auparavant, seuls les jeux de données Événement étaient pris en charge. [En savoir plus](/help/connections/create-connection.md) | 21 juin 2023 | 12 juillet 2023 |
| **Améliorations apportées à Report Builder** | <ul><li>Filtrez à partir de la cellule pour plusieurs blocs de données. Vous pouvez modifier les filtres sur plusieurs blocs de données à partir d’une cellule. Utilisez une cellule prédéfinie, affectez-la à plusieurs blocs de données et mettez à jour les données en fonction des filtres définis dans la cellule. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=fr)</li><li>Affichez et masquez les en-têtes de lignes et de colonnes. Vous pouvez afficher ou masquer les en-têtes de tableau de blocs de données ou les en-têtes de ligne et de colonne pour reformater le tableau et aligner les blocs de données dans un rapport. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=fr#build-the-data-block)</li></ul> | S.O. | 19 juillet 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-317971, AN-319234, AN-320439, AN-320519, AN-321740, AN-322444, AN-323116

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
