---
title: Comprendre les fonctionnalités propres à Customer Journey Analytics
description: En savoir plus sur les fonctionnalités propres à Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
TQID: https://experienceleague.adobe.com/8yBVFyHrc31-ac8XLV-aW-SWBfDZodlIXirICmdzpkY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 591
ht-degree: 100%

---

# Comprendre les fonctionnalités propres à Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Lier les données de différentes sources"
>abstract="(Recommandé) Liez les données provenant de diverses propriétés web, mobiles et hors ligne pour créer une vue unique et consolidée du comportement des clientes et clients. La possibilité de combiner des données d’analyse provenant d’autres canaux est le principal cas d’utilisation de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Regrouper les accès à partir de plusieurs jeux de données"
>abstract="Si l’un de vos jeux de données ne partage pas d’identifiant principal (tel qu’un Experience Cloud ID), vous pouvez toujours regrouper ces données à l’aide d’une autre dimension, telle que le nom d’utilisateur ou d’utilisatrice ou l’adresse e-mail de connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Activer le groupement pour les jeux de données pertinents"
>abstract="Si un champ contient un identifiant qui existe dans plusieurs jeux de données mais n’est pas l’identifiant principal, vous pouvez utiliser l’assemblage pour transférer les données dans un ou plusieurs de ces jeux de données."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Intégrer à Real-time CDP"
>abstract="Combinez des données de profil provenant de plusieurs sources afin de générer des audiences et des segments en fonction des caractéristiques des utilisateurs et utilisatrices."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Intégrer temporairement à Adobe Target"
>abstract="Adobe recommande l’intégration à Adobe Journey Optimizer pour les cas d’utilisation de la personnalisation. L’intégration à Adobe Target est possible, mais il s’agit d’une solution temporaire."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Intégrer à Journey Optimizer"
>abstract="Proposez des expériences connectées, contextuelles et personnalisées aux clientes et clients."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Intégrer temporairement à Adobe Audience Manager"
>abstract="Adobe recommande l’intégration à Adobe Real-time CDP pour les cas d’utilisation basés sur l’audience. L’intégration à Audience Manager est possible, mais il s’agit d’une solution temporaire."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La liste suivante affiche uniquement les fonctionnalités Customer Journey Analytics qui doivent être prises en compte pendant le processus de mise à niveau. Pour obtenir une liste complète des fonctionnalités Adobe Analytics entièrement prises en charge, partiellement prises en charge ou non prises en charge dans Customer Journey Analytics, consultez [Prise en charge des fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Tenez compte des fonctionnalités Customer Journey Analytics suivantes que vous souhaitez adopter lors de la mise à niveau vers Customer Journey Analytics :

| Fonctionnalité Customer Journey Analytics | Fonction |
|---------|----------|
| [Associer des données web à des données provenant d’autres canaux, par exemple, des données de centres d’appel](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous types et schémas de données. Grâce au [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr), les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. Adobe Analytics est principalement axé sur les données d’analyse web et mobile, avec certaines fonctionnalités permettant d’[importer les données](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=fr). |
| [Assembler des résultats provenant d’autres jeux de données à l’aide d’une dimension personnalisée](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics vous permet de [combiner les données](/help/connections/combined-dataset.md) de plusieurs suites de rapports comme s’il s’agissait d’une seule suite de rapports dans Adobe Analytics. |
| [Intégrer à Adobe Real-Time CDP](/help/components/audiences/audiences-overview.md) | Vous pouvez [créer et publier des audiences](/help/components/audiences/audiences-overview.md) découvertes dans Customer Journey Analytics dans le profil client en temps réel d’Adobe Experience Platform pour le ciblage des clientes et clients et la personnalisation. |
| [Intégrer à Adobe Target (A4T)](/help/integrations/at.md) | Le reporting des performances Target dans Customer Journey Analytics vous permet de [mesurer et de générer des rapports sur les activités Adobe Target](/help/integrations/at.md) directement dans Customer Journey Analytics. Adobe recommande toutefois l’intégration à Adobe Journey Optimizer pour la personnalisation. |
| [Intégrer à Adobe Journey Optimizer](/help/integrations/ajo.md) | Vous pouvez configurer les données générées par Journey Optimizer afin d’[effectuer une analyse avancée dans Customer Journey Analytics](/help/integrations/ajo.md). |
| [Intégrer à Adobe Audience Manager](https://experienceleague.adobe.com/fr/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Vous pouvez [partager des caractéristiques et des segments Audience Manager vers Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Adobe recommande toutefois l’intégration à Adobe Real-time CDP pour les cas d’utilisation basés sur les audiences. |
