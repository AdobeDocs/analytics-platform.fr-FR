---
description: Présentation de l’utilisation de modèles par défaut dans Analysis Workspace.
title: Utiliser les modèles
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: 34b94eeeeb501f6c0deb982351b7c65e0a97bc68
workflow-type: tm+mt
source-wordcount: '18106'
ht-degree: 81%

---

# Utiliser les modèles

Les modèles (ou modèles d’entreprise) d’Analysis Workspace fournissent des informations rapides sur les scénarios de création de rapports les plus courants. Voici quelques exemples de questions auxquelles vous pouvez répondre à l’aide de modèles :

* Nombre de visiteurs sur votre site
* Nombre de ces visiteurs qui sont uniques (comptabilisés une seule fois)
* Leur acheminement vers le site (s’ils ont suivi un lien ou se sont rendus directement dessus)
* Mots-clés utilisés par les visiteurs pour rechercher le contenu du site
* Leur durée passée sur une page donnée ou sur le site entier
* Liens sur lesquels les visiteurs ont cliqué et le moment où ils ont quitté le site
* Les canaux marketing les plus efficaces pour générer des recettes ou des événements de conversion
* Le temps passé à regarder une vidéo
* Les navigateurs et appareils utilisés pour consulter votre site

Les informations suivantes décrivent comment accéder aux modèles et les utiliser à partir de l’onglet [!UICONTROL Modèles] dans Analysis Workspace.

## Accès et exécution d’un modèle

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**].

   ![Onglets Modèles](assets/view-prebuilt-templates.png)

1. Dans la section [!UICONTROL **Modèles**], sélectionnez l’un des onglets suivants :

   * **[!UICONTROL Modèles Adobe]** : affiche tous les modèles fournis par Adobe.

   * **[!UICONTROL _login_company_name _templates]**: affiche tous les modèles d’entreprise qui ont été créés pour votre organisation.

     Les modèles d’entreprise ne peuvent être créés que par un administrateur. Pour plus d’informations sur la création d’un modèle d’entreprise, voir [Création et gestion de modèles](/help/analysis-workspace/templates/create-templates.md).

1. Utilisez l’une des options suivantes pour modifier l’affichage des modèles disponibles :

   * Choisissez d’afficher les modèles en mode Colonnes ou Carte en sélectionnant l’icône Mode Colonnes ![icône Mode Colonnes](assets/column-view-icon.png) ou Mode Carte ![icône Mode Carte](assets/card-view-icon.png).

   * Lors de l’utilisation du mode Carte ![icône du mode Carte](assets/card-view-icon.png), choisissez l’un des ordres de tri suivants : **[!UICONTROL Le plus récemment utilisé]**, **[!UICONTROL Le plus populaire]**, **[!UICONTROL Alphabétique]**, **[!UICONTROL Catégoriel]**.

1. Dans le champ de recherche, commencez à saisir le nom du modèle à rechercher, puis sélectionnez-le dans la liste des modèles.

   Ou

   Sélectionnez la catégorie du modèle que vous souhaitez afficher, puis sélectionnez le modèle dans la liste des modèles.

   >[!TIP]
   >
   >Pour naviguer dans le menu à l’aide des touches fléchées, appuyez sur la touche Barre oblique (/), puis sur la touche Flèche vers le bas. Appuyez sur Entrée pour charger le modèle sélectionné.

   Pour obtenir la liste des modèles disponibles, reportez-vous à la section [Modèles disponibles](#available-templates) ci-dessous.

1. (Facultatif) Vous pouvez afficher des modèles contenant des composants qui ne sont pas disponibles dans votre vue de données. (Par défaut, les modèles ne s’affichent que s’ils utilisent des composants disponibles dans votre vue de données.)

   >[!NOTE]
   >
   >   Avant de pouvoir utiliser ces modèles, un administrateur ou une administratrice doit d’abord ajouter les libellés de contexte requis pour ces composants manquants à la vue de données. Pour plus d’informations, voir [Ajouter les composants manquants à la vue de données d’un modèle donné](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) dans [Utiliser des modèles](/help/analysis-workspace/templates/create-templates.md).

   1. Sélectionnez l’icône de filtre .

   1. Sélectionnez **[!UICONTROL Pas prêt à l’emploi]** pour afficher les modèles qui nécessitent des composants supplémentaires.

      ![Utiliser un modèle sans composants](assets/template-not-ready.png)

1. Sélectionnez le modèle pour créer un rapport basé sur le modèle que vous avez choisi.

1. (Conditionnel) Si le modèle contient des composants qui ne sont pas disponibles dans votre vue de données, la boîte de dialogue Vue de données incompatible s’affiche, indiquant que la vue de données est incompatible avec le modèle et quels composants sont manquants.

   Effectuez l’une des opérations suivantes :

   * Choisissez une autre vue de données dans le menu déroulant **[!UICONTROL Modifier la vue de données]**.

   * Sélectionnez **[!UICONTROL Continuer quand même]** pour afficher le modèle avec les composants manquants.

## Création d’un projet basé sur un modèle {#use-reports}

Un modèle peut ne pas correspondre exactement à vos besoins, mais il peut vous rapprocher. Dans ce cas, vous pouvez utiliser le modèle comme point de départ de votre projet, puis le personnaliser selon vos besoins.

Si vous quittez un modèle après avoir apporté des modifications, vous êtes invité à enregistrer ou à ignorer vos modifications. L’enregistrement des modifications dans un modèle enregistre le modèle en tant que nouveau projet.

Pour personnaliser un modèle et l’enregistrer en tant que projet :

1. Dans Customer Journey Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**].

1. Sélectionnez l’onglet [!UICONTROL **Modèles**].

