---
title: Cas dʼutilisation des vues de données dans Customer Journey Analytics
description: Découvrez plusieurs cas dʼutilisation qui montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: e40232916ee93136583d9ecf460367ecb7df5c8b
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 47%

---

# Cas dʼutilisation des vues de données

Ces cas dʼutilisation montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics.

## 1. Création d’une mesure à partir d’un champ de schéma de chaîne

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

Un autre exemple consiste à utiliser l’identifiant visiteur, une dimension, comme mesure pour déterminer le nombre d’identifiants visiteur de votre société.

## 2. Utiliser des entiers comme dimensions

Auparavant, les entiers étaient automatiquement traités comme des mesures dans CJA. Désormais, les données numériques (y compris les événements personnalisés dʼAdobe Analytics) peuvent être traités comme des dimensions. Voici un exemple :

1. Faites glisser lʼentier [!UICONTROL call_length_min] vers la section [!UICONTROL Dimensions] sous [!UICONTROL Composants inclus] :

   ![](assets/integers.png)

1. Vous pouvez maintenant ajouter lʼoption [!UICONTROL Regroupement des valeurs] afin de présenter cette dimension de manière regroupée dans le compte rendu des performances. (Sans regroupement, chaque instance de cette dimension sʼaffiche sous la forme dʼun élément de ligne dans le compte rendu des performances Workspace.)

   ![](assets/bucketing.png)

## 3. Utiliser les dimensions numériques comme &quot;mesures&quot; dans les diagrammes de flux

Vous pouvez utiliser une dimension numérique pour obtenir des &quot;mesures&quot; dans votre visualisation [!UICONTROL  Flux].

1. Sur l’onglet Vues de données [Composants](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) , faites glisser le champ de schéma [!UICONTROL Canaux marketing] dans la zone [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
2. Dans les rapports Workspace, ce flux affiche [!UICONTROL Canaux marketing] qui se dirigent vers [!UICONTROL Commandes] :

![](assets/flow.png)

## 4. Effectuer le filtrage des sous-événements

Vous pouvez filtrer les événements pour n’afficher que ce que vous souhaitez voir. Par exemple, utilisez la fonctionnalité d’inclusion/exclusion dans les vues de données pour vous concentrer uniquement sur les produits qui ont généré des ventes de plus de 50 dollars. Ainsi, si vous avez une commande qui comprend un achat de produit de 50 dollars et un achat de produit de 25 dollars, nous ne supprimerions que l’achat de produit de 25 dollars, et non la commande entière.

1. Sur l’onglet Vues de données [Composants](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) , faites glisser le champ de schéma [!UICONTROL Recettes] dans la zone [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
1. Sélectionnez la mesure et configurez les éléments suivants sur le côté droit :
a. Sous [!UICONTROL Format], sélectionnez [!UICONTROL Devise].
b. Sous [!UICONTROL Devise], sélectionnez USD.
c. Sous [!UICONTROL Inclure/Exclure des valeurs], cochez la case en regard de [!UICONTROL Définir les valeurs d’inclusion/exclusion].
d. Sous [!UICONTROL Correspondance], sélectionnez [!UICONTROL Si tous les critères sont satisfaits].
e. Sous [!UICONTROL Critères], sélectionnez [!UICONTROL est supérieur ou égal à].
f. Indiquez &quot;50&quot; comme valeur.

Ces nouveaux paramètres vous permettent d’afficher uniquement les recettes à valeur élevée et de filtrer les recettes inférieures à 50 $.

## 5. Utilisez le paramètre [!UICONTROL No Value Options]

Votre entreprise a peut-être passé du temps à former vos utilisateurs à l’exigence &quot;Non spécifié&quot; dans les rapports. La valeur par défaut dans les vues de données est &quot;Aucune valeur&quot;. Vous pouvez désormais [renommer &quot;Aucune valeur&quot; en &quot;Non spécifié&quot;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-no-value-options-settings) dans l’interface utilisateur des vues de données.

## 6. Créez plusieurs mesures avec différents paramètres [!UICONTROL Attribution]

À l’aide de la fonction [!UICONTROL Dupliquer] en haut à droite, créez plusieurs mesures de recettes avec différents paramètres d’attribution tels que [!UICONTROL Première touche], [!UICONTROL Dernière touche] et [!UICONTROL Algorithmique].

N’oubliez pas de renommer chaque mesure pour refléter les différences, telles que &quot;Recettes algorithmiques&quot; :

![](assets/algo-revenue.png)

Pour plus dʼinformations sur les autres paramètres de vues de données, voir [Création de vues de données](/help/data-views/create-dataview.md).
Pour un aperçu conceptuel des vues de données, voir [Présentation des vues de données](/help/data-views/data-views.md).