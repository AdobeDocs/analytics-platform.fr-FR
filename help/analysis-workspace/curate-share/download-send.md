---
description: Vous pouvez télécharger des données à partir d’Analysis Workspace en les copiant, ou aux formats PDF et CSV.
title: Téléchargement de fichiers PDF ou CSV
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 12%

---


# Téléchargement de fichiers PDF ou CSV

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez exporter des données à partir d’Analysis Workspace de plusieurs manières différentes, en fonction de l’ensemble de données que vous souhaitez analyser en dehors de l’outil et de la personne qui doit recevoir les informations. Les données exportées peuvent prendre la forme de données copiées, de fichiers CSV ou PDF. Il est généralement préférable d’utiliser un fichier PDF si vous souhaitez inclure des visualisations dans le fichier, tandis qu’un fichier CSV (ou des données copiées) est préférable si vous souhaitez simplement des données en texte brut.

## Télécharger le projet au format CSV ou PDF {#download-project}

Vous pouvez télécharger un projet complet en accédant à **[!UICONTROL Projet > Télécharger au format PDF (ou au format CSV)]**. Le fichier téléchargé contient tous les tableaux et visualisations affichés (visibles) dans le projet. Il est généralement préférable d’utiliser un fichier PDF si vous souhaitez inclure des visualisations dans le fichier, tandis qu’un fichier CSV est préférable si vous souhaitez simplement des données en texte brut.

![](assets/download-project.png)

Pour les téléchargements de projet, gardez à l’esprit :

