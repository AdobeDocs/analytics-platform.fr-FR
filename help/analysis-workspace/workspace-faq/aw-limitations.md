---
description: En savoir plus sur les limites connues d’Adobe Analysis Workspace et ses composants connexes
title: Limites connues
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
TQID: https://experienceleague.adobe.com/rbguvYCSFfbmMVr5IBC1M9OD0wDIG0Z4p28Z2dOerBc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 100%

---

# Limites connues

Voici une liste des limites connues dans Analysis Workspace et ses composants connexes :

## Tableaux

* Impossibilité d’ajouter des colonnes de comparaison de dates lorsque des périodes ou des mesures sont utilisées comme lignes d’un tableau.
* L’option Créer une mesure d’après la sélection est désactivée lorsque des segments sont utilisés comme lignes d’un tableau. De plus, l’option Créer une mesure d’après la sélection ne doit pas être appliquée aux colonnes alignées sur la date.
* La mise en forme conditionnelle des lignes de répartition ne peut pas utiliser de plages personnalisées.
* Les lignes totales du tableau ne peuvent pas être sous forme de tendances lorsque le paramètre Calculer les totaux en totalisant les valeurs est appliqué (généralement utilisé avec les éléments de ligne statique).

## Visualisations

* Les visualisations qui tirent parti des segments, par exemple [!UICONTROL Abandons], [!UICONTROL Flux], [!UICONTROL Cohorte] et [!UICONTROL Histogramme], ne peuvent pas accepter les mesures calculées en tant qu’entrées.
* [!UICONTROL Flux] : les dimensions d’entrée/de sortie, comme la [!UICONTROL page d’entrée], ne peuvent pas être utilisées dans Flux.
* [!UICONTROL Cohorte] : Les nombres non entiers ne peuvent pas être utilisés comme critères Cohorte.

## Segments

* Certaines mesures et dimensions ne peuvent pas être filtrées, comme [!UICONTROL Événements], [!UICONTROL Personnes], etc.
* Les segments ad hoc créés dans la [zone de dépôt du panneau](/help/analysis-workspace/c-panels/panels.md) sont un type de segment rapide. Ils n’apparaissent pas dans le panneau de gauche de Workspace ni dans le gestionnaire de segments, sauf s’ils sont rendus publics. Pour en savoir plus, consultez [Segments rapides](/help/components/segments/seg-quick.md).

## Mesures calculées

* Il n’est pas possible d’utiliser les mesures calculées dans certaines visualisations. Consultez [Visualisations](#visualizations).
* Les mesures calculées ne peuvent pas être utilisées dans le panneau [!UICONTROL Attribution], car elles peuvent inclure elles-mêmes des modèles d’attribution distincts.
* Certains composants et opérateurs ne sont pas disponibles si une mesure calculée est créée à partir de Workspace (contrairement à une création à partir de [!UICONTROL Composants > Segments]). Par exemple, [!UICONTROL Adresse IP].

## Périodes

* Les périodes personnalisées ne prennent pas en charge [!UICONTROL Ce jour l’année dernière], [!UICONTROL Ce jour le mois dernier], etc.


## Paramètres des rapports

* Certains paramètres de la page [!UICONTROL Paramètres de rapport] ne s’appliquent pas. Analysis Workspace utilise uniquement les paramètres [!UICONTROL Langue/Devise/Encodage] situés en bas : [!UICONTROL Séparateur des milliers], [!UICONTROL Encodage d’un rapport planifié] et [!UICONTROL Caractère de séparation CSV].

