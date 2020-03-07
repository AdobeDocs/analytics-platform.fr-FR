---
title: Présentation de la confidentialité d’Analytics de parcours du client
description: Décrit le fonctionnement des paramètres de confidentialité dans Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Présentation de la confidentialité d’Analytics de parcours du client

En règle générale, tous les paramètres liés à la confidentialité dans Customer Journey Analytics sont hérités d’Adobe Experience Platform.

## RGPD

Customer Journey Analytics ne s’abonne pas directement au service Central General Data Protection Regulation (GDPR) et hérite à la place de toutes les modifications apportées aux jeux de données dans Experience Platform. Nous dépendons de Platform Data Lake pour faire respecter les demandes de suppression du RMMD et nous informer lorsqu’elles ont été effectuées sur le pipeline. Nous écoutons Pipeline et synchronisons toutes les modifications apportées aux lots concernés dans les analyses de parcours des clients pour les jeux de données  des. Les  et les jeux de données de recherche affectés par les demandes de suppression de GDPR seront entièrement réassimilés après chaque demande de suppression. Nous pouvons garantir que les demandes de suppression sont exécutées dans les 7 jours suivant la  de suppression dans Data Lake.

## CCPA

Le California Consumer Privacy Act (CCPA) protège la vie privée et les consommateurs pour les personnes résidant en Californie, États-Unis. Ce document sera en vigueur à partir du 1er janvier 2020.
Le CCPA offre aux Californiens de nouveaux droits sur leurs données personnelles, comme le droit d’y accéder et de les supprimer, mais aussi de savoir si leurs données sont vendues ou divulguées (et, le cas échéant, à qui) et de refuser la vente de leurs données.
Afin de préparer l’arrivée du CCPA, le Privacy Service recevra les demandes de refus de vente de données personnelles.
