---
title: Cas dʼutilisation des vues de données dans Customer Journey Analytics
description: Découvrez plusieurs cas dʼutilisation qui montrent la flexibilité et la puissance des vues de données dans Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 684918af270a77355b7cefab4ae2e32720a71cae
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 87%

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

Vous pouvez utiliser une dimension numérique pour obtenir des « mesures » dans votre visualisation des [!UICONTROL Flux].

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

## 7. Création de rapports sur les nouvelles sessions et les sessions répétées {#new-repeat}

Vous pouvez déterminer si une session constitue bien la première session d’un utilisateur ou non, grâce au créneau de rapport que vous avez défini pour cette vue de données et à un intervalle de recherche en amont de 13 mois. Ces rapports permettent, entre autres, de répondre aux questions suivantes :

* Quel pourcentage de vos commandes provient de nouvelles sessions ou de sessions répétées ?

* Pour un canal marketing ou une campagne spécifique, ciblez-vous les nouveaux utilisateurs ou les utilisateurs récurrents ? Comment ces choix ont-ils influencé les taux de conversion ?

Trois composants rendent ces rapports possibles :

* 1 dimension : [Type de session](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=fr#optional) : cette dimension possède deux valeurs : 1) [!UICONTROL Nouveau] et 2) [!UICONTROL Récurrent]. L’élément de ligne [!UICONTROL Nouveau] comprend tous les comportements (c’est-à-dire les mesures par rapport à cette dimension) d’une session qui a été déterminée comme étant la première session définie d’une personne. Tous les autres éléments sont inclus dans l’élément de ligne [!UICONTROL Récurrent] (en supposant que tous ceux-ci appartiennent à une session). Les mesures qui ne font partie d’aucune session se retrouvent dans le compartiment « Non applicable » pour cette dimension.

* 2 mesures : [Nouvelles sessions, sessions récurrentes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional). Une nouvelle session est définie comme la première session d’une personne dans le créneau de rapport. Les sessions récurrentes correspondent au nombre de sessions qui n’étaient pas la toute première session d’une personne.

Pour accéder à ces composants, procédez comme suit :

1. Accédez à l’Éditeur de vue de données.
1. Cliquez sur l’onglet **[!UICONTROL Composants]** > **[!UICONTROL Composants standard facultatifs]** dans le rail de gauche.
1. Faites glisser ces composants dans votre vue de données.

95 % à 99 % du temps, les nouvelles sessions sont consignées avec précision. Ces exceptions sont les suivantes :

* Lorsqu’une première session s’est produite avant l’intervalle de recherche en amont de 13 mois. Cette session sera ignorée.

* Lorsqu’une session s’étend à la fois sur l’intervalle de recherche en amont et le créneau de rapport. Prenons l’exemple suivant : votre rapport couvre la période du 1er au 15 juin 2022. Votre intervalle de recherche en amont s’étend du 1er mai 2021 au 31 mai 2022. Si une session devait commencer le 30 mai 2022 et se terminer le 1er juin 2022, car la session est incluse dans l’intervalle de recherche en amont, toutes les sessions dans l’intervalle de création de rapports sont comptabilisées comme des sessions de retour.

## Utilisation de la fonctionnalité Date et heure {#date}

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Exemples de cas d’utilisation:

* Date : Une agence de voyages collecte la date de départ pour les voyages comme champ dans ses données. Ils souhaitent obtenir un rapport qui compare la variable [!UICONTROL Jour de la semaine] pour toutes les dates de départ collectées afin de déterminer laquelle est la plus populaire. Ils aimeraient faire de même pour [!UICONTROL Mois de l’année].

* Date-Time : Une société de vente au détail collecte le temps de chacun de ses achats de point de vente en magasin (POS). Au cours d’un mois donné, ils souhaitent comprendre les périodes d’achat les plus animées par [!UICONTROL Heure de la journée].

>[!MORELIKETHIS]
>[Date et heure dans le paramètre du composant Format](/help/data-views/component-settings/format.md)

