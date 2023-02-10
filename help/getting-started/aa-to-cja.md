---
title: Evolution à partir d’Adobe Analytics
description: Étapes de transformation des données Adobe Analytics en données Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: tm+mt
source-wordcount: '1414'
ht-degree: 99%

---

# Evolution à partir d’Adobe Analytics

Tandis que votre organisation utilise peu à peu Customer Journey Analytics, voici quelques étapes pour préparer au mieux vos données et prendre conscience des différences majeures entre les deux technologies. Cet article s’adresse aux administrateurs.

## Préparation de vos données

La préparation de vos données Adobe Analytics pour une migration fluide vers Customer Journey Analytics est essentielle pour conserver l’intégrité des données et la cohérence des rapports.

### 1. Collecte des identités {#identities}

La chose la plus importante pour comprendre un parcours client est de savoir qui est le client à chaque étape. Pour Customer Journey Analytics, disposer d’un identifiant qui existe sur tous vos canaux et des données correspondantes permet de regrouper plusieurs sources dans CJA.
Il peut s’agir d’un identifiant de client, d’un identifiant de compte ou d’un identifiant d’e-mail. Quelle que soit l’identité (et il peut y en avoir plusieurs), veillez à tenir compte des points suivants pour chaque identifiant :

* L’identifiant existe ou peut être ajouté à toutes les sources de données que vous souhaitez importer dans CJA.
* L’identifiant est renseigné sur chaque ligne de données.
* L’identifiant ne contient pas de PII. Appliquez le hachage à tout ce qui peut être sensible.
* L’identifiant utilise le même format pour toutes les sources (même longueur, même méthode de hachage, etc.).

Dans des jeux de données tels qu’Adobe Analytics, une identité peut ne pas exister sur chaque ligne de données, mais une identité secondaire existe alors. Dans ce cas, Cross-Channel Analytics (anciennement appelée « Assemblage basé sur les champs ») peut être utilisée pour combler l’écart entre les lignes lorsqu’un client n’est identifié que par son ECID et lorsqu’une identité est collectée (par exemple lorsqu’un client s’authentifie). [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=fr)

### 2. Alignement de vos variables {#variables}

La méthode la plus simple pour transformer les données Adobe Analytics en données Customer Journey Analytics consiste à ingérer une [suite de rapports globale](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=fr) dans Experience Platform à l’aide du [connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr). Ce connecteur mappe directement vos variables Adobe Analytics à un jeu de données et à un schéma XDM dans Experience Platform, qui peuvent à leur tour être facilement connectés à Customer Journey Analytics.

Une suite de rapports globale complète peut ne pas toujours être faisable pour une implémentation. Si vous prévoyez d’importer plusieurs suites de rapports dans Customer Journey Analytics, deux options s’offrent à vous :

* Planifiez pour aligner les variables sur ces suites de rapports. Par exemple, l’eVar1 de la suite de rapports 1 peut pointer vers [!UICONTROL Page]. Dans la suite de rapports 2, l’eVar1 peut pointer vers [!UICONTROL Campagne interne]. Lorsqu’elles sont importées dans CJA, ces variables se combinent en une seule dimension eVar1, ce qui peut entraîner des rapports potentiellement déroutants et inexacts.

