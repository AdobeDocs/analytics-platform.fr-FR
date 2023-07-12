---
title: FAQ sur les analyses guidées
description: Questions fréquentes sur l’analyse guidée.
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 3%

---

# FAQ sur les analyses guidées

{{release-limited-testing}}

Questions fréquentes sur l’analyse guidée.

+++**L’analyse guidée est-elle disponible pour tous ?**

Non. L’analyse guidée est un module complémentaire payant pour Customer Journey Analytics. Si vous souhaitez commencer à utiliser ce module complémentaire, contactez votre équipe de compte d’Adobe.

+++

+++**Quelles modifications de mise en oeuvre sont requises pour utiliser l’analyse guidée ?**

Si vous utilisez déjà Analysis Workspace dans Customer Journey Analytics, aucune modification supplémentaire de mise en oeuvre n’est nécessaire. L’analyse guidée utilise les mêmes vues et connexions de données qu’Analysis Workspace. Le processus d’intégration et d’utilisation de n’importe quel type de projet est identique pour tous les Customer Journey Analytics, y compris l’analyse guidée.

+++

+++**Comment les termes sont-ils liés les uns aux autres à l’intérieur et à l’extérieur de l’analyse guidée ?**

L’analyse guidée utilise des termes qui sont plus fréquemment utilisés dans l’analyse de produit. Vous pouvez référencer ce tableau lorsque vous passez d’une analyse guidée à l’autre.

| Terme d’analyse guidée | Terme Analysis Workspace |
| --- | --- |
| Événement | Mesure |
| Propriété | Dimension |
| Valeur | Élément de dimension |
| Segment | Filtrer |

{style="table-layout:auto"}

+++

+++**Quelles sont les différences concernant la manière dont Analysis Workspace et l’analyse guidée traitent les rapports ?**

Bien qu’Analysis Workspace et les analyses guidées utilisent les mêmes données sous-jacentes, la manière dont chaque outil interroge ces données est différente.

* **Analysis Workspace est une expérience centrée sur les dimensions.** Les tableaux se composent généralement de lignes d’éléments de dimension, tandis que les colonnes sont généralement des mesures. Vous pouvez appliquer des filtres à l’une ou l’autre de ces méthodes pour obtenir les données souhaitées.

* **L’analyse guidée est une expérience centrée sur un événement.** Les visualisations se concentrent sur les événements, à l’aide de dimensions et de filtres pour compléter ces données.

![Structure](assets/structure.png)

Examinez l’exemple suivant où vous vous focalisez sur les données de la page d’accueil de votre site web. Les équipes posent des questions similaires, mais l’approche de l’analyse peut être différente.

* Une approche Analysis Workspace généralement centrée sur les dimensions serait : &quot;Combien de pages vues a-t-elle reçu la page d’accueil ?&quot;

  ![Dimension centrée](assets/dimension-centered.png)

* Une approche d’analyse guidée généralement centrée sur les événements serait : &quot;Combien d’utilisateurs ont consulté la page d’accueil ?&quot;

  ![Événement centré](assets/event-centered.png)

Ces instructions illustrent deux méthodes différentes pour obtenir un même rapport, selon votre stratégie de gestion des événements.

+++
