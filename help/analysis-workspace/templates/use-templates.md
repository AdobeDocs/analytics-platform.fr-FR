---
description: Présentation de l’utilisation des modèles par défaut dans Analysis Workspace.
title: Utiliser des modèles
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 9f2f79e264d9cdd460751c50fe252bb7237682fd
workflow-type: tm+mt
source-wordcount: '13206'
ht-degree: 3%

---

# Utiliser des modèles

Les modèles (ou modèles d’entreprise) dans Analysis Workspace fournissent des informations rapides sur les scénarios de création de rapports les plus courants. Voici quelques exemples de questions auxquelles vous pouvez répondre à l’aide de modèles :

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

1. Sélectionnez [!UICONTROL **Modèles**].

   ![Onglet Rapports.](assets/view-prebuilt-reports.png)

1. Dans le champ de recherche, commencez à saisir le nom du modèle à rechercher, puis sélectionnez-le dans la liste des modèles.

   Ou

   Sélectionnez la catégorie du modèle à afficher, puis choisissez le modèle dans la liste des modèles.

   >[!TIP]
   >
   >Pour naviguer dans le menu à l’aide des touches fléchées, appuyez sur la touche Barre oblique (/), puis sur la touche Flèche vers le bas. Appuyez sur Entrée pour charger le modèle sélectionné.

   Pour obtenir la liste des modèles disponibles, reportez-vous à la section [Modèles disponibles](#available-templates) ci-dessous.

1. (Facultatif) Affichez et utilisez des modèles qui contiennent des composants qui ne sont pas disponibles dans votre vue de données. (Par défaut, les seuls modèles affichés sont ceux qui utilisent des composants disponibles dans votre vue de données.)

   1. Sélectionnez (nom de l’option de filtre ?) pour afficher les modèles qui nécessitent des composants supplémentaires.

      <!-- add screenshot -->

   1. Sélectionnez le modèle à utiliser.

   1. Si le modèle contient des composants qui ne sont pas disponibles dans votre vue de données, un message s’affiche, indiquant les composants manquants. Cliquez sur (bouton ?) pour accéder à la vue de données dans laquelle vous pouvez les créer automatiquement. <!--how do you do this? Walk through the process -->

1. Sélectionnez le modèle pour créer un rapport à partir du modèle que vous avez choisi.

## Personnaliser et enregistrer un modèle {#use-reports}

Un modèle peut ne pas répondre exactement à vos besoins, mais il peut vous rapprocher. Dans ce cas, vous pouvez utiliser le modèle comme point de départ, puis le personnaliser selon vos besoins spécifiques.

Si vous quittez un modèle après avoir apporté des modifications, vous êtes invité à enregistrer ou ignorer vos modifications. L’enregistrement des modifications dans un modèle enregistre le modèle en tant que nouveau projet.

Pour personnaliser et enregistrer un modèle :

1. Dans Adobe Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**].

1. Sélectionnez l’onglet [!UICONTROL **Modèles**] .

1. Sélectionnez le modèle à afficher. Par exemple, sous [!UICONTROL **Les plus populaires**], sélectionnez le rapport [!UICONTROL **Pages**].

   Le modèle Pages, tel qu’il s’affiche dans Analysis Workspace, affiche deux [ visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Graphique à barres](/help/analysis-workspace/visualizations/bar.md) et [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md)) et un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La mesure utilisée est Occurrences.

   ![Modèle de pages](assets/pages-report.png)

1. Effectuez l’une des opérations suivantes :

   * Affichez le modèle.
   * Faites glisser un ou plusieurs segments dans la zone de dépôt de segments située en haut. Par exemple, faites glisser le segment [!UICONTROL **Clients mobiles**] et observez les résultats.
   * Modifiez la période en accédant au calendrier en haut à droite.
   * Ajoutez des ventilations de dimension, faites glisser d’autres mesures et personnalisez généralement le modèle en fonction de vos besoins.

