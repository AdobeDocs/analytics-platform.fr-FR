---
title: API de création de rapports Customer Journey Analytics
description: Décrit comment utiliser l’API de création de rapports pour récupérer des données Customer Journey Analytics par programmation.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%
---

# API Reporting

Cet article décrit comment le [!DNL Customer Journey Analytics Reporting API] peut être utilisé pour implémenter le cas d’utilisation d’exportation de données [ suivant ](overview.md) :

- Intégration d’applications personnalisées

## Introduction

Le [!DNL Customer Journey Analytics Reporting API] vous permet de récupérer par programmation les mêmes dimensions et mesures traitées que celles disponibles dans Analysis Workspace. Utilisez le [!DNL Reporting API] pour alimenter des applications personnalisées, incorporer des rapports dans des outils internes ou automatiser la récupération de données Customer Journey Analytics sans exportation manuelle.

## Informations supplémentaires

Le [!DNL Reporting API] utilise le même format de requête et de réponse que le [!DNL Reporting API] [!DNL Adobe Analytics], mais utilise un autre point d’entrée. Si vous migrez des intégrations de rapports à partir d’[!DNL Adobe Analytics], consultez le workflow de migration dans le [guide de démarrage rapide](/help/getting-started/cja-getting-started.md) pour plus d’informations.

Pour l’authentification, les points d’entrée disponibles et les limites de requête actuelles, consultez la documentation de l’API Customer Journey Analytics [](https://developer.adobe.com/cja-apis/docs/?lang=fr).
