---
description: Comprenez comment un flux interdimensionnel vous permet d’examiner les chemins d’accès des utilisateurs sur différentes dimensions.
title: Flux interdimensionnels
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
autotag-review: '2026-05-19T08:41:06.716Z'
TQID: 'https://experienceleague.adobe.com/1er03t5uOypgXP6sjFW3z7vbN8IucVak2OiDeUG-OaU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 89%

---

# Flux interdimensionnels

Un flux interdimensionnel vous permet d’examiner les chemins d’accès pour les utilisateurs et utilisatrices sur plusieurs dimensions. Cet article montre comment utiliser ce flux pour deux cas d’utilisation : les interactions et les événements d’applications mobiles, et la manière dont les campagnes génèrent des visites web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interactions et événements des applications mobiles

La dimension [!UICONTROL Nom de l’écran] est utilisée dans cet exemple de flux pour voir comment les utilisateurs et utilisatrices utilisent les différents écrans (scènes) dans l’application. L’écran supérieur renvoyé est **[!UICONTROL luma: content: ios: en: home]**, qui est la page d’accueil de l’application :

![Flux affichant l’élément ajouté.](assets/flowapp.png)

Pour explorer l’interaction entre les écrans et les types d’événement (tels que l’ajout au panier, les achats, etc.) dans cette application, effectuez un glisser-déposer de la dimension **[!UICONTROL Types d’événement]** :

* En plus de toute étape disponible dans le flux, pour remplacer cette dimension, procédez comme suit :

  ![Flux présentant la dimension Page placée dans plusieurs zones.](assets/flowapp-replace.png)

* En dehors de la visualisation de flux actuelle, pour ajouter la dimension, procédez comme suit :

  ![Flux affichant la dimension Page placée dans l’espace blanc à la fin.](assets/flowapp-add.png)

La visualisation de flux ci-dessous montre le résultat de l’ajout de la dimension **[!UICONTROL Types d’événement]**. La visualisation fournit des informations sur la manière dont les utilisateurs et utilisatrices d’applications mobiles se déplacent sur différents écrans de l’application avant d’ajouter des produits à un panier, de fermer l’application, de se voir présenter une offre, etc.

![Flux affichant les résultats de la dimension Page en haut de la liste.](assets/flowapp-result.png)

## Génération de visites web par les campagnes

Vous souhaitez analyser les campagnes qui génèrent des visites sur le site web. Vous créez une visualisation de flux avec la dimension **[!UICONTROL Nom de la campagne]**.

![Dimension du nom de la campagne web de flux](assets/flowweb.png)

Vous remplacez la dernière dimension **[!UICONTROL Nom de la campagne]** par la dimension **[!UICONTROL Nom de page formaté]** et ajoutez une autre dimension **[!UICONTROL Nom de page formaté]** à la fin de la visualisation de flux.

![Nom de campagne web de flux et dimension de page web](assets/flowweb-replace.png)

Vous pouvez pointer sur n’importe quel flux pour afficher plus de détails. Par exemple, les campagnes qui ont généré un passage en caisse du panier.

![Nom de campagne web de flux et pointage sur la dimension de page web](assets/flowweb-hover.png)