1. (Facultatif) Enregistrez le modèle en tant que projet en sélectionnant [!UICONTROL **Projet**] > [!UICONTROL **Enregistrer**].

   Le modèle est enregistré comme un nouveau projet ; il ne modifie pas le rapport existant. Pour plus d’informations sur l’enregistrement d’un rapport en tant que projet, voir [Enregistrer des projets](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Modèles disponibles

Pour accéder à tous les modèles prédéfinis disponibles :

1. Dans Adobe Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**], puis l’onglet [!UICONTROL **Modèles**].

   Les modèles prédéfinis sont organisés par catégorie.

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

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--training"
>title="Modèle de tutoriel de formation"
>abstract="Découvrez la terminologie et les étapes courantes d’Analysis Workspace pour créer votre première analyse."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pagesRankedReport"
>title="Identifiez les pages les plus populaires et les moins populaires."
>abstract="**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui les intéressent le plus.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pageViewsOvertimeReport"
>title="Afficher le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. "
>abstract="**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic des vacances d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Pages vues."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitsOvertimeReport"
>title="Afficher le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic des vacances d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitorsOvertimeReport"
>title="Afficher le nombre total de visiteurs uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. "
>abstract="**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les vacances d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Visiteurs uniques. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--keyMetricsReport"
>title="Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de visiteurs uniques sur le site, du nombre de visites de pages et du nombre de sessions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. <br/>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--siteSectionRankedReport"
>title="Affichez les sections les plus populaires ou les plus performantes de votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les sections de votre site les plus visitées.<br>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.<br/>Ce modèle utilise la dimension Section du site et la mesure Visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--next-page-report"
>title="Afficher les endroits les plus courants où les visiteurs se rendent immédiatement après leur visite ou juste avant de visiter un certain endroit."
>abstract="**Cela peut vous aider** à comprendre comment le trafic passe d’une page donnée à d’autres parties de votre site, et comprendre les chemins empruntés par les visiteurs pour atteindre une page donnée.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si la conception ou la mise en page peut être optimisée pour diriger les visiteurs vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser une révision. Ou évaluez si les informations de la page active sont susceptibles de fournir la direction ou les actions que les gens recherchent lorsqu’ils arrivent des pages précédentes. Vous pouvez également déterminer si les pages qui ne s’affichent pas comme des pages précédentes ont besoin de liens plus proéminents vers la page actuelle.<br/> Ce modèle utilise le panneau Suivant ou Article précédent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignRankedReport"
>title="Afficher les liens qui ont généré le plus de trafic vers votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les codes de suivi (et les liens auxquels ils sont associés) qui ont été les plus utilisés pour accéder à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster votre stratégie en fonction de l’endroit où vous ajoutez des liens à votre site.<br/>Ce modèle utilise la dimension Code de suivi et la mesure Visites."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productsRankedReport"
>title="Afficher le nombre de commandes par produit. Les données s’affichent sur une période donnée."
>abstract="**Cela peut vous aider** à comprendre les produits présentant la demande la plus élevée ou la plus faible.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos stratégies marketing pour promouvoir des produits hautement performants ou améliorer ou arrêter les produits sous-performants. Vous pouvez également ajuster votre inventaire de produits en fonction de votre analyse des données.<br/>Ce modèle utilise la dimension Produit et la mesure Commandes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelRankedReport"
>title="Afficher les canaux marketing les plus récents avec lesquels les visiteurs correspondent pendant leur période d’engagement (30 jours par défaut)."
>abstract="**Cela peut vous aider** à comprendre les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.<br/>Ce modèle utilise la dimension Canal Dernière touche et la mesure Visiteurs uniques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelDetailRankedReport"
>title="Affichez les détails sur les canaux marketing les plus récents avec lesquels les visiteurs correspondent pendant leur période d’engagement (30 jours par défaut)."
>abstract="**Cela peut vous aider** à comprendre non seulement les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions, mais aussi des détails sur ces canaux marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.<br/>Ce modèle utilise la dimension Détails du canal Dernière touche et la mesure Visiteurs uniques. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--revenueOvertimeReport"
>title="Afficher la valeur monétaire des produits achetés dans toutes les commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à comprendre comment les recettes augmentent ou diminuent au fil du temps. Vous pouvez associer cette mesure à n’importe quelle dimension pour savoir quels éléments de dimension ont contribué aux recettes.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des recettes futures du projet basées sur les tendances précédentes. Vous pouvez également ajouter une autre dimension, comme la dimension Code de suivi , pour savoir quelles campagnes génèrent le plus de recettes.<br/>Ce modèle utilise la dimension Jour et la mesure Recettes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ordersOvertimeReport"
>title="Afficher le nombre total d’événements d’achat. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre comment l’intérêt pour vos produits et services augmente ou diminue au fil du temps. Vous pouvez appliquer un segment pour identifier les clients ou les zones géographiques qui passent le plus de commandes et déterminer les tendances de ces commandes au fil du temps.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les commandes avant et après le lancement de la campagne. Vous pouvez également comparer des commandes de jours fériés d’une année à l’autre.<br/>Ce modèle utilise la dimension Jour et la mesure Commandes."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutoriel de formation**] | Découvrez la terminologie et les étapes courantes d’Analysis Workspace pour créer votre première analyse |
| [!UICONTROL **Pages**] | <!--duplicated in Engagement section--> Identifiez les pages les plus populaires et les moins populaires. <p>**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui les intéressent le plus.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.</p><p>Ce modèle utilise la dimension Page et la mesure Pages vues .</p> |
| [!UICONTROL **Pages vues**] | <!--duplicated in Engagement section--> Afficher le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic des vacances d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Pages vues.</p> |
| [!UICONTROL **Visites Web**] | <!--duplicated in Engagement section--> Afficher le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic des vacances d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visites .</p> |
| [!UICONTROL **Visiteurs web**] | <!--duplicated in Engagement section--> Afficher le nombre total de visiteurs uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les vacances d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Mesures clés**] | <!--duplicated in Engagement section--> Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de visiteurs uniques sur le site, du nombre de visites de pages et du nombre de sessions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. </p><p>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Sections du site**] | Affichez les sections les plus populaires ou les plus performantes de votre site. <p>**Cela peut vous aider** à mieux comprendre les sections de votre site les plus visitées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.</p> <p>Ce modèle utilise la dimension Section du site et la mesure Visites .</p> |
| [!UICONTROL **Page suivante et page précédente**] | Afficher les endroits les plus courants où les visiteurs se rendent immédiatement après leur visite ou juste avant de visiter un certain endroit. <p>**Cela peut vous aider** à comprendre comment le trafic passe d’une page donnée à d’autres parties de votre site, et comprendre les chemins empruntés par les visiteurs pour atteindre une page donnée.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si la conception ou la mise en page peut être optimisée pour diriger les visiteurs vers des pages plus souhaitables, telles qu’une page pour effectuer un achat ou laisser une révision. Ou évaluez si les informations de la page active sont susceptibles de fournir la direction ou les actions que les gens recherchent lorsqu’ils arrivent des pages précédentes. Vous pouvez également déterminer si les pages qui ne s’affichent pas comme des pages précédentes ont besoin de liens plus proéminents vers la page actuelle.</p><p>Ce modèle utilise le panneau Suivant ou Elément précédent.</p> |
| [!UICONTROL **Campagnes (Code de suivi)**] | Afficher les liens qui ont généré le plus de trafic vers votre site. <p>**Cela peut vous aider** à mieux comprendre les codes de suivi (et les liens auxquels ils sont associés) qui ont été les plus utilisés pour accéder à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster votre stratégie en fonction de l’endroit où vous ajoutez des liens à votre site.</p><p>Ce modèle utilise la dimension Code de suivi et la mesure Visites .</p> |
| [!UICONTROL **Produits**] | Afficher le nombre de commandes par produit. Les données s’affichent sur une période donnée. <p>**Cela peut vous aider** à comprendre les produits présentant la demande la plus élevée ou la plus faible.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos stratégies marketing pour promouvoir des produits hautement performants ou améliorer ou arrêter les produits sous-performants. Vous pouvez également ajuster votre inventaire de produits en fonction de votre analyse des données.</p><p>Ce modèle utilise la dimension Produit et la mesure Commandes .</p> |
| [!UICONTROL **Canal marketing Dernière touche**] | Afficher les canaux marketing les plus récents avec lesquels les visiteurs correspondent pendant leur période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à comprendre les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.</p><p>Ce modèle utilise la dimension Canal Dernière touche et la mesure Visiteurs uniques .</p> |
| [!UICONTROL **Détails du canal marketing Dernière touche**] | Affichez les détails sur les canaux marketing les plus récents avec lesquels les visiteurs correspondent pendant leur période d’engagement (30 jours par défaut).<p>**Cela peut vous aider** à comprendre non seulement les canaux marketing les plus efficaces pour amener des personnes sur votre site qui génèrent des conversions, mais aussi des détails sur ces canaux marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme allouer plus de ressources à des canaux hautement performants ou allouer moins de ressources à des canaux peu performants.</p><p>Ce modèle utilise la dimension Détails du canal Dernière touche et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Recettes**] | <!--duplicated in Web Conversion section-->Afficher la valeur monétaire des produits achetés dans toutes les commandes. Les données sont affichées sur une période donnée et comparées à des périodes antérieures.<p>**Cela peut vous aider** à comprendre comment les recettes augmentent ou diminuent au fil du temps. Vous pouvez associer cette mesure à n’importe quelle dimension pour savoir quels éléments de dimension ont contribué aux recettes.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des recettes futures du projet basées sur les tendances précédentes. Vous pouvez également ajouter une autre dimension, comme la dimension Code de suivi , pour savoir quelles campagnes génèrent le plus de recettes.</p><p>Ce modèle utilise la dimension Jour et la mesure Recettes.</p> |
| [!UICONTROL **Commandes**] | <!--duplicated in Web Conversion section-->Afficher le nombre total d’événements d’achat. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment l’intérêt pour vos produits et services augmente ou diminue au fil du temps. Vous pouvez appliquer un segment pour identifier les clients ou les zones géographiques qui passent le plus de commandes et déterminer les tendances de ces commandes au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer l’efficacité d’une campagne marketing récemment lancée en comparant les commandes avant et après le lancement de la campagne. Vous pouvez également comparer des commandes de jours fériés d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Commandes .</p> |

