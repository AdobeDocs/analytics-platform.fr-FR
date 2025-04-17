---
title: Évaluer la durée de conservation nécessaire d’Adobe Analytics après la mise à niveau vers Customer Journey Analytics
description: Découvrir comment évaluer la durée de conservation nécessaire d’Adobe Analytics après la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# Déterminer quand désactiver Adobe Analytics après la mise à niveau vers Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Passer entièrement à Customer Journey Analytics"
>abstract="(Recommandé) Adobe vous recommande d’effectuer une transition complète d’Adobe Analytics vers Customer Journey Analytics. Pendant la période de transition, vous devez prévoir d’exécuter Adobe Analytics avec Customer Journey Analytics afin d’effectuer des comparaisons de données côte à côte. Lorsque les données vous conviennent, vous pouvez désactiver Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Conserver les deux produits d’analyse"
>abstract="(Non recommandé) Si vous sélectionnez cette option, votre contrat avec Adobe comprend à la fois Adobe Analytics et Customer Journey Analytics, ce qui peut s’avérer plus coûteux pour votre entreprise au fil du temps."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Désactivez le connecteur source Analytics pour utiliser les données exclusivement à partir du SDK Web."
>abstract="Le connecteur source Analytics permet de fournir une comparaison côte à côte des données, des données historiques et l’accès à certaines fonctionnalités qui ne sont pas entièrement disponibles dans Customer Journey Analytics. Lorsque vous n’avez plus besoin d’Adobe Analytics à ces fins, vous pouvez désactiver le connecteur source Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La plupart des entreprises finiront par désactiver Adobe Analytics après la mise à niveau vers Customer Journey Analytics. Cela est dû au coût et à la complexité de la maintenance de deux environnements d’analyse.

Cependant, Adobe vous recommande de conserver votre environnement Adobe Analytics en cours d’exécution pendant un certain temps après l’implémentation de Customer Journey Analytics. Les sections suivantes décrivent les raisons de ce choix ainsi que le moment suggéré pour désactiver d’Adobe Analytics.

## Utilisations d’Adobe Analytics pendant et après une mise à niveau

Lorsque vous décidez si et quand votre organisation doit désactiver Adobe Analytics, tenez compte des utilisations suivantes d’Adobe Analytics pendant et après une mise à niveau vers Customer Journey Analytics :

