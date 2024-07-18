---
title: En savoir plus sur la publication Audiences du Customer Journey Analytics
description: En savoir plus sur le concept de publication d’audience dans Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 50%

---

# Présentation de la publication d’audiences Customer Journey Analytics

Vous pouvez désormais créer et publier des audiences découvertes en Customer Journey Analytics dans [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients.

La publication d’audiences offre un moyen clair d’activer et d’agir sur les informations trouvées dans Customer Journey Analytics. Ces actions peuvent inclure les éléments suivants :

* Utilisation de l’audience pour un parcours dans Adobe Journey Optimizer.
* Exportation de l’audience vers un tiers par le biais d’une destination Experience Platform.
* Enrichissement du profil client en temps réel avec des attributs utiles dérivés de données basées sur un événement dans Customer Journey Analytics.
* Tout cela avec une latence minimale après la publication de l’audience. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* Publier des audiences ponctuelles ou récurrentes.

Les audiences que vous créez dans Customer Journey Analytics ne doivent pas nécessairement être basées sur des jeux de données activés pour le profil. Vous pouvez ingérer des données historiques dans Experience Platform sans activer les jeux de données et les schémas associés pour le profil. Utilisez ensuite ces jeux de données pour découvrir les audiences pertinentes en Customer Journey Analytics et publiez ces audiences dans Real-time Customer Profile en Experience Platform à des fins d’activation.

## Terminologie clé

**Audience** : un ensemble ou une liste d’identités ayant à la fois un espace de noms et un identifiant spécifique associé à cet espace de noms. Les audiences sont transportables à partir de Adobe Experience Platform et des applications qui s’y trouvent (comme Customer Journey Analytics). Les audiences peuvent contenir des espaces de noms mixtes.

**Filtre** : un ensemble de règles qui, lorsqu’elles sont évaluées sur un jeu de données pour une période donnée, produit un sous-ensemble de données. Un filtre peut être utilisé dans le processus de création d’une audience lorsqu’il est associé à d’autres services de support. Les filtres sont définis et conservés dans Customer Journey Analytics.

**Filtres** par rapport à **Segments** : Customer Journey Analytics n’utilise pas le concept de &quot;segments&quot;, mais utilise &quot;filtres&quot;. Bien que chacun d’entre eux soit un ensemble de règles pouvant contenir une logique similaire, ils produisent des sorties différentes. Un filtre est utilisé pour réduire un jeu de données à des fins d’analyse. Un segment est utilisé pour produire une liste d’identités qui peuvent être utilisées pour l’activation. Les segments génèrent des audiences dans le profil client en temps réel, contrairement aux filtres (seuls). La publication d’audience de Customer Journey Analytics est le processus par lequel nous utilisons un filtre de Customer Journey Analytics pour créer une audience qui peut être utilisée par Real-time Customer Profile.

## Autorisations

* Les administrateurs se voient automatiquement attribuer l’autorisation **[!UICONTROL Publication d’audiences]** dans Adobe Admin Console.

* Les administrateurs peuvent accorder cette autorisation à des utilisateurs individuels.

* Les administrateurs ont également besoin de l’autorisation **[!UICONTROL Gérer les profils]** dans Adobe Experience Platform.

## Gouvernance des données et consentement

Lorsque vous publiez une audience dans Customer Journey Analytics, les étiquettes et les stratégies de gouvernance des données associées aux champs utilisés dans l’audience sont enregistrées.  Lorsque l’audience est activée dans une application Adobe Experience, toutes les étiquettes et politiques de gouvernance des données associées sont disponibles pour cette audience et une application appropriée peut être utilisée. [En savoir plus sur le consentement](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=fr#consent-policy).

## Étapes suivantes

* [Créer et publier des audiences](/help/components/audiences/publish.md)
* [Gérer des audiences](/help/components/audiences/manage.md)
