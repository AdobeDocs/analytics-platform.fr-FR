---
title: Utiliser l’objet de personnalisation pour l’utiliser avec Adobe Journey Optimizer
description: Découvrir comment utiliser l’objet de personnalisation pour l’utiliser avec Adobe Journey Optimizer
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5086ac6e-5bee-4f0f-b7e5-a3d9bd8a1332
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 90%

---

# Utiliser l’objet de personnalisation pour l’utiliser avec Adobe Journey Optimizer {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="Utiliser l’objet de personnalisation pour Adobe Journey Optimizer"
>abstract="En tirant parti des technologies de pointe en matière de machine learning et de deep learning supervisés, l’optimisation personnalisée permet à une personne professionnelle (spécialisée dans le marketing) de définir des objectifs commerciaux et d’utiliser ses données de clientèle pour entraîner des modèles orientés métier afin de fournir des offres personnalisées et d’optimiser les KPI."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

En tirant parti des technologies de pointe en matière de machine learning et de deep learning supervisés, l’optimisation personnalisée permet à une personne professionnelle (spécialisée dans le marketing) de définir des objectifs commerciaux et d’utiliser ses données de clientèle pour entraîner des modèles orientés métier afin de fournir des offres personnalisées et d’optimiser les KPI.

1. Suivez les informations de la section [Modèle d’optimisation personnalisée](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/personalized-optimization-model) du guide de Journey Optimizer.

{{upgrade-final-step}}

<!--

The result of the personalization object ends up in a dataset. The result of experimentation. When a customer has used AA with Target, that ends up in a complete different space than when they're migrating to CJA and they're going to use CJA with Adobe Target. 

Target was the old way of setting up an A/B test or experimentation. Then ensuring the results of those tests in Target ended up in AA for reporting. Now if you're using Target, instead of saying that you want the data in Target, you can now select CJA as your reporting source for an Adobe Target activity. So if a customer is doing this in AA and they want to move to CJA, ...

If a customer has AJO, and is using Offers in AJO, then they can set up offers, and that also creates datasets in Platform... But that's not relevant with upgrade, exactly.



Questions we need to answer:

1. How do we determine the personalization criteria (Red for user A and blue for User B)

1. What do we implement on the site to determine the red / blue object?


2 ways we can do it:

Manually rendering content or Automatically rendering content. 


## Manual implementation of the Web SDK


## Mobile SDK implementation 





## Tags

-->
