---
title: En savoir plus sur la vue d’ensemble de la publication des audiences Customer Journey Analytics
description: En savoir plus sur le concept de publication d’audience dans Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 9a7ba4913a4724116455566ff783fb270f5e289c
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 79%

---

# Vue d’ensemble de la publication des audiences

>[!NOTE]
>
>Comprenez la différence entre l’analyse de l’audience et la publication d’audience :
>
>* **Analyse de l’audience** : vous permet d’ingérer des données d’appartenance à une audience à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics. Pour plus d’informations sur l’analyse de l’audience, voir [&#x200B; Présentation de l’analyse de l’audience](/help/connections/audience-analysis/audience-analysis-overview.md).
>* **Publication d’audiences** : permet de créer et de publier des audiences découvertes dans Customer Journey Analytics sur Adobe Experience Platform pour le ciblage et la personnalisation des clients.

Vous pouvez créer et publier des audiences découvertes dans Customer Journey Analytics dans le [profil client en temps réel](https://experienceleague.adobe.com/fr/docs/experience-platform/profile/home.html) dans Adobe Experience Platform pour le ciblage et la personnalisation des clients. (Pour plus d’informations sur l’ingestion de données d’appartenance à une audience à partir de jeux de données Profil Experience Platform dans une connexion Customer Journey Analytics, voir [Présentation de l’analyse de l’audience](/help/connections/audience-analysis/audience-analysis-overview.md).)

La publication d’audiences offre un moyen clair d’activer et d’agir sur les informations trouvées dans Customer Journey Analytics. Ces actions peuvent inclure les éléments suivants :

* Utilisation de l’audience pour un parcours dans Adobe Journey Optimizer.
Pour plus d’informations sur l’utilisation des audiences publiées sur Experience Platform, voir [Commencer avec les audiences](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences) dans la documentation de Journey Optimizer.
* Exportation de l’audience vers un tiers par le biais d’une destination Experience Platform.
* Enrichissement du profil client en temps réel avec des attributs utiles dérivés de données basées sur un événement dans Customer Journey Analytics.
* Tout cela avec une latence minimale après la publication de l’audience.
Pour plus d’informations, voir [Considérations relatives à la latence](/help/components/audiences/publish.md#latency-considerations) dans [Créer et publier des audiences](/help/components/audiences/publish.md).
* Publication d’audiences ponctuelles ou d’audiences récurrentes

Les audiences que vous créez dans Customer Journey Analytics ne doivent pas nécessairement être basées sur des jeux de données activés pour le profil. Vous pouvez ingérer des données historiques dans Experience Platform sans activer les jeux de données et les schémas associés pour le profil. Utilisez ensuite ces jeux de données pour découvrir les audiences appropriées dans Customer Journey Analytics et publier ces audiences dans le profil client en temps réel dans Experience Platform à des fins d’activation.

## Terminologie clé

**Audience** : un ensemble ou une liste d’identités ayant à la fois un espace de noms et un identifiant spécifique associé à cet espace de noms. Les audiences sont transportables à partir d’Adobe Experience Platform et des applications qui s’y trouvent (comme Customer Journey Analytics). Les audiences peuvent contenir des espaces de noms mixtes.

**Segment** : un ensemble de règles qui, lorsqu’elles sont évaluées sur un ensemble de données pour une période donnée, produit un sous-ensemble de données. Un segment peut être utilisé dans le processus de création d’une audience lorsqu’il est associé à d’autres services de support. Les segments sont définis et conservés dans Customer Journey Analytics.

## Autorisations

* Les administrateurs et administratrices se voient automatiquement attribuer l’autorisation **[!UICONTROL Publication d’audiences]** dans Adobe Admin Console.

* Les administrateurs et administratrices et les administrateurs et administratrices de profil de produit peuvent accorder les autorisations **[!UICONTROL Création d’audience]** et **[!UICONTROL Affichage d’audience]** à des utilisateurs et utilisatrices individuels. Pour plus d’informations, consultez [Contrôle d’accès au niveau de l’utilisateur ou de l’utilisatrice](/help/technotes/access-control.md#user-level-access).

* Les administrateurs et administratrices ont également besoin de l’autorisation **[!UICONTROL Gérer les profils]** dans Adobe Experience Platform.

## Gouvernance des données et consentement

Lorsque vous publiez une audience dans Customer Journey Analytics, les libellés et les politiques de gouvernance des données associés aux champs utilisés dans l’audience sont enregistrés.  Lorsque l’audience est activée dans une application Adobe Experience, toutes les étiquettes et politiques de gouvernance des données associées sont disponibles pour cette audience et une application appropriée peut être utilisée. [En savoir plus sur le consentement](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=fr#consent-policy).

## Étapes suivantes

* [Créer et publier des audiences](/help/components/audiences/publish.md)
* [Gérer des audiences](/help/components/audiences/manage.md)
