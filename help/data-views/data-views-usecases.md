---
title: Cas d’utilisation des vues de données dans le Customer Journey Analytics
description: Plusieurs cas d'utilisation qui montrent la flexibilité et la puissance des vues de données dans le Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# Cas d’utilisation des vues de données

Les possibilités

## Création d’une mesure Commandes à partir d’un champ de schéma pageTitle (chaîne)

Par exemple, lors de la création d’une vue de données, vous pouvez créer une mesure [!UICONTROL Commandes] à partir d’un champ de schéma [!UICONTROL pageTitle] qui est une chaîne. Voici les étapes :

1. Dans l’onglet Composants, faites glisser [!UICONTROL pageTitle] dans la section [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
   ![](assets/use-case1a.png)
1. Mettez maintenant en surbrillance la mesure que vous venez de faire glisser et renommez-la sous [!UICONTROL Paramètres du composant] sur la droite :
   ![](assets/orders.png)
1. Ouvrez la boîte de dialogue [!UICONTROL Inclure/Exclure les valeurs] sur la droite et spécifiez les éléments suivants :
   ![](assets/orders2.png)

   La phrase &quot;confirmation&quot; indique qu’il s’agit d’une commande. Après avoir examiné tous les titres de page pour lesquels ces critères sont satisfaits, un &quot;1&quot; est comptabilisé pour chaque instance. Le résultat est une nouvelle mesure (pas une mesure calculée). Il fonctionne avec l’Attribution IQ, les filtres et partout où vous pouvez utiliser des mesures standard.
1. Vous pouvez également spécifier un modèle d’attribution pour cette mesure, tel que [!UICONTROL Dernière touche], avec une [!UICONTROL fenêtre de recherche] de [!UICONTROL Session].
Vous pouvez également créer une autre mesure [!UICONTROL Commandes] à partir du même champ et spécifier un modèle d’attribution différent pour celui-ci, tel que [!UICONTROL Première touche], et une autre [!UICONTROL fenêtre de recherche], telle que [!UICONTROL 30 jours].

## Créer plusieurs dimensions à partir d’un champ de schéma

## Utiliser des entiers comme dimensions

34:00

Inclusion du cumul