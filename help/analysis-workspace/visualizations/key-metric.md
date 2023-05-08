---
description: Utilisez la visualisation de synthèse des mesures clés pour comparer les performances des mesures sur deux chronologies.
title: Synthèse des mesures clés
feature: Visualizations
role: User, Admin
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
source-git-commit: f2e152345d7a395c684a964e72b1bcdaa5d817b0
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 99%

---

# Synthèse des mesures clés

La visualisation [!UICONTROL de synthèse des mesures clés] vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une seule période. Il vous permet également de comparer les performances des mesures sur deux périodes. Il offre les avantages de plusieurs visualisations en une seule visualisation :

* Visualisations **[!UICONTROL en ligne]** qui montrent les tendances de la mesure pour les périodes principales et de comparaison

* **[!UICONTROL Synthèse des modifications de pourcentage]** qui affiche une augmentation ou une diminution de la mesure entre les périodes Principale et de comparaison

* Valeur totale actuelle ([!UICONTROL **numéro de synthèse**]) pour la mesure

## Cas d’utilisation

Cette visualisation aborde divers cas d’utilisation courants, notamment :

* Un analyste qui essaie de comprendre à quoi ressemblait la création d’opportunités ce mois-ci par rapport à la même période l’an dernier.

* Un spécialiste du marketing qui explore la manière dont la génération de pistes pour un type de piste spécifique a changé de ce mois-ci au mois dernier.

* Un administrateur qui veut comprendre comment de nouvelles réservations ont changé de ce trimestre au dernier.

## Configuration de la synthèse des mesures clés

1. Faites glisser la visualisation de la **[!UICONTROL synthèse des mesures clés]** du menu **[!UICONTROL Visualisations]** se trouvant dans le rail gauche d’un panneau.

1. Configurez la visualisation en sélectionnant une mesure, une période Principale, et une période de comparaison et un segment (si vous le souhaitez) :

   ![configuration des mesures clés](assets/key-metric-config.png)

   | Paramètre de configuration | Définition |
   | --- | --- |
   | **[!UICONTROL Mesure]** | Sélectionnez la mesure à analyser. Toutes les mesures sont prises en charge. |
   | **[!UICONTROL Période principale]** | La période actuelle du tableau à structure libre. |
   | **[!UICONTROL Période de comparaison]** | La période à laquelle vous souhaitez comparer la période principale. |
   | **[!UICONTROL Segment (facultatif)]** | Tout segment qui vous intéresse spécifiquement pour cette synthèse. |

   {style="table-layout:auto"}

1. Cliquez sur **[!UICONTROL Créer]**.

## Afficher la sortie

![](assets/key-metric-output.png)

Remarque :

* La **[!UICONTROL Période précédente]** du graphique linéaire (toujours affiché en gris) correspond à la **[!UICONTROL Période de comparaison]** de l’étape de configuration.

* Si aucune période de comparaison n’est spécifiée lors de la configuration ou si elle est masquée dans les paramètres de visualisation, seul le graphique linéaire correspondant à la période principale s’affiche. La synthèse des modifications sera masquée.

* À partir de là, vous pouvez placer le pointeur de la souris sur les graphiques linéaires pour afficher les statistiques pour chaque jour :

![statistics](assets/key-metric-output2.png)

## Paramètres de visualisation

La synthèse des mesures clés offre plusieurs paramètres flexibles pour une meilleure communication et création de rapports sur les mesures importantes. Les paramètres sont accessibles par le biais de l’icône d’engrenage dans le coin supérieur droit de la visualisation.

![](assets/key-metric-settings.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Mettre en gras le pourcentage de modification]** | Afficher la synthèse des modifications dans le style gras au centre de la visualisation |
| **[!UICONTROL Mettre en gras la valeur numérique]** | Afficher le numéro de synthèse en caractères gras au centre de la visualisation |
| **[!UICONTROL Légende visible]** | Afficher ou masquer la légende au bas de la visualisation |
| **[!UICONTROL Afficher les annotations]** | Afficher ou masquer les annotations ajoutées par un administrateur |
| **[!UICONTROL Afficher les graphiques sparkline]** | Afficher ou masquer les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
| **[!UICONTROL Afficher les min. et max. sur les graphiques sparkline]** | Afficher ou masquer les valeurs minimales et maximales sur les graphiques en courbes Principal et de comparaison |
| **[!UICONTROL Afficher la comparaison]** | Afficher ou masquer les données de comparaison. Lorsqu’ils sont masqués, les objets de modification de graphique en courbes de comparaison et de modification de synthèse sont hors de vue. |
| **[!UICONTROL Afficher le nombre total]** | Afficher ou masquer la synthèse des chiffres |
| **[!UICONTROL Afficher la différence brute]** | Afficher ou masquer la différence brute entre la valeur totale de la mesure dans la période Principale et la période secondaire |
| **[!UICONTROL Abréger la valeur]** | Abréger les valeurs numériques pour simplifier les insights communiqués (par exemple, 20 000 -> 20 000) |

## Modifier la visualisation

Après avoir créé la visualisation, vous pouvez toujours modifier la configuration d’origine.

1. Cliquez sur l’icône en forme de crayon dans le coin supérieur droit de la visualisation (en regard de l’icône d’engrenage des paramètres).

   ![edit](assets/edit-icon.png)

   Vous revenez maintenant à la vue de configuration d’origine.

1. Modifiez la mesure, la période Principale, la période de comparaison ou le segment selon vos préférences.
