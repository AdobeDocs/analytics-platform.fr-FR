---
description: Découvrez les modèles par défaut dans Analysis Workspace et comment les utiliser.
title: Utiliser des modèles
feature: Workspace Basics
role: User, Admin
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: 02aa4b4c9b357efca3d620bb72d8a505153bc079
workflow-type: tm+mt
source-wordcount: '21006'
ht-degree: 96%

---

# Utiliser des modèles

Les modèles (ou modèles d’entreprise) dans Analysis Workspace fournissent un aperçu rapide sur les scénarios de création de rapports les plus courants. Voici quelques exemples de questions auxquelles vous pouvez répondre à l’aide de modèles :

* Nombre de personnes qui visitent votre site.
* Nombre de ces visiteurs et visiteuses qui sont des visiteurs et visiteuses uniques (comptabilisés une seule fois).
* comment ils sont arrivés sur le site (par exemple, s’ils ont suivi un lien ou s’ils y sont venus directement) ;
* Mots-clés utilisés par les visiteurs et visiteuses pour rechercher du contenu sur le site.
* Durée pendant laquelle les visiteurs et visiteuses sont restés sur une page donnée ou sur l’ensemble du site.
* Les liens sur lesquels les visiteurs et visiteuses ont cliqué et le moment où ils ont quitté le site.
* Les canaux marketing les plus efficaces pour générer du chiffre d’affaires ou des événements de conversion.
* Combien de temps ils ont passé à regarder une vidéo ?
* Les navigateurs et appareils utilisés pour visiter votre site.

Les informations suivantes décrivent comment accéder aux modèles à partir de l’onglet [!UICONTROL Modèles] dans Analysis Workspace.

## Accéder à un modèle et l’exécuter

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**].

   ![Onglets Modèles](assets/view-prebuilt-templates-full.png)

1. Dans la section [!UICONTROL **Modèles**], sélectionnez l’un des onglets suivants :

   * **[!UICONTROL Modèles Adobe]** : affiche tous les modèles fournis par Adobe.

   * **[!UICONTROL _Modèles login_company_name _]** : affiche tous les modèles d’entreprise qui ont été créés pour votre organisation.

     Seuls les administrateurs et administratrices peuvent créer des modèles d’entreprise. Pour plus d’informations sur la création d’un modèle d’entreprise, consultez [Création et gestion de modèles](/help/analysis-workspace/templates/create-templates.md).

1. Utilisez l’une des options suivantes pour modifier l’affichage des modèles disponibles :

   * Choisissez d’afficher les modèles en mode Colonnes ou Carte en sélectionnant l’icône de mode Colonnes ![ViewColumn](/help/assets/icons/ViewColumn.svg) ou de mode Carte ![Carte](/help/assets/icons/Card.svg).

   * Lors de l’utilisation du mode Carte ![Carte](/help/assets/icons/Card.svg), choisissez l’un des ordres de tri suivants : **[!UICONTROL Le plus récemment utilisé]**, **[!UICONTROL Le plus populaire]**, **[!UICONTROL Alphabétique]**, **[!UICONTROL Catégorique]**.

1. Dans le champ de recherche, commencez à saisir le nom du modèle à rechercher, puis sélectionnez-le dans la liste des modèles.

   Ou

   Sélectionnez la catégorie de modèle à afficher, puis le modèle dans la liste des modèles.

   >[!TIP]
   >
   >Pour naviguer dans le menu à l’aide des touches fléchées, appuyez sur la touche Barre oblique (/), puis sur la touche Flèche vers le bas. Appuyez sur Entrée pour charger le modèle sélectionné.

   Pour obtenir la liste des modèles disponibles, reportez-vous à la section [Modèles disponibles](#available-templates) ci-dessous.

1. (Facultatif) Vous pouvez afficher des modèles contenant des composants qui ne sont pas disponibles dans votre vue de données. (Par défaut, les modèles ne s’affichent que s’ils utilisent des composants disponibles dans votre vue de données.)

   >[!NOTE]
   >
   >Avant de pouvoir utiliser ces modèles, un administrateur ou une administratrice doit d’abord ajouter les libellés de contexte requis pour ces composants manquants à la vue de données. Pour plus d’informations, consultez [Ajouter les composants manquants à la vue de données d’un modèle donné](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) dans [Utiliser des modèles](/help/analysis-workspace/templates/create-templates.md).
   >
   >Pour plus d’informations sur les libellés de contexte, consultez [Paramètres des composants](/help/data-views/component-settings/overview.md).

   1. Sélectionnez l’icône de segment.

   1. Sélectionnez **[!UICONTROL Pas prêt à l’emploi]** pour afficher les modèles qui nécessitent des composants supplémentaires.

      ![Utiliser un modèle avec des composants manquants](assets/template-not-ready.png)

1. Sélectionnez le modèle pour créer un rapport basé sur le modèle que vous avez choisi.

1. (Le cas échéant) Si le modèle contient des composants qui ne sont pas disponibles dans votre vue de données, la boîte de dialogue Vue de données incompatible s’affiche, indiquant que la vue de données est incompatible avec le modèle et quels composants sont manquants.

   Effectuez l’une des opérations suivantes :

   * Choisissez une autre vue de données dans le menu déroulant **[!UICONTROL Modifier la vue de données]**.

   * Sélectionnez **[!UICONTROL Continuer quand même]** pour afficher le modèle avec les composants manquants.

## Créer un projet basé sur un modèle {#use-reports}

Un modèle peut ne pas correspondre exactement à vos besoins, mais il peut vous rapprocher. Dans ce cas, vous pouvez utiliser le modèle comme point de départ de votre projet, puis le personnaliser selon vos besoins.

Si vous quittez un modèle après avoir apporté des modifications, nous vous demandons d’enregistrer ou d’ignorer vos modifications. L’enregistrement des modifications dans un modèle enregistre le modèle en tant que nouveau projet.

Pour personnaliser un modèle et l’enregistrer en tant que projet, procédez comme suit :

1. Dans Customer Journey Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**].

1. Sélectionnez l’onglet [!UICONTROL **Modèles**].