1. Sélectionnez le modèle que vous souhaitez afficher. Par exemple, sous [!UICONTROL **Les plus populaires**], sélectionnez le modèle [!UICONTROL **Pages**].

   Le modèle Pages, tel qu’affiché dans Analysis Workspace, affiche deux [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Graphique à barres](/help/analysis-workspace/visualizations/bar.md) et [Numéro du résumé](/help/analysis-workspace/visualizations/summary-number-change.md)) ainsi qu’un [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La mesure utilisée est Occurrences.

   <!--update screenshot. The following is AA -->

   ![Modèle Pages](assets/pages-report.png)

1. Effectuez l’une des opérations suivantes :

   * Affichez le modèle.
   * Faites glisser un ou plusieurs filtres dans la zone de dépôt Filtre en haut. Par exemple, faites glisser le filtre [!UICONTROL **Clients mobiles**] et affichez les résultats.
   * Modifiez la période en accédant au calendrier en haut à droite.
   * Ajoutez des répartitions de dimension, faites glisser d’autres mesures et personnalisez généralement le modèle en fonction de vos besoins.

1. (Facultatif) Enregistrez le modèle en tant que projet en sélectionnant [!UICONTROL **Projet**] > [!UICONTROL **Enregistrer**].

   Le modèle est enregistré en tant que nouveau projet ; il ne modifie pas le modèle existant. Pour plus d’informations sur l’enregistrement de projets, voir [Enregistrer des projets](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Modèles disponibles

Pour accéder à tous les modèles préconfigurés disponibles, procédez comme suit :

1. Dans Adobe Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**], puis sélectionnez l’onglet [!UICONTROL **Modèles**].

   Les modèles préconfigurés sont organisés par catégorie.

   <!--add screenshot-->

1. Sélectionnez une catégorie pour afficher les modèles qu’elle contient.

   Les sections suivantes correspondent aux catégories disponibles et fournissent des informations sur chaque modèle.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

   * [[!UICONTROL ](#web-conversion)

   * [[!UICONTROL ](#web-audience)

   * [[!UICONTROL ](#web-acquisition)

   * [[!UICONTROL ](#mobile-mobile-app)

   * [[!UICONTROL ](#mobile-mobile-device-information)

   * [[!UICONTROL ](#time-parting)

   * [[!UICONTROL ](#cross-channel)

   * [[!UICONTROL ](#other-channels)

   * [[!UICONTROL ](#ajo)

### Les plus populaires {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Affichez le nombre total d’unités achetées pour toutes les commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comprendre comment les ventes unitaires augmentent ou diminuent au fil du temps. Vous pouvez appliquer un segment pour identifier les personnes ou les zones géographiques qui achètent le plus d’unités et déterminer les tendances de ces ventes unitaires au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les ventes unitaires du site avant et après le lancement de la campagne. Vous pouvez aussi comparer les ventes unitaires d’une année à l’autre pendant les fêtes.<br/>Ce modèle utilise la dimension Jour et la mesure Unités."

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Modèle de tutoriel de formation"
>abstract="Découvrez la terminologie et les étapes courantes d’Analysis Workspace pour créer votre première analyse."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identifiez les pages les plus populaires et les moins populaires."
>abstract="**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui l’intéresse le plus.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Affichez le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. "
>abstract="**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Pages vues."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Affichez le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Affichez le nombre total de visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. "
>abstract="**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs et visiteuses uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Visiteurs et visiteuses uniques. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de personnes uniques sur le site, du nombre de visites de pages et du nombre de sessions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. <br/>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs et visiteuses uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Affichez les sections les plus populaires ou les plus performantes de votre site."
>abstract="**Cela peut vous aider** à mieux comprendre quelles sections de votre site sont les plus visitées.<br>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.<br/>Ce modèle utilise la dimension Section du site et la mesure Visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite ou juste avant de visiter un certain emplacement."
>abstract="**Cela peut vous aider** à comprendre comment le trafic passe d’une page donnée à d’autres parties de votre site, et comprendre les chemins empruntés par les personnes pour atteindre une page donnée.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si la conception ou la mise en page peut être optimisée pour diriger les personnes vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser un avis. Ou évaluez si les informations de la page active sont susceptibles de fournir la direction ou les actions que les personnes recherchent lorsqu’elles arrivent des pages précédentes. Vous pouvez également déterminer si les pages qui ne s’affichent pas comme des pages précédentes ont besoin de liens plus importants vers la page actuelle.<br/>Ce modèle utilise le panneau d’éléments Suivant ou Précédent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Affichez les liens qui ont généré le plus de trafic vers votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les codes de suivi (et les liens auxquels ils sont associés) qui ont été les plus utilisés pour accéder à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster votre stratégie en fonction de l’endroit où vous ajoutez des liens à votre site.<br/>Ce modèle utilise la dimension Code de suivi et la mesure Visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Affichez le nombre de commandes par produit. Les données s’affichent sur une période donnée."
>abstract="**Cela peut vous aider** à comprendre les produits présentant la demande la plus élevée ou la plus faible.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos stratégies marketing pour promouvoir des produits hautement performants, ou améliorer ou arrêter les produits peu performants. Vous pouvez également ajuster votre inventaire de produits en fonction de votre analyse des données.<br/>Ce modèle utilise la dimension Produit et la mesure Commandes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Affichez les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut)."
>abstract="**Cela peut vous aider** à comprendre les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.<br/>Ce modèle utilise la dimension Canal Dernière touche et la mesure Visiteurs et visiteuses uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Affichez les détails sur les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut)."
>abstract="**Cela peut vous aider** à comprendre non seulement les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions, mais aussi des détails sur ces canaux marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.<br/>Ce modèle utilise la dimension Détails du canal Dernière touche et la mesure Visiteurs et visiteuses uniques. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Affichez la valeur monétaire des produits achetés dans l’ensemble des commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comprendre comment le chiffre d’affaires augmente ou diminue au fil du temps. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au chiffre d’affaires.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que projeter le chiffre d’affaires futur basé sur les tendances précédentes. Vous pouvez également ajouter une autre dimension, comme la dimension Code de suivi, pour savoir quelles campagnes génèrent le plus de chiffre d’affaires.<br/>Ce modèle utilise la dimension Jour et la mesure Chiffre d’affaires."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Affichez le nombre total d’événements d’achat. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre comment l’intérêt pour vos produits et services augmente ou diminue au fil du temps. Vous pouvez appliquer un segment pour identifier les personnes ou les zones géographiques qui passent le plus de commandes et déterminer les tendances de ces commandes au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les commandes avant et après le lancement de la campagne. Vous pouvez également comparer les commandes passées pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Commandes."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutoriel de formation**] | Découvrez la terminologie et les étapes courantes d’Analysis Workspace pour créer votre première analyse |
| [!UICONTROL **Pages**] | <!--duplicated in Engagement section--> Identifiez les pages les plus populaires et les moins populaires. <p>**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui l’intéresse le plus.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.</p><p>Ce modèle utilise la dimension Page et la mesure Pages vues .</p> |
| [!UICONTROL **Pages vues**] | <!--duplicated in Engagement section--> Affichez le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Pages vues .</p> |
| [!UICONTROL **Visites Web**] | <!--duplicated in Engagement section--> Affichez le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visites .</p> |
| [!UICONTROL **Visiteurs Web**] | <!--duplicated in Engagement section--> Affichez le nombre total de visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs et visiteuses uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visiteurs uniques .</p> |
| [!UICONTROL **Mesures clés**] | <!--duplicated in Engagement section--> Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de personnes uniques sur le site, du nombre de visites de pages et du nombre de sessions.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme évaluer le nombre moyen de pages que chaque personne a consultées lors de sa visite du site au cours d’une semaine ou d’un mois donné, et comment cela a changé à certaines périodes de l’année ou avant et après l’exécution des campagnes marketing. </p><p>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Sections du site**] | Affichez les sections les plus populaires ou les plus performantes de votre site. <p>**Cela peut vous aider** à mieux comprendre quelles sections de votre site sont les plus visitées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.</p> <p>Ce modèle utilise la dimension Section du site et la mesure Visites .</p> |
| [!UICONTROL **Page suivante et précédente**] | Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite ou juste avant de visiter un certain emplacement. <p>**Cela peut vous aider** à comprendre comment le trafic passe d’une page donnée à d’autres parties de votre site, et comprendre les chemins empruntés par les personnes pour atteindre une page donnée.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si la conception ou la mise en page peut être optimisée pour diriger les personnes vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser un avis. Ou évaluez si les informations de la page active sont susceptibles de fournir la direction ou les actions que les personnes recherchent lorsqu’elles arrivent des pages précédentes. Vous pouvez également déterminer si les pages qui ne s’affichent pas comme des pages précédentes ont besoin de liens plus importants vers la page actuelle.</p><p>Ce modèle utilise le panneau Élément suivant ou précédent.</p> |
| [!UICONTROL **Campagnes (code de suivi)**] | Affichez les liens qui ont généré le plus de trafic vers votre site. <p>**Cela peut vous aider** à mieux comprendre les codes de suivi (et les liens auxquels ils sont associés) qui ont été les plus utilisés pour accéder à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster votre stratégie en fonction de l’endroit où vous ajoutez des liens à votre site.</p><p>Ce modèle utilise la dimension Code de suivi et la mesure Visites .</p> |
| [!UICONTROL **Produits**] | Affichez le nombre de commandes par produit. Les données s’affichent sur une période donnée. <p>**Cela peut vous aider** à comprendre les produits présentant la demande la plus élevée ou la plus faible.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos stratégies marketing pour promouvoir des produits hautement performants, ou améliorer ou arrêter les produits peu performants. Vous pouvez également ajuster votre inventaire de produits en fonction de votre analyse des données.</p><p>Ce modèle utilise la dimension Produit et la mesure Commandes .</p> |
| [!UICONTROL **Canal marketing Dernière touche**] | Affichez les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à comprendre les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.</p><p>Ce modèle utilise la dimension Canal Dernière touche et la mesure Visiteurs uniques .</p> |
| [!UICONTROL **Détails du canal marketing Dernière touche**] | Affichez les détails sur les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à comprendre non seulement les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions, mais aussi des détails sur ces canaux marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.</p><p>Ce modèle utilise la dimension Détails du canal Dernière touche et la mesure Visiteurs uniques .</p> |
| [!UICONTROL **Recettes**] | <!--duplicated in Web Conversion section-->Affichez la valeur monétaire des produits achetés dans l’ensemble des commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures.<p>**Cela peut vous aider** à comprendre comment le chiffre d’affaires augmente ou diminue au fil du temps. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au chiffre d’affaires.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que projeter le chiffre d’affaires futur basé sur les tendances précédentes. Vous pouvez également ajouter une autre dimension, comme la dimension Code de suivi, pour savoir quelles campagnes génèrent le plus de chiffre d’affaires.</p><p>Ce modèle utilise la dimension Jour et la mesure Revenus .</p> |
| [!UICONTROL **Commandes**] | <!--duplicated in Web Conversion section-->Affichez le nombre total d’événements d’achat. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment l’intérêt pour vos produits et services augmente ou diminue au fil du temps. Vous pouvez appliquer un segment pour identifier les personnes ou les zones géographiques qui passent le plus de commandes et déterminer les tendances de ces commandes au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les commandes avant et après le lancement de la campagne. Vous pouvez également comparer les commandes passées pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Commandes .</p> |

### Web : engagement {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Affichez la durée moyenne des visiteurs et visiteuses sur votre site lors de chaque visite. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et visiteuses et leur temps passé sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer si les modifications apportées à votre site amènent les visiteurs et visiteuses à passer plus de temps sur le site.<br/>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Affichez la durée moyenne des utilisateurs et utilisatrices sur le site avant un événement de succès."
>abstract="**Cela peut vous aider** à mieux comprendre le temps nécessaire aux visiteurs et visiteuses pour effectuer l’action souhaitée, comme effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des personnes à atteindre rapidement un événement de succès.<br/>Ce modèle utilise la dimension Durée avant événement et la mesure Visiteurs et visiteuses uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Affichez les endroits où les personnes abandonnent ou poursuivent une séquence de pages prédéfinie."
>abstract="**Cela peut vous aider** à mieux comprendre où les personnes sortent du parcours d’utilisateur ou d’utilisatrice.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les taux de conversion par le biais de processus spécifiques sur votre site (tels qu’un processus d’achat ou d’enregistrement) ou analyser les corrélations entre les événements de votre site. (Par exemple, quel pourcentage de personnes qui ont consulté votre politique de confidentialité ont ensuite acheter un produit.) Vous pouvez également utiliser ce modèle pour effectuer des comparaisons côte à côte de deux segments différents dans le même rapport.<br/>Ce modèle utilise la visualisation Abandons."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Affichez les appareils utilisés par les visiteurs et visiteuses à tous les stades du parcours."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes qui interagissent avec votre marque, les types d’appareils qu’elles utilisent et la manière dont leur utilisation de plusieurs appareils affecte leur expérience. Par exemple, quelle est fréquence à laquelle les personnes commencent une tâche sur un appareil mobile avant de passer à un PC de bureau pour terminer la tâche ? Quels sont les chemins les plus courants empruntés par les utilisateurs d’un appareil à l’autre ? Où abandonnent-ils ? Où réussissent-ils ? Et ainsi de suite.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le parcours d’utilisateur et d’utilisatrice d’une expérience mobile.<br/>Ce modèle utilise la visualisation Flux, la visualisation Abandon, l’analyse de cohortes, la mesure Personnes et la mesure Appareils uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Identifiez vos fidèles utilisateurs et utilisatrices et leurs activités sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de fois où une personne lambda visite votre site, la fréquence à laquelle les personnes reviennent sur le site et le nombre de jours entre les visites.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser le contenu le plus efficace pour inciter les visiteurs et visiteuses à revenir sur le site.<br/>Ce modèle utilise la mesures Visites et la mesure Visiteurs et visiteuses uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Affichez les tendances et les principales mesures de la consommation de média audio sur tous les appareils numériques."
>abstract="**Cela peut vous aider** à mieux comprendre comment les visiteurs et visiteuses consomment du contenu audio sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser le contenu le plus efficace.<br/>Ce modèle utilise la mesures Visites et la mesure Visiteurs et visiteuses uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Affichez les tendances et les principales mesures de la consommation de média sur tous les appareils numériques."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de fois où une personne lambda visite votre site, la fréquence à laquelle les personnes reviennent sur le site et le nombre de jours entre les visites.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser le contenu le plus efficace pour inciter les visiteurs et visiteuses à revenir sur le site.<br/>Ce modèle utilise la mesures Visites et la mesure Visiteurs et visiteuses uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Affichez le nombre de fois où un élément de dimension était présent au cours d’une actualisation. Un visiteur actualisant son navigateur est la méthode la plus courante pour déclencher une actualisation."
>abstract="**Cela peut vous aider** à identifier le moment où des problèmes peuvent se produire sur une page donnée et inciter un visiteur à charger à nouveau la page.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer quelles pages présentent des problèmes qui doivent être résolus.<br/>Ce modèle utilise la mesure Rechargement."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Affichez la durée moyenne des visiteurs et visiteuses sur votre site lors de chaque visite. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et visiteuses et leur temps passé sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer si les modifications apportées à votre site amènent les visiteurs et visiteuses à passer plus de temps sur le site.<br/>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Affichez les principales pages auxquelles les personnes accèdent à la première visite de votre site, sur la durée de vie d’un visiteur ou d’une visiteuse."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site, ainsi que les premières impressions des personnes quant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des personnes accédant au site, ou vous assurer que les premières pages consultées dès la connexion sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de graphique en barres et la visualisation en tableau à structure libre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Affichez le nombre de visites composées d’une page unique."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et visiteuses et leur temps passé sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer si les modifications apportées à votre site amènent les visiteurs et visiteuses à passer plus de temps sur le site.<br/>Ce modèle utilise la dimension Visites de page unique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Affichez les données de performances de votre site Adobe Experience Manager."
>abstract="**Cela peut vous aider** à mieux comprendre la réalisation de valeurs à partir d’Adobe Experience Manager.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser vos paramètres Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Affichez et analysez les effets de l’ITP (Intelligent Tracking Prevention) sur la collecte de données et la création de rapports."
>abstract="**Cela peut vous aider** à mieux comprendre la perte potentielle de données en raison des restrictions de cookies imposées par l’ITP.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme adapter la configuration de votre analyse afin de minimiser l’impact de l’ITP."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Permet d’afficher la durée moyenne passée par les personnes sur votre site au cours de chaque visite, ainsi que la durée moyenne passée par les utilisateurs et utilisatrices avant un événement de succès. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des personnes et le temps qui leur est nécessaire pour effectuer l’action souhaitée, par exemple effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des personnes à atteindre rapidement un événement de succès.<br/>Ce modèle utilise la dimension Jour et la mesure Durée par visite (secondes)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Affichez le contenu web le plus consommé et qui engage les utilisateurs et utilisatrices."
>abstract="**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les personnes vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs et visiteuses uniques, la mesure Taux d’entrée, la mesure Taux de rebond, la mesure Taux de sortie et la mesure Vitesse du contenu. Il utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Affichez le contenu multimédia le plus consommé et qui engage les utilisateurs et utilisatrices."
>abstract="**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les personnes vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs et visiteuses uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Il utilise également les visualisations de flux pour les sections d’entrée, de sortie et supérieure ; une visualisation de graphique à nuages de points qui présente les pages vues pour les pages les plus courantes ; une visualisation de graphique en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation de graphique linéaire qui affiche une vue de tendance de la durée moyenne passée sur le site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Affichez des informations clés sur une page dans vos propriétés. Affiche les pages vues, une ligne de tendance, une visualisation de flux, etc."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes interagissent avec une page donnée.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les performances de la page sur une période donnée ou mieux comprendre ce qui entraîne le trafic vers la page.<br/>Ce modèle utilise la mesure Pages vues. Il utilise également la visualisation de graphique linéaire et la visualisation de flux."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Affichez les principales pages auxquelles les personnes accèdent à la première visite de votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site, ainsi que les premières impressions des personnes quant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des personnes accédant au site, ou vous assurer que les premières pages consultées dès la connexion sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de graphique en barres et la visualisation en tableau à structure libre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Affichez les principales pages auxquelles les personnes accèdent immédiatement avant de quitter votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui font quitter le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que la mise à jour de pages de sortie courantes afin d’optimiser l’expérience des personnes avant qu’elles quittent le site, ou inclure du contenu et des liens pour encourager les personnes à rester sur votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de graphique en barres et la visualisation en tableau à structure libre."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Mesures clés**] | <!--duplicated in Most popular section--> Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de personnes uniques sur le site, du nombre de visites de pages et du nombre de sessions.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme évaluer le nombre moyen de pages que chaque personne a consultées lors de sa visite du site au cours d’une semaine ou d’un mois donné, et comment cela a changé à certaines périodes de l’année ou avant et après l’exécution des campagnes marketing. </p><p>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Pages vues**] | <!--duplicated in Most popular section-->Affichez le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Pages vues .</p> |
| [!UICONTROL **Pages**] | <!--duplicated in Most popular section-->Identifiez les pages les plus populaires et les moins populaires. <p>**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui l’intéresse le plus.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.</p><p>Ce modèle utilise la dimension Page et la mesure Pages vues .</p> |
| [!UICONTROL **Visites**] | <!--duplicated in Most popular section-->Affichez le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visites .</p> |
| [!UICONTROL **Visiteurs**] | <!--duplicated in Most popular section-->Affichez le nombre total de visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs et visiteuses uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visiteurs uniques .</p> |
| [!UICONTROL **Durée**] | Permet d’afficher la durée moyenne passée par les personnes sur votre site au cours de chaque visite, ainsi que la durée moyenne passée par les utilisateurs et utilisatrices avant un événement de succès. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des personnes et le temps qui leur est nécessaire pour effectuer l’action souhaitée, par exemple effectuer un achat.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des personnes à atteindre rapidement un événement de succès.</p><p>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes), la dimension Jour et la mesure Durée de la visite (secondes).</p> |
| [!UICONTROL **Sections du site**] | <!--duplicated in Most popular section-->Affichez les sections les plus populaires ou les plus performantes de votre site. <p>**Cela peut vous aider** à mieux comprendre quelles sections de votre site sont les plus visitées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.</p> <p>Ce modèle utilise la dimension Section du site et la mesure Visites .</p> |
| [!UICONTROL **Consommation de contenu web**] | Affichez le contenu web le plus consommé et qui engage les utilisateurs et utilisatrices.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme évaluer quels chemins du site dirigent les visiteurs vers les pages les plus importantes et quelles pages sont les plus susceptibles de les éloigner du site <!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page et les mesures Pages vues , Visites , Visiteurs uniques , Taux d’entrée , Taux de rebond , Taux de sortie et Vitesse du contenu . Il utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure.</p> |
| [!UICONTROL **Consommation de contenu multimédia**] | Affichez le contenu multimédia le plus consommé et qui engage les utilisateurs et utilisatrices.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme évaluer quels chemins du site dirigent les visiteurs vers les pages les plus importantes et quelles pages sont les plus susceptibles de les éloigner du site <!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page et les mesures Pages vues , Visites , Visiteurs uniques , Taux d’entrée , Taux de rebond , Taux de sortie et Vitesse du contenu . Il utilise également les visualisations de flux pour les sections d’entrée, de sortie et supérieure ; une visualisation de graphique à nuages de points qui présente les pages vues pour les pages les plus courantes ; une visualisation de graphique en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation de graphique linéaire qui affiche une vue de tendance de la durée moyenne passée sur le site.</p> |
| [!UICONTROL **Page suivante et précédente**] | <!--duplicated in Most popular section-->Afficher les endroits les plus fréquents où les gens vont avant ou après avoir visité un certain endroit.<p>**Cela peut vous aider** à mieux comprendre où les personnes entrent en premier sur le site, quelles sections du site les personnes visitent le plus et quelles pages sont les plus susceptibles d’être visitées avant de quitter le site.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme évaluer quels chemins du site dirigent les visiteurs vers les pages les plus importantes et quelles pages sont les plus susceptibles de les éloigner du site<!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page , la mesure Pages vues , la mesure Visites , la mesure Visiteurs uniques , la mesure Taux d’entrée , la mesure Taux de rebond , la mesure Taux de sortie et la mesure Vitesse du contenu . Il utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieures. Il s’agit d’une visualisation en graphique à dispersion qui affiche les pages vues pour les pages les plus courantes, d’une visualisation Barre qui affiche les pages vues par temps regroupé et d’une visualisation Ligne qui affiche une vue en tendance du temps moyen passé sur le site.</p> |
| **Résumé de la page** | Affichez des informations clés sur une page dans vos propriétés. Affiche les pages vues, une ligne de tendance, une visualisation de flux, etc.  <p>**Cela peut vous aider** à mieux comprendre comment les personnes interagissent avec une page donnée.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les performances de la page sur une période donnée ou mieux comprendre ce qui entraîne le trafic vers la page.</p><p>Ce modèle utilise la mesure Pages vues . Il utilise également la visualisation de graphique linéaire et la visualisation de flux.</p> |
| **Pages d’entrée** | Affichez les principales pages auxquelles les personnes accèdent à la première visite de votre site. <p>**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site, ainsi que les premières impressions des personnes quant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des personnes accédant au site, ou vous assurer que les premières pages consultées dès la connexion sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.</p><p>Ce modèle utilise la mesure Sessions . Il utilise également la visualisation de graphique en barres et la visualisation en tableau à structure libre.</p> |
| **Pages de sortie** | Affichez les principales pages auxquelles les personnes accèdent immédiatement avant de quitter votre site.<p>**Cela peut vous aider** à mieux comprendre quelles pages éloignent les personnes du site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que la mise à jour de pages de sortie courantes afin d’optimiser l’expérience des personnes avant qu’elles quittent le site, ou inclure du contenu et des liens pour encourager les personnes à rester sur votre site.</p><p>Ce modèle utilise la mesure Sessions . Il utilise également la visualisation de graphique en barres et la visualisation en tableau à structure libre.</p> |

### Web : conversion {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="."
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Consultez les informations préconfigurées pour les détaillants sur vos activités commerciales afin de contribuer à l’amélioration de vos ventes. Il s’adresse principalement aux utilisateurs et utilisatrices de Magento, mais n’importe quel détaillant en ligne peut l’utiliser."
>abstract="**Cela peut vous aider** à mieux comprendre comment vos activités commerciales contribuent aux chiffres de vente.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les budgets aux activités qui obtiennent le plus de retour sur investissement."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Modèle Entonnoir de conversion de produits"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Identifiez les produits les plus performants."
>abstract="**Cela peut vous aider** à mieux comprendre les produits les plus performants.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.<br/>Ce modèle utilise les mesures Vues de produits, Ajouts au panier, Commandes, Revenus et Unités. Il utilise également la dimension Produit."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Permet d’afficher le nombre de fois où des personnes ont effectué des événements de passage en caisse clés, tels que l’ajout d’articles dans leur panier, l’affichage de leur panier, la suppression d’articles de leur panier et le paiement."
>abstract="**Cela peut vous aider** à mieux comprendre quelles parties de l’entonnoir du processus de passage en caisse mènent à la conversion et lesquelles sont plus susceptibles de provoquer un abandon de panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme réduire le point de friction à certaines étapes du processus de passage en caisse.<br/>Ce modèle utilise la"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="vue du nombre de personnes qui ont ajouté un produit à leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes qui ajoutent un produit à leur panier, par opposition au nombre total de produits qui sont ajoutés à un panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme mesurer l’efficacité de vos pages de produits.<br/>Ce modèle utilise la mesure Paniers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Permet d’afficher le nombre de fois où les personnes ont consulté leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre l’expérience de passage en caisse afin de réduire les taux d’abandon de panier ou d’analyser le temps entre les ajouts au panier et les passages en caisse pour différents produits.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des promotions d’offres pour les produits qui restent dans le panier le plus longtemps et qui présentent le plus grand risque d’abandon.<br/>Ce modèle utilise la mesure Vues du panier."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Affichez le nombre de fois où des personnes ont ajouté un article à leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle l’intérêt pour un produit est suffisamment élevé pour que les personnes l’ajoutent au panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les recommandations de produits pour l’ensemble de la clientèle. Pour ce faire, vous pouvez analyser les produits qui sont fréquemment ajoutés au même panier et suggérer les produits associés en fonction des articles déjà présents dans le panier."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Affichez le nombre de fois où des personnes ont supprimé un article de leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle les personnes ne sont plus intéressées par un produit, ou encore vous aider à comprendre où des problèmes peuvent se produire dans le processus de passage en caisse.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer les obstacles potentiels qui peuvent exister dans le processus de passage en caisse, comme une expérience client compliquée.<br/>Ce modèle utilise la mesure Retraits du panier."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Modèle Entonnoir de conversion d’achat"
>abstract=""

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Entonnoir de conversion de produit**] | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><p>Ce modèle utilise |
| **Produits** | Afficher les produits qui génèrent des mesures clés, tels que les articles les plus vendus ou les plus consultés. <p>**Cela peut vous aider** à mieux comprendre les produits les plus performants.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.</p><p>Ce modèle utilise la mesure Commandes et la dimension Produit . |
| **Performances du produit** | Identifiez les produits les plus performants.<p>**Cela peut vous aider** à mieux comprendre les produits les plus performants.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.</p><p>Ce modèle utilise les mesures Consultations de produit, Ajouts au panier, Commandes, Chiffre d’affaires et Unités. Il utilise également la dimension Produit. |
| **Entonnoirs de conversion de panier** | Permet d’afficher le nombre de fois où des personnes ont effectué des événements de passage en caisse clés, tels que l’ajout d’articles dans leur panier, l’affichage de leur panier, la suppression d’articles de leur panier et le paiement. <p>**Cela peut vous aider** à mieux comprendre quelles parties de l’entonnoir du processus de passage en caisse mènent à la conversion et lesquelles sont plus susceptibles de provoquer un abandon de panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme réduire le point de friction à certaines étapes du processus de passage en caisse.</p><p>Ce modèle utilise |
| **Paniers** | vue du nombre de personnes qui ont ajouté un produit à leur panier.<p>**Cela peut vous aider** à mieux comprendre le nombre de personnes qui ajoutent un produit à leur panier, par opposition au nombre total de produits qui sont ajoutés à un panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme mesurer l’efficacité de vos pages de produits.</p><p>Ce modèle utilise la mesure Paniers . |
| **Consultations du panier** | Permet d’afficher le nombre de fois où les personnes ont consulté leur panier. <p>**Cela peut vous aider** à mieux comprendre l’expérience de passage en caisse afin de réduire les taux d’abandon de panier ou d’analyser le temps entre les ajouts au panier et les passages en caisse pour différents produits.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des promotions d’offres pour les produits qui restent dans le panier le plus longtemps et qui présentent le plus grand risque d’abandon.</p><p>Ce modèle utilise la mesure Consultations du panier . |
| **Ajouts au panier** | Affichez le nombre de fois où des personnes ont ajouté un article à leur panier. <p>**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle l’intérêt pour un produit est suffisamment élevé pour que les personnes l’ajoutent au panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les recommandations de produits pour l’ensemble de la clientèle. Pour ce faire, vous pouvez analyser les produits qui sont fréquemment ajoutés au même panier et suggérer les produits associés en fonction des articles déjà présents dans le panier. |
| **Retraits du panier** | Affichez le nombre de fois où des personnes ont supprimé un article de leur panier.<p>**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle les personnes ne sont plus intéressées par un produit, ou encore vous aider à comprendre où des problèmes peuvent se produire dans le processus de passage en caisse.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer les obstacles potentiels qui peuvent exister dans le processus de passage en caisse, comme une expérience client compliquée.</p><p>Ce modèle utilise la mesure Retraits du panier . |
| **Entonnoir de conversion d’achat** | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><p>Ce modèle utilise |
| **Recettes** | <!--duplicated in Most popular section-->Affichez le montant monétaire des produits achetés dans toutes les commandes.<p>**Cela peut vous aider** en combinant la mesure Revenus avec n’importe quelle dimension, à mieux comprendre quels éléments de dimension ont contribué au chiffre d’affaires. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code de suivi ) qui ont contribué au chiffre d’affaires. </p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme ajuster les campagnes qui n’atteignent pas les objectifs de chiffre d’affaires auxquels vous vous attendriez.</p><p>Ce modèle utilise la mesure Revenu . |
| **Commandes** | <!--duplicated in Most popular section-->Afficher le nombre total d’événements d’achat effectués sur votre site. <p>**Cela peut vous aider** en combinant la mesure Commandes avec n’importe quelle dimension, à mieux comprendre quels éléments de dimension ont contribué à une commande. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code de suivi ) qui ont contribué aux achats.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme ajuster les campagnes qui n’atteignent pas les cibles d’achat attendues. </p><p>Ce modèle utilise la mesure Commandes . |

### Web : Audience {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Affichez les fuseaux horaires supérieurs des visiteurs et visiteuses qui accèdent à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre dans quels fuseaux horaires vivent vos visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les activités de maintenance du site à des moments qui affecteront le moins de personnes possible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Afficher les principaux domaines des visiteurs qui accèdent à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre de quelles organisations proviennent vos visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme cibler votre contenu pour vos clientes et clients les plus importants."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Afficher les principaux domaines des visiteurs qui accèdent à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre de quelles organisations proviennent vos visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme cibler votre contenu pour vos clientes et clients les plus importants."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Affichez les principales largeurs de navigateur que les visiteurs utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des largeurs de navigateur les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Affichez les principales hauteurs de navigateur que les visiteurs utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des hauteurs de navigateur les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Affichez le nom des systèmes d’exploitation et de la version utilisés par les visiteurs et visiteuses pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les versions et les systèmes d’exploitation les plus courants utilisés par les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des principaux systèmes d’exploitation et des principales versions. Cela permet de maximiser les efforts de contrôle de la qualité."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Affichez le nom des systèmes d’exploitation utilisés par les personnes pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les systèmes d’exploitation les plus courants utilisés par les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des principaux systèmes d’exploitation. Cela permet de maximiser les efforts de contrôle de la qualité."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Opérateur de téléphonie mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Opérateur de téléphonie mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Affichez le nombre de visites d’une personne sur le site."
>abstract="**Cela peut vous aider** à mieux comprendre l’engagement des visiteurs et visiteuses lors de leur retour sur votre site. Cela s’applique à la durée de vie du visiteur ou de la visiteuse, quelle que soit la période du projet.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les efforts marketing pour les visiteurs et visiteuses réguliers.<br/>Ce modèle utilise la dimension Nombre de visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Affichez le nombre de visiteurs et de visiteuses de votre site qui ont effectué 0 achat auparavant, 1 achat auparavant, 2 achats auparavant ou 3 achats ou plus auparavant."
>abstract="**Cela peut vous aider** à mieux comprendre comment votre site affecte le comportement d’achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme vous concentrer sur les visiteurs et visiteuses qui reviennent effectuer un achat, afin d’encourager un comportement similaire pour les nouveaux visiteurs et visiteuses.<br/>Ce modèle utilise la dimension Fidélisation de la clientèle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Affichez le nombre de jours entre la première visite des clientes et clients sur votre site et la date de leur achat. Par exemple, si un visiteur ou une visiteuse effectue un achat un jour après sa première visite, l’ensemble des visites ou événements ultérieurs appartiennent à l’élément de dimension 1 jour."
>abstract="**Cela peut vous aider** à mieux comprendre le temps nécessaire aux visiteurs et visiteuses pour effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme mettre à jour votre site pour favoriser une acquisition plus rapide.<br/>Ce modèle utilise la dimension Jours avant le premier achat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Affichez le temps écoulé entre l’accès actuel du visiteur ou de la visiteuse et son dernier achat à ce moment-là."
>abstract="**Cela peut vous aider** à mieux comprendre le comportement des visiteurs et visiteuses après leur achat sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme mettre à jour votre site pour favoriser les achats ultérieurs.<br/>Ce modèle utilise la dimension Jours depuis le dernier achat."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Affichez les principales tailles d’écran des appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des tailles d’écran des appareils mobiles les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Affichez les principales hauteurs d’écran d’appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des hauteurs d’écran d’appareils mobiles les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Affichez les principales largeurs d’écran d’appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des largeurs d’écran d’appareils mobiles les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Permet d’afficher le pays d’origine des personnes consultant le site."
>abstract="**Cela peut vous aider** à mieux comprendre les pays les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues principales différentes.<br/>Ce modèle utilise la dimension Pays."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Affichez l’État d’origine des personnes accédant au site (aux États-Unis). Cette fonction est similaire au modèle Géocalisation des régions, sauf qu’il est propre aux États-Unis."
>abstract="**Cela peut vous aider** à mieux comprendre les États nord-américains les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces États.<br/>Ce modèle utilise la dimension États."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Affichez la région géographique des personnes consultant le site. Une région est une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. "
>abstract="**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces régions ou vous assurer que l’expérience de votre site est optimale dans des régions qui ont des langues principales différentes. <br/>Ce modèle utilise les dimensions ID(variables/geocountry) et Régions. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Permet d’afficher la ville d’origine des personnes consultant le site."
>abstract="**Cela peut vous aider** à mieux comprendre les villes les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces villes. <br/>Ce modèle utilise la dimension Villes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Affichez les zones marketing désignées (DMA) aux États-Unis d’où proviennent les personnes qui visitent le site."
>abstract="**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes qui visitent votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans les régions les plus performantes. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Affichez les principales langues dans lesquelles les personnes préfèrent voir le contenu."
>abstract="**Cela peut vous aider** à mieux comprendre les langues les plus fréquemment préférées des personnes.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que des actions de localisation ou de marketing pour les langues les plus populaires.<br/>Ce modèle utilise la dimension Langue."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Vue d’ensemble de la technologie"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Affichez le nom et la version des principaux navigateurs utilisés par les personnes pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les personnes.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Affichez les noms des organisations qui ont créé les principaux navigateurs que les personnes utilisent pour accéder à votre site. Cela diffère du modèle Navigateurs dans la mesure où il ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts."
>abstract="**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants que les personnes utilisent.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité. <br/>Ce modèle utilise la dimension Type de navigateur. "

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Utilisateurs initiaux et récurrents**] | Affichez une comparaison des nouveaux visiteurs avec les visiteurs réguliers. <p>**Cela peut vous aider** à mieux comprendre l’efficacité de votre site pour fidéliser la clientèle ou le taux d’acquisition de nouveaux clients.</p><p>**En fonction de ce que vous avez appris** vous pouvez prendre un certain nombre de mesures, telles que proposer des incentives pour les futurs achats aux nouveaux visiteurs afin de les inciter à revenir.</p><!-- This template uses the --> |
| **Id De Personne/Espace De Noms** | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><!-- This template uses the --> |
| **Présentation de l’emplacement** | Affichez un aperçu de l’emplacement des visiteurs dans une visualisation de carte.<p>**Cela peut vous aider** à mieux comprendre où se trouvent les visiteurs et visiteuses qui visitent votre site. </p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme concentrer les ressources marketing sur les endroits où vous voyez le plus d’intérêt et d’opportunité.</p><!-- This template uses the --> |
| **Pays géographiques** | Permet d’afficher le pays d’origine des personnes consultant le site.<p>**Cela peut vous aider** à mieux comprendre les pays les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues principales différentes.</p><p>Ce modèle utilise la dimension Pays . </p> |
| **États américains géographiques** | Affichez l’État d’origine des personnes accédant au site (aux États-Unis). Cette fonction est similaire au modèle Géocalisation des régions, sauf qu’il est propre aux États-Unis.<p>**Cela peut vous aider** à mieux comprendre les États nord-américains les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces États.</p><p>Ce modèle utilise la dimension États américains . </p> |
| **Régions géographiques** | Affichez la région géographique des personnes consultant le site. Une région est une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. <p>**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces régions, ou vous assurer que l’expérience de votre site est optimale dans les régions qui ont des langues principales différentes. </p><p>Ce modèle utilise les dimensions ID(variables/geocountry) et Régions . </p> |
| **Villes géographiques** | Permet d’afficher la ville d’origine des personnes consultant le site. <p>**Cela peut vous aider** à mieux comprendre les villes les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme utiliser les données pour vous concentrer sur les efforts de marketing dans ces villes. </p><p>Ce modèle utilise la dimension Villes . </p> |
| **Géosegmentation - DMA US** | Affichez les zones marketing désignées (DMA) aux États-Unis d’où proviennent les personnes qui visitent le site.<p>**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes qui visitent votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans les régions les plus performantes. </p><!-- This template uses the --> |
| **Langues** | Affichez les principales langues dans lesquelles les personnes préfèrent voir le contenu. <p>**Cela peut vous aider** à mieux comprendre les langues les plus fréquemment préférées des personnes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que des actions de localisation ou de marketing pour les langues les plus populaires.</p><p>Ce modèle utilise la dimension Langue .</p> |
| **Présentation de la technologie** | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><p>Ce modèle utilise </p> |
| **Navigateurs** | Affichez le nom et la version des principaux navigateurs utilisés par les personnes pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les personnes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité.</p><p>Ce modèle utilise la dimension Navigateur . </p> |
| **Types de navigateur** | Affichez les noms des organisations qui ont créé les principaux navigateurs que les personnes utilisent pour accéder à votre site. Cela diffère du modèle Navigateurs dans la mesure où il ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.<p>**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les visiteurs</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité. </p><p>Ce modèle utilise la dimension Type de navigateur . </p> |

### Web : acquisition {#web-acquisition}

<!--CJA only-->

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Affichez la manière dont votre site web obtient les visiteurs et visiteuses sur des appareils mobiles."
>abstract="**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux les plus efficaces.<br/>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Il utilise également la dimension Moteur de recherche, la dimension Mot-clé de recherche, la dimension Page d’accès, la dimension Domaine référent, la dimension Code de suivi et la dimension Référent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Affichez côte à côte toutes vos données de référencement payant Google et Bing."
>abstract="**Cela peut vous aider** à mieux comprendre le volume de trafic envoyé vers votre site et si les clientes et clients se convertissent.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme estimer le rapport coût-efficacité d’une campagne publicitaire."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Affichez la page des résultats de recherche sur laquelle un visiteur ou une visiteuse a cliqué pour accéder à votre site. Par exemple, si votre site apparaît sur la deuxième page de résultats d’un moteur de recherche, l’élément de dimension de cette variable est Page de recherche 2."
>abstract="**Cela peut vous aider** à mieux comprendre le classement de vos pages dans les résultats de recherche.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, commc améliorer votre stratégie SEO pour vous assurer que votre contenu s’affiche sur la première page des résultats de la recherche."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="Lors de l’utilisation de l’attribution personnalisée, ce modèle indique comment les personnes arrivent sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les canaux marketing les plus efficaces.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple investir plus massivement dans des canaux marketing efficaces et désinvestir des canaux marketing moins efficaces.<br/>Ce modèle utilise la dimension ID (variables/marketingchannel) et la mesure Chiffre d’affaires."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Affichez le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut)."
>abstract="**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic initial vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces.<br/>Ce modèle utilise la dimension Canal Première touche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Affichez des détails sur le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut)."
>abstract="**Cela peut vous aider** à mieux comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces.<br/>Ce modèle utilise la dimension Détails du canal Première touche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Entonnoir de conversion de campagne"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Affichez les détails sur les performances de vos campagnes marketing."
>abstract="**Cela peut vous aider** à mieux comprendre les différents indicateurs de succès associés aux campagnes, tels que le chiffre dʼaffaires, les affichages de produits, les commandes, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de chiffre dʼaffaires. <br/>Ce modèle utilise la mesure Chiffre dʼaffaires, la mesure Vues de produits, la mesure Ajouts au panier, la mesure Commandes et la mesure Unités. Il utilise également la dimension Code de suivi et la dimension Domaine référent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Affichez la manière dont votre site web gagne des visiteurs et visiteuse."
>abstract="**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux les plus efficaces.<br/>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Il utilise également la dimension Moteur de recherche, la dimension Mot-clé de recherche, la dimension Page d’accès, la dimension Domaine référent, la dimension Code de suivi et la dimension Référent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qu’ils soient payants ou naturels."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.<br/>Ce modèle utilise la dimension Mot-clé de recherche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site. <br/>Ce modèle utilise la dimension Mot-clé de recherche - Payant. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.<br/>Ce modèle utilise la dimension Mot-clé de recherche - Naturel. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, que cela soit payant ou naturel."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.<br/>Ce modèle utilise la dimension Moteur de recherche. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site. <br/>Ce modèle utilise la dimension Moteur de recherche - Payant."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.<br/>Ce modèle utilise la dimension Moteur de recherche - Naturel."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Affichez les domaines sur lesquels les personnes cliquent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre. (Un lien doit exister sur le site externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principaux domaines référents. <br/>Ce modèle utilise la dimension Domaine référent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Affichez le premier domaine référent sur lequel les personnes ont cliqué pour accéder à votre site. (Un fois défini, il contient la même valeur pour toute la durée de vie de cet identifiant visiteur.)"
>abstract="**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principaux domaines référents d’origine. <br/>Ce modèle utilise la dimension Domaine référent d’origine."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Affichez les URL sur lesquelles se trouvaient les personnes lorsqu’elles ont effectué un clic pour accéder à votre site. (Un lien doit exister sur l’URL externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)"
>abstract="**Cela peut vous aider** à mieux comprendre quelles URL spécifiques génèrent le plus de trafic vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principales URL. <br/>Ce modèle utilise la dimension Domaine référent.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Affichez les canaux génériques sur lesquels les personnes ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque canal. Les canaux possibles sont les moteurs de recherche, les réseaux sociaux, d’autres sites web, le disque dur ou les e-mails."
>abstract="**Cela peut vous aider** à mieux comprendre quel type de référents génère le plus de trafic vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant d’un certain canal.<br/>Ce modèle utilise la dimension Type de référent."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Rapport de présentation des canaux marketing**] | Lors de l’utilisation de l’attribution personnalisée, ce modèle indique comment les personnes arrivent sur votre site.<p>**Cela peut vous aider** à mieux comprendre les canaux marketing les plus efficaces.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple investir plus massivement dans des canaux marketing efficaces et désinvestir des canaux marketing moins efficaces.</p><p>Ce modèle utilise la dimension ID(variables/marketingchannel) et la mesure Revenu .</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Canal marketing Première touche**] | Affichez le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut). <p>**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic initial vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Canal Première touche .</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Détails du canal marketing Première touche**] | Affichez des détails sur le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Détails du canal Première touche .</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Canal marketing Dernière touche**] | Affichez le dernier canal marketing auquel un visiteur ou une visiteuse correspond au cours de sa période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent du trafic qui entraîne des conversions sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Canal Dernière touche .  </p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Détails du canal marketing Dernière touche**] | Affichez des détails sur le dernier canal marketing auquel un visiteur ou une visiteuse correspond au cours de sa période d’engagement (30 jours par défaut)<p>**Cela peut vous aider** à mieux comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces. </p><p>Ce modèle utilise la dimension Détails du canal Dernière touche . </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Campagnes (Code De Suivi)**] | Affichez les noms des codes de suivi sur votre site. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet.<p>**Cela peut vous aider** à mieux comprendre quels liens ont généré le plus de trafic sur votre site. Les chaînes de requête de code de suivi en attente sont courantes dans les e-mails, les publicités, les publications de médias sociaux et d’autres efforts marketing utilisés par votre organisation</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de chiffre d’affaires.</p><p>Ce modèle utilise la dimension Code de suivi . </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Entonnoir de conversion de campagne**] | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><p>Ce modèle utilise  </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Performances de la campagne**] | Affichez les détails sur les performances de vos campagnes marketing.<p>**Cela peut vous aider** à mieux comprendre les différents indicateurs de succès associés aux campagnes, tels que le chiffre dʼaffaires, les affichages de produits, les commandes, etc.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de chiffre d’affaires. </p><p>Ce modèle utilise les mesures Chiffre d’affaires, Vues des produits, Ajouts au panier, Commandes et Unités . Il utilise également la dimension Code de suivi et la dimension Domaine référent. </p> |
| **Acquisition Web** | Affichez la manière dont votre site web gagne des visiteurs et visiteuse.<p>**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux les plus efficaces.</p><p>Ce modèle utilise les mesures Taux de rebond et Rebonds . Il utilise également la dimension Moteur de recherche, la dimension Mot-clé de recherche, la dimension Page d’accès, la dimension Domaine référent, la dimension Code de suivi et la dimension Référent.  </p> |
| **Rechercher des mots-clés-Tous** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qu’ils soient payants ou naturels. <p>**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.</p><p>Ce modèle utilise la dimension Mot-clé de recherche . </p> |
| **Rechercher mots-clés-payants** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site. </p><p>Ce modèle utilise la dimension Mot-clé de recherche - Payant . </p> |
| **Mots-clés de recherche-Naturel** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.</p><p>Ce modèle utilise la dimension Mot-clé de recherche - Naturel . </p> |
| **Moteurs de recherche-Tous** | Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, que cela soit payant ou naturel. <p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.</p><p>Ce modèle utilise la dimension Moteur de recherche . </p> |
| **Moteurs de recherche-Paid** | Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site. </p><p>Ce modèle utilise la dimension Moteur de recherche - Payant . </p> |
| **Moteurs de recherche-Naturel** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.</p><p>Ce modèle utilise la dimension Moteur de recherche - Naturel . </p> |
| **Domaines référents** | Affichez les domaines sur lesquels les personnes cliquent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre. (Un lien doit exister sur le site externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs et visiteuses provenant des principaux domaines référents. </p><p>Ce modèle utilise la dimension Domaine référent . </p> |
| **Domaines référents d’origine** | Affichez le premier domaine référent sur lequel les personnes ont cliqué pour accéder à votre site. (Un fois défini, il contient la même valeur pour toute la durée de vie de cet identifiant visiteur.)<p>**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs et visiteuses provenant des principaux domaines référents d’origine. </p><p>Ce modèle utilise la dimension Domaine référent d’origine . </p> |
| **Référents** | Affichez les URL sur lesquelles se trouvaient les personnes lorsqu’elles ont effectué un clic pour accéder à votre site. (Un lien doit exister sur l’URL externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)  <p>**Cela peut vous aider** à mieux comprendre quelles URL spécifiques génèrent le plus de trafic vers votre site.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs et visiteuses qui proviennent des principales URL. </p><p>Ce modèle utilise la dimension Domaine référent . </p><p>Ce modèle utilise la dimension Référent . </p> |
| **Types de référents** | Affichez les canaux génériques sur lesquels les personnes ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque canal. Les canaux possibles sont les moteurs de recherche, les réseaux sociaux, d’autres sites web, le disque dur ou les e-mails.<p>**Cela peut vous aider** à mieux comprendre quel type de référents génère le plus de trafic vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant d’un certain canal.</p><p>Ce modèle utilise la dimension Type de référent .</p> |

### Mobile : application mobile {#mobile-app}

<!-- add contextual help for Mobile app screens and mobile app actions -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Affichez le nombre d’utilisateurs et d’utilisatrices, de lancements et de premiers lancements sur votre application, ainsi que la durée de session moyenne."
>abstract="**Cela peut vous aider** à mieux comprendre l’utilisation de votre application. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les performances de l’application, afin qu’elle puisse s’adapter à la quantité d’utilisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Affichez les schémas d’utilisation dominants de votre application mobile."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes utilisent votre application. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la façon dont les personnes peuvent passer d’un écran à un autre pour cibler les workflows les plus courants."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Affichez certaines des mesures d’application mobile les plus courantes."
>abstract="**Cela peut vous aider** à mieux comprendre les performances de base de votre application mobile.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’intégrité globale et les performances de votre application."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Affichez les données de performances pour les messages in-app et les notifications push de votre application."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes utilisent les fonctionnalités de messages in-app, ainsi que l’efficacité des notifications push qui génèrent du trafic vers votre application.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer l’expérience des notifications push et des messages in-app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Affichez les performances de votre application et l’endroit où les utilisateurs et utilisatrices rencontrent des problèmes."
>abstract="**Cela peut vous aider** à mieux comprendre si les personnes qui utilisent votre application rencontrent une lenteur ou une dégradation des performances. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme résoudre des problèmes existants ou améliorer les performances de l’application avant que des problèmes ne se produisent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Identifiez les plus fidèles utilisateurs et utilisatrices à votre application et leurs activités dans l’application."
>abstract="**Cela peut vous aider** à mieux comprendre comment vos plus fidèles utilisateurs et utilisatrices utilisent votre application.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer vos efforts de marketing pour les fonctionnalités utilisées par vos plus fidèles utilisateurs et utilisatrices."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Screens des applications mobiles**] | Affichez le nombre d’événements, de sessions et de personnes associés à chaque écran sur l’application mobile.<p>**Cela peut vous aider** à mieux comprendre quels écrans de votre site sont les plus populaires.</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme améliorer le contenu sur les écrans les plus populaires.</p><p>Ce modèle utilise les mesures Événements, Sessions, Personnes et Pourcentage de changement. Elle utilise également la dimension Titre de la page .</p> |
| **Actions des applications mobiles** | Affichez les actions que les utilisateurs entreprennent sur votre application mobile. <p>**Cela peut vous aider** à mieux comprendre comment les gens utilisent votre application et la valeur qu&#39;ils en tirent.</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme améliorer les fonctionnalités de développement qui complètent ou améliorent celles qui sont les plus populaires.</p><p>Ce modèle utilise les mesures Événements, Sessions, Personnes et Pourcentage de changement. |
| **Utilisation des applications mobiles** | Affichez le nombre d’utilisateurs et d’utilisatrices, de lancements et de premiers lancements sur votre application, ainsi que la durée de session moyenne.<p>**Cela peut vous aider** à mieux comprendre dans quelle mesure votre application est utilisée. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les performances de l’application, afin qu’elle puisse s’adapter à la quantité d’utilisation.</p><!-- This template uses the --> |
| **Parcours d’application mobile** | Affichez les schémas d’utilisation dominants de votre application mobile. <p>**Cela peut vous aider** à mieux comprendre comment les gens utilisent votre application. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la façon dont les personnes peuvent passer d’un écran à un autre pour cibler les workflows les plus courants. </p><!-- This template uses the --> |
| **Mesures sur application mobile** | Affichez certaines des mesures d’application mobile les plus courantes. <p>**Cela peut vous aider** à mieux comprendre les performances de base de votre application mobile.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’intégrité globale et les performances de votre application.</p><!-- This template uses the --> |
| **Messagerie sur application mobile** | Affichez les données de performances pour les messages in-app et les notifications push de votre application.<p>**Cela peut vous aider** à mieux comprendre comment les personnes utilisent les fonctionnalités de messages in-app, ainsi que l’efficacité des notifications push qui génèrent du trafic vers votre application.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer l’expérience des notifications push et des messages in-app.</p><!-- This template uses the --> |
| **Performances des applications mobiles** | Affichez les performances de votre application et l’endroit où les utilisateurs et utilisatrices rencontrent des problèmes. <p>**Cela peut vous aider** à mieux comprendre si les personnes qui utilisent votre application rencontrent une lenteur ou une dégradation des performances. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme résoudre des problèmes existants ou améliorer les performances de l’application avant que des problèmes ne se produisent.</p><!-- This template uses the --> |
| **Conservation des applications mobiles** | Identifiez les plus fidèles utilisateurs et utilisatrices à votre application et leurs activités dans l’application. <p>**Cela peut vous aider** à mieux comprendre comment vos plus fidèles utilisateurs et utilisatrices utilisent votre application.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer vos efforts de marketing pour les fonctionnalités utilisées par vos plus fidèles utilisateurs et utilisatrices.</p><!-- This template uses the --> |

### Mobile : informations sur les appareils mobiles {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Opérateur de téléphonie mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Affichez la marque et le modèle des appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les périphériques mobiles les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les appareils mobiles les plus courants.<br/>Ce modèle utilise la dimension Nom de l’appareil mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Affichez les types d’appareils mobiles que les personnes utilisent pour accéder à votre site, tels que les téléphones et tablettes."
>abstract="**Cela peut vous aider** à mieux comprendre les différents types d’appareils mobiles utilisés pour accéder à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les types d’appareils mobiles les plus utilisés.<br/>Ce modèle utilise la dimension Type d’appareil mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Affichez les fabricants qui produisent les appareils mobiles que les personnes utilisent pour accéder à votre site, comme Apple et Samsung."
>abstract="**Cela peut vous aider** à mieux comprendre les fabricants les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des capacités de différents fabricants afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Fabricant mobile."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Opérateur de téléphonie mobile**] | Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.</p><p>Ce modèle utilise la dimension Opérateur mobile .</p> |
| **Appareils mobiles** | Affichez la marque et le modèle des appareils mobiles que les personnes utilisent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les périphériques mobiles les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les appareils mobiles les plus courants.</p><p>Ce modèle utilise la dimension Nom de l’appareil mobile .</p> |
| **Type d’appareil mobile** | Affichez les types d’appareils mobiles que les personnes utilisent pour accéder à votre site, tels que les téléphones et tablettes.<p>**Cela peut vous aider** à mieux comprendre les différents types d’appareils mobiles utilisés pour accéder à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les types d’appareils mobiles les plus utilisés.</p><p>Ce modèle utilise la dimension Type d’appareil mobile .</p> |
| **Fabricant** | Affichez les fabricants qui produisent les appareils mobiles que les personnes utilisent pour accéder à votre site, comme Apple et Samsung.<p>**Cela peut vous aider** à mieux comprendre les fabricants les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des capacités de différents fabricants afin d’assurer une expérience client fluide.</p><p>Ce modèle utilise la dimension Fabricant du dispositif mobile.</p> |

