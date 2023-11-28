---
description: En savoir plus sur les
title: Type de mesure et attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 36%

---

# Type de mesure et attribution

Lorsque vous sélectionnez l’icône représentant un engrenage en regard d’une mesure, vous pouvez spécifier le type de mesure et le modèle d’attribution.

## Type de mesure

Pour spécifier le type de mesure lors de la création d’une mesure calculée :

1. Sélectionnez l’icône d’engrenage en regard de la mesure dont vous souhaitez sélectionner le type.

   ![Icône d’engrenage avec fenêtre contextuelle affichant le type de mesure égal à Standard.](assets/cm_type_alloc.png)

1. Choisissez l’une des options suivantes :

   | Type de mesure | Définition |
   |---|---|
   | Standard | Ces mesures sont les mêmes mesures que celles utilisées dans la création de rapports standard [!DNL Analytics]. Si une formule est composée d’une seule mesure standard, elle affiche des données identiques à sa contrepartie de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque ligne. Par exemple : [Commandes] / [Sessions] prend les commandes de cet élément spécifique et le divise par le nombre de sessions de cet élément spécifique. |
   | Total général | Utilisez le Total général pour la période de création de rapports dans chaque ligne. Si une formule est composée d’une seule mesure Total général, elle affiche le même nombre total général sur chaque ligne. Les mesures totales globales sont utiles pour créer des mesures calculées qui se comparent au total des données. Par exemple : [Commandes] / [Sessions totales] affiche la proportion des commandes par rapport à TOUTES les sessions sur un canal, et pas seulement les sessions par rapport à l’élément de ligne spécifique. |

## Attribution

Pour plus d’informations sur l’attribution en Customer Journey Analytics, voir [Paramètres du composant d’attribution](/help/data-views/component-settings/attribution.md).