1. Sélectionnez le modèle à afficher. Par exemple, sous [!UICONTROL **Les plus populaires**], sélectionnez le modèle [!UICONTROL **Pages**].

   Le modèle Pages, tel qu’affiché dans Analysis Workspace, contient deux [visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Graphique en barres](/help/analysis-workspace/visualizations/bar.md) et [Synthèse des chiffres](/help/analysis-workspace/visualizations/summary-number-change.md)) ainsi qu’un [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La mesure utilisée est Occurrences.

   <!--update screenshot. The following is AA -->

   ![Modèle Pages](assets/pages-report.png)

1. Effectuez l’une des opérations suivantes :

   * Affichez le modèle.
   * Faites glisser un ou plusieurs segments dans la zone de dépôt de segments située en haut. Par exemple, faites glisser le segment [!UICONTROL **Clients mobiles**] et observez les résultats.
   * Modifiez la période en accédant au calendrier en haut à droite.
   * Ajoutez des répartitions de dimension, faites glisser d’autres mesures et personnalisez généralement le modèle selon vos besoins.

1. (Facultatif) Enregistrez le modèle en tant que projet en sélectionnant [!UICONTROL **Projet**] > [!UICONTROL **Enregistrer**].

   Le modèle est enregistré comme nouveau projet. Le modèle existant n’est pas modifié. Pour plus d’informations sur l’enregistrement de projets, consultez [Enregistrer des projets](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Modèles disponibles

Pour accéder à tous les modèles préconfigurés disponibles, procédez comme suit :

1. Dans Adobe Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**], puis l’onglet [!UICONTROL **Modèles**].

   Les modèles préconfigurés sont organisés par catégorie.

   <!--add screenshot-->

1. Sélectionnez une catégorie pour afficher les modèles qu’elle contient.

   Les sections suivantes correspondent aux catégories disponibles et fournissent des informations sur chaque modèle.

   * **[[!UICONTROL Les plus populaires]](#most-popular)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Engagement]](#engagement)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Conversion]](#web-conversion)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Audience]](#web-audience)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Acquisition]](#web-acquisition)**

   * **[[!UICONTROL Mobile]** > **[!UICONTROL Application mobile]](#mobile-mobile-app)**

   * **[[!UICONTROL Mobile]** > **[!UICONTROL Informations sur les appareils mobiles]](#mobile-mobile-device-information)**

   * **[[!UICONTROL Répartition temporelle]](#time-parting)**

   * **[[!UICONTROL Cross-canal]](#cross-channel)**

   * **[[!UICONTROL Autres canaux]](#other-channels)**

   * **[[!UICONTROL AJO]](#ajo)**

### Les plus populaires {#most-popular}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Affichez le nombre total d’unités achetées pour toutes les commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comprendre comment les ventes unitaires augmentent ou diminuent au fil du temps. Vous pouvez appliquer un segment pour identifier les personnes ou les zones géographiques qui achètent le plus d’unités et déterminer les tendances de ces ventes unitaires au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les ventes unitaires du site avant et après le lancement de la campagne. Vous pouvez aussi comparer les ventes unitaires d’une année à l’autre pendant les fêtes.<br/>Ce modèle utilise la dimension Jour et la mesure Unités."


<!--both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Modèle de tutoriel de formation"
>abstract="Découvrez la terminologie et les étapes courantes d’Analysis Workspace pour créer votre première analyse."

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identifiez les pages les plus populaires et les moins populaires."
>abstract="**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui l’intéresse le plus.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues."

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Affichez le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. "
>abstract="**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Pages vues."

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Affichez le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Visites."

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Affichez le nombre total de visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. "
>abstract="**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs et visiteuses uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Visiteurs et visiteuses uniques. "

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de personnes uniques sur le site, du nombre de visites de pages et du nombre de sessions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. <br/>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs et visiteuses uniques."

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Affichez les sections les plus populaires ou les plus performantes de votre site."
>abstract="**Cela peut vous aider** à mieux comprendre quelles sections de votre site sont les plus visitées.<br>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.<br/>Ce modèle utilise la dimension Section du site et la mesure Visites."

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite d’une certaine page."
>abstract="**Cela peut vous aider** à mieux comprendre le comportement des utilisateurs et utilisatrices après leur visite d’une certaine page.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme évaluer si la conception ou la disposition de page peut être optimisée pour diriger les personnes vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser un avis.<br/>Ce modèle utilise la dimension Page et la mesure Événements."

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite d’une certaine page."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui dirigent le plus de trafic vers une certaine page.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme évaluer si les pages qui n’apparaissent pas comme des pages précédentes ont besoin de liens plus visibles vers la page actuelle."

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Affichez les liens qui ont généré le plus de trafic vers votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les codes de suivi (et les liens auxquels ils sont associés) qui ont été les plus utilisés pour accéder à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster votre stratégie en fonction de l’endroit où vous ajoutez des liens à votre site.<br/>Ce modèle utilise la dimension Code de suivi et la mesure Visites."

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Affichez le nombre de commandes par produit. Les données s’affichent sur une période donnée."
>abstract="**Cela peut vous aider** à comprendre les produits présentant la demande la plus élevée ou la plus faible.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos stratégies marketing pour promouvoir des produits hautement performants, ou améliorer ou arrêter les produits peu performants. Vous pouvez également ajuster votre inventaire de produits en fonction de votre analyse des données.<br/>Ce modèle utilise la dimension Produit et la mesure Commandes."

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Affichez les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut)."
>abstract="**Cela peut vous aider** à comprendre les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.<br/>Ce modèle utilise la dimension Canal Dernière touche et la mesure Visiteurs et visiteuses uniques."

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Affichez les détails sur les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut)."
>abstract="**Cela peut vous aider** à comprendre non seulement les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions, mais aussi des détails sur ces canaux marketing. Par exemple, si une personne arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.<br/>Ce modèle utilise la dimension Détails du canal Dernière touche et la mesure Visiteurs et visiteuses uniques. "

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Affichez le nombre monétaire des produits achetés dans l’ensemble des commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comprendre comment le chiffre d’affaires augmente ou diminue au fil du temps. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au chiffre d’affaires.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que projeter le chiffre d’affaires futur basé sur les tendances précédentes. Vous pouvez également ajouter une autre dimension, comme la dimension Code de suivi, pour savoir quelles campagnes génèrent le plus de chiffre d’affaires.<br/>Ce modèle utilise la dimension Jour et la mesure Chiffre d’affaires."

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Affichez le nombre total d’événements d’achat. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre comment l’intérêt pour vos produits et services augmente ou diminue au fil du temps. Vous pouvez appliquer un segment pour identifier les personnes ou les zones géographiques qui passent le plus de commandes et déterminer les tendances de ces commandes au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les commandes avant et après le lancement de la campagne. Vous pouvez également comparer les commandes passées pendant les fêtes d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Commandes."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Tutoriel de formation**] | Découvrir la terminologie et les étapes courantes d’Analysis Workspace pour créer votre première analyse |
| [!UICONTROL **Pages**] | <!--duplicated in Engagement section--> Identifiez les pages les plus populaires et les moins populaires. <p>**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui l’intéresse le plus.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.</p><p>Ce modèle utilise la dimension Page et la mesure Pages vues.</p> |
| [!UICONTROL **Pages vues**] | <!--duplicated in Engagement section--> Affichez le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Pages vues.</p> |
| [!UICONTROL **Visites web**] | <!--duplicated in Engagement section--> Affichez le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visites.</p> |
| [!UICONTROL **Visiteurs et visiteuses web**] | <!--duplicated in Engagement section--> Affichez le nombre total de visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs et visiteuses uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visiteurs et visiteuses uniques.</p> |
| [!UICONTROL **Mesures clés**] | <!--duplicated in Engagement section--> Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de personnes uniques sur le site, du nombre de visites de pages et du nombre de sessions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine donnée ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. </p><p>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs et visiteuses uniques.</p> |
| [!UICONTROL **Sections du site**] | Affichez les sections les plus populaires ou les plus performantes de votre site. <p>**Cela peut vous aider** à mieux comprendre quelles sections de votre site sont les plus visitées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.</p> <p>Ce modèle utilise la dimension Section du site et la mesure Visites.</p> |
| [!UICONTROL **Page suivante**] | Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite d’une certaine page. <p>**Cela peut vous aider** à mieux comprendre le comportement des utilisateurs et utilisatrices après leur visite d’une certaine page.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme évaluer si la conception ou la disposition de page peut être optimisée pour diriger les personnes vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser un avis.</p> <p>Ce modèle utilise la dimension Page et la mesure Événements.</p> |
| [!UICONTROL **Page précédente**] | Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite d’une certaine page. <p>**Cela peut vous aider** à mieux comprendre les pages qui dirigent le plus de trafic vers une certaine page.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme évaluer si les pages qui n’apparaissent pas comme des pages précédentes ont besoin de liens plus visibles vers la page actuelle.</p><p>Ce modèle utilise la dimension Page et la mesure Événements.</p> |
| [!UICONTROL **Code de suivi**] | Affichez les liens qui ont généré le plus de trafic vers votre site. <p>**Cela peut vous aider** à mieux comprendre les codes de suivi (et les liens auxquels ils sont associés) qui ont été les plus utilisés pour accéder à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster votre stratégie en fonction de l’endroit où vous ajoutez des liens à votre site.</p><p>Ce modèle utilise la dimension Code de suivi et la mesure Visites.</p> |
| [!UICONTROL **Produits**] | Affichez le nombre de commandes par produit. Les données s’affichent sur une période donnée. <p>**Cela peut vous aider** à comprendre les produits présentant la demande la plus élevée ou la plus faible.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos stratégies marketing pour promouvoir des produits hautement performants, ou améliorer ou arrêter les produits peu performants. Vous pouvez également ajuster votre inventaire de produits en fonction de votre analyse des données.</p><p>Ce modèle utilise la dimension Produit et la mesure Commandes.</p> |
| [!UICONTROL **Canal Dernière touche**] | Affichez les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à comprendre les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.</p><p>Ce modèle utilise la dimension Canal Dernière touche et la mesure Visiteurs et visiteuses uniques.</p> |
| [!UICONTROL **Détails du canal Dernière touche**] | Affichez les détails sur les canaux marketing les plus récents auxquels les personnes correspondent pendant leur période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à comprendre non seulement les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions, mais aussi des détails sur ces canaux marketing. Par exemple, si une personne arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.</p><p>Ce modèle utilise la dimension Détails du canal Dernière touche et la mesure Visiteurs et visiteuses uniques.</p> |
| [!UICONTROL **Recettes**] | <!--duplicated in Web Conversion section-->Affichez le nombre monétaire des produits achetés dans l’ensemble des commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures.<p>**Cela peut vous aider** à comprendre comment le chiffre d’affaires augmente ou diminue au fil du temps. Vous pouvez associer cette mesure à n’importe quelle dimension pour déterminer les éléments de dimension ayant contribué au chiffre d’affaires.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que projeter le chiffre d’affaires futur basé sur les tendances précédentes. Vous pouvez également ajouter une autre dimension, comme la dimension Code de suivi, pour savoir quelles campagnes génèrent le plus de chiffre d’affaires.</p><p>Ce modèle utilise la dimension Jour et la mesure Chiffre d’affaires.</p> |
| [!UICONTROL **Commandes**] | <!--duplicated in Web Conversion section-->Affichez le nombre total d’événements d’achat. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment l’intérêt pour vos produits et services augmente ou diminue au fil du temps. Vous pouvez appliquer un segment pour identifier les personnes ou les zones géographiques qui passent le plus de commandes et déterminer les tendances de ces commandes au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les commandes avant et après le lancement de la campagne. Vous pouvez également comparer les commandes passées pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Commandes.</p> |

### Web : engagement {#web-engagement}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="Affichez les dimensions et les mesures en cours de collecte sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les tendances sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme répondre aux performances de votre contenu et de vos campagnes marketing actuels et les gérer activement."

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Affichez la durée moyenne des visiteurs et visiteuses sur votre site lors de chaque visite. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et visiteuses et leur temps passé sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer si les modifications apportées à votre site amènent les visiteurs et visiteuses à passer plus de temps sur le site.<br/>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes)."

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Affichez la durée moyenne des utilisateurs et utilisatrices sur le site avant un événement de succès."
>abstract="**Cela peut vous aider** à mieux comprendre le temps nécessaire aux visiteurs et visiteuses pour effectuer l’action souhaitée, comme effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des personnes à atteindre rapidement un événement de succès.<br/>Ce modèle utilise la dimension Durée avant événement et la mesure Visiteurs et visiteuses uniques."

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Affichez les endroits où les personnes abandonnent ou poursuivent une séquence de pages prédéfinie."
>abstract="**Cela peut vous aider** à mieux comprendre où les personnes sortent du parcours d’utilisateur ou d’utilisatrice.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les taux de conversion par le biais de processus spécifiques sur votre site (tels qu’un processus d’achat ou d’enregistrement) ou analyser les corrélations entre les événements de votre site. (Par exemple, quel pourcentage de personnes qui ont consulté votre politique de confidentialité ont ensuite acheter un produit.) Vous pouvez également utiliser ce modèle pour effectuer des comparaisons côte à côte de deux segments différents dans le même rapport.<br/>Ce modèle utilise la visualisation Abandons."

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Affichez les appareils utilisés par les visiteurs et visiteuses à tous les stades du parcours."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes qui interagissent avec votre marque, les types d’appareils qu’elles utilisent et la manière dont leur utilisation de plusieurs appareils affecte leur expérience. Par exemple, quelle est fréquence à laquelle les personnes commencent une tâche sur un appareil mobile avant de passer à un PC de bureau pour terminer la tâche ? Quels sont les chemins les plus courants empruntés par les utilisateurs d’un appareil à l’autre ? Où abandonnent-ils ? Où réussissent-ils ? Et ainsi de suite.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le parcours d’utilisateur et d’utilisatrice d’une expérience mobile.<br/>Ce modèle utilise la visualisation Flux, la visualisation Abandon, l’analyse de cohortes, la mesure Personnes et la mesure Appareils uniques."

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Identifiez vos fidèles clientes et clients et leurs activités sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de fois où une personne lambda visite votre site, la fréquence à laquelle les personnes reviennent sur le site et le nombre de jours entre les visites.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser le contenu le plus efficace pour inciter les visiteurs et visiteuses à revenir sur le site.<br/>Ce modèle utilise la mesures Visites et la mesure Visiteurs et visiteuses uniques."

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Affichez les tendances et les principales mesures de la consommation de média audio sur tous les appareils numériques."
>abstract="**Cela peut vous aider** à mieux comprendre comment les visiteurs et visiteuses consomment du contenu audio sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser le contenu le plus efficace.<br/>Ce modèle utilise la mesures Visites et la mesure Visiteurs et visiteuses uniques."

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Affichez les tendances et les principales mesures de la consommation de média sur tous les appareils numériques."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de fois où une personne lambda visite votre site, la fréquence à laquelle les personnes reviennent sur le site et le nombre de jours entre les visites.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser le contenu le plus efficace pour inciter les visiteurs et visiteuses à revenir sur le site.<br/>Ce modèle utilise la mesures Visites et la mesure Visiteurs et visiteuses uniques."

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Affichez le nombre de fois où un élément de dimension était présent au cours d’une actualisation. Un visiteur actualisant son navigateur est la méthode la plus courante pour déclencher une actualisation."
>abstract="**Cela peut vous aider** à identifier le moment où des problèmes peuvent se produire sur une page donnée et inciter une personne à charger à nouveau la page.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer quelles pages présentent des problèmes qui doivent être résolus.<br/>Ce modèle utilise la mesure Rechargement."

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Affichez la durée moyenne des visiteurs et visiteuses sur votre site lors de chaque visite. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et visiteuses et leur temps passé sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer si les modifications apportées à votre site amènent les visiteurs et visiteuses à passer plus de temps sur le site.<br/>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes)."

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Affichez les principales pages auxquelles les personnes accèdent à la première visite de votre site, sur la durée de vie d’un visiteur ou d’une visiteuse."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site, ainsi que les premières impressions des personnes quant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des personnes accédant au site, ou vous assurer que les premières pages consultées dès la connexion sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de Barres et la visualisation Tableau à structure libre."

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Affichez le nombre de visites composées d’une page unique."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et visiteuses et leur temps passé sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer si les modifications apportées à votre site amènent les visiteurs et visiteuses à passer plus de temps sur le site.<br/>Ce modèle utilise la dimension Visites de page unique."

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Affichez les données de performances de votre site Adobe Experience Manager."
>abstract="**Cela peut vous aider** à mieux comprendre la réalisation de valeurs à partir d’Adobe Experience Manager.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser vos paramètres Experience Manager."

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="Affichez les données de performances de votre instance Adobe Experience Manager Forms."
>abstract="**Cela peut vous aider** à mieux comprendre la réalisation de valeurs à partir d’Adobe Experience Manager.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser vos paramètres Experience Manager."

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Affichez et analysez les effets de l’ITP (Intelligent Tracking Prevention) sur la collecte de données et la création de rapports."
>abstract="**Cela peut vous aider** à mieux comprendre la perte potentielle de données en raison des restrictions de cookies imposées par l’ITP.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme adapter la configuration de votre analyse afin de minimiser l’impact de l’ITP."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="Permet d’afficher la durée moyenne passée par les personnes sur votre site au cours de chaque visite, ainsi que la durée moyenne passée par les utilisateurs et utilisatrices avant un événement de succès. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des personnes et le temps qui leur est nécessaire pour effectuer l’action souhaitée, par exemple effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des personnes à atteindre rapidement un événement de succès.<br/>Ce modèle utilise la dimension Jour et la mesure Durée par visite (secondes)."

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Affichez le contenu web le plus consommé et qui engage les utilisateurs et utilisatrices."
>abstract="**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les personnes vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs et visiteuses uniques, la mesure Taux d’entrée, la mesure Taux de rebond, la mesure Taux de sortie et la mesure Vitesse du contenu. Il utilise également les visualisations en flux pour les sections d’entrée, de sortie et supérieure."

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Affichez le contenu multimédia le plus consommé et qui engage les utilisateurs et utilisatrices."
>abstract="**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les personnes vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs et visiteuses uniques, la mesure Taux d’entrée, la mesure Taux de rebond, la mesure Taux de sortie et la mesure Vitesse du contenu. Il utilise également les visualisations de flux pour les sections d’entrée, de sortie et supérieure ; une visualisation de graphique à nuages de points (dispersion) qui présente les pages vues pour les pages les plus courantes ; une visualisation de graphique en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation de graphique linéaire qui affiche une vue de tendance de la durée moyenne passée sur le site."

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="Affichez les emplacements les plus courants où les personnes se rendent immédiatement après leur visite ou juste avant de visiter un certain emplacement."
>abstract="**Cela peut vous aider** à comprendre comment le trafic passe d’une page donnée à d’autres parties de votre site, et comprendre les chemins empruntés par les personnes pour atteindre une page donnée.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si la conception ou la mise en page peut être optimisée pour diriger les personnes vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser un avis. Ou évaluez si les informations de la page active sont susceptibles de fournir la direction ou les actions que les personnes recherchent lorsqu’elles arrivent des pages précédentes. Vous pouvez également déterminer si les pages qui ne s’affichent pas comme des pages précédentes ont besoin de liens plus importants vers la page actuelle.<br/>Ce modèle utilise le panneau d’éléments Suivant ou Précédent."

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Affichez des informations clés sur une page dans vos propriétés. Affiche les pages vues, une ligne de tendance, une visualisation de flux, etc."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes interagissent avec une page donnée.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les performances de la page sur une période donnée ou mieux comprendre ce qui entraîne le trafic vers la page.<br/>Ce modèle utilise la mesure Pages vues. Il utilise également la visualisation Ligne et la visualisation Flux."

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Affichez les principales pages auxquelles les personnes accèdent à la première visite de votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site, ainsi que les premières impressions des personnes quant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des personnes accédant au site, ou vous assurer que les premières pages consultées dès la connexion sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de Barres et la visualisation Tableau à structure libre."

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Affichez les principales pages auxquelles les personnes accèdent immédiatement avant de quitter votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui font quitter le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que la mise à jour de pages de sortie courantes afin d’optimiser l’expérience des personnes avant qu’elles quittent le site, ou inclure du contenu et des liens pour inciter les personnes à rester sur votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de Barres et la visualisation Tableau à structure libre."

>[!CONTEXTUALHELP]
>id="template--productUsageOverviewReport"
>title="Découvrez comment le produit Customer Journey Analytics est utilisé au sein de votre organisation."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes utilisant Customer Journey Analytics, ainsi que la fréquence et les tendances d’utilisation au fil du temps. Vous pouvez également voir le nombre de projets créés et les détails de ces projets (tels que les composants, les visualisations et les panneaux les plus utilisés), ainsi que de nombreuses autres statistiques d’utilisation.<br/>**Sur la base de ce que vous avez appris, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer des projets ou des composants inutilisés, ou former les utilisateurs et utilisatrices aux fonctionnalités les plus populaires."

>[!CONTEXTUALHELP]
>id="template--content-analytics"
>title="Découvrez le contenu et les attributs de contenu les plus performants."
>abstract="**Cela peut vous aider** à découvrir comment votre contenu se comporte à un niveau granulaire. Vous pouvez examiner les performances de ressources individuelles ou d’attributs spécifiques. Content Analytics utilise l’IA pour générer automatiquement des attributs et baliser votre contenu avec ceux-ci. <a href="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/content-analytics/content-analytics" target="&quot;_blank&quot;">En savoir plus</a>.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme promouvoir des ressources hautement performantes sur votre page d’accueil, personnaliser le contenu pour des segments spécifiques afin d’inclure des attributs hautement performants ou remplacer le contenu qui a commencé à devenir obsolète."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Mesures clés**] | <!--duplicated in Most popular section--> Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de personnes uniques sur le site, du nombre de visites de pages et du nombre de sessions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine donnée ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. </p><p>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs et visiteuses uniques.</p> |
| [!UICONTROL **Pages vues**] | <!--duplicated in Most popular section-->Affichez le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Pages vues.</p> |
| [!UICONTROL **Pages**] | <!--duplicated in Most popular section-->Identifiez les pages les plus populaires et les moins populaires. <p>**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui l’intéresse le plus.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.</p><p>Ce modèle utilise la dimension Page et la mesure Pages vues.</p> |
| [!UICONTROL **Visites**] | <!--duplicated in Most popular section-->Affichez le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visites.</p> |
| [!UICONTROL **Visiteurs**] | <!--duplicated in Most popular section-->Affichez le nombre total de visiteurs et visiteuses uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs et visiteuses uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les fêtes d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visiteurs et visiteuses uniques.</p> |
| [!UICONTROL **Durée**] | Permet d’afficher la durée moyenne passée par les personnes sur votre site au cours de chaque visite, ainsi que la durée moyenne passée par les utilisateurs et utilisatrices avant un événement de succès. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des personnes et le temps qui leur est nécessaire pour effectuer l’action souhaitée, par exemple effectuer un achat.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des personnes à atteindre rapidement un événement de succès.</p><p>Ce modèle utilise la dimension Jour et la mesure Durée par visite (secondes).</p> |
| [!UICONTROL **Sections du site**] | <!--duplicated in Most popular section-->Affichez les sections les plus populaires ou les plus performantes de votre site. <p>**Cela peut vous aider** à mieux comprendre quelles sections de votre site sont les plus visitées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.</p> <p>Ce modèle utilise la dimension Section du site et la mesure Visites.</p> |
| [!UICONTROL **Consommation de contenu web**] | Affichez le contenu web le plus consommé et qui engage les utilisateurs et utilisatrices.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les personnes vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.</p> <p>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs et visiteuses uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Il utilise également les visualisations en flux pour les sections d’entrée, de sortie et supérieure.</p> |
| [!UICONTROL **Consommation de contenu multimédia**] | Affichez le contenu multimédia le plus consommé et qui engage les utilisateurs et utilisatrices.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les personnes vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site <!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs et visiteuses uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Il utilise également les visualisations de flux pour les sections d’entrée, de sortie et supérieure ; une visualisation de graphique à nuages de points (dispersion) qui présente les pages vues pour les pages les plus courantes ; une visualisation de graphique en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation de graphique linéaire qui affiche une vue de tendance de la durée moyenne passée sur le site.</p> |
| [!UICONTROL **Flux de pages suivante et précédente**] | Affichez une visualisation de flux des emplacements les plus courants où les personnes se rendent immédiatement après leur visite ou juste avant de visiter une certaine page. <p>**Cela peut vous aider** à comprendre comment le trafic passe d’une page donnée à d’autres parties de votre site, et comprendre les chemins empruntés par les personnes pour atteindre une page donnée.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si la conception ou la mise en page peut être optimisée pour diriger les personnes vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser un avis. Ou évaluez si les informations de la page active sont susceptibles de fournir la direction ou les actions que les personnes recherchent lorsqu’elles arrivent des pages précédentes. Vous pouvez également déterminer si les pages qui ne s’affichent pas comme des pages précédentes ont besoin de liens plus importants vers la page actuelle.</p><p>Ce modèle utilise le panneau d’éléments Suivant ou Précédent.</p> |
| **Résumé de la page** | Affichez des informations clés sur une page dans vos propriétés. Affiche les pages vues, une ligne de tendance, une visualisation de flux, etc.  <p>**Cela peut vous aider** à mieux comprendre comment les personnes interagissent avec une page donnée.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les performances de la page sur une période donnée ou mieux comprendre ce qui entraîne le trafic vers la page.</p><p>Ce modèle utilise la mesure Pages vues. Il utilise également la visualisation Ligne et la visualisation Flux.</p> |
| **Pages d’entrée** | Affichez les principales pages auxquelles les personnes accèdent à la première visite de votre site. <p>**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site, ainsi que les premières impressions des personnes quant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des personnes accédant au site, ou vous assurer que les premières pages consultées dès la connexion sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.</p><p>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de Barres et la visualisation Tableau à structure libre.</p> |
| **Pages de sortie** | Affichez les principales pages auxquelles les personnes accèdent immédiatement avant de quitter votre site.<p>**Cela peut vous aider** à mieux comprendre les pages qui font quitter le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que la mise à jour de pages de sortie courantes afin d’optimiser l’expérience des personnes avant qu’elles quittent le site, ou inclure du contenu et des liens pour encourager les personnes à rester sur votre site.</p><p>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation de Barres et la visualisation Tableau à structure libre.</p> |
| **Vue d’ensemble de l’utilisation du produit** | Découvrez comment le produit Customer Journey Analytics est utilisé au sein de votre organisation. <p>**Cela peut vous aider** à mieux comprendre le nombre de personnes utilisant Customer Journey Analytics, ainsi que la fréquence et les tendances d’utilisation au fil du temps. Vous pouvez également voir le nombre de projets créés et les détails de ces projets (tels que les composants, les visualisations et les panneaux les plus utilisés), ainsi que de nombreuses autres statistiques d’utilisation.</p><p>**Sur la base de ce que vous avez appris, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer des projets ou des composants inutilisés, ou former les utilisateurs et utilisatrices aux fonctionnalités les plus populaires.</p> |
| **Content Analytics** | Découvrez le contenu et les attributs de contenu les plus performants.<p>**Cela peut vous aider** à découvrir comment votre contenu se comporte à un niveau granulaire. Vous pouvez examiner les performances de ressources individuelles ou d’attributs spécifiques. Content Analytics utilise l’IA pour générer automatiquement des attributs et baliser votre contenu avec ceux-ci. Pour plus d’informations, consultez [Content Analytics](/help/content-analytics/content-analytics.md){target="_blank"}.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme promouvoir des ressources hautement performantes sur votre page d’accueil, personnaliser le contenu pour des segments spécifiques afin d’inclure des attributs hautement performants ou remplacer le contenu qui a commencé à devenir obsolète.</p> |

### Web : conversion {#web-conversion}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="Affichez le nombre de visites associées à chaque catégorie de produits sur votre site. Cela s’avère utile pour les implémentations qui utilisent la variable Produits et qui souhaitent afficher les mesures relatives à la catégorie du produit. Il est possible que la dimension qui renseigne ce modèle reste délibérément vide si votre site ne contient aucun produit."
>abstract="**Cela peut vous aider** à mieux comprendre les produits les plus vendus ou les plus consultés. &lt;/br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme mesurer l’efficacité d’une campagne marketing pour un produit donné.<br/>Ce modèle utilise la dimension Catégorie et la mesure Visites. "

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Consultez les informations préconfigurées pour les détaillants sur vos activités commerciales afin de contribuer à l’amélioration de vos ventes. Il s’adresse principalement aux utilisateurs et utilisatrices d’Adobe Commerce, mais n’importe quel détaillant en ligne peut l’utiliser."
>abstract="**Cela peut vous aider** à mieux comprendre comment vos activités commerciales contribuent aux chiffres de vente.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme ajuster les budgets aux activités qui obtiennent le meilleur retour sur investissement."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Affichez la conversion de produit dans une visualisation en entonnoir qui affiche les paniers, les passages en caisse et les commandes. Vous pouvez également afficher les pourcentages de conversion, les moyennes de chiffres d’affaires, les moyennes d’unités et les moyennes de commandes."
>abstract="**Cela peut vous aider** à mieux comprendre la progression et l’abandon des personnes au cours du processus de conversion.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer votre site web pour faciliter un processus de passage en caisse plus fluide."

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Identifiez les produits les plus performants."
>abstract="**Cela peut vous aider** à mieux comprendre les produits les plus performants.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.<br/>Ce modèle utilise les mesures Vues de produits, Ajouts au panier, Commandes, Revenus et Unités. Il utilise également la dimension Produit."

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Permet d’afficher le nombre de fois où des personnes ont effectué des événements de passage en caisse clés, tels que l’ajout d’articles dans leur panier, l’affichage de leur panier, la suppression d’articles de leur panier et le paiement."
>abstract="**Cela peut vous aider** à mieux comprendre quelles parties de l’entonnoir du processus de passage en caisse mènent à la conversion et lesquelles sont plus susceptibles de provoquer un abandon de panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme réduire le point de friction à certaines étapes du processus de passage en caisse.<br/>Ce modèle utilise la"

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="vue du nombre de personnes qui ont ajouté un produit à leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes qui ajoutent un produit à leur panier, par opposition au nombre total de produits qui sont ajoutés à un panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme mesurer l’efficacité de vos pages produits.<br/>Ce modèle utilise la mesure Paniers."

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Permet d’afficher le nombre de fois où les personnes ont consulté leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre l’expérience de passage en caisse afin de réduire les taux d’abandon de panier ou d’analyser le temps entre les ajouts au panier et les passages en caisse pour différents produits.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des promotions d’offres pour les produits qui restent dans le panier le plus longtemps et qui présentent le plus grand risque d’abandon.<br/>Ce modèle utilise la mesure Vues du panier."

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Affichez le nombre de fois où des personnes ont ajouté un article à leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle l’intérêt pour un produit est suffisamment élevé pour que les personnes l’ajoutent au panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les recommandations de produits pour l’ensemble de la clientèle. Pour ce faire, vous pouvez analyser les produits qui sont fréquemment ajoutés aux mêmes paniers et suggérer les produits associés en fonction des articles déjà présents dans le panier."

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Affichez le nombre de fois où des personnes ont supprimé un article de leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle les personnes ne sont plus intéressées par un produit, ou encore vous aider à comprendre où des problèmes peuvent se produire dans le processus de passage en caisse.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer les obstacles potentiels qui peuvent exister dans le processus de passage en caisse, comme une expérience client compliquée.<br/>Ce modèle utilise la mesure Retraits du panier."

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Affichez la conversion d’achat dans une visualisation en entonnoir qui affiche les sessions, les paniers et les commandes. Vous pouvez également afficher les pourcentages de conversion, les moyennes de chiffres d’affaires, les moyennes d’unités et les moyennes de commandes."
>abstract="**Cela peut vous aider** à mieux comprendre la progression et l’abandon des personnes au cours du processus de conversion.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer votre site web pour faciliter un processus de passage en caisse plus fluide."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Entonnoir de conversion de produit**] | Affichez la conversion de produit dans une visualisation en entonnoir qui affiche les paniers, les passages en caisse et les commandes. Vous pouvez également afficher les pourcentages de conversion, les moyennes de chiffres d’affaires, les moyennes d’unités et les moyennes de commandes.<p>**Cela peut vous aider** à mieux comprendre la progression et l’abandon des personnes au cours du processus de conversion.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer votre site web pour faciliter un processus de passage en caisse plus fluide.</p> |
| **Produits** | Affichez les produits qui stimulent les mesures clés, tels que les articles les plus vendus ou les plus consultés. <p>**Cela peut vous aider** à mieux comprendre les produits les plus performants.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.</p><p>Ce modèle utilise la mesure Commandes et la dimension Produit. |
| **Performance du produit** | Identifiez les produits les plus performants.<p>**Cela peut vous aider** à mieux comprendre les produits les plus performants.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.</p><p>Ce modèle utilise les mesures Vues de produits, Ajouts au panier, Commandes, Chiffre d’affaires et Unités. Il utilise également la dimension Produit. |
| **Entonnoir de conversion de panier** | Permet d’afficher le nombre de fois où des personnes ont effectué des événements de passage en caisse clés, tels que l’ajout d’articles dans leur panier, l’affichage de leur panier, la suppression d’articles de leur panier et le paiement. <p>**Cela peut vous aider** à mieux comprendre quelles parties de l’entonnoir du processus de passage en caisse mènent à la conversion et lesquelles sont plus susceptibles de provoquer un abandon de panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme réduire le point de friction à certaines étapes du processus de passage en caisse.</p> |
| **Paniers** | vue du nombre de personnes qui ont ajouté un produit à leur panier.<p>**Cela peut vous aider** à mieux comprendre le nombre de personnes qui ajoutent un produit à leur panier, par opposition au nombre total de produits qui sont ajoutés à un panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme mesurer l’efficacité de vos pages produits.</p><p>Ce modèle utilise la mesure Paniers. |
| **Consultations du panier** | Permet d’afficher le nombre de fois où les personnes ont consulté leur panier. <p>**Cela peut vous aider** à mieux comprendre l’expérience de passage en caisse afin de réduire les taux d’abandon de panier ou d’analyser le temps entre les ajouts au panier et les passages en caisse pour différents produits.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des promotions d’offres pour les produits qui restent dans le panier le plus longtemps et qui présentent le plus grand risque d’abandon.</p><p>Ce modèle utilise la mesure Vues du panier. |
| **Ajouts au panier** | Affichez le nombre de fois où des personnes ont ajouté un article à leur panier. <p>**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle l’intérêt pour un produit est suffisamment élevé pour que les personnes l’ajoutent au panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les recommandations de produits pour l’ensemble de la clientèle. Pour ce faire, vous pouvez analyser les produits qui sont fréquemment ajoutés au même panier et suggérer les produits associés en fonction des articles déjà présents dans le panier. |
| **Retraits du panier** | Affichez le nombre de fois où des personnes ont supprimé un article de leur panier.<p>**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle les personnes ne sont plus intéressées par un produit, ou encore vous aider à comprendre où des problèmes peuvent se produire dans le processus de passage en caisse.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer les obstacles potentiels qui peuvent exister dans le processus de passage en caisse, comme une expérience client compliquée.</p><p>Ce modèle utilise la mesure Retraits du panier. |
| **Entonnoir de conversion d’achat** | Affichez la conversion d’achat dans une visualisation en entonnoir qui affiche les sessions, les paniers et les commandes. Vous pouvez également afficher les pourcentages de conversion, les moyennes de chiffres d’affaires, les moyennes d’unités et les moyennes de commandes.<p>**Cela peut vous aider** à mieux comprendre la progression et l’abandon des personnes au cours du processus de conversion.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer votre site web pour faciliter un processus de passage en caisse plus fluide.</p> |
| **Recettes** | <!--duplicated in Most popular section-->Affichez le nombre total de produits achetés dans l’ensemble des commandes.<p>**Cela peut vous aider** à mieux comprendre quels éléments de dimension ont contribué au chiffre d’affaires en combinant la mesure Revenus avec n’importe quelle dimension. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code de suivi ) qui ont contribué au chiffre d’affaires. </p><p>**En fonction de ce que vous avez appris, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les campagnes qui n’atteignent pas les objectifs de chiffre d’affaires auxquels vous vous attendiez.</p><p>Ce modèle utilise la mesure Chiffre d’affaires. |
| **Commandes** | <!--duplicated in Most popular section-->Affichez le nombre total d’événements d’achat effectués sur votre site. <p>**Cela peut vous aider** à mieux comprendre quels éléments de dimension ont contribué à une commande en combinant la mesure Commandes avec n’importe quelle dimension. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code de suivi ) qui ont contribué aux achats.</p><p>**En fonction de ce que vous avez appris, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les campagnes qui n’atteignent pas les cibles d’achat attendues. </p><p>Ce modèle utilise la mesure Commandes. |