### Tranches temporelles {#time-parting}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Affichez le nombre d’événements, de sessions et de personnes sur votre site, par minute. Si, par exemple, un rapport porte sur une seule journée, la première minute de chaque heure de la journée est regroupée dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les tendances à un niveau granulaire.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les ressources pour les périodes de pointe, à la minute près.<br/>Ce modèle utilise la dimension Minute de l’heure."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Affichez les événements, sessions et personnes sur votre site, par heure de la journée. Par exemple, si un rapport s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.<br/>Ce modèle utilise la dimension Heure de la journée."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Affichez les événements, sessions et personnes sur votre site, répartis entre le matin et l’après-midi. Par exemple, si un rapport s’étend du 1er au 7 janvier, les heures matinales de chaque jour sont regroupées dans le même élément de dimension."
>abstract="* **Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.<br/>Ce modèle utilise la dimension Matin/Après-midi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jour de la semaine. Si, par exemple, un rapport porte sur le mois de janvier, chaque jour de la semaine est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les jours de la semaine où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.<br/>Ce modèle utilise la dimension Jour de la semaine."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jour du mois. Si, par exemple, un rapport porte sur une année entière, chaque jour du mois est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les jours de chaque mois où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.<br/>Ce modèle utilise la dimension Jour du mois."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jour de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque jour de l’année est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les jours de chaque année où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.<br/>Ce modèle utilise la dimension Jour de l’année."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jours de la semaine et week-ends. Si, par exemple, un rapport porte sur le mois de janvier, les jours de semaine et les week-ends sont regroupés dans des éléments de dimension distincts."
>abstract="**Cela peut vous aider** à mieux comprendre les différences entre les jours de la semaine et les week-ends sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme affecter davantage de personnel de votre centre d’appel les week-ends si le rapport indique que le trafic est plus élevé le week-end qu’en semaine.<br/>Ce modèle utilise la dimension Jour de la semaine/Week-end."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par semaine de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque semaine est regroupée dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les semaines de l’année où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé, comme pendant les vacances.<br/>Ce modèle utilise la dimension Semaine de l’année."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par mois de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque mois est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les mois où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux mois où le trafic est élevé, comme pendant les vacances.<br/>Ce modèle utilise la dimension Mois de l’année."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par trimestre de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque trimestre est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les trimestres où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme programmer le lancement des produits afin de stimuler les trimestres où le trafic est habituellement faible.<br/>Ce modèle utilise la dimension Trimestre de l’année."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minute de l’heure**] | Affichez le nombre d’événements, de sessions et de personnes sur votre site, par minute. Si, par exemple, un rapport porte sur une seule journée, la première minute de chaque heure de la journée est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les tendances à un niveau granulaire.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les ressources pour les périodes de pointe, à la minute près.</p><p>Ce modèle utilise la dimension Minute de l’heure .</p> |
| **Heure de la journée** | Affichez les événements, sessions et personnes sur votre site, par heure de la journée. Par exemple, si un rapport s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.</p><p>Ce modèle utilise la dimension Heure de la journée .</p> |
| **Matin/après-midi** | Affichez les événements, sessions et personnes sur votre site, répartis entre le matin et l’après-midi. Par exemple, si un rapport s’étend du 1er au 7 janvier, les heures matinales de chaque jour sont regroupées dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre à quel moment de la journée votre site est le plus et le moins visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.</p><p>Ce modèle utilise la dimension AM/PM .</p> |
| **Jour de la semaine** | Affichez les événements, sessions et personnes sur votre site, répartis par jour de la semaine. Si, par exemple, un rapport porte sur le mois de janvier, chaque jour de la semaine est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de la semaine où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.</p><p>Ce modèle utilise la dimension Jour de la semaine .</p> |
| **Jour du mois** | Affichez les événements, sessions et personnes sur votre site, répartis par jour du mois. Si, par exemple, un rapport porte sur une année entière, chaque jour du mois est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de chaque mois où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.</p><p>Ce modèle utilise la dimension Jour du mois .</p> |
| **Jour de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par jour de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque jour de l’année est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de chaque année où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.</p><p>Ce modèle utilise la dimension Jour de l’année .&lt;/> |
| **Jour ouvrable/week-end** | Affichez les événements, sessions et personnes sur votre site, répartis par jours de la semaine et week-ends. Si, par exemple, un rapport porte sur le mois de janvier, les jours de semaine et les week-ends sont regroupés dans des éléments de dimension distincts. <p>**Cela peut vous aider** à mieux comprendre les différences entre les jours de la semaine et les week-ends sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme affecter davantage de personnel de votre centre d’appel les week-ends si le rapport indique que le trafic est plus élevé le week-end qu’en semaine.</p><p>Ce modèle utilise la dimension Jour de la semaine/Week-end .</p> |
| **Semaine de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par semaine de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque semaine est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les semaines de l’année où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé, comme pendant les vacances.</p><p>Ce modèle utilise la dimension Semaine de l’année .</p> |
| **Mois de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par mois de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque mois est regroupé dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les mois où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux mois où le trafic est élevé, comme pendant les vacances.</p><p>Ce modèle utilise la dimension Mois de l’année .</p> |
| **Trimestre de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par trimestre de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque trimestre est regroupé dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les trimestres où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme programmer le lancement des produits afin de stimuler les trimestres où le trafic est habituellement faible.</p><p>Ce modèle utilise la dimension Trimestre de l’année .</p> |

