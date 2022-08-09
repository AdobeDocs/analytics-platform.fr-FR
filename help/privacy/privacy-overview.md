---
title: Customer Journey Analytics et gouvernance des données
description: Décrit le fonctionnement de la gouvernance des données en Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics et gouvernance des données

En règle générale, tous les paramètres liés à la gouvernance des données dans Customer Journey Analytics sont hérités de Adobe Experience Platform.

## Gouvernance des données

CJA prend en charge les étiquettes et les stratégies de gouvernance des données configurées dans Adobe Experience Platform. Pour plus d’informations, voir [Prise en charge de CJA pour la gouvernance des données Adobe Experience Platform](/help/data-views/data-governance.md).

## RGPD

Customer Journey Analytics ne souscrit pas directement au Service Central du Règlement Général sur la Protection des Données (RGPD) et hérite à la place de toutes les modifications apportées aux jeux de données dans Experience Platform. Nous dépendons de Platform Data Lake pour faire respecter les demandes de suppression liées au RGPD et nous informer lorsqu’elles ont été effectuées sur Pipeline. Nous écoutons Pipeline et synchronisons toutes les modifications apportées aux lots concernés dans Customer Journey Analytics pour les jeux de données d’événement. Les jeux de données de profil et de recherche affectés par les demandes de suppression liées au RGPD seront entièrement ré-ingérés après chaque demande de suppression. Nous pouvons garantir que les demandes de suppression seront exécutées dans les 7 jours suivant un événement de suppression dans Data Lake.

## CCPA

Le California Consumer Privacy Act (CCPA) protège la vie privée et les consommateurs pour les personnes résidant en Californie, aux États-Unis. Cette loi rentrera en vigueur le 1er janvier 2020.
Le CCPA offre aux Californiens de nouveaux droits sur leurs données personnelles, comme le droit d’y accéder et de les supprimer, mais aussi de savoir si leurs données sont vendues ou divulguées (et, le cas échéant, à qui) et de refuser la vente de leurs données.
Afin de préparer l’arrivée du CCPA, le Service Confidentialité recevra les demandes de refus de vente de données personnelles.
