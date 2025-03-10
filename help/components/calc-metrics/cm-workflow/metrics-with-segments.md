---
description: Le filtrage sur des mesures individuelles vous permet d’effectuer des comparaisons de mesures dans le même rapport.
title: Mesures filtrées
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Mesures filtrées

Dans le [créateur de mesures calculées](cm-build-metrics.md#definition-builder), vous pouvez appliquer des filtres au sein de votre définition de mesure. L’application de filtres s’avère utile si vous souhaitez utiliser des mesures pour un sous-ensemble de vos données dans votre analyse.

>[!NOTE]
>
>Les définitions de filtre sont mises à jour via le [ Créateur de filtres ](/help/components/filters/filter-builder.md). Si vous apportez une modification à un filtre, le filtre est automatiquement mis à jour partout où il est utilisé, y compris si le filtre fait partie d’une définition de mesure calculée.
>

Vous souhaitez comparer les mesures pour les Allemands qui interagissent avec votre marque par rapport aux personnes en dehors de l’Allemagne. Vous pouvez donc répondre à des questions telles que :

1. Combien de visiteurs allemands et internationaux visitent vos pages les plus [populaires](#popular-pages).
1. Combien de personnes allemandes par rapport aux personnes internationales au [total](#totals) ont interagi en ligne avec votre marque ce mois-ci ?
1. Quels sont les [pourcentages](#percentages) d&#39;Allemands et d&#39;internationaux qui ont visité vos pages populaires ?

Consultez les sections ci-dessous pour illustrer la manière dont les mesures filtrées peuvent vous aider à répondre à ces questions. Le cas échéant, il est fait référence à une documentation plus détaillée.

## Pages populaires

1. [Création d’une mesure calculée](cm-workflow.md) à partir d’un projet Workspace appelé `German people`.
1. Dans le [créateur de mesures calculées](cm-build-metrics.md), [créez un filtre](/help/components/filters/filter-builder.md) intitulé `Germany`, qui utilise le champ Pays du CRM des données de votre CRM pour déterminer la provenance d’une personne.

   >[!TIP]
   >
   >Dans le créateur de mesures calculées, vous pouvez créer un filtre directement à l’aide du panneau Composants .
   >   

   Votre filtre pourrait ressembler à ceci.

   ![Filtrer Allemagne](assets/filter-germany.png)

1. De retour dans le créateur de mesures calculées, utilisez le filtre pour mettre à jour la mesure calculée.

   ![Mesure calculée Allemagne](assets/calculated-metric-germany.png)

Répétez les étapes ci-dessus pour la version internationale de votre mesure calculée.

1. Créez une mesure calculée à partir de votre projet Workspace, intitulée `International people`.
1. Dans le créateur de Mesures calculées , créez un filtre, appelé `Not Germany`, qui utilise le champ Pays CRM de vos données CRM pour déterminer d’où vient une personne.

   Votre filtre doit ressembler à ceci.

   ![Filtrer Allemagne](assets/filter-not-germany.png)

1. De retour dans le créateur de mesures calculées, utilisez le filtre pour mettre à jour la mesure calculée.

   ![Mesure calculée Allemagne](assets/calculated-metric-notgermany.png)


1. Créez un projet dans Analysis Workspace, où vous affichez les pages visitées par des Allemands et des Internationaux.

   ![Visualisation du tableau à structure libre de Workspace montrant les Allemands par rapport aux Internationaux](assets/workspace-german-vs-international.png)


## Totaux

1. Créez deux nouveaux filtres basés sur le total général. Ouvrez chacun des filtres créés précédemment, renommez le filtre, définissez le **[!UICONTROL Type de mesure]** pour **[!UICONTROL Personnes]** sur **[!UICONTROL Total général]** puis utilisez **[!UICONTROL Enregistrer sous]** pour enregistrer le filtre sous un nouveau nom. Par exemple :

   ![Mesure totale pour l’Allemagne](assets/calculated-metric-germany-total.png)

1. Ajoutez une nouvelle visualisation de tableau à structure libre à votre projet Workspace, en affichant le nombre total de pages pour ce mois.

   Visualisation du tableau à structure libre de ![Workspace montrant le nombre total d’Allemands par rapport aux internationaux](assets/workspace-german-vs-international-totals.png)


## Pourcentages

1. Créez deux nouvelles mesures calculées qui calculent un pourcentage à partir des mesures calculées que vous avez créées précédemment.

   Visualisation du tableau à structure libre de ![Workspace indiquant le pourcentage de personnes totales en Allemagne par rapport à l’international](assets/calculated-metric-germany-total-percentage.png)


1. Mettez à jour votre projet Workspace.

   Visualisation du tableau à structure libre de ![Workspace montrant le nombre total d’Allemands par rapport aux internationaux](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utiliser une mesure calculée filtrée comme mesure sans implémentation](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]