### Cross-canal {#cross-channel}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Affichez la répartition du trafic sur plusieurs canaux."
>abstract="**Cela peut vous aider** à mieux comprendre les canaux qui génèrent le plus de trafic et d’engagement. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les canaux qui permettent d’obtenir le meilleur retour sur investissement.<br/>Ce modèle utilise les mesures d’utilisateurs et d’utilisatrices, de session et d’événement."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Découvrez comment le trafic web affecte le trafic du centre d’appel."
>abstract="**Cela peut vous aider** à mieux comprendre dans quelle mesure le contenu en libre-service de votre site web détourne le trafic vers votre centre d’appel.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer le contenu en libre-service afin de réduire le trafic vers votre centre d’appel ou mesurer le retour sur investissement de votre contenu en libre-service en calculant le montant économisé grâce à la diminution du nombre d’appels au service clientèle.<br/>Ce modèle utilise les mesures Sessions web, Sessions d’application mobile et Sessions cross-canal web+application."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Affichez le trafic web et le trafic mobile ensemble."
>abstract="**Cela peut vous aider** à mieux comprendre la répartition du trafic web et mobile vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à l’expérience de votre application mobile lorsqu’elle atteint un certain niveau de trafic.<br/>Ce modèle utilise les mesures Sessions web, Sessions d’application mobile et Sessions cross-canal web+application."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Affichez le trafic en ligne et hors ligne ensemble."
>abstract="**Cela peut vous aider** à mieux comprendre la répartition du trafic en ligne et hors ligne sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à votre expérience en ligne lorsqu’elle atteint un certain niveau de trafic."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Présentation Multicanal**] | Affichez la répartition du trafic sur plusieurs canaux. <p>**Cela peut vous aider** à mieux comprendre quels canaux génèrent le plus de trafic et d’engagement. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les canaux qui permettent d’obtenir le meilleur retour sur investissement.</p><p>Ce modèle utilise les mesures d’utilisateur, de session et d’événement.</p> |
| **Déviation du centre d’appels (Web+Centre d’appels)** | Découvrez comment le trafic web affecte le trafic du centre d’appel.<p>**Cela peut vous aider** à mieux comprendre dans quelle mesure le contenu en libre-service de votre site web détourne le trafic vers votre centre d’appel.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer le contenu en libre-service afin de réduire le trafic vers votre centre d’appel ou mesurer le retour sur investissement de votre contenu en libre-service en calculant le montant économisé grâce à la diminution du nombre d’appels au service clientèle.</p><p>Ce modèle utilise les mesures Sessions web, Sessions d’applications mobiles et Sessions cross-canal Web+App .</p> |
| **Web+App** | Affichez le trafic web et le trafic mobile ensemble.<p>**Cela peut vous aider** à mieux comprendre la répartition du trafic web et mobile vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à l’expérience de votre application mobile lorsqu’elle atteint un certain niveau de trafic.</p><p>Ce modèle utilise les mesures Sessions web, Sessions d’applications mobiles et Sessions cross-canal Web+App .</p> |
| **En ligne/hors ligne** | Affichez le trafic en ligne et hors ligne ensemble.<p>**Cela peut vous aider** à mieux comprendre la répartition du trafic en ligne et hors ligne sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à votre expérience en ligne lorsqu’elle atteint un certain niveau de trafic.</p><!-- This template uses the ... --> |

