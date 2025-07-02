---
title: Évolution À Partir D’Adobe Analytics
description: Étapes de transformation des données Adobe Analytics en données Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 4dcf9ab808475cc3cc48cab4c076b6c3cfb66f8a
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 79%

---

# Évolution à partir d’Adobe Analytics

## Préparer vos données existantes

La préparation de vos données Adobe Analytics pour une migration fluide vers Customer Journey Analytics est essentielle pour conserver l’intégrité des données et la cohérence des rapports.

### Collecter les identités

La chose la plus importante pour comprendre un parcours client est de savoir qui est le client ou la cliente à chaque étape. Pour Customer Journey Analytics, disposer d’un identifiant qui existe sur tous vos canaux et des données correspondantes permet de regrouper plusieurs sources dans Customer Journey Analytics.
Il peut s’agir d’un identifiant de client, d’un identifiant de compte ou d’un identifiant d’e-mail. Quelle que soit l’identité (et il peut y en avoir plusieurs), veillez à tenir compte des points suivants pour chaque identifiant :

* L’identifiant existe ou peut être ajouté à toutes les sources de données que vous souhaitez importer dans Customer Journey Analytics
* L’identifiant est renseigné sur chaque ligne de données.
* L’identifiant ne contient pas de PII. Appliquez le hachage à tout ce qui peut être sensible.
* L’identifiant utilise le même format pour toutes les sources (même longueur, même méthode de hachage, etc.).

Dans des jeux de données tels qu’Adobe Analytics, une identité peut ne pas exister sur chaque ligne de données, mais une identité secondaire existe alors. Dans ce cas, l’analyse cross-canal [ (également appelée assemblage)](/help/stitching/overview.md) peut être utilisée pour combler l’écart entre les lignes lorsqu’un client n’est identifié que par son ECID et lorsqu’une identité est collectée (par exemple lorsqu’un client s’authentifie).

### Aligner vos variables

