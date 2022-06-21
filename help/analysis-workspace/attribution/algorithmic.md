---
title: Attribution algorithmique
description: Détails sur le modèle d’attribution algorithmique.
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 100%

---

# Attribution algorithmique

Regardez cet aperçu vidéo sur lʼattribution algorithmique :

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

Le [modèle d’attribution](models.md) algorithmique dans Analysis Workspace diffère des autres modèles dans la mesure où il utilise des techniques statistiques pour répartir le crédit entre les éléments de dimension dans votre rapport ou tableau à structure libre. Comme tous les autres modèles d’attribution dans Analysis Workspace, il peut être utilisé sur n’importe quelle dimension ou mesure et prend en charge les filtres et les ventilations illimitées. Il distribue 100 % des conversions aux dimensions du tableau (cela est également appelé attribution « partielle »).

L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.

À un niveau élevé, le calcul d’attribution du crédit de conversion pour chaque point de contact prend en compte chacun des points de contact marketing dans un intervalle de recherche en amont comme une coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des éléments de dimension ayant participé précédemment) de façon récurrente. Pour plus d’informations, consultez les publications originales de John Harsanyi et de Lloyd Shapley :

* Shapley, Lloyd S. 1953. A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. 1963. A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>Le résultat de l’attribution algorithmique diffère des autres modèles uniquement lorsque plusieurs points de contact existent dans l’intervalle de recherche en amont donné. Les conversions avec un seul point de contact reçoivent 100 % du crédit, quel que soit le modèle d’attribution.
