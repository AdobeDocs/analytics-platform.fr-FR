---
title: Cas dʼutilisation des vues de données dans Customer Journey Analytics
description: Découvrez plusieurs cas dʼutilisation qui montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 80f31a77df68dca91c1f9f5a0d521b0ea7d450ce
workflow-type: ht
source-wordcount: '979'
ht-degree: 100%

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

1. Sous lʼonglet [Composants](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr#configure-component-settings) dans les Vues de données, faites glisser le champ de schéma [!UICONTROL Chiffre dʼaffaires] dans la zone [!UICONTROL Mesures] sous [!UICONTROL Composants inclus].
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

## 7. Nouveau rapport de session {#new-repeat}

Vous pouvez déterminer si une session constitue bien la première session d’un utilisateur ou non, grâce au créneau de rapport que vous avez défini pour cette vue de données et à un intervalle de recherche en amont de 13 mois. Ces rapports permettent, entre autres, de répondre aux questions suivantes :

* Quel pourcentage de vos commandes provient de nouvelles sessions ?

* Pour un canal marketing ou une campagne spécifique, ciblez-vous les nouveaux utilisateurs ? Comment ce choix influence-t-il les taux de conversion ?

Une mesure facilite la création de rapports suivante :

<!--* 1 dimension: [Session type](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) - This dimension has two values: 1) [!UICONTROL New] and 2) [!UICONTROL Returning]. The [!UICONTROL New] line item includes all of the behavior (i.e. metrics against this dimension) from a session that has been determined to be a person's defined first session. Everything else is included in the [!UICONTROL Returning] line item (assuming everything belongs to a session). Where metrics are not part of any session, they fall into the 'Not applicable' bucket for this dimension.-->

* [Nouvelles sessions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=fr#optional). Une nouvelle session est définie comme la première session d’une personne dans le créneau de rapport.

   <!--* [Return sessions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) Return sessions is the number of sessions that were not a person's first-ever session.-->

Pour accéder à ce composant :

1. Accédez à l’Éditeur de vue de données.
1. Cliquez sur l’onglet **[!UICONTROL Composants]** > **[!UICONTROL Composants standard facultatifs]** dans le rail de gauche.
1. Faites glisser ces composants dans votre vue de données.

Dans l’immense majorité des cas, les nouvelles sessions sont rapportées avec exactitude. Ces exceptions sont les suivantes :

* Lorsqu’une première session s’est produite avant l’intervalle de recherche en amont de 13 mois. Cette session sera ignorée.

* Lorsqu’une session s’étend à la fois sur l’intervalle de recherche en amont et le créneau de rapport. Prenons l’exemple suivant : votre rapport couvre la période du 1er au 15 juin 2022. Votre intervalle de recherche en amont s’étend du 1er mai 2021 au 31 mai 2022. Si une session devait commencer le 30 mai 2022 et se terminer le 1er juin 2022, toutes les sessions du créneau de rapport seraient comptabilisées comme des sessions récurrentes, car la session serait incluse dans l’intervalle de recherche en amont.

<!--## Use the Date and Date-Time functionality {#date}

Schemas in Adobe Experience Platform contain [!UICONTROL Date] and [!UICONTROL Date-Time] fields. CJA data views now support these fields. When you drag these fields into a data view as a dimension, you can specify their [format](/help/data-views/component-settings/format.md). This format setting determines how the fields are displayed in reporting. For example:

* For the Date format, if you select **[!UICONTROL Day]** with the format **[!UICONTROL Month, Day, Year]**, an example output in reporting might look like: August 23, 2022.

* For the Date-Time format, if you select **[!UICONTROL Minute of Day]** with the format **[!UICONTROL Hour:Minute]**, your output might look like: 20:20.

### Example use cases:

* Date: A travel company is collecting the departure date for trips as a field in their data. They would like to have a report which compares the [!UICONTROL Day of Week] for all departure dates collected to understand which is most popular. They would like to do the same for [!UICONTROL Month of Year].

* Date-Time: A retail company is collecting the time for each of their in-store point-of-sale (POS) purchases. Over a given month, they would like to understand the busiest shopping periods by [!UICONTROL Hour of Day].

>[!MORELIKETHIS]
>[Date and Date-Time in the Format component setting](/help/data-views/component-settings/format.md)-->

