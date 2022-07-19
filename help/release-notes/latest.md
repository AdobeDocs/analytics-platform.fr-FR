---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 11171eb6e079adbf41e0abc798a54a5749492eac
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 46%

---

# Notes de mise à jour du Customer Journey Analytics actuel (CJA) (juillet 2022)

**Dernière mise à jour**: 19 juillet 2022

>[!NOTE]
>
>Cette page contient des informations préliminaires. Elles peuvent être modifiées à tout moment.

## Principales fonctionnalités

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Prise en charge des champs numériques comme clés et valeurs de recherche | Utile pour classer les valeurs de chaîne avec un champ numérique comme un COGS ou une marge sur un SKU de produit. L’autorisation d’utiliser les mesures issues de recherches vous permet d’intégrer ces points de données aux rapports. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#numeric) | 20 juillet 2022 |
| Rapports Première session et Répétition de la session | Vous pouvez désormais déterminer si une session particulière a été la toute première session d’un utilisateur. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 17 août 2022 |

## Correctifs

AN-288455 ; AN-288828 ; AN-289323

## Avis importants à l’intention des administrateurs CJA

| Remarque | d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| Amélioration du mappage IP/géolocalisation | 11 juillet 2022 | Le fournisseur d’Adobe pour les recherches IP, Digital Element, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAsset Pulse) pour le mappage IP/géolocalisation. Adobe Analytics adoptera ce nouveau jeu de données dans le délai d’octobre 2022. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géo seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du connecteur source Analytics tirent également automatiquement parti des nouveaux mappages. |

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