### Web : audience {#web-audience}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="template--audienceOverview"
>title="Affichez les audiences représentées parmi les personnes qui visitent votre site."
>abstract="**Cela peut vous aider** entre autres à mieux comprendre les informations générales sur les audiences, leur origine (RTCDP, Customer Journey Analytics, etc.), le chevauchement des audiences.<br/>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme utiliser les données pour vous concentrer sur les efforts marketing pour ces audiences spécifiques, ou créer des expériences personnalisées pour les clients qui s’étendent sur plusieurs audiences.<br/> Ce modèle utilise les dimensions Nom de l’audience, Origine de l’audience, Nom de l’audience sortie et Origine de l’audience sortie ."

<!--AA only-->

>[!CONTEXTUALHELP]
>id="template--people"
>title="Affichez le nombre de personnes qui interagissent avec votre marque."
>abstract="**Cela peut vous aider** à mieux comprendre les tendances d’utilisation de votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme mesurer l’efficacité des efforts marketing récents pour générer de nouveaux visiteurs et visiteuses sur votre site."

>[!CONTEXTUALHELP]
>id="template--bots"
>title="Affichez les pages vues et les tendances concernant le trafic de robots sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre le volume de trafic de robots filtré à partir de vos rapports en fonction des règles de robots que vous avez configurées.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme continuer à surveiller l’activité de robots afin d’identifier de nouveaux modèles."

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="Affichez une comparaison des nouveaux visiteurs et visiteuses par rapport aux visiteurs et visiteuses réguliers."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité de votre site pour fidéliser la clientèle ou le taux d’acquisition de nouveaux clients et clientes.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme proposer des incitations pour les futurs achats aux nouveaux visiteurs et visiteuses afin de les encourager à revenir."

