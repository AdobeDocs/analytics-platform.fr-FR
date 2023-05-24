---
description: Utilisation de la visualisation de flux dans un projet Workspace.
title: Configuration d’une visualisation de flux
feature: Visualizations
role: User, Admin
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 86%

---

# Configuration d’une visualisation de flux

Les visualisations de flux vous permettent de comprendre le parcours qui résulte d’un événement de conversion spécifique ou qui en résulte sur votre site web ou votre application. Elle trace un chemin d’accès à travers vos dimensions (et éléments de dimension) ou mesures. Le flux vous permet de configurer le début ou la fin du chemin qui vous intéresse, ou d’analyser tous les chemins qui traversent une dimension ou un élément de dimension.

![nouvelle interface utilisateur de flux](assets/new-flow.png)

## Étapes de configuration {#configure}

1. Pour commencer à créer un diagramme de flux, ajoutez un panneau vierge à votre projet, puis cliquez sur l’icône Visualisations dans le rail de gauche. Faites ensuite glisser la visualisation Flux dans le panneau. Vous pouvez aussi faire glisser la visualisation [!UICONTROL Flux] dans un projet existant.

1. Ancrez votre visualisation Flux à l’aide de l’une des trois options suivantes :

   * [!UICONTROL Commence par] (mesures, dimensions ou éléments) ou
   * [!UICONTROL Contient] (dimensions ou éléments) ou
   * [!UICONTROL Se termine par] (mesures, dimensions ou éléments)

   Chacune de ces catégories est présentée à l’écran comme une « zone de dépôt ». Il existe 3 manières de renseigner la zone de dépôt :

   * Utiliser le menu déroulant pour sélectionner des mesures ou des dimensions.
   * Faire glisser des éléments depuis la liste de dimensions ou de mesures.
   * Effectuer une recherche pour trouver les mesures ou la dimension souhaitée(s).

   Supposons, par exemple, que vous souhaitiez suivre tout ce qui mène à un événement de passage en caisse. Faites glisser une dimension ou une mesure liée au passage en caisse (telle que [!UICONTROL La commande existe]) dans la zone de dépôt **[!UICONTROL Se termine par]**.

1. Si vous choisissez une mesure, vous devez également fournir une [!UICONTROL Dimension de cheminement], comme illustré ici, que vous utiliserez pour créer le chemin. La valeur par défaut est [!UICONTROL Page].

   ![dimension du cheminement](assets/pathing-dim.png)

   >[!IMPORTANT]
   >
   >Les mesures calculées ne peuvent pas être déposées dans les zones de dépôt **[!UICONTROL Commence par]** ou **[!UICONTROL Se termine par]**.

1. (Facultatif) Cliquez sur **[!UICONTROL Afficher les paramètres avancés]** pour configurer les paramètres avancés :

   ![paramètres avancés](assets/adv-settings.png)

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Développer les étiquettes]** | Habituellement, les étiquettes sur les éléments de flux sont tronquées pour gagner de l’espace à l’écran, mais vous pouvez afficher l’étiquette complète en cochant cette case.  Valeur par défaut = non coché. |
   | **[!UICONTROL Inclure des instances de répétition]** | Les visualisations de flux sont basées sur des instances d’une dimension. Ce paramètre vous donne la possibilité d’inclure ou d’exclure des instances de répétition, telles que des rechargements de page. Toutefois, les répétitions ne peuvent pas être supprimées des visualisations de flux qui incluent des dimensions à valeurs multiples, comme des listVars, listProps, s.product, eVars de marchandisage, etc. Valeur par défaut = non coché. |
   | **[!UICONTROL Limiter à la première/dernière occurrence]** | Limitez les chemins à ceux qui commencent/se terminent par la première/dernière occurrence d’une dimension/élément/mesure. Consultez la section « Exemple de scénario de limitation à la première/dernière occurrence »ci-dessous pour en savoir plus. |
   | **[!UICONTROL Nombre de colonnes]** | Détermine le nombre de colonnes souhaité dans le diagramme Flux. |
   | **[!UICONTROL Éléments développés par colonne]** | Nombre d’éléments à inclure dans chaque colonne. |
   | **[!UICONTROL Conteneur de flux]** | <ul><li>Visite</li><li>Visiteur</li></ul> Permet de basculer entre Visite et Visiteur afin d’analyser le cheminement de la personne. Ces paramètres vous aident à comprendre l’engagement des personnes au niveau de la personne (entre les visites) ou à contraindre l’analyse à une seule visite. |

