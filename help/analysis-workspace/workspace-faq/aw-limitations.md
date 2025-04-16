---
description: En savoir plus sur les limites connues d’Adobe Analysis Workspace et ses composants connexes
title: Limites connues dans Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 79%

---

# Limites connues dans Analysis Workspace

Voici une liste des limites connues dans Analysis Workspace et ses composants connexes :

## Tableaux

* Impossibilité d’ajouter des colonnes de comparaison de dates lorsque des périodes ou des mesures sont utilisées comme lignes d’un tableau.
* L’option Créer une mesure d’après la sélection est désactivée lorsque des filtres sont utilisés comme lignes d’un tableau. De plus, l’option Créer une mesure d’après la sélection ne doit pas être appliquée aux colonnes alignées sur la date.
* La mise en forme conditionnelle des lignes de répartition ne peut pas utiliser de plages personnalisées.
* Les lignes totales du tableau ne peuvent pas être sous forme de tendances lorsque le paramètre Calculer les totaux en totalisant les valeurs est appliqué (généralement utilisé avec les éléments de ligne statique).

## Visualisations

* Les visualisations qui tirent parti des segments, telles que [!UICONTROL Abandon], [!UICONTROL Flux], [!UICONTROL Cohorte] et [!UICONTROL Histogramme], ne peuvent pas accepter les mesures calculées en tant qu’entrées.
* [!UICONTROL Flux] : les dimensions d’entrée/de sortie, comme la [!UICONTROL page d’entrée], ne peuvent pas être utilisées dans Flux.
* [!UICONTROL Cohorte] : Les nombres non entiers ne peuvent pas être utilisés comme critères Cohorte.

## Filtres

* Certaines mesures et dimensions ne peuvent pas être segmentées, comme [!UICONTROL Événements], [!UICONTROL Personnes], etc.
* Les segments ad hoc créés dans la [zone de dépôt du panneau](/help/analysis-workspace/c-panels/panels.md) sont un type de segment rapide. Ils n’apparaissent pas dans le panneau de gauche de Workspace ni dans le gestionnaire du composant Filtre, sauf s’ils sont rendus publics. Pour en savoir plus, voir [Segments rapides](/help/components/filters/quick-filters.md).

## Mesures calculées

* Il n’est pas possible d’utiliser les mesures calculées dans certaines visualisations. Consultez [Visualisations](#visualizations).
* Les mesures calculées ne peuvent pas être utilisées dans le panneau [!UICONTROL Attribution], car elles peuvent inclure elles-mêmes des modèles d’attribution distincts.
* Certains composants et opérateurs ne sont pas disponibles si une mesure calculée est créée à partir de Workspace (contrairement à une création à partir de [!UICONTROL Composants > segments]). Par exemple, [!UICONTROL Adresse IP].

## Périodes

* Les périodes personnalisées ne prennent pas en charge [!UICONTROL Ce jour l’année dernière], [!UICONTROL Ce jour le mois dernier], etc.


## Paramètres des rapports

* Certains paramètres de la page [!UICONTROL Paramètres de rapport] ne s’appliquent pas. Analysis Workspace utilise uniquement les paramètres [!UICONTROL Langue/Devise/Encodage] situés en bas : [!UICONTROL Séparateur des milliers], [!UICONTROL Encodage d’un rapport planifié] et [!UICONTROL Caractère de séparation CSV].