* Le projet peut être enregistré ou non lorsque vous demandez un téléchargement de projet. Cependant, seuls les projets enregistrés peuvent être [planifiés](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* L’exportation des fichiers PDF téléchargés dans le navigateur peut prendre plusieurs minutes, car le projet est réexécuté sur les serveurs d’Adobe avant d’être rendu au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’a pas été téléchargé dans votre navigateur. Cependant, vous pouvez continuer à apporter des modifications au projet pendant que vous patientez. Si le rendu d’un fichier PDF prend plus de 5 minutes, vous êtes invité à le faire parvenir par courrier électronique.
* Les téléchargements PDF sont générés en une seule page sans pagination.
* Lorsqu’un projet est rendu au format PDF, nous rendons ce qui se trouve sur la page. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.

## Copier les données dans le Presse-papiers (raccourci clavier : Ctrl+C) {#copy-data}

L’option de clic droit **[!UICONTROL Copier dans le Presse-papiers]** permet de copier rapidement des données de Workspace et de les coller ailleurs.

* Si vous souhaitez copier le tableau affiché, cliquez avec le bouton droit sur l’en-tête du tableau et choisissez **Copier les données dans le Presse-papiers**.
* Si vous souhaitez copier un sous-ensemble de données, effectuez une sélection dans le tableau, puis cliquez avec le bouton droit de la souris > **Copier la sélection dans le Presse-papiers**.

De plus, la touche d&#39;accès rapide `Ctrl+C` copie votre sélection dans le Presse-papiers. Une fois copié, vous pouvez aller dans un autre outil et coller les informations (ou cliquer sur `Ctrl+V`).

![](assets/copy-selection.png)

## Télécharger les données au format CSV {#download-data}

L’option de clic droit **[!UICONTROL Télécharger les données au format CSV]** vous permet de télécharger un tableau de données ou la source de données de toute visualisation au format CSV.

* Dans l’en-tête d’un tableau ou d’une visualisation, cliquez avec le bouton droit de la souris sur **[!UICONTROL Télécharger les données au format CSV]**. Cela télécharge les données affichées dans le tableau ou la source de données sous-jacente pour une visualisation au format CSV. Remarque : la visualisation de zone cliquable ne prend pas en charge cette option.
* Si une sélection est effectuée dans le tableau, l’option indique **[!UICONTROL Télécharger la sélection au format CSV]**. Seule la sélection est téléchargée avec cette option, par opposition au tableau complet affiché.

![](assets/download-data-viz.png)

## Télécharger les éléments au format CSV {#download-items}

Si vous souhaitez analyser plus de 400 lignes de données visibles dans un tableau, cliquez avec le bouton droit de la souris sur l’en-tête du tableau ou sur une ligne et sélectionnez **Télécharger les éléments au format CSV (nom de la Dimension)**. Cette option exporte jusqu’à 50 000 éléments de dimension (selon le tri du tableau) pour la dimension sélectionnée, avec des filtres et des segments appliqués. Si vous choisissez cette option dans la partie supérieure du tableau, la première dimension du tableau est exportée. Bien qu’aucune limite ne soit appliquée dans le tableau à structure libre, il est recommandé d’utiliser l’option Télécharger les éléments dans des tableaux de moins de 20 colonnes afin d’assurer des performances optimales.

>[!TIP]
>
> Si votre dimension dépasse 50 000 éléments, téléchargez le fichier avec différentes mesures de tri appliquées ou appliquez un filtre. Par exemple, triez par descente les visites dans un téléchargement, puis par montée les visites dans un second téléchargement. Cette astuce peut vous aider à récupérer des éléments à queue longue.

Vous pouvez effectuer plusieurs tâches dans le projet et même accéder à un nouveau projet Workspace dans le même onglet pendant le téléchargement. Le téléchargement s’interrompt si vous ouvrez un nouvel onglet de navigateur. Le téléchargement s’annule si vous quittez Workspace complètement ou fermez l’onglet du navigateur.

![](assets/download-items.png)

### Fichier d&#39;éléments téléchargés

Les fonctionnalités du tableau seront appliquées au fichier téléchargé comme suit :

* Tous les segments de panneau sont appliqués en tant que filtres.
* Les ventilations **au-dessus** de la dimension sélectionnée dans le tableau sont appliquées en tant que filtres au-dessus de chaque colonne.
* Les ventilations **inférieures** à la dimension sélectionnée dans le tableau sont supprimées.

Dans l’exemple ci-dessus, les éléments de page sont téléchargés avec le segment de panneau (Nouveaux clients Visiteurs) et les composants ci-dessus (Canal marketing = E-mail) appliqués en tant que filtres, et les composants ci-dessous (Type de périphérique mobile) supprimés du fichier CSV téléchargé.

![](assets/downloaded-file.png)

### Téléchargement de notifications

Au fur et à mesure du téléchargement du fichier, vous verrez une notification d’informations avec la progression. Vous pouvez à tout moment annuler le téléchargement en cliquant sur **[!UICONTROL Annuler le téléchargement]**. La fermeture du toast **n&#39;annulera pas** le téléchargement.

Une fois le fichier terminé, une notification d’achèvement s’affiche et le fichier est téléchargé dans votre navigateur.

Si vous demandez plusieurs téléchargements à la fois, vous recevrez une notification indiquant que chaque téléchargement supplémentaire sera mis en file d’attente jusqu’à ce que le téléchargement précédent se termine.

![](assets/toast.png)

## FAQ {#faq}

| Question | Réponse |
| --- | --- |
| Pourquoi mon PDF téléchargé contient-il une page ? | Workspace ne pagine pas actuellement les fichiers PDF téléchargés. |
| Puis-je exporter plus de 50 000 éléments avec l’option &quot;Télécharger les éléments au format CSV&quot; ? | Bien que chaque téléchargement puisse contenir jusqu’à 50 000 éléments de dimension, vous pouvez modifier le type de votre tableau pour récupérer des éléments plus longs ou appliquer un filtre pour télécharger des éléments plus spécifiques. |
| Que fait **[!UICONTROL Copier la visualisation]** ? | **[!UICONTROL La]** visualisation de copie n’est pas une option d’exportation. Il vous permet de copier une visualisation ou un panneau d’un emplacement de Workspace à un autre. Par exemple, d’un panneau à un autre dans le même projet, ou d’un projet à un autre. [Vidéo avec liaison interne](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |

