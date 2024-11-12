---
title: Présentation des filtres
description: Découvrez à quoi servent les filtres et comment créer un filtre simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 5fbb228fc02304be2246f0b49cb49de7f160b227
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# Présentation des filtres

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les filtres permettent d’identifier des sous-ensembles de personnes, de sessions ou d’événements en fonction de caractéristiques ou d’interactions. Les filtres sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de votre équipe.

Les filtres peuvent être basés sur :

- attributs (type de navigateur, appareil, nombre de visites, pays, genre),
- interactions (campagnes, recherche de mots-clés, moteur de recherche),
- les sorties et entrées (personnes issues de Facebook, une landing page définie, un domaine référent, un événement de géolocalisation),
- variables personnalisées (champ de formulaire, catégories définies, ID de client),
- et d’autres critères.

Voir [Création de filtres](/help/components/filters/create-filters.md) pour connaître les différentes options disponibles pour créer des filtres. Vous créez, modifiez et enregistrez ensuite la définition d’un filtre dans le [Créateur de filtres](filter-builder.md). Vous pouvez également créer des filtres rapides à l’aide de la [bulder de filtre rapide](quick-filters.md). Vous pouvez également générer des filtres à partir des visualisations dans Workspace, par exemple à l’aide de la visualisation [Abandons](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) .

Vous utilisez le [gestionnaire de filtres](manage-filters.md) pour gérer les filtres.

## Planification des filtres

En tant qu’administrateur notamment, la planification adéquate des filtres améliore les chances d’utilisation des filtres. Tenez compte des points suivants lors de la planification des filtres :

- **Audience** : qui utilisera vos filtres ? Assurez-vous de fournir une description adéquate du filtre pour que l’audience comprenne :
   - Quel est l’objet de ce filtre ?

   - Quand dois-je utiliser ce filtre ?