1. Cliquez sur **[!UICONTROL Créer]**.

## Afficher et modifier la sortie Flux {#output}

![sortie de flux](assets/flow-output.png)

Un résumé de la configuration Flux s’affiche en haut du diagramme. Les tracés dans le diagramme sont proportionnels. Les tracés plus épais sont ceux pour lesquels l’activité est la plus intense.

Pour approfondir l’analyse des données, vous disposez de plusieurs options :

* Le diagramme de flux est interactif. Pointez sur le diagramme pour modifier les détails présentés.

* Si vous cliquez sur un nœud du diagramme, les détails correspondants s’affichent. Cliquez de nouveau sur le nœud pour le réduire.

   ![node-details](assets/node-details.png)

* Vous pouvez filtrer une colonne pour n’afficher que certains résultats, tels que l’inclusion et l’exclusion, la spécification de critères, etc.

* Cliquez sur le signe plus (+) à gauche pour développer une colonne.

* Utilisez les options de clic droit décrites ci-dessous pour personnaliser davantage la sortie.

* Cliquez sur l’icône en forme de crayon en regard du résumé de la configuration pour modifier davantage le flux ou le recréer avec différentes options.

* Vous pouvez également exporter le diagramme Flux pour procéder à une analyse approfondie dans un fichier CSV de projet en sélectionnant **[!UICONTROL Projet]** > **[!UICONTROL Télécharger CSV]**.

## Filtrage

Un filtre apparaît au-dessus de chaque colonne lorsque vous le survolez avec votre curseur. En cliquant sur le filtre, vous verrez s’afficher une boîte de dialogue de filtre identique à celle qui se trouve actuellement dans le tableau à structure libre. Ce filtre fonctionne de la même manière que celui du tableau à structure libre.

* Utilisez les paramètres avancés pour inclure ou exclure certains critères avec notre liste d’opérateurs.
* Une fois que vous avez filtré un élément de la liste, la colonne en question reflète le filtrage. (Le filtre la réduit et affiche uniquement l’élément autorisé dans le filtre ou supprime tous les éléments à l’exception de celui que vous avez sélectionné dans le filtre.)
* Toutes les colonnes en aval et en amont doivent être conservées tant que les données alimentent les nœuds restants.
* Une fois appliquée, l’icône de filtre devient bleue au-dessus de la colonne filtrée.
* Pour supprimer un filtre, cliquez sur l’icône de filtre pour en ouvrir le menu. Supprimez les filtres appliqués, puis cliquez sur **[!UICONTROL Enregistrer]**. Le flux doit revenir à son état précédent, c’est-à-dire non filtré.

## Options du menu contextuel {#right-click}

