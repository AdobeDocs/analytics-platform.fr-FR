---
description: Découvrez comment les totaux de Workspace sont calculés.
title: Totaux de Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: b9abcf48c5334d71639d7d96558a63611a4a491c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 15%

---

# Totaux de Workspace {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_grandtotal"
>title="Total général"
>abstract="Le total général n’est pas pris en charge pour les tableaux ou les ventilations avec des lignes statiques."

<!-- markdownlint-enable MD034 -->


Dans les tableaux à structure libre, une ligne de total s’affiche à chaque niveau de répartition et peut afficher deux totaux :

![Tableau à structure libre mettant en surbrillance le total général et le total du tableau.](assets/total-row.png)

* **[!UICONTROL Total de la table]** : ce total est généralement égal à ou est un sous-ensemble du [!UICONTROL total général]. Le total reflète les filtres de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Inclure aucun].
* **[!UICONTROL Total général]** (**[!UICONTROL sur]** *nombre*) - Ce total représente tous les événements qui ont été collectés. Lorsqu’un filtre est appliqué au niveau du panneau ou dans le tableau à structure libre, ce total s’ajuste pour refléter tous les événements qui correspondent aux critères de filtre.




## Afficher les totaux

Sous ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres de colonne]**, il existe des options pour **[!UICONTROL Afficher les totaux]** et **[!UICONTROL Afficher le total général]**. Si ces paramètres ne sont pas cochés, les totaux sont supprimés du tableau, ce qui peut être souhaitable dans les cas où les totaux n’ont pas de sens. Par exemple, dans certains [scénarios de mesures calculées](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals).


Les totaux de [lignes statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) se comportent différemment et sont contrôlés à l’aide de la ![définition](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres de ligne]**.

| Option | Description |
|---|---|
| **[!UICONTROL Afficher la somme des lignes actuelles en tant que total]** | Afficher la somme des lignes du tableau côté client. Ce total ne déduplique **pas** les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher le total général]** | Afficher une somme côté serveur. Ce total dédupliquait les mesures telles que les sessions ou les personnes. |

Voir [Éléments de dimension dynamiques ou statiques dans les tables à structure libre](column-row-settings/manual-vs-dynamic-rows.md).


## Questions fréquentes

| Questions | Réponse |
|---|---|
| Sur quels *total* sont basés les pourcentages des colonnes grises ? | Ce *total* dépend de la sélection du paramètre **[!UICONTROL Pourcentages]** sous **[!UICONTROL Paramètres de ligne]** :<ul><li>Calculer les pourcentages par colonne : ce paramètre est le paramètre par défaut. Les pourcentages sont basés sur le total du tableau.</li><li>Calculer les pourcentages par ligne : les pourcentages sont basés sur le total général.</li></ul> |
| Comment le paramètre **[!UICONTROL Inclure &quot;Aucune valeur&quot;]** affecte-t-il les totaux ? | Si le paramètre **[!UICONTROL Inclure &quot;Aucune valeur&quot;]** n’est pas coché, la ligne **[!UICONTROL Aucune valeur]** est supprimée de la table, le total du tableau, et porte vers toutes les mesures calculées qui utilisent les [*types de mesures* Total](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc). |
| Lorsque des filtres de tableau personnalisés sont appliqués à un tableau à structure libre, est-ce que toutes mes mesures calculées et mon compte de mise en forme conditionnelle sont associés au filtre ? | Pas pour le moment. **[!UICONTROL Inclure &quot;Aucune valeur&quot;]** est un compte, mais les filtres de table personnalisés n’ont pas d’impact sur les éléments suivants :<ul><li>La plage max./min. de la colonne utilisée par la mise en forme conditionnelle s’applique à toutes les données.</li><li>Mesures calculées qui exploitent les types de mesures **[!UICONTROL Total général]**.</li><li>Mesures calculées avec des fonctions qui effectuent le calcul sur plusieurs lignes d’un tableau à structure libre : Somme des colonnes, Max. des colonnes, Min. des colonnes, Comptage, Moyenne, Moyenne, Percentile, Quartile, Décompte des lignes, Écart type, Variance, Moyenne cumulée, Moyenne cumulée, Variantes de régression, Score en T, Test-Z et Test-Z.</li></ul> |
| Dans les mesures calculées, que reflète le type de mesure **[!UICONTROL Total général]** ? | **[!UICONTROL Total général]** continue de faire référence au **[!UICONTROL total général]** et ne reflète pas les filtres appliqués à une table ou au **[!UICONTROL total de la table]**. |
| Quel est le total affiché lorsque les données sont copiées et collées à partir d’un tableau à structure libre ou téléchargées via le format CSV ? | La ligne de total reflète uniquement le **[!UICONTROL total du tableau]** et respecte le paramètre de colonne **[!UICONTROL Afficher les totaux]**. |