### Autres canaux {#other-channels}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pointOfSale"
>title="Affichez les données sur les transactions de point de vente (POS), y compris le chiffre d&#39;affaires gagné, les commandes passées et les unités vendues. Ce modèle inclut également des visualisations qui affichent des informations sur les meilleurs magasins, les meilleurs produits et les principales catégories de produits, ainsi que sur les ventes en ligne et hors ligne."
>abstract="**Cela peut vous aider** à mieux comprendre quels sont vos produits les plus vendus dans les magasins et en ligne.<br/>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme affecter davantage de ressources marketing à vos produits et canaux les plus performants."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--survey"
>title="Affichez l’interaction client pour vos questionnaires. Affichez le nombre de débuts et d’achèvements, les questions et réponses les plus fréquentes, ainsi que le nombre de participants qui ont commencé ou qui se sont répétés."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement et le taux de succès de vos enquêtes.<br/>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme ajuster les enquêtes futures pour obtenir une meilleure participation."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tableau de bord du centre d’appels**] | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><p>Ce modèle utilise |
| **POS/Offline** | Affichez les données sur les transactions de point de vente (POS), y compris le chiffre d&#39;affaires gagné, les commandes passées et les unités vendues. Ce modèle inclut également des visualisations qui affichent des informations sur les meilleurs magasins, les meilleurs produits et les principales catégories de produits, ainsi que sur les ventes en ligne et hors ligne. <p>**Cela peut vous aider** à mieux comprendre quels sont vos produits les plus vendus dans les magasins et en ligne.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme affecter davantage de ressources marketing à vos produits et canaux les plus performants.</p><p>Ce modèle utilise les mesures Utilisateurs, Chiffre d’affaires et Commandes .</p> |
| **Email/AJO** | <p>**Cela peut vous aider** mieux comprendre</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme : </p><p>Ce modèle utilise |
| **Enquête** | Affichez l’interaction client pour vos questionnaires. Affichez le nombre de débuts et d’achèvements, les questions et réponses les plus fréquentes, ainsi que le nombre de participants qui ont commencé ou qui se sont répétés.<p>**Cela peut vous aider** à mieux comprendre les niveaux d’engagement et le taux de succès de vos enquêtes.</p><p>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme ajuster les enquêtes futures pour obtenir une meilleure participation.</p><p>Ce modèle utilise les mesures Utilisateurs, Événements, Début du questionnaire, Fin du questionnaire et Taux de fin du questionnaire.</p> |