### Web : engagement {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Permet d’afficher la durée moyenne passée par les visiteurs sur votre site au cours de chaque visite, ainsi que la durée moyenne passée par les utilisateurs avant un événement de succès. Les données sont affichées sur une période donnée et comparées à des périodes antérieures."
>abstract="**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et le temps nécessaire aux visiteurs pour effectuer l’action souhaitée, par exemple effectuer un achat.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des visiteurs à atteindre rapidement un événement de succès.<br/>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes), la dimension Jour et la mesure Durée de la visite (secondes)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-content-consumption"
>title="Permet de déterminer quel contenu web est le plus consommé et attire le plus d’utilisateurs."
>abstract="**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les visiteurs vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Elle utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--media-content-consumption"
>title="Permet de savoir quel contenu multimédia est le plus consommé et attire le plus d’utilisateurs."
>abstract="**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les visiteurs vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site.<br/>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Elle utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure ; une visualisation en graphique à 360° qui présente les pages vues pour les pages les plus courantes ; une visualisation en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation en ligne qui affiche une vue de tendance de la durée moyenne passée sur le site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--page-summary-report"
>title="Affichez des informations clés sur une page dans vos propriétés. Affiche les pages vues, une ligne de tendance, une visualisation de flux, etc."
>abstract="**Cela peut vous aider** à mieux comprendre comment les personnes interagissent avec une page donnée.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les performances de la page sur une période donnée ou mieux comprendre ce qui entraîne le trafic vers la page.<br/>Ce modèle utilise la mesure Pages vues. Il utilise également la visualisation Ligne et la visualisation Flux ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--entryPageRankedReport"
>title="Affichez les principales pages auxquelles les visiteurs accèdent la première fois que vous visitez votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site ou à mieux comprendre les premières impressions des visiteurs sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des visiteurs du site, ou vous assurer que les pages que les visiteurs voient d’abord lorsqu’ils se connectent à votre site sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation en barres et la visualisation en tableau à structure libre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--exitPageRankedReport"
>title="Affichez les principales pages auxquelles les visiteurs accèdent immédiatement avant de quitter votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les pages qui éloignent les visiteurs du site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que la mise à jour de pages de sortie courantes afin d’optimiser l’expérience que les visiteurs reçoivent avant de quitter l’ordinateur, ou inclure du contenu ou des liens pour encourager les visiteurs à rester sur votre site.<br/>Ce modèle utilise la mesure Sessions. Il utilise également la visualisation en barres et la visualisation en tableau à structure libre."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Mesures clés**] | <!--duplicated in Most popular section--> Affichez un rapport qui affiche côte à côte les mesures Pages vues, Visites et Visiteurs uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à comparer ces mesures importantes pour obtenir une image plus complète du nombre de visiteurs uniques sur le site, du nombre de visites de pages et du nombre de sessions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer le nombre moyen de pages consultées par chaque personne lors de sa visite sur le site au cours d’une semaine ou d’un mois donné, et la manière dont cela a changé à certains moments de l’année ou avant et après l’exécution des campagnes marketing. </p><p>Ce modèle utilise la dimension Jour, la mesure Pages vues, la mesure Visites et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Pages vues**] | <!--duplicated in Most popular section-->Afficher le nombre total de pages vues. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic des vacances d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Pages vues.</p> |
| [!UICONTROL **Pages**] | <!--duplicated in Most popular section-->Identifiez les pages les plus populaires et les moins populaires. <p>**Cela peut vous aider** à mieux comprendre votre audience et le type d’informations qui les intéressent le plus.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les métadonnées de page afin d’améliorer la visibilité sur les pages moins consultées ou passer du temps à améliorer le contenu de vos pages les plus consultées.</p><p>Ce modèle utilise la dimension Page et la mesure Pages vues .</p> |
| [!UICONTROL **Visites**] | <!--duplicated in Most popular section-->Afficher le nombre total de visites. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment le trafic sur votre site peut augmenter ou diminuer au fil du temps.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme évaluer l’efficacité d’une campagne marketing récemment lancée en comparant le trafic du site avant et après le lancement de la campagne. Vous pouvez également comparer le trafic des vacances d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visites .</p> |
| [!UICONTROL **Visiteurs**] | <!--duplicated in Most popular section-->Afficher le nombre total de visiteurs uniques. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre comment la portée et la taille de l’audience de votre site augmentent ou diminuent au fil du temps ou par rapport à une période précédente.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si une campagne marketing récemment lancée a réussi à attirer de nouvelles personnes sur le site en comparant les visiteurs uniques avant et après le lancement de la campagne. Vous pouvez également comparer le nombre de personnes qui visitent le site pendant les vacances d’une année à l’autre.</p><p>Ce modèle utilise la dimension Jour et la mesure Visiteurs uniques.</p> |
| [!UICONTROL **Durée**] | Permet d’afficher la durée moyenne passée par les visiteurs sur votre site au cours de chaque visite, ainsi que la durée moyenne passée par les utilisateurs avant un événement de succès. Les données sont affichées sur une période donnée et comparées à des périodes antérieures. <p>**Cela peut vous aider** à mieux comprendre les niveaux d’engagement des visiteurs et le temps nécessaire aux visiteurs pour effectuer l’action souhaitée, par exemple effectuer un achat.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer si les modifications apportées à votre site améliorent la capacité des visiteurs à atteindre rapidement un événement de succès.</p><p>Ce modèle utilise la dimension Jour et la mesure Durée de la visite (secondes), la dimension Jour et la mesure Durée de la visite (secondes).</p> |
| [!UICONTROL **Sections du site**] | <!--duplicated in Most popular section-->Affichez les sections les plus populaires ou les plus performantes de votre site. <p>**Cela peut vous aider** à mieux comprendre les sections de votre site les plus visitées.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple évaluer les produits ou services que vous fournissez qui suscitent le plus d’intérêt.</p> <p>Ce modèle utilise la dimension Section du site et la mesure Visites .</p> |
| [!UICONTROL **Consommation de contenu web**] | Permet de déterminer quel contenu web est le plus consommé et attire le plus d’utilisateurs.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les visiteurs vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site <!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Elle utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure.</p> |
| [!UICONTROL **Consommation de contenu multimédia**] | Permet de savoir quel contenu multimédia est le plus consommé et attire le plus d’utilisateurs.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui accèdent au site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles de les éloigner du site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les visiteurs vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site <!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page et la mesure Pages vues, la mesure Visites, la mesure Visiteurs uniques, la mesure Taux d’entrée, la mesure Taux de rebonds, la mesure Taux de sortie et la mesure Vitesse du contenu. Elle utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure ; une visualisation en graphique à 360° qui présente les pages vues pour les pages les plus courantes ; une visualisation en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation en ligne qui affiche une vue de tendance de la durée moyenne passée sur le site.</p> |
| [!UICONTROL **Page suivante et page précédente**] | <!--duplicated in Most popular section-->Afficher les endroits les plus courants où les gens se rendent avant ou après avoir visité un certain endroit.<p>**Cela peut vous aider** à mieux comprendre où se rendent les personnes qui consultent le site pour la première fois, les sections du site les plus consultées et les pages les plus susceptibles d’être visitées avant de quitter le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme déterminer les chemins empruntés par le site pour diriger les visiteurs vers les pages les plus importantes et les pages les plus susceptibles de les éloigner du site<!-- not sure about these takeaways... -->.</p> <p>Ce modèle utilise la dimension Page , la mesure Pages vues , la mesure Visites , la mesure Visiteurs uniques , la mesure Taux d’entrée , la mesure Taux de rebonds , la mesure Taux de sortie et la mesure Vitesse du contenu . Elle utilise également les visualisations Flux pour les sections d’entrée, de sortie et supérieure ; une visualisation en graphique de dispersion qui présente les pages vues pour les pages les plus courantes ; une visualisation en barres qui présente les pages vues par intervalle de temps regroupé ; et une visualisation en ligne qui affiche une vue de tendance de la durée moyenne passée sur le site.</p> |
| **Résumé de la page** | Affichez des informations clés sur une page dans vos propriétés. Affiche les pages vues, une ligne de tendance, une visualisation de flux, etc.  <p>**Cela peut vous aider** à mieux comprendre comment les personnes interagissent avec une page donnée.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme analyser les performances de la page sur une période donnée ou mieux comprendre ce qui entraîne le trafic vers la page.</p><p>Ce modèle utilise la mesure Pages vues . Il utilise également la visualisation Ligne et la visualisation Flux .</p> |
| **Pages d’entrée** | Affichez les principales pages auxquelles les visiteurs accèdent la première fois que vous visitez votre site. <p>**Cela peut vous aider** à mieux comprendre les pages qui génèrent le plus de trafic sur votre site ou à mieux comprendre les premières impressions des visiteurs sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que l’optimisation de l’expérience initiale des visiteurs du site, ou vous assurer que les pages que les visiteurs voient d’abord lorsqu’ils se connectent à votre site sont accueillantes et fournissent les liens nécessaires vers d’autres zones de votre site.</p><p>Ce modèle utilise la mesure Sessions . Il utilise également la visualisation en barres et la visualisation en tableau à structure libre.</p> |
| **Pages de sortie** | Affichez les principales pages auxquelles les visiteurs accèdent immédiatement avant de quitter votre site.<p>**Cela peut vous aider** à mieux comprendre les pages qui éloignent les visiteurs du site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, telles que la mise à jour de pages de sortie courantes afin d’optimiser l’expérience que les visiteurs reçoivent avant de quitter l’ordinateur, ou inclure du contenu ou des liens pour encourager les visiteurs à rester sur votre site.</p><p>Ce modèle utilise la mesure Sessions . Il utilise également la visualisation en barres et la visualisation en tableau à structure libre.</p> |

