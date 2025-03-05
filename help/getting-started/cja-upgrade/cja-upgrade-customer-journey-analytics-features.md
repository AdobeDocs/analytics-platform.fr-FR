---
title: Comprendre les fonctionnalités propres à Customer Journey Analytics
description: En savoir plus sur les fonctionnalités propres à Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: d745e0c3bc75ba6f9d29aedcdbaaae9aa17d6ab8
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 27%

---

# Comprendre les fonctionnalités propres à Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Lier les données de différentes sources"
>abstract="(Recommandé) Lier les données de diverses propriétés web, mobiles et hors ligne pour créer une vue unique et consolidée du comportement des clients. Cette possibilité de combiner des données d’analyse provenant d’autres canaux est le principal cas d’utilisation de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Regrouper les accès à partir de plusieurs jeux de données"
>abstract="Si l’un de vos jeux de données ne partage pas d’identifiant principal (tel qu’un ID Experience Cloud), vous pouvez toujours regrouper ces données à l’aide d’une autre dimension, telle que le nom utilisé pour la connexion ou l’adresse e-mail."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Contactez l’assistance clientèle d’Adobe pour générer un jeu de données groupé"
>abstract="Si un champ contient un identifiant qui existe dans plusieurs jeux de données mais n’est pas l’identifiant principal, vous pouvez l’utiliser pour générer un nouveau jeu de données avec un identifiant cohérent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Intégration à la plateforme de données clients en temps réel"
>abstract="Combinez des données de profil provenant de plusieurs sources afin de générer des audiences et des segments en fonction des caractéristiques de l’utilisateur."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Intégrer temporairement à Adobe Target"
>abstract="Adobe recommande d’intégrer à Adobe Journey Optimizer pour les cas d’utilisation de la personnalisation. L’intégration à Adobe Target est possible, mais il s’agit d’une solution à court terme."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Intégration à Journey Optimizer"
>abstract="Proposez des expériences connectées, contextuelles et personnalisées aux clients."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Intégrer temporairement à Adobe Audience Manager"
>abstract="Adobe recommande l’intégration à la plateforme de données clients en temps réel d’Adobe pour les cas d’utilisation basés sur l’audience. L’intégration à Audience Manager est possible, mais il s’agit d’une solution à court terme."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La liste suivante affiche uniquement les fonctionnalités Customer Journey Analytics qui doivent être prises en compte pendant le processus de mise à niveau. Pour obtenir une liste complète des fonctionnalités Adobe Analytics entièrement prises en charge, partiellement prises en charge ou non prises en charge dans Customer Journey Analytics, consultez [Prise en charge des fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Tenez compte des fonctionnalités Customer Journey Analytics suivantes que vous souhaitez adopter lors de la mise à niveau vers Customer Journey Analytics :

| Fonctionnalité Customer Journey Analytics | Fonction |
|---------|----------|
| [lier les données web aux données d’autres canaux, telles que les données du centre d’appels](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous types et schémas de données. Grâce au [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr), les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. Adobe Analytics est principalement axé sur les données d’analyse web et mobile, avec certaines fonctionnalités permettant d’[importer les données](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=fr). |
| [Regrouper les accès d’autres jeux de données à l’aide d’une dimension personnalisée](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics vous permet de [combiner les données](/help/connections/combined-dataset.md) de plusieurs suites de rapports comme s’il s’agissait d’une seule suite de rapports dans Adobe Analytics. |
| [Intégration à la plateforme de données clients en temps réel Adobe](/help/components/audiences/audiences-overview.md) | Vous pouvez [créer et publier des audiences](/help/components/audiences/audiences-overview.md) découvertes dans Customer Journey Analytics dans le profil client en temps réel dans Adobe Experience Platform pour le ciblage et la personnalisation des clients. |
| [Intégration à Adobe Target (A4T)](/help/integrations/at.md) | Le compte rendu des performances Target dans Customer Journey Analytics vous permet de [mesurer et générer des rapports sur les activités Adobe Target](/help/integrations/at.md) directement dans Customer Journey Analytics. Cependant, Adobe recommande d’intégrer à Adobe Journey Optimizer pour les cas d’utilisation de la personnalisation. |
| [Intégration à Adobe Journey Optimizer](/help/integrations/ajo.md) | Vous pouvez configurer les données générées par Journey Optimizer pour [effectuer une analyse avancée dans Customer Journey Analytics](/help/integrations/ajo.md). |
| [Intégration à Adobe Audience Manager](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Vous pouvez [partager des caractéristiques et des segments Audience Manager vers Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Cependant, Adobe recommande d’intégrer à la plateforme de données clients en temps réel d’Adobe pour les cas d’utilisation basés sur l’audience. |
