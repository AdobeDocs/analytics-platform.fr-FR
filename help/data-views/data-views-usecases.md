---
title: Cas dʼutilisation des vues de données dans Customer Journey Analytics
description: Découvrez plusieurs cas dʼutilisation qui montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 8492a400d7402a95ba98dc0800970b25a1d7d473
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 91%

---

# Cas dʼutilisation des vues de données

Ces cas dʼutilisation montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics.

## 1. Création dʼune mesure à partir dʼun champ de schéma de chaîne {#string}

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

Un autre exemple consiste à utiliser lʼidentifiant visiteur, une dimension, en tant que mesure pour déterminer le nombre dʼidentifiants visiteur de votre société.

## 2. Utilisation de nombres entiers en tant que dimensions {#integers}

Auparavant, les entiers étaient automatiquement traités comme des mesures dans CJA. Désormais, les données numériques (y compris les événements personnalisés dʼAdobe Analytics) peuvent être traités comme des dimensions. Voici un exemple :

1. Faites glisser lʼentier [!UICONTROL call_length_min] vers la section [!UICONTROL Dimensions] sous [!UICONTROL Composants inclus] :

   ![](assets/integers.png)

1. Vous pouvez maintenant ajouter lʼoption [!UICONTROL Regroupement des valeurs] afin de présenter cette dimension de manière regroupée dans le compte rendu des performances. (Sans regroupement, chaque instance de cette dimension sʼaffiche sous la forme dʼun élément de ligne dans le compte rendu des performances Espace de travail.)

   ![](assets/bucketing.png)

## 3. Utilisation des dimensions numériques en tant que « mesures » dans les diagrammes de flux {#numeric}

Vous pouvez utiliser une dimension numérique pour obtenir des « mesures » dans votre visualisation des [!UICONTROL Flux].

