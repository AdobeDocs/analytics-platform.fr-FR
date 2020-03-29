---
title: Présentation de la confidentialité de Customer Journey Analytics
description: Décrit le fonctionnement des paramètres de confidentialité dans Customer Journey Analytics.
translation-type: ht
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Présentation de la confidentialité de Customer Journey Analytics

En règle générale, tous les paramètres liés à la confidentialité dans Customer Journey Analytics sont hérités d’Adobe Experience Platform.

## RGPD

Customer Journey Analytics ne souscrit pas directement au Service Central du Règlement Général sur la Protection des Données (RGPD) et hérite à la place de toutes les modifications apportées aux jeux de données dans Experience Platform. Nous dépendons de Platform Data Lake pour faire respecter les demandes de suppression liées au RGPD et nous informer lorsqu’elles ont été effectuées sur Pipeline. Nous écoutons Pipeline et synchronisons toutes les modifications apportées aux lots concernés dans Customer Journey Analytics pour les jeux de données d’événement. Les jeux de données de profil et de recherche affectés par les demandes de suppression liées au RGPD seront entièrement ré-ingérés après chaque demande de suppression. Nous pouvons garantir que les demandes de suppression seront exécutées dans les 7 jours suivant un événement de suppression dans Data Lake.

## CCPA

Le California Consumer Privacy Act (CCPA) protège la vie privée et les consommateurs pour les personnes résidant en Californie, aux États-Unis. Cette loi rentrera en vigueur le 1er janvier 2020.
Le CCPA offre aux Californiens de nouveaux droits sur leurs données personnelles, comme le droit d’y accéder et de les supprimer, mais aussi de savoir si leurs données sont vendues ou divulguées (et, le cas échéant, à qui) et de refuser la vente de leurs données.
Afin de préparer l’arrivée du CCPA, le Service Confidentialité recevra les demandes de refus de vente de données personnelles.
