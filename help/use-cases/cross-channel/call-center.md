---
title: Importer les données du centre d’appel et web
description: Découvrez comment créer un jeu de données qui lie les données du centre dʼappel et du site web.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 100%

---

# Importer les données du centre d’appel et web

Customer Journey Analytics offre la fonctionnalité utile et robuste de combiner des jeux de données provenant de différentes sources dans un seul projet Espace de travail. Utilisez ce guide pour comprendre comment votre organisation peut combiner les données de site web aux données de centre d’appel. Vous pouvez, par exemple, comprendre les actions qu’un client effectue, le contenu qu’il affiche et les termes qu’il recherche avant de contacter le Service clientèle. Vous pouvez ensuite déterminer le contenu et les outils en libre-service afin d’améliorer la résolution des problèmes par les clients eux-mêmes sans qu’ils aient à appeler.

## Conditions préalables

* Le composant le plus important pour combiner ces deux jeux de données est un identifiant commun entre chaque source de données. Par exemple, un identifiant de client, une adresse e-mail, un nom d’utilisateur ou un numéro de téléphone hachés.
* Accès à Adobe Experience Platform et Customer Journey Analytics
* Si votre jeu de données comprend des journaux provenant d’un système de réponse vocale interactif, Adobe recommande de traiter les données afin qu’elles incluent uniquement des interactions rapides avant de les importer dans Platform.
* Si votre jeu de données comprend des journaux d’appels, Adobe recommande d’inclure les colonnes suivantes :
   * Date/heure de début de lʼappel
   * Raison de lʼappel
   * Identifiant du centre dʼappel
   * Identifiant de lʼagent du centre dʼappel
   * Durée de lʼappel
   * Résultat de l’appel
   * Coût de lʼappel (si disponible)
   * Toute métadonnée dʼappel supplémentaire que votre entreprise souhaite inclure

## Importer des données web et du centre d’appel dans Platform

Importez vos données dans Adobe Experience Platform. Voir [Création d’un schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=fr) et [Ingestion de données](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=fr) dans la documentation Adobe Experience Platform.

Lors de l’importation de données dans Platform, les conseils suivants peuvent vous aider à mieux comprendre les rapports en résultant :

* Assurez-vous que les identifiants utilisés pour lier ensemble les données du centre d’appel et web ont le même format.
* Incluez la source de données dans chaque jeu de données. Par exemple, incluez une colonne `data_source` dans chaque schéma et définissez la valeur de chaque événement sur `"Web"` ou `"Call center"`, respectivement. <!--mapper-->

## Assembler les identifiants des personnes ensemble

CJA requiert un identifiant commun pour générer un [jeu de données combiné](/help/connections/combined-dataset.md).

* Si vos jeux de données comportent déjà un identifiant commun sur chaque événement des deux jeux de données, vous pouvez ignorer cette étape et créer une connexion.
* Si l’un ou l’autre de vos jeux de données comporte un identifiant commun sur certains événements uniquement, vous pouvez assembler les données à l’aide de l’Analyse cross-canal. Voir la [Présentation de l’Analyse cross-canal](/help/cca/overview.md) pour connaître les étapes permettant d’activer l’ACC pour ces deux jeux de données.

## Créer une connexion dans CJA

[Créer une connexion](/help/connections/create-connection.md) dans CJA.

* Si vous utilisez l’ACC, vous pouvez utiliser un nouveau jeu de données assemblé. Utilisez le nouveau champ d’identifiant assemblé comme identifiant de personne.
* Sinon, vous pouvez sélectionner à la fois des jeux de données web et des jeux de centres d’appel d’origine à utiliser dans la connexion.

## Création d’une vue de données

Après avoir créé une connexion, vous pouvez [Créer une vue de données](/help/data-views/create-dataview.md) à utiliser dans Analysis Workspace. Les composants utiles sont les suivants :

* Une dimension de page avec la dernière touche et la persistance de session. Vous pouvez connecter les mesures du centre d’appel avec la dernière page qu’un client a consultée avant d’appeler.
* Une mesure d’appels qui utilise un champ de schéma « Raison du centre d’appels » pour augmenter les occurrences. Utilisez [Déduplication des mesures](/help/data-views/component-settings/metric-deduplication.md) afin qu’elle augmente une seule fois par session.

## Création de visualisations

Vous pouvez utiliser les visualisations suivantes pour obtenir des informations à partir de votre jeu de données assemblé.

### Superposition de jeux de données

Cette visualisation vous aide à comprendre comment l’ACC assemble les données.

1. Créez deux filtres. La variable utilisée dans ces deux filtres est la même variable mentionnée ci-dessus qui reflète la source de données de chaque événement. Voir [Créer un filtre](/help/components/filters/create-filters.md) pour plus d’informations.
   * Conteneur de personne où l’identifiant de jeu de données est égal à vos données web
   * Conteneur de personne où l’identifiant de jeu de données est égal à vos données de centre d’appel