1. Sous lʼonglet [Composants](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#configure-component-settings) dans les Vues de données, faites glisser le champ de schéma [!UICONTROL Canaux marketing] dans la zone [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
2. Dans le compte rendu des performances Espace de travail, ce flux affiche les [!UICONTROL Canaux marketing] qui convergent vers les [!UICONTROL Commandes] :

![](assets/flow.png)

## 4. Filtrage des sous-événements {#sub-event}

Cette fonctionnalité s’applique spécifiquement aux champs basés sur des tableaux. La fonctionnalité dʼinclusion/exclusion vous permet d’effectuer un filtrage au niveau des sous-événements, tandis que les filtres (segments) créés dans le créateur de filtres fournissent uniquement un filtrage au niveau des événements. Vous pouvez donc effectuer un filtrage des sous-événements à l’aide de la fonctionnalité dʼinclusion/exclusion dans les vues de données, puis référencer cette nouvelle mesure/dimension dans un filtre au niveau des événements.

Par exemple, utilisez la fonctionnalité dʼinclusion/exclusion dans les vues de données pour vous concentrer uniquement sur les produits qui ont généré des ventes de plus de 50 dollars. Ainsi, si vous avez une commande qui comprend un achat de produit pour 50 dollars et un achat de produit pour 25 dollars, nous ne supprimons que lʼachat de produit pour 25 dollars, et non la commande entière.

1. Sous lʼonglet [Composants](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings) dans les Vues de données, faites glisser le champ de schéma [!UICONTROL Chiffre dʼaffaires] dans la zone [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
1. Sélectionnez la mesure et configurez les éléments suivants sur le côté droit :
a. Sous [!UICONTROL Format], sélectionnez [!UICONTROL Devise].
b. Sous [!UICONTROL Devise], sélectionnez USD.
c. Sous [!UICONTROL Inclure/Exclure des valeurs], cochez la case en regard de [!UICONTROL Définir des valeurs dʼinclusion/exclusion].
d. Sous [!UICONTROL Correspond à], sélectionnez [!UICONTROL Si tous les critères sont remplis].
e. Sous [!UICONTROL Critères], sélectionnez [!UICONTROL Est supérieur ou égal à].
f. Indiquez « 50 » comme valeur.

Ces nouveaux paramètres vous permettent dʼafficher uniquement les chiffres dʼaffaires de grande valeur et de filtrer ceux inférieurs à 50 $.

## 5. Utilisation du paramètre [!UICONTROL Options pour Aucune valeur] {#no-value}

Les utilisateurs formés par votre entreprise sʼattendent peut-être à retrouver lʼélément de ligne « Non spécifié » dans les rapports. La valeur par défaut dans les vues de données est « Aucune valeur ». Vous pouvez désormais [renommer « Aucune valeur » en « Non spécifié »](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#configure-no-value-options-settings) dans lʼinterface utilisateur des vues de données.

Un autre exemple serait une dimension pour l’enregistrement à un programme d’abonnement. Dans ce cas, vous pouvez renommer « Aucune valeur » en « Aucun enregistrement à un programme d’abonnement ».

## 6. Création de plusieurs mesures avec différents paramètres dʼ[!UICONTROL Attribution] {#attribution}

À lʼaide de la fonction [!UICONTROL Dupliquer] dans le coin supérieur droit, créez plusieurs mesures de chiffre dʼaffaires avec différents paramètres dʼattribution tels que [!UICONTROL Première touche], [!UICONTROL Dernière touche] et [!UICONTROL Algorithmique].

Nʼoubliez pas de renommer chaque mesure afin de refléter les différences, par exemple « Chiffre dʼaffaires algorithmique » :

![](assets/algo-revenue.png)

Pour plus dʼinformations sur les autres paramètres de vues de données, voir [Création de vues de données](/help/data-views/create-dataview.md).
Pour un aperçu conceptuel des vues de données, voir [Présentation des vues de données](/help/data-views/data-views.md).

## 7. Création de rapports de session et de session de retour {#new-repeat}

Vous pouvez déterminer si une session est effectivement la première session d’un utilisateur ou d’une session de retour, en fonction de la fenêtre de rapport que vous avez définie pour cette vue de données et d’un intervalle de recherche en amont de 13 mois. Ces rapports permettent, entre autres, de répondre aux questions suivantes :

* Quel pourcentage de vos commandes provient de sessions nouvelles ou de retour ?

* Pour un canal marketing ou une campagne spécifique, ciblez-vous les nouveaux utilisateurs ou les utilisateurs récurrents ? Comment ce choix influence-t-il les taux de conversion ?

Une dimension et deux mesures facilitent ce reporting :

* [Type de session](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=fr#optional) - Cette dimension a deux valeurs : 1) [!UICONTROL Nouveau] et 2) [!UICONTROL Renvoi]. L’élément de ligne [!UICONTROL Nouveau] comprend tous les comportements (c’est-à-dire les mesures par rapport à cette dimension) d’une session qui a été déterminée comme étant la première session définie d’une personne. Tous les autres éléments sont inclus dans l’élément de ligne [!UICONTROL Récurrent] (en supposant que tous ceux-ci appartiennent à une session). Les mesures qui ne font partie d’aucune session se retrouvent dans le compartiment « Non applicable » pour cette dimension.

* [Nouvelles sessions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional). La mesure Nouvelles sessions est définie comme la première session d’une personne définie dans la fenêtre de création de rapports.

* [Sessions de retour](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) La mesure Sessions de retour correspond au nombre de sessions qui n’ont pas été la toute première session d’une personne.—>

Pour accéder à ces composants :

1. Accédez à l’Éditeur de vue de données.
1. Cliquez sur l’onglet **[!UICONTROL Composants]** > **[!UICONTROL Composants standard facultatifs]** dans le rail de gauche.
1. Faites glisser ces composants dans votre vue de données.

Dans l’immense majorité des cas, les nouvelles sessions sont rapportées avec exactitude. Ces exceptions sont les suivantes :

* Lorsqu’une première session s’est produite avant l’intervalle de recherche en amont de 13 mois. Cette session sera ignorée.

* Lorsqu’une session s’étend à la fois sur l’intervalle de recherche en amont et le créneau de rapport. Prenons l’exemple suivant : votre rapport couvre la période du 1er au 15 juin 2022. Votre intervalle de recherche en amont s’étend du 1er mai 2021 au 31 mai 2022. Si une session devait commencer le 30 mai 2022 et se terminer le 1er juin 2022, toutes les sessions du créneau de rapport seraient comptabilisées comme des sessions récurrentes, car la session serait incluse dans l’intervalle de recherche en amont.

## Utiliser la fonctionnalité Date et Date et heure {#date}

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de tests limités.

Les schémas d’Adobe Experience Platform contiennent des champs [!UICONTROL Date] et [!UICONTROL Date et heure]. Les vues de données CJA prennent désormais en charge ces champs. Lorsque vous faites glisser ces champs dans une vue de données en tant que dimension, vous pouvez spécifier leur [format](/help/data-views/component-settings/format.md). Ce paramètre de format détermine l’affichage des champs dans les rapports. Par exemple :

* Pour le format de date, si vous sélectionnez **[!UICONTROL Jour]** dans le format **[!UICONTROL Jour, mois, année]**, la date s’affiche de la manière suivante dans les rapports : 23 août 2022.

* Pour le format de date et heure, si vous sélectionnez **[!UICONTROL Minute de la journée]** dans le format **[!UICONTROL Heure:minute]**, l’heure s’affiche de la manière suivante : 20:20.

### Exemples de cas d’utilisation :

* Date : une agence de voyages collecte les dates de départ des voyages et les enregistre dans un champ dans leurs données. Ils souhaitent déterminer le jour de la semaine le plus propice aux départs en voyage. Ils vont donc établir un rapport comparant le [!UICONTROL Jour de la semaine] de toutes les dates de départ collectées. Ils souhaitent faire de même pour le [!UICONTROL Mois de l’année].

* Date et heure : une société de vente au détail collecte l’heure de chacun des achats effectués dans ses points de vente (POS). Sur un mois donné, ils souhaitent déterminer les périodes de plus forte affluence en fonction de l’[!UICONTROL Heure de la journée].

>[!MORELIKETHIS]
>[Date et Date et heure dans le paramètre du composant Format](/help/data-views/component-settings/format.md).

