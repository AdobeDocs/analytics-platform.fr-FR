---
description: Utilisez la visualisation de synthèse des mesures clés pour comparer les performances des mesures sur deux chronologies.
title: Synthèse des mesures clés
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 97%

---

# Synthèse des mesures clés {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Synthèse des mesures clés"
>abstract="Créez une visualisation qui combine les graphes à courbes, de changements de résumé et de nombres de résumé. Utilisez cette visualisation pour comparer les tendances des mesures importantes entre deux périodes."


>[!BEGINSHADEBOX]

_Cet article présente la visualisation Synthèse des mesures clés dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consultez [Synthèse des mesures clés](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/visualizations/key-metric) pour la_ version ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


La visualisation ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Synthèse des mesures clés]** vous permet de visualiser le niveau de tendance d’une mesure importante au cours d’une seule période. Il vous permet également de comparer les performances des mesures sur deux périodes. Il offre les avantages de plusieurs visualisations en une seule visualisation :

* La visualisation **[!UICONTROL Ligne]** montre les tendances de la mesure pour les périodes principale et de comparaison.

* **[!UICONTROL Synthèse des modifications de pourcentage]** affiche une augmentation ou une diminution de la mesure entre les périodes principale et de comparaison.

* Valeur totale actuelle ([!UICONTROL **numéro de synthèse**]) pour la mesure

## Cas d’utilisation

Cette visualisation aborde divers cas d’utilisation courants, notamment les suivants :

* Un analyste qui essaie de comprendre à quoi ressemblait la création d’opportunités ce mois-ci par rapport à la même période l’an dernier.

* Un spécialiste du marketing qui explore la manière dont la génération de pistes pour un type de piste spécifique a changé de ce mois-ci au mois dernier.

* Un administrateur qui veut comprendre comment de nouvelles réservations ont changé de ce trimestre au dernier.

## Utilisation

1. Ajoutez une visualisation ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Résumé des mesures clés]**. Consultez [Ajouter une visualisation à un panneau](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configurez la visualisation en sélectionnant une **[!UICONTROL Mesure]**, une **[!UICONTROL période de Principal]**, une **[!UICONTROL Période de comparaison]** (facultatif) et une **[!UICONTROL Segment]** (facultatif) :

   ![Configuration des mesures clés présentant les options pour la mesure, la période principale, la période de comparaison et le segment.](assets/key-metrics-config.png)

   | Option | Description |
   | --- | --- |
   | **[!UICONTROL Mesure]** | Sélectionnez la mesure à analyser. Toutes les mesures sont prises en charge. |
   | **[!UICONTROL Période principale]** | La période actuelle du tableau à structure libre.<p>Effectuez un choix parmi toutes les périodes disponibles dans votre vue de données.</p> <p>Choisissez [!UICONTROL **Période du panneau**] si vous souhaitez utiliser la même période que celle utilisée sur le panneau où se trouve la visualisation.</p> |
   | **[!UICONTROL Période de comparaison]** | Période à laquelle vous souhaitez comparer la période principale. |
   | **[!UICONTROL Segment (facultatif)]** | Tout segment qui vous intéresse pour ce résumé. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Lorsque le champ [!UICONTROL **Période principale**] est défini sur [!UICONTROL **Période du panneau**], l’option **[!UICONTROL Période de comparaison]** peut être automatiquement mise à jour, selon que l’option **[!UICONTROL Période de comparaison]** que vous choisissez est relative à la période principale ou fixe.
   >
   >* **Relative :** si le champ **[!UICONTROL Période de comparaison]** est défini sur une option relative à la période principale (par exemple [!UICONTROL **Jour précédent**], [!UICONTROL **Même jour de la semaine dernière**], [!UICONTROL **Même jour 4 semaines avant**], etc.), toutes les mises à jour du champ [!UICONTROL **Période principale**] entraînent la mise à jour automatique de la **[!UICONTROL Période de comparaison]** qui suit immédiatement la période du panneau.
   >* **Fixe :** si le champ [!UICONTROL **Période de comparaison**] est défini sur une période fixe (par exemple, le **3 février 2023**), les modifications apportées au champ [!UICONTROL **Période principale**] ou à la période du panneau n’ont aucun effet sur la [!UICONTROL **Période de comparaison**]. Toutefois, toute mise à jour de la période du panneau entraîne la mise à jour automatique de la [!UICONTROL **Période principale**].

1. Sélectionnez la **[!UICONTROL Version]**.

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

La sortie de la synthèse des mesures clés se présente comme suit :

![Sortie de mesure clé présentant la mesure, la synthèse des modifications, la synthèse des chiffres et les graphiques linéaires.](assets/key-metrics.png)

Tenez compte des points suivants lorsque vous affichez la sortie :

* Le graphique linéaire **[!UICONTROL Période précédente]** (toujours affiché en gris) correspond à la **[!UICONTROL Période de comparaison]** de l’étape de configuration.

* Si aucune période de comparaison n’est spécifiée lors de la configuration ou si elle est masquée dans les paramètres de visualisation, seul le graphique linéaire correspondant à la période principale s’affiche. La synthèse des modifications est masquée.

* À partir de là, vous pouvez placer le pointeur de la souris sur les graphiques linéaires pour afficher les statistiques pour chaque jour :


## Configurer

Après avoir créé la visualisation, vous pouvez modifier la configuration d’origine.

1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) **[!UICONTROL Configurer la visualisation]** en haut de la visualisation.

   Vous revenez maintenant à la boîte de dialogue de configuration d’origine.

