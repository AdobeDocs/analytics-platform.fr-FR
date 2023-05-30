---
title: 'Paramètres des composants : attribution'
description: Permet de définir lʼattribution par défaut dʼune mesure.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 81e04d177596430b6e9d971cb1b157b461524314
workflow-type: tm+mt
source-wordcount: '1781'
ht-degree: 38%

---

# Paramètres des composants : attribution

Attribution vous permet de personnaliser la manière dont les éléments de dimension obtiennent du crédit pour les événements de succès.

![](../assets/attribution-settings.png)

Par exemple :

1. Une personne qui se rend sur votre site clique sur un lien de recherche payante vers l’une de vos pages de produits. Ils ajoutent le produit à leur panier, mais ne l’achètent pas.
2. Le lendemain, ils ont vu un message sur les médias sociaux d&#39;un de leurs amis. Ils cliquent sur le lien, puis effectuent l’achat.

Dans certains rapports, vous voudrez peut-être attribuer la commande au référencement payant. Dans d’autres rapports, vous voudrez peut-être attribuer la commande à Social. Attribution vous permet de contrôler cet aspect des rapports.

Ce paramètre de composant de vue de données vous permet de définir un modèle d’attribution par défaut pour une mesure. Vous pouvez remplacer le modèle dʼattribution dʼune mesure donnée lorsque vous travaillez dans Analysis Workspace.



Si votre entreprise exige qu’une mesure comporte plusieurs paramètres d’attribution, vous pouvez effectuer l’une des opérations suivantes :

* Copiez la mesure dans la vue de données avec chaque paramètre d’attribution souhaité. Vous pouvez inclure plusieurs fois la même mesure dans une vue de données, ce qui donne à chaque mesure un paramètre différent. Veillez à étiqueter correctement chaque mesure afin que les analystes comprennent la différence entre ces mesures lors de la génération des rapports.
* Permet de remplacer la mesure dans Analysis Workspace. Dans une mesure [Paramètres des colonnes](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md), sélectionnez **[!UICONTROL Utilisation d’un modèle d’attribution différent du modèle par défaut]** pour modifier le modèle d’attribution de la mesure et l’intervalle de recherche en amont pour ce rapport spécifique.

## Modèles d’attribution

Un modèle d’attribution détermine les éléments de dimension qui reçoivent du crédit pour une mesure lorsque plusieurs valeurs sont affichées dans l’intervalle de recherche en amont d’une mesure. Les modèles d’attribution ne s’appliquent que lorsque plusieurs éléments de dimension sont définis dans l’intervalle de recherche en amont. Si un seul élément de dimension est défini, celui-ci obtient un crédit de 100 %, quel que soit le modèle d’attribution utilisé.

