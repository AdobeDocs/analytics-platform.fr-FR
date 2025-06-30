---
description: Découvrez les différentes possibilités de téléchargement de données à partir de votre projet Analysis Workspace.
title: Téléchargement De Projets Et De Données Analysis Workspace
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 25%

---

# Téléchargement de projets et de données

Vous pouvez télécharger des projets et des données Analysis Workspace sur votre appareil local. Ce téléchargement peut être un fichier de données copiées, un fichier CSV (valeurs séparées par des virgules) ou un document PDF (format de document portable).

* Sélectionnez l’option PDF si vous souhaitez que les visualisations soient incluses dans le fichier téléchargé.
* Sélectionnez les options CSV et données copiées si vous avez simplement besoin de données en texte brut.

D’autres méthodes d’exportation des données Customer Journey Analytics sont décrites dans la [présentation de l’exportation](/help/analysis-workspace/export/export-project-overview.md).

## Télécharger au format CSV ou PDF {#download-project}

![Menu déroulant Projet avec les options Télécharger au format CSV et Télécharger au format PDF mises en surbrillance.](assets/download-project.png)

Tenez compte des points suivants lorsque vous téléchargez un projet en tant que PDF :

* Le téléchargement peut prendre plusieurs minutes, car le projet est réexécuté sur les serveurs Adobe pour effectuer le rendu au format PDF. Ne quittez pas le projet tant qu’il n’a pas été téléchargé dans votre navigateur.  Vous pouvez continuer à apporter des modifications au projet pendant le rendu du téléchargement. Si le rendu d’un PDF dure plus de 5 minutes, vous êtes invité à [envoyer le PDF par e-mail](../curate-share/send-schedule-files.md) à la place.
* Les téléchargements sont générés en une seule page sans pagination.
* Les PDF contiennent ce qui est visible dans la page du navigateur dans Analysis Workspace. Vous devez dimensionner automatiquement les visualisations et les panneaux aux dimensions personnalisées pour éviter la troncation du contenu. Sélectionnez ![Redimensionner](/help/assets/icons/Resize.svg) pour redimensionner automatiquement un panneau ou une visualisation aux dimensions personnalisées.
* [Hyperliens](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) dans les tableaux à structure libre sous forme de liens hypertexte dans le PDF téléchargé.



Pour télécharger un projet sous la forme d’un fichier PDF :

1. Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Télécharger PDF]**.
Une barre verte avec le message ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Votre téléchargement a été demandé. Veuillez patienter.]** s’affiche.

1. Dès que votre téléchargement est prêt, une barre verte contenant le message ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *Nom du projet *PDF est prête.]**&#x200B;apparaît.
Sélectionnez&#x200B;**[!UICONTROL Télécharger]**&#x200B;pour télécharger le PDF. La manière exacte dont le PDF est présenté ou téléchargé dépend de la configuration de votre navigateur pour gérer les documents PDF.


Pour télécharger un projet sous la forme d’un fichier CSV :

* Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Télécharger CSV]**. Le projet est directement téléchargé vers le dossier de téléchargement configuré dans le cadre de la configuration de votre navigateur. Le nom du fichier se compose de *nom du projet* - *nom de la suite de rapports* - *date*, par exemple `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`.

## Copier dans le presse-papiers {#copy-data}

L&#39;option **[!UICONTROL Copier dans le presse-papiers]** du menu contextuel permet de copier rapidement des données d&#39;Analysis Workspace et de les coller dans un outil tiers.

* Si vous souhaitez copier les données affichées dans le tableau, sélectionnez l’en-tête du tableau, puis sélectionnez **Copier les données dans le presse-papiers** dans le menu contextuel.
* Si vous souhaitez copier un sous-ensemble des données, effectuez une sélection dans le tableau et sélectionnez **Copier la sélection dans le presse-papiers** dans le menu contextuel.

>[!TIP]
>
>Vous pouvez utiliser la touche de raccourci **_cmd + c_** (macOS) ou **_ctrl + c_** (Windows) pour copier votre sélection dans le presse-papiers. Utilisez ensuite **_cmd + v_** (macOS) ou **_ctrl + v_** (Windows) pour coller les données.


![Option Copier la sélection dans le presse-papiers. ](assets/copy-clipboard.png){zoomable="yes"}

## Téléchargement au format CSV {#download-data}

Les options Télécharger au format CSV du menu contextuel vous permettent de télécharger un tableau de données ou la source de données de toute visualisation au format CSV.

Pour ce faire, procédez comme suit :

* Dans l’en-tête d’un tableau ou d’une visualisation, sélectionnez **[!UICONTROL Télécharger les données au format CSV]** dans le menu contextuel. Cette option télécharge les données affichées dans le tableau ou la source de données sous-jacente pour une visualisation au format CSV.

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* Dans un tableau, sélectionnez **[!UICONTROL Télécharger la sélection au format CSV]** dans le menu contextuel. Seule la sélection est téléchargée avec cette option, par opposition au tableau complet affiché.

![Option Télécharger les données au format CSV.](assets/download-data-as-csv.png)

## Télécharger les éléments au format CSV {#download-items}

