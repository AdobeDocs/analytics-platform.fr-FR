---
title: Customer Journey Analytics et gouvernance des données
description: Décrit le fonctionnement de la gouvernance des données dans Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 56%

---

# Adobe Customer Journey Analytics et gouvernance des données

En règle générale, tous les paramètres liés à la gouvernance de données dans Customer Journey Analytics sont hérités d’Adobe Experience Platform.

## Gouvernance des données

Intégration entre Adobe Customer Journey Analytics et [Gouvernance des données Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=fr) permet l’étiquetage des données Customer Journey Analytics sensibles et l’application des politiques de confidentialité.

Les libellés et les politiques de confidentialité créés sur les jeux de données consommés par Experience Platform peuvent être affichés dans le workflow des vues de données Customer Journey Analytics. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles.

En outre, lorsque des données sont exportées à partir d’un Customer Journey Analytics (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des libellés sont ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des politiques pour restreindre l’utilisation. Par conséquent, vos utilisateurs Customer Journey Analytics peuvent utiliser les données avec plus de confiance, tout en sachant qu’elles sont conformes aux stratégies définies par les gestionnaires de données.

[En savoir plus](/help/data-views/data-governance.md)

## RGPD

Customer Journey Analytics ne souscrit pas directement au Service Central du Règlement Général sur la Protection des Données (RGPD) et hérite à la place de toutes les modifications apportées aux jeux de données dans Experience Platform. Customer Journey Analytics dépend de Platform Data Lake pour faire respecter les demandes de suppression en vertu du RGPD et informer Customer Journey Analytics une fois les demandes terminées. Toutes les modifications apportées aux lots affectés dans Customer Journey Analytics pour les jeux de données d’événement sont synchronisées avec les données Platform. Les jeux de données de profil et de recherche affectés par les demandes de suppression en vertu du RGPD sont entièrement réingérés après chaque demande de suppression. Les demandes de suppression sont généralement terminées dans les 7 jours suivant un événement de suppression dans le lac de données.

## CCPA

Le California Consumer Privacy Act (CCPA) protège la vie privée et les consommateurs pour les personnes résidant en Californie, aux États-Unis. Cette loi est entrée en vigueur le 1er janvier 2020.
Le CCPA offre aux Californiens de nouveaux droits sur leurs données personnelles, comme le droit d’y accéder et de les supprimer, mais aussi de savoir si leurs données sont vendues ou divulguées (et, le cas échéant, à qui) et de refuser la vente de leurs données.
Conformément au CCPA, le Service Confidentialité reçoit les demandes de refus de vente de données personnelles.
