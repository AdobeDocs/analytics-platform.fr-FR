---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b2a6225d6f94b158e217df4963611cb6d55580e
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 80%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (CJA) (juillet 2022)

**Dernière mise à jour** : 28 juillet 2022.

## Principales fonctionnalités

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Prise en charge des champs numériques comme clés et valeurs de recherche | Utile pour classer les valeurs de chaîne avec un champ numérique comme un COGS ou une marge sur un SKU de produit. L’autorisation d’utiliser les mesures issues de recherches vous permet d’intégrer ces points de données aux rapports. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#numeric) | 20 juillet 2022 |
| Création de rapports sur les nouvelles sessions et les sessions répétées | Vous pouvez désormais déterminer si une session particulière a été la toute première session d’un utilisateur. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=fr#new-repeat) | 17 août 2022 |
| Panneau d’observateurs simultanés de médias | Déterminez où s’est produit le pic d’accès simultanés et où des abandons ont eu lieu. Obtenez des informations importantes sur la qualité du contenu et l’engagement des observateurs, ainsi que de l’aide concernant la résolution de problèmes ou la planification du volume et de l’échelle. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 31 août 2022 |
| Panneau Durée de lecture des médias | La durée de lecture du média offre des informations précieuses sur l’engagement des visiteurs et permet aux entreprises multimédias d’obtenir des informations plus détaillées et plus granulaires avec un engagement minute par minute de l’utilisateur grâce à une analyse avancée de la durée de la visite avec des fonctionnalités de partage de journée. Vous pouvez observer la durée de visionnage de vos flux multimédias à un moment précis. Vous pouvez diviser la durée de lecture selon différentes granularités, notamment les nouvelles granularités de 5 minutes, 15 minutes et 30 minutes.  [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 31 août 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs

AN-288455 ; AN-288828 ; AN-289323

## Avis importants destinés aux administrateurs de CJA

| Avis | Avis ajouté ou mis à jour | Description |
| --- | --- | --- |
| **Amélioration du mappage IP/géolocalisation** | 11 juillet 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics adoptera ce nouveau jeu de données dans la variable **Octobre 2022**, délai. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du connecteur source Analytics tirent également automatiquement parti des nouveaux mappages. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