| Icône | Modèle d’attribution | Définition |
| :---: | :--- | --- |
| ![Dernière touche](../assets/attribution-models/last_touch1.png) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. Ce modèle d’attribution est généralement la valeur par défaut d’une mesure pour laquelle aucun modèle d’attribution n’est spécifié autrement. Les entreprises utilisent généralement ce modèle lorsque le temps de conversion est relativement court, comme lors de l’analyse des mots-clés de recherche interne. |
| ![Première touche](../assets/attribution-models/first_touch.png) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont des attributions. Les entreprises utilisent généralement ce modèle pour comprendre la notoriété de la marque ou l’acquisition de clients. |
| ![Linéaire](../assets/attribution-models/linear.png) | Linéaire | Attribue le même crédit à chaque point de contact visible menant à une conversion. Elle s’avère utile lorsque les cycles de conversion sont plus longs ou nécessitent un engagement plus fréquent de la part des clients. Les entreprises utilisent généralement ce modèle d’attribution qui mesure l’efficacité des notifications d’applications mobiles ou avec des produits par abonnement. |
| ![Participation](../assets/attribution-models/participation.png) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Chaque point de contact recevant un crédit de 100 %, les données de mesure s’élèvent généralement à plus de 100 %. Si un élément de dimension apparaît plusieurs fois, ce qui entraîne une conversion, les valeurs sont dédupliquées à 100 %. Ce modèle d’attribution est idéal lorsque vous souhaitez identifier les points de contact les plus exposés. Les organisations multimédias utilisent généralement ce modèle pour calculer la vitesse du contenu. Les entreprises de vente au détail utilisent généralement ce modèle pour déterminer les parties de leur site qui sont essentielles à la conversion. |
| ![Même touche](../assets/attribution-models/same_touch.png) | Même touche | Attribue un crédit de 100 % au même événement que celui où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même événement qu’une conversion, il est placé sous &quot;Aucun&quot;. Ce modèle d’attribution est parfois assimilé à l’absence de modèle d’attribution. Elle s’avère utile dans les cas où vous ne souhaitez pas que les valeurs d’autres événements affectent la manière dont une mesure accorde du crédit aux éléments de dimension. Les équipes produit ou de conception peuvent utiliser ce modèle pour évaluer l’efficacité d’une page où une conversion se produit. |
| ![En forme de U](../assets/attribution-models/u_shaped.png) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est attribué aux deux. Ce modèle d’attribution est mieux utilisé dans les scénarios où vous évaluez le plus les premières et les dernières interactions, mais ne souhaitez pas entièrement ignorer les interactions supplémentaires entre les deux. |
| ![Courbe en J](../assets/attribution-models/j_shaped.png) | Courbe en J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la dernière interaction et 25 % à la première. Tout comme en forme de U, ce modèle d’attribution favorise la première et la dernière interactions, mais favorise plus fortement la dernière interaction. |
| ![En forme de J inversé](../assets/attribution-models/inverse_j.png) | En forme de J inversé | Attribue un crédit de 60 % au premier point de contact, de 20 % au dernier point de contact et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la première interaction et 25 % à la première. Tout comme en forme de J, ce modèle d’attribution favorise la première et la dernière interactions, mais favorise plus fortement la première interaction. |
| ![Décroissance temporelle](../assets/attribution-models/time_decay.png) | Décroissance temporelle | Suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de sept jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2^(-t/halflife)`, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont alors normalisés à 100 %. Idéal pour les scénarios où vous souhaitez mesurer l’attribution par rapport à un événement spécifique et significatif. Plus une conversion se produit après cet événement, moins le crédit est attribué. |
| ![Personnalisé](../assets/attribution-models/custom.png) | Personnalisé | Permet de spécifier les pondérations à attribuer au premier point de contact, au dernier point de contact et aux points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne totalisent pas 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les premiers et derniers points de contact sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. Ce modèle est idéal pour les analystes qui souhaitent un contrôle total sur leur modèle d’attribution et qui ont des besoins spécifiques que d’autres modèles d’attribution ne remplissent pas. |
| ![Algorithmique](../assets/attribution-models/algorithmic.png) | Algorithmique | Utilise des techniques statistiques pour déterminer de manière dynamique l’allocation optimale du crédit pour la mesure sélectionnée. L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.<br>À un haut niveau, l’attribution est calculée en une coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l&#39;excédent de chaque coalition est déterminée en fonction de l&#39;excédent précédemment créé par chaque sous-coalition (ou des éléments de dimension ayant participé précédemment) de manière récurrente. Pour plus de détails, voir les documents originaux de John Harsanyi et de Lloyd Shapley :<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. 1963. A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Intervalle de recherche en amont

Un intervalle de recherche en amont est la durée pendant laquelle une conversion doit faire une recherche en amont pour inclure des points de contact. Si un élément de dimension est défini en dehors de l’intervalle de recherche en amont, la valeur n’est incluse dans aucun calcul d’attribution.

* **14 jours**: Recherche jusqu’à 14 jours à partir du moment où la conversion a eu lieu.
* **30 jours**: Recherche jusqu’à 30 jours à compter du moment de la conversion.
* **60 jours**: Recherche jusqu’à 60 jours à partir du moment où la conversion a eu lieu.
* **90 jours**: Recherche jusqu’à 90 jours à partir du moment où la conversion a eu lieu.
* **Session**: Recherche en amont jusqu’au début de la session au cours de laquelle une conversion s’est produite. Les intervalles de recherche en amont des sessions respectent la modification [Timeout de session](../create-dataview.md#session-settings).
* **Personne (fenêtre de création de rapports)**: Recherche toutes les visites en amont jusqu’au premier du mois de la période en cours. Par exemple, si la période du rapport s’étend du 15 au 30 septembre, la période de recherche en amont des personnes est du 1er au 30 septembre. Si vous utilisez cet intervalle de recherche en amont, vous pouvez parfois constater que les éléments de dimension sont attribués aux dates en dehors de votre créneau de rapport.
* **Heure personnalisée :** Permet de définir un intervalle de recherche en amont personnalisé à partir du moment où une conversion s’est produite. Vous pouvez spécifier le nombre de minutes, heures, jours, semaines, mois ou trimestres. Par exemple, si une conversion a eu lieu le 20 février, un intervalle de recherche en amont de cinq jours évalue tous les points de contact de dimension du 15 au 20 février dans le modèle d’attribution.

## Exemple

Examinez l’exemple suivant :

1. Le 15 septembre, une personne arrive sur votre site par le biais d’une annonce de référencement payant, puis la quitte.
2. Le 18 septembre, la personne arrive de nouveau sur votre site par le biais d&#39;un lien sur les médias sociaux qu&#39;elle a reçu d&#39;un ami. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
3. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre intervalle de recherche en amont et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples intéressants :

* Utilisation **Première touche** et un **intervalle de recherche en amont des sessions**, l’attribution ne tient compte que de la troisième visite. Entre le courrier électronique et l’affichage, le courrier électronique était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $.
* Utilisation **Première touche** et un **intervalle de recherche en amont des personnes**, l’attribution examine les trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $.
* Utilisation **linear** et un **intervalle de recherche en amont des sessions**, le crédit est divisé entre le courrier électronique et l’affichage. Ces deux canaux reçoivent chacun un crédit de 25 $.
* Utilisation **linear** et un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat.
* Utilisation **En forme de J** et un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage.
   * Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.
   * Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.
* Utilisation **Décroissance temporelle** et un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage. Utilisation de la demi-vie de sept jours par défaut :
   * Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`
   * Intervalle de zéro jour entre le point de contact du courrier électronique et la conversion. `2^(-0/7) = 1`
   * Intervalle de six jours entre le point de contact du réseau social et la conversion. `2^(-6/7) = 0.552`
   * Intervalle de neuf jours entre le point de contact du référencement payant et la conversion. `2^(-9/7) = 0.41`
   * La normalisation de ces valeurs entraîne les résultats suivants :
      * Affichage : 33,8 %, gain de 16,88 $
      * Courrier électronique : 33,8 %, gain de 16,88 $
      * Réseaux sociaux : 18,6 %, gain de 9,32 $
      * Référencement payant : 13,8 %, gain de 6,92 $

Les événements de conversion qui comportent généralement des nombres entiers sont divisés si le crédit appartient à plusieurs canaux. Par exemple, si deux canaux contribuent à une commande à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de cet ordre. Ces mesures partielles sont additionnées pour toutes les personnes, puis arrondies à l’entier le plus proche pour la création de rapports.
