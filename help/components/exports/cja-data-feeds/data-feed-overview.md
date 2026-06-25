---
description: Découvrez comment utiliser les flux de données pour extraire des données brutes de Customer Journey Analytics. Découvrez les conditions préalables requises afin d’utiliser les flux de données pour les étapes suivantes.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Flux de données Analytics - Vue d’ensemble
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 8c577ff8508f15944ced77aaf20b692c911fdd3e
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 21%

---

# Présentation des flux de données

Les flux de données sont un moyen puissant d’extraire des données brutes de Customer Journey Analytics. Vous pouvez utiliser ces données brutes sur d’autres plateformes en dehors d’Adobe à la discrétion de votre entreprise. Les données sont diffusées sous la forme de lots horaires à la fin de chaque heure ou sous la forme de lots quotidiens à la fin de chaque jour.

## Conditions préalables

Assurez-vous de respecter toutes les exigences suivantes avant d’utiliser les flux de données :

* Une implémentation fonctionnelle avec des données ingérées dans Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Votre compte est un administrateur de produit Analytics ou votre compte appartient à un profil de produit ayant accès aux flux de données <!--???-->
* Compartiment configuré sur [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] ou [!DNL Azure SAS]

## Commencer

Pour commencer à utiliser les flux de données dans Customer Journey Analytics, commencez par comprendre en quoi les flux de données dans Customer Journey Analytics diffèrent des flux de données dans Adobe Analytics. Après avoir compris les différences, vous pouvez mapper les flux de données d’Adobe Analytics à Customer Journey Analytics, puis commencer à créer un flux de données.

1. [Comprenez les différences entre les flux de données dans Customer Journey Analytics et Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Mappez les colonnes de flux de données Adobe Analytics à Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Créer un flux de données](/help/components/exports/cja-data-feeds/create-feed.md).
