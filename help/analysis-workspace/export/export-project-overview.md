---
description: Découvrez les méthodes disponibles pour l’exportation depuis Analysis Workspace.
keywords: Analysis Workspace
title: Comment exporter des données de projet
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Présentation de l’exportation

Vous pouvez exporter des rapports de Customer Journey Analytics à partir d’Analysis Workspace. Vous pouvez exporter des rapports de Customer Journey Analytics pour plusieurs raisons, par exemple pour les utiliser dans des outils tiers ou les combiner à des données externes.

Les sections suivantes décrivent les types de fichiers pris en charge, les différentes méthodes d’exportation disponibles et les avantages de chaque méthode.

## Types de fichiers pris en charge

Vous pouvez exporter des rapports de Customer Journey Analytics au format PDF, CSV ou JSON.

* **PDF :** Permet de partager facilement des données visuelles avec les parties prenantes. Les fichiers PDF contiennent tous les tableaux et visualisations affichés (visibles) dans le projet.

* **CSV :** Permet d’afficher les données brutes dans une application de feuille de calcul, telle qu’Excel. Les fichiers CSV contiennent des données en texte brut.

* **JSON :** Fournit un format de fichier standard ouvert pour le partage de données.

## Méthodes d&#39;export

Plusieurs méthodes sont disponibles lors de l’export depuis Analysis Workspace. Lorsque vous choisissez une méthode d’exportation, tenez compte de ce que vous souhaitez exporter et de qui doit y accéder.

| Méthode d’exportation | Avantages |
|---------|----------|
| [Télécharger vers votre poste de travail](/help/analysis-workspace/export/download-send.md) | Utilisez cette méthode pour : <ul><li>Téléchargez des projets sur votre poste de travail personnel.</li><li>Les téléchargements sont ad hoc uniquement (ils ne peuvent pas être programmés).</li> <li>Téléchargez un total de 50 000 lignes.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Envoyer à d’autres utilisateurs](/help/analysis-workspace/export/t-schedule-report.md) | Utilisez cette méthode pour : <ul><li>Envoyez par courrier électronique des données de Customer Journey Analytics exportées à d’autres utilisateurs de votre entreprise.</li><li>Il peut s’agir d’une opération ad hoc ou d’une planification.</li> <li>Incluez un total de 50 000 lignes.</li> <!--true?--> |
| [Envoi à une application cloud](/help/analysis-workspace/export/export-cloud.md) | Utilisez cette méthode pour : <ul><li>Exportez vers un emplacement partagé, tel que Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 ou Snowflake.</li><li>Il peut s’agir d’une opération ad hoc ou d’une planification.</li><li>Stocker de plus grandes quantités de données de Customer Journey Analytics.</li><li>Exportez des tableaux complets qui contiennent des milliers ou des millions de lignes.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
