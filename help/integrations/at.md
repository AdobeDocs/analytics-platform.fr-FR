---
title: Rapports Target dans Adobe Customer Journey Analytics
description: Intégration d’Adobe Target à Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 40%

---

# Rapports Target dans Adobe Customer Journey Analytics

La création de rapports Target dans Customer Journey Analytics vous permet de mesurer les activités Adobe Target et d’en créer des rapports directement dans Customer Journey Analytics. Cette fonctionnalité est comparable à ce qui est effectué dans Adobe Analytics (AA) via Analytics for Target (A4T), mais avec la connectivité à Adobe Experience Platform (AEP).

En ajoutant le jeu de données de recherche de classification cible (disponible par défaut dans Experience Platform) dans une connexion Customer Journey Analytics, les utilisateurs sont désormais bien exposés aux outils de création de rapports Target, à l’attribution de commandes Target et à d’autres fonctionnalités. Avec seulement quelques préparations mineures et des ajustements apportés dans la vue de données du Customer Journey Analytics, ces activités peuvent être immédiatement disponibles pour tout utilisateur qui souhaite envoyer des données Target directement dans CJA.

## Avantages du Principal

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de Customer Journey Analytics aux rapports d’activité de Target, à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Les personnes spécialisées dans le marketing peuvent tirer parti des fonctionnalités de Customer Journey Analytics, telles que le panneau Expérimentation, pour analyser davantage la personnalisation de leur site web.
* Les personnes spécialisées dans le marketing peuvent disposer d’une source unique de création de rapports pour Adobe Journey Optimizer et Target. Les deux produits de personnalisation peuvent être connectés à Customer Journey Analytics pour une vue plus holistique de votre personnalisation web.

## Remarques et considérations

Une fois que le jeu de données d’événement de classification cible a été ajouté à une connexion CJA, quelques ajustements mineurs doivent être effectués dans la vue de données CJA une fois que ces composants ont été ajoutés en tant que dimensions, notamment :

* La définition de la persistance comme étant similaire à la manière dont elle est suivie dans Target (contactez un consultant Target ou le client pour vérifier les paramètres appropriés).

* Définissez la persistance sur ALL, ce qui permet le suivi simultané de plusieurs activités Target et de ne pas les remplacer par des activités antérieures ou futures.

## Informations plus détaillées

Voir [Création de rapports de Target dans Adobe Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja) dans la documentation de Target pour plus d’informations.

Voir le [panneau Expérimentation](../analysis-workspace/c-panels/experimentation.md) pour en savoir plus sur la manière dont les personnes chargées des analyses peuvent comparer des variantes d’expérience client, de marketing ou de messagerie afin de déterminer la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation, en ligne, hors ligne, à partir de solutions Adobe comme Target ou Journey Optimizer et même de données BYO (apportez vos propres données).