>[!CONTEXTUALHELP]
>id="template--personid"
>title="Affichez le comportement individuel des utilisateurs et utilisatrices sur différents canaux."
>abstract="**Cela peut vous aider** à mieux comprendre l’ensemble du parcours client et les interactions entre plusieurs points de contact.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme personnaliser les efforts marketing pour mieux cibler les préférences des utilisateurs et utilisatrices."

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Affichez les fuseaux horaires supérieurs des visiteurs et visiteuses qui accèdent à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre dans quels fuseaux horaires vivent vos visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme ajuster les activités de maintenance du site à des moments qui affecteront le moins de personnes possible."

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="Affichez une vue d’ensemble de l’emplacement des visiteurs et visiteuses dans une visualisation de carte."
>abstract="**Cela peut vous aider** à mieux comprendre où les visiteurs et visiteuses se trouvent lors de la visite de votre site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les ressources marketing là où vous constatez le plus d’intérêt et d’opportunité."

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Afficher les principaux domaines des visiteurs qui accèdent à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre de quelles organisations proviennent vos visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme cibler votre contenu pour vos clientes et clients les plus importants."

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Afficher les principaux domaines des visiteurs qui accèdent à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre de quelles organisations proviennent vos visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme cibler votre contenu pour vos clientes et clients les plus importants."

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Affichez les principales largeurs de navigateur que les visiteurs utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des largeurs de navigateur les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur."

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Affichez les principales hauteurs de navigateur que les visiteurs utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des hauteurs de navigateur les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur. "

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Affichez le nom des systèmes d’exploitation et de la version utilisés par les visiteurs et visiteuses pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les versions et les systèmes d’exploitation les plus courants utilisés par les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des principaux systèmes d’exploitation et des principales versions. Cela permet de maximiser les efforts de contrôle de la qualité."

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Affichez le nom des systèmes d’exploitation utilisés par les personnes pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les systèmes d’exploitation les plus courants utilisés par les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des principaux systèmes d’exploitation. Cela permet de maximiser les efforts de contrôle de la qualité."

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Opérateur de téléphonie mobile."

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Opérateur de téléphonie mobile."

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Affichez le nombre de visites d’une personne sur le site."
>abstract="**Cela peut vous aider** à mieux comprendre l’engagement des visiteurs et visiteuses lors de leur retour sur votre site. Cela s’applique à la durée de vie du visiteur ou de la visiteuse, quelle que soit la période du projet.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les efforts marketing pour les visiteurs et visiteuses réguliers.<br/>Ce modèle utilise la dimension Nombre de visites."

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Affichez le nombre de visiteurs et de visiteuses de votre site qui ont effectué 0 achat auparavant, 1 achat auparavant, 2 achats auparavant ou 3 achats ou plus auparavant."
>abstract="**Cela peut vous aider** à mieux comprendre comment votre site affecte le comportement d’achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme vous concentrer sur les visiteurs et visiteuses qui reviennent effectuer un achat, afin d’inciter un comportement similaire pour les nouveaux visiteurs et visiteuses.<br/>Ce modèle utilise la dimension Fidélisation de la clientèle."

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Affichez le nombre de jours entre la première visite des clientes et clients sur votre site et la date de leur achat. Par exemple, si un visiteur ou une visiteuse effectue un achat un jour après sa première visite, l’ensemble des visites ou événements ultérieurs appartiennent à l’élément de dimension 1 jour."
>abstract="**Cela peut vous aider** à mieux comprendre le temps nécessaire aux visiteurs et visiteuses pour effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme mettre à jour votre site pour favoriser une acquisition plus rapide.<br/>Ce modèle utilise la dimension Jours avant le premier achat."

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Affichez le temps écoulé entre l’accès actuel du visiteur ou de la visiteuse et son dernier achat à ce moment-là."
>abstract="**Cela peut vous aider** à mieux comprendre le comportement des visiteurs et visiteuses après leur achat sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme mettre à jour votre site pour favoriser les achats ultérieurs.<br/>Ce modèle utilise la dimension Jours depuis le dernier achat."

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Affichez les principales tailles d’écran des appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des tailles d’écran des appareils mobiles les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité."

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Affichez les principales hauteurs d’écran d’appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des hauteurs d’écran d’appareils mobiles les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité."

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Affichez les principales largeurs d’écran d’appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre comment le contenu s’affiche pour les visiteurs et visiteuses.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des largeurs d’écran d’appareils mobiles les plus courantes. Cela permet de maximiser les efforts de contrôle de la qualité."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--consentPolicyOverview"
>title="Permet d’afficher le pays d’origine des personnes consultant le site."
>abstract="**Cela peut vous aider** à mieux comprendre les pays les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues principales différentes.<br/>Ce modèle utilise la dimension Pays."

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Permet d’afficher le pays d’origine des personnes consultant le site."
>abstract="**Cela peut vous aider** à mieux comprendre les pays les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues principales différentes.<br/>Ce modèle utilise la dimension Pays."

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Affichez l’État d’origine des personnes accédant au site (aux États-Unis). Cette fonction est similaire au modèle Géocalisation des régions, sauf qu’il est propre aux États-Unis."
>abstract="**Cela peut vous aider** à mieux comprendre les États nord-américains les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces États.<br/>Ce modèle utilise la dimension États."

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Affichez la région géographique des personnes consultant le site. Une région est une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un État, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. "
>abstract="**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces régions ou vous assurer que l’expérience de votre site est optimale dans des régions qui ont des langues principales différentes. <br/>Ce modèle utilise les dimensions ID(variables/geocountry) et Régions. "

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Permet d’afficher la ville d’origine des personnes consultant le site."
>abstract="**Cela peut vous aider** à mieux comprendre les villes les plus populaires d’où proviennent les personnes accédant à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces villes. <br/>Ce modèle utilise la dimension Villes."

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Affichez les zones marketing désignées (DMA) aux États-Unis d’où proviennent les personnes qui visitent le site."
>abstract="**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes qui visitent votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans les régions les plus performantes. "

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Affichez les principales langues dans lesquelles les personnes préfèrent voir le contenu."
>abstract="**Cela peut vous aider** à mieux comprendre les langues les plus fréquemment préférées des personnes.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que des actions de localisation ou de marketing pour les langues les plus populaires.<br/>Ce modèle utilise la dimension Langue."

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Affichez des informations relatives à la technologie utilisée par les personnes pour accéder à votre site, telles que les systèmes d’exploitation, les navigateurs et les appareils."
>abstract="**Cela peut vous aider** à mieux comprendre les technologies les plus utilisées lors de l’accès à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les technologies utilisées."

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Affichez le nom et la version des principaux navigateurs utilisés par les personnes pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les personnes.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur."

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Affichez les noms des organisations qui ont créé les principaux navigateurs que les personnes utilisent pour accéder à votre site. Cela diffère du modèle Navigateurs dans la mesure où il ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts."
>abstract="**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants que les personnes utilisent.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité. <br/>Ce modèle utilise la dimension Type de navigateur. "


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| **[!UICONTROL Présentation des audiences]** | Affichez les audiences représentées parmi les personnes qui visitent votre site.<p>**Cela peut vous aider** entre autres à mieux comprendre les informations générales sur les audiences, leur origine (RTCDP, Customer Journey Analytics, etc.), le chevauchement des audiences.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme utiliser les données pour vous concentrer sur les efforts marketing pour ces audiences spécifiques, ou créer des expériences personnalisées pour les clients qui s’étendent sur plusieurs audiences.</p><p>Ce modèle utilise les dimensions Nom de l’audience, Origine de l’audience, Nom de l’audience sortie et Origine de l’audience sortie .</p><p>Pour plus d’informations, voir [Analyse des audiences Experience Platform dans Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).</p> |
| [!UICONTROL **Visiteurs et visiteuses nouveaux et récurrents**] | Affichez une comparaison des nouveaux visiteurs et visiteuses par rapport aux visiteurs et visiteuses réguliers. <p>**Cela peut vous aider** à mieux comprendre l’efficacité de votre site pour fidéliser la clientèle ou le taux d’acquisition de nouveaux clients et clientes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme proposer des incitations pour les futurs achats aux nouveaux visiteurs et visiteuses afin de les encourager à revenir.</p><!-- This template uses the --> |
| **ID de personne** | Affichez le comportement individuel des utilisateurs et utilisatrices sur différents canaux.<p>**Cela peut vous aider** à mieux comprendre l’ensemble du parcours client et les interactions entre plusieurs points de contact.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme personnaliser les efforts marketing pour mieux cibler les préférences des utilisateurs et utilisatrices.</p><!-- This template uses the --> |
| **Pays géographiques** | Permet d’afficher le pays d’origine des personnes consultant le site.<p>**Cela peut vous aider** à mieux comprendre les pays les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues principales différentes.</p><p>Ce modèle utilise la dimension Pays. </p> |
| **États américains géographiques** | Affichez l’État d’origine des personnes accédant au site (aux États-Unis). Cette fonction est similaire au modèle Géocalisation des régions, sauf qu’il est propre aux États-Unis.<p>**Cela peut vous aider** à mieux comprendre les États nord-américains les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces États.</p><p>Ce modèle utilise la dimension États américains. </p> |
| **Régions géographiques** | Affichez la région géographique des personnes consultant le site. Une région est une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un État, une province ou une préfecture. Dans d’autres, il peut s’agir d’un pays constitutif, d’un département ou d’une région métropolitaine. <p>**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces régions ou vous assurer que l’expérience de votre site est optimale dans des régions qui ont des langues principales différentes. </p><p>Ce modèle utilise les dimensions ID(variables/geocountry) et Régions. </p> |
| **Villes géographiques** | Permet d’afficher la ville d’origine des personnes consultant le site. <p>**Cela peut vous aider** à mieux comprendre les villes les plus populaires d’où proviennent les personnes accédant à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces villes. </p><p>Ce modèle utilise la dimension Villes. </p> |
| **DMA géographique US** | Affichez les zones marketing désignées (DMA) aux États-Unis d’où proviennent les personnes qui visitent le site.<p>**Cela peut vous aider** à mieux comprendre les régions les plus populaires d’où proviennent les personnes qui visitent votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans les régions les plus performantes. </p><!-- This template uses the --> |
| **Langues** | Affichez les principales langues dans lesquelles les personnes préfèrent voir le contenu. <p>**Cela peut vous aider** à mieux comprendre les langues les plus fréquemment préférées des personnes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que des actions de localisation ou de marketing pour les langues les plus populaires.</p><p>Ce modèle utilise la dimension Langue.</p> |
| **Vue d’ensemble de la technologie** | Affichez des informations relatives à la technologie utilisée par les personnes pour accéder à votre site, telles que les systèmes d’exploitation, les navigateurs et les appareils. <p>**Cela peut vous aider** à mieux comprendre les technologies les plus utilisées lors de l’accès à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les technologies utilisées.</p> |
| **Navigateurs** | Affichez le nom et la version des principaux navigateurs utilisés par les personnes pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les personnes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité.</p><p>Ce modèle utilise la dimension Navigateur. </p> |
| **Types de navigateur** | Affichez les noms des organisations qui ont créé les principaux navigateurs que les personnes utilisent pour accéder à votre site. Cela diffère du modèle Navigateurs dans la mesure où il ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.<p>**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les personnes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité. </p><p>Ce modèle utilise la dimension Type de navigateur. </p> |

