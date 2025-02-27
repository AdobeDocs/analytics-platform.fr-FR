---
title: Choisir le schéma pour Customer Journey Analytics
description: Découvrez les options disponibles lors du choix d’un schéma pour Customer Journey Analytics ainsi que les avantages et les inconvénients de chacune d’elles
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 40%

---

# Choisir le schéma pour Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Utilisation d’un schéma personnalisé"
>abstract="(Recommandé) La personnalisation de votre schéma permet à votre entreprise de ne suivre que ce dont vous avez besoin et d’éviter les frais généraux liés à des champs désordonnés et inutiles. Cette option inclut les groupes de champs ajoutés par le Web SDK et les groupes de champs personnalisés pour votre organisation."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Utiliser le schéma par défaut"
>abstract="(Non recommandé) Le schéma Adobe Analytics contient plus d’un millier de champs, ce qui peut entraîner un schéma encombré et complexe. Votre entreprise serait forcée de continuer à adhérer au concept de props et d’eVars, qui est un concept hérité non utilisé dans Customer Journey Analytics. L’intégration à d’autres services Adobe Experience Platform est plus difficile."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Lors de la mise à niveau vers Customer Journey Analytics, Adobe recommande de créer un schéma de modèle de données d’expérience (XDM) personnalisé pour mieux s’aligner sur les besoins de votre entreprise lorsque vous commencez à utiliser d’autres services Platform. Vous pouvez également choisir d’utiliser votre schéma Adobe Analytics existant.

Tenez compte des avantages et des inconvénients de chacun.

## Créer un schéma personnalisé adapté à votre organisation (recommandé)

Adobe recommande de créer un schéma personnalisé lors de la mise à niveau vers Customer Journey Analytics.

| Avantages | Inconvénients |
|----------|---------|
| <ul><p>Les avantages de la mise à jour vers votre propre schéma personnalisé sont les suivants :</p><ul><li>Schéma rationalisé adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.</li><p>Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></ul> | <p>Les inconvénients de la mise à jour vers votre propre schéma personnalisé sont les suivants :</p><ul><li>La mise à jour de votre schéma est un processus long qui est nécessaire avant de commencer à envoyer des données à Platform.</li></ul> |

## Utiliser votre schéma Adobe Analytics existant

L’option permettant d’utiliser votre schéma Adobe Analytics existant avec Customer Journey Analytics n’est disponible que si votre implémentation d’Adobe Analytics est configurée avec le SDK web Adobe Experience Platform. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Avantages | Inconvénients |
|----------|---------|
| <p>L’utilisation du schéma Adobe Analytics offre les avantages suivants :</p><ul><li>Facilité de mise à niveau<p>Si vous envoyez déjà des données à Adobe Analytics avec le SDK web d’Adobe Experience Platform, vous pouvez ajouter un service supplémentaire à votre flux de données pour envoyer des données à Adobe Experience Platform (qui peuvent ensuite être utilisées dans votre configuration de Customer Journey Analytics).</p></li></ul> | <p>L’utilisation du schéma Adobe Analytics présente les inconvénients suivants :</p><ul><li>Bien que l’utilisation du schéma Adobe Analytics ne vous limite pas en termes d’utilisation avec d’autres applications Platform, elle génère un schéma plus complexe que nécessaire. En effet, le schéma Adobe Analytics contient de nombreux objets spécifiques à Adobe Analytics qui ne seront probablement pas utilisés par votre organisation.<p>Lorsque des modifications du schéma sont requises, vous devez passer en revue des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