1. Modifiez les paramètres selon vos préférences. Sélectionnez **[!UICONTROL Réinitialiser]** pour réinitialiser les paramètres actuels. Sélectionnez **[!UICONTROL Créer]** pour recréer la visualisation.

## Paramètres

Dans le cadre des paramètres de visualisation, des paramètres spécifiques de synthèse des mesures clés sont disponibles.

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Mettre en gras le pourcentage de modification]** | Afficher la synthèse des modifications dans le style gras au centre de la visualisation |
| **[!UICONTROL Mettre en gras la valeur numérique]** | Afficher le numéro de synthèse en caractères gras au centre de la visualisation |
| **[!UICONTROL Légende visible]** | Afficher ou masquer la légende au bas de la visualisation |
| **[!UICONTROL Afficher les annotations]** | Afficher ou masquer les annotations ajoutées par un administrateur |
| **[!UICONTROL Masquer le titre]** | Masquez le titre de la visualisation. |
| **[!UICONTROL Pourcentages]** | Affiche la visualisation sous la forme d’un pourcentage plutôt que d’un nombre. |
| **[!UICONTROL Afficher les tendances]** | Affichez les tendances dans la visualisation. |
| **[!UICONTROL Afficher les valeurs maximales et mininimales sur les tendances]** | Afficher ou masquer les valeurs minimales et maximales sur les graphiques en courbes Principal et de comparaison |
| **[!UICONTROL Afficher le pourcentage de comparaison ainsi que la tendance]** | Afficher ou masquer les données de comparaison. Lorsqu’ils sont masqués, les objets de modification de graphique en courbes de comparaison et de modification de résumé sont n’apparaissent pas dans la vue. |
| **[!UICONTROL Afficher le nombre total]** | Afficher ou masquer la synthèse des chiffres |
| **[!UICONTROL Afficher la différence brute]** | Afficher ou masquer la différence brute entre la valeur totale de la mesure dans la période Principale et la période secondaire |
| **[!UICONTROL Abréger la valeur]** | Sélectionnez **[!UICONTROL Abréger la valeur]** pour abréger intelligemment la valeur numérique. Lorsque cette option est sélectionnée, saisissez un nombre pour définir le montant de l’abréviation. Par exemple :<br/><table><tr><td>**Valeur d’origine**</td><td>**Abréviation**</td><td>**Résultat**</td></tr><tr><td>12 011 141,25 $</td><td>Non sélectionné</td><td align="right">12 011 141,25 $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur 1</td><td align="right">12 M $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur 2</td><td align="right">12,0 M $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur 2</td><td align="right">12,011 M $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur 3</td><td align="right">12,011 M $</td></tr></table> |

## Modifier la visualisation

Après avoir créé la visualisation, vous pouvez toujours modifier la configuration d’origine.

1. Cliquez sur l’icône en forme de crayon dans le coin supérieur droit de la visualisation (en regard de l’icône d’engrenage des paramètres).

   ![Icône Modifier la visualisation](assets/edit-icon.png)

   Vous revenez maintenant à la vue de configuration d’origine.

1. Modifiez la mesure, la période Principale, la période de comparaison ou le segment selon vos préférences.

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
