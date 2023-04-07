---
description: 'Liste des limites connues d’Adobe Analysis Workspace et ses composants connexes :'
title: Limites connues dans Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c21eb39e0af36ad54fd675c147e2f50b6b00711a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Limites connues dans Analysis Workspace

Voici une liste des limites connues dans Analysis Workspace et ses composants connexes :

## Tableaux

* Impossibilité d’ajouter des colonnes de comparaison de dates lorsque des périodes ou des mesures sont utilisées comme lignes d’un tableau.
* L’option Créer une mesure d’après la sélection est désactivée lorsque des filtres sont utilisés comme lignes d’un tableau. De plus, l’option Créer une mesure d’après la sélection ne doit pas être appliquée aux colonnes alignées sur la date.
* La mise en forme conditionnelle des lignes de ventilation ne peut pas utiliser de plages personnalisées.
* Les lignes totales du tableau ne peuvent pas être sous forme de tendances lorsque le paramètre Calculer les totaux en totalisant les valeurs est appliqué (généralement utilisé avec les éléments de ligne statique).
* [!UICONTROL L’analyse des contributions] peut être exécutée avec la granularité [!UICONTROL quotidienne] _uniquement_. Elle ne peut pas être exécutée par rapport à des données [!UICONTROL horaires], [!UICONTROL hebdomadaires], etc.

## Visualisations

* Les visualisations qui tirent parti des filtres, telles que [!UICONTROL Abandons], [!UICONTROL Flux], [!UICONTROL Cohorte] et [!UICONTROL Histogramme], ne peuvent pas accepter les mesures calculées en tant qu’entrées.
* [!UICONTROL Flux] : les dimensions d’entrée/de sortie, comme la [!UICONTROL page d’entrée], ne peuvent pas être utilisées dans Flux.
* [!UICONTROL Cohorte] : Les nombres non entiers ne peuvent pas être utilisés comme critères Cohorte.

## Composants > Filtres

* Il n’est pas possible de filtrer certaines mesures et dimensions, comme [!UICONTROL Occurrences], [!UICONTROL Visiteurs uniques], etc.
* Les filtres ad hoc créés dans la [zone de dépôt du panneau](/help/analysis-workspace/c-panels/panels.md) n’apparaissent pas dans le rail de gauche de l’espace de travail ou dans le gestionnaire de composants Filtre, sauf s’ils sont rendus publics. Pour ce faire, modifiez le filtre et sélectionnez **[!UICONTROL Rendre ce filtre public]**.

## Composants > Mesures calculées

* Il n’est pas possible d’utiliser les mesures calculées dans certaines visualisations. Voir « Visualisations » ci-dessus.
* Les mesures calculées ne peuvent pas être utilisées dans le panneau [!UICONTROL Attribution], car elles peuvent inclure elles-mêmes des modèles d’attribution distincts.
* Certains composants et opérateurs ne sont pas disponibles si une mesure calculée est créée à partir de l’espace de travail (contrairement à une création à partir de [!UICONTROL Composants > Filtres]). Par exemple, [!UICONTROL Adresse IP].

## Composants > Périodes

* Les périodes personnalisées ne prennent pas en charge [!UICONTROL Ce jour l’année dernière], [!UICONTROL Ce jour le mois dernier], etc.


## Composants > Paramètres de rapport

* Certains paramètres de la page [!UICONTROL Paramètres de rapport] ne s’appliquent pas. Analysis Workspace utilise uniquement les paramètres [!UICONTROL Langue/Devise/Encodage] situés en bas : [!UICONTROL Séparateur des milliers], [!UICONTROL Encodage d’un rapport planifié] et [!UICONTROL Caractère de séparation CSV].