### Web : acquisition {#web-acquisition}

<!--AA only-->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Affichez la manière dont votre site web obtient les visiteurs et visiteuses sur des appareils mobiles."
>abstract="**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux les plus efficaces.<br/>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Il utilise également les dimensions suivantes : Moteur de recherche, Mot-clé de recherche, Page d’accès, Domaine référent, Code de suivi et Référent."

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Affichez côte à côte toutes vos données de référencement payant Google et Bing."
>abstract="**Cela peut vous aider** à mieux comprendre le volume de trafic envoyé vers votre site et si les clientes et clients se convertissent.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme estimer le rapport coût-efficacité d’une campagne publicitaire."

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Affichez la page des résultats de recherche sur laquelle un visiteur ou une visiteuse a cliqué pour accéder à votre site. Par exemple, si votre site apparaît sur la deuxième page de résultats d’un moteur de recherche, l’élément de dimension de cette variable est Page de recherche 2."
>abstract="**Cela peut vous aider** à mieux comprendre le classement de vos pages dans les résultats de recherche.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer votre stratégie SEO pour vous assurer que votre contenu s’affiche sur la première page des résultats de la recherche."


<!--Both AA and CJA-->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="Lors de l’utilisation de l’attribution personnalisée, ce modèle indique comment les personnes arrivent sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les canaux marketing les plus efficaces.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple investir plus massivement dans des canaux marketing efficaces et désinvestir des canaux marketing moins efficaces.<br/>Ce modèle utilise la dimension ID (variables/marketingchannel) et la mesure Chiffre d’affaires."

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Affichez le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut)."
>abstract="**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic initial vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing dans les domaines les plus efficaces.<br/>Ce modèle utilise la dimension Canal Première touche."

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Affichez des détails sur le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut)."
>abstract="**Cela peut vous aider** à mieux comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si une personne arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing dans les domaines les plus efficaces.<br/>Ce modèle utilise la dimension Détails du canal Première touche."

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Affichez le nombre de clics et de passages en caisse pour vos campagnes."
>abstract="**Cela peut vous aider** à mieux comprendre comment les campagnes marketing génèrent des conversions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme déterminer quelles campagnes marketing génèrent le meilleur retour sur investissement."

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Affichez les détails sur les performances de vos campagnes marketing."
>abstract="**Cela peut vous aider** à mieux comprendre les différents indicateurs de succès associés aux campagnes, tels que le chiffre dʼaffaires, les affichages de produits, les commandes, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de chiffre dʼaffaires. <br/>Ce modèle utilise la mesure Chiffre dʼaffaires, la mesure Vues de produits, la mesure Ajouts au panier, la mesure Commandes et la mesure Unités. Il utilise également la dimension Code de suivi et la dimension Domaine référent."

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Affichez la manière dont votre site web gagne des visiteurs et visiteuse."
>abstract="**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux les plus efficaces.<br/>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Il utilise également les dimensions suivantes : Moteur de recherche, Mot-clé de recherche, Page d’accès, Domaine référent, Code de suivi et Référent."

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qu’ils soient payants ou naturels."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et rectifier les lacunes d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.<br/>Ce modèle utilise la dimension Mot-clé de recherche."

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et rectifier les lacunes d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site. <br/>Ce modèle utilise la dimension Mot-clé de recherche - Payant. "

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et rectifier les lacunes d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.<br/>Ce modèle utilise la dimension Mot-clé de recherche - Naturel. "

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, que cela soit payant ou naturel."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.<br/>Ce modèle utilise la dimension Moteur de recherche. "

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site. <br/>Ce modèle utilise la dimension Moteur de recherche - Payant."

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.<br/>Ce modèle utilise la dimension Moteur de recherche - Naturel."

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Affichez les domaines sur lesquels les personnes cliquent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre. (Un lien doit exister sur le site externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principaux domaines référents. <br/>Ce modèle utilise la dimension Domaine référent."

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Affichez le premier domaine référent sur lequel les personnes ont cliqué pour accéder à votre site. (Un fois défini, il contient la même valeur pour toute la durée de vie de cet identifiant visiteur.)"
>abstract="**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principaux domaines référents d’origine. <br/>Ce modèle utilise la dimension Domaine référent d’origine."

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Affichez les URL sur lesquelles les personnes ont cliqué pour accéder à votre site. (Un lien doit exister sur l’URL externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)"
>abstract="**Cela peut vous aider** à mieux comprendre quelles URL spécifiques génèrent le plus de trafic vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principales URL. <br/>Ce modèle utilise la dimension Domaine référent.</p>"

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Affichez les canaux génériques sur lesquels les personnes ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque canal. Les canaux possibles sont les moteurs de recherche, les réseaux sociaux, d’autres sites web, le disque dur ou les e-mails."
>abstract="**Cela peut vous aider** à mieux comprendre quel type de référents génère le plus de trafic vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant d’un certain canal.<br/>Ce modèle utilise la dimension Type de référent."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Rapport de vue d’ensemble de canal**] | Lors de l’utilisation de l’attribution personnalisée, ce modèle indique comment les personnes arrivent sur votre site.<p>**Cela peut vous aider** à mieux comprendre les canaux marketing les plus efficaces.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple investir plus massivement dans des canaux marketing efficaces et désinvestir des canaux marketing moins efficaces.</p><p>Ce modèle utilise la dimension ID (variables/marketingchannel) et la mesure Chiffre d’affaires.</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Canal Première touche**] | Affichez le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut). <p>**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic initial vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Canal Première touche.</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Détails du canal Première touche**] | Affichez des détails sur le premier canal marketing auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si une personne arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Détails du canal Première touche.</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Canal Dernière touche**] | Affichez le canal marketing le plus récent auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic vers votre site menant à des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Canal Dernière touche.  </p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Détails du canal Dernière touche**] | Affichez des détails sur le canal marketing le plus récent auquel une personne correspond au cours de la période d’engagement de cette personne (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si une personne arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing dans les domaines les plus efficaces. </p><p>Ce modèle utilise la dimension Détails du canal Dernière touche. </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Code de suivi**] | Affichez les noms des codes de suivi sur votre site. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet.<p>**Cela peut vous aider** à mieux comprendre quels liens ont généré le plus de trafic vers votre site. L’ajout de chaînes de requête de code de suivi est courant dans les e-mails, les publicités, les publications de médias sociaux et d’autres efforts marketing utilisés par votre organisation</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de chiffre dʼaffaires.</p><p>Ce modèle utilise la dimension Code de suivi. </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Entonnoir de conversion de campagne**] | Affichez le nombre de clics et de passages en caisse pour vos campagnes. <p>**Cela peut vous aider** à mieux comprendre comment les campagnes marketing génèrent des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme déterminer quelles campagnes marketing génèrent le meilleur retour sur investissement.</p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Performances de la campagne**] | Affichez les détails sur les performances de vos campagnes marketing.<p>**Cela peut vous aider** à mieux comprendre les différents indicateurs de succès associés aux campagnes, tels que le chiffre dʼaffaires, les affichages de produits, les commandes, etc.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de chiffre dʼaffaires. </p><p>Ce modèle utilise la mesure Chiffre dʼaffaires, la mesure Vues de produits, la mesure Ajouts au panier, la mesure Commandes et la mesure Unités. Il utilise également la dimension Code de suivi et la dimension Domaine référent. </p> |
| **Acquisition web** | Affichez la manière dont votre site web gagne des visiteurs et visiteuse.<p>**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux les plus efficaces.</p><p>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Il utilise également la dimension Moteur de recherche, la dimension Mot-clé de recherche, la dimension Page d’accès, la dimension Domaine référent, la dimension Code de suivi et la dimension Référent.  </p> |
| **Mots-clés de recherche - Tous** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qu’ils soient payants ou naturels. <p>**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et rectifier les lacunes d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.</p><p>Ce modèle utilise la dimension Mot-clé de recherche. </p> |
| **Mots-clés de recherche - Payant** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et rectifier les lacunes d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site. </p><p>Ce modèle utilise la dimension Mot-clé de recherche - Payant. </p> |
| **Mots-clés de recherche - Naturel** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les mots-clés que les personnes utilisent dans les recherches qui génèrent du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et rectifier les lacunes d’optimisation du moteur de recherche (SEO) entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.</p><p>Ce modèle utilise la dimension Mot-clé de recherche - Naturel. </p> |
| **Moteurs de recherche - Tous** | Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, que cela soit payant ou naturel. <p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.</p><p>Ce modèle utilise la dimension Moteur de recherche. </p> |
| **Moteurs de recherche - Payant** | Affichez les moteurs de recherche que les personnes utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site. </p><p>Ce modèle utilise la dimension Moteur de recherche - Payant. </p> |
| **Moteurs de recherche - Naturel** | Affichez les mots-clés de recherche que les personnes utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les personnes utilisent pour générer du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation du moteur de recherche (SEO) sur les moteurs de recherche qui génèrent le plus de trafic sur le site.</p><p>Ce modèle utilise la dimension Moteur de recherche - Naturel. </p> |
| **Domaines référents** | Affichez les domaines sur lesquels les personnes cliquent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre. (Un lien doit exister sur le site externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principaux domaines référents. </p><p>Ce modèle utilise la dimension Domaine référent. </p> |
| **Domaines référents d’origine** | Affichez le premier domaine référent sur lequel les personnes ont cliqué pour accéder à votre site. (Un fois défini, il contient la même valeur pour toute la durée de vie de cet identifiant visiteur.)<p>**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent le plus de trafic vers le vôtre.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principaux domaines référents d’origine. </p><p>Ce modèle utilise la dimension Domaine référent d’origine. </p> |
| **Référents** | Affichez les URL sur lesquelles se trouvaient les personnes lorsqu’elles ont effectué un clic pour accéder à votre site. (Un lien doit exister sur l’URL externe et une personne doit cliquer sur celui-ci pour afficher l’élément de dimension.)  <p>**Cela peut vous aider** à mieux comprendre quelles URL spécifiques génèrent le plus de trafic vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant des principales URL. </p><p>Ce modèle utilise la dimension Domaine référent. </p><p>Ce modèle utilise la dimension Référent. </p> |
| **Types de référents** | Affichez les canaux génériques sur lesquels les personnes ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque canal. Les canaux possibles sont les moteurs de recherche, les réseaux sociaux, d’autres sites web, le disque dur ou les e-mails.<p>**Cela peut vous aider** à mieux comprendre quel type de référents génère le plus de trafic vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des personnes provenant d’un certain canal.</p><p>Ce modèle utilise la dimension Type de référent.</p> |

### Mobile : application mobile {#mobile-app}

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="Affichez le nombre d’événements, de sessions et de personnes associés à chaque écran sur l’application mobile."
>abstract="**Cela peut vous aider** à mieux comprendre quels écrans de votre site sont les plus appréciés.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer le contenu des écrans les plus appréciés."

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="Affichez les actions que les personnes effectuent sur votre application mobile."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes utilisent votre application et le parti qu’elles en tirent.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme développer des fonctionnalités qui complètent ou améliorent celles qui sont les plus appréciées."


<!--CJA only-->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Affichez le nombre d’utilisateurs et d’utilisatrices, de lancements et de premiers lancements sur votre application, ainsi que la durée de session moyenne."
>abstract="**Cela peut vous aider** à mieux comprendre l’intensité de l’utilisation de votre application. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les performances de l’application, afin qu’elle puisse s’adapter à la quantité d’utilisation."

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Affichez les schémas d’utilisation dominants de votre application mobile."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes utilisent votre application. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la façon dont les personnes peuvent passer d’un écran à un autre pour cibler les workflows les plus courants."

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Affichez certaines des mesures d’application mobile les plus courantes."
>abstract="**Cela peut vous aider** à mieux comprendre les performances de base de votre application mobile.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme évaluer l’intégrité globale et les performances de votre application."

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Affichez les données de performances pour les messages in-app et les messages de notifications push de votre application."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes utilisent les fonctionnalités de messages in-app, ainsi que l’efficacité des notifications push pour générer du trafic vers votre application.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer l’expérience des notifications push et des messages in-app."

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Affichez les performances de votre application et l’endroit où les utilisateurs et utilisatrices rencontrent des problèmes."
>abstract="**Cela peut vous aider** à mieux comprendre si les personnes qui utilisent votre application rencontrent une lenteur ou une dégradation des performances. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme résoudre des problèmes existants ou améliorer les performances de l’application avant que des problèmes se produisent."

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Identifiez les clientes et clients les plus fidèles à votre application et leurs activités dans l’application."
>abstract="**Cela peut vous aider** à mieux comprendre comment vos plus fidèles clientes et clients utilisent votre application.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer vos efforts de marketing pour les fonctionnalités utilisées par vos plus fidèles clientes et clients."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Écrans de l’application mobile**] | Affichez le nombre d’événements, de sessions et de personnes associés à chaque écran sur l’application mobile.<p>**Cela peut vous aider** à mieux comprendre quels écrans de votre site sont les plus appréciés.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme améliorer le contenu des écrans les plus appréciés.</p><p>Ce modèle utilise les mesures Événements, Sessions, Personnes et Pourcentage de modification. Il utilise également la dimension Titre de page.</p> |
| **Actions de l’application mobile** | Affichez les actions que les personnes effectuent sur votre application mobile. <p>**Cela peut vous aider** à mieux comprendre comment les personnes utilisent votre application et le parti qu’elles en tirent.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme développer des fonctionnalités qui complètent ou améliorent celles qui sont les plus appréciées.</p><p>Ce modèle utilise les mesures Événements, Sessions, Personnes et Pourcentage de modification. |
| **Utilisation des applications mobiles** | Affichez le nombre d’utilisateurs et d’utilisatrices, de lancements et de premiers lancements sur votre application, ainsi que la durée de session moyenne.<p>**Cela peut vous aider** à mieux comprendre l’intensité de l’utilisation de votre application. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les performances de l’application, afin qu’elle puisse s’adapter à la quantité d’utilisation.</p><!-- This template uses the --> |
| **Parcours sur les applications mobiles** | Affichez les schémas d’utilisation dominants de votre application mobile. <p>**Cela peut vous aider** à mieux comprendre comment les personnes utilisent votre application. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la façon dont les personnes peuvent passer d’un écran à un autre pour cibler les workflows les plus courants. </p><!-- This template uses the --> |
| **Mesures sur les applications mobiles** | Affichez certaines des mesures d’application mobile les plus courantes. <p>**Cela peut vous aider** à mieux comprendre les performances de base de votre application mobile.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme évaluer l’intégrité globale et les performances de votre application.</p><!-- This template uses the --> |
| **Messages sur les applications mobiles** | Affichez les données de performances pour les messages in-app et les messages de notifications push de votre application.<p>**Cela peut vous aider** à mieux comprendre comment les personnes utilisent les fonctionnalités de messages in-app, ainsi que l’efficacité des notifications push pour générer du trafic vers votre application.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer l’expérience des notifications push et des messages in-app.</p><!-- This template uses the --> |
| **Performances des applications mobiles** | Affichez les performances de votre application et l’endroit où les utilisateurs et utilisatrices rencontrent des problèmes. <p>**Cela peut vous aider** à mieux comprendre si les personnes qui utilisent votre application rencontrent une lenteur ou une dégradation des performances. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme résoudre des problèmes existants ou améliorer les performances de l’application avant que des problèmes ne se produisent.</p><!-- This template uses the --> |
| **Rétention sur les applications mobiles** | Identifiez les clientes et clients les plus fidèles à votre application et leurs activités dans l’application. <p>**Cela peut vous aider** à mieux comprendre comment vos plus fidèles clientes et clients utilisent votre application.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer vos efforts de marketing pour les fonctionnalités utilisées par vos plus fidèles clientes et clients.</p><!-- This template uses the --> |