Si vous souhaitez analyser plus de 400 lignes de données visibles dans un tableau, sélectionnez **Télécharger les éléments au format CSV (_nom du Dimension_)** dans le menu contextuel de l’en-tête du tableau ou de n’importe quelle ligne. Cette option exporte jusquʼà 50 000 éléments de dimension (selon le tri du tableau) pour la dimension sélectionnée, avec des options de tri et des filtres appliqués. Si vous sélectionnez cette option dans la partie supérieure du tableau, la première dimension du tableau est exportée.

![Option Télécharger les éléments au format CSV (page).](assets/download-items-as-csv.png)

Aucune limite n’est appliquée dans le tableau à structure libre. Pour garantir des performances optimales, il est recommandé d’utiliser cette option dans les tableaux de moins de 20 colonnes.

>[!TIP]
>
> Si votre dimension dépasse 50 000 éléments, téléchargez le fichier avec différentes mesures de tri appliquées ou appliquez un segment. Par exemple, triez les visites par ordre descendant dans un téléchargement, puis par ordre ascendant dans un second téléchargement. Cette astuce peut vous aider à récupérer des éléments à traîne longue.

Vous pouvez réaliser plusieurs tâches au sein du projet et même naviguer vers un nouveau projet Workspace dans le même onglet pendant le téléchargement est en cours. Le téléchargement est interrompu si vous ouvrez un nouvel onglet du navigateur. Le téléchargement est annulé si vous quittez complètement Workspace ou si vous fermez lʼonglet du navigateur.


### Fichier des éléments téléchargés {#items-file}

Les fonctionnalités suivantes d’un tableau à structure libre sont appliquées au fichier téléchargé :

* Tous les segments du panneau sont appliqués en tant que filtres.
* Les répartitions **au-dessus** de la dimension sélectionnée dans le tableau sont appliquées en tant que filtres au-dessus de chaque colonne.
* Les répartitions **en dessous** de la dimension sélectionnée dans le tableau sont supprimées.

![Fichier .csv téléchargé ouvert dans Excel.](assets/download-items-file.png)

### Notifications de téléchargement {#notifications}

Les notifications suivantes s’affichent au fur et à mesure des téléchargements du fichier :

* Un bleu **[!UICONTROL _Nom de la table _-_Dimension _.csv a été demandé._x _% terminé]**&#x200B;indiquant la progression. Pour annuler le téléchargement à tout moment, sélectionnez **[!UICONTROL Annuler le téléchargement]**. Sélectionnez ![CrossSize100](/help/assets/icons/CrossSize100.svg) si vous souhaitez fermer le message, ce qui n’annule pas le téléchargement.
* Un **[!UICONTROL _Nom de la table _vert -_Dimension _.csv a été téléchargé]**&#x200B;notification d’achèvement une fois le téléchargement du fichier terminé. Le fichier est téléchargé dans le dossier des téléchargements configuré pour votre navigateur.

Si vous demandez plusieurs téléchargements à la fois, vous recevez une notification indiquant que chaque téléchargement supplémentaire est mis en file d’attente jusqu’à ce que le téléchargement précédent soit terminé.


## Télécharger des données sensibles {#sensitive}

Imaginez une [politique de gouvernance des données](/help/data-views/data-governance.md) qui empêche le téléchargement des données. Cette politique est activée dans la vue de données sur laquelle vous établissez des rapports. Par conséquent, tout téléchargement (par exemple lorsque vous envoyez un e-mail ou partagez des fichiers PDF) de projets hache les champs de données libellés comme sensibles. Vous pouvez toujours effectuer une analyse sur ces champs dans Analysis Workspace. Si vous tentez d’envoyer un e-mail ou de partager un projet, les champs de données sensibles apparaissent comme vides dans le fichier PDF ou CSV.

Si les champs de données libellés comme sensibles sont inclus dans la vue de données, l’option permettant de sélectionner et de copier les données de l’écran est limitée pour toutes les données de la vue de données.

## Questions fréquentes {#faq}

| Question | Réponse |
| --- | --- |
| Pourquoi mon PDF téléchargé ne comprend-il qu’une seule page ? | La fonctionnalité [Télécharger PDF](#download-as-csv-or-pdf) ne pagine pas les PDF téléchargés. |
| Puis-je exporter plus de 50 000 éléments avec l’option **[!UICONTROL Télécharger les éléments au format CSV]** ? | Bien que chaque téléchargement puisse contenir jusquʼà 50 000 éléments de dimension, vous pouvez modifier le tri de votre tableau pour récupérer des éléments à traîne longue ou appliquer un filtre pour télécharger des éléments plus spécifiques. |
| À quoi sert l’option **[!UICONTROL Copier la visualisation]** ? | Contrairement à [!UICONTROL **Copier les données dans le presse-papiers**] ou [!UICONTROL **Copier la sélection dans le presse-papiers**], l’option de menu contextuel **[!UICONTROL Copier la visualisation]** n’est pas une option d’exportation. Cette option vous permet de [copier une visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) ou [copier un panneau](/help/analysis-workspace/c-panels/panels.md#context-menu) d’un emplacement de Workspace à un autre. Par exemple, d’un panneau à un autre dans le même projet, ou d’un projet à un autre. |
