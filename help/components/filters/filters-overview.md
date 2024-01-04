---
title: Présentation des filtres
description: Découvrez à quoi servent les filtres et comment créer un filtre simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 23%

---


# Présentation des filtres {#overview}

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les filtres permettent d’identifier des sous-ensembles de personnes en fonction de caractéristiques ou d’interactions. Les filtres sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de votre équipe.

Les filtres peuvent être basés sur

- attributs (type de navigateur, appareil, nombre de visites, pays, genre),
- interactions (campagnes, recherche de mots-clés, moteur de recherche),
- les sorties et entrées (personnes issues de Facebook, une landing page définie, un domaine référent, un événement de géolocalisation),
- variables personnalisées (champ de formulaire, catégories définies, ID de client),
- et d’autres critères.

Vous pouvez créer et enregistrer des filtres dans le Créateur de filtres ou générer des filtres à partir d’une visualisation Abandons (dans Workspace). En outre, les filtres peuvent être utilisés ensemble comme filtres empilés.

Le filtrage comprend la variable [Créateur de filtres](/help/components/filters/filter-builder.md) pour créer des filtres et exécuter un pré-test, et la variable [Gestionnaire de filtres](/help/components/filters/manage-filters.md) pour collecter, baliser, approuver, définir la sécurité et partager des filtres dans l’ensemble de votre entreprise.

Le nombre maximal de filtres que vous pouvez créer par organisation IMS est de 50 000.

## Types de filtre {#types}

Pour plus d’informations sur les types de filtres disponibles et sur la manière de les créer, voir [Création de filtres](/help/components/filters/create-filters.md).

## Filtres séquentiels {#sequential}

Les filtres séquentiels vous permettent d’identifier les personnes en fonction de la navigation (pages vues sur votre site, interactions avec des scènes dans votre application mobile ou utilisation d’un menu dans une zone décochée). Les filtres séquentiels fournissent un filtre d’actions et d’interactions définies et vous aident à identifier ce qu’aime une personne et ce qu’elle évite. Lors de la création de filtres séquentiels, l’opérateur ALORS est utilisé pour définir et classer la navigation des personnes.

>[!IMPORTANT]
>
>Vous devez disposer de la variable **Sélectionner** pour créer des filtres séquentiels cross-canal. Contactez votre administrateur si vous ne savez pas quel package de Customer Journey Analytics vous disposez.

Voici un exemple :

| Session 1 | Session 2 | Session trois |
| --- | --- | --- |
| La personne s’est rendue sur la page d’entrée principale A, a exclu la page de la campagne B, puis a consulté la page des produits C. | La personne s’est à nouveau rendue à la page d’entrée principale A, a exclu la page de campagne B, est retournée à la page de produit C, puis à une nouvelle page D. | La personne a suivi le même chemin que lors des première et deuxième visites, puis a exclu la page F pour accéder directement à la page G du produit ciblé. |

## Conteneurs de filtres {#containers}

Les filtres sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués permettent de définir les attributs des personnes et les actions en fonction de règles entre et dans les conteneurs.


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Personne</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Session</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Événement</td>
</tr>
</table>

>[!NOTE]
>Le conteneur Personne s’appelait autrefois conteneur Visiteur. Le conteneur Session s’appelait conteneur Visite et le conteneur Événement s’appelait conteneur Accès.

Un filtre définit des conditions pour filtrer une personne en fonction de ses attributs ou interactions avec votre site, application mobile ou tout autre type d’appareil à partir duquel vous avez collecté des données. Pour définir des conditions dans un filtre, vous définissez des règles pour filtrer les personnes selon leurs caractéristiques de personne et/ou de navigation. Pour ventiler plus en détail les données des personnes, vous pouvez filtrer selon les visites et/ou les accès aux pages vues spécifiques, les touches d’écran et les choix de menus sur une décodeur pour chaque personne. Mais filtrez également les attributs que vous avez ingérés à partir d’un système de gestion de la relation client ou de fidélité. Le Créateur de filtres fournit une architecture simple permettant de créer ces sous-ensembles et d’appliquer des règles sous la forme de conteneurs imbriqués, selon la hiérarchie Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le Créateur de filtres définit Personne comme le conteneur le plus éloigné. Le conteneur contient les données principales spécifiques à la personne pour les visites et les pages vues, les écrans d’application mobile ou les écrans de menu sur un décodeur. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne selon les sessions, et un conteneur Événement imbriqué permet de ventiler les informations de la personne selon des interactions individuelles. Chaque conteneur vous permet de créer des rapports sur l’historique d’une personne, les interactions ventilées par sessions ou la ventilation d’événements d’expérience individuels.

