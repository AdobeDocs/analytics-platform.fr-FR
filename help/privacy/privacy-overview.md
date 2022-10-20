---
title: Customer Journey Analytics et gouvernance des données
description: Décrit le fonctionnement de la gouvernance des données dans Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 5f69840fa19fbf7ba6ecac1cd198cfa4a7dd905d
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 89%

---

# Customer Journey Analytics et gouvernance des données

En règle générale, tous les paramètres liés à la gouvernance de données dans Customer Journey Analytics sont hérités d’Adobe Experience Platform.

## Gouvernance des données

L’intégration entre CJA et [la gouvernance de données Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=fr) permet l’étiquetage des données CJA sensibles et l’application des politiques de confidentialité.

Les étiquettes de confidentialité et les stratégies créées sur les jeux de données consommés par Experience Platform peuvent être affichées dans le workflow des vues de données CJA. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles.

En outre, lorsque des données sont exportées à partir de CJA (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des étiquettes sont ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des stratégies pour restreindre l’utilisation. Par conséquent, vos utilisateurs CJA peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux stratégies définies par les gestionnaires de données.

[En savoir plus](/help/data-views/data-governance.md)

## RGPD

Customer Journey Analytics ne souscrit pas directement au Service Central du Règlement Général sur la Protection des Données (RGPD) et hérite à la place de toutes les modifications apportées aux jeux de données dans Experience Platform. Nous dépendons de Platform Data Lake pour faire respecter les demandes de suppression en vertu du RGPD et nous informer lorsqu’elles ont été effectuées sur Pipeline. Nous écoutons Pipeline et synchronisons toutes les modifications apportées aux lots concernés dans Customer Journey Analytics pour les jeux de données d’événement. Les jeux de données de profil et de recherche affectés par les demandes de suppression liées au RGPD seront entièrement ré-ingérés après chaque demande de suppression. Nous pouvons garantir que les demandes de suppression seront exécutées dans les 7 jours suivant un événement de suppression dans Data Lake.

## CCPA

Le California Consumer Privacy Act (CCPA) protège la vie privée et les consommateurs pour les personnes résidant en Californie, aux États-Unis. Cette loi est entrée en vigueur le 1er janvier 2020.
Le CCPA offre aux Californiens de nouveaux droits sur leurs données personnelles, comme le droit d’y accéder et de les supprimer, mais aussi de savoir si leurs données sont vendues ou divulguées (et, le cas échéant, à qui) et de refuser la vente de leurs données.
Conformément à la CCPA, le Privacy Service prend en charge les demandes de refus de vente de données personnelles.
