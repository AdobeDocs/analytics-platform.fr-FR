---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 94b3e7417b82e9ae3ad080884d4c184bee412c2c
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 93%

---

# Notes de mise à jour de la version actuelle de Customer Journey Analytics (CJA) (juillet 2022)

**Dernière mise à jour**: 5 août 2022

## Principales fonctionnalités

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Prise en charge des champs numériques comme clés et valeurs de recherche | Utile pour classer les valeurs de chaîne avec un champ numérique comme un COGS ou une marge sur un SKU de produit. L’autorisation d’utiliser les mesures issues de recherches vous permet d’intégrer ces points de données aux rapports. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#numeric) | 20 juillet 2022 |
| **Publication d’audiences dans le profil client en temps réel** | Permet de publier les audiences découvertes dans CJA dans Adobe Experience Platform/Real-time Customer Profile pour le ciblage et la personnalisation des clients. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=fr) | 5 août 2022 |
| Panneau Observateurs simultanés de médias | Déterminez où s’est produit le pic d’accès simultanés et où des abandons ont eu lieu. Obtenez des informations importantes sur la qualité du contenu et l’engagement des observateurs, ainsi que de l’aide concernant la résolution de problèmes ou la planification du volume et de l’échelle. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=fr) | **9 août 2022** |
| Panneau Temps de lecture de média | Le panneau Temps de lecture de média fournit des informations importantes sur lʼengagement des observateurs. Il permet également aux organisations de médias dʼobtenir des informations plus approfondies et plus granulaires sur lʼinteraction client, minute par minute, grâce à une analyse avancée de la durée de la lecture et des fonctionnalités dʼanalyse par tranches horaires. Vous pouvez observer la durée de visionnage de vos flux multimédia à un moment précis. Vous pouvez diviser la durée de lecture selon différentes granularités, notamment les nouvelles granularités de 5 minutes, 15 minutes et 30 minutes.  [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=fr) | **9 août 2022** |
| Création de rapports sur les nouvelles sessions et les sessions répétées | Vous pouvez désormais déterminer si une session particulière a été la toute première session d’un utilisateur. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=fr#new-repeat) | 17 août 2022 |

{style=&quot;table-layout:auto&quot;}

## Correctifs

AN-288455 ; AN-288828 ; AN-289323

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Amélioration du mappage IP/géolocalisation** | 11 juillet 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics adoptera ce nouveau jeu de données durant le mois d’**octobre 2022**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du connecteur source Analytics tirent également automatiquement parti des nouveaux mappages. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
