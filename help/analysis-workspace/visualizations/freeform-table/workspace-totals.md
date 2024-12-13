---
description: Découvrez comment les totaux de Workspace sont calculés.
title: Totaux de Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 18%

---

# Totaux de Workspace {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Total général"
>abstract="Le total général n’est pas pris en charge pour les tableaux ou les ventilations avec des lignes statiques."

<!-- markdownlint-enable MD034 -->


Dans les tableaux à structure libre, une ligne de total s’affiche à chaque niveau de répartition et peut afficher deux totaux :

![Tableau à structure libre mettant en surbrillance le total général et le total du tableau.](assets/total-row.png)

* **[!UICONTROL Total du tableau]** ➊ - Ce total est généralement égal à ou à un sous-ensemble du [!UICONTROL Total général]. Le total reflète tous les filtres de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Inclure aucun].
* **[!UICONTROL Total général]** (**[!UICONTROL sur]** *nombre*) ➋ - Ce total représente tous les événements qui ont été collectés. Lorsqu’un filtre est appliqué au niveau du panneau ou dans le tableau à structure libre, ce total s’ajuste pour refléter tous les événements qui correspondent aux critères de filtre.




## Afficher les totaux

Sous ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres des colonnes]**, il existe des options pour **[!UICONTROL Afficher les totaux]** et **[!UICONTROL Afficher le total général]**. Si ces paramètres ne sont pas cochés, les totaux sont supprimés du tableau, ce qui peut être souhaitable dans les cas où les totaux n’ont pas de sens.


[Ligne statique](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) les totaux se comportent différemment et sont contrôlés à l’aide des ![Paramètres](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres de ligne]**.

| Option | Description |
|---|---|
| **[!UICONTROL Afficher la somme des lignes actives comme total]** | Afficher une somme côté client des lignes du tableau. Ce total ne déduplique **pas** les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher le total général]** | Afficher une somme côté serveur. Ce total déduplique les mesures telles que les sessions ou les personnes. |

Voir [Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre](column-row-settings/manual-vs-dynamic-rows.md).


## Questions fréquentes

| Questions | Réponse |
|---|---|
| Sur quel *total* les pourcentages de la colonne grise sont-ils basés ? | Ce *total* dépend de la sélection du paramètre **[!UICONTROL Pourcentages]** sous **[!UICONTROL Paramètres de ligne]** :<ul><li>Calculer les pourcentages par colonne - Ce paramètre est la valeur par défaut. Les pourcentages sont basés sur le total du tableau.</li><li>Calculer les pourcentages par ligne - Les pourcentages sont basés sur le total général.</li></ul> |
| Comment le paramètre **[!UICONTROL Inclure « Aucune valeur »]** affecte-t-il les totaux ? | Si le paramètre **[!UICONTROL Inclure « Aucune valeur »]** n’est pas coché, la ligne **[!UICONTROL Aucune valeur]** est supprimée du tableau, du total du tableau et est transférée vers toute mesure calculée qui utilise des types de mesure [*Total*](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Lorsque des filtres de tableau personnalisés sont appliqués à un tableau à structure libre, est-ce que toutes mes mesures calculées et mon compte de mise en forme conditionnelle sont associés au filtre ? | Pas pour le moment. **[!UICONTROL Inclure « Aucune valeur »]** est comptabilisé, mais les filtres de tableau personnalisés n’ont aucune incidence sur les éléments suivants :<ul><li>La plage de colonnes max/min que la mise en forme conditionnelle utilise s’applique à toutes les données.</li><li>Mesures calculées qui utilisent des types de mesures **[!UICONTROL Total général]**.</li><li>Mesures calculées avec des fonctions qui calculent entre les lignes d’un tableau à structure libre : Somme des colonnes, Max des colonnes, Min des colonnes, Nombre, Moyenne, Médiane, Percentile, Quartile, Nombre de lignes, Écart type, Variance, Cumulé, Moyenne cumulée, Variantes de régression, Score en T, Test en T, Score en Z et Test en Z.</li></ul> |
| Dans les mesures calculées, que reflète le type de mesure **[!UICONTROL Total général]** ? | Le **[!UICONTROL total général]** continue de faire référence au **[!UICONTROL total général]** et ne reflète pas les filtres appliqués à un tableau ni le **[!UICONTROL total du tableau]**. |
| Quel est le total affiché lorsque les données sont copiées et collées à partir d’un tableau à structure libre ou téléchargées via le format CSV ? | La ligne des totaux reflète uniquement le paramètre **[!UICONTROL Total du tableau]** et respecte les valeurs de la colonne **[!UICONTROL Afficher les totaux]**. |
