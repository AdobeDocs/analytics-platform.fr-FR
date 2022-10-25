---
title: Présentation de la publication des audiences CJA
description: En savoir plus sur le concept de publication d’audience dans Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: eba2eb71ca434e0306c018b80209caf52266ee15
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 86%

---

# Présentation de la publication des audiences CJA

Vous pouvez désormais créer et publier des audiences découvertes dans Customer Journey Analytics (CJA) dans le [profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr) (RTCP) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients.

La publication d’audiences offre un moyen clair d’activer et d’agir sur les insights trouvés dans CJA. Ces actions peuvent inclure les éléments suivants :

* Utilisation de l’audience pour un parcours dans Adobe Journey Optimizer.
* Exportation de l’audience vers un tiers par le biais d’une destination Experience Platform.
* Enrichissement du profil client en temps réel avec des attributs utiles dérivés de données basées sur un événement dans CJA.
* Réalisez tout cela avec une latence minimale après la publication de l’audience (quelques minutes).
* Publication d’audiences ponctuelles ou d’audiences récurrentes

## Terminologie clé

**Audience** : un ensemble ou une liste d’identités ayant à la fois un espace de noms et un identifiant spécifique associé à cet espace de noms. Les audiences sont transportables à partir d’Adobe Experience Platform et des applications qui s’y trouvent (comme CJA). Les audiences peuvent contenir des espaces de noms mixtes.

**Filtre** : un ensemble de règles qui, lorsqu’elles sont évaluées sur un jeu de données pour une période donnée, produit un sous-ensemble de données. Un filtre peut être utilisé dans le processus de création d’une audience lorsqu’il est associé à d’autres services de support. Les filtres sont définis et conservés dans CJA.

**Filtres** ou **Segments** : CJA n’utilise pas le concept de « segments » mais plutôt de « filtres ». Bien que chacun d’entre eux soit un ensemble de règles pouvant contenir une logique similaire, ils produisent des sorties différentes. Un filtre est utilisé pour réduire un jeu de données à des fins d’analyse. Un segment est utilisé pour produire une liste d’identités qui peuvent être utilisées pour l’activation. Les segments génèrent des audiences dans le profil client en temps réel, contrairement aux filtres (seuls). La publication d’audience CJA est le processus par lequel nous utilisons un filtre CJA pour créer une audience qui peut être consommée par le profil client en temps réel.

## Autorisations

* Les administrateurs se voient automatiquement attribuer l’autorisation **[!UICONTROL Publication d’audiences]** dans Adobe Admin Console.

* Les administrateurs peuvent accorder cette autorisation à des utilisateurs individuels.

* Les administrateurs ont également besoin de l’autorisation **[!UICONTROL Gérer les profils]** dans Adobe Experience Platform.

## Gouvernance et consentement des données

Lorsque vous publiez une audience dans CJA, les étiquettes et les stratégies de gouvernance des données associées aux champs utilisés dans l’audience sont enregistrées.  Lorsque l’audience est activée dans une application Adobe Experience, toutes les étiquettes et politiques de gouvernance des données associées sont disponibles pour cette audience et une application appropriée peut être appliquée. [En savoir plus sur le consentement](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=fr#consent-policy).

## Étapes suivantes

* [Créer et publier des audiences](/help/components/audiences/publish.md)
* [Gérer des audiences](/help/components/audiences/manage.md)
