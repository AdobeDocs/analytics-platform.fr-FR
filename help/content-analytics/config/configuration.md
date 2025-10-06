---
title: Configurer Content Analytics
description: Vue d’ensemble de la manière de configurer Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: f149a2bd7f184f4e8f6e67979649e2d9f609d603
workflow-type: ht
source-wordcount: '599'
ht-degree: 100%

---

# Configurer Content Analytics

Cet article explique, à un niveau général, comment configurer Content Analytics.

Avant de configurer Content Analytics, vous devez vous assurer que les [conditions préalables](#prerequisites) sont remplies, que vous disposez du [contrôle d’accès](#access-control) requis et que vous connaissez les [limites](#limitations).


Étapes générales

![Configuration de Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Utilisez l’assistant Content Analytics de [configuration guidée](guided.md) pour une aide tout au long des étapes requises pour mettre en place les conditions préalables pour une configuration de Content Analytics. Vous pouvez enregistrer vos configurations à tout moment et y revenir ultérieurement.
1. Une fois que les valeurs de configuration vous satisfont, vous pouvez implémenter la configuration. Cette implémentation crée tous les artefacts requis, en fonction de ce que vous avez configuré dans l’assistant.
1. Ce n’est que lorsque vous [publiez manuellement](manual.md) la propriété Balises que votre configuration Content Analytics est effectivement déployée et que la collecte de données commence.

1. Vous pouvez uniquement apporter des modifications mineures à une configuration implémentée à l’aide de l’assistant de [configuration guidée](guided.md). Par exemple, vous pouvez modifier la [vue de données](/help/data-views/data-views.md).
1. Vous pouvez apporter d’autres modifications à une configuration implémentée à l’aide de l’[extension Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Balises associée.
1. Ce n’est que lorsque vous [republiez manuellement](manual.md) la propriété Balises que les modifications de configuration sont effectivement déployées et que la collecte de données, en fonction de vos modifications, commence.


## Conditions préalables

Avant de configurer Content Analytics, assurez-vous de remplir les conditions préalables suivantes :

* Vous avez placé sur la liste autorisée l’agent utilisateur et l’adresse IP du service de fonctionnalité utilisé dans Content Analytics. La chaîne de l’agent utilisateur à configurer est : <code>AdobeFeaturization/1.0</code>.
* Si vous avez implémenté le [SDK web à l’aide de JavaScript](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/library){target="_blank"} pour la collecte régulière de données comportementales, assurez-vous d’utiliser le nom par défaut <code>alloy</code> pour la bibliothèque JavaScript.
* Vous disposez d’un rôle d’administration de produit Customer Journey Analytics, avec des autorisations supplémentaires pour gérer les connexions et les vues de données.
* Si vous envisagez de collecter des expériences Content Analytics, assurez-vous de configurer et de mettre à jour le contrôle de version de [Content Analytics](manual.md#versioning) en fonction des modifications apportées à vos pages web.
* Vous devez disposer des [autorisations pour la collecte de données](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/permissions){target="_blank"} :
   * [Autorisations Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Autorisations pour la collecte de données Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Vous avez soigneusement examiné les options de configuration importantes suivantes :

   * Votre site est adapté à la création de rapports d’expérience. La création de rapports d’expérience n’est possible que si les conditions suivantes sont remplies :
      * Les pages du site doivent être reproductibles à l’aide de l’URL de la page.
      * Le contenu textuel affiché par une personne donnée peut être reproduit à l’aide de l’URL de la page et ne dépend pas de cookies ou d’autres mécanismes de personnalisation.
   * Vous comprenez clairement les pages pour lesquelles vous souhaitez capturer des analyses et des informations sur l’engagement du contenu.
   * Vous comprenez clairement pour quelles ressources et quels types de ressources vous souhaitez capturer des analyses et des informations sur l’engagement du contenu.


## Contrôle d’accès

>[!IMPORTANT]
>
>Vous ne pouvez configurer aucune autorisation Content Analytics pour activer ou désactiver l’accès Content Analytics pour des personnes spécifiques ou des groupes d’utilisateurs et d’utilisatrices.
>

Pour permettre à une personne ou à un groupe d’utilisateurs et d’utilisatrices d’accéder à Content Analytics, vous devez accorder l’accès à une ou plusieurs [vues de données configurées pour Content Analytics](guided.md#data-view).

Cet accès implique ce qui suit :

1. La vue de données activée pour Content Analytics est incluse dans les autorisations de vues de données pour un profil de produit Customer Journey Analytics spécifique.
1. Ce profil de produit Customer Journey Analytics spécifique est l’un des profils de produit affectés à la personne ou au groupe d’utilisateurs et d’utilisatrices.

## Limites

Le schéma utilisé pour les données d’événement Content Analytics appartient au système. Un schéma détenu par le système ne peut pas être modifié, ce qui implique les points suivants :

* Vous ne pouvez pas inclure de groupes de champs pour la prise en charge de fonctionnalités telles que la géolocalisation, la détection de robots ou la recherche d’appareils.
* Vous ne pouvez pas ajouter d’identifiant spécifique pour prendre en charge le [groupement basé sur les champs](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Configuration guidée](guided.md)
>* [Configuration manuelle](manual.md)
>* [Contrôle d’accès](/help/technotes/access-control.md)
>