### Web : conversion {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productConversionReport"
>title="Modèle Entonnoir de conversion de produit"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-products-template"
>title="Identifier les produits les plus performants."
>abstract="**Cela peut vous aider** à mieux comprendre les produits les plus performants.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.<br/>Ce modèle utilise les mesures Consultations produits, Ajouts au panier, Commandes, Recettes et Unités. Il utilise également la dimension Produit ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartConversionReport"
>title="Permet d’afficher le nombre de fois où des personnes ont effectué des événements de passage en caisse clés, tels que l’ajout d’éléments dans leur panier, l’affichage de leur panier, la suppression d’éléments du panier et l’extraction."
>abstract="**Cela peut vous aider** à mieux comprendre quelles parties de l’entonnoir du processus de passage en caisse qui mènent à la conversion et lesquelles sont plus susceptibles d’abandonner le panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme réduire la friction à certaines étapes du processus de passage en caisse.<br/> Ce modèle utilise la variable"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartsOvertimeReport"
>title="Afficher le nombre de personnes qui ont ajouté un produit à leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre le nombre de personnes qui ajoutent un produit à leur panier, par opposition au nombre total de produits qui sont ajoutés à un panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme mesurer l’efficacité de vos pages de produits.<br/>Ce modèle utilise la mesure Paniers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartViewsOvertimeReport"
>title="Permet d’afficher le nombre de fois où les visiteurs ont consulté leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre l’expérience de passage en caisse afin de réduire les taux d’abandon de panier ou d’analyser le temps entre les ajouts au panier et les passages en caisse pour différents produits.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des promotions d’offres pour les produits qui restent dans le panier le plus longtemps et qui présentent le plus grand risque d’abandon.<br/>Ce modèle utilise la mesure Consultations du panier."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartAdditionsOvertimeReport"
>title="Afficher le nombre de fois où des personnes ont ajouté quelque chose à leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle l’intérêt des clients pour un produit est suffisamment élevé pour qu’ils l’ajoutent au panier.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les recommandations de produits pour tous les clients. Pour ce faire, vous pouvez analyser les produits qui sont fréquemment ajoutés au même panier et suggérer les produits associés en fonction des articles déjà présents dans le panier."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartRemovalsOvertimeReport"
>title="Afficher le nombre de fois où des personnes ont supprimé un article de leur panier."
>abstract="**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle les clients ne sont plus intéressés par un produit, ou cela peut vous aider à comprendre où des problèmes peuvent se produire dans le processus de passage en caisse.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer les obstacles potentiels qui peuvent exister dans le processus de passage en caisse, comme une expérience utilisateur compliquée.<br/>Ce modèle utilise la mesure Retraits du panier."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--purchaseConversionReport"
>title="Modèle Entonnoir de conversion d’achat"
>abstract=""

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Entonnoir de conversion de produit**] | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Produits** | Permet de déterminer les produits qui génèrent des mesures clés, telles que les articles les plus vendus ou les plus consultés. <p>**Cela peut vous aider** à mieux comprendre les produits les plus performants.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.</p><p>Ce modèle utilise la mesure Commandes et la dimension Produit . |
| **Performance du produit** | Identifier les produits les plus performants.<p>**Cela peut vous aider** à mieux comprendre les produits les plus performants.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que l’augmentation du financement des produits performants et la diminution du financement des produits moins performants.</p><p>Ce modèle utilise les mesures Consultations produits, Ajouts au panier, Commandes, Recettes et Unités. Il utilise également la dimension Produit . |
| **Entonnoirs de conversion de panier** | Permet d’afficher le nombre de fois où des personnes ont effectué des événements de passage en caisse clés, tels que l’ajout d’éléments dans leur panier, l’affichage de leur panier, la suppression d’éléments du panier et l’extraction. <p>**Cela peut vous aider** à mieux comprendre quelles parties de l’entonnoir du processus de passage en caisse qui mènent à la conversion et lesquelles sont plus susceptibles d’abandonner le panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme réduire la friction à certaines étapes du processus de passage en caisse.</p><p>Ce modèle utilise la méthode |
| **Paniers** | Afficher le nombre de personnes qui ont ajouté un produit à leur panier.<p>**Cela peut vous aider** à mieux comprendre le nombre de personnes qui ajoutent un produit à leur panier, par opposition au nombre total de produits qui sont ajoutés à un panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme mesurer l’efficacité de vos pages de produits.</p><p>Ce modèle utilise la mesure Paniers . |
| **Consultations du panier** | Permet d’afficher le nombre de fois où les visiteurs ont consulté leur panier. <p>**Cela peut vous aider** à mieux comprendre l’expérience de passage en caisse afin de réduire les taux d’abandon de panier ou d’analyser le temps entre les ajouts au panier et les passages en caisse pour différents produits.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des promotions d’offres pour les produits qui restent dans le panier le plus longtemps et qui présentent le plus grand risque d’abandon.</p><p>Ce modèle utilise la mesure Consultations du panier. |
| **Ajouts au panier** | Afficher le nombre de fois où des personnes ont ajouté quelque chose à leur panier. <p>**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle l’intérêt des clients pour un produit est suffisamment élevé pour qu’ils l’ajoutent au panier.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer les recommandations de produits pour tous les clients. Pour ce faire, vous pouvez analyser les produits qui sont fréquemment ajoutés au même panier et suggérer les produits associés en fonction des articles déjà présents dans le panier. |
| **Retraits du panier** | Afficher le nombre de fois où des personnes ont supprimé un article de leur panier.<p>**Cela peut vous aider** à mieux comprendre la partie de l’entonnoir de conversion dans laquelle les clients ne sont plus intéressés par un produit, ou cela peut vous aider à comprendre où des problèmes peuvent se produire dans le processus de passage en caisse.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme supprimer les obstacles potentiels qui peuvent exister dans le processus de passage en caisse, comme une expérience utilisateur compliquée.</p><p>Ce modèle utilise la mesure Retraits du panier . |
| **Entonnoir de conversion d’achat** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Recettes** | <!--duplicated in Most popular section-->Afficher la valeur monétaire des produits achetés dans toutes les commandes.<p>**Cela peut vous aider** à mieux comprendre les éléments de dimension qui ont contribué aux recettes, en combinant la mesure Recettes à n’importe quelle dimension. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code de suivi ) ayant contribué aux recettes. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple ajuster les campagnes qui ne répondent pas aux objectifs de recettes attendues.</p><p>Ce modèle utilise la mesure Recettes. |
| **Commandes** | <!--duplicated in Most popular section-->Permet d’afficher le nombre total d’événements d’achat effectués sur votre site. <p>**Cela peut vous aider** à mieux comprendre les éléments de dimension ayant contribué à une commande, en combinant la mesure Commandes à n’importe quelle dimension. Par exemple, vous pouvez afficher les principales campagnes (à l’aide de la dimension Code de suivi ) ayant contribué aux achats.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster les campagnes qui ne répondent pas aux cibles d’achat attendues. </p><p>Ce modèle utilise la mesure Commandes . |

### Web : audience {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Permet d’afficher le pays d’origine des visiteurs du site."
>abstract="**Cela peut vous aider** à mieux comprendre les pays les plus populaires d&#39;où proviennent les visiteurs de votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues primaires différentes.<br/>Ce modèle utilise la dimension Pays."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Permet d’afficher l’état d’origine des visiteurs du site (aux États-Unis). Cela est similaire au modèle Régions géographiques , sauf qu’il est spécifique aux États-Unis."
>abstract="**Cela peut vous aider** à mieux comprendre les États-Unis les plus populaires d&#39;où viennent les visiteurs de votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces états.<br/>Ce modèle utilise la dimension États-Unis."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Permet d’afficher la région géographique d’où proviennent les visiteurs du site. Une région est une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d’autres régions, il s’agit d’un pays constitutif, d’un département ou d’une région métropolitaine. "
>abstract="**Cela peut vous aider** à mieux comprendre les régions les plus populaires d&#39;où proviennent les visiteurs de votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces régions ou vous assurer que l’expérience de votre site est optimale dans des régions qui ont des langues primaires différentes. <br/>Ce modèle utilise les dimensions ID(variables/geocountry) et Régions. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Permet d’afficher la ville d’où proviennent les visiteurs du site."
>abstract="**Cela peut vous aider** à mieux comprendre les villes les plus populaires d&#39;où proviennent les visiteurs de votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces villes. <br/>Ce modèle utilise la dimension Villes"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Affichez les zones marketing désignées (DMA) aux États-Unis d’où proviennent les visiteurs du site."
>abstract="**Cela peut vous aider** à mieux comprendre les régions les plus populaires d&#39;où proviennent les visiteurs de votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans les régions les plus performantes. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Afficher les principales langues dans lesquelles les visiteurs préfèrent voir le contenu."
>abstract="**Cela peut vous aider** à mieux comprendre les langues les plus fréquemment préférées des visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des actions de localisation ou de marketing pour les langues les plus populaires.<br/>Ce modèle utilise la dimension Langue ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Présentation des technologies"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Affichez le nom et la version des principaux navigateurs utilisés par les visiteurs pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les visiteurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité.<br/>Ce modèle utilise la dimension Navigateur."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Affichez les noms des organisations qui ont créé les principaux navigateurs que les visiteurs utilisent pour accéder à votre site. Cela diffère du modèle Navigateur dans la mesure où il ne répertorie pas les différentes versions d’un même navigateur comme éléments de dimension distincts."
>abstract="**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants que les visiteurs utilisent <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité. <br/>Ce modèle utilise la dimension Type de navigateur . "

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Premiers utilisateurs par rapport aux utilisateurs répétés**] | Permet d’afficher une comparaison entre les nouveaux visiteurs et les visiteurs réguliers. <p>**Cela peut vous aider** à mieux comprendre l’efficacité de votre site à fidéliser la clientèle ou le taux auquel vous acquérez de nouveaux clients.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme proposer des incitations pour les achats futurs aux nouveaux visiteurs afin de les inciter à revenir.</p><p>Ce modèle utilise la méthode </p> |
| **ID De Personne/Espace De Noms** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode  </p> |
| **Présentation de l’emplacement** | Affichez un aperçu de l’emplacement du visiteur dans une visualisation de carte.<p>**Cela peut vous aider** à mieux comprendre où se trouvent les visiteurs qui visitent votre site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les ressources marketing dans les emplacements où vous constatez le plus d’intérêt et d’opportunité.</p><p>Ce modèle utilise la méthode  </p> |
| **Pays géographiques** | Permet d’afficher le pays d’origine des visiteurs du site.<p>**Cela peut vous aider** à mieux comprendre les pays les plus populaires d&#39;où proviennent les visiteurs de votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces pays ou vous assurer que l’expérience de votre site est optimale dans les pays qui ont des langues primaires différentes.</p><p>Ce modèle utilise la dimension Pays . </p> |
| **États géo-américains** | Permet d’afficher l’état d’origine des visiteurs du site (aux États-Unis). Cela est similaire au modèle Régions géographiques , sauf qu’il est spécifique aux États-Unis.<p>**Cela peut vous aider** à mieux comprendre les États-Unis les plus populaires d&#39;où viennent les visiteurs de votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces états.</p><p>Ce modèle utilise la dimension États américains. </p> |
| **Régions géographiques** | Permet d’afficher la région géographique d’où proviennent les visiteurs du site. Une région est une zone géographique plus petite qu’un pays, mais plus grande qu’une ville. Dans certains pays, une région est un état, une province ou une préfecture. Dans d’autres régions, il s’agit d’un pays constitutif, d’un département ou d’une région métropolitaine. <p>**Cela peut vous aider** à mieux comprendre les régions les plus populaires d&#39;où proviennent les visiteurs de votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces régions ou vous assurer que l’expérience de votre site est optimale dans des régions qui ont des langues primaires différentes. </p><p>Ce modèle utilise les dimensions ID (variables/pays) et Régions . </p> |
| **Géographie des villes** | Permet d’afficher la ville d’où proviennent les visiteurs du site. <p>**Cela peut vous aider** à mieux comprendre les villes les plus populaires d&#39;où proviennent les visiteurs de votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans ces villes. </p><p>Ce modèle utilise la dimension Villes . </p> |
| **Geo US DMA** | Affichez les zones marketing désignées (DMA) aux États-Unis d’où proviennent les visiteurs du site.<p>**Cela peut vous aider** à mieux comprendre les régions les plus populaires d&#39;où proviennent les visiteurs de votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme utiliser les données pour vous concentrer sur les efforts marketing dans les régions les plus performantes. </p><p>Ce modèle utilise la méthode </p> |
| **Langues** | Afficher les principales langues dans lesquelles les visiteurs préfèrent voir le contenu. <p>**Cela peut vous aider** à mieux comprendre les langues les plus fréquemment préférées des visiteurs.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, telles que des actions de localisation ou de marketing pour les langues les plus populaires.</p><p>Ce modèle utilise la dimension Langue .</p> |
| **Présentation de la technologie** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode </p> |
| **Navigateurs** | Affichez le nom et la version des principaux navigateurs utilisés par les visiteurs pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les visiteurs.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité.</p><p>Ce modèle utilise la dimension Navigateur . </p> |
| **Types de navigateur** | Affichez les noms des organisations qui ont créé les principaux navigateurs que les visiteurs utilisent pour accéder à votre site. Cela diffère du modèle Navigateur dans la mesure où il ne répertorie pas les différentes versions d’un même navigateur comme éléments de dimension distincts.<p>**Cela peut vous aider** à mieux comprendre les navigateurs les plus courants utilisés par les visiteurs</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer la qualité du site en testant de nouvelles versions de votre site à l’aide des navigateurs les plus performants. Cela permet de maximiser les efforts de contrôle de la qualité. </p><p>Ce modèle utilise la dimension Type de navigateur . </p> |