| Option | Description |
|--- |--- |
| [!UICONTROL Se concentrer sur ce nœud] | Fait la mise au point sur le nœud sélectionné. Le nœud d’intérêt s’affiche au centre du diagramme Flux. |
| [!UICONTROL Recommencer] | Vous renvoie au générateur de diagrammes Structure libre, d’où vous pouvez créer un autre diagramme Flux. |
| [!UICONTROL Créer un segment à partir de ce point du flux] | Création d’un segment. Ouvre le Créateur de segments, d’où vous pouvez configurer le nouveau segment. |
| [!UICONTROL Répartition] | Permet de ventiler le nœud d’après les dimensions, les mesures ou le temps disponibles. |
| [!UICONTROL Tendance] | Permet de créer un diagramme de tendance pour le nœud. |
| [!UICONTROL Développer toute la colonne] | Permet de développer une colonne pour afficher tous les nœuds. Par défaut, seuls les cinq premiers nœuds sont présentés. |
| [!UICONTROL Réduire toute la colonne] | Permet de masquer tous les nœuds d’une colonne. |
| [!UICONTROL Exclure un élément]/[!UICONTROL Restaurer les éléments exclus] | Supprime un nœud donné de la colonne et le transforme automatiquement en filtre en haut de la colonne. Pour restaurer l’élément exclu, cliquez de nouveau avec le bouton droit de la souris et sélectionnez **[!UICONTROL Restaurer un élément exclu]**. Vous pouvez également ouvrir le filtre en haut de la colonne et supprimer le rectangle contenant l’élément que vous venez d’exclure. |

## Exemple de scénario de limitation à la première/dernière occurrence

Lorsque vous utilisez cette option, gardez à l’esprit que :

* **[!UICONTROL Limiter à la première/dernière occurrence]** compte uniquement la première ou la dernière occurrence de la série. Toutes les autres occurrences du critère **[!UICONTROL Commence par]** ou **[!UICONTROL Se termine par]** sont ignorées.
* Si vous utilisez cette option avec un flux **[!UICONTROL Commence par]**, seule la première occurrence correspondant au critère de début est incluse.
* Si vous utilisez cette option avec un flux **[!UICONTROL Se termine par]**, seule la dernière occurrence correspondant au critère de fin est incluse.
* La série utilisée diffère en fonction du conteneur. Si vous utilisez la variable **[!UICONTROL Visite]** , la série d’événements correspond à la session . Si vous utilisez la variable **[!UICONTROL Visiteur]** , la série d’événements correspond à tous les événements d’un utilisateur donné dans la période fournie.
* L’option **[!UICONTROL Limiter à la première/dernière occurrence]** peut être configurée dans les paramètres avancés lors de l’utilisation d’un élément de mesure ou de dimension dans les champs « Commence par » ou « Se termine par ».

Exemple de série d’événements :

Accueil > Produits > Ajouter au panier > Produits > Ajouter au panier > Facturation > Confirmation de commande

### Prenons une analyse de flux aux paramètres suivants :

* Commencer par [!UICONTROL Ajouter au panier] (élément de dimension)
* Dimension du cheminement [!UICONTROL Page]
* Conteneur de [!UICONTROL visites]

Si &quot;Limiter à la première/dernière occurrence&quot; est désactivé, cette série unique d’événements comptabilise 2 occurrences de &quot;Ajouter au panier&quot;.
Sortie de flux attendue :
« Ajouter au panier » (2) —> « Produits » (1)
-> « Facturation » (1)

Cependant, si l’option &quot;Limiter à la première/dernière occurrence&quot; est activée, seule la première occurrence de &quot;Ajouter au panier&quot; est incluse dans l’analyse.
Sortie de flux attendue :
« Ajouter au panier » (1) —> « Produits » (1)

### Tenez compte de la même série d’événements, mais en utilisant les paramètres suivants :

* Se termine par [!UICONTROL Ajouter au panier] (élément de dimension)
* Dimension du cheminement [!UICONTROL Page]
* Conteneur de [!UICONTROL visites]

If **[!UICONTROL Limiter à la première/dernière occurrence]** is *disabled*, cette série unique d’événements comptabilise 2 occurrences de &quot;Ajouter au panier&quot;.
Sortie de flux attendue :
« Produits » (2) &lt;— « Ajouter au panier » (2)

Cependant, si l’option **[!UICONTROL Limiter à la première/dernière occurrence]** est *activée*, seule la dernière occurrence d’[!UICONTROL Ajouter au panier] est incluse dans l’analyse.
Sortie de flux attendue :
« Produits » (1) &lt;— « Ajouter au panier » (1)
