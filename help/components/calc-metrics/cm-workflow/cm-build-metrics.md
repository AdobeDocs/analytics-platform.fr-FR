---
description: Le créateur de mesures calculées fournit un canevas où faire glisser et déposer des dimensions, des mesures, des filtres et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou des mesures calculées avancées complexes.
title: Création de mesures
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 7cdd81c9e38219d2d17decd5b9c3e987b814fc53
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 49%

---

# Création de mesures

Customer Journey Analytics fournit un canevas permettant de faire glisser et de déposer des dimensions, des mesures, des filtres et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou des mesures calculées avancées complexes.

## Commencer à créer une mesure calculée

Vous pouvez utiliser le créateur de mesures calculées pour créer des mesures calculées. Une fois créées de cette manière, les mesures calculées sont disponibles dans la liste des composants et peuvent ensuite être utilisées dans des projets à l’échelle de votre organisation. Vous pouvez également créer une mesure calculée rapide, comme décrit dans la section [Créer des mesures calculées pour un seul projet](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) dans [Mesures](/help/components/apply-create-metrics.md).

Accédez au créateur de mesures calculées pour commencer à créer une mesure calculée disponible dans la liste des composants.

1. Accédez au créateur de mesures calculées de l’une des manières suivantes :

   * Dans Analysis Workspace, ouvrez un projet, puis sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Créer une mesure]**.
   * Dans Analysis Workspace, ouvrez un projet, puis sélectionnez l’icône **Plus** en regard de la section [!UICONTROL **Mesures**] dans le rail de gauche.
   * Dans [!DNL Customer Journey Analytics], accédez à **[!UICONTROL Composants]** > **[!UICONTROL Mesures calculées]**, puis sélectionnez **[!UICONTROL + Ajouter]** dans la partie supérieure de la page Mesures calculées.

