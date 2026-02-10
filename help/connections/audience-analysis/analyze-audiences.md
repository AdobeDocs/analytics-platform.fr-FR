---
title: Analyse Des Audiences Experience Platform Dans Customer Journey Analytics
description: Découvrez comment analyser les audiences Experience Platform dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Analyse des audiences Experience Platform dans Customer Journey Analytics {#analyze-audiences-RTCDP}

Après avoir [créé une configuration d’analyse d’audience](/help/connections/audience-analysis/audience-analysis-configure.md), les données d’audience sont disponibles sous la forme de nouvelles dimensions dans les vues de données où vous les configurez pour les créer. Vous pouvez utiliser les nouvelles dimensions d’audience n’importe où dans Analysis Workspace si vous avez accès à une vue de données dans laquelle les dimensions d’analyse d’audience ont été ajoutées.

## Utiliser le modèle de présentation de l’audience

Un modèle de présentation des audiences est disponible dans Customer Journey Analytics.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

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

## Panneau d’utilisation de l’audience quitté

Affiche les données de toutes les audiences sorties avec des événements d’utilisation associés à la vue de données sélectionnée. Les données sont toujours affichées pour hier. Par conséquent, la modification de la période du panneau génère des données inexactes. Les « audiences sorties » sont des audiences dans lesquelles les personnes ayant des événements d’utilisation ont quitté hier.

Utilisez le tableau de ce panneau pour mieux comprendre le comportement de l’audience. Faites glisser la dimension Description de l’audience sortie de la vue de données sélectionnée et ajoutez-la en tant que répartition. Vous pouvez également utiliser toute autre dimension ou mesure d’interaction (telle que Page, Action, etc.) comme répartition.

## Panneau des principales origines d’audience sorties

Indique l’emplacement de création initial de chaque audience qui a été fermée, que ce soit dans RTCDP, Customer Journey Analytics, etc.

Utilisez le tableau de ce panneau pour mieux comprendre comment l’origine de l’audience peut affecter d’autres facteurs. Faites glisser la dimension Nom de l’audience sortie de la vue de données sélectionnée et ajoutez-la en tant que répartition. Vous pouvez également utiliser toute autre dimension ou mesure d’interaction (telle que Page, Action, etc.) comme répartition.
