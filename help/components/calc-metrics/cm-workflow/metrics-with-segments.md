---
description: Découvrez comment segmenter des mesures individuelles, ce qui vous permet d’effectuer des comparaisons de mesures dans la même visualisation.
title: Mesures Segmentées
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
TQID: https://experienceleague.adobe.com/dOOOOGytHT-5IMC9LNcNlBKLufs9PUkvjBoAgw38bEI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 1%

---

# Mesures segmentées

Dans le [créateur de mesures calculées](cm-build-metrics.md#definition-builder), vous pouvez appliquer des segments dans votre définition de mesure. L’application de segments s’avère utile si vous souhaitez utiliser des mesures pour un sous-ensemble de vos données dans votre analyse.

>[!NOTE]
>
>Les définitions de segment sont mises à jour via le [créateur de segments](/help/components/segments/seg-builder.md). Si vous apportez une modification à un segment, le segment est automatiquement mis à jour partout où il est utilisé, y compris si le segment fait partie d’une définition de mesure calculée.
>

Vous souhaitez comparer les mesures pour les Allemands qui interagissent avec votre marque par rapport aux personnes en dehors de l’Allemagne. Vous pouvez donc répondre à des questions telles que :

1. Combien de visiteurs allemands et internationaux visitent vos pages les plus [populaires](#popular-pages).
1. Combien de personnes allemandes par rapport aux personnes internationales au [total](#totals) ont interagi en ligne avec votre marque ce mois-ci ?
1. Quels sont les [pourcentages](#percentages) d&#39;Allemands et d&#39;internationaux qui ont visité vos pages populaires ?

Consultez les sections ci-dessous pour illustrer la manière dont les mesures segmentées peuvent vous aider à répondre à ces questions. Le cas échéant, il est fait référence à une documentation plus détaillée.

## Pages populaires

1. [Création d’une mesure calculée](cm-workflow.md) à partir d’un projet Workspace appelé `German people`.
1. Dans le [créateur de mesures calculées](cm-build-metrics.md), [créez un segment](/help/components/segments/seg-builder.md) intitulé `Germany`, qui utilise le champ Pays CRM des données de votre CRM pour déterminer d’où vient une personne.

   >[!TIP]
   >
   >Dans le créateur de mesures calculées, vous pouvez créer un segment directement à l’aide du panneau Composants .
   >   

   Votre segment pourrait ressembler à ceci :

   ![Segment Allemagne](assets/filter-germany.png)

1. De retour dans le créateur de mesures calculées, utilisez le segment pour mettre à jour la mesure calculée.

   ![Mesure calculée Allemagne](assets/calculated-metric-germany.png)

Répétez les étapes ci-dessus pour la version internationale de votre mesure calculée.

1. Créez une mesure calculée à partir de votre projet Workspace, intitulée `International people`.
1. Dans le créateur de mesures calculées , créez un segment, appelé `Not Germany`, qui utilise le champ Pays CRM de vos données CRM pour déterminer la provenance d’une personne.

   Votre segment doit ressembler à ceci :

   ![Segment Allemagne](assets/filter-not-germany.png)

1. De retour dans le créateur de mesures calculées, utilisez le segment pour mettre à jour la mesure calculée.

   ![Mesure calculée Allemagne](assets/calculated-metric-notgermany.png)


1. Créez un projet dans Analysis Workspace, où vous affichez les pages visitées par des Allemands et des Internationaux.

   ![Visualisation du tableau à structure libre de Workspace montrant les Allemands par rapport aux Internationaux](assets/workspace-german-vs-international.png)


## Totaux

1. Créez deux nouvelles mesures calculées basées sur le total général. Ouvrez chacun des segments créés précédemment, renommez le segment, définissez le **[!UICONTROL Type de mesure]** pour **[!UICONTROL Personnes]** sur **[!UICONTROL Total général]** puis utilisez **[!UICONTROL Enregistrer sous]** pour enregistrer le segment en utilisant le nouveau nom. Par exemple :

   ![Mesure totale pour l’Allemagne](assets/calculated-metric-germany-total.png)

1. Ajoutez une nouvelle visualisation de tableau à structure libre à votre projet Workspace, en affichant le nombre total de pages pour ce mois.

   Visualisation du tableau à structure libre de ![Workspace montrant le nombre total d’Allemands par rapport aux internationaux](assets/workspace-german-vs-international-totals.png)


## Pourcentages

1. Créez deux nouvelles mesures calculées qui calculent un pourcentage à partir des mesures calculées que vous avez créées précédemment.

   Visualisation du tableau à structure libre de ![Workspace indiquant le pourcentage de personnes totales en Allemagne par rapport à l’international](assets/calculated-metric-germany-total-percentage.png)


1. Mettez à jour votre projet Workspace.

   Visualisation du tableau à structure libre de ![Workspace montrant le nombre total d’Allemands par rapport aux internationaux](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utiliser une mesure calculée segmentée comme mesure sans implémentation](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]

