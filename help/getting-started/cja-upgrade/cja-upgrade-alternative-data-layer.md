---
title: Autres méthodes lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez les autres méthodes disponibles lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 44%

---

# Alternative de mise à niveau : envoyez votre couche de données à Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Envoyer la couche de données à Adobe"
>abstract="Au lieu d’envoyer des données par le biais d’un objet XDM, vous pouvez envoyer l’intégralité de votre couche de données à Adobe par le biais de l’objet de données.<br><br>Cette option permet de gagner du temps d’implémentation en vous permettant de mapper votre couche de données à XDM, plutôt que de renseigner entièrement un objet XDM. Cependant, ce mappage représente une charge de travail importante, car il contient une quantité importante de données qu’Adobe ne peut pas interpréter facilement. Cette option introduit également une complexité supplémentaire au fil du temps, car tout champ ajouté ultérieurement à vos données doit être mappé à XDM dans le train de données."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Envoyer votre couche de données à Adobe"
>abstract="Configurez votre implémentation pour envoyer des données à Adobe au moment souhaité et configurez la payload JSON pour qu’elle constitue votre couche de données dans son intégralité."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Attribuer chaque élément de couche de données à XDM"
>abstract="Mappez chaque élément de couche de données au champ XDM souhaité. Tous les éléments de couche de données qui ne sont pas mappés à un champ XDM sont définitivement supprimés, car Adobe ne sait pas où ni comment stocker ces données."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Lors de la mise à niveau vers Customer Journey Analytics, Adobe [recommande une nouvelle implémentation de la SDK Web Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Cependant, en fonction de plusieurs facteurs, tels que les contraintes de calendrier et de ressources, les étapes de mise à niveau recommandées peuvent ne pas être pratiques pour votre organisation.

Vous pouvez envoyer l’intégralité de la couche de données à Customer Journey Analytics au lieu de collecter des données avec l’objet XDM. Cependant, cette alternative introduit une complexité supplémentaire au fil du temps.

## Avantages et inconvénients

Cette méthode s’exclut mutuellement [en utilisant la logique de collecte de données d’AppMeasurement avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), car les deux méthodes effectuent la même tâche.

Voici les avantages et les inconvénients de cette alternative de mise à niveau :

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise la logique de couche de données active** : cette méthode utilise la logique de couche de données active à la place d’une implémentation de Web SDK conventionnelle. Bien que cette approche nécessite une configuration, elle ne nécessite pas une implémentation entièrement nouvelle à partir de zéro et elle ne nécessite aucun remplissage d’éléments de données ou de règles de balises. Il vous permet de mapper les données de la couche de données à XDM, plutôt que de renseigner entièrement un objet XDM.</li></ul> | <ul><li>**Nécessite un mappage pour envoyer des données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. <p>Comme cette option vous permet de placer l’intégralité de votre couche de données côté client dans l’objet de données et de l’envoyer à Adobe, vous obtenez une quantité importante de données qu’Adobe ne peut pas interpréter facilement. Pour permettre à Adobe d’interpréter les données, vous devez utiliser le mappage de flux de données pour mapper chaque champ individuel au champ XDM souhaité.</p></li><li>**Implémentation rigide** : l’implémentation est limitée à ce que la couche de données fournit au moment de l’envoi de l’accès. Cela pourrait être acceptable pour les organisations ayant des besoins de données de base, mais la plupart des organisations devraient éviter ce type d’implémentation rigide au profit d’une implémentation plus flexible qui permet de renseigner les éléments de données.</li><li>**Les modifications futures sont plus difficiles à implémenter** : tout champ que vous ajoutez ultérieurement à vos données doit être mappé à XDM dans le flux de données.</li></ul> |

{style="table-layout:auto"}

## Étapes de base

Les étapes de base pour envoyer l’intégralité de la couche de données à Customer Journey Analytics sont les suivantes :

1. Configurez votre implémentation pour envoyer des données à Adobe au moment souhaité et configurez la payload JSON pour qu’elle constitue votre couche de données dans son intégralité.

1. Mappez chaque élément de couche de données au champ XDM souhaité.

   Tous les éléments de couche de données qui ne sont pas mappés à un champ XDM sont définitivement supprimés, car Adobe ne sait pas où ni comment stocker ces données.
