---
title: Entrées et sorties du panneau Durée de lecture des médias
description: Quels sont les paramètres dʼentrée et de sortie du panneau Durée de lecture des médias ?
feature: Panels
role: User, Admin
exl-id: 4c0380ff-f55c-48a7-a4b2-1a291511e4d9
source-git-commit: 9f1394df9b57707d57c701e997df8f4cd70c7baa
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 100%

---

# Entrées et sorties du panneau Durée de lecture des médias {#Inputs-and-outputs}

Personnalisez le panneau Durée de lecture des médias à lʼaide des paramètres d’entrée et de sortie suivants.

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau Durée de lecture des médias à lʼaide des paramètres dʼentrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou dʼheure relatifs à la durée de la lecture, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. La somme additionne la durée de lecture totale de la sélection. Le panneau nʼindique par défaut que la valeur maximale, mais vous pouvez modifier cette valeur par défaut et afficher la valeur minimale, la valeur totale ou une combinaison des trois valeurs.<br>Si vous utilisez des ventilations, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Ventilations de la série | Vous pouvez éventuellement ventiler votre visualisation par segments, dimensions, éléments de dimension ou périodes.<p>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les ventilations sont limitées à un seul niveau.</p><p>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.</p>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de ventilation de la série. |
| Format de l’heure | Vous pouvez afficher la durée de lecture en heures:Minutes:secondes (par défaut) ou en minutes (sʼaffiche en nombres entiers, arrondis à 0,5). |
| Affichage de la séquence de dates | Si vous avez placé au moins deux segments de période en tant que ventilations de série, lʼoption permettant de sélectionner superposition (par défaut) ou séquentiel sʼaffiche. La superposition affiche les lignes avec un point de départ commun sur lʼaxe X afin quʼelles se déroulent en parallèle. Séquentiel affiche les lignes avec leur point de départ spécifique sur lʼaxe X. Si les données se suivent (par exemple, le segment 1 se termine à 20 h 44 et le segment 2 à 20 h 45), les lignes sʼaffichent de manière séquentielle. |

### Affichage par défaut

![Affichage par défaut](../assets/mpts_default_view.png)

## Sortie de panneau {#Output}

Le panneau Durée de lecture des médias renvoie un graphique en courbes et des numéros de synthèse, qui incluent des détails sur la durée maximale, minimale et/ou totale de la lecture. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, vous pouvez modifier et recréer le panneau en cliquant sur l’icône de modification en forme de crayon dans le coin supérieur droit.

Si vous avez sélectionné la ventilation des séries, une ligne du graphique en courbe et une synthèse des chiffres s’affichent pour chacune d’elles :

![sortie de durée de lecture des médias](../assets/mpts_outputs1.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est Durée de la lecture.

| Mesure | Description |
|---|---|
| Durée de la lecture | Nombre total dʼheures:minutes:secondes (ou minutes) de contenu affiché lors de la granularité sélectionnée, y compris la mise en pause, la mise en mémoire tampon et le temps de démarrage. |
