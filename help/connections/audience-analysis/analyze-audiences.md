---
title: Analyse des audiences Experience Platform dans Customer Journey Analytics
description: Découvrez comment analyser les audiences Experience Platform dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Analyse des audiences Experience Platform dans Customer Journey Analytics {#analyze-audiences-RTCDP}

Vous pouvez commencer à analyser les audiences Experience Platform dans Customer Journey Analytics après [création d’une configuration d’analyse d’audience](/help/connections/audience-analysis/audience-analysis-configure.md), lorsque les données d’audience sont disponibles en tant que nouvelles dimensions dans Analysis Workspace.

Un modèle de présentation des audiences est disponible dans Customer Journey Analytics.

Pour plus d’informations sur l’accès au modèle de présentation de l’audience, voir [Accès et exécution d’un modèle](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) dans [Utilisation de modèles](/help/analysis-workspace/templates/use-templates.md).

Le modèle Vue d’ensemble de l’audience contient les panneaux suivants :

## Panneau de présentation de l’utilisation

Affiche les données de toutes les audiences avec des événements d’utilisation associés à la vue de données sélectionnée. Les données d’appartenance à une audience sont mises à jour quotidiennement à partir d’Experience Platform. Les données sont toujours affichées pour hier. Par conséquent, la modification de la période du panneau génère des données inexactes.

Utilisez le tableau de ce panneau pour mieux comprendre le comportement de l’audience. Faites glisser la dimension Description de l’audience de la vue de données sélectionnée et ajoutez-la en tant que répartition. Vous pouvez également utiliser toute autre dimension d’interaction (telle que Page, Action, etc.) comme répartition.

## Panneau Principales origines d’audience

Indique l’emplacement de création de l’audience, que ce soit dans RTCDP, Customer Journey Analytics, etc.

Utilisez le tableau de ce panneau pour mieux comprendre comment l’origine de l’audience peut affecter d’autres facteurs. Faites glisser la dimension Nom de l’audience à partir de la vue de données sélectionnée et ajoutez-la en tant que répartition. Vous pouvez également utiliser toute autre dimension d’interaction (telle que Page, Action, etc.) comme répartition.

## Panneau de chevauchement des audiences

Affiche les données de toutes les audiences avec des événements d’utilisation associés à la vue de données sélectionnée. Les données sont toujours affichées pour hier. Par conséquent, la modification de la période du panneau génère des données inexactes.

Sélectionnez jusqu’à trois audiences dans le tableau de ce panneau pour voir comment elles se chevauchent dans le diagramme de Venn correspondant.

## Utilisation de l’audience quittée

Affiche les données de toutes les audiences sorties avec des événements d’utilisation associés à la vue de données sélectionnée. Les données sont toujours affichées pour hier. Par conséquent, la modification de la période du panneau génère des données inexactes. Les « audiences sorties » sont des audiences dans lesquelles les personnes ayant des événements d’utilisation ont quitté hier.

Utilisez le tableau de ce panneau pour mieux comprendre le comportement de l’audience. Faites glisser la dimension Description de l’audience existante de la vue de données sélectionnée et ajoutez-la en tant que répartition. Vous pouvez également utiliser toute autre dimension ou mesure d’interaction (telle que Page, Action, etc.) comme répartition.

## Panneau des principales origines d’audience sorties

Indique l’emplacement de création initial de chaque audience qui a été fermée, que ce soit dans RTCDP, Customer Journey Analytics, etc.

Utilisez le tableau de ce panneau pour mieux comprendre comment l’origine de l’audience peut affecter d’autres facteurs. Faites glisser la dimension Nom de l’audience sortie de la vue de données sélectionnée et ajoutez-la en tant que répartition. Vous pouvez également utiliser toute autre dimension ou mesure d’interaction (telle que Page, Action, etc.) comme répartition.