### Mobile : informations sur les appareils mobiles {#mobile-devices}

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Opérateur de téléphonie mobile."

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Affichez la marque et le modèle des appareils mobiles que les personnes utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les périphériques mobiles les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les appareils mobiles les plus courants.<br/>Ce modèle utilise la dimension Nom de l’appareil mobile."

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Affichez les types d’appareils mobiles que les personnes utilisent pour accéder à votre site, tels que les téléphones et tablettes."
>abstract="**Cela peut vous aider** à mieux comprendre les différents types d’appareils mobiles utilisés pour accéder à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les types d’appareils mobiles les plus utilisés.<br/>Ce modèle utilise la dimension Type d’appareil mobile."

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Affichez les fabricants qui produisent les appareils mobiles que les personnes utilisent pour accéder à votre site, comme Apple et Samsung."
>abstract="**Cela peut vous aider** à mieux comprendre les fabricants les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des capacités de différents fabricants afin d’assurer une expérience client fluide.<br/>Ce modèle utilise la dimension Fabricant mobile."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Opérateur de téléphonie mobile**] | Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les personnes utilisent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus appréciés parmi votre base d’utilisateurs et d’utilisatrices.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience client fluide.</p><p>Ce modèle utilise la dimension Opérateur de téléphonie mobile.</p> |
| **Appareils** | Affichez la marque et le modèle des appareils mobiles que les personnes utilisent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les périphériques mobiles les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les appareils mobiles les plus courants.</p><p>Ce modèle utilise la dimension Nom de l’appareil mobile.</p> |
| **Type d’appareil** | Affichez les types d’appareils mobiles que les personnes utilisent pour accéder à votre site, tels que les téléphones et tablettes.<p>**Cela peut vous aider** à mieux comprendre les différents types d’appareils mobiles utilisés pour accéder à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les types d’appareils mobiles les plus utilisés.</p><p>Ce modèle utilise la dimension Type d’appareil mobile.</p> |
| **Fabricant** | Affichez les fabricants qui produisent les appareils mobiles que les personnes utilisent pour accéder à votre site, comme Apple et Samsung.<p>**Cela peut vous aider** à mieux comprendre les fabricants les plus populaires parmi votre base d’utilisateurs et d’utilisatrices.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des capacités de différents fabricants afin d’assurer une expérience client fluide.</p><p>Ce modèle utilise la dimension Fabricant mobile.</p> |