| Utilisations d’Adobe Analytics pendant et après la mise à niveau | Explication |
|---------|----------|
| Effectuer une comparaison des données côte à côte | Adobe vous recommande de conserver votre environnement Adobe Analytics en cours d’exécution pendant un certain temps après l’exécution de votre nouvel environnement Customer Journey Analytics et lde sa collecte de données. Il s’agit de la meilleure manière de comparer vos données Customer Journey Analytics côte à côte avec vos données Adobe Analytics.<p>Ne désactivez pas Adobe Analytics tant que vous n’êtes pas à l’aise avec les données de votre environnement Customer Journey Analytics.</p><p>**Note :** Adobe recommande une nouvelle implémentation du SDK web pour votre environnement Customer Journey Analytics, conjointement avec le connecteur source Analytics pour les données historiques. [En savoir plus](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Conserver les données historiques depuis Adobe Analytics | Adobe vous recommande de conserver votre environnement Adobe Analytics en place avec le connecteur source Analytics pendant un certain temps après l’exécution de votre nouvel environnement Customer Journey Analytics et de sa collecte de données. Il s’agit de la meilleure façon d’importer des données Adobe Analytics historiques dans Customer Journey Analytics.<p>Après avoir collecté suffisamment de données historiques dans Customer Journey Analytics avec votre nouvelle implémentation du SDK web, vous pouvez supprimer entièrement le connecteur source Analytics. Effectuez cette opération lorsque vous ne pouvez vous fier qu’aux données historiques que vous avez collectées avec la nouvelle implémentation du SDK web Customer Journey Analytics.</p><p>**Note :** Adobe recommande une nouvelle implémentation du SDK web pour votre environnement Customer Journey Analytics, conjointement avec le connecteur source Analytics pour les données historiques. [En savoir plus](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Utiliser les flux de données ou d’autres fonctionnalités Adobe Analytics | Un petit nombre de fonctionnalités ne sont pas encore entièrement disponibles dans Customer Journey Analytics. Si vous avez besoin d’accéder à ces fonctionnalités, il peut être nécessaire d’utiliser Adobe Analytics conjointement avec Customer Journey Analytics jusqu’à ce que ces fonctionnalités soient disponibles. <p>Les fonctionnalités qui ne sont pas entièrement disponibles dans Customer Journey Analytics incluent les flux de données et l’analyse des contributions. Pour obtenir la liste complète des fonctionnalités qui ne sont pas encore disponibles, consultez [Prise en charge des fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Processus et calendrier de désactivation d’Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Désactiver un système de gestion des balises tiers"
>abstract="Une fois les données du SDK web entièrement fonctionnelles, contactez votre administrateur ou administratrice des balises pour supprimer la bibliothèque AppMeasurement de votre système de gestion des balises tiers.<br><br>Le temps estimé nécessaire à l’exécution de cette étape dépend de la facilité de désactivation d’AppMeasurement à partir de votre produit de gestion des balises, ainsi que du cycle de publication utilisé par votre entreprise pour déployer et gérer le code de balise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Désactiver l’extension Analytics dans les balises"
>abstract="Une fois les données du SDK Web entièrement fonctionnelles, demandez à votre administrateur ou administratrice de balises de supprimer l’extension Adobe Analytics de la propriété de balise. Avant de procéder, assurez-vous que vos utilisateurs et utilisatrices ont effectué une transition, d’Adobe Analytics vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Désactiver la collecte de données de l’API pour Adobe Analytics"
>abstract="Une fois les données du SDK Web entièrement fonctionnelles, travaillez avec l’équipe d’ingénierie concernée pour supprimer le code Adobe Analytics du projet. Avant de procéder, assurez-vous que vos utilisateurs et utilisatrices ont effectué une transition, d’Adobe Analytics vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Votre implémentation d’Adobe Analytics existante est un élément essentiel pour réussir la mise à niveau vers Customer Journey Analytics, comme décrit dans la section ci-dessus, [Utilisations d’Adobe Analytics pendant et après une mise à niveau](#uses-of-adobe-analytics-during-and-after-an-upgrade).

Lorsque vous n’avez plus besoin d’Adobe Analytics aux fins décrites dans la section ci-dessus, utilisez les informations suivantes pour supprimer Adobe Analytics :

1. Arrêtez de collecter des données avec Adobe Analytics.

   Une fois que les comparaisons côte à côte de vos données Adobe Analytics et de vos données Customer Journey Analytics vous satisfont, vous pouvez arrêter la collecte de données avec votre implémentation Adobe Analytics. Les nouvelles données Adobe Analytics ne seront plus transmises à Customer Journey Analytics par le biais du connecteur source Analytics.

   Toutefois, les données que vous avez collectées auparavant dans votre environnement Adobe Analytics sont toujours disponibles en tant que données historiques dans Customer Journey Analytics via le connecteur source Analytics.

   Ce processus varie en fonction de la méthode de collecte de données utilisée pour implémenter Adobe Analytics :

+++ AppMeasurement

   [Désactivez la collecte de données d’AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Extension Analytics (Balises)

   Désactivez l’extension Analytics dans les balises.

+++

+++ API

   Désactivez la collecte de données d’API.

+++

+++ Troisième niveau

   Contactez votre administrateur ou administratrice de balises pour supprimer la bibliothèque AppMeasurement de votre système de gestion des balises tiers.

+++

1. Supprimez Adobe Analytics en tant que service du train de données.

   Lorsque les données du SDK web sont entièrement fonctionnelles, contactez votre administrateur ou administratrice Platform pour supprimer Adobe Analytics en tant que service du train de données.

   Avant de supprimer Adobe Analytics en tant que service, assurez-vous que vos utilisateurs et utilisatrices Analytics utilisent Customer Journey Analytics et non Adobe Analytics.

1. Supprimez entièrement le connecteur source Analytics.

   Après avoir collecté suffisamment de données historiques dans Customer Journey Analytics avec votre nouvelle implémentation du SDK web, vous pouvez supprimer entièrement le connecteur source Analytics.

   Effectuez cette opération lorsque vous n’avez plus besoin des données historiques de votre environnement Adobe Analytics via le connecteur source Analytics et que vous pouvez vous fier uniquement aux données historiques collectées avec la nouvelle implémentation du SDK web.

{{upgrade-final-step}}

