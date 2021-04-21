---
title: Rapport sur les données Google Analytics dans le Customer Journey Analytics
description: Affiche des rapports utiles sur les données Google Analytics dans le Customer Journey Analytics
translation-type: tm+mt
source-git-commit: a4e95424ee304869e76a0532b7240290a3f13418
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---


# Rapport sur les données Google Analytics dans le Customer Journey Analytics

Maintenant que vous avez [assimilé les données Google Analytics à l&#39;Experience Platform et au Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md), nous vous montrerons quelques scénarios utiles pour le rapports de ces données.

## Visualiser les données Web et d’application sous forme de jeux de données combinés

Ce diagramme de Venn montre le chevauchement des utilisateurs de votre site Web (à partir de vos données Google Analytics) et de votre application mobile (à partir de vos données Firebase) et de votre centre d’appels. Vous pouvez également consulter les produits les plus performants, pas seulement sur le Web, mais également dans l’application mobile. Vous pouvez même obtenir le total des recettes des deux, à l’aide d’une mesure calculée. Notez comment les principaux produits racontent une autre histoire lorsque vous regardez les recettes combinées. Sans les ensembles de données combinés, vous n&#39;auriez jamais su que le &quot;Twill cap&quot; était un si bon rendement.

![](assets/combined-datasets.png)

## Identifier les raisons des appels et réduire le volume des appels

Pour vérifier que vous avez reçu beaucoup d&#39;appels, vous pouvez déterminer la tendance du temps passé par notre centre d&#39;appels au cours des deux derniers mois. Il est facile de voir la tendance croissante. C&#39;est inquiétant, car chaque minute où vos employés du centre d&#39;appels sont au téléphone vous coûte de l&#39;argent. Cela peut certainement avoir un impact sur vos résultats.

Examinons les principales raisons à l&#39;origine de l&#39;augmentation des appels vers le centre d&#39;appels. Notez que &quot;Carte de crédit refusée&quot;, &quot;Retirer la carte de crédit&quot; et &quot;Produit endommagé&quot; sont les principales raisons. Cela peut déjà indiquer comment améliorer l&#39;expérience en ligne. Vous pouvez également déterminer les raisons de ces appels et déterminer celles qui ont le plus contribué au pic global. Il est intéressant de constater que les clients ayant un &quot;produit endommagé&quot; ont passé plus de 3 minutes par appel.

![](assets/call-volume.png)

Examinons de plus près quels produits sont à l&#39;origine de la plupart des appels à votre centre d&#39;appels et combien de clients ont passé ces appels. Le graphique à bulles indique que 20 000 personnes ont appelé, passé plus de 4 heures 30 et renvoyé 33 unités du produit Men&#39;s short Sleeve Tee.

Nous pouvons ventiler cette information et déterminer pourquoi ces personnes ont renvoyé le produit en faisant glisser la dimension &quot;Raison de l’appel&quot;. Comme vous pouvez le constater, la raison pour laquelle ce produit reçoit autant d&#39;appels est due à &quot;Produit endommagé&quot;. L&#39;étape suivante consisterait à contacter le service de contrôle de la qualité et à savoir pourquoi les clients ont reçu des T-shirts endommagés.

![](assets/call-reason.png)

Examinons maintenant les pages du site Web qui ont généré les appels entrants au centre d’appels. Cela vous permet de savoir où se trouvent les expériences peu performantes sur le site Web et d’aider vos responsables de produits à résoudre ces problèmes.

Nous faisons cela en

* Utilisation d’une mesure calculée pour filtrer les données jusqu’aux seules sessions qui se sont terminées par un appel au centre d’appels.
* Utiliser le modèle &quot;participation&quot; dans l’Attribution IQ [de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace).

Vous pouvez facilement identifier les pages qui participent le plus souvent à une session qui se termine par un appel. Vous pouvez voir que les pages &quot;Panier&quot; et &quot;Informations sur le passage en caisse&quot; ont généré la plupart des appels. Puisque vous avez également inclus les données d&#39;application mobile de base de feu, vous pouvez même constater des erreurs de page et des blocages d&#39;application générant les appels. Il s’agit d’un point de données très important si vous souhaitez offrir des expériences Web et d’applications mobiles exceptionnelles.

![](assets/contributing-pages.png)

Enfin, en utilisant le tableau de cohortes en Analysis Workspace, il est facile de déterminer combien de temps il faut généralement aux utilisateurs pour appeler notre centre d’appels après avoir visité le site Web. Vous pouvez voir ici que la durée moyenne est comprise entre 3 et 4 semaines.

![](assets/cohort.png)

## Utilisation de l’attribution marketing avancée

CJA vous permet d’utiliser des modèles d’attribution sophistiqués sur vos données entre canaux. Dans l’exemple suivant, vous pouvez comparer l’application de l’attribution Dernière touche, Première touche, En forme de u et algorithmique des recettes à la dimension Regroupement de Canaux Google Analytics.

![](assets/mktg-attribution.png)

A l’aide d’une mesure calculée, vous pouvez appliquer cette attribution à vos recettes Web, aux recettes des applications mobiles et même supprimer les retours sur les produits. Par conséquent, vous pouvez voir les recettes nettes réelles pour chaque canal marketing.

![](assets/calc-metric.png)

Attribution IQ vous permet également de filtrer facilement vos données. Vous pouvez voir l’attribution par rapport à des jeux spécifiques d’utilisateurs, tels que ceux qui utilisent plusieurs appareils.

![](assets/filter.png)

Enfin, vous pouvez également attribuer vos recettes Web et App à votre contenu publicitaire Google. Vous remarquerez que vous avez gagné plus de recettes grâce à l&#39;application mobile pilotée par nos publicités Google en ligne que grâce au Web. En triant les publicités par recettes web et applicatives, vous obtenez une image très différente de ce que sont les publicités Google les plus performantes.

![](assets/google-ad.png)

Sans CJA, vous n’auriez pas pu savoir que vos publicités en ligne avaient un impact quelconque sur les produits achetés sur votre application mobile. Vous pouvez maintenant constater que les recettes générées par les applications mobiles provenant des publicités Google représentent entre 14 000 et 5 000 dollars de plus, par rapport au Web uniquement.

![](assets/google-ad2.png)