### Web : Acquisition {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Lors de l’utilisation de l’attribution personnalisée, ce modèle indique comment les visiteurs arrivent sur votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les canaux marketing les plus efficaces.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple investir plus massivement dans des canaux marketing efficaces et désinvestir des canaux marketing moins efficaces.<br/>Ce modèle utilise la dimension ID(variables/marketingchannel) et la mesure Recettes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Afficher le premier canal marketing auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut)."
>abstract="**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic initial vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts de marketing dans les domaines les plus efficaces.<br/>Ce modèle utilise la dimension Canal Première touche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Affichez les détails sur le premier canal marketing auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut)."
>abstract="**Cela peut vous aider** à mieux comprendre ce qui a contribué à l’accès correspondant à un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts de marketing dans les domaines les plus efficaces.<br/>Ce modèle utilise la dimension Détails du canal Première touche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Entonnoir de conversion de campagne"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Affichez les détails sur les performances de vos campagnes marketing."
>abstract="**Cela peut vous aider** à mieux comprendre les différents indicateurs de succès associés aux campagnes, tels que les recettes, les consultations de produits, les commandes, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de recettes. <br/>Ce modèle utilise la mesure Recettes, la mesure Consultations produits, la mesure Ajouts au panier, la mesure Commandes et la mesure Unités. Elle utilise également la dimension Code de suivi et la dimension Domaine référent ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-acquisition-template"
>title="Permet d’afficher la manière dont votre site web reçoit des visiteurs."
>abstract="**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts marketing sur les canaux les plus efficaces.<br/>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Elle utilise également la dimension Moteur de recherche, la dimension Mot-clé de recherche, la dimension Page d’accès, la dimension Domaine référent, la dimension Code de suivi et la dimension Référent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qu’ils soient payants ou naturels."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les visiteurs utilisent dans les recherches qui génèrent du trafic sur le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation pour les moteurs de recherche entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.<br/>Ce modèle utilise la dimension Mot-clé de recherche ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les visiteurs utilisent dans les recherches qui génèrent du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation pour les moteurs de recherche entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site. <br/>Ce modèle utilise la dimension Mot-clé de recherche - Payée . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les mots-clés que les visiteurs utilisent dans les recherches qui génèrent du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation pour les moteurs de recherche entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.<br/>Ce modèle utilise la dimension Mot-clé de recherche - Naturelle . "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Afficher les moteurs de recherche que les visiteurs utilisent pour accéder à votre site, qu’il soit payant ou naturel."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les visiteurs utilisent pour générer du trafic sur le site. <br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation pour les moteurs de recherche sur les moteurs de recherche qui génèrent le plus de trafic sur le site.<br/>Ce modèle utilise la dimension Moteur de recherche. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Affichez les moteurs de recherche que les visiteurs utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les visiteurs utilisent pour générer du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation pour les moteurs de recherche sur les moteurs de recherche qui génèrent le plus de trafic sur le site. <br/>Ce modèle utilise la dimension Moteur de recherche - Payée ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant."
>abstract="**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les visiteurs utilisent pour générer du trafic sur le site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation pour les moteurs de recherche sur les moteurs de recherche qui génèrent le plus de trafic sur le site.<br/>Ce modèle utilise la dimension Moteur de recherche - Naturelle ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Permet d’afficher les domaines sur lesquels les visiteurs cliquent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les sites tiers qui génèrent le plus de trafic sur le vôtre. (Un lien doit exister sur le site externe et un visiteur doit cliquer dessus pour que l’élément de dimension s’affiche.)<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant des principaux domaines référents. <br/>Ce modèle utilise la dimension Domaine référent ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Affichez le premier domaine référent sur lequel les visiteurs ont cliqué pour accéder à votre site. (Une fois défini, il contient la même valeur pour toute la durée de vie de cet identifiant visiteur.)"
>abstract="**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent initialement du trafic sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant des principaux domaines référents d’origine. <br/> Ce modèle utilise la dimension Domaine référent initial ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Permet de déterminer les URL sur lesquelles se trouvaient les visiteurs lorsqu’ils cliquaient pour accéder à votre site. (Un lien doit exister sur l’URL externe et un visiteur doit cliquer dessus pour que l’élément de dimension s’affiche.)"
>abstract="**Cela peut vous aider** à mieux comprendre les URL spécifiques qui génèrent le plus de trafic sur votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant des principales URL. <br/>Ce modèle utilise la dimension Domaine référent .</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Permet de déterminer les canaux génériques sur lesquels les visiteurs ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque canal. Les canaux possibles sont les moteurs de recherche, les réseaux sociaux, d’autres sites web, le disque dur ou le courrier électronique."
>abstract="**Cela peut vous aider** à mieux comprendre quel type de référents génère le plus de trafic vers votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant d’un certain canal.<br/>Ce modèle utilise la dimension Type de référent ."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Rapport Présentation du canal marketing**] | Lors de l’utilisation de l’attribution personnalisée, ce modèle indique comment les visiteurs arrivent sur votre site.<p>**Cela peut vous aider** à mieux comprendre les canaux marketing les plus efficaces.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple investir plus massivement dans des canaux marketing efficaces et désinvestir des canaux marketing moins efficaces.</p><p>Ce modèle utilise la dimension ID(variables/marketingChannel) et la mesure Recettes.</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Canal marketing Première touche**] | Afficher le premier canal marketing auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut). <p>**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent le trafic initial vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Canal Première touche .</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Détails du canal marketing Première touche**] | Affichez les détails sur le premier canal marketing auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre ce qui a contribué à l’accès correspondant à un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Détails du canal Première touche .</p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Canal marketing Dernière touche**] | Affichez le canal marketing le plus récent avec lequel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut).<p>**Cela peut vous aider** à mieux comprendre quels canaux marketing génèrent du trafic sur votre site qui génèrent des conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts de marketing dans les domaines les plus efficaces.</p><p>Ce modèle utilise la dimension Canal Dernière touche .  </p> |
| [!UICONTROL **Canaux marketing**] > [!UICONTROL **Détails du canal marketing Dernière touche**] | Afficher les détails sur le canal marketing le plus récent auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut)<p>**Cela peut vous aider** à mieux comprendre ce qui a contribué à l’accès correspondant à un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts de marketing dans les domaines les plus efficaces. </p><p>Ce modèle utilise la dimension Détails du canal Dernière touche . </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Campagnes (Code de suivi)**] | Affichez les noms des codes de suivi sur votre site. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet.<p>**Cela peut vous aider** à mieux comprendre les liens qui ont généré le plus de trafic vers votre site. L’ajout de chaînes de requête de code de suivi est courant dans les emails, les publicités, les publications de médias sociaux et d’autres efforts marketing que votre entreprise utilise.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de recettes.</p><p>Ce modèle utilise la dimension Code de suivi . </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Entonnoir de conversion de campagne**] | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode  </p> |
| [!UICONTROL **Campagnes**] > [!UICONTROL **Performances de la campagne**] | Affichez les détails sur les performances de vos campagnes marketing.<p>**Cela peut vous aider** à mieux comprendre les différents indicateurs de succès associés aux campagnes, tels que les recettes, les consultations de produits, les commandes, etc.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer les efforts de marketing sur les campagnes qui génèrent le plus de recettes. </p><p>Ce modèle utilise les mesures Recettes, Consultations produits, Ajouts au panier, Commandes et Unités. Elle utilise également la dimension Code de suivi et la dimension Domaine référent . </p> |
| **Acquisition Web** | Permet d’afficher la manière dont votre site web reçoit des visiteurs.<p>**Cela peut vous aider** à mieux comprendre les différents facteurs qui mènent à l’acquisition, tels que les mots-clés de recherche, le domaine référent, etc.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’actions, comme concentrer les efforts marketing sur les canaux les plus efficaces.</p><p>Ce modèle utilise la mesure Taux de rebond et la mesure Rebonds. Elle utilise également la dimension Moteur de recherche, la dimension Mot-clé de recherche, la dimension Page d’accès, la dimension Domaine référent, la dimension Code de suivi et la dimension Référent.  </p> |
| **Mots-clés de recherche-tous** | Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qu’ils soient payants ou naturels. <p>**Cela peut vous aider** à mieux comprendre les mots-clés que les visiteurs utilisent dans les recherches qui génèrent du trafic sur le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation pour les moteurs de recherche entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.</p><p>Ce modèle utilise la dimension Mot-clé de recherche . </p> |
| **Mots-clés de recherche-payante** | Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les mots-clés que les visiteurs utilisent dans les recherches qui génèrent du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation pour les moteurs de recherche entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site. </p><p>Ce modèle utilise la dimension Mots-clés de recherche - Payée . </p> |
| **Mots-clés de recherche-Naturelle** | Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les mots-clés que les visiteurs utilisent dans les recherches qui génèrent du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme identifier et remplir les trous d’optimisation pour les moteurs de recherche entre les mots-clés utilisés et ceux qui génèrent du trafic sur le site.</p><p>Ce modèle utilise la dimension Mot-clé de recherche - Naturelle . </p> |
| **Moteurs de recherche -Tous** | Afficher les moteurs de recherche que les visiteurs utilisent pour accéder à votre site, qu’il soit payant ou naturel. <p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les visiteurs utilisent pour générer du trafic sur le site. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation pour les moteurs de recherche sur les moteurs de recherche qui génèrent le plus de trafic sur le site.</p><p>Ce modèle utilise la dimension Moteur de recherche . </p> |
| **Moteurs de recherche payants** | Affichez les moteurs de recherche que les visiteurs utilisent pour accéder à votre site, qui correspondent à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les visiteurs utilisent pour générer du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation pour les moteurs de recherche sur les moteurs de recherche qui génèrent le plus de trafic sur le site. </p><p>Ce modèle utilise la dimension Moteur de recherche - Payé . </p> |
| **Moteurs de recherche - Naturelle** | Affichez les mots-clés de recherche que les visiteurs utilisent pour accéder à votre site, qui ne correspondent pas à la détection de référencement payant.<p>**Cela peut vous aider** à mieux comprendre les moteurs de recherche que les visiteurs utilisent pour générer du trafic sur le site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme concentrer vos efforts d’optimisation pour les moteurs de recherche sur les moteurs de recherche qui génèrent le plus de trafic sur le site.</p><p>Ce modèle utilise la dimension Moteur de recherche - Naturelle . </p> |
| **Domaines référents** | Permet d’afficher les domaines sur lesquels les visiteurs cliquent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les sites tiers qui génèrent le plus de trafic sur le vôtre. (Un lien doit exister sur le site externe et un visiteur doit cliquer dessus pour que l’élément de dimension s’affiche.)</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant des principaux domaines référents. </p><p>Ce modèle utilise la dimension Domaine référent . </p> |
| **Domaines référents d’origine** | Affichez le premier domaine référent sur lequel les visiteurs ont cliqué pour accéder à votre site. (Une fois défini, il contient la même valeur pour toute la durée de vie de cet identifiant visiteur.)<p>**Cela peut vous aider** à mieux comprendre quels sites tiers génèrent initialement du trafic sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant des principaux domaines référents d’origine. </p><p>Ce modèle utilise la dimension Domaine référent initial . </p> |
| **Référents** | Permet de déterminer les URL sur lesquelles se trouvaient les visiteurs lorsqu’ils cliquaient pour accéder à votre site. (Un lien doit exister sur l’URL externe et un visiteur doit cliquer dessus pour que l’élément de dimension s’affiche.)  <p>**Cela peut vous aider** à mieux comprendre les URL spécifiques qui génèrent le plus de trafic sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant des principales URL. </p><p>Ce modèle utilise la dimension Domaine référent . </p><p>Ce modèle utilise la dimension Référent . </p> |
| **Types de référents** | Permet de déterminer les canaux génériques sur lesquels les visiteurs ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque canal. Les canaux possibles sont les moteurs de recherche, les réseaux sociaux, d’autres sites web, le disque dur ou le courrier électronique.<p>**Cela peut vous aider** à mieux comprendre quel type de référents génère le plus de trafic vers votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme créer ou ajuster le contenu pour mieux vous aligner sur les intérêts des visiteurs provenant d’un certain canal.</p><p>Ce modèle utilise la dimension Type de référent .</p> |

