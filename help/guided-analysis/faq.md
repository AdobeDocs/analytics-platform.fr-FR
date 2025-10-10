---
title: Questions fréquences sur l’analyse guidée
description: Questions fréquentes sur l’analyse guidée.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 100%

---

# Questions fréquences sur l’analyse guidée

Questions fréquentes sur l’analyse guidée.

+++**Mon organisation a-t-elle accès à l’analyse guidée ?**

Les vues d’analyse guidée sont incluses dans tous les packages Customer Journey Analytics. Pour en savoir plus sur les vues déverrouillées par votre package CJA, consultez la section [approvisionnement](overview.md#provisioning) sur la page Vue d’ensemble.

+++

+++**Quelles modifications de mise en œuvre sont requises pour utiliser l’analyse guidée ?**

Si vous utilisez déjà Customer Journey Analytics, aucune modification supplémentaire de mise en œuvre n’est nécessaire. L’analyse guidée utilise les mêmes [Vues de données](../data-views/data-views.md) et [Connexions](../connections/overview.md) que d’autres interfaces CJA, comme [Analysis Workspace](../analysis-workspace/home.md).

Pour que les utilisateurs et les utilisatrices finaux puissent tirer le meilleur parti de l’analyse guidée, nous vous recommandons d’avoir un schéma d’événement et une stratégie de gestion efficaces incorporés dans Adobe Experience Platform et dans les [Vues de données](../data-views/data-views.md).

+++

+++**Quand devez-vous utiliser l’analyse guidée ou Analysis Workspace ?**

Grâce à l’**analyse guidée**, les utilisateurs et les utilisatrices peuvent obtenir rapidement des informations de qualité. Elle est utile aux équipes produit, aux utilisateurs et utilisatrices qui souhaitent exploiter les données en toute confiance, et même aux personnes chargées de l’analyse pour leur permettre d’approfondir l’analyse.

**[Analysis Workspace](../analysis-workspace/home.md)** est un espace à structure plus libre qui vous permet d’approfondir l’analyse des données afin d’en découvrir d’autres. Il est utile aux personnes chargées de l’analyse et aux utilisateurs et utilisatrices expérimentés familiarisés avec les données et qui souhaitent les approfondir davantage.

+++

+++**Quelles sont les différences de terminologie entre l’analyse guidée et Analysis Workspace ?**

L’analyse guidée et [Analysis Workspace](../analysis-workspace/home.md) s’alignent sur la plupart des termes clés, avec quelques petites différences.

| Terme d’analyse guidée | Terme d’Analysis Workspace |
| --- | --- |
| Événement (mesure binaire 1/0) | Mesure |
| Utilisateurs et utilisatrices | Personnes |
| Dimension | Dimension |
| Élément de dimension | Élément de dimension |
| Segment | Segment |
| Filtre | Filtre de rapport |
| Mesure calculée, mesures | Mesure calculée |

{style="table-layout:auto"}

+++

+++**Quelles sont les différences d’approche concernant la création de rapports entre l’analyse guidée et Analysis Workspace ?**

Bien qu’[Analysis Workspace](../analysis-workspace/home.md) et l’analyse guidée utilisent les mêmes données sous-jacentes, la manière dont chaque outil vous permet de formuler des requêtes sur ces données est différente.

* **Analysis Workspace est une expérience centrée sur la dimension.** Les tableaux comprennent généralement des lignes dimensionnelles, tandis que les colonnes sont généralement des mesures. Des segments peuvent être appliqués à la fois aux lignes et aux colonnes pour obtenir les données souhaitées.

* **L’analyse guidée est une expérience centrée sur l’événement et l’utilisateur ou l’utilisatrice.** Chaque analyse commence par sélectionner des événements, puis des dimensions et des segments peuvent être ajoutés pour affiner ces données d’événement.

![Vues d’Analysis Workspace et d’analyse guidée](assets/structure.png){style="border:1px solid gray"}

Observez l’exemple suivant dans lequel vous ciblez les données de la page d’accueil de votre site web. Les équipes posent des questions similaires, mais l’approche de l’analyse peut être différente.

* Une approche Analysis Workspace centrée sur la dimension type serait la suivante : « Observons la page d’accueil et voyons combien de pages ont été consultées ».

  ![Centrée sur la dimension](assets/dimension-centered.png){style="border:1px solid gray"}

* Une approche d’analyse guidée d’événement type, centrée sur l’utilisateur ou l’utilisatrice, serait la suivante : « Combien d’utilisateurs et d’utilisatrices ont consulté notre page d’accueil ? ».

  ![Centrée sur l’événement](assets/event-centered.png){style="border:1px solid gray"}

+++
