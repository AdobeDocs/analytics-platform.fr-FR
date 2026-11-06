---
description: Découvrez comment comparer les fonctionnalités des flux de données dans Customer Journey Analytics et Adobe Analytics
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Fonctionnalité Comparaison des flux de données dans Customer Journey Analytics et Adobe Analytics
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# Comprendre les écarts de données entre les flux de données et Analysis Workspace

{{release-limited-testing}}

Les données d’une exportation de flux de données ne correspondent pas toujours exactement aux données affichées dans Analysis Workspace. Les informations de cette page en expliquent quelques-unes des principales raisons.

Certaines de ces différences proviennent des comportements Workspace qui sont difficiles à voir dans les rapports Workspace seuls, car les données Workspace sont agrégées. Les flux de données diffusent des données au niveau de l’événement. Ces comportements sont donc évidents lorsque vous comparez la sortie des flux de données aux rapports Workspace.

## Fenêtre de traitement (Flux de données) ou fenêtre de création de rapports (Analysis Workspace) {#processing-window}

Chaque diffusion de flux de données utilise une fenêtre dynamique de traitement de 30 jours. La fenêtre de traitement fournit le contexte historique nécessaire pour classer les événements dans une diffusion de flux de données. Pour plus d’informations sur la fenêtre de traitement, y compris des exemples, voir [Présentation de la fenêtre de traitement](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

En ce sens, la fenêtre de traitement est similaire à la fenêtre de création de rapports dans Analysis Workspace (la période que vous choisissez pour un rapport). Cependant, il existe des différences majeures.

| Principales différences | Créneau de reporting (Analysis Workspace) | Fenêtre de traitement (Flux de données) |
|---------|---------|----------|
| **Période pour la création de rapports**<br/> Quels événements sont inclus dans un rapport ou un flux ? | Commence le premier jour du mois calendaire au cours duquel le créneau de reporting démarre et se termine à la fin du créneau de reporting.<p>Par exemple, un rapport avec une période de création de rapports allant du 6 octobre au 5 novembre inclut également les événements allant du 1er octobre au 5 octobre. Comme les données Workspace sont agrégées, ces événements supplémentaires peuvent être difficiles à remarquer.</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | Différent de la fenêtre de traitement. <p>La période pour laquelle créer des rapports est la fenêtre de fréquence, qui peut être une heure ou un jour à la fin de la fenêtre de traitement.</p> |
| **Limite des données**<br/> si les données en dehors de la fenêtre sont incluses ou influencent un rapport ou un flux | Flexible<p>Les événements qui surviennent à partir du premier jour du mois calendaire au cours duquel la période de création des rapports commence sont inclus dans un rapport Workspace, même s’ils se situent avant cette période. Pour plus d’informations, voir **Période pour la création de rapports** ci-dessus.</p><p>Les événements qui se produisent en dehors de la fenêtre de création de rapports peuvent également influencer les données d’un rapport Workspace par l’un des facteurs suivants :</p><ul><li>**Persistance Dimension** : peut persister au-delà de la fenêtre de création de rapports lors de l’utilisation de l’expiration Session, Heure personnalisée ou Mesure [expiration](/help/data-views/component-settings/persistence.md#expiration-settings).</li><li>**Qualification du segment** : par défaut, les segments peuvent s’étendre au-delà de la fenêtre de création de rapports.<p>Les utilisateurs peuvent choisir de limiter le segment à la fenêtre de création de rapports lorsqu’ils créent le segment. Même dans ce cas, la qualification du segment prend en compte les événements à partir du premier jour du mois calendaire au cours duquel la période de création de rapports commence.</p></li><li>**Calcul de session** : les sessions peuvent s’étendre au-delà de la fenêtre de compte rendu des performances. </li><li>**Transformations de champ dérivé** : toutes les fonctions de champ dérivé qui font référence à des conteneurs utilisent la fenêtre de création de rapports<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.-->.</li></ul> | Fixe<p>Seuls les événements de la fenêtre de fréquence sont inclus dans un flux de données. Pour plus d’informations, voir **Période pour la création de rapports** ci-dessus.</p><p>Les événements qui se produisent en dehors de la fenêtre de fréquence, mais dans la fenêtre de traitement, peuvent influencer les données d’un flux de données. Les événements qui se trouvent avant la fenêtre de traitement ne le peuvent généralement pas. La fenêtre de traitement limite les facteurs suivants :</p><ul><li>**Persistance Dimension** : impossible de persister au-delà de la fenêtre de traitement lors de l’utilisation de la session, de la fenêtre de rapport de personne ou de la mesure [expiration](/help/data-views/component-settings/persistence.md#expiration-settings). Contrairement à Workspace, la recherche en amont ne s’étend pas jusqu’au premier jour du mois. Peut persister au-delà de la fenêtre de traitement (jusqu’à 90 jours) lors de l’utilisation de l’Heure personnalisée [expiration](/help/data-views/component-settings/persistence.md#expiration-settings), comme dans Workspace. Dans Workspace et les flux de données, la recherche en amont de l’heure personnalisée ne s’étend pas jusqu’au premier jour du mois.<p>**Remarque :** actuellement, l’expiration du temps personnalisé est également limitée à la fenêtre de traitement. La prise en charge des délais personnalisés qui s’étendent au-delà de la fenêtre de traitement sera bientôt disponible.</p></li><li>**Qualification du segment** : toujours limitée à la fenêtre de traitement. Contrairement à Workspace, ne s’étend pas jusqu’au premier jour du mois.</li><li>**Calcul de session** : toujours limité à la fenêtre de traitement.</li><li>**Transformations de champ dérivé** : toutes les fonctions de champ dérivé qui font référence à des conteneurs utilisent la fenêtre de traitement dans les exportations de flux de données.</li></ul> |

>[!BEGINSHADEBOX]

**Exemple**

Les exemples ci-dessous illustrent comment les différences entre la fenêtre de création de rapports et la fenêtre de traitement peuvent entraîner des incohérences de données entre les rapports Workspace et les diffusions de flux de données.

* **Période pour laquelle créer un rapport** : un utilisateur dispose d’un événement le 1er octobre qui définit une valeur de dimension, ainsi que d’autres événements plus tard en octobre. Un rapport Workspace avec une fenêtre de création de rapports commençant le 6 octobre inclut l’événement du 1er octobre, car Workspace inclut les événements du premier jour du mois. La valeur définie le 1er octobre peut également persister pour les événements de l’utilisateur dans la fenêtre de création de rapports. Une diffusion de flux de données avec une fenêtre de traitement commençant le 6 octobre ne prend pas en compte l’événement du 1er octobre. Par conséquent, la valeur qu’elle a définie ne persiste pas pour les événements de l’utilisateur dans la diffusion.

* **Qualification du segment** : un utilisateur s’est qualifié pour un segment avec un conteneur Personne 45 jours auparavant et a un événement aujourd’hui. Un rapport Workspace avec une fenêtre de création de rapports de 30 jours inclut l’événement de l’utilisateur ou de l’utilisatrice, car les segments peuvent s’étendre au-delà de la fenêtre de création de rapports par défaut. La diffusion des flux de données pour aujourd’hui n’inclut pas l’événement, car la qualification du segment est limitée à la fenêtre de traitement de 30 jours.

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## Assemblage de relectures

Chaque fois qu’une relecture d’assemblage s’exécute, les données d’identité historiques sont mises à jour rétroactivement.

Les flux de données et Analysis Workspace traitent différemment l’assemblage des relectures, comme suit :

* **Flux de données** : reflète uniquement l’identité regroupée au moment de l’exportation. Les résultats de la relecture ne sont pas appliqués rétroactivement aux fichiers exportés.

* **&#x200B;**&#x200B;: affiche les données regroupées les plus récentes, mises à jour rétroactivement chaque fois qu’une relecture s’exécute. Les données historiques changent après chaque relecture, de sorte que Workspace reflète toujours la dernière résolution d’identité.

## Evénements en retard

Dans un flux de données, les événements peuvent arriver après la fermeture de la fenêtre d’exportation du flux de données.

Les flux de données et Analysis Workspace fonctionnent différemment concernant les événements passés, comme suit :

* **Flux de données** : exporte les données dans une fenêtre temporelle fixe (l’heure ou le jour de chaque diffusion), en fonction des horodatages d’événement.

  Avant de traiter chaque diffusion, Customer Journey Analytics attend le [délai de traitement](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) que vous avez choisi. Les événements qui arrivent pendant le délai de traitement sont inclus dans la diffusion. Les événements qui arrivent après le début du traitement ne sont pas inclus dans le fichier de flux de données.

* **&#x200B;**&#x200B;: traite les données au moment du rapport, de sorte que les événements soient inclus dans les rapports, quelle que soit la date de réception.

## Traitement par lots de données

Parfois, les données sont envoyées dans un lot qui s’étend sur une période prolongée.

Les flux de données et Analysis Workspace fonctionnent différemment concernant les données par lots, comme suit :

* **Flux de données** : distribue des données par lots sur chaque jour ou heure en fonction des horodatages d’origine. Par exemple, un lot contenant 30 jours de données est réparti sur 30 jours d’exportations. Par conséquent, une seule petite tranche apparaît dans une exportation unique.

* **&#x200B;**&#x200B;: affiche toutes les données d&#39;un lot dès qu&#39;elles sont entièrement traitées, quelle que soit la période incluse dans le lot.

