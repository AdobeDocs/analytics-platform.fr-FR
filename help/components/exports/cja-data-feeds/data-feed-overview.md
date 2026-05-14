---
description: Découvrez comment utiliser les flux de données pour extraire des données brutes de Customer Journey Analytics. Découvrez les conditions préalables requises afin d’utiliser les flux de données pour les étapes suivantes.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Flux de données Analytics - Vue d’ensemble
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 21%

---

# Présentation des flux de données

Les flux de données sont un moyen puissant d’extraire des données brutes de Customer Journey Analytics. Vous pouvez utiliser ces données brutes sur d’autres plateformes en dehors d’Adobe à la discrétion de votre entreprise. Les données sont diffusées sous la forme de lots horaires à la fin de chaque heure ou sous la forme de lots quotidiens à la fin de chaque jour.

## Conditions préalables

Assurez-vous de respecter toutes les exigences suivantes avant d’utiliser les flux de données :

* Une implémentation fonctionnelle avec des données ingérées dans Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Votre compte est un administrateur de produit Analytics ou votre compte appartient à un profil de produit ayant accès aux flux de données <!--???-->
* Un compartiment configuré sur {DNL Amazon S3}, {DNL Google Cloud Platform}, {DNL Azure RBAC} ou {DNL Azure SAS}

## Commencer

Pour commencer à utiliser les flux de données dans Customer Journey Analytics, commencez par comprendre en quoi les flux de données dans Customer Journey Analytics diffèrent des flux de données dans Adobe Analytics. Après avoir compris les différences, vous pouvez mapper les flux de données d’Adobe Analytics à Customer Journey Analytics, puis commencer à créer un flux de données.

1. [Comprenez les différences entre les flux de données dans Customer Journey Analytics et Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Mappez les colonnes de flux de données Adobe Analytics à Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Créer un flux de données](/help/components/exports/cja-data-feeds/create-feed.md).
