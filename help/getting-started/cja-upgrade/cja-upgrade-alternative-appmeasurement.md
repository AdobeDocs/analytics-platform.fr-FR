---
title: Autres méthodes lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez les autres méthodes disponibles lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 19%

---

# Alternative de mise à niveau : utilisez la collecte de données AppMeasurement avec Experience Platform Web SDK et Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Utilisation de la logique AppMeasurement avec le SDK Web"
>abstract="Au lieu d’envoyer des données par le biais d’un objet XDM, envoyez toutes vos variables au format AppMeasurement par le biais de l’objet de données.<br><br>Cette option permet de gagner du temps d’implémentation en vous permettant de mapper votre logique AppMeasurement à XDM, plutôt que de renseigner entièrement un objet XDM. Cependant, cela introduit une complexité supplémentaire au fil du temps, car tout champ que vous ajouterez ultérieurement doit être mappé à XDM dans le flux de données."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Lors de la mise à niveau vers Customer Journey Analytics, Adobe [recommande une nouvelle implémentation de la SDK Web Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Cependant, en fonction de plusieurs facteurs, tels que les contraintes de calendrier et de ressources, les étapes de mise à niveau recommandées peuvent ne pas être pratiques pour votre organisation.

Vous pouvez utiliser la logique de collecte de données de l’extension AppMeasurement ou Analytics avec le SDK Web afin d’envoyer des données à Platform et à Customer Journey Analytics, au lieu de collecter des données avec l’objet XDM. Cependant, cette alternative introduit une complexité supplémentaire au fil du temps.

## Avantages et inconvénients

Cette méthode s’exclut mutuellement lors de l’[envoi de l’intégralité de la couche de données à Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), car les deux méthodes effectuent la même tâche. (Cette méthode est préférable à l’envoi de l’ensemble de la couche de données à Adobe. Elle est plus précise, car les props et les evars passent tous par les données.__adobe.analytics._nom-variable_.)

Tenez compte des avantages et des inconvénients suivants de l’utilisation de cette alternative de mise à niveau :

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Non limité à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Il vous permet de mapper votre logique AppMeasurement à XDM, plutôt que de renseigner un objet XDM à partir de zéro.</li></ul> | <ul><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet de données soit une entrée dans l’outil de mappage de train de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li><li>**Ajoute une complexité supplémentaire au fil du temps** : tout champ que vous ajouterez ultérieurement doit être mappé à XDM dans le flux de données.<p>Chaque fois qu’un nouveau champ est ajouté à votre implémentation, vous pouvez effectuer l’une des opérations suivantes :</p><ul><li>**Option 1 :** renseignez une nouvelle evar arbitraire ou une nouvelle prop dans l’objet de données, puis mappez-la au champ XDM souhaité.<p>Ce processus améliore la cohérence de l’implémentation côté client, mais il nécessite un mappage.</p></li><li>**Option 2 :** laissez l’objet de données en tant qu’implémentation héritée et commencez à renseigner uniquement l’objet XDM pour tous les nouveaux champs.<p>Ce processus ne nécessite pas de mappage, mais cela signifie que certaines de vos variables sont situées uniquement dans un objet de données, tandis que d’autres variables sont situées uniquement dans un objet XDM. Chaque fois que vous devez résoudre les problèmes d’implémentation, vous devez accéder à deux emplacements. Veillez à ce que vos workflows internes prennent en charge cette fonctionnalité.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Étapes de base

Les étapes de base pour migrer une implémentation d’Adobe Analytics (AppMeasurement ou l’extension Analytics) pour utiliser le SDK Web afin d’envoyer des données à Customer Journey Analytics sont les suivantes :

1. (Facultatif) Migrez votre mise en œuvre Adobe Analytics pour utiliser le SDK web Adobe Experience Platform et commencer à envoyer des données à Edge Network.

   Il s’agit d’une étape facultative qui vous permet de migrer votre implémentation Adobe Analytics existante pour utiliser le SDK web et vérifier que tout fonctionne dans Adobe Analytics. Une fois cette configuration effectuée et les données dans Adobe Analytics satisfaisantes, vous pouvez envoyer des données d’Edge Network vers Customer Journey Analytics.

   Cette flexibilité permet une mise à niveau vers Customer Journey Analytics plus méthodique et réfléchie.

   Pour plus d’informations sur la procédure à suivre, consultez les articles suivants de la documentation d’Adobe Analytics :

   * [Migration vers Web SDK à l’aide de balises](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migration vers Web SDK à l’aide de JavaScript](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Envoyez des données d’Edge Network vers Customer Journey Analytics.

   1. Envoyez toutes vos variables au format AppMeasurement via l’objet de données.

      Pour plus d’informations, voir [Mappage des variables d’objet de données à Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Si ce n’est pas déjà fait, créez un schéma XDM pour votre organisation.

      Pour plus d’informations, voir [Création d’un schéma personnalisé à utiliser avec votre implémentation de Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Utilisez le mappage des flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.

      Pour plus d’informations, consultez [Mappage](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) dans [Préparation des données pour la collecte de données](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) dans la documentation d’Experience Platform.
