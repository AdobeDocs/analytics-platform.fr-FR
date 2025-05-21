---
title: Présentation de la segmentation
description: Découvrez à quoi servent les segments et comment créer un segment simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: d0268ce9ba22228c5c42d600c173f39cd1001638
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---


# Présentation de la segmentation

Customer Journey Analytics vous permet de créer, gérer, partager et appliquer des segments d’audience puissants et ciblés à vos rapports. Les segments vous permettent d’identifier des sous-ensembles de personnes, de sessions ou d’événements en fonction de caractéristiques ou d’interactions. Les segments sont conçus comme des informations d’audience codifiées que vous pouvez créer pour vos besoins spécifiques, puis vérifier, modifier et partager avec d’autres membres de l’équipe.

Les segments peuvent être basés sur :

- les attributs (type de navigateur, appareil, nombre de visites, pays, sexe),
- interactions (campagnes, recherche de mots-clés, moteur de recherche),
- les sorties et entrées (personnes provenant de Facebook, une page de destination définie, un domaine référent, un événement de limite géographique),
- les variables personnalisées (champ de formulaire, catégories définies, ID de client),
- et d’autres critères.

Voir [Créer des segments](/help/components/filters/create-filters.md) pour connaître les différentes options disponibles pour créer des segments. Vous pouvez ensuite créer, modifier et enregistrer la définition d’un segment dans le [créateur de segments](filter-builder.md). Vous pouvez également créer des segments rapides à l’aide du [créateur de segments rapides](quick-filters.md). Vous pouvez également générer des segments à partir de visualisations dans Workspace, par exemple à l’aide de la visualisation [Abandons](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utilisez le [Gestionnaire de segments](manage-filters.md) pour gérer les segments.

## Planification des segments

En particulier, en tant qu’administrateur, une planification appropriée des segments améliore les chances que les segments soient utilisés. Tenez compte des points suivants lors de la planification des segments :

- **Audience** : qui utilisera vos segments ? Veillez à fournir une bonne description du segment afin que l’audience comprenne :
   - Quel est l’objet de ce segment ?

   - Quand dois-je utiliser ce segment ?

- **Portée** : quel [Conteneur de segments](#segment-containers) représente le mieux les données que vous recherchez ? Utilisez le plus petit conteneur possible.

- **Composants** : décidez des composants à inclure dans la définition de segment et par rapport aux valeurs que les conditions doivent valider.

- **Processus** : envisagez un processus d’approbation pour vos segments. Il n’existe pas de workflow d’approbation dans Customer Journey Analytics, mais vous pouvez tout de même organiser un processus pour déterminer si vous approuvez ou non un segment.

- **Modularité** : définissez des segments en gardant à l’esprit la modularité. Les utilisateurs de vos segments doivent pouvoir facilement [empiler des segments](filter-builder.md#stack-filters) pour créer de nouveaux segments puissants.


## Types de segments

Vous pouvez créer trois types de segments :

### Segments rapides

Les segments rapides vous permettent d’explorer facilement les données d’un projet Workspace donné, sans avoir à créer de segment dans le [Créateur de segments](/help/components/filters/create-filters.md). Vous définissez directement votre segment dans l’interface de Workspace. Voir [Segments rapides](quick-filters.md) pour plus d’informations.

### Segments standard

Les segments réguliers vous permettent d’identifier des données (personnes, sessions, événements) en fonction d’une ou de plusieurs conditions. Si vous disposez de plusieurs conditions, vous utilisez des opérateurs logiques tels que Et et Ou pour définir davantage le segment. Vous pouvez utiliser des conteneurs pour regrouper des conditions et créer des segments plus complexes. Voir [Créateur de segments](filter-builder.md) pour plus d’informations.

### Segments séquentiels

>[!IMPORTANT]
>
>Vous devez disposer du package **Select** pour créer des segments séquentiels cross-canal. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

Les segments séquentiels vous permettent d’identifier les données (personnes, sessions, événements) en fonction de la navigation (pages vues sur l’ensemble de votre site, interactions avec des scènes dans votre application mobile ou à l’aide d’un menu sur un terminal). Les segments séquentiels vous permettent, par exemple, d’identifier ce qu’une personne aime et ce qu’elle évite. Vous utilisez l’opérateur logique Then pour définir un segment séquentiel. Voir [Segments séquentiels](seg-sequential-build.md) pour plus d’informations.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Conteneurs de segments {#containers}

Les segments sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués vous permettent de définir des conditions entre et au sein des conteneurs.


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

Un segment définit des conditions pour segmenter des personnes, des sessions ou des événements en fonction de conditions. Par exemple, les conditions de segmentation des personnes sont basées sur les caractéristiques de la personne et les caractéristiques de navigation. Pour ventiler davantage les données, vous pouvez segmenter des sessions spécifiques, des événements de pages vues, des touches d’écran, des choix de menu sur un décodeur, etc. Vous pouvez également segmenter les attributs que vous avez ingérés à partir d’un CRM ou d’un système de fidélité. Le [créateur de segments](/help/components/filters/filter-builder.md) fournit une interface simple pour créer ces sous-ensembles et appliquer des conditions dans des conteneurs Personne, Session ou Événement imbriqués et hiérarchiques.

L’architecture de conteneur utilisée dans le [créateur de segments](/help/components/filters/filter-builder.md) définit la personne comme le conteneur le plus à l’extérieur. Ce conteneur contient les données principales spécifiques à la personne dans les sessions et événements tels que les pages vues, les écrans d&#39;applications mobiles ou les écrans de menus sur un terminal. Un conteneur Session imbriqué permet de définir des règles pour ventiler les données de la personne en fonction des sessions. Un conteneur Événement imbriqué vous permet de ventiler les informations sur la personne en fonction d’interactions individuelles. Chaque conteneur vous permet de créer des rapports sur l’historique d’une personne, les interactions réparties par sessions ou de ventiler des événements individuels.

### Conteneur Personne

Le conteneur Personne comprend chaque session et chaque événement pour les personnes qui remplissent les critères de la condition spécifiée dans le conteneur. Lorsque vous définissez un segment avec une condition simple telle que `Page Name equals Checkout`, le conteneur de personnes est résolu sur :

- Toutes les personnes qui ont visité la page nommée `Checkout`.
- Toutes les sessions pour ces personnes.
- Toutes les données d’événement pour ces personnes.

En tant que conteneur le plus largement défini, les rapports générés au niveau du conteneur de personnes renvoient des événements et des sessions pour toutes les personnes qui remplissent les critères pour le segment. Le conteneur de personnes est le plus susceptible d’être modifié en fonction de périodes définies.
Les conteneurs Personne peuvent inclure des valeurs en fonction de l’historique global d’une personne :

- Jours avant le premier achat.
- Page d’entrée originale ou écran d’accueil de l’application mobile.
- Domaines référents d’origine.

### Conteneur Session

Le conteneur Session vous permet d’identifier les interactions de page ou les interactions d’application mobile, les campagnes ou les conversions pour une session spécifique. Le conteneur Session est le conteneur le plus couramment utilisé, car il capture les comportements pour l’ensemble de la session une fois la règle remplie. Le conteneur Session permet également de définir les sessions à inclure ou à exclure lors de la création et de l’application d’un segment.  Lorsque vous définissez un segment avec une condition simple telle que `Page Name equals Checkout`, le conteneur de sessions est résolu sur :

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

Le conteneur Événement définit la page, l’application mobile ou tout autre type d’événement que vous souhaitez inclure ou exclure d’un segment. Il s’agit du conteneur le plus étroit disponible. Il vous permet d’identifier des clics spécifiques, des pages vues et des appuis sur un bouton dans une application mobile où une condition est vraie. Le conteneur Événement permet d&#39;afficher un code de suivi unique ou d&#39;isoler le comportement dans une zone particulière de votre application mobile. Vous pouvez également localiser une valeur spécifique lorsqu’une action se produit, par exemple le canal marketing sur lequel une commande a été passée. Lorsque vous définissez un segment avec une condition simple telle que `Page Name equals Checkout`, le conteneur Événement est résolu sur :

- Tous les événements de page vue pour lesquels le nom de la page est `Checkout`.

Les conteneurs Événement incluent des répartitions de page unique basées sur des valeurs pour :

- Produits
- Propriétés de liste
- Dimensions de liste
- Dimensions de marchandisage (dans le contexte des événements)



### Conteneurs B2B

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

Lorsque vous avez accès à [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md), des conteneurs supplémentaires à utiliser dans les segments sont disponibles. Pour plus d’informations sur l’utilisation de ces conteneurs supplémentaires, consultez les concepts et fonctionnalités [B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Conteneur de groupe logique

Groupe logique vous permet de regrouper des conditions dans un point de contrôle de segment séquentiel unique. Dans le cadre de la séquence, la logique définie dans le conteneur identifié comme [!UICONTROL Groupe logique] est évaluée après tout point de contrôle séquentiel précédent et avant tout point de contrôle séquentiel suivant. Voir [Groupe logique](seg-sequential-build.md#logic-group) pour plus d’informations.

### Imbrication de conteneurs

Lors de la création de conteneurs dans d’autres conteneurs, vous créez en fait un segment dans un segment. La logique suivante est appliquée aux conteneurs imbriqués :

1. Déterminez les données qui sont incluses à l’aide du conteneur le plus éloigné. Toutes les données qui ne correspondent pas à cette règle externe sont ignorées dans le rapport.
2. Appliquez la définition de segment imbriqué aux données restantes. La définition de segment imbriqué NE s’applique PAS aux données ignorées par la première définition.
3. Répétez l’opération jusqu’à ce que toutes les définitions de segment de conteneur imbriqué aient été calculées. Les données restantes sont ensuite incluses dans le résultat et utilisées pour le compte rendu des performances.

>[!NOTE]
>
>Lorsque vous imbriquez un segment dans un segment (par exemple, vous faites glisser un segment du panneau Composants sur votre définition de segment), un conteneur est créé avec une copie (et non une référence) de la définition de segment déplacée.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Création de segments](create-filters.md)
>[Créateur de segments](filter-builder.md)
>[Segments rapides ](quick-filters.md)
>[Segments séquentiels ](seg-sequential-build.md)
>[Gestion des segments ](manage-filters.md)
>
