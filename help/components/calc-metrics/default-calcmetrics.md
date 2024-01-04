---
description: Adobe fournit diverses mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leurs utilisations prévues.
title: Mesures calculées par défaut
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 27%

---

# Mesures calculées par défaut

Customer Journey Analytics fournit les mesures calculées suivantes pour couvrir les cas d’utilisation les plus courants :

| Nom de la mesure calculée | Description | Formule |
|---------|----------|---------|
| Taux de début de session | Pourcentage du nombre d’éléments de dimension qui se sont produits au premier événement d’une session.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez la variable `[Session Starts]` [composant standard](/help/data-views/component-reference.md) dans votre [vue des données](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Durée par personne | Durée moyenne passée par une personne sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez la variable `[Time Spent (seconds)]` [composant standard](/help/data-views/component-reference.md) dans votre [vue des données](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sessions par personne | Nombre moyen de sessions par personne. | `[Sessions] / [Users]` |
| Durée par session | Durée moyenne passée par personne et par session sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez la variable `[Time Spent (seconds)]` [composant standard](/help/data-views/component-reference.md) dans votre [vue des données](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Taux de fin de session | Pourcentage du dernier événement d’une session auquel un élément de dimension s’est produit. <p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez la variable `[Session Ends]` [composant standard](/help/data-views/component-reference.md) dans votre [vue des données](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
