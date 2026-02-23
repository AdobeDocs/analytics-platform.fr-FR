---
title: Attribution algorithmique
description: Comprenez les détails du modèle d’attribution algorithmique.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 42%

---

# Attribution algorithmique

Le [modèle d’attribution](models.md) algorithmique dans Analysis Workspace diffère des autres modèles dans la mesure où il utilise des techniques statistiques pour répartir le crédit entre les éléments de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution d’Analysis Workspace, l’attribution algorithmique peut être utilisée sur n’importe quelle dimension ou mesure. L’attribution algorithmique prend en charge une segmentation et des répartitions illimitées et distribue 100 % des conversions à une ou plusieurs dimensions du tableau (également appelée attribution « partielle »).


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution algorithmique](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende de Harsanyi est une généralisation de la solution de valeur de Shapley (du nom de Lloyd Shapley, lauréat du prix Nobel d&#39;économie) pour répartir le crédit entre les joueurs d&#39;un jeu ayant des contributions inégales au résultat.

À un niveau élevé, le calcul de l’attribution du crédit de conversion pour chaque point de contact considère chacun des points de contact marketing dans un intervalle de recherche en amont comme une coalition de joueurs. Pour cette coalition d&#39;acteurs, un surplus doit être équitablement réparti. La distribution des excédents de chaque coalition est déterminée à partir de l&#39;excédent que chaque sous-coalition a créé de manière récursive auparavant.

Pour plus de détails, voir les articles originaux de John Harsanyi et Lloyd Shapley :

* Shapley, Lloyd S. 1953. A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. 1963. A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Le résultat de l’attribution algorithmique diffère des autres modèles uniquement lorsque plusieurs points de contact existent dans l’intervalle de recherche en amont donné. Les conversions avec un seul point de contact reçoivent 100 % du crédit, quel que soit le modèle d’attribution.
