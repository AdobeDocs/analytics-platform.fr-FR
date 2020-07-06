---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 7%

---


# Attribution algorithmique

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL Les tests d’attribution]** algorithmique sont actuellement limités. Pour plus d’informations, reportez-vous à la page [Versions](https://docs.adobe.com/content/help/fr-FR/analytics/landing/an-releases.html) des fonctionnalités Adobe.

Le modèle [d’](models.md) attribution algorithmique dans l’Analysis Workspace diffère des autres modèles en ce qu’il utilise des techniques statistiques pour allouer du crédit sur les valeurs de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution en Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge la segmentation et les ventilations illimitées et distribue 100 % des conversions à la ou aux dimensions du tableau (également appelée attribution fractionnelle).

L&#39;algorithme utilisé pour l&#39;attribution est basé sur le Dividende Harsanyi de la théorie du jeu coopératif. Le dividende de Harsanyi est une généralisation de la solution de valeur de Shapley (du nom de Lloyd Shapley, un économiste lauréat du prix Nobel) pour distribuer le crédit entre les joueurs dans un jeu avec des contributions inégales au résultat.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact considère chacun des points de contact marketing dans une fenêtre de recherche en amont comme une coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des valeurs de dimension précédemment participantes) de façon récursive. Pour plus de détails, voir les documents originaux de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. (1953). Valeur pour les jeux en personne. *Contributions à la Théorie des Jeux, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Un modèle de négociation simplifié pour le jeu coopératif en personne. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Le résultat de l’attribution algorithmique ne diffère que des autres modèles lorsque plusieurs points de contact existent dans la fenêtre de recherche donnée. Les conversions avec un seul point de contact reçoivent un crédit de 100 %, quel que soit le modèle d’attribution.
