---
title: Customer Journey Analytics et gouvernance des données
description: Décrit le fonctionnement de la gouvernance des données dans Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
hold: true
autotag-review: '2026-05-19T09:18:17.400Z'
TQID: 'https://experienceleague.adobe.com/oDdNRwjtEU2vmeDvQ3DcM8w6XKQTBoTaXAIhmgjSoBk'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 116c169326e98f4e3d649c2fe72dbff44eaa0225
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 88%

---

# Adobe Customer Journey Analytics et gouvernance des données

En règle générale, tous les paramètres liés à la gouvernance des données dans Customer Journey Analytics sont hérités d’Adobe Experience Platform.

## Gouvernance des données

L’intégration entre Adobe Customer Journey Analytics et la [gouvernance de données Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=fr) permet l’étiquetage des données Customer Journey Analytics sensibles et l’application des politiques de confidentialité.

Les libellés et les politiques de confidentialité créés sur les jeux de données consommés par Experience Platform peuvent être affichés dans le workflow des vues de données Customer Journey Analytics. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles.

En outre, lorsque des données sont exportées à partir de Customer Journey Analytics (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des libellés sont ajoutés afin d’informer les personnes qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des politiques pour restreindre l’utilisation. Par conséquent, vos utilisateurs et utilisatrices Customer Journey Analytics peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux politiques définies par les gestionnaires de données.

[En savoir plus](/help/data-views/data-governance.md)

## Rapports et filtrage de consentement

Customer Journey Analytics peut utiliser les données d’appartenance à la politique de consentement dans vos jeux de données de profil Experience Platform pour créer des rapports sur le consentement des visiteurs et, éventuellement, exclure les visiteurs non consentants avant que leurs données ne soient ingérées. Les rapports de consentement rendent les politiques de consentement disponibles en tant que composants dans Analysis Workspace et le filtrage du consentement exclut les visiteurs non consentants au moment de l’ingestion en fonction des actions marketing que vous configurez.

[En savoir plus](/help/connections/consent-reporting-filtering/consent-overview.md)

## Demandes d’accès à des informations personnelles

Adobe gère les demandes d’accès à des informations personnelles conformément aux lois locales et internationales applicables.

Customer Journey Analytics utilisant des données disponibles dans Adobe Experience Platform, Adobe offre la fonctionnalité [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour envoyer des demandes d’accès aux données et de suppression. Ces demandes s’appliquent aussi bien aux jeux de données originaux qu’aux jeux de données recomposés.

## RGPD

Customer Journey Analytics ne souscrit pas directement au Service Central du Règlement Général sur la Protection des Données (RGPD) et hérite à la place de toutes les modifications apportées aux jeux de données dans Experience Platform. Customer Journey Analytics dépend du lac de données de Platform pour appliquer les demandes de suppression liées au RGPD et informer Customer Journey Analytics lorsque les demandes sont terminées. Toutes les modifications apportées aux lots affectés dans Customer Journey Analytics pour les jeux de données d’événement sont synchronisées avec les données de Platform. Les jeux de données de profil et de recherche affectés par les demandes de suppression liées au RGPD sont entièrement ré-ingérés après chaque demande de suppression. Les demandes de suppression sont généralement terminées dans les 7 jours suivant un événement de suppression dans le lac de données.

## CCPA

Le California Consumer Privacy Act (CCPA) protège la vie privée et les consommateurs pour les personnes résidant en Californie aux États-Unis. Cette loi est entrée en vigueur le 1er janvier 2020.Le CCPA offre aux Californiens de nouveaux droits sur leurs données personnelles, comme le droit d’y accéder et de les supprimer, mais aussi de savoir si leurs données sont vendues ou divulguées (et, le cas échéant, à qui) et de refuser la vente de leurs données.Conformément au CCPA, le Service Confidentialité reçoit les demandes de refus de vente de données personnelles.

>[!MORELIKETHIS]
>
>* [Blog : comment maintenir une gouvernance efficace dans Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
