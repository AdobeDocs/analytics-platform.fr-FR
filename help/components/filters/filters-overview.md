---
title: 'Présentation des '
description: Découvrez à quoi servent les  et comment créer un filtre simple.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


#  de

Les analyses de parcours client vous permettent de créer, gérer, partager et appliquer des  puissants et ciblés  à vos rapports.  vous permet d’identifier des sous-ensembles de en fonction de caractéristiques ou d’interactions sur le site Web. Les  de sont conçues comme des  d’informations codifiées que vous pouvez créer pour vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de l’équipe.

Les  de peuvent être basées sur des attributs (type de navigateur, périphérique, nombre de visites, pays, sexe), des interactions (campagnes, recherche de mots-clés, moteur de recherche), des sorties et des entrées (de Facebook, un  défini, un domaine référent), des variables personnalisées (champ de formulaire,  défini, ID de client) et d’autres critères.

Vous pouvez créer et enregistrer des  de dans le Créateur de filtres ou générer des  de à partir d’une visualisation Abandon (dans Workspace). En outre, les  peuvent être utilisés ensemble comme  de empilé.

>[!IMPORTANT]
Les  sont appelés &quot;segments&quot; dans Adobe Analytics. Nous avons renommé les segments en  car Adobe Experience Platform a une définition différente de &quot;segment&quot;. Un segment dans AEP fait référence à...

Filtering includes the [Filter Builder](/help/components/filters/create-filters.md) to construct filters and run a pre-test, and the [Filter Manager](/help/components/filters/manage-filters.md) to collect, tag, approve, set security, and share filters across your organization.

##  séquentiel

Les  séquentiels vous permettent d’identifier les en fonction de la navigation et des  de page sur votre site, fournissant un filtre des actions et interactions définies. Les segments séquentiels permettent d’identifier ce qu’aime un visiteur et ce qu’il évite. Lors de la création de  séquentiels, l’opérateur ALORS est utilisé pour définir et commander la navigation du.

Voici un exemple :

![](assets/sequential_fil.png)

| Visite 1 | Visite 2 | Visite 3 |
|---|---|---|
| Le est allé au principal (A), a exclu la page de campagne (B), puis a consulté la page Produit (C). | Le est de nouveau allé à la  principale (A), a exclu la page de campagne (B), puis est de nouveau allé à la page Produit (C), puis à une nouvelle page (D). | Le est entré et a suivi le même chemin que lors des première et deuxième visites, puis a exclu la page F pour accéder directement à une page de produit ciblée (G). |

## Filtrer les 

Les  de sont basées sur une hiérarchie de niveau Personne, Session et à l’aide d’un modèle de imbriqué. Le  imbriqué vous permet de définir les attributs et actions des personnes en fonction des règles entre et à l’intérieur du  du.

>[!NOTE]
>Le  de la personne était autrefois connu comme le . Le de session s’appelait le  Visite, et ledelaVisite était autrefois le Accès.

Un filtre définit des conditions pour filtrer un en fonction de ses attributs ou interactions avec votre site. Pour définir des conditions dans un filtre, vous définissez des règles pour filtrer les en fonction des caractéristiques du et/ou des caractéristiques de navigation. Pour ventiler plus en détail les données du visiteur, vous pouvez filtrer selon des visites spécifiques et/ou les accès aux pages vues pour chaque visiteur. Le Créateur de filtres fournit une architecture simple pour créer ces sous-ensembles et appliquer des règles sous la forme d’une personne, d’une session ou d’un  imbriqué et hiérarchique.

L’architecture de  utilisée dans le Créateur de filtres définit Personne comme le  le plus éloigné, contenant les données globales spécifiques auentre les visites et les  de page. Un de session imbriqué vous permet de définir des règles pour ventiler les données  du en fonction des sessions, tandis qu’un de  de session imbriqué vous permet de ventiler les informations du en fonction du de chaque page. Chaque  vous permet de créer des rapports sur un  historique de, les interactions ventilées par session ou la ventilation d’un  individuel.

###  de personne

Le de personne inclut chaque visite et chaque de page pour lesdans une période donnée. Un filtre au niveau Personne renvoie la page qui répond à la condition plus toutes les autres pages consultées par le (et uniquement limitée par des plages de dates définies). En tant que  de défini de manière plus large, les rapports générés au niveau du de personne renvoient des  de page pour toutes les visites et vous permettent de générer un de à plusieurs visites. Par conséquent, le  de la personne est le plus susceptible de changer selon des plages de dates définies.
Les  de personne peuvent inclure des valeurs basées sur un historique  de :

* Jours avant le premier achat

* Page d’accès originale

* Domaines référents d’origine

###  de session

Le de session vous permet d’identifier les interactions de page, les campagnes ou les conversions pour une session spécifique. Le de session est le le plus souvent utilisé, car il capture les comportements pour l’ensemble de la session de visite une fois la règle respectée et vous permet de définir les sessions que vous souhaitez inclure ou exclure dans la création et l’application d’un segment. Il peut vous aider à répondre à ces questions :

* Combien d&#39;ont consulté la section Actualités et sports au cours de la même session ?

* Quelles pages ont contribué à une conversion réussie en vente ?

Les  de session incluent des valeurs basées sur une occurrence par session :

* Numéro de session

* Page d’accès

* Fréquence des retours

* Mesures de participation

* Mesures allouées linéairement

### Event container

Le de  définit l’ de page que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du plus étroit des conteneurs disponibles, permettant d’identifier des clics et des pages vues spécifiques pour lesquels une condition est vraie (true) ou encore d’afficher un code de suivi unique ou d’isoler un comportement dans une section spécifique de votre site. Vous souhaitez peut-être également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une commande est passée.

Les  de  incluent des valeurs basées sur des ventilations d’une seule page :

* Produits

* Propriétés de liste

* Dimensions 

* Dimensions de marchandisage (dans le contexte des  de)