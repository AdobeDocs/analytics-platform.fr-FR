---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique.
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 78%

---

# Attribution algorithmique

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL L’]** attribution algorithmique fait actuellement l’objet de tests limités. Voir [Versions des fonctionnalités Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/landing/an-releases.html) pour plus d’informations.

Le [modèle d’attribution](models.md) algorithmique dans Analysis Workspace diffère des autres modèles dans la mesure où il utilise des techniques statistiques pour répartir le crédit entre les éléments de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution dans Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge un nombre illimité de filtres et de ventilations et distribue 100 % des conversions aux dimensions du tableau (également appelée attribution &quot;partielle&quot;).

L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact prend en compte chacun des points de contact marketing dans un intervalle de recherche en amont comme une coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des éléments de dimension ayant participé précédemment) de façon récurrente. Pour plus d’informations, consultez les publications originales de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. 1953. A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. 1963. A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Le résultat de l’attribution algorithmique diffère des autres modèles uniquement lorsque plusieurs points de contact existent dans l’intervalle de recherche en amont donné. Les conversions avec un seul point de contact reçoivent 100 % du crédit, quel que soit le modèle d’attribution.
