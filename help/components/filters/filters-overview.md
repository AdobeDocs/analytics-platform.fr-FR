---
title: Présentation des filtres
description: Découvrez à quoi servent les filtres et comment créer un filtre simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 58%

---


# Présentation des filtres {#overview}

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les filtres permettent d’identifier des sous-ensembles de personnes en fonction de caractéristiques ou d’interactions web. Les filtres sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de votre équipe.

Les filtres peuvent être basés sur des attributs (type de navigateur, appareil, nombre de visites, pays, sexe), des interactions (campagnes, recherche de mots-clés, moteur de recherche), des sorties et entrées (personnes de Facebook, page d’entrée définie, domaine référent), des variables personnalisées (champ de formulaire, catégories définies, ID de client), ainsi que d’autres critères.

Vous pouvez créer et enregistrer des filtres dans le Créateur de filtres ou générer des filtres à partir d’une visualisation Abandons (dans Workspace). En outre, les filtres peuvent être utilisés ensemble comme filtres empilés.

Les options de filtrage comprennent le [Créateur de filtres](/help/components/filters/filter-builder.md) permettant de créer des segments et d’exécuter un pré-test et le [Gestionnaire de filtres](/help/components/filters/manage-filters.md) permettant de collecter, baliser, approuver, définir la sécurité et partager des filtres dans l’ensemble de votre organisation.

Le nombre maximal de filtres que vous pouvez créer par organisation IMS est de 50 000.

## Types de filtre {#types}

Pour plus d’informations sur les types de filtres disponibles et sur la manière de les créer, voir [Création de filtres](/help/components/filters/create-filters.md).

## Filtres séquentiels {#sequential}

Les filtres séquentiels vous permettent d’identifier des personnes en fonction de la navigation et de la page vue sur votre site, fournissant ainsi un filtre d’actions et d’interactions définies. Les filtres séquentiels vous aident à identifier ce qu’une personne aime et ce qu’elle évite. Lors de la création de filtres séquentiels, l’opérateur ALORS est utilisé pour définir et classer la navigation des personnes.

Voici un exemple :

![](assets/sequential_fil.png)

| Visite 1 | Visite 2 | Visite 3 |
| --- | --- | --- |
| La personne s’est rendue sur la page d’entrée principale (A), a exclu la page de la campagne (B), puis a consulté la page des produits (C). | La personne s’est à nouveau rendue sur la page d’entrée principale (A), a exclu la page de la campagne (B), est retournée sur la page des produits (C), puis a consulté une nouvelle page (D). | La personne a suivi le même chemin que lors des première et deuxième visites, puis a exclu la page F pour accéder directement à une page de produit ciblée (G). |

## Conteneurs de filtres {#containers}

Les filtres sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués permettent de définir les attributs des personnes et les actions en fonction de règles entre et dans les conteneurs.

>[!NOTE]
>Le conteneur Personne s’appelait autrefois conteneur Visiteur. Le conteneur Session s’appelait conteneur Visite et le conteneur Événement s’appelait conteneur Accès.

Un filtre définit des conditions pour filtrer une personne selon ses attributs ou interactions avec votre site. Pour définir des conditions dans un filtre, vous définissez des règles pour filtrer les personnes selon leurs caractéristiques de personne et/ou de navigation. Pour ventiler davantage les données sur les personnes, vous pouvez filtrer selon des visites spécifiques et/ou des accès aux pages vues pour chaque personne. Le Créateur de filtres fournit une architecture simple permettant de créer ces sous-ensembles et d’appliquer des règles sous la forme de conteneurs imbriqués, selon la hiérarchie Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le Créateur de filtres définit Personne en tant que conteneur le plus éloigné, contenant les données principales spécifiques à la personne pour les visites et les pages vues. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne selon les sessions, et un conteneur Événement imbriqué permet de ventiler les informations de la personne selon des pages vues spécifiques. Chaque conteneur permet de créer des rapports sur l’historique d’une personne, les interactions ventilées par sessions ou la ventilation d’événements individuels.

### Conteneur Personne {#person}

Le conteneur Personne inclut chaque visite et page vue pour les personnes pendant une période donnée. Un filtre au niveau Personne renvoie la page qui respecte la condition plus toutes les autres pages consultées par la personne (et contraintes uniquement par des périodes définies). Comme il s’agit du conteneur ayant la définition la plus large, les rapports générés au niveau du conteneur Personne renvoient les pages vues de toutes les visites et permettent de générer une analyse multi-visites. De ce fait, le conteneur Personne est le plus susceptible de changer selon les périodes définies.
Les conteneurs Personne peuvent inclure des valeurs basées sur l’historique global d’une personne :

* Jours avant le premier achat
* Page d’accès originale
* Domaines référents d’origine

### Conteneur Session {#session}

Le conteneur Session permet d’identifier les interactions de pages, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus souvent utilisé, car il capture les comportements pour lʼensemble de la Session une fois que la règle est respectée et permet de définir les sessions que vous souhaitez inclure ou exclure de la création et de lʼapplication dʼun filtre. Il peut vous aider à répondre aux questions suivantes :

* Combien de sessions ont été associées aux sources de données Web et du centre d’appels ?
* Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs Session incluent des valeurs basées sur l’occurrence par Session :

* Type de session
* Page d’accès
* Fréquence des retours
* Mesures de participation
* Mesures allouées linéairement

### Conteneur Événement {#event}

Le conteneur Événement définit les événements de page que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du plus étroit des conteneurs disponibles, permettant d’identifier des clics et des pages vues spécifiques pour lesquels une condition est vraie (true) ou encore d’afficher un code de suivi unique ou d’isoler un comportement dans une section spécifique de votre site. Vous souhaitez peut-être également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une commande est passée.

Les conteneurs Événement comprennent des répartitions d’une seule page basées sur des valeurs :

* Produits
* Propriétés de liste
* Dimensions de liste
* Dimensions de marchandisage (dans le contexte d’événements)

## Modèle de filtre prêt à lʼemploi {#template}

Adobe Analytics classique sʼaccompagne de nombreux modèles de filtres (filtres) et de mesures calculées prêts à lʼemploi. Nombre d’entre eux ne sʼappliquent pas à CJA, ou devront être renommés ou recrées. Dʼautres dépendent dʼune solution pour les variables contextuelles dans CJA.

| Nom du filtre | Description |
| --- | --- |
| Toutes les données | Il sʼagit dʼun filtre obligatoire qui est ajouté de manière dynamique au compte rendu des performances lorsquʼune mesure est ajoutée à la ligne dʼun tableau à structure libre. |
