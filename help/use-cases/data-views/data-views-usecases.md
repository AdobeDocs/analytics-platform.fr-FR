---
title: Cas dʼutilisation des vues de données dans Customer Journey Analytics
description: Découvrez plusieurs cas dʼutilisation qui montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 629935d66b0f2c5731806a68cc2fcda5fb11fc9a
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 33%

---

# Cas dʼutilisation des vues de données

Ces cas d’utilisation illustrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics.

## Utilisation des mesures de dimensions de liaison

Pour plus d’informations, consultez le cas d’utilisation des mesures de dimensions de liaison [ .](binding-dimensions-metrics.md)

## Utiliser des données de résumé

Pour plus d’informations, voir le cas d’utilisation [Utiliser des données récapitulatives](summary-data.md) .

## Cas d’utilisation de l’extension BI

Consultez les [cas d’utilisation de l’extension BI](bi-extension-usecases.md) pour savoir comment réaliser un certain nombre de cas d’utilisation à l’aide de l’extension Customer Journey Analytics BI.

## Création d’une mesure à partir d’un champ de schéma de chaîne {#string}

Par exemple, lors de la création d’une vue de données, vous pouvez créer une mesure [!UICONTROL Commandes] à partir d’un champ de schéma [!UICONTROL Titre de page] qui est une chaîne.



1. Sur l’onglet **[!UICONTROL Composants]**, faites glisser le **[!UICONTROL Titre de page]** dans la section **[!UICONTROL Mesures]** sous [!UICONTROL Composants inclus].
1. Mettez en surbrillance la mesure que vous venez de faire glisser et renommez-la `Orders` dans les **[!UICONTROL paramètres des composants]** sur
1. Ouvrez la section **[!UICONTROL Inclure/Exclure les valeurs]** et spécifiez les éléments suivants :
   1. Activez **[!UICONTROL Définir les valeurs d’exclusion d’inclusion]**.
   1. Sélectionnez **[!UICONTROL Si tous les critères sont satisfaits]** depuis **[!UICONTROL Correspondance]**.
   1. Spécifiez `confirmation`. Ce texte pour page_title indique que cette page est liée au placement d’une commande. Après avoir passé en revue tous les titres de page pour lesquels ces critères sont remplis, un `1` sera comptabilisé pour chaque instance. Le résultat est une nouvelle mesure (et non une mesure calculée). Une mesure qui contient des valeurs incluses/exclues peut être utilisée partout où toute autre mesure peut être utilisée. Elle fonctionne avec Attribution IQ, les filtres et partout où vous pouvez utiliser des mesures standard.

   ![Dimension à la mesure](../assets/string-to-metric.gif){width=100%}
1. Vous pouvez également définir un modèle dʼattribution pour cette mesure, tel que [!UICONTROL Dernière touche], avec un [!UICONTROL intervalle de recherche en amont] de [!UICONTROL Session].
Vous pouvez également créer une autre mesure [!UICONTROL Commandes] à partir du même champ et spécifier un modèle d’attribution différent. Comme [!UICONTROL Première touche] et une [!UICONTROL fenêtre de recherche en amont] différente, comme [!UICONTROL 30 jours].

Un autre exemple consiste à utiliser l’ID de personne, une dimension, comme mesure pour déterminer le nombre d’ID de personne de votre société.

## Utilisation de nombres entiers en tant que dimensions {#integers}

Auparavant, les entiers étaient automatiquement traités comme des mesures dans Customer Journey Analytics. Désormais, les données numériques (y compris les événements personnalisés dʼAdobe Analytics) peuvent être traités comme des dimensions. Voici un exemple :



1. Faites glisser l’entier **[!UICONTROL Durée]** dans la section **[!UICONTROL Dimensions]** sous [!UICONTROL Composants inclus] :
1. Vous pouvez maintenant ajouter lʼoption **[!UICONTROL Regroupement des valeurs]** afin de présenter cette dimension de manière regroupée dans le compte rendu des performances. Sans regroupement des segments, chaque instance de cette dimension apparaîtra sous la forme d’un élément de ligne dans les rapports Workspace.
   ![Entier à la dimension](../assets/integer-to-dimension.gif){width=100%}


## Utiliser des dimensions numériques comme mesures dans les diagrammes de flux {#numeric}

Vous pouvez utiliser une dimension numérique pour incorporer des mesures dans votre visualisation [!UICONTROL  Flux].

