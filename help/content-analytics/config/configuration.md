---
title: Configurer Content Analytics
description: Présentation de la configuration de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 320b1cb94f63d0e6813999c1dc293b7e78ac7845
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---

# Configurer Content Analytics

{{release-limited-testing}}


La configuration de Content Analytics comprend les étapes suivantes :

![Configuration de Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Utilisez l’assistant Content Analytics [configuration guidée](guided.md) pour vous guider tout au long des étapes requises pour configurer les conditions préalables d’une configuration de Content Analytics. Vous pouvez enregistrer vos configurations à tout moment et revenir ultérieurement.
1. Une fois que vous êtes à l’aise avec les valeurs de configuration, vous pouvez implémenter la configuration. Cette implémentation crée tous les artefacts requis, en fonction de ce que vous avez configuré dans l’assistant.
1. Ce n’est que lorsque vous [publiez manuellement](manual.md) la propriété Tags que votre configuration Content Analytics est déployée efficacement et que la collecte de données est lancée.

1. Vous pouvez uniquement apporter des modifications mineures à une configuration implémentée à l’aide de l’assistant [configuration guidée](guided.md). Par exemple, modifiez la [ vue de données ](/help/data-views/data-views.md).
1. Vous pouvez apporter d’autres modifications à une configuration implémentée à l’aide de l’extension [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Tags associée.
1. Ce n’est que lorsque vous [republiez manuellement](manual.md) la propriété Balises que les modifications de configuration sont déployées efficacement et que la collecte de données, en fonction de vos modifications, commence.


## Conditions préalables

Avant de configurer Content Analytics, vérifiez que les conditions préalables suivantes sont remplies :

* Vous avez placé sur la liste autorisée l’agent utilisateur et l’adresse IP du service de fonctionnalité utilisé dans Content Analytics. La chaîne de l’agent utilisateur à configurer est : <code>AdobeFeaturization/1.0</code>.
* Si vous avez implémenté le [Web SDK à l’aide de JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library){target="_blank"} pour la collecte régulière de données comportementales, assurez-vous d’utiliser le nom par défaut <code>alloy</code> pour la bibliothèque JavaScript.
* Vous disposez d’un rôle d’administrateur de produit Customer Journey Analytics, avec les autorisations supplémentaires pour gérer les connexions et les vues de données.
* Vous devez disposer des autorisations [autorisations pour la collecte de données](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}. Ces autorisations se composent des éléments suivants :
   * [autorisations Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Autorisations de la collecte de données Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Vous avez soigneusement examiné les options de configuration importantes suivantes :

   * Votre site est adapté aux rapports d’expérience. Un compte rendu des performances approprié n’est possible que lorsque les conditions suivantes sont remplies :
      * Les pages du site doivent être reproductibles à l’aide de l’URL de la page.
      * Le contenu textuel affiché par un utilisateur donné peut être reproduit à l’aide de l’URL de la page et ne dépend pas de cookies ou d’autres mécanismes de personnalisation.
   * Vous comprenez clairement les pages pour lesquelles vous souhaitez capturer des analyses et des informations sur l’engagement du contenu.
   * Vous comprenez clairement pour quel (type) de ressources vous souhaitez capturer des analyses et des informations sur l’engagement du contenu.


## Contrôle d’accès

>[!IMPORTANT]
>
>Vous ne pouvez configurer aucune autorisation Content Analytics pour activer ou désactiver l’accès Content Analytics pour des utilisateurs individuels ou des groupes d’utilisateurs.
>

Pour permettre à un utilisateur ou à un groupe d’utilisateurs d’accéder à Content Analytics, vous devez lui donner accès à une ou plusieurs [vues de données configurées pour Content Analytics](guided.md#data-view).

Cet accès implique :

1. La vue de données activée pour Content Analytics est incluse dans les autorisations de vues de données pour un profil de produit Customer Journey Analytics spécifique.
1. Ce profil de produit Customer Journey Analytics spécifique est l’un des profils de produit affectés à l’utilisateur ou au groupe d’utilisateurs.

>[!MORELIKETHIS]
>
>* [Configuration guidée](guided.md)
>* [Configuration manuelle](manual.md)
>* [Contrôle d’accès](/help/technotes/access-control.md)
>