La méthode la plus simple pour transformer les données Adobe Analytics en données Customer Journey Analytics consiste à ingérer une [suite de rapports globale](https://experienceleague.adobe.com/fr/docs/analytics/implementation/prepare/global-rs) dans Experience Platform à l’aide du [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics?lang=fr). Ce connecteur mappe directement vos variables Adobe Analytics à un jeu de données et à un schéma XDM dans Experience Platform, qui peuvent à leur tour être facilement connectés à Customer Journey Analytics.

Une suite de rapports globale complète peut ne pas toujours être faisable pour une implémentation. Si vous prévoyez d’importer plusieurs suites de rapports dans Customer Journey Analytics, deux options s’offrent à vous :

* Planifiez pour aligner les variables sur ces suites de rapports. Par exemple, l’eVar1 de la suite de rapports 1 peut pointer vers [!UICONTROL Page]. Dans la suite de rapports 2, l’eVar1 peut pointer vers [!UICONTROL Campagne interne]. Lorsqu’elles sont importées dans Customer Journey Analytics, ces variables se mélangent dans une seule dimension eVar1, ce qui peut entraîner des rapports potentiellement déroutants et inexacts.

* Utilisez la fonctionnalité [Préparation des données](https://experienceleague.adobe.com/fr/docs/experience-platform/data-prep/home) pour mapper des variables. Bien qu’il soit plus facile d’avoir des suites de rapports avec les mêmes variables, ce n’est pas nécessaire si vous utilisez la nouvelle fonctionnalité [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics?lang=fr) d’Experience Platform. Vous pouvez ainsi référencer une variable par sa valeur mappée, qui se situe au niveau du flux de données (ou de la propriété).

Si vous avez évité de passer à une suite de rapports globale en raison de problèmes liés à des [!UICONTROL Valeurs uniques dépassées] ou à un [!UICONTROL Faible trafic], sachez que Customer Journey Analytics n’a pas de [limites de cardinalité sur une dimension](/help/components/dimensions/high-cardinality.md). Cela permet à n’importe quelle valeur unique d’apparaître et d’être comptabilisée.

Voici un cas pratique portant sur la [combinaison de suites de rapports avec des schémas différents](/help/use-cases/aa-data/combine-report-suites.md).

### (Re)configurer vos canaux marketing

Les paramètres traditionnels du canal marketing Adobe Analytics ne s’exécutent pas de la même manière dans Customer Journey Analytics. Il existe une différence pour deux raisons :

* D’une part, le niveau de traitement des données Adobe Analytics ingérées dans Adobe Experience Platform.

* D’autre part, la nature de Customer Journey Analytics en matière de période des rapports.

Adobe a publié une [mise à jour des bonnes pratiques relatives à l’implémentation des canaux marketing](https://experienceleague.adobe.com/fr/docs/analytics/components/marketing-channels/mchannel-best-practices). Ces recommandations mises à jour vous aident à tirer le meilleur parti des fonctionnalités déjà présentes dans Adobe Analytics avec des fonctionnalités d’attribution avancées. Les recommandations vous permettent également de réussir la transition vers Customer Journey Analytics.

Avec l’introduction de [Champs dérivés](../data-views/derived-fields/derived-fields.md) dans le cadre des vues de données de Customer Journey Analytics, les canaux marketing sont également pris en charge de manière non destructive et rétroactive à l’aide du [Modèle de fonction Canal marketing](../data-views/derived-fields/derived-fields.md#function-templates).

## Se préparer aux différences critiques lors de la migration vers Customer Journey Analytics

Tandis que votre organisation utilise peu à peu Customer Journey Analytics, voici quelques étapes pour préparer au mieux vos données et prendre conscience des différences majeures entre les deux technologies. Cet article s’adresse aux administrateurs.

### Compréhension du traitement de la période de rapport {#report-time}

Dans Adobe Analytics, le compte rendu des performances sʼappuie sur une quantité importante de prétraitement des données pour générer des résultats tels que la persistance que vous voyez dans les [!UICONTROL eVars]. En revanche, Customer Journey Analytics effectue ces calculs au moment de l’exécution du rapport.

Le [!UICONTROL Traitement de la période de rapport] offre la possibilité d’appliquer des paramètres rétroactifs et de créer plusieurs versions de la persistance des variables, sans avoir besoin de modifier la façon dont les données sous-jacentes sont collectées.

Ce changement entraîne certaines différences dans la manière dont les données sont rapportées, en particulier pour les variables qui peuvent avoir une longue période d’expiration. Vous pouvez commencer par évaluer la manière dont le traitement de la période de rapport peut avoir un impact sur le compte rendu des performances à l’aide d’une [suite de rapports virtuelle](https://experienceleague.adobe.com/fr/docs/analytics/components/virtual-report-suites/vrs-report-time-processing).

### Identifier les segments et mesures calculées importants {#segments-calcmetrics}

Les mesures calculées et les segments Adobe Analytics ne sont pas compatibles avec Customer Journey Analytics. Dans de nombreux cas, ces composants peuvent être reconstruits dans Customer Journey Analytics à l’aide des nouveaux schémas et données disponibles.

Pour que la migration entre les deux systèmes se passe le mieux possible pour les utilisateurs, effectuez au préalable les actions suivantes :

1. Identifiez les composants les plus importants.

2. Documentez leurs définitions et

3. Identifier les champs requis dans les données pour les répliquer dans Customer Journey Analytics en tant que [Segments](/help/components/segments/seg-overview.md) et [Mesures calculées](/help/components/calc-metrics/calc-metr-overview.md).

Regardez ces deux vidéos pour obtenir plus dʼinformations :

* [Déplacer des segments Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=fr)

* [Déplacer vos mesures calculées d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics)

### Autres considérations

* Grâce à la puissance des vues de données Customer Journey Analytics, vous disposez de beaucoup plus de flexibilité dans la définition des mesures et dimensions au sein de Customer Journey Analytics. Par exemple, la valeur d’une dimension peut devenir la définition dʼune mesure. [En savoir plus](/help/use-cases/data-views/data-views-usecases.md)

* Si vous avez défini un calendrier personnalisé dans Adobe Analytics, vous disposez de fonctionnalités similaires [calendrier personnalisé](/help/components/date-ranges/overview.md) dans Customer Journey Analytics. Vous devez vous assurer que votre calendrier est correctement défini.

* Dans Customer Journey Analytics, vous pouvez définir un délai d’expiration de session personnalisé, ainsi qu’une mesure qui démarrera une nouvelle session. Vous pouvez créer des vues de données avec différentes définitions de session, et ainsi obtenir des informations dʼune pertinence que nʼoffrait pas Adobe Analytics. Cette fonctionnalité peut être particulièrement utile pour les jeux de données mobiles.

* Pensez à fournir un dictionnaire de données à vos utilisateurs. Vous pouvez également étendre la SDR pour inclure le nom du champ Experience Platform pour les éléments de schéma.

### Étapes suivantes

Si vous constatez des écarts de données une fois la migration vers Customer Journey Analytics effectuée, vous pouvez comparer vos données Adobe Analytics dʼorigine avec les données Adobe Analytics qui se trouvent maintenant dans Customer Journey Analytics. [En savoir plus](/help/troubleshooting/compare.md)
