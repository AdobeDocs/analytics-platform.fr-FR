---
description: Vous pouvez télécharger des données à partir dʼAnalysis Workspace aux formats PDF et CSV, ou en les copiant.
title: Téléchargement de données de Customer Journey Analytics
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: 24e9e4151360597b099a7985a4566b3ca7bfff00
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 58%

---

# Téléchargement de données de Customer Journey Analytics

Vous pouvez télécharger des données de Customer Journey Analytics sur votre poste de travail personnel. Il peut s’agir de données copiées, de fichiers CSV ou de PDF. Il est généralement préférable d’utiliser un PDF si vous souhaitez inclure des visualisations dans le fichier téléchargé. Il est préférable d’utiliser le format CSV et les données copiées si vous souhaitez simplement des données en texte brut.

D’autres méthodes d’exportation de données de Customer Journey Analytics sont également disponibles, comme décrit dans la section [Présentation de l’exportation](/help/analysis-workspace/export/export-project-overview.md).

## Téléchargement au format CSV ou PDF {#download-project}

1. Effectuez l’une des opérations suivantes, selon le format dans lequel vous souhaitez que le téléchargement se trouve :

   * **PDF :** Sélectionner **[!UICONTROL Projet]** > **[!UICONTROL PDF de téléchargement]**.

     Choisissez cette option si vous souhaitez que le fichier téléchargé contienne tous les tableaux et visualisations affichés (visibles) dans le projet.

   * **CSV :** Sélectionner **[!UICONTROL Projet]** > **[!UICONTROL Téléchargement de fichier CSV]**.

     Choisissez cette option si vous souhaitez que le fichier téléchargé soit en texte brut.

   ![](assets/download-project.png)

1. (Conditionnel) Si vous choisissez de télécharger un PDF, un message s’affiche une fois le projet prêt à être téléchargé. Sélectionnez [!UICONTROL **Télécharger**].

Pour les téléchargements de projet, gardez à lʼesprit :

* Le projet peut être enregistré ou non lorsque vous demandez un téléchargement de projet. Cependant, seuls les projets enregistrés peuvent être [planifiés](/help/analysis-workspace/export/t-schedule-report.md).
* Lʼexportation des fichiers PDF téléchargés dans le navigateur peut prendre plusieurs minutes, car le projet est réexécuté sur les serveurs dʼAdobe avant dʼêtre rendu au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’a pas été téléchargé dans votre navigateur. Cependant, vous pouvez continuer à apporter des modifications au projet pendant que vous patientez. Si le rendu dʼun fichier PDF prend plus de 5 minutes, vous serez invité à l’envoyer par e-mail.
* Les téléchargements PDF sont générés en une seule page sans pagination.
* Lorsquʼun projet est rendu au format PDF, nous rendons ce qui se trouve sur la page. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.

## Copier dans le Presse-papiers (touche rapide : Ctrl+C) {#copy-data}

Option de clic droit **[!UICONTROL Copier dans le presse-papiers]** vous permet de copier rapidement des données de Customer Journey Analytics à partir de Workspace et de les coller dans un outil tiers.

* Si vous souhaitez copier le tableau affiché, cliquez avec le bouton droit sur l’en-tête du tableau et choisissez **Copie de données dans le presse-papiers**.
* Si vous souhaitez copier un sous-ensemble de données, effectuez une sélection dans le tableau et cliquez avec le bouton droit > **Copier la sélection dans le presse-papiers**.

>[!TIP]
>
>Vous pouvez utiliser la touche de raccourci `Ctrl+C` pour copier votre sélection dans le Presse-papiers, puis utilisez `Ctrl+V` pour le coller dans un outil tiers.


![](assets/copy-selection.png)

## Téléchargement au format CSV {#download-data}

Option de clic droit **[!UICONTROL Téléchargement de données au format CSV]** vous permet de télécharger un tableau de données de Customer Journey Analytics ou la source de données d’une visualisation au format CSV.

* Dans l’en-tête d’un tableau ou d’une visualisation, cliquez avec le bouton droit de la souris et choisissez **[!UICONTROL Téléchargement de données au format CSV]**. Cela télécharge les données de Customer Journey Analytics affichées dans le tableau ou la source de données sous-jacente pour une visualisation au format CSV.

  >[!NOTE]
  >
  >  Remarque : la visualisation Carte ne prend pas en charge cette option.


* Dans un tableau, cliquez avec le bouton droit de la souris et choisissez **[!UICONTROL Téléchargement de la sélection au format CSV]**. Seule la sélection est téléchargée avec cette option, par opposition au tableau complet affiché.

![](assets/download-data-viz.png)

## Télécharger les éléments au format CSV {#download-items}