### Tranches temporelles {#time-parting}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Affichez le nombre d’événements, de sessions et de personnes sur votre site, par minute. Si, par exemple, un rapport porte sur une seule journée, la première minute de chaque heure de la journée est regroupée dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les tendances à un niveau granulaire.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les ressources pour les périodes de pointe, à la minute près.<br/>Ce modèle utilise la dimension Minute de l’heure."

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par heure de la journée. Par exemple, si un rapport s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.<br/>Ce modèle utilise la dimension Heure de la journée."

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Affichez les événements, sessions et personnes sur votre site, répartis entre le matin et l’après-midi. Par exemple, si un rapport s’étend du 1er au 7 janvier, les heures matinales de chaque jour sont regroupées dans le même élément de dimension."
>abstract="* **Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.<br/>Ce modèle utilise la dimension Matin/Après-midi."

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jour de la semaine. Si, par exemple, un rapport porte sur le mois de janvier, chaque jour de la semaine est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les jours de la semaine où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.<br/>Ce modèle utilise la dimension Jour de la semaine."

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jour du mois. Si, par exemple, un rapport porte sur une année entière, chaque jour du mois est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les jours de chaque mois où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.<br/>Ce modèle utilise la dimension Jour du mois."

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jour de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque jour de l’année est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les jours de chaque année où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.<br/>Ce modèle utilise la dimension Jour de l’année."

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par jours de la semaine et week-ends. Si, par exemple, un rapport porte sur le mois de janvier, les jours de semaine et les week-ends sont regroupés dans des éléments de dimension distincts."
>abstract="**Cela peut vous aider** à mieux comprendre les différences entre les jours de la semaine et les week-ends sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme affecter davantage de personnel de votre centre d’appel les week-ends si le rapport indique que le trafic est plus élevé le week-end qu’en semaine.<br/>Ce modèle utilise la dimension Jour de la semaine/Week-end."

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par semaine de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque semaine est regroupée dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les semaines de l’année où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé, comme pendant les vacances.<br/>Ce modèle utilise la dimension Semaine de l’année."

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par mois de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque mois est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les mois où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux mois où le trafic est élevé, comme pendant les vacances.<br/>Ce modèle utilise la dimension Mois de l’année."

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Affichez les événements, sessions et personnes sur votre site, répartis par trimestre de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque trimestre est regroupé dans le même élément de dimension."
>abstract="**Cela peut vous aider** à mieux comprendre les trimestres où votre site est le plus souvent et le moins souvent visité.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme programmer le lancement des produits afin de stimuler les trimestres où le trafic est habituellement faible.<br/>Ce modèle utilise la dimension Trimestre de l’année."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Minute de l’heure**] | Affichez le nombre d’événements, de sessions et de personnes sur votre site, par minute. Si, par exemple, un rapport porte sur une seule journée, la première minute de chaque heure de la journée est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les tendances à un niveau granulaire.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les ressources pour les périodes de pointe, à la minute près.</p><p>Ce modèle utilise la dimension Minute de l’heure.</p> |
| **Heure de la journée** | Affichez les événements, sessions et personnes sur votre site, par heure de la journée. Par exemple, si un rapport s’étend du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.</p><p>Ce modèle utilise la dimension Heure de la journée.</p> |
| **Matin/après-midi** | Affichez les événements, sessions et personnes sur votre site, répartis entre le matin et l’après-midi. Par exemple, si un rapport s’étend du 1er au 7 janvier, les heures matinales de chaque jour sont regroupées dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre le moment de la journée où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les pics de trafic.</p><p>Ce modèle utilise la dimension Matin/Après-midi.</p> |
| **Jour de la semaine** | Affichez les événements, sessions et personnes sur votre site, répartis par jour de la semaine. Si, par exemple, un rapport porte sur le mois de janvier, chaque jour de la semaine est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de la semaine où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.</p><p>Ce modèle utilise la dimension Jour de la semaine.</p> |
| **Jour du mois** | Affichez les événements, sessions et personnes sur votre site, répartis par jour du mois. Si, par exemple, un rapport porte sur une année entière, chaque jour du mois est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de chaque mois où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.</p><p>Ce modèle utilise la dimension Jour du mois.</p> |
| **Jour de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par jour de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque jour de l’année est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de chaque année où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé.</p><p>Ce modèle utilise la dimension Jour de l’année.&lt;/> |
| **Jour ouvrable/week-end** | Affichez les événements, sessions et personnes sur votre site, répartis par jours de la semaine et week-ends. Si, par exemple, un rapport porte sur le mois de janvier, les jours de semaine et les week-ends sont regroupés dans des éléments de dimension distincts. <p>**Cela peut vous aider** à mieux comprendre les différences entre les jours de la semaine et les week-ends sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme affecter davantage de personnel de votre centre d’appel les week-ends si le rapport indique que le trafic est plus élevé le week-end qu’en semaine.</p><p>Ce modèle utilise la dimension Jour de la semaine/Week-end.</p> |
| **Semaine de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par semaine de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque semaine est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les semaines de l’année où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux jours où le trafic est élevé, comme pendant les vacances.</p><p>Ce modèle utilise la dimension Semaine de l’année.</p> |
| **Mois de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par mois de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque mois est regroupé dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les mois où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme adapter le personnel de votre centre d’appel aux mois où le trafic est élevé, comme pendant les vacances.</p><p>Ce modèle utilise la dimension Mois de l’année.</p> |
| **Trimestre de l’année** | Affichez les événements, sessions et personnes sur votre site, répartis par trimestre de l’année. Si, par exemple, un rapport porte sur plusieurs années, chaque trimestre est regroupé dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les trimestres où votre site est le plus souvent et le moins souvent visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme programmer le lancement des produits afin de stimuler les trimestres où le trafic est habituellement faible.</p><p>Ce modèle utilise la dimension Trimestre de l’année.</p> |

### Cross-canal {#cross-channel}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Affichez la répartition du trafic sur plusieurs canaux."
>abstract="**Cela peut vous aider** à mieux comprendre les canaux qui génèrent le plus de trafic et d’engagement. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts marketing sur les canaux qui permettent d’obtenir le meilleur retour sur investissement.<br/>Ce modèle utilise les mesures d’utilisateurs et d’utilisatrices, de session et d’événement."

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Découvrez comment le trafic web affecte le trafic du centre d’appel."
>abstract="**Cela peut vous aider** à mieux comprendre dans quelle mesure le contenu en libre-service de votre site web détourne le trafic vers votre centre d’appel.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer le contenu en libre-service afin de réduire le trafic vers votre centre d’appel ou mesurer le retour sur investissement de votre contenu en libre-service en calculant le montant économisé grâce à la diminution du nombre d’appels au service clientèle.<br/>Ce modèle utilise les mesures Sessions web, Sessions d’application mobile et Sessions cross-canal web+application."

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Affichez le trafic web et le trafic mobile ensemble."
>abstract="**Cela peut vous aider** à mieux comprendre la répartition du trafic web et mobile vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à l’expérience de votre application mobile lorsqu’elle atteint un certain niveau de trafic.<br/>Ce modèle utilise les mesures Sessions web, Sessions d’application mobile et Sessions cross-canal web+application."

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Affichez le trafic en ligne et hors ligne ensemble."
>abstract="**Cela peut vous aider** à mieux comprendre la répartition du trafic en ligne et hors ligne sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à votre expérience en ligne lorsqu’elle atteint un certain niveau de trafic."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Vue d’ensemble multicanaux**] | Affichez la répartition du trafic sur plusieurs canaux. <p>**Cela peut vous aider** à mieux comprendre les canaux qui génèrent le plus de trafic et d’engagement. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme concentrer les efforts de marketing sur les canaux qui permettent d’obtenir le meilleur retour sur investissement.</p><p>Ce modèle utilise les mesures Utilisateurs et utilisatrices, Session et Événement.</p> |
| **Web et application** | Affichez le trafic web et le trafic mobile ensemble.<p>**Cela peut vous aider** à mieux comprendre la répartition du trafic web et mobile vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à l’expérience de votre application mobile lorsqu’elle atteint un certain niveau de trafic.</p><p>Ce modèle utilise les mesures Sessions web, Sessions d’application mobile et Sessions cross-canal web et application.</p> |
| **En ligne/hors ligne** | Affichez le trafic en ligne et hors ligne ensemble.<p>**Cela peut vous aider** à mieux comprendre la répartition du trafic en ligne et hors ligne sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à votre expérience en ligne lorsqu’elle atteint un certain niveau de trafic.</p><!-- This template uses the ... --> |
| **Déviation du centre dʼappel** | Découvrez comment le trafic web affecte le trafic du centre d’appel.<p>**Cela peut vous aider** à mieux comprendre dans quelle mesure le contenu en libre-service de votre site web détourne le trafic vers votre centre d’appel.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer le contenu en libre-service afin de réduire le trafic vers votre centre d’appel ou mesurer le retour sur investissement de votre contenu en libre-service en calculant le montant économisé grâce à la diminution du nombre d’appels au service clientèle.</p><p>Ce modèle utilise les mesures Sessions web, Sessions d’application mobile et Sessions cross-canal web et application.</p> |

### Autres canaux {#other-channels}

>[!CONTEXTUALHELP]
>id="cja-template--callcenterdashboard"
>title="Affichez les données du centre d’appel, notamment pourquoi les clientes et clients ont appelé et combien de fois."
>abstract="**Cela peut vous aider** à mieux comprendre où les clientes et clients rencontrent des problèmes et où les ressources du centre d’appel sont dépensées.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme résoudre les problèmes de produit qui entraînent une augmentation du trafic du centre d’appel, ce qui améliore finalement la rentabilité du produit."

>[!CONTEXTUALHELP]
>id="cja-template--pointOfSale"
>title="Affichez les données sur les transactions de point de vente (POS), y compris le chiffre d’affaires généré, les commandes passées et les unités vendues. Ce modèle inclut également des visualisations qui affichent des informations sur les principaux magasins, les principaux produits et les principales catégories de produits, ainsi que sur les ventes en ligne et hors ligne."
>abstract="**Cela peut vous aider** à mieux comprendre quels sont vos produits les plus vendus dans les magasins et en ligne.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources marketing à vos produits et canaux dont les performances sont les meilleures."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-email"
>title="Découvrez comment les e-mails que vous concevez et envoyez à l’aide d’Adobe Journey Optimizer génèrent des abonnements, des membres du programme de fidélité et des opportunités de vente croisée."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité des e-mails que vous concevez et envoyez à l’aide d’Adobe Journey Optimizer.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme ajuster votre stratégie en matière d’e-mails pour une campagne par e-mail donnée."

>[!CONTEXTUALHELP]
>id="cja-template--survey"
>title="Affichez l’engagement client pour vos questionnaires. Affichez le nombre de débuts et d’achèvements, les questions et réponses principales, ainsi que le nombre de participantes et participants nouveaux et réguliers."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement et le taux de succès de vos questionnaires.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme ajuster les futurs questionnaires pour en améliorer la participation."

