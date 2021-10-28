---
description: Un panneau est un ensemble de tableaux et de visualisations
title: Panneaux - Aperçu
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
source-git-commit: 80a41d5678728eaab8a8a66455c8e1e8f1cdbb8e
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 60%

---

# Panneaux - Aperçu

Un [!UICONTROL panneau] est un ensemble de tableaux et de visualisations. Vous pouvez accéder aux panneaux à partir de l’icône située en haut à gauche dans Workspace ou à partir d’un [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md). Les panneaux s’avèrent utiles lorsque vous souhaitez organiser vos projets en fonction des périodes, des vues de données ou des cas pratiques d’analyse. Voici les types de panneau disponibles dans Analysis Workspace :

| Nom du panneau | Description |
| --- | --- |
| [Panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) | Faites votre choix parmi les panneaux et visualisations disponibles pour démarrer votre analyse. |
| [Panneau Quick Insights](quickinsight.md) | Construisez rapidement un tableau de forme libre et une visualisation d’accompagnement afin d’analyser et de découvrir des informations plus rapidement. |
| [Panneau d’attribution](attribution.md) | Comparez et visualisez rapidement de nombreux modèles d’attribution en utilisant n’importe quelle dimension ou mesure de conversion. |
| [Panneau à structure libre](freeform-panel.md) | Effectuez des comparaisons et des ventilations illimitées, puis ajoutez des visualisations pour raconter une histoire riche en données. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights], [!UICONTROL Vide] et [!UICONTROL Structure libre] Les panneaux constituent un excellent point de départ pour votre analyse. [!UICONTROL Attribution IQ] se prête à des analyses plus avancées. Un bouton `"+"` est disponible dans les projets afin que vous puissiez ajouter des panneaux vierges à tout moment.

Le panneau de démarrage par défaut est le panneau [!UICONTROL à structure libre], mais vous pouvez également choisir d’utiliser le [panneau vierge](/help/analysis-workspace/c-panels/blank-panel.md) par défaut.

## Calendrier {#calendar}

Le calendrier du panneau contrôle la plage de compte-rendu des performances des tableaux et des visualisations dans un panneau.

Remarque : si un composant de période (violet) est utilisé dans un tableau, une visualisation ou une zone de dépôt de panneau, il remplace le calendrier du panneau.

![](assets/panel-calendar.png)

Vous pouvez appliquer une période de niveau minute sous les paramètres avancés de votre calendrier du panneau. Si vous créez des rapports sur une période qui s’étend sur plusieurs jours, l’heure de début s’applique au premier jour et l’heure de fin s’applique au dernier jour de la période.

## Zone de dépôt {#dropzone}

La zone de dépôt du panneau vous permet d’appliquer des filtres et des filtres de menu déroulant à tous les tableaux et visualisations d’un panneau. Vous pouvez appliquer un ou plusieurs filtres à un panneau. Le titre au-dessus de chaque filtre peut être modifié en cliquant sur le crayon de modification. Vous pouvez également faire un clic droit pour le supprimer complètement.

### Filtres

Faites glisser et déposez les filtres du rail de gauche dans la zone de dépôt du panneau pour commencer à filtrer votre panneau.

![](assets/segment-filter.png)

### Filtres ad hoc

Vous pouvez également faire glisser directement les composants qui ne sont pas des filtres vers la zone de dépôt pour créer des filtres ad hoc, ce qui vous permet de gagner du temps et vous évite de passer par le Créateur de filtres. Les filtres ainsi créés sont automatiquement définis comme des filtres de niveau accès. Cette définition peut être modifiée en cliquant sur l’icône d’informations (i) en regard du filtre, puis sur l’icône de modification en forme de crayon et en la modifiant dans le Créateur de filtres.

Les filtres ad hoc sont locaux au projet et ne s’afficheront pas dans le rail de gauche à moins que vous ne les rendiez publics.

![](assets/adhoc-segment-filter.png)

### Filtres de menu déroulant {#dropdown-filter}

Outre les filtres, les filtres déroulants permettent d&#39;interagir avec les données de manière contrôlée. Par exemple, vous pouvez ajouter un filtre déroulant pour les types d’appareils mobiles afin de pouvoir filtrer le panneau par tablette, téléphone mobile ou bureau.

Les filtres de menu déroulant peuvent également servir à fusionner plusieurs projets. Par exemple, si vous avez plusieurs versions d’un même projet avec des filtres Pays différents appliqués, vous pouvez consolider toutes les versions en un seul projet et ajouter un filtre déroulant Pays .

![](assets/dropdown-filter-intro.png)

Pour créer des filtres de menu déroulant :

1. Pour créer un filtre de menu déroulant à l’aide des [!UICONTROL éléments de dimension], comme les valeurs dans la dimension [!UICONTROL canal marketing], cliquez sur l’icône de flèche vers la droite située à côté de votre dimension dans le rail de gauche. Cette opération expose tous les éléments disponibles. Sélectionnez un ou plusieurs éléments de composant dans le rail de gauche et déposez-les dans la zone de dépôt du panneau **tout en maintenant la touche Maj enfoncée**. Cela permet de transformer les composants en filtre déroulant plutôt qu’en filtre unique.
1. Pour créer un filtre déroulant à l’aide d’autres composants tels que les mesures, les filtres ou les périodes, sélectionnez un type de composant dans le rail de gauche et déposez-le dans la zone de dépôt du panneau. **tout en maintenant la touche Maj enfoncée**.
1. Sélectionnez l’une des options de la liste déroulante pour modifier les données du panneau. Vous pouvez également choisir de ne pas filtrer les données du panneau en sélectionnant **[!UICONTROL Pas de filtre]**.

![](assets/create-dropdown.png)

[Regardez la vidéo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=fr) pour en savoir plus sur l’ajout de filtres de menu déroulant à votre projet.

## Menu contextuel {#right-click}

Pour accéder à d’autres fonctionnalités d’un panneau, faites un clic droit sur l’en-tête du panneau.

![](assets/right-click-menu.png)

Les paramètres suivants sont disponibles :

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Insérer la copie du panneau/de la visualisation] | Permet de coller (« insérer ») la copie d’un panneau ou d’une visualisation à un autre emplacement au sein du projet, ou dans un tout autre projet. |
| [!UICONTROL Copier le panneau] | Permet de faire un clic droit et de copier un panneau de sorte que vous puissiez l’insérer à un autre emplacement du projet, ou dans un tout autre projet. |
| [!UICONTROL Dupliquer le panneau] | Crée un double exact du panneau actuel, que vous pouvez ensuite modifier. |
| [!UICONTROL Réduire/Développer tous les panneaux] | Réduit et développe tous les panneaux du projet. |
| [!UICONTROL Réduire/Développer toutes les visualisations dans le panneau] | Réduit et développe toutes les visualisations du panneau actif. |
| [!UICONTROL Modifier la description] | Ajouter (ou modifier) une description textuelle du panneau. |
| [!UICONTROL Obtenir un lien vers le panneau] | Permet de renvoyer un utilisateur vers un panneau spécifique dans un projet. Lorsque l’utilisateur clique sur le lien, le destinataire doit se connecter avant d’être dirigé vers le panneau exact auquel il est lié. |
