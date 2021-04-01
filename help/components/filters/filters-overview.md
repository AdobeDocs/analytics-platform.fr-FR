---
title: Présentation des filtres
description: Découvrez à quoi servent les filtres et comment créer un filtre simple.
translation-type: tm+mt
source-git-commit: bbf33bd751a6f66f58dc40a5efb48bd2f1c29021
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 92%

---


# Présentation des filtres

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les filtres vous permettent d’identifier des sous-ensembles de visiteurs selon des caractéristiques ou des interactions Web. Les filtres sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de votre équipe.

Les filtres peuvent être basés sur des attributs (type de navigateur, périphérique, nombre de visites, pays, sexe), des interactions (campagnes, recherche de mots-clés, moteur de recherche), des sorties et entrées (visiteurs provenant de Facebook, une landing page définie, un domaine référent), des variables personnalisées (champ de formulaire, catégories définies, ID de client) et d’autres critères.

Vous pouvez créer et enregistrer des filtres dans le Créateur de filtres ou générer des filtres à partir d’une visualisation Abandons (dans Workspace). En outre, les filtres peuvent être utilisés ensemble comme filtres empilés.

>[!IMPORTANT]
>Les filtres sont appelés « segments » dans Adobe Analytics. Nous avons renommé les segments en filtres, car Adobe Experience Platform a [une définition différente de « segment »](https://docs.adobe.com/content/help/fr-FR/experience-platform/segmentation/home.html).

Les options de filtrage comprennent le [Créateur de filtres](/help/components/filters/create-filters.md) permettant de créer des segments et d’exécuter un pré-test et le [Gestionnaire de filtres](/help/components/filters/manage-filters.md) permettant de collecter, baliser, approuver, définir la sécurité et partager des filtres dans l’ensemble de votre organisation.

## Filtres séquentiels

Les filtres séquentiels permettent d’identifier les visiteurs selon la navigation et la page vue sur votre site, fournissant un filtre d’actions et d’interactions définies. Les filtres séquentiels permettent d’identifier ce qu’aime un visiteur et ce qu’il évite. Lors de la création de filtres séquentiels, l’opérateur ALORS est utilisé pour définir et classer la navigation du visiteur.

Voici un exemple :

![](assets/sequential_fil.png)

| Visite 1 | Visite 2 | Visite 3 |
| --- | --- | --- |
| Le visiteur s’est rendu sur la landing page principale (A), a exclu la page de la campagne (B), puis a consulté la page des produits (C). | Puis le visiteur s’est à nouveau rendu sur la landing page principale (A), a exclu la page de la campagne (B), est retourné sur la page des produits (C), puis a consulté une nouvelle page (D). | Le visiteur a suivi le même chemin que lors des première et deuxième visites, puis a exclu la page F pour se rendre directement à la page des produits ciblés (G). |

## Conteneurs de filtres

Les filtres sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués permettent de définir les attributs des personnes et les actions en fonction de règles entre et dans les conteneurs.

>[!NOTE]
>Le conteneur Personne s’appelait autrefois conteneur Visiteur. Le conteneur Session s’appelait conteneur Visite et le conteneur Événement s’appelait conteneur Accès.

Un filtre définit des conditions de filtrage d’un visiteur basées sur ses attributs ou interactions avec votre site. Pour définir des conditions dans un filtre, définissez des règles permettant de filtrer les visiteurs selon leurs caractéristiques de visiteur et/ou de navigation. Pour ventiler plus en détail les données du visiteur, vous pouvez filtrer selon des visites spécifiques et/ou les accès aux pages vues pour chaque visiteur. Le Créateur de filtres fournit une architecture simple permettant de créer ces sous-ensembles et d’appliquer des règles sous la forme de conteneurs imbriqués, selon la hiérarchie Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le Créateur de filtres définit la Personne en tant que conteneur le plus éloigné, comportant les données principales spécifiques au visiteur pour les visites et les pages vues. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne selon les visites, et un conteneur Accès imbriqué permet de ventiler les informations du visiteur selon des pages vues spécifiques. Chaque conteneur permet de créer un rapport de l’historique du visiteur, de ses interactions ventilées par sessions ou de ses ventilations par événements individuels.

### Conteneur Personne

Le conteneur Personne inclut chaque visite et page vue pour les visiteurs au cours d’une période indiquée. Un filtre au niveau de la Personne renvoie la page qui respecte la condition plus toutes les autres pages consultées par le visiteur (et contraintes uniquement par des périodes définies). Comme il s’agit du conteneur ayant la définition la plus large, les rapports générés au niveau du conteneur Personne renvoient les pages vues de toutes les visites et permettent de générer une analyse multi-visites. De ce fait, le conteneur Personne est le plus susceptible de changer selon les périodes définies.
Les conteneurs Personne peuvent inclure des valeurs basées sur l’historique global d’un visiteur :

* Jours avant le premier achat
* Page d’accès originale
* Domaines référents d’origine

### Conteneur Session

Le conteneur Session permet d’identifier les interactions de pages, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus souvent utilisé car il capture les comportements pour l’ensemble de la Session une fois que la règle est respectée et permet de définir les sessions que vous souhaitez inclure ou exclure de la création et de l’application d’un segment. Il peut vous aider à répondre aux questions suivantes :

* Combien de visiteurs ont consulté la section Actualités et sports au cours de la même session ?
* Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs Session incluent des valeurs basées sur l’occurrence par Session :

* Numéro de session
* Page d’accès
* Fréquence des retours
* Mesures de participation
* Mesures allouées linéairement

### Conteneur Événement

Le conteneur Événement définit les événements de page que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du plus étroit des conteneurs disponibles, permettant d’identifier des clics et des pages vues spécifiques pour lesquels une condition est vraie (true) ou encore d’afficher un code de suivi unique ou d’isoler un comportement dans une section spécifique de votre site. Vous souhaitez peut-être également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une commande est passée.

Les conteneurs Événement comprennent des ventilations d’une seule page basées sur des valeurs :

* Produits
* Propriétés de liste
* Dimensions de liste
* Dimensions de marchandisage (dans le contexte d’événements)

## Modèle de filtre prêt à l’emploi

Les analyses traditionnelles s’accompagnent de nombreux segments de modèle prêts à l’emploi (filtres) et mesures calculées. Beaucoup d&#39;entre eux ne s&#39;appliquent pas à la CJA, ou devront être renommés ou recréés. D’autres dépendront d’une solution pour les variables contextuelles dans CJA.

| Nom du filtre | Description |
| --- | --- |
| Toutes les données | Il s’agit d’un filtre obligatoire qui est dynamiquement ajouté au rapports lorsqu’une mesure est ajoutée à la ligne d’un tableau à structure libre. |
