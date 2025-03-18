---
title: Configurer Content Analytics
description: Présentation de la configuration de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 11%

---

# Configurer Content Analytics

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{{release-limited-testing}}

La configuration de Content Analytics comprend les étapes suivantes :

![Configuration de Content Analytics](../assets/aca-configuration.svg)

1. Utilisez l’assistant Content Analytics [configuration guidée](guided.md) pour vous guider tout au long des étapes requises pour configurer les conditions préalables d’une configuration de Content Analytics. Vous pouvez enregistrer vos configurations et revenir ultérieurement.
1. Une fois que vous êtes à l’aise avec les valeurs de configuration, vous pouvez implémenter la configuration. Cette implémentation crée tous les artefacts requis, en fonction de ce que vous avez configuré dans l’assistant. Les artefacts suivants sont créés, mis à jour ou sélectionnés :
   * Customer Journey Analytics
      * Une [vue de données](/help/data-views/data-views.md) est sélectionnée.
      * Une [connexion](/help/connections/overview.md) est sélectionnée et est automatiquement dérivée de la vue de données sélectionnée.
   * Experience Platform
      * Le sandbox est sélectionné et est automatiquement dérivé de la connexion. Les workflows et services nécessaires sont activés dans le sandbox .
      * Les schémas Content Analytics sont sélectionnés dans le sandbox . S’ils ne sont pas disponibles, les schémas nécessaires sont créés.
      * Les jeux de données Content Analytics sont sélectionnés dans le sandbox . S’ils ne sont pas disponibles, les jeux de données nécessaires sont créés.
   * Collecte de données
      * Un flux de données est créé et un service Experience Platform est configuré dans le flux de données pour diffuser des données vers le jeu de données d’événement d’expérience Content Analytics.
      * Une propriété Tags est créée avec l’extension Adobe Content Analytics configurée pour le sandbox, le flux de données et d’autres options de configuration appropriés à partir de l’assistant de configuration.
1. Ce n’est que lorsque vous [publiez manuellement](manual.md) la propriété Balises que votre configuration Content Analytics est déployée et activée.

1. Vous pouvez uniquement apporter des modifications mineures à une configuration implémentée à l’aide de l’assistant [configuration guidée](guided.md). Par exemple, modifiez la [vue de données](/help/data-views/data-views.md).
1. Vous pouvez apporter d’autres modifications à une configuration implémentée. Utilisez l’extension [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Tags associée.
1. Ce n’est que lorsque vous [republiez manuellement](manual.md) la propriété Tags que les modifications de configuration des étapes 4 et 5 sont déployées et activées efficacement.


## Conditions préalables

Avant de configurer Content Analytics, vérifiez que les conditions préalables suivantes sont remplies :

* Vous avez placé sur la liste autorisée l’agent utilisateur et l’adresse IP du service de fonctionnalité utilisé dans Content Analytics. La chaîne de l’agent utilisateur à configurer est : <code>AdobeFeaturization/1.0</code>.
* Vous disposez d’un rôle d’administrateur de produit Customer Journey Analytics, avec les autorisations supplémentaires pour gérer les connexions et les vues de données.
* Vous disposez des autorisations Experience Platform requises :

  | Catégorie | Autorisation | Description |
  |---|---|---|
  | [!UICONTROL Collecte de données] | Afficher les flux de données | Accès en lecture seule aux flux de données. |
  | [!UICONTROL Collecte de données] | Gérer les flux de données | Accès à la lecture, la création, la modification et la suppression des flux de données. |
  | [!UICONTROL Modélisation des données] | [!UICONTROL Affichage des schémas] | Accès en lecture seule aux schémas et aux ressources associées. |
  | [!UICONTROL Modélisation des données] | [!UICONTROL Gestion des schémas] | Accès pour lire, créer, modifier et supprimer des schémas et des ressources associées. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Affichage des jeux de données] | Accès en lecture seule aux jeux de données et aux schémas. |
  | [!UICONTROL Gestion des données] | [!UICONTROL Gestion des jeux de données] | Accès à la lecture, la création, la modification et la suppression des jeux de données. Accès en lecture seule aux schémas. |
  | [!UICONTROL Ingestion des données] | [!UICONTROL Gestion des sources] | Accès à la lecture, la création, la modification et la désactivation des sources. |
  | [!UICONTROL Identity Management] | [!UICONTROL Affichages des espaces de noms d’identité] | Accès en lecture seule aux espaces de noms d’identité. |

* Vous avez soigneusement examiné les options de configuration importantes suivantes :

   * Votre site est adapté aux rapports d’expérience. Un compte rendu des performances approprié n’est possible que lorsque les conditions suivantes sont remplies :
      * Vous pouvez accéder au contenu du site uniquement par le biais d’URL publiques. L&#39;accès au site ne nécessite pas de jetons personnalisés, de cookies ou d&#39;autres mécanismes non disponibles via l&#39;URL.
      * Les pages de votre site sont reproductibles à l’aide de l’URL de page. Vous comprenez également quels paramètres d’URL facultatifs pilotent les expériences.
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
