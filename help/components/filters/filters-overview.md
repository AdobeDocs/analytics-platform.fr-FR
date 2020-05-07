---
title: Présentation des Filtres
description: Identifiez les filtres utilisés et comment créer un filtre simple.
translation-type: tm+mt
source-git-commit: 09dcb36b96d95276b357e0f1308a977f5db5d711
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 15%

---


# Présentation des filtres

Les analyses de parcours client vous permettent de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les Filtres vous permettent d’identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d’interactions sur le site Web. Les Filtres sont conçus comme des informations d’audience codifiées que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de l’équipe.

Les Filtres peuvent être basés sur des attributs (type de navigateur, périphérique, nombre de visites, pays, sexe), des interactions (campagnes, recherche de mots-clés, moteur de recherche), des sorties et entrées (visiteurs de Facebook, un landing page défini, domaine référent), des variables personnalisées (champ de formulaire, catégories définies, ID de client) et d’autres critères.

Vous pouvez créer et enregistrer des filtres dans le Créateur de filtres ou générer des filtres à partir d’une visualisation Abandons (dans Workspace). En outre, les filtres peuvent être utilisés ensemble comme filtres empilés.

>[!IMPORTANT]
>Les Filtres sont appelés &quot;segments&quot; dans Adobe Analytics. Nous avons renommé les segments en filtres, car Adobe Experience Platform a une définition différente de &quot;segment&quot;.

Filtering includes the [Filter Builder](/help/components/filters/create-filters.md) to construct filters and run a pre-test, and the [Filter Manager](/help/components/filters/manage-filters.md) to collect, tag, approve, set security, and share filters across your organization.

## filtres séquentiels

Les filtres séquentiels vous permettent d’identifier les visiteurs en fonction de la navigation et de la vue des pages sur votre site, ce qui vous permet de filtrer les actions et interactions définies. Les segments séquentiels permettent d’identifier ce qu’aime un visiteur et ce qu’il évite. Lors de la création de filtres séquentiels, l’opérateur ALORS est utilisé pour définir et commander la navigation du visiteur.

Voici un exemple :

![](assets/sequential_fil.png)

| Visite 1 | Visite 2 | Visite 3 |
|---|---|---|
| Le visiteur s’est rendu au landing page principal (A), a exclu la page de campagne (B), puis a consulté la page Produit (C). | Le visiteur s’est de nouveau rendu au landing page principal (A), a exclu la page de campagne (B) et est retourné à la page Produit (C), puis à une nouvelle page (D). | Le visiteur est entré et a suivi le même chemin que lors des première et deuxième visites, puis a exclu la page F pour accéder directement à une page de produit ciblée (G). |

## Filtrer les conteneurs

Les Filtres sont basés sur une hiérarchie au niveau de la personne, de la session et du Événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués vous permettent de définir des attributs de personne et des actions en fonction de règles entre et à l’intérieur des conteneurs.

>[!NOTE]
>Le conteneur de la Personne était autrefois connu comme le conteneur Visiteur. Le conteneur de session s’appelait le conteneur de visite et le conteneur de Événement était autrefois le conteneur Accès.

Un filtre définit des conditions pour filtrer un visiteur en fonction de ses attributs ou interactions avec votre site. Pour définir des conditions dans un filtre, vous définissez des règles pour filtrer les visiteurs en fonction des caractéristiques du visiteur et/ou des caractéristiques de navigation. Pour ventiler plus en détail les données du visiteur, vous pouvez filtrer selon des visites spécifiques et/ou les accès aux pages vues pour chaque visiteur. Le Créateur de filtres fournit une architecture simple pour créer ces sous-ensembles et appliquer des règles sous la forme de conteneurs imbriqués, hiérarchiques Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le Créateur de filtres définit Personne comme le conteneur le plus à l’extérieur, contenant des données globales spécifiques au visiteur entre les visites et les vues de page. Un conteneur de session imbriqué vous permet de définir des règles pour ventiler les données du visiteur en fonction des sessions et un conteneur de Événement imbriqué vous permet de ventiler les informations du visiteur en fonction de vues de page individuelles. Chaque conteneur vous permet de créer des rapports sur l’historique d’un visiteur, les interactions ventilées par session ou la ventilation de événements individuels.

### conteneur de personne

Le conteneur Personne inclut chaque visite et vue de page pour les visiteurs dans un délai spécifié. Un filtre au niveau Personne renvoie la page qui répond à la condition plus toutes les autres pages consultées par le visiteur (et limitée par des plages de dates définies). En tant que conteneur défini de manière plus générale, les rapports générés au niveau conteneur Personne renvoient des vues de page pour toutes les visites et vous permettent de générer une analyse à plusieurs visites. Par conséquent, le conteneur de la personne est le plus susceptible de changer en fonction de plages de dates définies.
Les conteneurs de personne peuvent inclure des valeurs basées sur l’historique global d’un visiteur :

* Jours avant le premier achat

* Page d’accès originale

* Domaines référents d’origine

### conteneur de session

Le conteneur de session vous permet d’identifier les interactions de page, les campagnes ou les conversions pour une session spécifique. Le conteneur de session est le conteneur le plus couramment utilisé, car il capture les comportements de la session de visite entière une fois la règle respectée et vous permet de définir les sessions que vous souhaitez inclure ou exclure dans la création et l’application d’un segment. Il peut vous aider à répondre à ces questions :

* Combien de visiteurs ont consulté la section Actualités et sports au cours de la même session ?

* Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs de session incluent des valeurs basées sur une occurrence par session :

* Numéro de session

* Page d’accès

* Fréquence des retours

* Mesures de participation

* Mesures allouées linéairement

### conteneur Événement

Le conteneur de Événement définit les événements de page que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du plus étroit des conteneurs disponibles, permettant d’identifier des clics et des pages vues spécifiques pour lesquels une condition est vraie (true) ou encore d’afficher un code de suivi unique ou d’isoler un comportement dans une section spécifique de votre site. Vous souhaitez peut-être également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une commande est passée.

Les conteneurs de Événement incluent des valeurs basées sur des ventilations d’une seule page :

* Produits

* Propriétés de liste

* Dimensions de Liste

* Dimensions de marchandisage (dans le contexte de événements)