### Mobile : application mobile {#mobile-app}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-lifecycle-metrics-app-usage-template"
>title="Utilisation des applications mobiles"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-journeys"
>title="Parcours d’applications mobiles"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-key-metrics"
>title="Mesures des applications mobiles"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-messaging"
>title="Messagerie des applications mobiles"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-performance-template"
>title="Performances de l’application mobile"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-retention"
>title="Conservation des applications mobiles"
>abstract=""

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Mobile App Screens**] | Affichez des informations sur les écrans mobiles que les visiteurs utilisent lors de l’accès à votre site, telles que la taille d’écran, la largeur d’écran et la hauteur d’écran. <p>**Cela peut vous aider** à mieux comprendre comment les visiteurs expérimentent votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les tailles d’écran les plus courantes.</p><p>Ce modèle utilise la méthode |
| **Actions d’application mobile** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Utilisation des applications mobiles** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Parcours d’applications mobiles** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Mesures d’application mobile** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Messagerie d’application mobile** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Performances de l’application mobile** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Rétention des applications mobiles** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |

### Mobile : informations sur les périphériques mobiles {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileCarrierRankedReport"
>title="Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les visiteurs utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus populaires parmi votre base d&#39;utilisateurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience utilisateur fluide.<br/> Ce modèle utilise la dimension Opérateur de téléphonie mobile ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceNameRankedReport"
>title="Affichez la marque et le modèle des appareils mobiles que les visiteurs utilisent pour accéder à votre site."
>abstract="**Cela peut vous aider** à mieux comprendre les périphériques mobiles les plus populaires parmi votre base d’utilisateurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les appareils mobiles les plus courants.<br/>Ce modèle utilise la dimension Nom de l’appareil mobile ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceTypeRankedReport"
>title="Affichez les types de périphériques mobiles que les visiteurs utilisent pour accéder à votre site, tels que les téléphones et tablettes."
>abstract="**Cela peut vous aider** à mieux comprendre les différents types d’appareils mobiles utilisés pour accéder à votre site.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les types d’appareils mobiles les plus utilisés.<br/>Ce modèle utilise la dimension Type de périphérique mobile ."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileManufacturerRankedReport"
>title="Identifiez les fabricants qui produisent les appareils mobiles que les visiteurs utilisent pour accéder à votre site, comme Apple et Samsung."
>abstract="**Cela peut vous aider** à mieux comprendre les fabricants les plus populaires parmi votre base d’utilisateurs.<br/>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des capacités de différents fabricants afin d’assurer une expérience utilisateur fluide.<br/>Ce modèle utilise la dimension Fabricant mobile ."

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Opérateur de téléphonie mobile**] | Affichez la société de télécommunications qui fournit une connexion réseau cellulaire aux appareils mobiles que les visiteurs utilisent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les opérateurs de téléphonie mobile les plus populaires parmi votre base d&#39;utilisateurs.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des fonctionnalités réseau de différents opérateurs afin d’assurer une expérience utilisateur fluide.</p><p>Ce modèle utilise la dimension Opérateur de téléphonie mobile .</p> |
| **Périphériques mobiles** | Affichez la marque et le modèle des appareils mobiles que les visiteurs utilisent pour accéder à votre site.<p>**Cela peut vous aider** à mieux comprendre les périphériques mobiles les plus populaires parmi votre base d’utilisateurs.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser le rendu de votre site pour les appareils mobiles les plus courants.</p><p>Ce modèle utilise la dimension Nom de l’appareil mobile .</p> |
| **Type de périphérique mobile** | Affichez les types de périphériques mobiles que les visiteurs utilisent pour accéder à votre site, tels que les téléphones et tablettes.<p>**Cela peut vous aider** à mieux comprendre les différents types d’appareils mobiles utilisés pour accéder à votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser votre site pour les types d’appareils mobiles les plus utilisés.</p><p>Ce modèle utilise la dimension Type de périphérique mobile .</p> |
| **Fabricant** | Identifiez les fabricants qui produisent les appareils mobiles que les visiteurs utilisent pour accéder à votre site, comme Apple et Samsung.<p>**Cela peut vous aider** à mieux comprendre les fabricants les plus populaires parmi votre base d’utilisateurs.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme personnaliser la diffusion de contenu en fonction des capacités de différents fabricants afin d’assurer une expérience utilisateur fluide.</p><p>Ce modèle utilise la dimension Fabricant mobile .</p> |

