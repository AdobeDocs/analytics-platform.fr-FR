---
title: Présentation de la publication des audiences CJA
description: En savoir plus sur le concept de publication d’audience dans Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: cfc4824c214ba8b60877bebe10a697f706f9c2fb
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 8%

---

# Présentation de la publication d’audience CJA

>[!NOTE]
>
>Cette fonctionnalité se trouve actuellement dans [test limité](/help/release-notes/releases.md).

Vous pouvez désormais créer et publier des audiences découvertes dans Customer Journey Analytics (CJA) sur [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) (RTCP) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients. Real-time Customer Profile offre une vue d’ensemble de chaque client en combinant des données issues de plusieurs canaux, notamment en ligne, hors ligne, CRM et tiers. Le Profil vous permet de consolider vos données client en une vue unifiée offrant un compte horodaté et exploitable de chaque interaction client.

La publication d’audiences offre un moyen clair d’agir sur les informations trouvées dans CJA. Ces actions peuvent inclure :

* Envoi d&#39;emails à cette audience.
* Envoi de messages push à cette audience.
* Utilisation de l’audience pour un parcours dans Adobe Journey Optimizer.
* Exportation de l’audience vers un tiers par le biais d’une destination Experience Platform.
* Enrichissement du profil client en temps réel avec des attributs utiles dérivés de données basées sur un événement dans CJA, sans avoir à ajouter toutes les données d’événement à RTCP.

## Terminologie clé

**Audience**: Un ensemble ou une liste d’identités ayant à la fois un espace de noms et un identifiant spécifique associé à cet espace de noms. Les audiences sont transportables à partir de Adobe Experience Platform et des applications qui s’y trouvent (comme CJA). Les audiences peuvent contenir des espaces de noms mixtes.

**Filtrer**: Ensemble de règles qui, lorsqu’elles sont évaluées sur un ensemble de données pour une période donnée, produit un sous-ensemble de données. Un filtre peut être utilisé dans le processus de création d’une audience lorsqu’il est couplé à d’autres services de support. Les filtres sont définis et conservés dans CJA.

**Filtres** versus **Segments**: CJA n’utilise pas le concept de &quot;segments&quot;, mais plutôt &quot;filtres&quot;. Bien qu’il s’agisse d’un ensemble de règles pouvant contenir une logique similaire, elles produisent des sorties différentes. Un filtre est utilisé pour réduire un jeu de données à des fins d’analyse. Un segment est utilisé pour produire une liste d’identités qui peuvent être utilisées pour l’activation. Les segments génèrent des audiences dans Real-time Customer Profile, contrairement aux filtres (seuls). La publication d’audience CJA est le processus par lequel nous utilisons un filtre CJA pour créer une audience qui peut être consommée par Real-time Customer Profile.

## Autorisations

Les administrateurs se voient automatiquement attribuer la variable [!UICONTROL Publication d’audiences] autorisation dans Adobe Admin Console. Ils peuvent accorder cette autorisation à des utilisateurs individuels.

## Étapes suivantes

* [Création et publication d’audiences](/help/components/audiences/publish.md)
* [Gestion des audiences](/help/components/audiences/manage.md)
