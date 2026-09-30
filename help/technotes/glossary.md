---
title: Glossaire Customer Journey Analytics
description: Glossaire de Customer Journey Analytics.
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
feature: Basics
role: User
autotag-review: '2026-05-19T09:29:03.007Z'
TQID: 'https://experienceleague.adobe.com/BxQ-hPP9Uh5gfdnEaVOWkfVG8UVj0KVhhmFqKtMXtRA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: cf731116-8803-4027-85aa-9c0a126e8321
    internal-label: Dataset configuration
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 95%
---
# Glossaire Customer Journey Analytics

Certains termes de Customer Journey Analytics diffèrent de leur utilisation habituelle dans Adobe Analytics :

| Nouveau terme Customer Journey Analytics | Terme Adobe Analytics | Description |
| --- | --- | --- |
| Jeu de données de recherche | En-tête | Utilisez la recherche pour récupérer la valeur du jeu de données spécifié pour une clé/clé correspondante (dans un jeu de données d’événement) où il existe une relation 1:1. Par exemple, vous pouvez spécifier « code_de_suivi » comme clé correspondant à « code_de_suivi » dans le jeu de données de l’événement. |
| Jeu de données de profil | Attribut du client | Si vous capturez les données client d’entreprise dans une base de données de gestion de la relation client (GRC), vous pouvez les charger dans un jeu de données de profil dans Adobe Experience Platform. Après avoir créé une connexion à ce jeu de données dans Customer Journey Analytics et créé une vue de données, exploitez les données dans Workspace. |
| Organisation CX Enterprise (Experience Cloud) | Société de connexion | Voir [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=fr#topic_C31CB834F109465A82ED57FF0563B3F1). |
| S.O. | Suite de rapports | Les suites de rapports au sens traditionnel d’Adobe Analytics n’existent plus. A la place, vous créez des [vues de données](/help/data-views/create-dataview.md) (virtuelles) à partir des jeux de données Platform vers lesquels vous avez établi des connexions. |
| Segment | Segment | Les segments étaient auparavant des « filtres ». Ils ont été renommés « segments ». |
| Vue de données | Suite de rapports virtuelle | Dans Adobe Analytics, une suite de rapports virtuelle est une vue filtrée dʼune suite de rapports parente. La principale différence entre une suite de rapports virtuelle et une vue de données dans Customer Journey Analytics réside dans le fait que la suite de rapports virtuelle est un sous-ensemble d’une suite de rapports « de base » ou « parente » et, en tant que telle, hérite de certains de ses paramètres. Comme les suites de rapports parents/de base n’existent plus, vous définissez des vues de données avec leurs propres paramètres. |

## Glossaire Adobe Experience Platform

Adobe Experience Platform standardise les données et le contenu à l’échelle de l’entreprise, alimentant ainsi les profils de consommateurs en temps réel, favorisant la science des données et améliorant la vélocité du contenu pour personnaliser les expériences tout au long du parcours client.
Pour plus d’informations, reportez-vous à la section [Glossaire Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html?lang=fr).