* Utilisez la fonctionnalité [Préparation des données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) pour mapper des variables. Bien qu’il soit plus facile d’avoir des suites de rapports avec les mêmes variables, ce n’est pas nécessaire si vous utilisez la nouvelle fonctionnalité [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr#mapping) d’Experience Platform. Elle vous permet de référencer une variable par sa valeur mappée, qui se situe au niveau du flux de données (ou de la propriété).

Si vous avez évité de passer à une suite de rapports globale en raison de problèmes liés à des [!UICONTROL Valeurs uniques dépassées] ou à un [!UICONTROL Faible trafic], sachez que CJA n’a pas de [limites de cardinalité sur une dimension](/help/components/dimensions/high-cardinality.md). Cela permet à n’importe quelle valeur unique d’apparaître et d’être comptabilisée.

Voici un cas pratique portant sur la [combinaison de suites de rapports avec des schémas différents](/help/use-cases/aa-data/combine-report-suites.md).

### 3.  (Re)configuration de vos canaux marketing {#marketing-channels}

Les paramètres traditionnels du canal marketing Adobe Analytics ne s’exécutent pas de la même manière dans CJA. Il y a deux raisons à cela :

* D’une part, le niveau de traitement des données Adobe Analytics ingérées dans Adobe Experience Platform.

* D’autre part, la nature de Customer Journey Analytics en matière de période des rapports.

Adobe a publié une [mise à jour des bonnes pratiques relatives à l’implémentation des canaux marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=fr). Ces recommandations mises à jour vous aident à tirer le meilleur parti des fonctionnalités déjà présentes dans Adobe Analytics avec Attribution IQ. Elles vous permettront également de réussir la transition vers Customer Journey Analytics.

### 4. Choix d’utilisation du connecteur source Analytics ou des SDK Experience Platform {#connector-vs-sdk}

Les client(e)s Adobe Analytics peuvent facilement exploiter leurs suites de rapports dans Adobe Experience Platform et Customer Journey Analytics à l’aide du connecteur source Analytics. Pour plus d’informations sur l’utilisation du connecteur source Analytics, voir [Création d’une connexion source Adobe Analytics dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr).

La collecte des données [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) évoluant, il est probable que vous migriez vers le [SDK web Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr) ou le [SDK mobile Adobe Experience Platform](https://experienceleague.adobe.com/docs/mobile.html?lang=fr) avec Adobe Experience Platform Edge Network. Bien qu’une implémentation standard des SDK envoie des données dans Adobe Analytics, une nouvelle opportunité s’affiche pour envoyer des données directement à Adobe Experience Platform. Il peut ensuite être ingéré dans Customer Journey Analytics, tout en conservant les données envoyées à Adobe Analytics.

Cette méthode élargit considérablement les possibilités de collecte de données : il n’y a plus de limitation du nombre de champs ni de nécessité de mapper les éléments de données aux props, eVars et événements comme dans Analytics. Vous pouvez utiliser un nombre illimité d’éléments de schéma de différents types et les représenter de différentes manières à l’aide des [Vues des données](/help/data-views/data-views.md) de CJA. Les données sont accessibles plus rapidement lorsqu’elles sont envoyées directement à Adobe Experience Platform, car le temps de traitement des données par Adobe Analytics est supprimé.

**Avantages de l’utilisation des SDK Experience Platform :**

* Schéma flexible permettant de définir tous les champs dont vous avez besoin
* Ne dépend pas de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)
* Pas de problème de limite de caractères (100 caractères pour les props)
* Disponibilité plus rapide des données dans Adobe Experience Platform pour alimenter [les cas d’utilisation de la personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr).
* [Identifiants d’appareils propriétaires](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=fr) pour une meilleure précision de l’identification des visiteurs

**Inconvénients de l’utilisation des SDK Experience Platform**

Les fonctionnalités ou composants Adobe Analytics suivants ne sont pas pris en charge :

* Canaux marketing
* Filtrage des robots
* Recherches géographiques, de domaines et dʼappareils
* Analytics for Target (A4T)

## Survenue de différences majeures

### Compréhension du traitement de la période de rapport {#report-time}

Dans Adobe Analytics, le compte rendu des performances sʼappuie sur une quantité importante de prétraitement des données pour générer des résultats tels que la persistance que vous voyez dans les [!UICONTROL eVars]. En revanche, Customer Journey Analytics effectue ces calculs au moment de l’exécution du rapport.

Le [!UICONTROL Traitement de la période de rapport] offre la possibilité d’appliquer des paramètres rétroactifs et de créer plusieurs versions de la persistance des variables, sans avoir besoin de modifier la façon dont les données sous-jacentes sont collectées.

Ce changement entraînera quelques différences dans la façon dont les données sont rapportées, en particulier pour les variables qui peuvent avoir une longue période d’expiration. Vous pouvez commencer par évaluer la manière dont le traitement de la période de rapport peut avoir un impact sur le compte rendu des performances à l’aide d’une [suite de rapports virtuelle](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=fr).

### Identifier les segments et mesures calculées importants {#segments-calcmetrics}

Les segments Adobe Analytics (appelés [!UICONTROL filtres] dans CJA) et les mesures calculées ne sont pas compatibles avec Customer Journey Analytics. Dans de nombreux cas, ces composants peuvent être reconstruits dans CJA à l’aide des nouveaux schémas et données disponibles.

Pour que la migration entre les deux systèmes se passe le mieux possible pour les utilisateurs, effectuez au préalable les actions suivantes :

1. Identifiez les composants les plus importants.

2. Documentez leurs définitions et

3. identifiez les champs qui seront nécessaires dans les données afin de les répliquer dans CJA en tant que [Filtres](/help/components/filters/filters-overview.md) et [Mesures calculées](/help/components/calc-metrics/calc-metr-overview.md).

Regardez ces deux vidéos pour obtenir plus dʼinformations :

* [Déplacer des segments Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=fr)

* [Déplacer vos mesures calculées d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=fr)

### Autres considérations

* Grâce à la puissance des vues de données CJA, vous disposez de beaucoup plus de flexibilité dans la définition des mesures et dimensions au sein de Customer Journey Analytics. Par exemple, la valeur d’une dimension peut devenir la définition dʼune mesure. [En savoir plus](/help/use-cases/data-views/data-views-usecases.md)

* Si vous avez défini un calendrier personnalisé dans Adobe Analytics, vous disposerez de [fonctionnalités propres au calendrier personnalisé](/help/components/date-ranges/custom-date-ranges.md) similaires dans CJA. Vous devez vous assurer que votre calendrier est correctement défini.

* Dans Customer Journey Analytics, vous pouvez définir un délai de visite/session personnalisé, ainsi qu’une mesure qui démarrera une nouvelle session. Vous pouvez créer des vues de données avec différentes définitions de session, et ainsi obtenir des informations dʼune pertinence que nʼoffrait pas Adobe Analytics. Cette fonctionnalité peut être particulièrement utile pour les jeux de données mobiles.

* Prévoyez un dictionnaire de données pour vos utilisateurs ou étendez le SDR afin d’inclure le nom du champ Experience Platform pour les éléments de schéma.

## Étapes suivantes

Si vous constatez des écarts de données une fois la migration vers CJA effectuée, vous pouvez comparer vos données Adobe Analytics dʼorigine avec les données Adobe Analytics qui se trouvent maintenant dans Customer Journey Analytics. [En savoir plus](/help/troubleshooting/compare.md)
