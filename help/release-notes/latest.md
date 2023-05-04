---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7737a285c701946dcf92c2610c1918022e05de36
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 66%

---

# Notes de mise à jour du Customer Journey Analytics actuel (CJA) (avril 2023)

**Dernière mise à jour** : 12 avril 2023

Les mises à jour de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Début du déploiement](/help/release-notes/releases.md) | [Disponibilité générale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Filtrage des lignes/colonnes pour la diffusion en continu du connecteur source Analytics** | Le connecteur source Analytics dans Adobe Experience Platform permet désormais de filtrer les données Analytics utilisées pour renseigner les profils dans [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr). Le filtrage au niveau des lignes permet de réduire le nombre d’événements associés aux profils. Le filtrage au niveau des colonnes contribue à réduire la richesse des événements eux-mêmes, ce qui vous permet d’optimiser l’utilisation des droits sur les profils. Ce filtrage s’applique uniquement aux données envoyées à Real-Time Customer Profile et au [Service d’identités](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr). **Le filtrage n’a aucune incidence sur les données envoyées au lac de données en vue de leur utilisation dans des applications telles que Customer Journey Analytics**. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr#filtering-for-profile) | S.O. | 29 mars 2023 |
| **Dictionnaire de données dans Analysis Workspace** | Le dictionnaire de données permet aux utilisateurs et utilisatrices, et aux administrateurs et administratrices, de suivre et de mieux comprendre les composants (dimensions, mesures) dans leur environnement CJA. [En savoir plus](/help/components/data-dictionary/data-dictionary-overview.md) | 8 mars 2023 | 29 mars 2023 |
| **Partage de liens pour les projets (aucune connexion requise)** | <p>Vous pouvez désormais partager des liens en lecture seule vers les projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela inclut le partage avec des personnes en dehors de votre organisation ou au sein de votre organisation qui ne sont pas configurées pour CJA. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>Cette fonctionnalité est activée par défaut et peut être désactivée par l’administrateur système. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 mai 2023 | Juin 2023 |
| **Adobe Product Analytics - Accès bêta privé uniquement** | Le 21 mars 2023, Adobe a annoncé Adobe Product Analytics, une nouvelle façon d’interagir avec les données et les informations cross-canal dans Customer Journey Analytics. Grâce à ces nouvelles fonctionnalités, les équipes produit peuvent mettre en libre-service des données et des informations sur leur expérience de produit au moyen de &#x200B; de workflows d’analyse guidée. Les équipes peuvent :<ul><li>Comprendre les schémas de l’engagement des utilisateurs au fil du temps &#x200B;</li><li>Analyser la croissance de la &#x200B; de base des utilisateurs</li><li>Identifier les zones de friction à travers une séquence d’étapes&#x200B;</li><li>Mesurer l’impact des nouvelles fonctionnalités&#x200B;</li><li>Découvrez des segments significatifs à interagir et à cultiver tout au long de leur parcours de vie avec les &#x200B; de produits</li><li>Ouvrez dans Analysis Workspace pour une analyse et une collaboration plus approfondies avec les analystes, et bien plus encore ! &#x200B;</li></ul>Si vous êtes client CJA et souhaitez rejoindre la version bêta privée, veuillez contacter votre équipe de compte d’Adobe. [En savoir plus](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | S.O. | 17 juillet 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | S.O. | S.O. |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
