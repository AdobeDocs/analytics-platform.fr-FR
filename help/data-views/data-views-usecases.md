---
title: Cas dʼutilisation des vues de données dans Customer Journey Analytics
description: Découvrez plusieurs cas dʼutilisation qui montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: 3553a6a684bc2cd015d1b2ad6a3b02987d6d6bb2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 90%

---

# Cas dʼutilisation des vues de données

Ces cas dʼutilisation montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics.

## Création dʼune mesure Commandes à partir dʼun champ de schéma pageTitle (chaîne)

Par exemple, lors de la création dʼune vue de données, vous pouvez créer une mesure [!UICONTROL Commandes] à partir dʼun champ de schéma [!UICONTROL pageTitle] qui est une chaîne. Voici la procédure à suivre :

1. Dans lʼonglet Composants, faites glisser [!UICONTROL pageTitle] vers la section [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
   ![](assets/use-case1a.png)
1. Maintenant, mettez en surbrillance la mesure que vous venez de faire glisser et renommez-la sous [!UICONTROL Paramètres du composant] sur la droite :
   ![](assets/orders.png)
1. Ouvrez la boîte de dialogue [!UICONTROL Valeurs dʼinclusion/exclusion] sur la droite et effectuez les actions suivantes :
   ![](assets/orders2.png)

   Lʼexpression « confirmation » indique quʼil sʼagit dʼune commande. Après lʼinspection de tous les titres de page où ces critères sont remplis, un « 1 » est comptabilisé pour chaque instance. Une nouvelle mesure est ainsi créée (il ne sʼagit pas dʼune mesure calculée). Une mesure qui contient des valeurs dʼinclusion/exclusion peut être utilisée partout où toute autre mesure peut être utilisée. Elle fonctionne avec Attribution IQ, les filtres et partout où vous pouvez utiliser des mesures standard.
1. Vous pouvez également définir un modèle dʼattribution pour cette mesure, tel que [!UICONTROL Dernière touche], avec un [!UICONTROL intervalle de recherche en amont] de [!UICONTROL Session].
Vous pouvez également créer une autre mesure [!UICONTROL Commandes] à partir du même champ et définir un modèle dʼattribution différent pour celui-ci, tel que [!UICONTROL Première touche], et un autre [!UICONTROL intervalle de recherche en amont], tel que [!UICONTROL 30 jours].

## Utilisation de nombres entiers en tant que dimensions

Auparavant, les entiers étaient automatiquement traités comme des mesures dans CJA. Désormais, les données numériques (y compris les événements personnalisés dʼAdobe Analytics) peuvent être traités comme des dimensions. Voici un exemple :

1. Faites glisser lʼentier [!UICONTROL call_length_min] vers la section [!UICONTROL Dimensions] sous [!UICONTROL Composants inclus] :

   ![](assets/integers.png)

1. Vous pouvez maintenant ajouter lʼoption [!UICONTROL Regroupement des valeurs] afin de présenter cette dimension de manière regroupée dans le compte rendu des performances. (Sans regroupement, chaque instance de cette dimension sʼaffiche sous la forme dʼun élément de ligne dans le compte rendu des performances Workspace.)

   ![](assets/bucketing.png)

## Utiliser les dimensions numériques comme &quot;mesures&quot; dans les diagrammes de flux

Vous pouvez utiliser une dimension numérique pour obtenir des &quot;mesures&quot; dans votre visualisation [!UICONTROL  Flux]. L’exemple ci-dessous illustre les [!UICONTROL canaux marketing] qui se dirigent vers [!UICONTROL Commandes] :

![](assets/flow.png)

## Inclure ou exclure des valeurs de mesure

Pour plus dʼinformations sur les autres paramètres de vues de données, voir [Création de vues de données](/help/data-views/create-dataview.md).
Pour un aperçu conceptuel des vues de données, voir [Présentation des vues de données](/help/data-views/data-views.md).