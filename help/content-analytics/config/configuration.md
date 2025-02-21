---
title: Configurer Content Analytics
description: Présentation de la configuration de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 20%

---

# Configurer Content Analytics

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{{release-limited-testing}}


Pour configurer Content Analytics pour votre organisation, utilisez la [configuration guidée](guided.md) de Content Analytics. L’assistant de configuration vous guide tout au long des étapes requises pour configurer les conditions préalables à une configuration automatique de Content Analytics.

Une fois l’implémentation terminée, vous pouvez apporter quelques modifications à l’aide de l’assistant de configuration guidé. Cependant, des [modifications manuelles](manual.md) peuvent s’avérer nécessaires en plus de cela.

## Conditions préalables

Avant de configurer Content Analytics, assurez-vous que les conditions préalables suivantes sont remplies :

* Vous avez placé sur la liste autorisée l’agent utilisateur et l’adresse IP du service de fonctionnalité utilisé dans Content Analytics. La chaîne de l’agent utilisateur est `AdobeFeaturization/1.0`.
* Vous disposez d’un rôle d’administrateur de produit Customer Journey Analytics, avec les autorisations supplémentaires pour gérer les connexions et les collections de données. Les autorisations Experience Platform requises sont les suivantes :

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

   * Votre site est adapté au reporting d’expérience ? Un compte rendu des performances approprié n’est possible que lorsque les conditions suivantes sont remplies :
      * Le contenu du site est piloté uniquement par des URL.
      * Les pages de votre site sont reproductibles à l’aide de l’URL de page. Vous comprenez également quels paramètres d’URL facultatifs pilotent les expériences.
   * Vous comprenez clairement les pages pour lesquelles vous souhaitez capturer des analyses et des informations sur l’engagement du contenu.
   * Vous comprenez clairement pour quel (type) de ressources vous souhaitez capturer des analyses et des informations sur l’engagement du contenu.


>>
[!MORELIKETHIS]
>>
* [Configuration guidée](guided.md)
* [Configuration manuelle](manual.md)
* [Contrôle d’accès](/help/technotes/access-control.md)
>


