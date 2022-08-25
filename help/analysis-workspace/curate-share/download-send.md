---
description: Vous pouvez télécharger des données à partir dʼAnalysis Workspace aux formats PDF et CSV, ou en les copiant.
title: Téléchargement de fichiers PDF ou CSV
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Téléchargement de fichiers PDF ou CSV

Il existe plusieurs façons dʼexporter des données depuis Analysis Workspace, en fonction du jeu de données que vous souhaitez analyser en dehors de lʼoutil et des personnes qui doivent recevoir ces informations. Les données exportées peuvent prendre la forme de données copiées, de fichiers CSV ou PDF. Un PDF est généralement préféré si vous souhaitez inclure des visualisations dans le fichier, tandis quʼun fichier CSV (ou des données copiées) est préféré si vous souhaitez simplement des données en texte brut.

## Téléchargement du projet au format CSV ou PDF {#download-project}

Vous pouvez télécharger un projet complet en accédant à **[!UICONTROL Projet > Télécharger au format PDF (ou au format CSV)]**. Le fichier téléchargé contient tous les tableaux et visualisations affichés (visibles) dans le projet. Un PDF est généralement préféré si vous souhaitez inclure des visualisations dans le fichier, tandis quʼun fichier CSV est préféré si vous souhaitez simplement des données en texte brut.

![](assets/download-project.png)

Pour les téléchargements de projet, gardez à lʼesprit :

* Le projet peut être enregistré ou non lorsque vous demandez un téléchargement de projet. Cependant, seuls les projets enregistrés peuvent être [planifiés](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html?lang=fr).
* Lʼexportation des fichiers PDF téléchargés dans le navigateur peut prendre plusieurs minutes, car le projet est réexécuté sur les serveurs dʼAdobe avant dʼêtre rendu au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’a pas été téléchargé dans votre navigateur. Cependant, vous pouvez continuer à apporter des modifications au projet pendant que vous patientez. Si le rendu dʼun fichier PDF prend plus de 5 minutes, vous serez invité à l’envoyer par e-mail.
* Les téléchargements PDF sont générés en une seule page sans pagination.
* Lorsquʼun projet est rendu au format PDF, nous rendons ce qui se trouve sur la page. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.

## Copier les données dans le presse-papiers (raccourci clavier : Ctrl+C) {#copy-data}

Lʼoption de clic droit **[!UICONTROL Copier dans le presse-papiers]** permet de copier rapidement des données de Workspace et de les coller ailleurs.

* Si vous souhaitez copier le tableau affiché, cliquez avec le bouton droit sur lʼen-tête du tableau et choisissez **Copier les données dans le presse-papiers**.
* Si vous souhaitez copier un sous-ensemble de données, effectuez une sélection dans le tableau et cliquez avec le bouton droit > **Copier la sélection dans le presse-papiers**.

De plus, la touche dʼaccès rapide `Ctrl+C` copie votre sélection dans le presse-papiers. Une fois copié, vous pouvez accéder à un autre outil et coller les informations (ou cliquer sur `Ctrl+V`).

![](assets/copy-selection.png)

## Télécharger les données au format CSV {#download-data}

Lʼoption de clic droit **[!UICONTROL Télécharger les données au format CSV]** vous permet de télécharger un tableau de données ou la source de données de nʼimporte quelle visualisation au format CSV.

* Dans lʼen-tête dʼun tableau ou dʼune visualisation, cliquez avec le bouton droit sur **[!UICONTROL Télécharger les données au format CSV]**. Cette option télécharge les données affichées dans le tableau ou la source de données sous-jacente pour une visualisation au format CSV. Remarque : la visualisation Carte ne prend pas en charge cette option.
* Si une sélection est effectuée dans le tableau, lʼoption indique **[!UICONTROL Télécharger la sélection au format CSV]**. Seule la sélection est téléchargée avec cette option, par opposition au tableau complet affiché.

![](assets/download-data-viz.png)

## Télécharger les éléments au format CSV {#download-items}

