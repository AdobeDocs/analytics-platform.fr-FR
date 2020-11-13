---
title: Importer les données du centre d’appels et du Web
description: Découvrez comment créer un jeu de données qui lie les données du centre d'appels et du site Web.
translation-type: tm+mt
source-git-commit: 8d2f70ad47dcf9b97808da3a04d32d3412a1f0c8
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# Importer les données du centre d’appels et du Web

Customer Journey Analytics offre la fonctionnalité utile et robuste de combiner des jeux de données provenant de différentes sources dans un seul projet Workspace. Utilisez ce guide pour comprendre comment votre entreprise peut associer des données de votre site Web à celles provenant de votre centre d’appels.

## Conditions préalables

* Le composant le plus important pour combiner ces deux ensembles de données est un identifiant commun entre chaque source de données. Par exemple, un ID de client, un courriel haché, un nom d’utilisateur de connexion ou un numéro de téléphone.
* Accès à Adobe Experience Platform et au Customer Journey Analytics
* Si votre jeu de données comprend des journaux provenant d’un système de réponse vocale interactif, l’Adobe recommande de traiter les données afin d’inclure uniquement des interactions rapides avant de les importer dans Platform.
* Si votre jeu de données comprend des journaux d’appels, l’Adobe recommande d’inclure les colonnes suivantes :
   * Date/heure de début de l&#39;appel
   * Raison de l&#39;appel
   * ID du centre d’appels
   * ID de l&#39;agent du centre d&#39;appels
   * Durée de l&#39;appel
   * Résultat de l&#39;appel
   * Coût de l&#39;appel (si disponible)
   * Toute méta-donnée d&#39;appel supplémentaire que votre entreprise souhaite inclure

## Importer des données Web et du centre d’appels dans la plate-forme

Commencez à importer des données dans Adobe Experience Platform. Voir [Création d’un schéma](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/tutorials/create-schema-ui.html) et [Envoi de données](https://docs.adobe.com/content/help/fr-FR/experience-platform/ingestion/home.html) dans la documentation Adobe Experience Platform.

Lors de l’importation de données dans la plate-forme, les conseils suivants peuvent vous aider à mieux comprendre les rapports résultants :

* Assurez-vous que l’identifiant utilisé pour lier ensemble les données du centre d’appels et du Web est également formaté.
* Incluez la source de données dans chaque jeu de données. Par exemple, incluez une colonne `data_source` dans chaque schéma et définissez la valeur de chaque événement sur `"Web"` ou `"Call center"`, respectivement. <!--mapper-->

## Affecter les identifiants des personnes ensemble

CJA requiert un identifiant commun pour générer un [ensemble de données combiné](../connections/combined-dataset.md).

* Si vos jeux de données comportent déjà un identifiant commun sur chaque événement des deux jeux de données, vous pouvez ignorer cette étape et créer une connexion.
* Si l’un ou l’autre de vos jeux de données comporte un identifiant commun sur certains événements seulement, vous pouvez assembler les données à l’aide d’Analytics sur plusieurs canaux. Voir [Présentation des analyses intercanaux](/help/connections/cca/overview.md) pour connaître les étapes permettant d&#39;activer le CCA pour ces deux ensembles de données.

## Créer une connexion dans CJA

[Créez une ](/help/connections/create-connection.md) connexion dans CJA.

* Si vous utilisez la DPA, vous pouvez utiliser un nouveau jeu de données assemblé. Utilisez le nouveau champ d’ID assemblé comme identifiant de personne.
* Sinon, vous pouvez sélectionner à la fois des jeux de données Web et des jeux de centres d’appels d’origine à utiliser dans la connexion.

## Création d’une vue de données

Après avoir créé une connexion, vous pouvez [créer une vue de données](/help/data-views/create-dataview.md) à utiliser dans Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Création de visualisations

Vous pouvez utiliser les visualisations suivantes pour obtenir des informations à partir de votre jeu de données assemblé.

### Superposition de données

Cette visualisation vous aide à comprendre comment l’ACC rassemble les données.

1. Créez deux filtres. La variable utilisée dans ces deux filtres est la même variable mentionnée ci-dessus qui reflète la source de données de chaque événement. Voir [Création d’un filtre](/help/components/filters/create-filters.md) pour plus d’informations.
   * Conteneur de personne où l’ID de jeu de données est égal à vos données Web
   * Conteneur de personne où l’ID de jeu de données est égal à vos données de centre d’appels
2. Dans Analysis Workspace, faites glisser une visualisation [Venn](/help/analysis-workspace/visualizations/venn.md) sur le canevas de l’espace de travail.
3. Faites glisser les deux nouveaux filtres dans la zone **[!UICONTROL Ajouter le filtre]** et la mesure Personnes dans la zone **[!UICONTROL Ajouter la mesure]**.

La visualisation de Venn qui en résulte montre le nombre de personnes dans votre jeu de données qui contiennent des données à la fois sur le Web et sur le centre d’appels. Plus le chevauchement est important, plus le nombre de personnes sélectionnées avec succès est élevé. Les zones qui ne se chevauchent pas représentent des personnes qui résident exclusivement dans un jeu de données ou l&#39;autre.

### Événements du centre d’appels d’attributs vers les pages Web

Ce tableau à structure libre vous permet d’afficher les pages principales qui contribuent aux événements du centre d’appels. Tout d’abord, assurez-vous que les dimensions et mesures souhaitées disposent du modèle d’attribution approprié :

1. Faites glisser la dimension qui contient les noms de vos pages Web sur une visualisation de tableau à structure libre.
1. Remplacez la mesure par la mesure du centre d’appels de votre choix que vous souhaitez mesurer la conversion.
1. Cliquez sur l’icône d’engrenage près de l’en-tête de mesure. Cliquez sur **[!UICONTROL Utiliser un modèle d’attribution autre que par défaut]**.
1. Définissez le [modèle d’attribution](/help/data-views/configure-dataviews.md#Attribution-model) souhaité.

Le rapport résultant affiche la mesure principale des données du centre d’appels. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: -->

<!--  use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
  filter by specific call reason using workspace dropdowns
  visualize flow of pages > call reason 
-->