### AJO {#AJO-templates}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Affichez les mesures essentielles pour vos campagnes Journey Optimizer, notamment les campagnes par e-mail, les expérimentations, les messages in-app, les SMS, etc."
>abstract="**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre campagne.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Affichez les mesures essentielles pour vos parcours Journey Optimizer, notamment les parcours par e-mail, les expérimentations, les messages in-app, les SMS, etc."
>abstract="**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre parcours.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Affichez le comportement des utilisateurs et utilisatrices, les schémas d’engagement, les taux de conversion et d’autres mesures clés."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité de votre landing page. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les performances de votre landing page."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Affichezun résumé exhaustif des mesures de trafic et d’engagement pour l’ensemble des campagnes et des parcours de votre environnement."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité générale de vos campagnes et parcours. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes et parcours en fonction du niveau d’engagement de votre audience cible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Affichez les abonnements et désabonnements des profils associés à des listes spécifiques."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité de différentes initiatives et campagnes d’abonnement pour stimuler l’engagement et générer des conversions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes d’abonnement en fonction des niveaux d’engagement de votre audience cible."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campagnes AJO**] | Affichez les mesures essentielles pour vos campagnes Journey Optimizer, notamment les campagnes par e-mail, les expérimentations, les messages in-app, les SMS, etc.<p>**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre campagne.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible.</p> |
| **AJO Parcours** | Affichez les mesures essentielles pour vos parcours Journey Optimizer, notamment les parcours par e-mail, les expérimentations, les messages in-app, les SMS, etc.<p>**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre parcours.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible.</p> |
| **Pages De Destination AJO** | Affichez le comportement des utilisateurs et utilisatrices, les schémas d’engagement, les taux de conversion et d’autres mesures clés.<p>**Cela peut vous aider** à mieux comprendre l’efficacité de votre page de destination. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les performances de votre landing page.</p> |
| **Rapport de présentation AJO** | Affichezun résumé exhaustif des mesures de trafic et d’engagement pour l’ensemble des campagnes et des parcours de votre environnement.<p>**Cela peut vous aider** à mieux comprendre l’efficacité globale de vos campagnes et parcours. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes et parcours en fonction du niveau d’engagement de votre audience cible.</p> |
| **Abonnements AJO** | Affichez les abonnements et désabonnements des profils associés à des listes spécifiques.<p>**Cela peut vous aider** à mieux comprendre l’efficacité de différentes initiatives et campagnes d’abonnement pour stimuler l’engagement et générer des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes d’abonnement en fonction des niveaux d’engagement de votre audience cible.</p> |