1. Passez à la section [Zones du créateur de mesures calculées](#areas-of-the-calculated-metrics-builder).

## Zones du créateur de mesures calculées

<!-- 

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_viz_product_compatibility"
>title="Product compatibility"
>abstract="Indicates where in Customer Journey Analytics this calculated metric can be used, such as in Analysis Workspace, Report Builder, and so forth."  
>"Some calculated metrics cannot be used with experimentation. Calculated metrics that are not compatible with experimentation have the following value: "Everywhere in Customer Journey Analytics (excluding experimentation)" "
>"Various factors affect whether a calculated metric is compatible with experimentation. Learn more (https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation) ."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Use calculated metrics in experimentation"

-->

L’image suivante et le tableau qui l’accompagne décrivent certains des principaux domaines et fonctionnalités du créateur de mesures calculées.

![Nouvelle fenêtre de mesures calculées présentant les principales zones et fonctionnalités décrites dans cette section.](assets/cm_builder_ui.png)

| Champ | Description |
| --- | --- |
| Titre | La dénomination de la mesure est obligatoire. Vous ne pouvez pas enregistrer la mesure tant qu’elle ne porte pas de nom. |
| Description | Donnez-lui une description conviviale afin d’expliquer son utilisation et pour la distinguer de mesures similaires. <p>La description apparaît également dans le rapport. Il est préférable de NE PAS mettre la formule dans la description. A la place, décrivez ce pour quoi cette mesure doit être utilisée ou ne doit pas être utilisée. (La formule est générée lorsque vous créez la mesure, sous l’en-tête Résumé. Il n’est donc pas nécessaire d’ajouter la formule à la description.) </p> |
| Format | Décimale, Heure, Pourcentage et Devise font partie des choix possibles. |
| Nombre de décimales | Affiche le nombre de décimales qui apparaîtra dans le rapport. Le nombre maximal de décimales que vous pouvez spécifier est 10. |
| Tendance à la hausse affichée... | Ce paramètre de polarité des mesures indique si Analytics doit considérer une tendance à la hausse dans la mesure comme un événement positif (vert) ou négatif (rouge). En conséquence, le graphique du rapport s’affiche en vert ou rouge lorsque la tendance est à la hausse. |
| Devise | Devise de base pour cette vue de données. |
| Balises | Le balisage est un moyen efficace d’organiser les mesures. Tous les utilisateurs peuvent créer des balises et en appliquer une ou plusieurs à un segment. Cependant, vous ne pouvez afficher les balises que pour les filtres que vous possédez ou qui ont été partagés avec vous. Quels types de balises devriez-vous créer ? Vous trouverez ci-dessous quelques suggestions de balises utiles :<ul><li>**Noms d’équipes**, tels que Social Marketing, Mobile Marketing.</li><li>**Projets** (balises d’analyse), comme l’analyse de page d’accès.</li><li>**Catégories**, telles que Femmes ; Géographie.</li><li>**Workflows**, tels que A approuver ; Traités pour (une unité opérationnelle spécifique)</li></ul> |
| Résumé | <p>La formule Résumé se met à jour chaque fois que vous apportez une modification à la définition de mesure. Cette formule s’affiche également dans le rail des mesures à gauche lorsque vous passez la souris sur une mesure et cliquez sur le Icône <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> |
| Définition | C’est là que vous faites glisser des mesures/mesures calculées, des filtres et/ou des fonctions pour créer la mesure calculée. <ul><li>Si vous faites glisser une mesure calculée, elle développe automatiquement sa définition de mesure. </li> <li>Vous pouvez imbriquer des définitions dans des conteneurs. Cependant, contrairement aux conteneurs de filtre, ces conteneurs fonctionnent comme une expression mathématique et déterminent l’ordre des opérations. </li> </ul> |
| Opérateur | Divisé par ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) est l’opérateur par défaut, plus les opérateurs +, - et x. |
| Aperçu | Fournit une lecture rapide des erreurs possibles. L’aperçu couvre les 90 derniers jours. C’est une manière d’évaluer initialement si vous avez sélectionné les composants appropriés à votre mesure. Un résultat inattendu signifie que vous devez vérifier à nouveau la définition de mesure. |
| Compatibilité des produits | Indique où cette mesure calculée peut être utilisée en Customer Journey Analytics. <p>Les valeurs possibles sont les suivantes :</p><ul><li>[!UICONTROL **Partout dans Customer Journey Analytics**] : la mesure calculée peut être utilisée dans tous les Customer Journey Analytics, y compris dans Analysis Workspace, Report Builder, etc.</li><li>[!UICONTROL **Partout en Customer Journey Analytics (hors expérimentation)**] : la mesure calculée peut être utilisée dans tous les Customer Journey Analytics, à l’exception du panneau Expérience.</li> <p>Pour plus d’informations sur les critères qui déterminent si une mesure calculée peut être utilisée avec l’expérimentation, voir [ Utilisation des mesures calculées dans le panneau Expérience](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) dans le [panneau Expérience](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| Ajouter | Pour tous les types de mesures calculées, vous pouvez ajouter des conteneurs et des nombres statiques à la définition. Pour les mesures calculées avancées, vous pouvez également ajouter des filtres et des fonctions.<ul><li>Les conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. De ce fait, tout ce que contient un conteneur sera traité avant l’opération suivante.</li><li>Le fait de faire glisser un filtre sur un conteneur filtre tout ce qu’il contient. (Mesures calculées avancées uniquement)</li><li>Vous pouvez empiler plusieurs filtres dans un conteneur.</li></ul> |
| Icône représentant un engrenage (Type de mesure, Attribution) | Lorsque vous sélectionnez l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure et les modèles d’attribution. <p>**Remarque :** Tenez compte des points suivants lors de la mise à jour de l’attribution d’un composant vers un modèle d’attribution autre que celui par défaut :</p><ul><li>**Lors de l’utilisation du composant dans un rapport avec *une seule dimension* :** L’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.</li><li>**Lors de l’utilisation du composant dans un rapport avec *plusieurs dimensions* :** L’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.</li><li>Plusieurs dimensions sont disponibles uniquement lors de l’ [ export de données vers le cloud ](/help/analysis-workspace/export/export-cloud.md).</li></ul> <p>Pour plus d’informations sur l’attribution, voir [Paramètres du composant de persistance](/help/data-views/component-settings/persistence.md).</p> |
| Icône Plus (+) | Permet de créer un composant tel quʼun nouveau filtre (grâce auquel vous accédez au créateur de filtres). |
| Recherche de composants | Cette barre de recherche permet de rechercher des dimensions, des mesures, des filtres (mesures calculées avancées uniquement) et des fonctions (mesures calculées avancées uniquement). |
| Liste des dimensions | Plutôt que de quitter le créateur de mesures calculées pour créer un filtre simple (dans le créateur de filtres), par exemple &quot;Page = Page d’accueil&quot;, vous pouvez faire glisser Page et sélectionner Page d’accueil directement dans le créateur de mesures calculées. Le workflow de création de mesures calculées filtrées est ainsi beaucoup plus rationnel. |
| Liste des mesures | Les mesures sont réparties en 3 catégories :<ul><li>Mesures standard</li><li>Mesures calculées</li><li>Modèles de mesures - à la fin de la liste.</li></ul>Lorsque vous passez le curseur sur une mesure, vous pouvez voir lʼicône Infos à droite de celle-ci. Le fait de cliquer sur cette icône vous donne les informations suivantes :<ul><li>La formule de calcul.</li><li>Une tendance d’aperçu de la mesure.</li><li>Une icône de modification (crayon) en haut à droite qui vous permet d’accéder au créateur de mesures calculées où vous pouvez modifier cette mesure calculée.</li></ul> |
| Liste des filtres | (Mesures calculées avancées uniquement) Si vous êtes lʼadministrateur, cette liste affiche tous les filtres créés dans votre société de connexion. Si vous êtes un utilisateur non administrateur, cette liste affiche les filtres que vous possédez et ceux que vous partagez. |
| Liste des fonctions | (Mesures calculées avancées uniquement) Les fonctions sont divisées en deux listes : De base (utilisée le plus souvent) et Avancé . |
| Sélecteur de vue de données  | Ce sélecteur (en haut à droite) vous permet de basculer vers une autre vue de données. |