Si vous souhaitez analyser plus de 400 lignes de données visibles dans un tableau, cliquez avec le bouton droit sur lʼen-tête du tableau ou sur une ligne et sélectionnez **Télécharger les éléments au format CSV (nom de la dimension)**. Cette option exporte jusquʼà 50 000 éléments de dimension (selon le tri du tableau) pour la dimension sélectionnée, avec des filtres appliqués. Si vous choisissez cette option dans la partie supérieure du tableau, la première dimension du tableau est exportée. Bien quʼaucune limite ne soit appliquée dans le tableau à structure libre, il est recommandé dʼutiliser lʼoption Télécharger les éléments dans des tableaux de moins de 20 colonnes afin dʼassurer des performances optimales.

>[!TIP]
>
> Si votre dimension dépasse 50 000 éléments, téléchargez le fichier avec différentes mesures de tri appliquées ou appliquez un filtre. Par exemple, triez les visites par ordre descendant dans un téléchargement, puis par ordre ascendant dans un second téléchargement. Cette astuce peut vous aider à récupérer des éléments à traîne longue.

Vous pouvez réaliser plusieurs tâches au sein du projet et même naviguer vers un nouveau projet Workspace dans le même onglet pendant le téléchargement est en cours. Le téléchargement est interrompu si vous ouvrez un nouvel onglet du navigateur. Le téléchargement est annulé si vous quittez complètement Workspace ou fermez lʼonglet du navigateur.

![](assets/download-items.png)

### Fichier des éléments téléchargés {#items-file}

Les fonctionnalités du tableau seront appliquées au fichier téléchargé comme suit :

* Tous les filtres du panneau sont appliqués en tant que filtres.
* Les répartitions **au-dessus** de la dimension sélectionnée dans le tableau sont appliquées en tant que filtres au-dessus de chaque colonne.
* Les répartitions **en dessous** de la dimension sélectionnée dans le tableau sont supprimées.

Dans lʼexemple ci-dessus, les éléments de page sont téléchargés avec le filtre de panneau (nouveaux visiteurs/clients) et les composants (canal marketing = e-mail) sont appliqués en tant que filtres. Quant aux composants ci-dessous (type dʼéquipement mobile), ils sont supprimés du fichier CSV téléchargé.

![](assets/downloaded-file.png)

### Notifications de téléchargement {#notifications}

Au fur et à mesure du téléchargement du fichier, une notification dʼinformation sʼaffiche et indique la progression du téléchargement. Vous pouvez à tout moment annuler le téléchargement en cliquant sur **[!UICONTROL Annuler le téléchargement]**. La fermeture du toast **nʼannulera pas** le téléchargement.

Une fois le fichier terminé, une notification dʼachèvement sʼaffiche et le fichier est téléchargé dans votre navigateur.

Si vous demandez plus dʼun téléchargement à la fois, vous recevrez une notification indiquant que chaque téléchargement supplémentaire sera mis en attente jusquʼà ce que le téléchargement précédent se termine.

![](assets/toast.png)

## Télécharger des données sensibles {#sensitive}

Si la [politique en matière de gouvernance](/help/data-views/data-governance.md) **[!UICONTROL Forcer le téléchargement]** est activée dans la vue de données sur laquelle vous établissez des rapports, tout téléchargement (tel que l’envoi par e-mail ou le partage de fichiers PDF) de projets Workspace hachera les champs de données libellés comme sensibles. Vous pouvez toujours effectuer une analyse sur ces champs dans Workspace, mais si vous tentez d’envoyer un e-mail ou de partager un projet, les champs bloqués apparaîtront comme vides dans le fichier PDF ou CSV.

## FAQ {#faq}

| Question | Réponse |
| --- | --- |
| Pourquoi mon PDF téléchargé ne comporte-t-il quʼune seule page ? | Pour lʼinstant, Workspace ne pagine pas les PDF téléchargés. |
| Puis-je exporter plus de 50 000 éléments avec lʼoption « Télécharger les éléments au format CSV » ? | Bien que chaque téléchargement puisse contenir jusquʼà 50 000 éléments de dimension, vous pouvez modifier le tri de votre tableau pour récupérer des éléments à traîne longue ou appliquer un filtre pour télécharger des éléments plus spécifiques. |
| À quoi sert l’option **[!UICONTROL Copier la visualisation]** ? | **[!UICONTROL Copier la visualisation]** nʼest pas une option dʼexportation. Cela vous permet de copier une visualisation ou un panneau dʼun emplacement Workspace à un autre. Par exemple, dʼun panneau à un autre au sein du même projet, ou dʼun projet à un autre. [Vidéo sur la liaison interne](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=fr) |
