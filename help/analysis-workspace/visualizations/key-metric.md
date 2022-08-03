---
description: Utilisez la visualisation de synthèse des mesures clés pour comparer les performances des mesures sur deux chronologies.
title: Synthèse des mesures clés
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: 6238a3b2239a20aaedbec5e5603d0c72bb4ae463
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 6%

---

# Synthèse des mesures clés

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Le [!UICONTROL Résumé des mesures clés] la visualisation vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une seule période. Il vous permet également de comparer les performances des mesures sur deux périodes. Il offre les avantages de plusieurs visualisations combinées en une seule visualisation :

* **[!UICONTROL Ligne]** des visualisations qui montrent les tendances de la mesure pour les périodes Principales et de comparaison.

* **[!UICONTROL Modification du pourcentage de résumé]** qui affiche une augmentation ou une diminution de la mesure entre les périodes Principale et de comparaison

* Valeur totale actuelle ([!UICONTROL **numéro de résumé**]) pour la mesure

## Cas d’utilisation

Cette visualisation aborde divers cas d’utilisation courants, notamment :

* Un analyste qui essaie de comprendre à quoi ressemblait la création d’opportunités ce mois-ci par rapport à la même période l’an dernier.

* Un spécialiste du marketing qui explore la manière dont la génération de pistes pour un type de piste spécifique a changé de ce mois-ci au mois dernier.

* Un administrateur qui voulait comprendre comment les nouvelles réservations ont changé du trimestre en dernier.

## Configuration du résumé des mesures clés

1. Faites glisser le **[!UICONTROL Résumé des mesures clés]** de la **[!UICONTROL Visualisations]** dans le rail de gauche et dans un panneau.

1. Configurez la visualisation en sélectionnant une mesure, une période Principale, une période de comparaison et un segment (si vous le souhaitez) :

   ![](assets/key-metric-config.png)

   | Paramètre de configuration | Définition |
   | --- | --- |
   | **[!UICONTROL Mesure]** | Sélectionnez la mesure à examiner. Toutes les mesures sont prises en charge. |
   | **[!UICONTROL Période principale]** | La période actuelle du tableau à structure libre. |
   | **[!UICONTROL Période de comparaison]** | La période à laquelle vous souhaitez comparer la Principale période. |
   | **[!UICONTROL Segment (facultatif)]** | Tout segment qui vous intéresse spécifiquement pour ce résumé. |

   {style=&quot;table-layout:auto&quot;}

1. Cliquez sur **[!UICONTROL Créer]**.

## Afficher la sortie

![](assets/key-metric-output.png)

Remarque :

* Le **[!UICONTROL Période précédente]** le graphique linéaire (toujours affiché en gris) correspond au **[!UICONTROL Période de comparaison]** à l’étape de configuration.

* Si aucune période de comparaison n’est spécifiée lors de la configuration ou si elle est masquée dans les paramètres de visualisation, seul le graphique linéaire correspondant à la période Principale s’affiche. Le résumé de la modification sera masqué.

* À partir de là, vous pouvez placer le pointeur de la souris sur les graphiques linéaires pour afficher les statistiques pour chaque jour :

![](assets/key-metric-output2.png)

## Paramètres de visualisation

Le résumé des mesures clés offre plusieurs paramètres flexibles pour une meilleure communication et création de rapports sur les mesures importantes. Les paramètres sont accessibles par le biais de l’icône d’engrenage dans le coin supérieur droit de la visualisation.

![](assets/key-metric-settings.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Mettre en évidence le changement de pourcentage]** | Afficher le résumé du changement dans le style en gras au centre de la visualisation |
| **[!UICONTROL Souligner la valeur numérique]** | Afficher le numéro de résumé en caractères gras au centre de la visualisation |
| **[!UICONTROL Légende visible]** | Afficher ou masquer la légende au bas de la visualisation |
| **[!UICONTROL Afficher les annotations]** | Afficher ou masquer les annotations ajoutées par un administrateur |
| **[!UICONTROL Afficher les graphiques sparkline]** | Afficher ou masquer les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
| **[!UICONTROL Afficher les min. et max. sur les graphiques sparkline]** | Afficher ou masquer les valeurs minimales et maximales sur les graphiques en courbes Principal et de comparaison |
| **[!UICONTROL Afficher la comparaison]** | Afficher ou masquer les données de comparaison. Lorsqu’ils sont masqués, les objets de changement de graphique en courbes de comparaison et de résumé sont masqués. |
| **[!UICONTROL Afficher le nombre total]** | Afficher ou masquer le nombre de synthèse |
| **[!UICONTROL Afficher la différence brute]** | Afficher ou masquer la différence brute entre la valeur totale de la mesure dans la période Principale et la période secondaire |
| **[!UICONTROL Abréger la valeur]** | Abréger les valeurs numériques pour simplifier les insights communiqués (par exemple, 20 000 -> 20 000) |

## Modifier la visualisation

Après avoir créé la visualisation, vous pouvez toujours modifier la configuration d’origine.

1. Cliquez sur l’icône en forme de crayon dans le coin supérieur droit de la visualisation (en regard de l’icône d’engrenage des paramètres).

   ![](assets/edit-icon.png)

   Vous revenez maintenant à la vue de configuration d’origine.

1. Modifiez la mesure, la période Principale, la période de comparaison ou le segment selon vos préférences.
