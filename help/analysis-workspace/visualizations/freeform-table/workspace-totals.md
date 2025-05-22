---
description: Découvrez comment les totaux de Workspace sont calculés.
title: Totaux de Workspace
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

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

* **[!UICONTROL Total du tableau]** ➊ : ce total est généralement égal au [!UICONTROL total général] ou est un sous-ensemble de ce dernier. Le total reflète les segments de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Ne rien inclure].
* **[!UICONTROL Total général]** (**[!UICONTROL sur]** *nombre*) ➋ : ce total représente tous les événements qui ont été collectés. Lorsqu’un segment est appliqué au niveau du panneau ou dans le tableau à structure libre, ce total s’ajuste pour refléter tous les événements qui correspondent aux critères du segment.




## Afficher les totaux

Sous ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres de colonne]**, vous pouvez trouver les options **[!UICONTROL Afficher les totaux]** et **[!UICONTROL Afficher le total général]**. Si ces paramètres ne sont pas cochés, les totaux sont supprimés du tableau, ce qui peut être souhaitable dans les cas où les totaux n’ont pas de sens.


Les totaux de [ligne statique](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) se comportent différemment et peuvent être contrôlés avec ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres de la ligne]**.

| Option | Description |
|---|---|
| **[!UICONTROL Afficher la somme des lignes actives comme total]** | Affichez une somme côté client des lignes du tableau. Ce total ne déduplique **pas** les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher le total général]** | Affichez une somme côté serveur. Ce total déduplique les mesures telles que les sessions ou les personnes. |

Consultez [Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre](column-row-settings/manual-vs-dynamic-rows.md).


## Questions fréquentes

| Questions | Réponse |
|---|---|
| Sur quel *total* sont basés les pourcentages de la colonne grise ? | Ce *total* dépend de la sélection du paramètre **[!UICONTROL Pourcentages]** sous **[!UICONTROL Paramètres de la ligne]** :<ul><li>Calculer les pourcentages par colonne : ce paramètre est la valeur par défaut. Les pourcentages sont basés sur le total du tableau.</li><li>Calculer les pourcentages par ligne : les pourcentages sont basés sur le total général.</li></ul> |
| De quelle manière le paramètre **[!UICONTROL Inclure « Aucune valeur »]** affecte-t-il les totaux ? | Si le paramètre **[!UICONTROL Inclure « Aucunevaleur »]** n’est pas coché, la ligne **[!UICONTROL Aucun valeur]** sera supprimée du tableau et du total du tableau, et sera répercutée sur toutes les mesures calculées qui utilisent les types de mesures [** Total](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Lorsque des segments de tableau personnalisés sont appliqués à un tableau à structure libre, est-ce que toutes les mesures calculées et la mise en forme conditionnelle tiennent compte du segment ? | Pas pour le moment. Le paramètre **[!UICONTROL Inclure « Aucune valeur »]** est pris en compte, mais les segments de tableau personnalisés n’auront aucun impact sur les éléments suivants :<ul><li>La plage max/min de la colonne utilisée par la mise en forme conditionnelle s’applique à toutes les données.</li><li>Mesures calculées qui utilisent les types de mesures **[!UICONTROL Total général]**.</li><li>Mesures calculées avec des fonctions qui effectuent des calculs sur les lignes d’un tableau à structure libre, c’est-à-dire Somme de la colonne, Colonne max, Colonne min, Nombre, Moyenne, Médiane, Percentile, Quartile, Nombre de lignes, Écart type, Variance, Cumulatif, Moyenne cumulée, Variantes de régression, Score normalisé, Test en T, Score centré réduit, Test Z.</li></ul> |
| Dans les mesures calculées, que signifie le type de mesure **[!UICONTROL Total général]** ? | **[!UICONTROL Total général]** continue de faire référence au **[!UICONTROL total général]** et ne reflète pas les segments appliqués à un tableau ou au **[!UICONTROL total du tableau]**. |
| Quel est le total affiché lorsque les données sont copiées et collées à partir d’un tableau à structure libre ou téléchargées via le format CSV ? | La ligne de total reflète uniquement le **[!UICONTROL total du tableau]** et respecte le paramètre **[!UICONTROL Afficher les totaux]** de la colonne. |