### Tranches temporelles

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minute de l’heure**] | Permet d’afficher le nombre d’événements, de sessions et de personnes sur votre site, par minute. Si, par exemple, vous disposez d’un rapport avec une période de rapport d’un seul jour, la première minute de chaque heure de la journée est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les tendances à un niveau granulaire.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la dimension Minute de l’heure . |
| **Heure de la journée** | Afficher les événements, sessions et personnes sur votre site, par heure de la journée. Si, par exemple, vous disposez d’un rapport couvrant la période du 1er au 7 janvier, la première heure de chaque jour est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre l’heure de la journée où votre site est le plus souvent et le moins fréquemment visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les heures de trafic élevé.</p><p>Ce modèle utilise la dimension Heure de la journée . |
| **Matin/après-midi** | Affichez les événements, les sessions et les personnes sur votre site, par heure du matin et par heure du soir. Si, par exemple, vous disposez d’un rapport couvrant la période du 1er au 7 janvier, les heures du matin de chaque jour sont regroupées dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre l’heure de la journée où votre site est le plus souvent et le moins fréquemment visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme affecter plus de ressources informatiques à votre site pendant les heures de trafic élevé.</p><p>Ce modèle utilise la dimension matin/après-midi. |
| **Jour de la semaine** | Afficher les événements, sessions et personnes de votre site, par jour de la semaine. Si, par exemple, vous disposez d’un rapport couvrant le mois de janvier, chaque jour de la semaine est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de la semaine où votre site est le plus souvent et le moins visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme de faire en sorte que votre centre d’appel soit plus adapté aux jours à trafic élevé.</p><p>Ce modèle utilise la dimension Jour de la semaine . |
| **Jour du mois** | Afficher les événements, sessions et personnes de votre site, par jour du mois. Si, par exemple, vous disposez d’un rapport couvrant une année complète, chaque jour du mois est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de chaque mois où votre site est le plus souvent et le moins visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme de faire en sorte que votre centre d’appel soit plus adapté aux jours à trafic élevé.</p><p>Ce modèle utilise la dimension Jour du mois . |
| **Jour de l’année** | Afficher les événements, sessions et personnes de votre site, par jour de l’année. Si, par exemple, un rapport s’étend sur plusieurs années, chaque jour de l’année est regroupé dans le même élément de dimension. <p>**Cela peut vous aider** à mieux comprendre les jours de chaque année où votre site est le plus souvent et le moins visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme de faire en sorte que votre centre d’appel soit plus adapté aux jours à trafic élevé.</p><p>Ce modèle utilise la dimension Jour de l’année . |
| **Jour ouvrable/week-end** | Permet d’afficher les événements, les sessions et les personnes de votre site, par jour et week-end. Si, par exemple, vous disposez d’un rapport couvrant le mois de janvier, les jours de semaine et les week-ends sont regroupés dans des éléments de dimension distincts. <p>**Cela peut vous aider** à mieux comprendre les différences de trafic sur le site pendant les jours de semaine par rapport aux week-ends.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que d’affecter davantage de personnel à votre centre d’appel le week-end, si le rapport indique que les week-ends sont plus occupés que les jours de semaine.</p><p>Ce modèle utilise la dimension Jour ouvrable/week-end. |
| **Semaine de l’année** | Afficher les événements, sessions et personnes sur votre site, par semaine de l’année. Si, par exemple, un rapport s’étend sur plusieurs années, chaque semaine est regroupée dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les semaines de l’année où votre site est le plus souvent et le moins visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme de faire en sorte que votre centre d’appel soit plus adapté aux semaines à trafic élevé, comme pendant les vacances.</p><p>Ce modèle utilise la dimension Semaine de l’année . |
| **Mois de l’année** | Afficher les événements, sessions et personnes sur votre site, par mois de l’année. Si, par exemple, un rapport s’étend sur plusieurs années, chaque mois est regroupé dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les mois où votre site est le plus souvent et le moins fréquemment visité.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, telles que d’affecter le personnel de votre centre d’appel de manière plus appropriée pour les mois à trafic élevé, comme pendant les jours fériés.</p><p>Ce modèle utilise la dimension Mois de l’année . |
| **Trimestre de l’année** | Afficher les événements, sessions et personnes de votre site, par trimestre de l’année. Si, par exemple, un rapport s’étend sur plusieurs années, chaque trimestre est regroupé dans le même élément de dimension.<p>**Cela peut vous aider** à mieux comprendre les quartiers de votre site les plus fréquemment et les moins fréquemment visités.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme le lancement des produits afin de stimuler les trimestres de faible trafic historiques.</p><p>Ce modèle utilise la dimension Trimestre de l’année . |

### Cross-Channel

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Présentation multicanal**] | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Comparaison cross-canal** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Désélection du centre d’appels (centre Web+appel)** | Afficher l’impact du trafic web sur le trafic du centre d’appels.<p>**Cela peut vous aider** à mieux comprendre le degré de réussite du contenu en libre-service de votre site web qui déverse le trafic vers votre centre d’appels.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme améliorer le contenu en libre-service afin de réduire le trafic vers votre centre d’appels ou mesurer le retour sur investissement de votre contenu en libre-service en calculant le montant enregistré par le biais d’un nombre moins élevé d’appels au service clientèle.</p><p>Ce modèle utilise la méthode |
| **Web+App** | Affichez le trafic web et le trafic mobile ensemble.<p>**Cela peut vous aider** à mieux comprendre la distribution du trafic web et mobile sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à l’expérience de votre application mobile lorsqu’elle atteint un certain niveau de trafic.</p><p>Ce modèle utilise la méthode |
| **Online/Offline** | Afficher le trafic en ligne et hors ligne ensemble.<p>**Cela peut vous aider** à mieux comprendre la distribution du trafic en ligne et hors ligne sur votre site.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme consacrer plus de ressources à votre expérience en ligne lorsqu’elle atteint un certain niveau de trafic.</p><p>Ce modèle utilise la méthode |

### Autres canaux

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tableau de bord du centre d’appels**] | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **POS/Offline** | Afficher les données de point de vente et de transaction hors ligne.<p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Email/AJO** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |
| **Enquête** | <p>**Cela peut vous aider** à mieux comprendre</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre de tâches, comme </p><p>Ce modèle utilise la méthode |

### AJO {#AJO-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Campagnes AJO"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Parcours AJO"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Pages de destination AJO"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Rapport Vue d’ensemble AJO"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Abonnements AJO"
>abstract=""

<!-- markdownlint-enable MD034 -->

Les modèles suivants sont disponibles :