1. Sous lʼonglet [Composants](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/create-dataview) dans les Vues de données, faites glisser le champ de schéma [!UICONTROL Canaux marketing] dans la zone [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
2. Dans le compte rendu des performances Espace de travail, ce flux affiche les [!UICONTROL Canaux marketing] qui convergent vers les [!UICONTROL Commandes] :

![Flux de canal marketing depuis les emails vers la sortie/les commandes.](../assets/flow.png)

## Filtrage des sous-événements {#sub-event}

Cette fonctionnalité s’applique spécifiquement aux champs basés sur des tableaux. La fonctionnalité d’inclusion/exclusion permet de filtrer au niveau des sous-événements, tandis que les filtres (segments) créés dans le créateur de filtres ne permettent de filtrer qu’au niveau des événements. Ainsi, vous pouvez effectuer un filtrage des sous-événements à l’aide de l’option inclure/exclure dans les vues de données, puis référencer cette nouvelle mesure/dimension dans un filtre au niveau de l’événement.

Par exemple, utilisez la fonctionnalité d’inclusion/exclusion dans les vues de données pour vous concentrer uniquement sur les produits qui ont généré des ventes de plus de 50 €. Ainsi, si vous avez une commande qui comprend un achat de produit de 50 € et un achat de produit de 25 €, la fonctionnalité d’inclusion/exclusion supprime l’achat de produit de 25 €, et non la commande entière.

1. Sous lʼonglet [Composants](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/create-dataview) dans les Vues de données, faites glisser le champ de schéma **[!UICONTROL Chiffre dʼaffaires]** dans la zone **[!UICONTROL Mesures]** sous [!UICONTROL Composants inclus].
1. Sélectionnez la mesure et configurez les éléments suivants sur le côté droit :
a. Sous **[!UICONTROL Format]**, sélectionnez **[!UICONTROL Devise]**.
b. Sous **[!UICONTROL Currency]**, sélectionnez **[!UICONTROL USD]**.
c. Sous **[!UICONTROL Inclure/Exclure des valeurs]**, cochez la case en regard de **[!UICONTROL Définir des valeurs dʼinclusion/exclusion]**.
d. Sous **[!UICONTROL Correspond à]**, sélectionnez **[!UICONTROL Si tous les critères sont remplis]**.
e. Sous **[!UICONTROL Critères]**, sélectionnez **[!UICONTROL Est supérieur ou égal à]**.
f. Spécifiez `50` comme valeur.

Ces nouveaux paramètres vous permettent dʼafficher uniquement les chiffres dʼaffaires de grande valeur et de filtrer ceux inférieurs à 50 $.

## Utilisation du paramètre [!UICONTROL Aucune option de valeur] {#no-value}

Votre entreprise a peut-être passé du temps à former vos utilisateurs à l’exigence &quot;Non spécifié&quot; pour les dimensions dans les rapports. La valeur par défaut des dimensions dans les vues de données est &quot;Aucune valeur&quot;. Cependant, vous pouvez spécifier, par dimension, la manière dont Aucune valeur ne doit être signalée. Voir Options Aucune valeur pour un composant de dimension.

![Aucune option de valeur](../assets/no-value-options.gif){width=100%}


## Création de plusieurs mesures avec différents paramètres d’attribution {#attribution}

À l’aide de la fonction **[!UICONTROL Dupliquer]** située en haut à droite, pour créer plusieurs mesures de recettes totales avec différents paramètres d’attribution tels que **[!UICONTROL Première touche]**, **[!UICONTROL Dernière touche]** et **[!UICONTROL Algorithmique]**.

N’oubliez pas de renommer chaque mesure pour refléter les différences, telles que `Total Revenue (Algorithmic)`.

![Dupliquer la mesure pour différents paramètres d’attribution](../assets/duplicate-metric-for-attribution.gif){width=100%}

Pour plus dʼinformations sur les autres paramètres de vues de données, voir [Création de vues de données](/help/data-views/create-dataview.md).
Pour un aperçu conceptuel des vues de données, voir [Présentation des vues de données](/help/data-views/data-views.md).

## Création de rapports de session et de session de retour {#new-repeat}

Vous pouvez déterminer si une session est effectivement la première session d’un utilisateur ou une session de retour. En fonction de la fenêtre de rapport que vous avez définie pour cette vue de données et d’un intervalle de recherche en amont de 13 mois. Ces rapports permettent, entre autres, de répondre aux questions suivantes :

* Quel pourcentage de vos commandes provient de nouvelles sessions ou de sessions récurrentes ?

* Pour un canal marketing ou une campagne spécifique, ciblez-vous les nouveaux utilisateurs ou les utilisateurs récurrents ? Comment ce choix influence-t-il les taux de conversion ?

Une dimension et deux mesures facilitent cette création de rapports :

* [Type de session](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference) - Cette dimension a deux valeurs : [!UICONTROL New] et [!UICONTROL Returning]. L’élément de ligne [!UICONTROL New] inclut tous les comportements (c’est-à-dire les mesures par rapport à cette dimension) d’une session qui a été déterminée comme étant la première session définie par une personne. Tous les autres éléments sont inclus dans l’élément de ligne [!UICONTROL Récurrent] (en supposant que tous ceux-ci appartiennent à une session). Les mesures qui ne font partie d’aucune session se retrouvent dans le compartiment « Non applicable » pour cette dimension.

* [Premières sessions](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference). La mesure Premières sessions est définie comme la première session d’une personne définie dans la fenêtre de création de rapports.

* [Sessions de retour](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference) La mesure Sessions de retour est le nombre de sessions qui n’étaient pas la première session d’une personne.—>

Pour accéder aux composants :

1. Accédez à l’Éditeur de vue de données.
1. Sélectionnez l’onglet **[!UICONTROL Composants]** , puis **[!UICONTROL Composants standard]** dans le rail de gauche.
1. Faites glisser les composants **[!UICONTROL Type de session]**, **[!UICONTROL Premières sessions]** et **[!UICONTROL Sessions de retour]** dans votre vue de données.

Les nouvelles sessions sont presque toujours reportées avec précision. Ces exceptions sont les suivantes :

* Lorsqu’une première session s’est produite avant l’intervalle de recherche en amont de 13 mois. <br/>Cette session est ignorée.

* Lorsqu’une session s’étend à la fois sur l’intervalle de recherche en amont et le créneau de rapport. <br/>Par exemple, vous exécutez un rapport du 1er au 15 juin 2022. La période de recherche arrière s’étendrait du 1er mai 2021 au 31 mai 2022. Si une session commence le 30 mai 2022 et se termine le 1er juin 2022, la session est incluse dans l’intervalle de recherche en amont. Et toutes les sessions dans la fenêtre de création de rapports sont comptabilisées comme des sessions de retour.

## Utiliser la fonctionnalité Date et Date et heure {#date}

Les schémas d’Adobe Experience Platform contiennent des champs [!UICONTROL Date] et [!UICONTROL Date et heure]. Les vues de données du Customer Journey Analytics prennent désormais en charge ces champs. Lorsque vous faites glisser ces champs dans une vue de données en tant que dimension, vous pouvez spécifier leur [format](/help/data-views/component-settings/format.md). Ce paramètre de format détermine l’affichage des champs dans les rapports. Par exemple :

* Pour le format de date, si vous sélectionnez **[!UICONTROL Jour]** dans le format **[!UICONTROL Jour, mois, année]**, la date s’affiche de la manière suivante dans les rapports : 23 août 2022.

* Pour le format de date et heure, si vous sélectionnez **[!UICONTROL Minute de la journée]** dans le format **[!UICONTROL Heure:minute]**, l’heure s’affiche de la manière suivante : 20:20.

Les dates postérieures au 1er janvier 1900 (à l’exception du 1er janvier 1970) et les valeurs de date-time postérieures au 1er janvier 2000 00:00:00 sont prises en charge.

### Cas d’utilisation de date et date-heure

* Date : une agence de voyages collecte la date de départ pour les voyages sous la forme d’un champ dans ses données. La société souhaite obtenir un rapport qui compare le [!UICONTROL Jour de la semaine] pour toutes les dates de départ collectées afin de déterminer laquelle est la plus populaire. Et l&#39;entreprise souhaite faire de même pour le [!UICONTROL mois de l&#39;année].

* Date-Time : une société de vente au détail collecte l’heure de chacun de ses achats de point de vente en magasin. Au cours d’un mois donné, la société souhaite connaître les périodes d’achats les plus fréquentées par [!UICONTROL Heure de la journée].

>[!MORELIKETHIS]
>
>[Date et heure dans le paramètre du composant Format](/help/data-views/component-settings/format.md)
>

