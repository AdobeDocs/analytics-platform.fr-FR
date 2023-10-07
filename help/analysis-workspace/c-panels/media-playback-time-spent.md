---
title: Panneau Durée de lecture des médias
description: Comment utiliser et interpréter le panneau Durée de lecture des médias dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
source-git-commit: 16f1a732260ace8393d7303134fc351740fd1661
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 74%

---

# Panneau Durée de lecture des médias

Dans Analysis Workspace, la durée de lecture correspond à la durée passée à visionner vos diffusions multimédia à un moment donné. Il comprend la mise en pause, la mise en mémoire tampon et le temps de démarrage.

Le panneau Durée de lecture des médias permet dʼanalyser la lecture au fil du temps. Il fournit également des informations détaillées sur le pic dʼaccès simultanés et la possibilité de ventiler et de comparer.

Les clients Media Analytics peuvent analyser le temps de lecture pour obtenir des informations précieuses sur la qualité du contenu et l’engagement des observateurs, et pour aider à résoudre les problèmes ou à planifier le volume ou l’échelle.

La durée de lecture de la visite peut vous aider à comprendre :

* Où le pic d’accès simultané s’est produit

* Où des abandons ont eu lieu

Voici une présentation vidéo de ce panneau :

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Utilisation du panneau Durée de lecture du média

1. Accédez à une suite de rapports avec les composants Media Analytics activés.

1. Sélectionnez l’icône de panneau à l’extrême gauche, puis faites glisser le panneau dans votre projet Analysis Workspace.

1. Passez aux sections suivantes pour personnaliser le panneau Durée de lecture multimédia

   * [Entrées de panneau](#panel-inputs)
   * [Sortie de panneau](#panel-output)

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau Durée de lecture des médias à lʼaide des paramètres dʼentrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou dʼheure relatifs à la durée de la lecture, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. La somme additionne la durée de lecture totale de la sélection. Le panneau nʼindique par défaut que la valeur maximale, mais vous pouvez modifier cette valeur par défaut et afficher la valeur minimale, la valeur totale ou une combinaison des trois valeurs.<br>Si vous utilisez des répartitions, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Répartition de la série | Vous pouvez éventuellement ventiler votre visualisation par filtres, dimensions, éléments de dimension ou périodes.<p>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.</p><p>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.</p>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de répartition de la série. |
| Format de l’heure | Vous pouvez afficher la durée de lecture en heures:Minutes:secondes (par défaut) ou en minutes (sʼaffiche en nombres entiers, arrondis à 0,5). |
| Affichage de la séquence de dates | Si vous avez placé au moins deux filtres de période en tant que ventilations de série, vous aurez la possibilité de sélectionner l’option de superposition (par défaut) ou séquentielle. La superposition affiche les lignes avec un point de départ commun sur lʼaxe X afin quʼelles se déroulent en parallèle. Séquentiel affiche les lignes avec leur point de départ spécifique sur lʼaxe X. Si les lignes de données s’affichent (par exemple, le filtre 1 se termine à 20 h 44 et le filtre 2 commence à 20 h 45), les lignes s’affichent dans l’ordre. |

## Affichage par défaut

![La vue par défaut Durée de la lecture du contenu multimédia.](assets/mpts_default_view.png)

## Sortie de panneau {#Output}

Le panneau Durée de lecture des médias renvoie un graphique en courbes et des numéros de synthèse, qui incluent des détails sur la durée maximale, minimale et/ou totale de la lecture. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, vous pouvez modifier et recréer le panneau en cliquant sur l’icône de modification en forme de crayon dans le coin supérieur droit.

Si vous avez sélectionné la répartition des séries, une ligne du graphique en courbe et une synthèse des chiffres s’affichent pour chacune d’elles :

![La sortie de la durée de lecture du média affiche un graphique en courbes et un résumé.](assets/mpts_outputs1.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est Durée de la lecture.

| Mesure | Description |
|---|---|
| Durée de la lecture | Nombre total dʼheures:minutes:secondes (ou minutes) de contenu affiché lors de la granularité sélectionnée, y compris la mise en pause, la mise en mémoire tampon et le temps de démarrage. |

## Questions fréquentes

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | <p></p><p>Le tableau à structure libre n’est pas disponible dans cet affichage. Téléchargez la source de données en effectuant un clic droit sur le graphique en courbes, puis téléchargez le fichier CSV.</p> |
| <p>Pourquoi ma granularité a-t-elle changé ?</p> | <p>La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à l’intégralité de la période.</p><p></p><p>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation.</p> |
| <p></p><p>Comment comparer les noms des vidéos, les filtres, les types de contenu, etc. ?</p> | <p>Pour les comparer dans une visualisation unique, faites glisser des filtres, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation de série.</p><p></p><p>L’affichage est limité à 10 répartitions. Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux.</p> |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les répartitions des séries en faisant glisser au moins 2 périodes. Ces périodes remplacent alors la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | <p></p><p>Ce panneau permet uniquement la visualisation des lignes pour la série temporelle.</p> |
| Puis-je exécuter la détection des anomalies ? | <p></p><p>Non. La détection des anomalies n’est pas disponible pour ce panneau.</p> |
