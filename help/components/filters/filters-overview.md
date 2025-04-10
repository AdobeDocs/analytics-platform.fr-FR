---
title: Présentation des filtres
description: Découvrez à quoi servent les filtres et comment créer un filtre simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 392ba2b9cfe090901c3dac12459f9bd8d51fdca7
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# Présentation des filtres

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des filtres d’audience puissants et ciblés à vos rapports. Les filtres vous permettent d’identifier des sous-ensembles de personnes, de sessions ou d’événements en fonction de caractéristiques ou d’interactions. Les filtres sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de votre équipe.

Les filtres peuvent être basés sur :

- les attributs (type de navigateur, appareil, nombre de visites, pays, sexe),
- interactions (campagnes, recherche de mots-clés, moteur de recherche),
- les sorties et entrées (personnes provenant de Facebook, une page de destination définie, un domaine référent, un événement de limite géographique),
- les variables personnalisées (champ de formulaire, catégories définies, ID de client),
- et d’autres critères.

Voir [Créer des filtres](/help/components/filters/create-filters.md) pour connaître les différentes options disponibles pour créer des filtres. Vous pouvez ensuite créer, modifier et enregistrer la définition d’un filtre dans le [créateur de filtres](filter-builder.md). Vous pouvez également créer des filtres rapides à l’aide du [créateur de filtres rapides](quick-filters.md). Vous pouvez également générer des filtres à partir des visualisations dans Workspace, par exemple à l’aide de la visualisation [Abandons](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utilisez le [Gestionnaire de filtres](manage-filters.md) pour gérer les filtres.

## Planification des filtres

En particulier, en tant qu’administrateur, une planification correcte des filtres améliore les chances que les filtres soient utilisés. Tenez compte des points suivants lors de la planification des filtres :

- **Audience** : qui utilisera vos filtres ? Veillez à fournir une bonne description du filtre afin que l’audience comprenne :
   - Quel est l’objet de ce filtre ?

   - Quand dois-je utiliser ce filtre ?

- **Portée** : quel [conteneur de filtres](#filter-containers) représente le mieux les données que vous recherchez ? Utilisez le plus petit conteneur possible.

- **Composants** : décidez des composants à inclure dans la définition de filtre et par rapport aux valeurs que les conditions doivent valider.

- **Processus** : envisagez un processus d’approbation pour votre filtre. Il n’existe pas de workflow d’approbation dans Customer Journey Analytics, mais vous pouvez tout de même organiser un processus pour déterminer si vous approuvez ou non un filtre.

- **Modularité** : définissez des filtres en tenant compte de la modularité. Ainsi, les utilisateurs de vos filtres peuvent facilement [empiler des filtres](filter-builder.md#stack-filters) pour créer de nouveaux filtres puissants.


## Types de filtre

Vous pouvez créer trois types de filtres :

### Filtres rapides

Les filtres rapides vous permettent d’explorer facilement les données d’un projet Workspace donné, sans avoir à créer de filtre dans le [Créateur de filtres](/help/components/filters/create-filters.md). Vous définissez directement votre filtre dans l’interface de Workspace. Voir [Filtres rapides](quick-filters.md) pour plus d’informations.

### Filtres standard

Les filtres réguliers vous permettent d&#39;identifier des données (personnes, sessions, événements) selon une ou plusieurs conditions. Si plusieurs conditions sont définies, vous utilisez des opérateurs logiques tels que Et et Ou pour définir plus précisément le filtre. Vous pouvez utiliser des conteneurs pour regrouper des conditions et créer des filtres plus complexes. Voir [Créateur de filtres](filter-builder.md) pour plus d’informations.

### Filtres séquentiels

>[!IMPORTANT]
>
>Vous devez disposer du package **Select** pour créer des filtres séquentiels cross-canal. Contactez votre administrateur ou administratrice si vous n’êtes pas sûr du package Customer Journey Analytics dont vous disposez.

Les filtres séquentiels vous permettent d’identifier les données (personnes, sessions, événements) en fonction de la navigation (pages vues sur l’ensemble de votre site, interactions avec des scènes dans votre application mobile ou utilisation d’un menu sur un terminal). Les filtres séquentiels vous aident à identifier, par exemple, ce qu’une personne aime et ce qu’elle évite. Vous utilisez l’opérateur logique Then pour définir un filtre séquentiel. Voir [Filtres séquentiels](seg-sequential-build.md) pour plus d’informations.


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Conteneurs de filtres {#containers}

Les filtres sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués vous permettent de définir des conditions entre et au sein des conteneurs.


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
> - Dans Adobe Analytics, le conteneur **Personne** est connu sous le nom de conteneur **Visiteur**.
> - Dans Adobe Analytics, le conteneur **Session** est connu sous le nom de conteneur **Visite**.
> - Dans Adobe Analytics, le conteneur **Event** est connu sous le nom de conteneur **Hit**.
>

Un filtre définit des conditions pour filtrer les personnes, les sessions ou les événements en fonction de conditions. Par exemple, les conditions pour filtrer les personnes en fonction des caractéristiques de la personne et des caractéristiques de navigation. Pour ventiler davantage les données, vous pouvez filtrer des sessions spécifiques, des événements de page vue, des touches d’écran, des choix de menu sur un décodeur, etc. Mais filtrez également les attributs que vous avez ingérés à partir d’un CRM ou d’un système de fidélité. Le [créateur de filtres](/help/components/filters/filter-builder.md) fournit une interface simple pour créer ces sous-ensembles et appliquer des conditions dans des conteneurs Personne, Session ou Événement imbriqués et hiérarchiques.

L’architecture de conteneur utilisée dans le [Créateur de filtres](/help/components/filters/filter-builder.md) définit Personne comme le conteneur le plus à l’extérieur. Le conteneur contient les données principales spécifiques à la personne pour les sessions et les événements tels que les pages vues, les écrans d&#39;applications mobiles ou les écrans de menus sur un terminal. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne en fonction des sessions. Un conteneur Événement imbriqué vous permet de ventiler les informations sur la personne en fonction d’interactions individuelles. Chaque conteneur vous permet de créer des rapports sur l’historique d’une personne, les interactions réparties par sessions ou de ventiler des événements individuels.

### Conteneur Personne

Le conteneur Personne comprend chaque session et chaque événement pour les personnes qui remplissent les critères de la condition spécifiée dans le conteneur. Lorsque vous définissez un filtre avec une condition simple telle que `Page Name equals Checkout`, le conteneur de personnes est résolu sur :

- Toutes les personnes qui ont visité la page nommée `Checkout`.
- Toutes les sessions pour ces personnes.
- Toutes les données d’événement pour ces personnes.

En tant que conteneur le plus largement défini, les rapports générés au niveau du conteneur Personne renvoient des événements et des sessions pour toutes les personnes qui remplissent les critères du filtre. Le conteneur de personnes est le plus susceptible d’être modifié en fonction de périodes définies.
Les conteneurs Personne peuvent inclure des valeurs en fonction de l’historique global d’une personne :

- Jours avant le premier achat.
- Page d’entrée originale ou écran d’accueil de l’application mobile.
- Domaines référents d’origine.

### Conteneur Session

Le conteneur Session vous permet d’identifier les interactions de page ou les interactions d’application mobile, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus couramment utilisé, car il capture les comportements pour l’ensemble de la session une fois la règle remplie. Le conteneur Session permet également de définir les sessions à inclure ou à exclure lors de la création et de l’application d’un filtre.  Lorsque vous définissez un filtre avec une condition simple telle que `Page Name equals Checkout`, le conteneur de sessions est résolu sur :

- Toutes les sessions au cours desquelles une page nommée `Checkout` est visitée.
- Toutes les données d’événement pour ces sessions.

Le conteneur de sessions peut vous aider à répondre aux questions suivantes :

- Combien de sessions impliquaient des sources de données web et de centre d’appels ?
- Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs de session incluent des valeurs basées sur les événements par session :

- Type de session.
- Page d’entrée.
- Fréquence des retours.
- Mesures de participation.
- Mesures allouées linéairement.

Les vues de données dans Customer Journey Analytics vous permettent de déterminer la durée d’une session, mais aussi le moment où une nouvelle session doit être créée. Par exemple, vous pouvez définir une nouvelle session d’application mobile en fonction de chaque fois qu’un utilisateur lance votre application mobile. Voir [Paramètres de session](/help/data-views/session-settings.md) pour plus d’informations.

### Conteneur Événement

Le conteneur Événement définit la page, l’application mobile ou tout autre type d’événement que vous souhaitez inclure ou exclure d’un filtre. Il s’agit du conteneur le plus étroit disponible pour vous permettre d’identifier des clics spécifiques, des pages vues, des appuis sur un bouton dans une application mobile où une condition est vraie. Le conteneur Événement permet d&#39;afficher un code de suivi unique ou d&#39;isoler le comportement dans une zone particulière de votre application mobile. Vous pouvez également localiser une valeur spécifique lorsqu’une action se produit, par exemple le canal marketing sur lequel une commande a été passée. Lorsque vous définissez un filtre avec une condition simple telle que `Page Name equals Checkout`, le conteneur Événement est résolu sur :

- Tous les événements de page vue pour lesquels le nom de la page est `Checkout`.

Les conteneurs Événement incluent des répartitions de page unique basées sur des valeurs pour :

- Produits
- Propriétés de liste
- Dimensions de liste
- Dimensions de marchandisage (dans le contexte des événements)


### Conteneur de groupe logique

Groupe logique vous permet de regrouper des conditions dans un point de contrôle de filtre séquentiel unique. Dans le cadre de la séquence, la logique définie dans le conteneur identifié comme [!UICONTROL Groupe logique] est évaluée après tout point de contrôle séquentiel précédent et avant tout point de contrôle séquentiel suivant. Voir [Groupe logique](seg-sequential-build.md#logic-group) pour plus d’informations.

### Imbrication de conteneurs

Lors de la création de conteneurs dans d’autres conteneurs, vous créez en fait un filtre dans un filtre . La logique suivante est appliquée aux conteneurs imbriqués :

1. Déterminez les données qui sont incluses à l’aide du conteneur le plus éloigné. Toutes les données qui ne correspondent pas à cette règle externe sont ignorées dans le rapport.
2. Appliquez la définition du filtre imbriqué aux données restantes. La définition de filtre imbriqué NE s’applique PAS aux données ignorées par la première définition.
3. Répétez l’opération jusqu’à ce que toutes les définitions de filtre de conteneur imbriqué aient été calculées. Les données restantes sont ensuite incluses dans le résultat et utilisées pour le compte rendu des performances.

>[!NOTE]
>
>Lorsque vous imbriquez un filtre dans un autre (par exemple, si vous faites glisser un filtre du panneau Composants vers votre définition de filtre), un conteneur est créé avec une copie (et non une référence) de la définition de filtre déplacée.

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
>[Création de filtres](create-filters.md)
>[Créateur de filtres ](filter-builder.md)
>[Filtres rapides ](quick-filters.md)
>[Filtres séquentiels](seg-sequential-build.md)
>[Gérer les filtres ](manage-filters.md)
>
