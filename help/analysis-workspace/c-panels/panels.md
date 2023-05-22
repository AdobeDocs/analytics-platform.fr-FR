---
description: Un panneau est un ensemble de tableaux et de visualisations
title: Panneaux - Aperçu
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 51%

---

# Panneaux - Aperçu

Un [!UICONTROL panneau] est un ensemble de tableaux et de visualisations. Vous pouvez accéder aux panneaux à partir de l’icône supérieure gauche dans Workspace ou d’un [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md). Les panneaux sont utiles lorsque vous souhaitez organiser vos projets en fonction de périodes de temps, de vues de données ou de cas dʼutilisation dʼanalyse.

## Types de panneaux

Les types de panneau suivants sont disponibles dans Analysis Workspace pour [!UICONTROL Customer Journey Analytics] :

| Nom du panneau | Description |
| --- | --- |
| [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) | Faites votre choix parmi les panneaux et visualisations disponibles pour démarrer votre analyse. |
| [Panneau Quick Insights](quickinsight.md) | Construisez rapidement un tableau de forme libre et une visualisation d’accompagnement afin d’analyser et de découvrir des informations plus rapidement. |
| [Panneau d’attribution](attribution.md) | Comparez et visualisez rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion. |
| [Panneau à structure libre](freeform-panel.md) | Effectuez des comparaisons et des répartitions illimitées, puis ajoutez des visualisations pour raconter une histoire riche en données. |
| [Panneau Observateurs simultanés de médias](media-concurrent-viewers.md) | Analysez les visionneuses au fil du temps, avec des informations sur la simultanéité la plus élevée, et sur la capacité à ventiler et à comparer. |
| [Panneau Temps de lecture de média](media-playback-timespent/media-playback-time-spent.md) | L’analyse du temps de lecture permet de déterminer où s’est produit le pic d’accès simultanés mais aussi où des abandons ont eu lieu. |

![](assets/panel-overview.png)

Les panneaux [!UICONTROL Quick Insights], [!UICONTROL Vierge] et [!UICONTROL À structure libre] constituent un excellent point de départ pour votre analyse. [!UICONTROL Attribution IQ] est réservé à des analyses plus poussées. Un bouton `"+"` est disponible dans les projets afin que vous puissiez ajouter des panneaux vierges à tout moment.

Le panneau de démarrage par défaut est le panneau [!UICONTROL à structure libre], mais vous pouvez également choisir d’utiliser le [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) par défaut.

## Calendrier {#calendar}

Le calendrier du panneau contrôle la plage de compte-rendu des performances des tableaux et des visualisations dans un panneau.

Remarque : si un composant de période (violet) est utilisé dans un tableau, une visualisation ou une zone de dépôt de panneau, il remplace le calendrier du panneau.

![](assets/panel-calendar.png)

Vous pouvez appliquer une période au niveau de la minute dans les paramètres avancés du calendrier du panneau. Si vous créez des rapports sur une période qui sʼétale sur plusieurs jours, lʼheure de début sʼapplique au premier jour et lʼheure de fin au dernier jour de celle-ci.

## Zone de dépôt {#dropzone}

La zone de dépôt des panneaux vous permet dʼappliquer des filtres et des filtres déroulants à tous les tableaux et visualisations dʼun panneau. Vous pouvez appliquer un ou plusieurs filtres à un panneau. Le titre au-dessus de chaque filtre peut être modifié en cliquant sur le crayon de modification. Vous pouvez également faire un clic droit pour le supprimer complètement.

### Filtres

Faites glisser et déposez un filtre du rail de gauche dans la zone de dépôt du panneau pour commencer à filtrer le panneau.

![](assets/segment-filter.png)

### Filtres ad hoc

Vous pouvez également faire glisser les composants qui ne sont pas des filtres directement vers la zone de dépôt pour créer des filtres ad hoc, ce qui vous permet de gagner du temps et vous évite de passer par le créateur de filtres. Les filtres ainsi créés sont automatiquement définis comme des filtres au niveau de l’événement. Vous pouvez modifier cette définition en cliquant sur lʼicône dʼinformations (i) à côté du filtre, puis sur lʼicône de modification en forme de crayon, et la modifier dans le créateur de filtres.

Les filtres ad hoc sont un type de filtre rapide et sont locaux au projet. Elles ne s’affichent pas dans le rail de gauche à moins que vous ne les rendiez publiques.

Pour plus d’informations, voir [Filtres rapides](/help/components/filters/quick-filters.md).

![](assets/adhoc-segment-filter.png)

### Filtres déroulants statiques

Les filtres déroulants permettent d&#39;interagir avec les données de manière contrôlée. Par exemple, vous pouvez ajouter un filtre déroulant pour les types dʼéquipement mobile afin de filtrer le panneau par tablette, téléphone mobile ou bureau.

Les filtres de menu déroulant peuvent également servir à fusionner plusieurs projets. Par exemple, si vous avez plusieurs versions dʼun même projet avec des filtres Pays différents, vous pouvez les fusionner en un seul projet et ajouter un filtre déroulant Pays.

![](assets/dropdown-filter-intro.png)

Pour créer un filtre de liste déroulante statique :

