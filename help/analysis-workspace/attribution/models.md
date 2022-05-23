---
title: Modèles d’attribution et intervalles de recherche en amont
description: La manière dont les différents types d’attributions répartissent le crédit entre les éléments de dimension.
Feature: Attribution
exl-id: 2ab6add7-9dc8-419d-96f7-e0c12e6b4761
source-git-commit: d165b3aaca9f99bb23bcbfbcfbca9d2e96b3cfcb
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 100%

---

# Modèles d’attribution et intervalles de recherche en amont

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). [En savoir plus...](/help/getting-started/cja-aa.md)

Le concept d’attribution dans Customer Journey Analytics requiert deux composants :

* **Modèles d’attribution :** le modèle décrit la distribution des conversions pour les accès dans un groupe. Par exemple, Première touche ou Dernière touche.
* **Intervalle de recherche en amont d’attribution :** l’intervalle de recherche en amont décrit les groupes d’accès pris en compte pour chaque modèle. Par exemple, visite ou visiteur.

## Modèles d’attribution

| Icône de l’interface utilisateur | Modèle d’attribution | Définition | Conditions d’utilisation |
| --- | --- | --- | --- |
| ![Dernière touche](assets/last_touch1.png) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. | Le modèle d’attribution le plus élémentaire et le plus courant. Il est fréquemment utilisé pour les conversions avec un cycle de traitement court. Le modèle Dernière touche est couramment utilisé par les équipes qui gèrent le marketing de moteur de recherche ou qui analysent les mots-clés de recherche interne. |
| ![Première touche](assets/first_touch.png) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont d’attribution. | Un autre modèle d’attribution commun utile pour l’analyse des canaux marketing destinés à accroître la notoriété de la marque ou à favoriser l’acquisition client. Il est fréquemment utilisé par les équipes Display ou Marketing social, mais est également utile pour évaluer l’efficacité des recommandations de produits sur site. |
| ![Même touche](assets/same_touch.png) | Même touche | Attribue un crédit de 100 % à l’accès même où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même accès qu’une conversion, il est placé sous « Aucun ». | Un modèle utile pour évaluer le contenu ou l’expérience client qui a été présenté immédiatement au moment de la conversion. Les équipes produit ou de conception utilisent souvent ce modèle pour évaluer l’efficacité d’une page où a lieu une conversion. |
| ![Linéaire](assets/linear.png) | Linéaire | Attribue le même crédit à chaque point de contact visible menant à une conversion. | Utile pour les conversions avec des cycles de traitement plus longs ou des expériences client qui nécessitent un engagement plus fréquent et plus constant de la part des clients. Il est souvent utilisé par des équipes qui mesurent l’efficacité des notifications d’applications mobiles ou avec des produits sur abonnement. |
| ![En forme de U](assets/u_shaped.png) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est attribué aux deux. | Un modèle conseillé à ceux qui valorisent les interactions qui ont introduit ou fermé une conversion, mais qui veulent tout de même reconnaître les interactions d’assistance. L’attribution En forme de U est souvent utilisée par des équipes qui adoptent une approche plus équilibrée, mais qui veulent accorder plus de crédit aux canaux ayant trouvé ou mis fin à une conversion. |
| ![En forme de J](assets/j_shaped.png) | En forme de J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la dernière interaction et 25 % à la première. | Ce modèle est conseillé à ceux qui donnent la priorité aux outils de recherche et de fermeture, mais qui souhaitent se concentrer sur les interactions de fermeture. L’attribution En forme de J est souvent utilisée par des équipes qui adoptent une approche plus équilibrée et qui veulent accorder plus de crédit aux canaux ayant mis fin à une conversion. |
| ![En forme de J inversé](assets/inverse_j.png) | En forme de J inversé | Attribue un crédit de 60 % au premier point de contact, de 20 % au dernier point de contact et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la première interaction et 25 % à la première. | Ce modèle est idéal pour ceux qui donnent la priorité aux outils de recherche et de fermeture, mais qui souhaitent se concentrer sur les interactions de recherche. L’attribution En forme de J inversé est utilisée par des équipes qui adoptent une approche plus équilibrée et qui veulent accorder plus de crédit aux canaux ayant déclenché une conversion. |
| ![Personnalisé](assets/custom.png) | Personnalisé | Permet de spécifier les pondérations à attribuer aux premiers points de contact, aux derniers points de contact et à tous les points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne totalisent pas 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les premiers et derniers points de contact sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. | Ce modèle est parfait pour ceux qui souhaitent un contrôle total sur leur modèle d’attribution et qui ont des besoins spécifiques que d’autres modèles d’attribution ne remplissent pas. |
| ![Décroissance temporelle](assets/time_decay.png) | Décroissance temporelle | Suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de sept jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2^(-t/halflife)`, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont alors normalisés à 100 %. | L’idéal pour les équipes qui exécutent régulièrement de la publicité vidéo ou qui font du marketing pour des événements avec une date prédéterminée. Plus une conversion se produit après un événement marketing, plus faible sera le crédit attribué. |
| ![Participation](assets/participation.png) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Le nombre total de conversions est gonflé par rapport aux autres modèles d’attribution. La participation déduplique les canaux qui sont vus à plusieurs reprises. | Excellent pour comprendre la fréquence à laquelle les clients sont exposés à une interaction donnée. Les sociétés de médias utilisent fréquemment ce modèle pour calculer la vitesse du contenu. Les sociétés de vente au détail utilisent souvent ce modèle pour comprendre les parties de leur site qui sont essentielles à la conversion. |
| ![Algorithmique](assets/algorithmic.png) | [Algorithmique](/help/analysis-workspace/attribution/algorithmic.md) | Utilise des techniques statistiques pour déterminer de manière dynamique l’allocation optimale du crédit pour la mesure sélectionnée. | Utile pour éviter les conjectures ou les heuristiques lors du choix du modèle d’attribution approprié pour votre entreprise. |

## Intervalles de recherche en amont

Un intervalle de recherche en amont est la durée pendant laquelle une conversion doit faire une recherche en amont pour inclure des points de contact. Les modèles d’attribution qui accordent plus de crédit aux premières interactions voient des différences plus importantes lors de l’affichage de différents intervalles de recherche en amont.

* **Intervalles de recherche en amont des visites :** recherchent en amont jusqu’au début d’une visite au cours de laquelle une conversion s’est produite. Les intervalles de recherche en amont des visites sont étroits, car ils ne recherchent pas au-delà de la visite. Les intervalles de recherche en amont des visites respectent la définition de visite modifiée dans les vues de données.

* **Intervalles de recherche en amont des visiteurs :** recherchent toutes les visites en amont jusqu’au 1er du mois de la période en cours. Les intervalles de recherche en amont des visiteurs sont larges, car ils peuvent porter sur plusieurs visites. La recherche en amont des visiteurs prend en compte toutes les valeurs depuis le début du mois de la période du rapport. Par exemple, si la période du rapport s’étend du 15 au 30 septembre, la période de recherche en amont des visiteurs est du 1er au 30 septembre.

* **Intervalle de recherche en amont personnalisé :** permet d’étendre l’intervalle d’attribution au-delà de la période des rapports pendant un maximum de 90 jours. Les intervalles de recherche en amont personnalisés sont évalués pour chaque conversion pendant la période des rapports. Par exemple, pour une conversion survenant le 20 février, un intervalle de recherche en amont de 10 jours évalue tous les points de contact de dimension du 10 au 20 février dans le modèle d’attribution.

## Exemple

Examinez l’exemple suivant :

1. Le 15 septembre, un visiteur arrive sur votre site par le biais d’une annonce de référencement payant, puis le quitte.
2. Le 18 septembre, le visiteur arrive de nouveau sur votre site par le biais d’un lien sur les médias sociaux qu’un ami lui a envoyé. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
3. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre intervalle de recherche en amont et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples intéressants :

* À l’aide de **Première touche** et d’un **intervalle de recherche en amont des visites**, l’attribution ne s’intéresse qu’à la troisième visite. Entre le courrier électronique et l’affichage, le courrier électronique était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $.
* À l’aide de **Première touche** et d’un **intervalle de recherche en amont des visiteurs**, l’attribution s’intéresse aux trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $.
* À l’aide de **Linéaire** et d’un **intervalle de recherche en amont des visites**, le crédit est divisé entre le courrier électronique et l’affichage. Ces deux canaux reçoivent chacun un crédit de 25 $.
* À l’aide de **linéaire** et d’un **intervalle de recherche en amont des visiteurs**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat.
* À l’aide de **En forme de J** et d’un **intervalle de recherche en amont des visiteurs**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage.
   * Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.
   * Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.
* À l’aide de **Décroissance temporelle** et d’un **intervalle de recherche en amont des visiteurs**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage. Utilisation de la demi-vie de sept jours par défaut :
   * Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`
   * Intervalle de zéro jour entre le point de contact du courrier électronique et la conversion. `2^(-0/7) = 1`
   * Intervalle de six jours entre le point de contact de réseaux sociaux et la conversion. `2^(-6/7) = 0.552`
   * Intervalle de neuf jours entre le point de contact du référencement payant et la conversion. `2^(-9/7) = 0.41`
   * La normalisation de ces valeurs entraîne les résultats suivants :
      * Affichage : 33,8 %, gain de 16,88 $
      * Courrier électronique : 33,8 %, gain de 16,88 $
      * Réseaux sociaux : 18,6 %, gain de 9,32 $
      * Référencement payant : 13,8 %, gain de 6,92 $

>[!NOTE]
>
>D’autres événements de conversion, tels que des commandes ou des événements personnalisés, sont également divisés si le crédit appartient à plusieurs canaux. Par exemple, si deux canaux contribuent à un événement personnalisé à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de l’événement personnalisé. Ces fractions d’événement sont additionnées pour toutes les visites, puis arrondies à l’entier le plus proche à des fins de création de rapports.
