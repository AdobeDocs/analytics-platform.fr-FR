---
title: Rapports Target
description: Intégration d’Adobe Target à Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# Rapports Target

Le compte rendu des performances de Target dans Customer Journey Analytics vous permet de mesurer les activités d’Adobe Target et d’en générer des rapports directement dans Customer Journey Analytics. Cette fonctionnalité est comparable à ce qui est effectué dans Adobe Analytics (AA) via Analytics for Target (A4T), mais avec la connectivité à Adobe Experience Platform (AEP).

En ajoutant le jeu de données de recherche de classification de Target (disponible par défaut dans Experience Platform) dans une connexion Customer Journey Analytics, les utilisateurs sont désormais correctement exposés aux outils de reporting de Target, à l’attribution d’ordre cible et à d’autres fonctionnalités. Avec seulement quelques préparations mineures et ajustements dans la vue de données Customer Journey Analytics, ces activités peuvent être mises immédiatement à la disposition de tout utilisateur qui souhaite envoyer des données Target directement dans CJA.

## avantages du Principal

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de Customer Journey Analytics aux rapports d’activité de Target, à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Les personnes spécialisées dans le marketing peuvent tirer parti des fonctionnalités de Customer Journey Analytics, telles que le panneau Expérimentation, pour analyser davantage la personnalisation de leur site web.
* Les personnes spécialisées dans le marketing peuvent disposer d’une source unique de création de rapports pour Adobe Journey Optimizer et Target. Les deux produits de personnalisation peuvent être connectés à Customer Journey Analytics pour une vue plus holistique de votre personnalisation web.

## Remarques et considérations

Votre activité Target doit [utiliser Customer Journey Analytics comme source de création de rapports](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja).

Une fois que le jeu de données d’événement de classification cible a été ajouté à une connexion, quelques ajustements mineurs doivent être effectués dans la vue de données une fois que ces composants ont été ajoutés en tant que dimensions, notamment :

* Définir la persistance de façon à ce qu’elle soit similaire au suivi dans Target (consultez un consultant Target ou le client pour vous assurer que les paramètres appropriés sont définis).

* Définition de la persistance sur ALL, ce qui permet le suivi simultané de plusieurs activités Target et de ne pas les remplacer par des activités antérieures ou futures.

## Informations plus détaillées

Voir [Création de rapports de Target dans Adobe Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja) dans la documentation de Target pour plus d’informations.

Voir le [panneau Expérimentation](../analysis-workspace/c-panels/experimentation.md) pour en savoir plus sur la manière dont les personnes chargées des analyses peuvent comparer des variantes d’expérience client, de marketing ou de messagerie afin de déterminer la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation, en ligne, hors ligne, à partir de solutions Adobe comme Target ou Journey Optimizer et même de données BYO (apportez vos propres données).