| Nom du modèle | Pourquoi utiliser ce modèle <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campagnes AJO**] | Affichez les mesures essentielles pour vos campagnes Journey Optimizer, notamment les campagnes par e-mail, les expériences, les messages in-app, les SMS, etc.<p>**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui permet d’avoir un aperçu complet de l’efficacité et du niveau d’engagement de votre campagne.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple ajuster vos campagnes en fonction des niveaux d’engagement de votre audience cible.</p> |
| **AJO Parcours** | Affichez les mesures essentielles pour vos parcours Journey Optimizer, notamment les parcours de messagerie, les expériences, les messages in-app, les SMS, etc.<p>**Cela peut vous aider** à mieux comprendre les détails tels que le nombre de clics et le nombre de messages diffusés, ce qui vous permet d’avoir un aperçu complet de l’efficacité et du niveau d’engagement de votre parcours.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, par exemple ajuster vos campagnes en fonction des niveaux d’engagement de votre audience cible.</p> |
| **Pages d’entrée AJO** | Afficher le comportement des utilisateurs, les schémas d’engagement, les taux de conversion et d’autres mesures clés.<p>**Cela peut vous aider** à mieux comprendre l’efficacité de votre landing page. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme optimiser les performances de votre landing page.</p> |
| **Rapport Aperçu d’AJO** | Affichez un résumé complet des mesures de trafic et d’engagement pour toutes les campagnes et tous les parcours de votre environnement.<p>**Cela peut vous aider** à mieux comprendre l’efficacité générale de vos campagnes et parcours. </p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes et vos parcours en fonction des niveaux d’engagement de votre audience cible.</p> |
| **Abonnements AJO** | Afficher les abonnements et désabonnements des profils associés à des listes spécifiques.<p>**Cela peut vous aider** à mieux comprendre l’efficacité de différentes campagnes et initiatives d’abonnement pour stimuler l’engagement et les conversions.</p><p>**En fonction de ce que vous apprenez, vous pouvez** effectuer un certain nombre d’opérations, comme ajuster vos campagnes d’abonnement en fonction des niveaux d’engagement de votre audience cible.</p> |


<!-- deleted: 

| [!UICONTROL **Real-Time**] | View the dimensions and metrics that are currently being collected on your site. <p>**This can help you** better understand what is trending on your site.</p><p>**Based on what you learn, you might** respond to and actively manage the performance of your current marketing content and campaigns.</p> <p>This template uses the [Real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> | 
| [!UICONTROL **Fallout**] | View where people leave or continue through a predefined sequence of pages.<p>**This can help you** better understand where people are falling out of the user journey.</p><p>**Based on what you learn, you might** do any number of things, like analyze conversion rates through specific processes on your site (such as a purchase or registration process), or analyze correlations between events on your site. (For example, what percentage of people who looked at your privacy policy went on to purchase a product.) You can also use this template to perform side-by-side comparisons of two different segments in the same report.</p> <p>This template uses the [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> | 
| [!UICONTROL **Cross-device analysis**] | View which devices people used across all points of the journey.<p>**This can help you** better understand how many people interact with your brand, the types of devices they use, and how their use of multiple devices affects their experience. For example, how often do people begin a task on a mobile device and then later move to a desktop to complete a task? What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed? And so forth.</p><p>**Based on what you learn, you might** do any number of things, like optimize certain parts of the user journey for a mobile experience.</p> <p>This template uses the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Cohort analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [the People metric](/help/components/metrics/people.md), and [the Unique devices metric](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Web retention**] | View who your loyal users are and what they are doing on your site.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 
| [!UICONTROL **Streaming Media Consumption**] | View  trends and top metrics of media consumption across all digital devices.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 

-->

<!--

Ignore below this 

| Menu item | Reports under this menu item |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Training Tutorial (Pre-existing Workspace template)</li><li>Pages (What are my top pages?)</li><li>Page views (How many page views am I generating?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Key metrics (How are my most important metrics performing?)</li><li>Site sections (Which sections of my site generated the most page views?)</li><li>Real-Time (What is trending on my site, and why?)</li><li>Next page (What are the next pages my visitors go to?)</li><li>Previous page (What are the previous pages my visitors went to?)</li><li>Campaigns (What campaigns are driving my key metrics?)</li><li>Products (What products are driving my key metrics?)</li><li>Last touch channel (Which last touch channel is performing best?</li><li>Last touch channel detail (Which specific last touch channel is outperforming others?)</li><li>Revenue (How is my revenue performing?)</li><li>Orders (How are my orders performing?)</li><li>Units (How many units am I selling?)</li></ul> | 
| **[!UICONTROL Engagement]** | <ul><li>Key metrics (How are my most important metrics performing?)</li><li>Page views (How many page views am I generating?)</li><li>Pages (What are my top pages?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Time spent per visit (How much time do my users spend per visit?)</li><li>Time prior to event (How much time do my users spend prior to a success event?)</li><li>Site sections (Which sections of my site generated the most page views?</li><li>Web content consumption (Which content is consumed most and is engaging users?)</li><li>Media content consumption (Which content is consumed most and is engaging users?)</li><li>Next and previous page flow (What are/were the next/previous paths my visitors take/took?)</li><li>Fallout (Where am I seeing fallout through my digital properties?)</li><li>Cross-device analysis (Using cross-device analysis in Analysis Workspace)</li><li>Web retention (Who are my loyal users and what do they do?)</li><li>Media audio consumption (What are trends and top metrics of audio consumption?)</li><li>Media recency, frequency, loyalty (Who are my loyal readers?)</li><li>Page analysis > Reloads (Which pages generate the most reloads?)</li><li>Page analysis > Time spent on page (How much time do my users spend on my pages?)</li><li>Entries & exits > Entry pages (What are my top entry pages?)</li><li>Entries & exits > Original entry pages (What page did my visitor originally enter from?)</li><li>Entries & exits > Single-page visits (Which pages generated the most single-page visits?)</li><li>Entries & exits > Exit pages (What are my top exit pages?)</li><li>Page Analysis > Page summary</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Products > Products (Which products are driving my key metrics?)</li><li>Products > Product performance (Which products are performing best?)</li><li>Products > Categories (What are my best performing product categories?</li><li>Shopping cart > Carts (How many users added a product to cart?</li><li>Shopping cart > Cart views (How many times did my visitors view their carts?)</li><li>Shopping cart > Cart additions (How often are users adding a product to their cart?)</li><li>Shopping cart > Cart removals (How often are users removing a product from their cart?)</li><li>Purchases > Revenue (How is my revenue performing?)</li><li>Purchases > Orders (How are my orders performing?)</li><li>Purchases > Units (How many units am I selling?)</li><li>[Magento: marketing and commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** |<ul><li>People metric (How many people are interacting with my brand?)</li><li>Visitor profile > Location overview (Which locations are driving the most usage among users)</li><li>Visitor profile > Geosegmentation > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Which geographies are my users visiting from?)</li><li>Visitor profile > Languages (Which language do my users prefer?)</li><li>Visitor profile > Time zones (Which time zones are my users visiting from?)</li><li>Visitor profile > Domains (Which ISPs are my visitors using to access my site?)</li><li>Visitor profile > Top level domains (Which domains are driving traffic to my site?)</li><li>Visitor profile > Technology > Technology overview (What technologies are people using to access my site?)</li><li>Visitor profile > Technology > Browsers, Browser type, Browser width, Browser height (Which company's browser, browser version, and its width and height, are people using to access my site?)</li><li>Visitor profile > Technology > Operating system, Operating system types (Which OS and which version of it do my visitors use?)</li><li>Visitor profile > Technology > Mobile carrier (Which mobile carriers do my visitors use to access my site?)</li><li>Visitor retention > Return frequency (How much time passes between my user's current visit and previous visits?)</li><li>Visitor retention > Return visits (How many of my visits are returning users?)</li><li>Visitor retention > Visit number (Which visit number bucket drives most of my key metrics)</li><li>Visitor retention > Sales cycle > Customer loyalty (Which loyalty segment do my users belong to?)</li><li>Visitor retention > Sales cycle > Days before first purchase (How many days passed between my users' first visit and their first purchase?)</li><li>Visitor retention > Sales cycle > Days since last purchase (How many days have passed between my users' current visit and their last purchase? )</li><li>Visitor retention > Mobile > Devices and Device types (Which devices and device types are my visitors using?)</li><li>Visitor retention > Mobile > Manufacturer (Which mobile device manufacturer do my visitors use?)</li><li>Visitor retention > Mobile > Screen size, Screen height, Screen width (Which mobile screen size/height/width do my visitors have?)</li><li>Visitor retention > Mobile > [Mobile app usage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app journeys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app metrics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app messaging](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app performance](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app retention](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** |<ul><li>Marketing channels > First touch channel, First touch channel detail (Which first touch channel, and which specific first touch channel is performing best?)</li><li>Marketing channels > First last channel, First last channel detail (Which last touch channel, and which specific last touch channel is performing best?)</li><li>Campaigns > Campaigns (Which campaigns are driving my key metrics?)</li><li>Campaigns > Campaign performance (What campaigns are driving the most revenue?)</li><li>Campaigns > Tracking code (Which campaign tracking codes perform the best?)</li><li>[Web acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobile acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: paid search](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Search keywords - all, paid, natural (Which search keywords and paid/natural search keywords drive my key metrics the best?)</li><li>Search engines - all, paid, natural (Which search engines and paid/natural search engines drive my key metrics the best?)</li><li>All search page ranking (Which search page are my users visiting from?)</li><li>Referring domains (Which domains are driving traffic to my site?)</li><li>Original referring domains (What was the first domain users were on before visiting my site?)</li><li>Referrers (Which URLs were my users on before clicking through to my site?)</li><li>Referrer types (Which category do my referring URLs belong to?)</li></ul> |

-->