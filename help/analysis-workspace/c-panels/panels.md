---
description: Un panneau est un ensemble de tableaux et de visualisations
title: Panneaux - Aperçu
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '2129'
ht-degree: 97%

---

# Panneaux - Aperçu

Un [!UICONTROL panneau] est un ensemble de tableaux et de visualisations. Vous pouvez accéder aux panneaux à partir de l’icône située en haut à gauche dans Workspace ou à partir d’un [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md). Les panneaux sont utiles lorsque vous souhaitez organiser vos projets en fonction de périodes de temps, de vues de données ou de cas dʼutilisation dʼanalyse.

## Types de panneaux

Les types de panneau suivants sont disponibles dans Analysis Workspace pour [!UICONTROL Customer Journey Analytics] :

| Nom du panneau | Description |
| --- | --- |
| [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) | Faites votre choix parmi les panneaux et visualisations disponibles pour démarrer votre analyse. |
| [Attribution](attribution.md) | Comparez et visualisez rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion. |
| [Expérimentation](experimentation.md) | Comparez différentes expériences utilisateur, variantes de marketing ou de messagerie pour déterminer le meilleur moyen d’obtenir un résultat spécifique. |
| [Structure libre](freeform-panel.md) | Effectuez des comparaisons et des répartitions illimitées, puis ajoutez des visualisations pour raconter une histoire riche en données. |
| [Audience moyenne par minute de média](average-minute-audience-panel.md) | Analysez l’audience moyenne par minute pour un élément spécifique de contenu ou au cours d’une période personnalisée. |
| [Visionneuses simultanées de médias](media-concurrent-viewers.md) | Analysez les visionneuses au fil du temps, avec des informations sur la simultanéité la plus élevée, et sur la capacité à ventiler et à comparer. |
| [Temps passé à lire des médias](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | L’analyse du temps de lecture permet de déterminer où se produisent les pics d’audience mais aussi où des abandons ont eu lieu. |
| [Élément suivant ou précédent](next-previous.md) | Affiche les pages visitées suivantes ou précédentes. |
| [Aperçu rapide](quickinsight.md) | Construisez rapidement un tableau à structure libre et une visualisation d’accompagnement afin d’analyser et de mettre en évidence les informations plus rapidement. |


Les panneaux [!UICONTROL Aperçu rapide], [!UICONTROL Blank] et [!UICONTROL Tableau à stucture libre] constituent d’excellents points de départ pour votre analyse, tandis qu’[!UICONTROL Attribution] est réservé à des analyses avancées. Un ![AddCircle](/help/assets/icons/AddCircle.svg) est disponible au bas de la zone de travail. Vous pouvez donc ajouter des panneaux vierges à tout moment.

Le panneau de démarrage par défaut est le panneau [!UICONTROL Tableau à structure libre], mais vous pouvez également choisir d’utiliser le [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) ou l’[Aperçu rapide](/help/analysis-workspace/c-panels/quickinsight.md) par défaut. Consultez [Préférences des projets et analyses](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Créer un panneau

Pour créer un panneau :

* Faites glisser un panneau à partir du panneau de gauche **[!UICONTROL Panneaux]** dans votre zone de travail.
* Sélectionnez un panneau dans le [Panneau vierge](blank-panel.md).
* Utilisez le menu **[!UICONTROL Insérer]** dans Workspace et sélectionnez votre panneau. Vous pouvez également utiliser l’un des [raccourcis](../build-workspace-project/fa-shortcut-keys.md) pour insérer un panneau.

  ![Créer un panneau](assets/create-panel.png)

Vous pouvez effectuer les opérations suivantes :

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **dans** n’importe quel panneau pour ajouter une autre visualisation. Une fenêtre contextuelle s’affiche, vous permettant de sélectionner une visualisation.

  ![Fenêtre contextuelle affichant les visualisations possibles](assets/blank-panel.png)

  | Sélectionnez... | Pour créer un/une... |
  |---|---|
  | ![Tableau](/help/assets/icons/Table.svg) | [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Ligne](/help/assets/icons/GraphTrend.svg) | [Ligne](/help/analysis-workspace/visualizations/line.md) |
  | ![Graphique à barres verticales](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Numéro de résumé](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Texte](/help/assets/icons/Text.svg) | [Texte](/help/analysis-workspace/visualizations/text.md) |
  | ![Entonnoir de conversion](/help/assets/icons/ConversionFunnel.svg) | [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Workflow](/help/assets/icons/GraphPathing.svg) | [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![Graphique à aires empilées](/help/assets/icons/GraphAreaStacked.svg) | [Aires empilées](/help/analysis-workspace/visualizations/area.md) |
  | ![ChiffresTexte](/help/assets/icons/TextNumbered.svg) | [Table de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![Graphique à puces](/help/assets/icons/GraphBullet.svg) | [Puces](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![Graphique à anneaux](/help/assets/icons/GraphDonut.svg) | [Anneau](/help/analysis-workspace/visualizations/donut.md) |
  | ![DéplacementHautBas](/help/assets/icons/MoveUpDown.svg) | [Résumé des changements](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Histogramme](/help/assets/icons/Histogram.svg) | [Histogramme](/help/analysis-workspace/visualizations/histogram.md) |
  | ![Nuage de points](/help/assets/icons/GraphScatter.svg) | [Dispersion](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![Type](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) |
  | ![Arborescence](/help/assets/icons/GraphTree.svg) | [Plan en arborescence](/help/analysis-workspace/visualizations/treemap.md) |

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **à l&#39;extérieur** du dernier panneau de votre espace de travail pour ajouter un autre [panneau vierge](blank-panel.md).


## Vue de données

Chaque panneau est associé à une [vue de données](/help/data-views/data-views.md), identifiée par ![Données](/help/assets/icons/Data.svg) **[!UICONTROL *nom de la vue de données *]**dans le menu déroulant en haut à droite du panneau.

Lorsque vous créez un projet Workspace vierge, la vue de données par défaut du panneau initial correspond à la dernière vue de données avec laquelle vous avez travaillé dans Customer Journey Analytics.

Lorsque vous créez un panneau, la vue de données par défaut est basée sur la vue de données du panneau sur lequel vous avez travaillé pour la dernière fois dans le projet Workspace.

>[!IMPORTANT]
>
>La vue de données sélectionnée détermine les dimensions, les mesures et les segments disponibles pour la création des visualisations dans un panneau.
>
>
>Lorsque vous changez la vue de données d’un panneau, certains composants peuvent ne pas être disponibles dans la nouvelle vue de données. Cette modification peut empêcher votre visualisation de s’afficher correctement. Des avertissements peuvent s’afficher, par exemple :
>
>* Ce panneau contient des composants qui ne sont pas activés dans la vue de données sélectionnée. Changez de vue de données ou activez les composants requis dans la vue de données.
>* Impossible d’afficher la visualisation : vérifiez vos colonnes et lignes pour vous assurer qu’elles contiennent des composants valides.
>

## Calendrier

Le calendrier de panneau contrôle la période des rapports des tableaux et des visualisations dans un panneau.

>[!NOTE]
>
>Si un composant de période ![Calendrier](/help/assets/icons/Calendar.svg) est utilisé dans une visualisation ou un panneau (par exemple, comme segment), le composant de période remplace le calendrier de panneau.
>


![Fenêtre du calendrier affichant la période sélectionnée.](assets/panel-calendar.png)

1. Sélectionnez une période en sélectionnant d’abord la date de début, puis la date de fin.
Vous pouvez également sélectionner un **[!UICONTROL paramètre prédéfini]** dans le menu déroulant [!UICONTROL *Sélectionner un paramètre prédéfini*].

1. Vous pouvez également sélectionner **[!UICONTROL Afficher les paramètres avancés]** pour :

   * Spécifier une **[!UICONTROL heure de départ]** et une **[!UICONTROL heure de fin]** différentes de celles par défaut, à savoir `12:00 AM` (`0:00`) et `11:59 PM` (`23:59`). Les heures de fin comprennent toujours 59 secondes. Pour une période qui s’étend sur plusieurs jours, l’heure de début s’applique au premier jour de la période et l’heure de fin s’applique au dernier jour de la période. Utilisez **[!UICONTROL (Réinitialiser les heures)]** pour réinitialiser les heures de début et de fin à leurs valeurs par défaut.
   * **[!UICONTROL Faire correspondre les composants de la période au calendrier du panneau]**. Si cette option est désactivée, les composants de période utilisés dans le panneau se rapportent à l’heure actuelle. Si cette option est activée, les composants de période utilisés dans le panneau correspondent au calendrier de panneau.
   * **[!UICONTROL Utilisation de dates glissantes]**. Si cette option est activée, les périodes prédéfinies telles que **[!UICONTROL 7 derniers jours complets]** se mettent dynamiquement à jour en fonction de l’évolution de la date et de l’heure actuelles. Si cette option est désactivée, ces paramètres prédéfinis ne sont pas mis à jour une fois appliqués.

     ![Dates mobiles](assets/calendar-rolling.png)

     Vous pouvez sélectionner le texte entre parenthèses (par exemple : **[!UICONTROL début fixe - dates glissantes chaque jour]**) pour étendre le panneau et spécifier des détails pour **[!UICONTROL Début]** et **[!UICONTROL Fin]**.

      1. Sélectionnez **[!UICONTROL Début de]**, **[!UICONTROL Fin de]** ou **[!UICONTROL Jour fixe]**.
      1. Lorsque vous avez sélectionné **[!UICONTROL Début de]** ou **[!UICONTROL Fin de]**, vous pouvez créer une expression complète. Par exemple : **[!UICONTROL Fin de]** **[!UICONTROL l’année en cours]** **[!UICONTROL plus]** `1` **[!UICONTROL jour]**. Sélectionnez la valeur appropriée pour chaque partie de l’expression.
         * Sélectionnez une valeur pour la période actuelle. Par exemple, **[!UICONTROL année en cours]**.
         * Sélectionnez une valeur pour le calcul supplémentaire. Par exemple, **[!UICONTROL plus]**.
         * Lorsque vous avez spécifié un calcul supplémentaire, indiquez une valeur. Par exemple `1`.
         * Lorsque vous avez spécifié un calcul supplémentaire, sélectionnez la période à utiliser pour le calcul. Par exemple, **[!UICONTROL jour]**.

     Sélectionnez **[!UICONTROL Masquer les détails]** pour masquer les détails du calcul des dates glissantes.

1. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer la période au panneau à partir duquel vous avez ouvert le calendrier.
Sélectionnez **[!UICONTROL Appliquer à tous les panneaux]** pour appliquer la période à tous les panneaux du projet Workspace.


## Zone de dépôt {#dropzone}

La zone de dépôt des panneaux vous permet d’appliquer des segments et des segments déroulants à tous les tableaux et visualisations d’un panneau. Vous pouvez appliquer un ou plusieurs segments à un panneau.

### Segments

Faites glisser un segment à partir du panneau de gauche vers la zone de dépôt du panneau pour commencer la segmentation de votre panneau. Répétez cette procédure pour ajouter des segments supplémentaires au panneau. Les segments s’affichent côte à côte en haut du panneau.

![Le panneau de gauche affiche les mesures disponibles et la mesure client ou cliente mobile déposée dans la zone de dépôt du panneau.](assets/segment-filter.png)

#### Segments rapides

Vous pouvez également faire glisser les composants qui ne sont pas des segments directement vers la zone de dépôt pour créer des segments rapides, ce qui vous permet de gagner du temps et vous évite de passer par le [créateur de segments](/help/components/segments/seg-builder.md). Les segments ainsi créés sont automatiquement définis comme des segments de niveau événement. Cette définition peut être rapidement modifiée en sélectionnant l’option ![Modifier](/help/assets/icons/Edit.svg) à côté du nom du segment.


Pour en savoir plus, consultez [Segments rapides](/help/components/segments/seg-quick.md).

![Segments ad hoc rendus publics et déposés dans la zone de dépôt](assets/adhoc-segment-filter.png)

### Segments déroulants

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Déposer les segments](https://video.tv.adobe.com/v/23877?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


#### Segments déroulants statiques

Les segments déroulants statiques vous permettent d’interagir avec les données de manière contrôlée. Par exemple, vous pouvez ajouter un segment de menu déroulant pour les types d’appareil mobile afin de segmenter le panneau par tablette, téléphone mobile ou poste de travail.

Les segments déroulants statiques peuvent également être utilisés pour consolider plusieurs projets en un seul. Par exemple, si vous avez plusieurs versions d’un même projet avec des segments Pays différents, vous pouvez les fusionner en un seul projet et ajouter un segment de menu déroulant Pays.

![Segments déroulants statiques affichant le segment Canal de marché « Direct » en surbrillance.](assets/dropdown-filter-intro.png)

##### Créer des segments déroulants statiques

* Pour les segments déroulants qui utilisent des éléments de dimension, sélectionnez une dimension dans le panneau de gauche et faites-la glisser vers la zone de dépôt du panneau en maintenant la touche ⇧ (*Maj*) enfoncée. Cette action crée un segment déroulant avec tous les éléments de dimension associés à cette dimension.

  Ou, si vous souhaitez que le segment déroulant comprenne uniquement des éléments de dimension spécifiques associés à une dimension, cliquez sur l’icône de flèche vers la droite à côté de la dimension souhaitée dans le panneau de gauche. Cette action affiche tous les éléments de dimension disponibles. Sélectionnez plusieurs éléments de dimension dans cette liste à l’aide de ⇧+![Sélectionner](/help/assets/icons/Select.svg) (*Maj* + *Sélectionner*) ou ^+![Sélectionner](/help/assets/icons/Select.svg) (*Ctrl* + *Sélectionner*), puis déposez-les dans la zone de dépôt du panneau **tout en maintenant la touche** ⇧ enfoncée.

* Pour les segments déroulants qui utilisent un seul type de composant (par exemple, uniquement des dimensions, des segments ou des mesures), sélectionnez plusieurs éléments du même type dans le panneau de gauche à l’aide de ⇧+![Sélectionner](/help/assets/icons/Select.svg) ou ^+![Sélectionner](/help/assets/icons/Select.svg). Déposez ensuite les éléments dans la zone de dépôt du panneau **tout en maintenant la touche** ⇧ enfoncée.

  Un seul segment déroulant est créé avec les composants que vous avez sélectionnés.

* Pour les segments déroulants utilisant un mélange de types de composants (par exemple, 2 mesures et 3 segments), sélectionnez plusieurs composants à l’aide de ⇧+![Sélectionner](/help/assets/icons/Select.svg) ou ^+![Sélectionner](/help/assets/icons/Select.svg). Déposez la sélection dans la zone de dépôt du panneau **tout en maintenant la touche** ⇧ enfoncée. Dans ce contexte, tous les types de composants sont traités comme des segments déroulants distincts. Par exemple, si vous incluez à la fois des mesures et des éléments de dimension dans votre sélection, deux segments déroulants distincts sont créés : un segment déroulant incluant des éléments de dimension et un autre incluant des mesures.

Un segment déroulant fournit les options de menu contextuel suivantes :

* **[!UICONTROL Supprimer le segment déroulant]** : supprime le segment déroulant du panneau.
* **[!UICONTROL Supprimer le libellé]** : supprime le texte affiché au-dessus d’un segment déroulant. Pour modifier le libellé, pointez dessus et sélectionnez ![Modifier le libellé du segment déroulant](/help/assets/icons/Edit.svg).
* **[!UICONTROL Ajouter un libellé]** : lorsque vous ajoutez un segment déroulant à un projet, un libellé est automatiquement défini sur le nom du composant. Si vous supprimez le libellé, vous pouvez l’ajouter à nouveau avec cette option.
* **[!UICONTROL Exiger une sélection]** : nécessite qu’un segment soit défini sur le panneau.

##### Utiliser des segments déroulants statiques

Pour segmenter le panneau, les utilisateurs et les utilisatrices peuvent utiliser le menu de segments déroulants de l’une des façons suivantes :

* Appliquez un seul segment au panneau en sélectionnant le segment dans le segment déroulant.

* Appliquez plusieurs segments au panneau en sélectionnant plusieurs segments dans le segment déroulant. Le panneau est segmenté pour inclure l’un des segments sélectionnés.


#### Segments déroulants dynamiques

Les segments déroulants dynamiques vous permettent de déterminer les valeurs disponibles en fonction des données dans la plage de rapports du panneau et des valeurs dans d’autres segments déroulants. Vous pouvez par exemple créer deux listes déroulantes dynamiques à l’aide d’une dimension Pays et d’une dimension Villes. Lorsque vous sélectionnez un pays dans le menu déroulant **[!UICONTROL Pays]**, le menu déroulant **[!UICONTROL Villes]** s’ajuste de manière dynamique pour afficher uniquement les villes de ce pays.

Ce même concept s’applique à toutes les dimensions. Seuls les éléments de dimension qui apparaissent dans la période du panneau et les segments sélectionnés sont visibles. Les éléments de dimension sélectionnés dans les segments déroulants statiques affectent les valeurs disponibles dans les segments déroulants dynamiques. Cependant, l’inverse n’est pas vrai : les éléments de dimension sélectionnés dans les segments déroulants dynamiques n’affectent pas les valeurs disponibles dans les segments déroulants statiques.

La sélection manuelle d’éléments de dimension est possible si vous prévoyez qu’un élément de dimension donné sera collecté ultérieurement. Vous pouvez également effacer un segment déroulant dynamique afin qu’il ne contienne aucune valeur, permettant ainsi à d’autres segments déroulants dynamiques de contenir plus de valeurs. Sélectionnez **[!UICONTROL Réinitialiser tous]** pour effacer la sélection de tous les segments déroulants de ce panneau.

Pour créer un segment déroulant dynamique, procédez comme suit :

* Glissez-déposez une seule dimension dans la zone de dépôt du panneau **tout en maintenant la touche** ⇧ enfoncée.

Notez que les segments déroulants dynamiques ne sont pas disponibles pour les mesures, les segments ou les périodes.

Un segment déroulant dynamique permet d’obtenir les mêmes options de menu contextuel que les segments déroulants statiques.


## Menu contextuel

Pour accéder aux fonctionnalités supplémentaires d’un panneau, faites un clic droit sur l’en-tête du panneau pour accéder au menu contextuel.

![Options de clic droit pour un en-tête de panneau.](assets/right-click-menu.png)

Les options disponibles sont les suivantes :

| Option | Description |
| --- | --- |
| **[!UICONTROL Insérer le panneau copié]** | Vous permet de coller la copie d’un panneau ou d’une visualisation dans un autre emplacement au sein du projet, ou dans un autre projet. |
| **[!UICONTROL Insérer une visualisation copiée]** | Permet de coller la copie d’une visualisation dans un autre emplacement au sein du panneau, du projet, ou dans un autre projet. |
| **[!UICONTROL Appliquer la vue Données à tous les panneaux]** | Applique la vue de données de ce panneau à tous les autres panneaux du projet. |
| **[!UICONTROL Copier le panneau]** | Copie un panneau pour vous permettre de l’insérer dans un autre emplacement au sein du projet, ou dans un autre projet. |
| **[!UICONTROL Dupliquer le panneau]** | Crée un double exact du panneau actuel, que vous pouvez ensuite modifier. |
| **[!UICONTROL Réduire tous les panneaux]** | Réduit tous les panneaux du projet. |
| **[!UICONTROL Développer tous les panneaux]** | Développe tous les panneaux du projet. |
| **[!UICONTROL Réduire toutes les visualisations dans le panneau]** | Réduit toutes les visualisations dans le panneau actif. |
| **[!UICONTROL Développer toutes les visualisations dans le panneau]** | Développe toutes les visualisations du panneau actif. |
| **[!UICONTROL Modifier la description]** | Ajouter (ou modifier) une description textuelle du panneau. |
| **[!UICONTROL Obtenir un lien vers le panneau]** | Dirige un utilisateur ou une utilisatrice vers un panneau spécifique dans un projet. Lorsque le lien est sélectionné, la personne destinataire doit se connecter avant d’être dirigée vers le panneau lié. |

## Configuration

Certains panneaux (comme [!UICONTROL Attribution], [!UICONTROL Expérience], [!UICONTROL Audience moyenne par minute de média], etc.) possèdent une boîte de dialogue de configuration pour vous aider à créer la visualisation. Utilisez ![Modifier](/help/assets/icons/Edit.svg) en haut du panneau pour accéder à la configuration et la modifier.

![Configurer un panneau](/help/analysis-workspace/c-panels/assets/configure-panel.png)
