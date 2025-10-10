---
title: Vue d’ensemble de la segmentation
description: Découvrez à quoi servent les segments et comment créer un segment simple.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 100%

---


# Vue d’ensemble de la segmentation

Customer Journey Analytics vous permet de créer, de gérer, de partager et d’appliquer des segments d’audience puissants et ciblés à vos rapports. Les segments vous permettent d’identifier des sous-ensembles de personnes, de sessions ou d’événements en fonction de caractéristiques ou d’interactions. Les segments sont conçus comme des informations codifiées sur les audiences que vous pouvez créer en fonction de vos besoins spécifiques. Vous pouvez ensuite les vérifier, les modifier et les partager avec d’autres membres de votre équipe.

Les segments peuvent être basés sur des :

- attributs (type de navigateur, appareil, nombre de visites, pays, genre),
- interactions (campagnes, recherche par mots-clés, moteur de recherche),
- sorties et entrées (personnes provenant de Facebook, d’une page de destination définie, d’un domaine référent, d’un événement de géorepérage),
- variables personnalisées (champ de formulaire, catégories définies, ID de client ou cliente),
- et d’autres critères.

Consultez [Créer des segments](/help/components/segments/seg-create.md) pour connaître les différentes options disponibles pour créer des segments. Vous pouvez ensuite créer, modifier et enregistrer la définition d’un segment dans le [créateur de segments](seg-builder.md). Vous pouvez également créer des segments rapides à l’aide du [créateur de segments rapides](seg-quick.md). Vous pouvez également générer des segments à partir de visualisations dans Workspace, par exemple à l’aide de la visualisation [Abandons](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utilisez le [gestionnaire de segments](seg-manage.md) pour gérer les segments.

## Préparer les segments

Particulièrement en tant qu’administrateur ou administratrice, une préparation appropriée des segments améliore les chances que les segments soient utilisés. Tenez compte des points suivants lors de la préparation des segments :

- **Audience** : qui va utiliser vos segments ? Veillez à fournir une bonne description du segment afin que l’audience comprenne :
   - Quel est l’objet de ce segment ?

   - Quand dois-je utiliser ce segment ?

- **Portée** : quel [conteneur de segments](#segment-containers) représente le mieux les données que vous recherchez ? Utilisez le plus petit conteneur possible.

- **Composants** : décidez des composants à inclure dans la définition de segment et par rapport aux valeurs que les conditions doivent valider.

- **Processus** : envisagez un processus d’approbation pour vos segments. Il n’existe pas de workflow d’approbation dans Customer Journey Analytics, mais vous pouvez tout de même organiser un processus pour déterminer si vous approuvez ou non un segment.

- **Modularité** : définissez des segments en gardant à l’esprit la modularité. Les utilisateurs et utilisatrices de vos segments doivent pouvoir facilement [empiler des segments](seg-builder.md#stack-filters) pour créer de nouveaux segments puissants.


## Types de segments

Vous pouvez créer trois types de segments :

### Segments rapides

Les segments rapides vous permettent d’explorer facilement les données au sein d’un projet Workspace donné, sans avoir à créer un segment dans le [créateur de segments](/help/components/segments/seg-create.md). Définissez votre segment directement dans l’interface de Workspace. Consultez [Segments rapides](seg-quick.md) pour plus d’informations.

### Segments standard

Les segments standard vous permettent d’identifier des données (personnes, sessions, événements) en fonction d’une ou de plusieurs conditions. Si vous voulez appliquer plusieurs conditions, utilisez des opérateurs logiques tels que Et et Ou pour définir plus précisément le segment. Vous pouvez utiliser des conteneurs pour regrouper des conditions et créer des segments plus complexes. Consultez [Créateur de segments](seg-builder.md) pour plus d’informations.

### Segments séquentiels

>[!IMPORTANT]
>
>Vous devez disposer du package **Select** pour créer des segments séquentiels cross-canal. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

Les segments séquentiels vous permettent d’identifier des données (personnes, sessions, événements) en fonction de la navigation (pages vues de l’ensemble de votre site, interactions avec des scènes sur votre application mobile ou à l’aide d’un menu via un boîtier TV). Les segments séquentiels vous permettent par exemple d’identifier ce qu’aime une personne et ce qu’elle évite. Utilisez l’opérateur logique Alors pour définir un segment séquentiel. Consultez [Segments séquentiels](seg-sequential-build.md) pour plus d’informations.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Conteneurs de segments {#containers}

Les segments sont basés sur une hiérarchie au niveau de la personne, de la session et de l’événement à l’aide d’un modèle de conteneur imbriqué. Les conteneurs imbriqués vous permettent de définir des conditions au sein des conteneurs et entre eux.


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
>Pour les utilisateurs et utilisatrices d’Adobe Analytics :
> 
> - Dans Adobe Analytics, le conteneur **Personne** est connu sous le nom de conteneur **Visiteur ou visiteuse**.
> - Dans Adobe Analytics, le conteneur **Session** est connu sous le nom de conteneur **Visite**.
> - Dans Adobe Analytics, le conteneur **Événement** est connu sous le nom de conteneur **Accès**.
>

Un segment définit des conditions pour segmenter des personnes, des sessions ou des événements en fonction de conditions. Par exemple, les conditions de segmentation des personnes sont basées sur leurs caractéristiques et leurs comportements de navigation. Pour ventiler davantage les données, vous pouvez segmenter des sessions spécifiques, des événements de page vue, des interactions avec l’écran, des choix de menu sur un décodeur, etc. Vous pouvez également segmenter les attributs que vous avez ingérés à partir d’un système CRM ou de fidélité. Le [créateur de segments](/help/components/segments/seg-builder.md) fournit une interface simple permettant de créer ces sous-ensembles et d’appliquer des conditions sous la forme de conteneurs imbriqués, selon la hiérarchie Personne, Session ou Événement.

L’architecture de conteneur utilisée dans le [créateur de segments](/help/components/segments/seg-builder.md) définit le conteneur Personne comme étant le plus englobant. Ce conteneur contient les données principales spécifiques à la personne dans les sessions et événements tels que les pages vues, les écrans d’applications mobiles ou les écrans de menus sur un décodeur. Un conteneur imbriqué Session vous permet de définir des règles pour ventiler les données d’une personne en fonction des sessions. Le conteneur imbriqué Événement vous permet de ventiler les informations d’une personne en fonction des interactions individuelles. Chaque conteneur permet de créer un rapport de l’historique d’une personne, de ses interactions ventilées par sessions ou de ses ventilations par événements individuels.

### Conteneur Personne

Le conteneur Personne comprend chaque session et chaque événement pour les personnes qui remplissent les critères de la condition spécifiée dans le conteneur. Lorsque vous définissez un segment avec une condition simple telle que `Page Name equals Checkout`, le conteneur Personne inclut alors :

- toutes les personnes qui ont visité la page nommée `Checkout` ;
- toutes les sessions de ces personnes ;
- toutes les données d’événement de ces personnes.

En tant que conteneur défini de la manière la plus large, les rapports générés au niveau du conteneur Personne renvoient des événements et des sessions de toutes les personnes qui remplissent les critères du segment. Le conteneur Personne est le plus susceptible de changer selon les périodes définies.
Les conteneurs Personne peuvent inclure des valeurs basées sur l’historique global d’une personne :

- Jours avant le premier achat
- Page d’accès d’origine ou écran d’accueil de l’application mobile
- Domaines référents d’origine

### Conteneur Session

Le conteneur Session permet d’identifier les interactions de pages, les interactions d’application mobile, les campagnes ou les conversions d’une session spécifique. Le conteneur Session est le conteneur le plus souvent utilisé, car il capture les comportements de l’ensemble de la session une fois la règle respectée. Le conteneur Session vous permet également de définir les sessions que vous souhaitez inclure ou exclure de la création et de l’application d’un segment.  Lorsque vous définissez un segment avec une condition simple telle que `Page Name equals Checkout`, le conteneur Session inclut alors :

- toutes les sessions au cours desquelles une page nommée `Checkout` est visitée ;
- toutes les données d’événement de ces sessions.

Le conteneur Session peut vous aider à répondre aux questions suivantes :

- Combien de sessions ont impliqué des sources de données web et du centre d’appel ?
- Quelles pages ont contribué à une conversion réussie en vente ?

Les conteneurs Session incluent des valeurs basées sur l’occurrence par session :

- Type de session
- Page d’accès
- Fréquence des retours
- Mesures de participation
- Mesures allouées linéairement

Les vues de données dans Customer Journey Analytics vous permettent de déterminer la durée d’une session, mais aussi le moment où une nouvelle session doit être créée. Par exemple, vous pouvez définir une nouvelle session d’application mobile chaque fois qu’un utilisateur ou une utilisatrice lance votre application mobile. Voir [Paramètres de session](/help/data-views/session-settings.md) pour plus d’informations.

### Conteneur Événement

Le conteneur Événement définit les événements de page, d’application mobile ou autre que vous souhaitez inclure ou exclure d’un segment. Il s’agit du conteneur le plus restreint disponible. Il vous permet d’identifier des clics spécifiques, des pages vues et des clics sur un bouton dans une application mobile où une condition est vraie. Le conteneur Événement permet d’afficher un code de suivi unique ou d’isoler le comportement dans une zone particulière de votre application mobile. Vous pouvez également déterminer une valeur spécifique lorsqu’une action se produit, tel que le canal marketing lorsqu’une personne passe une commande. Lorsque vous définissez un segment avec une condition simple telle que `Page Name equals Checkout`, le conteneur Événement est résolu sur :

- Tous les événements de page vue pour lesquels le nom de la page est `Checkout`.

Les conteneurs Événement incluent des répartitions de page unique basées sur des valeurs pour :

- Produits
- Propriétés de liste
- Dimensions de liste
- Dimensions de merchandising (dans le contexte d’événements)



### Conteneurs B2B

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Lorsque vous avez accès à [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md), vous disposez de conteneurs supplémentaires à utiliser dans les segments. Pour plus d’informations sur l’utilisation de ces conteneurs supplémentaires, consultez les [concepts et fonctionnalités B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Conteneur Groupe logique

Les conteneurs Groupe logique servent à regrouper des conditions dans un point de contrôle de segment séquentiel unique. Dans le cadre de la séquence, la logique définie dans le conteneur identifié comme [!UICONTROL Groupe logique] est évaluée après tout point de contrôle séquentiel précédent et avant tout point de contrôle séquentiel suivant. Pour plus d’informations, consultez [Groupe logique](seg-sequential-build.md#logic-group).

### Imbriquer des conteneurs

Lorsque vous créez des conteneurs dans d’autres conteneurs, vous créez un segment dans un segment. La logique suivante s’applique aux conteneurs imbriqués :

1. Déterminez les données qui sont incluses à l’aide du conteneur le plus éloigné. Les données qui ne correspondent pas à cette règle externe sont exclues du rapport.
2. Appliquez la définition de segment imbriqué aux données restantes. La définition de segment imbriqué NE s’applique PAS aux données exclues par la première définition.
3. Répétez l’opération jusqu’à ce que toutes les définitions de segment de conteneur imbriqué aient été calculées. Les données restantes sont ensuite incluses dans le résultat et utilisées pour le reporting.

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
>[Créer des segments](seg-create.md)
>>[Créateur de segments](seg-builder.md)
>>[Segments rapides](seg-quick.md)
>>[Segments séquentiels](seg-sequential-build.md)
>>[Gérer des segments](seg-manage.md)
