---
title: Rapports Target
description: Intégration d’Adobe Target à Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: 979564d0249abadd454ce43aba9aeae2c78a44f0
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 41%

---

# Rapports Target

Le compte rendu des performances de Target dans Customer Journey Analytics vous permet de mesurer les activités d’Adobe Target et d’en générer des rapports directement dans Customer Journey Analytics. Cette fonctionnalité est comparable à ce qui est effectué dans Adobe Analytics (AA) via Analytics for Target (A4T), mais avec la connectivité à Adobe Experience Platform (AEP).

En ajoutant le jeu de données de recherche de classification de Target (disponible par défaut dans Experience Platform) dans une connexion Customer Journey Analytics, les utilisateurs sont désormais correctement exposés aux outils de reporting de Target, à l’attribution d’ordre cible et à d’autres fonctionnalités. Avec seulement quelques préparations mineures et ajustements dans la vue de données Customer Journey Analytics, ces activités peuvent être mises immédiatement à la disposition de tout utilisateur qui souhaite envoyer des données Target directement dans CJA.

## avantages du Principal

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de Customer Journey Analytics aux rapports d’activité de Target, à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Les personnes spécialisées dans le marketing peuvent tirer parti des fonctionnalités de Customer Journey Analytics, telles que le panneau Expérimentation, pour analyser davantage la personnalisation de leur site web.
* Les personnes spécialisées dans le marketing peuvent disposer d’une source unique de création de rapports pour Adobe Journey Optimizer et Target. Les deux produits de personnalisation peuvent être connectés à Customer Journey Analytics pour une vue plus holistique de votre personnalisation web.

## Remarques et considérations

Une fois que le jeu de données d’événement de classification cible a été ajouté à une connexion CJA, quelques ajustements mineurs doivent être effectués dans la vue de données CJA une fois que ces composants ont été ajoutés en tant que dimensions, notamment :

* Définir la persistance de façon à ce qu’elle soit similaire au suivi dans Target (consultez un consultant Target ou le client pour vous assurer que les paramètres appropriés sont définis).

* Définition de la persistance sur ALL, ce qui permet le suivi simultané de plusieurs activités Target et de ne pas les remplacer par des activités antérieures ou futures.

## Informations plus détaillées

Voir [Création de rapports de Target dans Adobe Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja) dans la documentation de Target pour plus d’informations.

Voir le [panneau Expérimentation](../analysis-workspace/c-panels/experimentation.md) pour en savoir plus sur la manière dont les personnes chargées des analyses peuvent comparer des variantes d’expérience client, de marketing ou de messagerie afin de déterminer la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation, en ligne, hors ligne, à partir de solutions Adobe comme Target ou Journey Optimizer et même de données BYO (apportez vos propres données).