* Pour les filtres déroulants utilisant des éléments de dimension, cliquez sur l’icône de flèche vers la droite située en regard de la dimension souhaitée dans le rail de gauche. Cette action expose tous les éléments de dimension disponibles. Sélectionnez plusieurs éléments de dimension de cette liste à l’aide de la case `[Shift + Click]` ou `[Ctrl + Click]`, puis déposez-les dans la zone de dépôt du panneau **pendant la conservation`[Shift]`**.
* Pour les filtres déroulants utilisant d’autres composants tels que des mesures, des filtres ou des périodes, sélectionnez plusieurs composants à l’aide de la fonction `[Shift + Click]` ou `[Ctrl + Click]`. Déposez la sélection dans la zone de dépôt du panneau. **pendant la conservation`[Shift]`**. Tous les types de composants sont traités comme des filtres dans ce contexte.
* Un filtre déroulant unique ne peut contenir qu’un seul type de composant. Si vous incluez plusieurs types de composants dans votre sélection, un filtre déroulant distinct est créé par type de composant. Par exemple, si vous incluez des mesures et des éléments de dimension dans votre sélection, deux filtres déroulants distincts sont créés. Un filtre de menu déroulant comprend des éléments de dimension, tandis que l’autre inclut des mesures.

Sélectionnez l’une des options de la liste déroulante pour modifier les données du panneau. Vous pouvez également choisir de ne pas filtrer les données du panneau en sélectionnant **[!UICONTROL Aucun filtre]**.

![](assets/create-dropdown.png)

Le fait de cliquer avec le bouton droit de la souris sur un filtre déroulant propose les options suivantes :

* **[!UICONTROL Ajouter une étiquette]**: Lorsque vous ajoutez un filtre déroulant à un projet, un libellé est automatiquement défini sur le nom du composant. Si vous supprimez le libellé, vous pouvez l’ajouter à nouveau avec cette option.
* **[!UICONTROL Supprimer le libellé]**: Supprimez le texte au-dessus d’un filtre déroulant.
* **[!UICONTROL Supprimer le filtre déroulant]**: Supprime le filtre de liste déroulante du panneau.

[Regardez la vidéo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=fr) pour en savoir plus sur l’ajout de filtres de menu déroulant à votre projet.

### Filtres déroulants dynamiques

Les filtres déroulants dynamiques vous permettent de déterminer les valeurs disponibles en fonction des données de la plage de rapports du panneau et les valeurs d’autres filtres déroulants. Vous pouvez par exemple créer deux listes déroulantes dynamiques à l’aide d’une dimension Pays et d’une dimension Villes . Lorsque vous sélectionnez un pays dans la liste déroulante UICONTROL Pays , la liste déroulante Villes s’adapte dynamiquement afin de n’afficher que les villes de ce pays.

Ce même concept s&#39;applique à toutes les dimensions; seuls les éléments de dimension qui apparaissent dans la période du panneau et les filtres sélectionnés sont visibles. Les éléments de Dimension sélectionnés dans les filtres déroulants statiques affectent les valeurs disponibles dans les filtres déroulants dynamiques. Cependant, l’inverse n’est pas vrai ; Les éléments de Dimension sélectionnés dans les filtres déroulants dynamiques n’affectent pas les valeurs disponibles dans les filtres déroulants statiques.

La sélection manuelle d’éléments de dimension est disponible si vous prévoyez qu’un certain élément de dimension sera collecté ultérieurement. Vous pouvez également effacer un filtre de liste déroulante dynamique afin qu’il ne contienne aucune valeur, ce qui permet à d’autres filtres de liste déroulante dynamiques de contenir plus de valeurs. Sélectionner **[!UICONTROL Effacer tout]** pour effacer la sélection de tous les filtres déroulants de ce panneau.

Pour créer un filtre de liste déroulante dynamique :

* Faites glisser et déposez une seule dimension dans la zone de dépôt du panneau. **pendant la conservation`[Shift]`**.
* Les filtres déroulants dynamiques ne sont pas disponibles pour les mesures, filtres ou plages de dates.
* Cliquez avec le bouton droit de la souris sur un filtre déroulant et sélectionnez **[!UICONTROL Supprimer le filtre]** pour le supprimer.

Un clic droit sur un filtre de liste déroulante dynamique fournit les mêmes options que les filtres de liste déroulante statiques.

## Menu contextuel {#right-click}

Pour accéder à d’autres fonctionnalités d’un panneau, faites un clic droit sur l’en-tête du panneau.

![](assets/right-click-menu.png)

Les paramètres suivants sont disponibles :

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Insérer la copie du panneau/de la visualisation] | Permet de coller (&quot;insérer&quot;) un panneau ou une visualisation copié à un autre emplacement du projet ou dans un autre projet. |
| [!UICONTROL Copier le panneau] | Permet de cliquer avec le bouton droit de la souris et de copier un panneau, de sorte que vous puissiez l’insérer à un autre emplacement du projet ou dans un autre projet. |
| [!UICONTROL Dupliquer le panneau] | Crée un double exact du panneau actuel, que vous pouvez ensuite modifier. |
| [!UICONTROL Réduire/Développer tous les panneaux] | Réduit et développe tous les panneaux du projet. |
| [!UICONTROL Réduire/Développer toutes les visualisations dans le panneau] | Réduit et développe toutes les visualisations du panneau actif. |
| [!UICONTROL Modifier la description] | Ajouter (ou modifier) une description textuelle du panneau. |
| [!UICONTROL Obtenir un lien vers le panneau] | Permet de renvoyer un utilisateur vers un panneau spécifique dans un projet. Lorsque l’utilisateur clique sur le lien, le destinataire doit se connecter avant d’être dirigé vers le panneau exact auquel il est lié. |