### Conteneur Personne {#person}

Le conteneur Personne comprend chaque visite et page vue, écran d’application mobile, décodeur ou interaction console-jeu pour les personnes au cours d’une période donnée. Fondamentalement, chaque événement d’expérience qui fait partie des jeux de données que vous avez définis dans votre connexion de Customer Journey Analytics. Un filtre au niveau de la personne renvoie les pages vues, les applications mobiles ou les écrans de définition qui respectent la condition. Plus toutes les autres interactions de la même personne sur des canaux en ligne et hors ligne (et contraintes uniquement par des périodes définies). Comme il s’agit du conteneur ayant la définition la plus large, les rapports générés au niveau du conteneur Personne renvoient des pages vues, des écrans d’applications mobiles, etc., pour toutes les visites et vous permettent de générer une analyse cross-canal multi-visites. Par conséquent, le conteneur Personne est le plus susceptible de changer selon des périodes définies.
Les conteneurs Personne peuvent inclure des valeurs basées sur l’historique global d’une personne :

- Jours avant le premier achat
- Page d’accès d’origine ou écran d’accueil de l’application mobile
- Domaines référents d’origine

### Conteneur Session {#session}

Le conteneur Session permet d’identifier les interactions de page ou les interactions d’applications mobiles, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus souvent utilisé, car il capture les comportements pour l’ensemble de la session de visite une fois la règle respectée. Le conteneur Session permet également de définir les sessions que vous souhaitez inclure ou exclure de la création et de l&#39;application d&#39;un filtre. Il peut vous aider à répondre aux questions suivantes :

- Combien de sessions ont été associées aux sources de données Web et du centre d’appels ?
- Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs Session incluent des valeurs basées sur l’occurrence par Session :

- Type de session
- Page d’accès
- Fréquence des retours
- Mesures de participation
- Mesures allouées linéairement

Les vues de données dans Customer Journey Analytics vous permettent de déterminer la durée d’une session, mais aussi le moment où une nouvelle session doit être créée. Par exemple, vous pouvez définir une nouvelle session d’application mobile en fonction de chaque lancement de votre application mobile par un utilisateur. Voir [Paramètres de session](/help/data-views/session-settings.md) pour plus d’informations.

### Conteneur Événement {#event}

Le conteneur Événement définit la page, l’application mobile ou tout autre type d’événement que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du conteneur le plus étroit disponible pour vous permettre d’identifier des clics spécifiques, des pages vues, des clics sur le bouton dans une application mobile où une condition est vraie. Le conteneur Événement vous permet d’afficher un seul code de suivi ou d’isoler le comportement dans une zone spécifique de votre application mobile. Vous souhaitez peut-être également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une commande est passée.

Les conteneurs d’événements incluent des ventilations d’une seule page basées sur des valeurs pour :

- Produits
- Propriétés de liste
- Dimensions de liste
- Dimensions de marchandisage (dans le contexte d’événements)

## Modèle de filtre prêt à lʼemploi {#template}

Analytics traditionnel est fourni avec de nombreux modèles d’usine et mesures calculées. La plupart d’entre elles ne s’appliquent pas en Customer Journey Analytics, ou doivent être renommées ou recréées. D’autres dépendent d’une solution pour les variables contextuelles en Customer Journey Analytics.

| Nom du filtre | Description |
| --- | --- |
| Toutes les données | Toutes les données sont un filtre obligatoire qui est ajouté dynamiquement à la création de rapports lorsqu’une mesure est ajoutée à la ligne d’un tableau à structure libre. |
