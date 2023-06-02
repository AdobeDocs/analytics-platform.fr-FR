---
title: Présentation des filtres
description: Découvrez à quoi servent les filtres et comment créer un filtre simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 4e2d4d8c4f8145ae691114d57d663af96240b5f5
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 34%

---


# Présentation des filtres {#overview}

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les filtres permettent d’identifier des sous-ensembles de personnes en fonction de caractéristiques ou d’interactions web. Les filtres sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de votre équipe.

Les filtres peuvent être basés sur

- attributs (type de navigateur, appareil, nombre de visites, pays, genre),
- interactions (campagnes, recherche de mots-clés, moteur de recherche),
- sorties et entrées (personnes de Facebook,
- une landing page définie, un domaine référent),
- variables personnalisées (champ de formulaire, catégories définies, ID de client),
- et d’autres critères.

Vous pouvez créer et enregistrer des filtres dans le Créateur de filtres ou générer des filtres à partir d’une visualisation Abandons (dans Workspace). En outre, les filtres peuvent être utilisés ensemble comme filtres empilés.

Les options de filtrage comprennent le [Créateur de filtres](/help/components/filters/filter-builder.md) permettant de créer des segments et d’exécuter un pré-test et le [Gestionnaire de filtres](/help/components/filters/manage-filters.md) permettant de collecter, baliser, approuver, définir la sécurité et partager des filtres dans l’ensemble de votre organisation.

Le nombre maximal de filtres que vous pouvez créer par organisation IMS est de 50 000.

## Types de filtre {#types}

Pour plus d’informations sur les types de filtres disponibles et sur la manière de les créer, voir [Création de filtres](/help/components/filters/create-filters.md).

## Filtres séquentiels {#sequential}

Les filtres séquentiels vous permettent d’identifier des personnes en fonction de la navigation et de la page vue sur votre site, fournissant ainsi un filtre d’actions et d’interactions définies. Les filtres séquentiels vous aident à identifier ce qu’une personne aime et ce qu’elle évite. Lors de la création de filtres séquentiels, l’opérateur ALORS est utilisé pour définir et classer la navigation des personnes.

Voici un exemple :

<!--![](assets/sequential_fil.png)-->

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

Un filtre définit des conditions pour filtrer une personne selon ses attributs ou ses interactions avec votre site. Pour définir des conditions dans un filtre, vous définissez des règles pour filtrer les personnes selon leurs caractéristiques de personne et/ou de navigation. Pour ventiler davantage les données sur les personnes, vous pouvez filtrer selon des visites spécifiques et/ou des accès aux pages vues pour chaque personne. Le Créateur de filtres fournit une architecture simple permettant de créer ces sous-ensembles et d’appliquer des règles sous la forme de conteneurs imbriqués, selon la hiérarchie Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le Créateur de filtres définit Personne en tant que conteneur le plus éloigné, contenant les données principales spécifiques à la personne pour les visites et les pages vues. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne selon les sessions, et un conteneur Événement imbriqué permet de ventiler les informations de la personne selon des pages vues spécifiques. Chaque conteneur permet de créer des rapports sur l’historique d’une personne, les interactions ventilées par sessions ou la ventilation d’événements individuels.

### Conteneur Personne {#person}

Le conteneur Personne inclut chaque visite et page vue pour les personnes pendant une période donnée. Un filtre au niveau Personne renvoie la page qui respecte la condition plus toutes les autres pages consultées par la personne (et contraintes uniquement par des périodes définies). Comme il s’agit du conteneur ayant la définition la plus large, les rapports générés au niveau du conteneur Personne renvoient les pages vues de toutes les visites et vous permettent de générer une analyse multi-visites. Par conséquent, le conteneur Personne est le plus susceptible de changer selon des périodes définies.
Les conteneurs Personne peuvent inclure des valeurs basées sur l’historique global d’une personne :

- Jours avant le premier achat
- Page d’accès originale
- Domaines référents d’origine

### Conteneur Session {#session}

Le conteneur Session permet d’identifier les interactions de pages, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus souvent utilisé, car il capture les comportements pour l’ensemble de la session de visite une fois la règle respectée. Le conteneur Session permet également de définir les sessions que vous souhaitez inclure ou exclure de la création et de l&#39;application d&#39;un filtre. Il peut vous aider à répondre aux questions suivantes :

- Combien de sessions ont été associées aux sources de données Web et du centre d’appels ?
- Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs Session incluent des valeurs basées sur l’occurrence par Session :

- Type de session
- Page d’accès
- Fréquence des retours
- Mesures de participation
- Mesures allouées linéairement

### Conteneur Événement {#event}

Le conteneur Événement définit les événements de page que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du conteneur le plus étroit disponible pour vous permettre d’identifier des clics et des pages vues spécifiques pour lesquels une condition est vraie. Le conteneur Événement vous permet d’afficher un seul code de suivi ou d’isoler le comportement dans une section spécifique de votre site. Vous souhaitez peut-être également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une commande est passée.

Les conteneurs Événement comprennent des répartitions d’une seule page basées sur des valeurs :

- Produits
- Propriétés de liste
- Dimensions de liste
- Dimensions de marchandisage (dans le contexte d’événements)

## Modèle de filtre prêt à lʼemploi {#template}

Analytics traditionnel est fourni avec de nombreux filtres de modèle prêts à l’emploi (filtres) et mesures calculées. La plupart d’entre eux ne s’appliquent pas à CJA, ou doivent être renommés ou recréés. D’autres dépendent d’une solution pour les variables contextuelles dans CJA.

| Nom du filtre | Description |
| --- | --- |
| Toutes les données | Toutes les données sont un filtre obligatoire qui est ajouté dynamiquement à la création de rapports lorsqu’une mesure est ajoutée à la ligne d’un tableau à structure libre. |
