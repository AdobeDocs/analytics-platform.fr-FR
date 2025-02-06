---
title: Évaluer la durée pendant laquelle vous avez besoin d’Adobe Analytics après la mise à niveau vers Customer Journey Analytics
description: Découvrez comment évaluer la durée pendant laquelle Adobe Analytics est nécessaire après la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# Évaluer la durée pendant laquelle vous avez besoin d’Adobe Analytics après la mise à niveau vers Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Passer entièrement au Customer Journey Analytics"
>abstract="(Recommandé) Customer Journey Analytics vise à devenir le principal outil Analytics de votre entreprise. Cependant, votre organisation peut toujours avoir besoin d’Adobe Analytics si elle dépend fortement de fonctionnalités exclusives à l’outil et que ces workflows ne peuvent pas être modifiés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Conserver les deux produits d’analyse"
>abstract="(Non recommandé) Si vous sélectionnez cette option, votre contrat avec Adobe comprend à la fois Adobe Analytics et Customer Journey Analytics, ce qui peut s’avérer plus coûteux pour votre entreprise au fil du temps."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Cette documentation doit être utilisée dans le cadre du questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

La plupart des entreprises finissent par désactiver Adobe Analytics après la mise à niveau vers Customer Journey Analytics. Cela est dû au coût et à la complexité de la maintenance de deux environnements d’analyse.

Cependant, Adobe vous recommande de conserver votre environnement Adobe Analytics en cours d’exécution pendant un certain temps après l’implémentation de Customer Journey Analytics. Les sections suivantes décrivent les raisons de ce choix ainsi que la durée suggérée de désactivation d’Adobe Analytics.

## Utilisations d’Adobe Analytics pendant et après une mise à niveau

Lorsque vous décidez si et quand votre organisation doit désactiver Adobe Analytics, tenez compte des utilisations suivantes d’Adobe Analytics pendant et après une mise à niveau vers Customer Journey Analytics :

| Utilisations d’Adobe Analytics pendant et après la mise à niveau | Explication |
|---------|----------|
| Effectuer une comparaison des données côte à côte | Adobe vous recommande de conserver votre environnement Adobe Analytics en cours d’exécution pendant un certain temps après l’exécution de votre nouvel environnement de Customer Journey Analytics et la collecte de données. Il s’agit de la meilleure manière de comparer les données de votre Customer Journey Analytics côte à côte avec les données Adobe Analytics.<p>Ne désactivez pas Adobe Analytics tant que vous n’êtes pas à l’aise avec les données de votre environnement de Customer Journey Analytics.</p><p>**Remarque :** Adobe recommande une nouvelle implémentation de Web SDK pour votre environnement de Customer Journey Analytics, conjointement avec le connecteur source Analytics pour les données historiques. [En savoir plus](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Conserver les données historiques d’Adobe Analytics | Adobe vous recommande de conserver votre environnement Adobe Analytics en place avec le connecteur source Analytics pendant un certain temps après l’exécution de votre nouvel environnement de Customer Journey Analytics et la collecte de données. Il s’agit de la meilleure façon d’importer des données Adobe Analytics historiques dans Customer Journey Analytics.<p>Après avoir collecté suffisamment de données historiques en Customer Journey Analytics avec votre nouvelle implémentation de Web SDK, vous pouvez supprimer entièrement le connecteur source Analytics. Effectuez cette opération lorsque vous ne pouvez vous fier qu’aux données historiques que vous avez collectées avec la nouvelle implémentation de Customer Journey Analytics Web SDK.</p><p>**Remarque :** Adobe recommande une nouvelle implémentation de Web SDK pour votre environnement de Customer Journey Analytics, conjointement avec le connecteur source Analytics pour les données historiques. [En savoir plus](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Utilisation des flux de données ou d’autres fonctionnalités Adobe Analytics | Un petit ensemble de fonctionnalités ne sont pas encore entièrement disponibles en Customer Journey Analytics. Si vous avez besoin d’accéder à ces fonctionnalités, il peut être nécessaire d’utiliser Adobe Analytics conjointement avec Customer Journey Analytics jusqu’à ce que ces fonctionnalités soient disponibles. <p>Les fonctionnalités qui ne sont pas entièrement disponibles dans Customer Journey Analytics incluent les flux de données et l’analyse des contributions. Pour obtenir la liste complète des fonctionnalités qui ne sont pas encore disponibles, consultez [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Processus et calendrier de désactivation d’Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Désactivation d’un système de gestion des balises tiers"
>abstract="Une fois les données de Web SDK entièrement fonctionnelles, contactez votre administrateur des balises pour supprimer la bibliothèque d’AppMeasurement de votre système de gestion des balises tiers.<br><br>Le temps estimé nécessaire à l’exécution de cette étape dépend de la facilité de désactivation de l’AppMeasurement de votre produit de gestion des balises, ainsi que du cycle de publication utilisé par votre entreprise pour déployer et gérer le code de balise."

<!-- markdownlint-enable MD034 -->

Votre implémentation d’Adobe Analytics existante est essentielle pour réussir la mise à niveau vers Customer Journey Analytics, comme décrit dans la section ci-dessus, [Utilisations d’Adobe Analytics pendant et après une mise à niveau](#uses-of-adobe-analytics-during-and-after-an-upgrade).

Lorsque vous n’avez plus besoin d’Adobe Analytics aux fins décrites dans la section ci-dessus, utilisez les informations suivantes pour supprimer Adobe Analytics :

1. Arrêtez de collecter des données avec Adobe Analytics.

   Une fois que vous êtes satisfait(e) des comparaisons côte à côte des données Adobe Analytics et des données de votre Customer Journey Analytics, vous pouvez arrêter la collecte de données avec votre implémentation Adobe Analytics. Les nouvelles données Adobe Analytics ne seront plus transmises à Customer Journey Analytics par le biais du connecteur source Analytics.

   Toutefois, les données que vous avez collectées auparavant dans votre environnement Adobe Analytics sont toujours disponibles en tant que données historiques dans Customer Journey Analytics via le connecteur source Analytics.

   Ce processus varie en fonction de la méthode de collecte de données utilisée pour implémenter Adobe Analytics :

+++ AppMeasurement

   [Désactiver la collecte de données AppMeasurement ](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Extension Analytics (balises)

   Désactivez l’extension Analytics dans les balises.

+++

+++ API

   Désactivez la collecte de données API.

+++

+++ Troisième niveau

   Contactez votre administrateur de balises pour supprimer la bibliothèque d’AppMeasurement de votre système de gestion des balises tiers.

+++

1. Supprimez Adobe Analytics en tant que service du flux de données.

   Lorsque les données Web SDK sont entièrement fonctionnelles, contactez votre administrateur Platform pour supprimer Adobe Analytics en tant que service du flux de données.

   Avant de supprimer Adobe Analytics en tant que service, assurez-vous que vos utilisateurs Analytics utilisent Customer Journey Analytics et non Adobe Analytics.

1. Supprimez entièrement le connecteur source Analytics.

   Après avoir collecté suffisamment de données historiques en Customer Journey Analytics avec votre nouvelle implémentation de Web SDK, vous pouvez supprimer entièrement le connecteur source Analytics.

   Effectuez cette opération lorsque vous n’avez plus besoin des données historiques de votre environnement Adobe Analytics via le connecteur source Analytics et que vous ne pouvez vous fier qu’aux données historiques collectées avec la nouvelle mise en œuvre de Web SDK.