2. Dans Analysis Workspace, faites glisser une visualisation [Venn](/help/analysis-workspace/visualizations/venn.md) sur la zone de travail de l’espace de travail.
3. Faites glisser les deux nouveaux filtres dans la zone **[!UICONTROL Ajouter le filtre]** et la mesure Personnes dans la zone **[!UICONTROL Ajouter la mesure]**.

La visualisation Venn qui en résulte montre le nombre de personnes dans votre jeu de données qui contiennent à la fois des données web et de centre d’appels. Plus le chevauchement est important, plus le nombre de personnes assemblées avec succès est élevé. Les zones qui ne se chevauchent pas représentent des personnes qui résident exclusivement dans un jeu de données ou lʼautre.

### Attribuer les événements du centre d’appel aux pages web

Ce tableau à structure libre vous permet d’afficher les pages principales qui contribuent aux événements du centre d’appel. Tout d’abord, assurez-vous que les dimensions et mesures souhaitées disposent du modèle d’attribution approprié :

1. Faites glisser la dimension qui contient les noms de vos pages web sur une visualisation de tableau à structure libre.
1. Remplacez la mesure par celle du centre d’appel dont vous souhaitez mesurer la.
1. Cliquez sur l’icône d’engrenage près de l’en-tête de mesure. Cliquez sur **[!UICONTROL Utiliser le modèle d’attribution différent du modèle par défaut]**.
1. Définissez le [Modèle d’attribution](/help/analysis-workspace/attribution/models.md) souhaité. Par exemple, un modèle Décroissance temporelle avec une demi-vie de 15 minutes et une fenêtre rétroactive de session. Ce modèle d’attribution fait référence aux pages menant à l’appel à votre centre d’appels.

Le rapport qui en résulte affiche les pages principales qui dirigent les appels vers votre centre d’appels. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Vous pouvez améliorer les données de ce tableau en divisant les appels par motif ou par catégorie.

1. Cliquez sur le chevron droit sous la dimension « Motif de l’appel » dans la liste des composants. Cette action révèle les valeurs de dimension individuelles.
2. Faites glisser la ou les valeurs de dimension souhaitées sous la mesure « Appels » qui filtre cette mesure selon chaque raison d’appel respective.
3. Répétez l’opération pour chaque motif d’appel que vous souhaitez analyser. Utilisez le filtre « Toutes les sessions » pour visualiser le total agrégé.

<!-- screenshot -->

### Visualisation de flux

Vous pouvez obtenir des informations sur ce qu’un client tentait de faire avant d’utiliser le canal du centre d’appel. Cette visualisation de flux vous aide à comprendre les parcours les plus fréquents qu’un client prend pour atteindre votre centre d’appels. Grâce à ces informations, vous pouvez déterminer les améliorations les plus efficaces que vous pouvez apporter à votre site afin que les clients soient moins susceptibles d’appeler.

1. Cliquez sur l’onglet **[!UICONTROL Visualisations]** à gauche et faites glisser une visualisation de flux sur l’espace de travail.
2. Cliquez sur l’onglet **[!UICONTROL Composants]** à gauche et recherchez la dimension « Motif de l’appel ».
3. Cliquez sur le chevron droit en regard de cette dimension. Cette action révèle les valeurs de dimension individuelles.
4. Faites glisser l’élément de dimension de motif de l’appel souhaité vers l’emplacement central de la visualisation de flux.
5. La visualisation de flux renseigne automatiquement les motifs d’appel précédents et suivants. Remplacez le motif de l’appel précédent par la dimension de page du site web.
6. Cliquez sur l’icône d’engrenage en haut à droite de la visualisation de flux et changez le conteneur de flux en **[!UICONTROL Session]**.

### Histogramme

Combien de clients ont appelé une fois, deux fois ou six fois ou plus ? Certaines de ces personnes ne visitent jamais le site. Utilisez la visualisation de l’histogramme pour déterminer le nombre de personnes qui entrent dans chaque conteneur. Pour celles qui ne visitent jamais le site, découvrez comment nous pouvons les encourager à se prendre en charge.

1. Cliquez sur l’icône **[!UICONTROL Visualisations]** à gauche et faites glisser la visualisation de l’histogramme sur l’espace de travail.
2. Cliquez sur l’onglet **[!UICONTROL Composants]** à gauche et faites glisser la mesure des appels vers la visualisation de l’histogramme.
3. Cliquez sur **[!UICONTROL Afficher les paramètres avancés]** au centre de la visualisation et personnalisez les conteneurs de votre choix.
4. Cliquez sur **[!UICONTROL Créer]**.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
