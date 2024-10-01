---
description: Découvrez comment utiliser la visualisation de flux dans un projet Workspace.
title: Configuration d’une visualisation de flux
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 37%

---

# Configurer une visualisation de flux

Les visualisations de flux vous aident à comprendre le parcours provenant d’un événement de conversion spécifique sur votre site web ou votre application. Ou jusqu’à un événement de conversion spécifique. La visualisation trace un chemin d’accès à travers vos dimensions (et éléments de dimension) ou mesures.

Vous pouvez configurer le début ou la fin du chemin qui vous intéresse. Ou analysez tous les chemins qui traversent une dimension ou un élément de dimension.

![ L&#39;écran de configuration Flux qui affiche les champs Commence par, Contient et Se termine par.](assets/new-flow.png)

## Sélectionnez l’option  

1. Ajoutez une visualisation ![GraphPath](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Flux]**. Voir [Ajout d’une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Ancrez votre visualisation de flux à l’aide de l’une des options suivantes :

   * [!UICONTROL **Commence par**] (mesures, dimensions ou éléments) ou
   * [!UICONTROL **Contient**] (dimensions ou éléments) ou
   * [!UICONTROL **Se termine par**] (mesures, dimensions ou éléments)

   Chacune de ces catégories s’affiche à l’écran sous la forme d’une *zone de dépôt*. Il existe 3 manières de renseigner la zone de dépôt :

   * Utiliser le menu déroulant pour sélectionner des mesures ou des dimensions.
   * Faites glisser des dimensions ou des mesures depuis le panneau de gauche.
   * Commencez à saisir le nom d’une dimension ou d’une mesure, puis sélectionnez-la lorsqu’elle apparaît dans la liste déroulante.

   >[!IMPORTANT]
   >
   >Les mesures calculées ne peuvent pas être utilisées dans les champs **[!UICONTROL Commence par]** ou **[!UICONTROL Se termine par]** .

1. Si vous choisissez une mesure, vous devez également fournir une [!UICONTROL **Dimension de cheminement**] à utiliser comme chemin d’accès menant à ou provenant de votre composant sélectionné, comme illustré ici. La valeur par défaut est [!UICONTROL **Page**].

   ![Configuration du flux](assets/flow-configure.png)

1. (Facultatif) Sélectionnez **[!UICONTROL Afficher les paramètres avancés]** pour configurer l’une des options suivantes :


   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Développer les étiquettes]** | Habituellement, les étiquettes sur les éléments de flux sont tronquées pour gagner de l’espace à l’écran, mais vous pouvez afficher l’étiquette complète en cochant cette case.  Valeur par défaut = non coché. |
   | **[!UICONTROL Inclure des instances de répétition]** | Les visualisations de flux sont basées sur des instances d’une dimension. Ce paramètre vous donne la possibilité d’inclure ou d’exclure des instances répétées, par exemple des rechargements de page. Toutefois, les répétitions ne peuvent pas être supprimées des visualisations de flux qui incluent des dimensions à valeurs multiples, comme des listVars, listProps, s.product, eVars de marchandisage, etc. <p>Par défaut, cette option est désactivée.</p> |
   | **[!UICONTROL Limiter à la première/dernière occurrence]** | Limitez les chemins d’accès aux chemins qui commencent ou se terminent par la première ou la dernière occurrence d’une dimension, d’un élément ou d’une mesure. Voir [Limiter à la première/dernière occurrence](#example-scenario-for-limit-to-firstlast-occurrence) pour une explication plus détaillée. |
   | **[!UICONTROL Nombre de colonnes]** | Nombre de colonnes souhaité dans le diagramme de flux. Vous pouvez spéficier 5 colonnes maximum. |
   | **[!UICONTROL Éléments développés par colonne]** | Nombre d’éléments à inclure dans chaque colonne. Vous pouvez spécifier un maximum de 10 éléments développés par colonne. |
   | **[!UICONTROL Conteneur de flux]** | Vous pouvez basculer entre **[!UICONTROL Sessions]** et **[!UICONTROL Person]** pour analyser le cheminement. Ces paramètres vous aident à comprendre l’engagement d’une personne au niveau de la personne (entre les sessions) ou à contraindre l’analyse à une seule session. |

   >[!IMPORTANT]
   >
   >La combinaison du **[!UICONTROL Nombre de colonnes]** et des **[!UICONTROL Éléments développés par colonne]** détermine le nombre de requêtes sous-jacentes requises pour créer la visualisation de flux. Plus ces nombres sont élevés, plus le rendu d’une visualisation prend du temps.


1. Sélectionnez la **[!UICONTROL Version]**.


### Exemple

Supposons que vous souhaitiez tracer le chemin suivi par les utilisateurs vers et depuis les pages les plus populaires de votre site.

1. Créez une visualisation de flux comme décrit ci-dessus.
1. Faire glisser la dimension [!UICONTROL **Page**] dans le champ **[!UICONTROL Contient]**, puis sélectionner la [!UICONTROL **Version**].
1. La visualisation Flux se crée, avec la page la plus visualisée visible dans le noeud d’intérêt, au centre de la visualisation. Vous voyez également les pages principales qui mènent à cette page (à gauche du noeud de focus) ainsi que les pages principales qui sortent de cette page (à droite du noeud de focus).
1. Analysez les données dans le flux, comme décrit dans [Configurer](#configure).


## Configuration

Un résumé de la configuration Flux s’affiche en haut des visualisations. Les tracés dans le diagramme sont proportionnels. Les tracés plus épais sont ceux pour lesquels l’activité est la plus intense.

![Exemple de sortie de flux montrant Se termine par des visites, Dimension de cheminement : Page et Conteneur de flux : Visiteurs.](assets/flow-output.png)

Pour approfondir l’analyse des données, vous disposez de plusieurs options :

* Le diagramme de flux est interactif. Pointez sur le diagramme pour modifier les détails présentés.

* Si vous sélectionnez un nœud du diagramme, les détails correspondants s’affichent. Sélectionnez à nouveau le noeud pour le réduire.

  ![ Exemple de diagramme de flux interactif montrant les détails du noeud.](assets/node-details.png)

* Vous pouvez filtrer une colonne pour n’afficher que certains résultats, tels que l’inclusion et l’exclusion, la spécification de critères, etc.

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) sur le côté gauche ou droit pour développer une colonne.

* Pour personnaliser la sortie, utilisez les options [menu contextuel](#context-menu) .

* Pour modifier le flux ou le recréer avec différentes options, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) en regard du résumé de la configuration.

## Filtre

Au-dessus de chaque colonne, un filtre ![Filtre](/help/assets/icons/Filter.svg) s’affiche lorsque vous le survolez. En sélectionnant le filtre, vous obtenez la même boîte de dialogue de filtre qui existe dans le tableau à structure libre. Voir [Filtrer et trier](freeform-table/../../freeform-table/filter-and-sort.md).

* Utilisez **[!UICONTROL Afficher les paramètres avancés]** pour configurer des paramètres avancés afin d’inclure ou d’exclure certains critères avec une liste d’opérateurs. Voir [Filtres et tri](../freeform-table/filter-and-sort.md) pour plus d’informations.
* Une fois que vous avez filtré une colonne, cette colonne spécifique reflète le filtrage. Un ![filtre](/help/assets/icons/FilterColored.svg) bleu indique que la colonne est filtrée.  Le filtre réduit soit la colonne pour afficher uniquement l’élément autorisé dans le filtre. Ou il supprime tous les éléments, à l’exception de celui que vous souhaitez dans le filtre.
* Toutes les colonnes en aval et en amont persistent tant que des données circulent dans les noeuds restants.
* Pour supprimer un filtre, sélectionnez ![Filtre](/help/assets/icons/Filter.svg) pour ouvrir le menu de filtre. Supprimez les filtres appliqués, puis sélectionnez **[!UICONTROL Enregistrer]**. Le flux doit revenir à son état précédent, c’est-à-dire non filtré.

## Menu contextuel

Utilisez un menu contextuel sur n’importe quel noeud de la visualisation de flux avec les options suivantes :

| Option | Description |
|--- |--- |
| **[!UICONTROL Se concentrer sur ce nœud]** | Fait la mise au point sur le nœud sélectionné. Le nœud d’intérêt s’affiche au centre du diagramme Flux. |
| **[!UICONTROL Recommencer]** | Revenez au créateur de diagrammes à structure libre, où vous pouvez créer un diagramme Flux. |
| **[!UICONTROL Créez un filtre pour ce chemin]** | Création d’un filtre. Cette sélection vous amène au Créateur de filtres, où vous pouvez configurer le nouveau filtre. |
| **[!UICONTROL Répartition]** | Permet de ventiler le nœud d’après les dimensions, les mesures ou le temps disponibles. |
| **[!UICONTROL Colonne de filtre]** | Les mêmes options de filtre apparaissent que dans le tableau à structure libre. Pour plus d’informations sur les options disponibles, voir la section &quot;Appliquer un filtre simple ou avancé à une table&quot; dans [Filtrer et trier les tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| **[!UICONTROL Exclure l’élément]** ou **[!UICONTROL Restaurer les éléments exclus]** | Supprime un nœud donné de la colonne et le transforme automatiquement en filtre en haut de la colonne. Pour restaurer l’élément exclu, dans le menu contextuel, sélectionnez **[!UICONTROL Restaurer l’élément exclu]**. Vous pouvez également ouvrir le filtre en haut de la colonne et supprimer le rectangle contenant l’élément que vous venez d’exclure. |
| **[!UICONTROL Tendance]** | Permet de créer un diagramme de tendance pour le nœud. |
| **[!UICONTROL Afficher la colonne suivante]** / **[!UICONTROL Afficher la colonne précédente]** | Affiche la colonne suivante (à droite) ou précédente (à gauche) de la visualisation. |
| **[!UICONTROL Masquer la colonne]**n | Masque la colonne sélectionnée dans la visualisation. |
| **[!UICONTROL Développer toute la colonne]** | Permet de développer une colonne pour afficher tous les nœuds. Par défaut, seuls les cinq premiers nœuds sont présentés. |
| **[!UICONTROL Créer une audience d’après la sélection]** | Crée une audience à partir de la colonne sélectionnée. |
| **[!UICONTROL Réduire toute la colonne]** | Permet de masquer tous les nœuds d’une colonne. |

## Limiter à la première/dernière occurrence

Lorsque vous utilisez cette option, gardez à l’esprit que :

* **[!UICONTROL Limiter à la première/dernière occurrence]** compte uniquement la première ou la dernière occurrence de la série. Toutes les autres occurrences du critère **[!UICONTROL Commence par]** ou **[!UICONTROL Se termine par]** sont ignorées.
* Si elle est utilisée avec un flux **[!UICONTROL Commence par]**, seule la première occurrence correspondant au critère de départ est incluse.
Dans l’exemple ci-dessous, **toutes** occurrences de *Ajouter au panier* et *Catégorie principale de produit* dans chaque étape du flux sont incluses.
  ![Aucune limite, premier](assets/limitofffirst.png)

  Dans l’exemple ci-dessous, seules les occurrences **first** de *Add to cart* et *Product main category* dans chaque étape du flux sont incluses.
  ![Lint, start](assets/limitonfirst.png)
* Si elle est utilisée avec un flux **[!UICONTROL Se termine par]**, seule la dernière occurrence correspondant aux critères de fin est incluse.
Dans l’exemple ci-dessous, **toutes** occurrences de *Product main category* et *Add to cart* dans chaque étape du flux sont incluses.
  ![Aucune limite, premier](assets/limitofflast.png)

  Dans l’exemple ci-dessous, seules les occurrences **last** de *Product main category* et *Add to cart* dans chaque étape du flux sont incluses.
  ![Lint, start](assets/limitonlast.png)
* La série utilisée diffère en fonction du conteneur. Si vous utilisez le conteneur **[!UICONTROL Personne]**, la série d’événements correspond à la session. Si vous utilisez le conteneur **[!UICONTROL Session]** , la série d’événements correspond à tous les événements pour un utilisateur donné dans la période fournie.
* L’option **[!UICONTROL Limiter à la première/dernière occurrence]** peut être configurée dans les paramètres avancés lors de l’utilisation d’une mesure ou d’un élément de Dimension dans les champs **[!UICONTROL Commence par]** ou **[!UICONTROL Se termine par]** .


>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