>[!CONTEXTUALHELP]
>id="cja-template--product-usage"
>title="Observez comment votre organisation utilise Customer Journey Analytics."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes de votre organisation qui utilisent Customer Journey Analytics, ainsi que la fréquence et les tendances d’utilisation au fil du temps. Vous pouvez également voir le nombre de projets créés et les détails de ces projets. Voyez les composants, les visualisations et les panneaux les plus utilisés, entre autres statistiques d’utilisation.<br/>**Sur la base de ce que vous avez appris, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer des projets ou des composants inutilisés, ou former les utilisateurs et utilisatrices aux fonctionnalités les plus populaires."


Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Tableau de bord du centre dʼappel**] | Affichez les données du centre d’appel, notamment pourquoi les clientes et clients ont appelé et combien de fois. <p>**Cela peut vous aider** à mieux comprendre où les clientes et clients rencontrent des problèmes et où les ressources du centre d’appel sont dépensées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme résoudre les problèmes de produit qui entraînent une augmentation du trafic du centre d’appel, ce qui améliore finalement la rentabilité du produit.</p> |
| **Point de vente** | Affichez les données sur les transactions de point de vente (POS), y compris le chiffre d’affaires généré, les commandes passées et les unités vendues. Ce modèle inclut également des visualisations qui affichent des informations sur les principaux magasins, les principaux produits et les principales catégories de produits, ainsi que sur les ventes en ligne et hors ligne. <p>**Cela peut vous aider** à mieux comprendre quels sont vos produits les plus vendus dans les magasins et en ligne.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme affecter plus de ressources marketing à vos produits et canaux dont les performances sont les meilleures.</p><p>Ce modèle utilise les mesures Utilisateurs et utilisatrices, Chiffre d’affaires et Commandes.</p> |
| **Analyse des e-mails Journey Optimizer** | Découvrez comment les e-mails que vous concevez et envoyez à l’aide d’Adobe Journey Optimizer génèrent des abonnements, des membres du programme de fidélité et des opportunités de vente croisée. <p>**Cela peut vous aider** à mieux comprendre l’efficacité des e-mails que vous concevez et envoyez à l’aide d’Adobe Journey Optimizer.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme ajuster votre stratégie en matière d’e-mails pour une campagne par e-mail donnée.</p> |
| **Enquête** | Affichez l’engagement client pour vos questionnaires. Affichez le nombre de débuts et d’achèvements, les questions et réponses principales, ainsi que le nombre de participantes et participants nouveaux et réguliers.<p>**Cela peut vous aider** à mieux comprendre les niveaux d’engagement et le taux de succès de vos questionnaires.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme ajuster les futurs questionnaires pour en améliorer la participation.</p><p>Ce modèle utilise les mesures Utilisateurs et utilisatrices, Événements, Début du questionnaire, Fin du questionnaire et Taux d’achèvement du questionnaire.</p> |
| **Vue d’ensemble de l’utilisation du produit** | Observez comment votre organisation utilise Customer Journey Analytics.<p>**Cela peut vous aider** à mieux comprendre le nombre de personnes de votre organisation qui utilisent Customer Journey Analytics, ainsi que la fréquence et les tendances d’utilisation au fil du temps. Vous pouvez également voir le nombre de projets créés et les détails de ces projets. Voyez les composants, les visualisations et les panneaux les plus utilisés, entre autres statistiques d’utilisation. [En savoir plus](/help/tools/product-usage/usage-overview.md)</p><p>**Sur la base de ce que vous avez appris, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer des projets ou des composants inutilisés, ou former les utilisateurs et utilisatrices aux fonctionnalités les plus populaires.</p> |

### Journey Optimizer {#AJO-templates}

<!--CJA only-->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Affichez les mesures essentielles pour vos campagnes Journey Optimizer, notamment les campagnes par e-mail, les expérimentations, les messages in-app, les SMS, etc."
>abstract="**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre campagne.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Affichez les mesures essentielles pour vos parcours Journey Optimizer, notamment les parcours par e-mail, les expérimentations, les messages in-app, les SMS, etc."
>abstract="**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre parcours.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Affichez le comportement des utilisateurs et utilisatrices, les schémas d’engagement, les taux de conversion et d’autres mesures clés."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité de votre landing page. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les performances de votre page de destination."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Affichez un résumé exhaustif des mesures de trafic et d’engagement pour l’ensemble des campagnes et des parcours de votre environnement."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité générale de vos campagnes et parcours. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes et parcours en fonction du niveau d’engagement de votre audience cible."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Affichez les abonnements et désabonnements des profils associés à des listes spécifiques."
>abstract="**Cela peut vous aider** à mieux comprendre l’efficacité de différentes initiatives et campagnes d’abonnement pour stimuler l’engagement et générer des conversions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes d’abonnement en fonction des niveaux d’engagement de votre audience cible."

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Campagnes Journey Optimizer**] | Affichez les mesures essentielles pour vos campagnes Journey Optimizer, notamment les campagnes par e-mail, les expérimentations, les messages in-app, les SMS, etc.<p>**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre campagne.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible.</p> |
| **Parcours Journey Optimizer** | Affichez les mesures essentielles pour vos parcours Journey Optimizer, notamment les parcours par e-mail, les expérimentations, les messages in-app, les SMS, etc.<p>**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous offre des informations complètes sur l’efficacité et le niveau d’engagement de votre parcours.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes en fonction du niveau d’engagement de votre audience cible.</p> |
| **Pages de destination Journey Optimizer** | Affichez le comportement des utilisateurs et utilisatrices, les schémas d’engagement, les taux de conversion et d’autres mesures clés.<p>**Cela peut vous aider** à mieux comprendre l’efficacité de votre page de destination. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les performances de votre landing page.</p> |
| **Rapport de vue d’ensemble de Journey Optimizer** | Affichez un résumé exhaustif des mesures de trafic et d’engagement pour l’ensemble des campagnes et des parcours de votre environnement.<p>**Cela peut vous aider** à mieux comprendre l’efficacité générale de vos campagnes et parcours. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes et parcours en fonction du niveau d’engagement de votre audience cible.</p> |
| **Abonnements Journey Optimizer** | Affichez les abonnements et désabonnements des profils associés à des listes spécifiques.<p>**Cela peut vous aider** à mieux comprendre l’efficacité de différentes initiatives et campagnes d’abonnement pour stimuler l’engagement et générer des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes d’abonnement en fonction des niveaux d’engagement de votre audience cible.</p> |

### Brand Concierge {#brand-concierge-templates}

>[!CONTEXTUALHELP]
>id="template--brand-concierge--concierge"
>title="Analysez l’interaction client à travers les schémas de conversation, les commentaires des utilisateurs et l’efficacité de vos recommandations."
>abstract="**Cela peut vous aider** à identifier les schémas d’engagement, à évaluer la qualité de la conversation, à suivre les tendances de satisfaction des clients et à mesurer l’efficacité des recommandations de liens.<br/>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme affiner les réponses de votre agent d’IA, développer du contenu ciblé pour les problèmes fréquents, améliorer les algorithmes de recommandation ou créer des parcours spécialisés pour différents segments d’utilisateurs."

>[!CONTEXTUALHELP]
>id="template--brand-concierge--meeting"
>title="Suivez le cycle de vie complet des demandes de réunion B2B. Surveillez les taux de conversion, les performances des consultants et identifiez vos canaux de génération de leads les plus efficaces."
>abstract="**Cela peut vous aider** à suivre les taux de conversion des réunions, à identifier les membres de l’équipe les plus performants, à comprendre les tendances saisonnières du comportement de réservation et à identifier les pages qui génèrent les demandes de réunion les plus importantes.<br/>**En fonction de ce que vous avez appris** vous pouvez faire un certain nombre de choses, comme optimiser votre processus de demande de réunion, redistribuer les ressources vers des pages à conversion élevée, développer une formation ciblée pour les consultants ayant des taux de réservation plus faibles, ou mettre en œuvre de nouvelles stratégies pour réduire les réunions manquées."

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| Présentation de [!UICONTROL **Brand Concierge**] | Analysez l’interaction client à travers les schémas de conversation, les commentaires des utilisateurs et l’efficacité de vos recommandations. <p>**Cela peut vous aider** à identifier les schémas d’engagement, à évaluer la qualité de la conversation, à suivre les tendances de satisfaction des clients et à mesurer l’efficacité des recommandations de liens.</p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme affiner les réponses de votre agent d’IA, développer du contenu ciblé pour les problèmes fréquents, améliorer les algorithmes de recommandation ou créer des parcours spécialisés pour différents segments d’utilisateurs.</p> |
| **Réunions B2B Brand Concierge** | Suivez le cycle de vie complet des demandes de réunion B2B. Surveillez les taux de conversion, évaluez les performances de réservation des consultants et identifiez vos canaux de génération de leads les plus efficaces. <p>**Cela peut vous aider** à suivre les taux de conversion des réunions, à identifier les membres de l’équipe les plus performants, à comprendre les tendances saisonnières du comportement de réservation et à identifier les URL de pages qui génèrent les demandes de réunion les plus importantes. </p><p>**En fonction de ce que vous avez appris** vous pouvez effectuer un certain nombre de tâches, comme optimiser votre processus de demande de réunion, redistribuer les ressources vers des URL de page à conversion élevée, développer une formation ciblée pour les consultants ayant des taux de réservation plus faibles, ou mettre en œuvre de nouvelles stratégies pour réduire les réunions manquées.</p> |


### Modèles B2B {#b2b-templates}

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}


<!-- CJA B2B Edition only -->

>[!CONTEXTUALHELP]
>id="cja-template--b2b-account-engagement"
>title="Découvrez l’activité de vos comptes par rapport aux événements, aux personnes et aux opportunités."
>abstract="**Cela peut vous aider** à mieux comprendre si l’engagement au niveau du compte est à la hausse ou à la baisse, à comparer l’activité entre les comptes et à décider où concentrer les efforts de fidélisation ou d’acquisition.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme recentrer votre attention sur les comptes moins engagés mais qui nécessitent plus d’attention en raison de leur importance."

>[!CONTEXTUALHELP]
>id="cja-template--b2b-opportunity-engagement"
>title="Suivez l’engagement au niveau des opportunités et retrouvez les offres qui gagnent en intérêt ou s’essoufflent."
>abstract="**Cela peut vous aider** à prévoir plus précisément la progression des offres et à cibler l’activation là où l’engagement atteint des pics ou se bloque.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déployer des efforts supplémentaires sur les transactions qui sont presque conclues et rechercher les raisons pour lesquelles d’autres transactions deviennent moins intéressantes."

>[!CONTEXTUALHELP]
>id="cja-template--b2b-buying-group-activity"
>title="Visualisez l’activité du groupe d’achat dans chaque compte pour informer le compte et les diffusions marketing du groupe d’achat."
>abstract="**Cela peut vous aider** à visualiser les groupes d’achat, et les personnes au sein de ces groupes d’achat, qui sont les plus engagés, ce qui met en évidence les lacunes en matière de participation du groupe.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme essayer de dialoguer davantage avec les personnes au sein des groupes d’achat qui ne semblent pas impliquées."

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Vue d’ensemble de l’engagement des comptes B2B**] | Découvrez l’activité de vos comptes par rapport aux événements, aux personnes et aux opportunités.<p>**Cela peut vous aider** à mieux comprendre si l’engagement au niveau du compte est à la hausse ou à la baisse, à comparer l’activité entre les comptes et à décider où concentrer les efforts de fidélisation ou d’acquisition.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme vous recentrer sur les comptes qui sont moins engagés mais qui nécessitent davantage d’attention en raison de leur importance.</p> |
| [!UICONTROL **Vue d’ensemble de l’engagement de l’opportunité B2B**] | Suivez l’engagement au niveau des opportunités et retrouvez les offres qui gagnent en intérêt ou s’essoufflent.<p>**Cela peut vous aider** à prévoir plus précisément la progression des offres et à cibler l’activation là où l’engagement atteint des pics ou se bloque.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déployer des efforts supplémentaires sur les transactions qui sont presque conclues et rechercher les raisons pour lesquelles d’autres transactions perdent en intérêt.</p> |
| [!UICONTROL **Activité du groupe d’achat B2B**] | Visualisez l’activité du groupe d’achat dans chaque compte pour informer le compte et les diffusions marketing du groupe d’achat.<p>**Cela peut vous aider** à visualiser les groupes d’achat, et les personnes au sein de ces groupes d’achat, qui sont les plus engagés, ce qui met en évidence les lacunes en matière de participation du groupe.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme essayer de dialoguer davantage avec les personnes au sein des groupes d’achat qui ne semblent pas impliquées.</p> |


### Modèles Mix Modeler {#mix-modeler-templates}

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- |
| [!UICONTROL **Informations sur le modèle incrémentiel de Mix Modeler**] | Affichez les informations des modèles sélectionnés générés par Mix Modeler.<p>**Cela peut vous aider** afin de mieux comprendre les informations incrémentielles des modèles générés dans Mix Modeler. <p>**En vous basant sur ces informations** vous serez en mesure de :<ul><li>Visualisez et quantifiez l’impact des activités marketing de votre organisation.</li><li>Identifiez les canaux les plus performants.</li><li>Identifiez les canaux qui peuvent nécessiter une optimisation.</li></ul></p> |

<!-- CJA only -->

>[!CONTEXTUALHELP]
>id="template--mixmodeler-incremental-models-insights"
>title="Affichez les informations des modèles sélectionnés générés par Mix Modeler."
>abstract="**Cela peut vous aider** afin de mieux comprendre les informations incrémentielles des modèles générés dans Mix Modeler. <br/>**En vous basant sur ces informations** vous serez en mesure de :<ul><li>Visualisez et quantifiez l’impact des activités marketing de votre organisation.</li><li>Identifiez les canaux les plus performants.</li><li>Identifiez les canaux qui peuvent nécessiter une optimisation.</li></ul>"