Si vous souhaitez analyser plus de 400 lignes de données visibles dans un tableau, cliquez avec le bouton droit de la souris sur l’en-tête du tableau ou d’une ligne, puis sélectionnez **Téléchargement des éléments au format CSV (_Nom de la Dimension_)**. Cette option exporte jusqu’à 50 000 éléments de dimension (selon le tri du tableau) pour la dimension sélectionnée, avec les options de tri et les filtres appliqués. Si vous choisissez cette option dans la partie supérieure du tableau, la première dimension du tableau est exportée. Bien quʼaucune limite ne soit appliquée dans le tableau à structure libre, il est recommandé dʼutiliser lʼoption Télécharger les éléments dans des tableaux de moins de 20 colonnes afin dʼassurer des performances optimales.

>[!TIP]
>
> Si votre dimension dépasse 50 000 éléments, téléchargez le fichier avec différentes mesures de tri appliquées ou appliquez un filtre. Par exemple, triez les visites par ordre descendant dans un téléchargement, puis par ordre ascendant dans un second téléchargement. Cette astuce peut vous aider à récupérer des éléments à traîne longue.

Vous pouvez réaliser plusieurs tâches au sein du projet et même naviguer vers un nouveau projet Workspace dans le même onglet pendant le téléchargement est en cours. Le téléchargement s’interrompt si vous ouvrez un nouvel onglet du navigateur. Le téléchargement est annulé si vous quittez complètement Workspace ou fermez l’onglet du navigateur.

![](assets/download-items.png)

### Fichier des éléments téléchargés {#items-file}

Les fonctionnalités du tableau seront appliquées au fichier téléchargé comme suit :

* Tous les filtres du panneau sont appliqués en tant que filtres.
* Les répartitions **au-dessus** de la dimension sélectionnée dans le tableau sont appliquées en tant que filtres au-dessus de chaque colonne.
* Les répartitions **en dessous** de la dimension sélectionnée dans le tableau sont supprimées.

Dans lʼexemple ci-dessus, les éléments de page sont téléchargés avec le filtre de panneau (nouveaux visiteurs/clients) et les composants (canal marketing = e-mail) sont appliqués en tant que filtres. Quant aux composants ci-dessous (type dʼappareil mobile), ils sont supprimés du fichier CSV téléchargé.

![](assets/downloaded-file.png)

### Notifications de téléchargement {#notifications}

Au fur et à mesure du téléchargement du fichier, une notification dʼinformation sʼaffiche et indique la progression du téléchargement. Vous pouvez à tout moment annuler le téléchargement en cliquant sur **[!UICONTROL Annuler le téléchargement]**. La fermeture du toast **nʼannulera pas** le téléchargement.

Une fois le fichier terminé, une notification dʼachèvement sʼaffiche et le fichier est téléchargé dans votre navigateur.

Si vous demandez plus dʼun téléchargement à la fois, vous recevrez une notification indiquant que chaque téléchargement supplémentaire sera mis en attente jusquʼà ce que le téléchargement précédent se termine.

![](assets/toast.png)

## Télécharger des données sensibles {#sensitive}

Si la variable **[!UICONTROL Application du téléchargement]** [politique de gouvernance des données](/help/data-views/data-governance.md) est activé dans la vue de données sur laquelle vous créez des rapports, tout téléchargement (par exemple, envoi d’un courrier électronique ou partage de fichiers de PDF) de projets Workspace hachera les champs de données considérés comme sensibles. Vous pouvez toujours effectuer une analyse sur ces champs dans Workspace, mais si vous tentez d’envoyer un e-mail ou de partager un projet, les champs bloqués apparaîtront comme vides dans le fichier PDF ou CSV.

## FAQ {#faq}

| Question | Réponse |
| --- | --- |
| Pourquoi mon PDF téléchargé ne comporte-t-il quʼune seule page ? | Pour lʼinstant, Workspace ne pagine pas les PDF téléchargés. |
| Puis-je exporter plus de 50 000 éléments avec l’option &quot;Télécharger les éléments au format CSV&quot; ? | Bien que chaque téléchargement puisse contenir jusquʼà 50 000 éléments de dimension, vous pouvez modifier le tri de votre tableau pour récupérer des éléments à traîne longue ou appliquer un filtre pour télécharger des éléments plus spécifiques. |
| À quoi sert l’option **[!UICONTROL Copier la visualisation]** ? | Contrairement à [!UICONTROL **Copie de données dans le presse-papiers**] ou [!UICONTROL **Copier la sélection dans le presse-papiers**], la variable **[!UICONTROL Copier la visualisation]** l’option clic droit n’est pas une option d’exportation. Cela vous permet de copier une visualisation ou un panneau dʼun emplacement Workspace à un autre. Par exemple, dʼun panneau à un autre au sein du même projet, ou dʼun projet à un autre. [Vidéo sur la liaison interne](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=fr) |