- **Portée** : quel [conteneur de filtres](#filter-containers) représente le mieux les données que vous recherchez ? Utilisez le plus petit conteneur possible.

- **Composants** : choisissez les composants à inclure dans la définition de filtre et par rapport aux valeurs que les conditions doivent valider.

- **Processus** : envisagez un processus d’approbation pour votre filtre. Il n’existe aucun processus d’approbation en Customer Journey Analytics, mais vous pouvez tout de même organiser un processus pour déterminer si vous approuvez un filtre.

- **Modularité** : définissez des filtres avec la modularité en tête. Ainsi, les utilisateurs de vos filtres peuvent facilement [empiler des filtres](filter-builder.md#stack-filters) pour créer de nouveaux filtres puissants.


## Types de filtre

Vous pouvez créer trois types de filtres :

### Filtres rapides

Les filtres rapides vous permettent d’explorer facilement les données dans un projet Workspace donné, sans avoir à créer un filtre dans le [Créateur de filtres](/help/components/filters/create-filters.md). Vous définissez directement votre filtre dans l’interface de Workspace. Pour plus d’informations, voir [Filtres rapides](quick-filters.md) .

### Filtres réguliers

Les filtres réguliers permettent d&#39;identifier les données (personnes, sessions, événements) selon une ou plusieurs conditions. Si plusieurs conditions sont remplies, vous utilisez des opérateurs logiques tels que Et et Ou pour définir le filtre. Vous pouvez utiliser des conteneurs pour regrouper des conditions et créer des filtres plus complexes. Voir [Créateur de filtres](filter-builder.md) pour plus d’informations.

### Filtres séquentiels

>[!IMPORTANT]
>
>Vous devez disposer du package **Select** pour créer des filtres séquentiels cross-canal. Contactez votre administrateur si vous ne savez pas quel package de Customer Journey Analytics vous disposez.

Les filtres séquentiels vous permettent d’identifier les données (personnes, sessions, événements) en fonction de la navigation (pages vues sur votre site, interactions avec des scènes dans votre application mobile ou utilisation d’un menu dans une boîte de dialogue contextuelle). Les filtres séquentiels vous aident à identifier, par exemple, ce qu’une personne aime et ce qu’elle évite. Vous utilisez l’opérateur Alors logique pour définir un filtre séquentiel. Pour plus d’informations, voir [Filtres séquentiels](seg-sequential-build.md) .


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Conteneurs de filtres {#containers}

Les filtres sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués permettent de définir des conditions entre et dans les conteneurs.


<table style="table-layout: fixed; border: none;" width="100%">

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
>
>Pour les utilisateurs d’Adobe Analytics :
> 
> - Le conteneur **Personne** est connu dans Adobe Analytics sous le nom de conteneur **Visiteur**.
> - Le conteneur **Session** est connu dans Adobe Analytics sous le nom de conteneur **Visite**.
> - Le conteneur **Event** est connu dans Adobe Analytics sous le nom de conteneur **Hit**.
>

Un filtre définit des conditions pour filtrer les personnes, les sessions ou les événements selon des conditions. Par exemple, des conditions pour filtrer les personnes en fonction de caractéristiques de personne et de caractéristiques de navigation. Pour ventiler plus en détail les données, vous pouvez filtrer selon des sessions spécifiques, des événements de page vue, des touches d’écran, des choix de menus sur un décodeur, etc. Mais filtrez également les attributs que vous avez ingérés à partir d’un système de gestion de la relation client ou de fidélité. Le [Créateur de filtres](/help/components/filters/filter-builder.md) fournit une interface simple pour créer ces sous-ensembles et appliquer des conditions dans des conteneurs imbriqués, hiérarchiques Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le [Créateur de filtres](/help/components/filters/filter-builder.md) définit Personne comme le conteneur le plus éloigné. Le conteneur contient des données principales spécifiques à la personne pour l’ensemble des sessions et événements tels que les pages vues, les écrans d’application mobile ou les écrans de menu sur un décodeur. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne selon les sessions. Un conteneur Événement imbriqué permet de ventiler les informations sur la personne en fonction d’interactions individuelles. Chaque conteneur permet de créer des rapports sur l’historique d’une personne, les interactions ventilées par sessions ou la ventilation d’événements individuels.

### Conteneur Personne

Le conteneur Personne comprend chaque session et chaque événement pour les personnes remplissant les conditions spécifiées dans le conteneur. Lorsque vous définissez un filtre avec une condition simple comme `Page Name equals Checkout`, le conteneur Personne résout :

- Toutes les personnes qui ont consulté la page portant le nom `Checkout`.
- Toutes les sessions pour ces personnes.
- Toutes les données d’événement pour ces personnes.

En tant que conteneur ayant la définition la plus large, les rapports générés au niveau du conteneur Personne renvoient des événements et des sessions pour toutes les personnes qui remplissent les critères du filtre. Le conteneur Personne est le plus susceptible de changer selon des périodes définies.
Les conteneurs Personne peuvent inclure des valeurs basées sur l’historique global d’une personne :

- Jours avant le premier achat.
- Page d’entrée d’origine ou écran d’accueil de l’application mobile.
- Domaines référents initiaux.

### Conteneur Session

Le conteneur Session permet d’identifier les interactions de page ou les interactions d’applications mobiles, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus souvent utilisé, car il capture les comportements pour l’ensemble de la session une fois la règle respectée. Le conteneur Session permet également de définir les sessions que vous souhaitez inclure ou exclure de la création et de l&#39;application d&#39;un filtre.  Lorsque vous définissez un filtre avec une condition simple telle que `Page Name equals Checkout`, le conteneur Session résout alors :

- Toutes les sessions où une page nommée `Checkout` est visitée.
- Toutes les données d’événement pour ces sessions.

Le conteneur de sessions peut vous aider à répondre aux questions suivantes :

- Combien de sessions ont impliqué des sources de données web et de centre d’appels ?
- Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs Session incluent des valeurs basées sur des événements par session :

- Type de session.
- Page d’accès.
- Fréquence des retours.
- Mesures de participation.
- Mesures allouées linéairement.

Les vues de données dans Customer Journey Analytics vous permettent de déterminer la durée d’une session, mais aussi le moment où une nouvelle session doit être créée. Par exemple, vous pouvez définir une nouvelle session d’application mobile en fonction de chaque lancement de votre application mobile par un utilisateur. Voir [Paramètres de session](/help/data-views/session-settings.md) pour plus d’informations.

### Conteneur Événement

Le conteneur Événement définit la page, l’application mobile ou tout autre type d’événement que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du conteneur le plus étroit disponible pour vous permettre d’identifier des clics spécifiques, des pages vues, des clics sur le bouton dans une application mobile où une condition est vraie. Le conteneur Événement vous permet d’afficher un seul code de suivi ou d’isoler le comportement dans une zone spécifique de votre application mobile. Vous pouvez également déterminer une valeur spécifique lorsqu’une action se produit, par exemple le canal marketing lorsqu’une commande a été passée. Lorsque vous définissez un filtre avec une condition simple comme `Page Name equals Checkout`, le conteneur Événement résout alors :

- Tous les événements de page vue dont le nom de page est égal à `Checkout`.

Les conteneurs d’événements incluent des ventilations d’une seule page basées sur des valeurs pour :

- Produits
- Propriétés de liste
- Dimensions de liste
- Dimensions de marchandisage (dans le contexte d’événements)


### Conteneur de groupes logiques

Le groupe logique vous permet de regrouper des conditions dans un seul point de contrôle de filtre séquentiel. Dans le cadre de la séquence, la logique définie dans le conteneur identifié comme [!UICONTROL Groupe logique] est évaluée après tout point de contrôle séquentiel précédent et avant tout point de contrôle séquentiel suivant. Voir [Groupe logique](seg-sequential-build.md#logic-group) pour plus d’informations.

### Conteneurs d’imbrication

Lors de la création de conteneurs dans d’autres conteneurs, vous créez en fait un filtre dans un filtre. La logique suivante s’applique aux conteneurs imbriqués :

1. Déterminez les données qui sont incluses à l’aide du conteneur le plus éloigné. Toutes les données qui ne correspondent pas à cette règle d’éloignement sont ignorées dans le rapport.
2. Appliquez la définition de filtre imbriqué aux données restantes. La définition de filtre imbriqué NE s’applique PAS aux données que la première définition a ignorées.
3. Répétez cette opération jusqu’à ce que toutes les définitions de filtre de conteneur imbriqué aient été calculées. Les données restantes sont alors incluses dans le résultat et utilisées pour la création de rapports.

>[!NOTE]
>
>Lorsque vous imbriquez un filtre dans un filtre (par exemple, vous faites glisser un filtre du panneau Composants sur votre définition de filtre), un conteneur est créé avec une copie (et non une référence) de la définition de filtre glissé.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Créer des filtres](create-filters.md)
>[Créateur de filtres](filter-builder.md)
>[Filtres rapides](quick-filters.md)
>[Filtres séquentiels](seg-sequential-build.md)
>[Gestion des filtres](manage-filters.md)
>
