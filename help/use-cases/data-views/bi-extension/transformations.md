---
title: Transformations
description: Cas d’utilisation des transformations pour l’extension BI dans divers outils BI dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# Transformations


Vous souhaitez comprendre les transformations des objets Customer Journey Analytics tels que les dimensions, les mesures, les filtres, les mesures calculées et les périodes par les différents outils de BI.

+++ Customer Journey Analytics

Dans Customer Journey Analytics, vous définissez dans une [vue de données](/help/data-views/data-views.md) les composants de vos jeux de données qui sont exposés en tant que [dimensions](/help/components/dimensions/overview.md) et [mesures](/help/components/apply-create-metrics.md), ainsi que la manière dont ils le sont. Cette définition de dimension et de mesures est exposée aux outils BI à l’aide de l’extension BI.
Vous utilisez des composants tels que [Filtres](/help/components/segments/seg-overview.md), [Mesures calculées](/help/components/calc-metrics/calc-metr-overview.md) et [Périodes](/help/components/date-ranges/overview.md) dans le cadre de vos projets Workspace. Ces composants sont également exposés aux outils de BI à l’aide de l’extension BI.

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

Les objets Customer Journey Analytics sont disponibles dans le volet **[!UICONTROL Données]** et sont récupérés à partir du tableau que vous avez sélectionné dans Power BI Desktop. Par exemple, **[!UICONTROL public.cc_data_view]**. Le nom de la table est identique à l’ID externe que vous avez défini pour votre vue de données dans Customer Journey Analytics. Par exemple, la vue de données avec les **** Titre`C&C - Data View` **[!UICONTROL et]** ID externe`cc_data_view`.

**Dimensions**
Les dimensions Customer Journey Analytics sont identifiées par l’[!UICONTROL ID de composant]. L’[!UICONTROL ID de composant] est défini dans votre vue de données Customer Journey Analytics. Par exemple, la dimension **[!UICONTROL Nom du produit]** dans Customer Journey Analytics comporte un [!UICONTROL ID de composant] **[!UICONTROL nom_produit]**, qui est le nom de la dimension dans Power BI Desktop.
Les dimensions de période de Customer Journey Analytics, telles que **[!UICONTROL Jour]**, **[!UICONTROL Semaine]**, **[!UICONTROL Mois]**, etc. sont disponibles sous la forme **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]**, etc.

**Mesures**
Les mesures Customer Journey Analytics sont identifiées par l’[!UICONTROL ID de composant]. L’[!UICONTROL ID de composant] est défini dans votre vue de données Customer Journey Analytics. Par exemple, la mesure **[!UICONTROL Chiffre d’affaires d’achat]** dans Customer Journey Analytics comporte un [!UICONTROL ID de composant] **[!UICONTROL purchase_revenue]**, qui est le nom de la mesure dans Power BI Desktop. Un **[!UICONTROL ∑]** indique les mesures. Lorsque vous utilisez une mesure dans n’importe quelle visualisation, la mesure est renommée **[!UICONTROL Somme de *mesure *]**.

**Filtres**
Les filtres que vous définissez dans Customer Journey Analytics sont disponibles dans le champ **[!UICONTROL filterName]**. Lorsque vous utilisez un champ **[!UICONTROL filterName]** dans Power BI Desktop, vous pouvez spécifier le filtre à utiliser.

**Mesures calculées**
Les mesures calculées que vous définissez dans Customer Journey Analytics sont identifiées par l’[!UICONTROL ID externe] que vous avez défini pour la mesure calculée. Par exemple, la mesure calculée **[!UICONTROL Nom du produit (nombre distinct)]** comporte [!UICONTROL ID externe] **[!UICONTROL nom_produit_nombre_distinct]** et s’affiche sous la forme **[!UICONTROL cm_nom_produit_nombre_distinct]**t dans Power BI Desktop.

**périodes**
Les périodes que vous définissez dans Customer Journey Analytics sont disponibles dans le champ **[!UICONTROL daterangeName]**. Lorsque vous utilisez un champ **[!UICONTROL daterangeName]**, vous pouvez spécifier la période à utiliser.

**Transformations personnalisées**
Power BI Desktop fournit une fonctionnalité de transformation personnalisée à l’aide de [Data Analysis Expressions (DAX)](https://learn.microsoft.com/en-us/dax/dax-overview). Par exemple, vous souhaitez exécuter le cas d’utilisation [Classement sur une seule dimension](#single-dimension-ranked) avec les noms de produits en minuscules.

1. Dans la vue Rapport, sélectionnez la visualisation sous forme de barre.
1. Sélectionnez **[!UICONTROL product_name]** dans le volet Données.
1. Sélectionnez **[!UICONTROL Nouvelle colonne]** dans la barre d’outils.
1. Dans l’éditeur de formules, définissez une nouvelle colonne nommée `product_name_lower`, comme `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Power BI Desktop Transformation to Lower](../assets/uc14-powerbi-transformation.png)
1. Veillez à sélectionner la nouvelle colonne **[!UICONTROL product_name_lower]** dans le volet **[!UICONTROL Données]** au lieu de la colonne **[!UICONTROL product_name]**.
1. Sélectionnez **[!UICONTROL Rapport sous forme de tableau]** dans ![Plus](/help/assets/icons/More.svg) dans la visualisation du tableau.

   Votre bureau Power BI doit se présenter comme suit :
   ![Power BI Desktop Transformation Final](../assets/uc14-powerbi-final.png)

La transformation personnalisée entraîne une mise à jour des requêtes SQL. Consultez l’utilisation de la fonction `lower` dans l’exemple SQL ci-dessous :

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB  Tableau Desktop ]

Les objets Customer Journey Analytics sont disponibles dans la barre latérale **[!UICONTROL Données]** lorsque vous travaillez dans une feuille. et sont récupérés à partir du tableau que vous avez sélectionné dans le cadre de la page **[!UICONTROL Source de données]** de Tableau. Par exemple, **[!UICONTROL cc_data_view]**. Le nom de la table est identique à l’ID externe que vous avez défini pour votre vue de données dans Customer Journey Analytics. Par exemple, la vue de données avec les **** Titre`C&C - Data View` **[!UICONTROL et]** ID externe`cc_data_view`.

**Dimensions**
Les dimensions de Customer Journey Analytics sont identifiées par le [!UICONTROL nom du composant]. Le [!UICONTROL nom du composant] est défini dans votre vue de données Customer Journey Analytics. Par exemple, la dimension **[!UICONTROL Nom du produit]** dans Customer Journey Analytics comporte un [!UICONTROL Nom du composant] **[!UICONTROL Nom du produit]**, qui est le nom de la dimension dans Tableau. Toutes les dimensions sont identifiées par **[!UICONTROL Abc]**.
Les dimensions de période de Customer Journey Analytics, telles que **[!UICONTROL Jour]**, **[!UICONTROL Semaine]**, **[!UICONTROL Mois]**, etc. sont disponibles sous la forme **[!UICONTROL JourCatalogue]**, **[!UICONTROL SemaineCatalogue]**, **[!UICONTROL MoisCatalogue]**, etc. Lorsque vous utilisez une dimension de période, vous devez sélectionner une définition de date ou d’heure appropriée à appliquer à cette dimension de période dans le menu déroulant. Par exemple, **[!UICONTROL Année]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mois]**, **[!UICONTROL Jour]**.

**Mesures**
Les mesures Customer Journey Analytics sont identifiées par le [!UICONTROL nom du composant]. Le [!UICONTROL nom du composant] est défini dans votre vue de données Customer Journey Analytics. Par exemple, la mesure **[!UICONTROL Chiffre d’affaires d’achat]** dans Customer Journey Analytics comporte un [!UICONTROL Nom du composant] **[!UICONTROL Chiffre d’affaires d’achat]**, qui est le nom de la mesure dans Tableau. Toutes les mesures sont identifiées par **[!UICONTROL #]**. Lorsque vous utilisez une mesure dans n’importe quelle visualisation, la mesure est renommée **[!UICONTROL Somme(*mesure*)]**.

**Filtres**
Les filtres que vous définissez dans Customer Journey Analytics sont disponibles dans le champ **[!UICONTROL Nom du filtre]**. Lorsque vous utilisez un champ **[!UICONTROL Nom du filtre]** dans Tableau, vous pouvez spécifier le filtre à utiliser.

**Mesures calculées**
Les mesures calculées que vous définissez dans Customer Journey Analytics sont identifiées par le [!UICONTROL Titre] que vous avez défini pour la mesure calculée. Par exemple, la mesure calculée **[!UICONTROL Nom du produit (Nombre distinct)]** comporte [!UICONTROL Titre] **[!UICONTROL Nom du produit (Nombre distinct)]** et s’affiche sous la forme **[!UICONTROL Cm Nom du produit Nombre distinct]** dans le tableau.

**périodes**
Les périodes que vous définissez dans Customer Journey Analytics sont disponibles dans le champ **[!UICONTROL Nom de la période]**. Lorsque vous utilisez un champ **[!UICONTROL Nom de la période]**, vous pouvez spécifier la période à utiliser.

**Transformations personnalisées**
Tableau Desktop fournit une fonctionnalité de transformation personnalisée à l&#39;aide de [Champs calculés](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Par exemple, vous souhaitez exécuter le cas d’utilisation [Classement sur une seule dimension](#single-dimension-ranked) avec les noms de produits en minuscules.

1. Sélectionnez **[!UICONTROL Analyse]** > **[!UICONTROL Créer un champ calculé]** dans le menu principal.
   1. Définissez **[!UICONTROL Nom du produit en minuscules]** à l’aide de la fonction `LOWER([Product Name])`.
      ![Champ calculé Tableau](../assets/uc14-tableau-calculated-field.png)
   1. Sélectionnez **[!UICONTROL OK]**.
1. Sélectionnez la feuille **[!UICONTROL Données]**.
   1. Faites glisser **[!UICONTROL Nom du produit en minuscules]** depuis **[!UICONTROL Tableaux]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**.
   1. Supprimez **[!UICONTROL Nom du produit]** de **[!UICONTROL Lignes]**.
1. Sélectionnez la vue **[!UICONTROL Tableau de bord 1]**.

Votre Tableau Desktop devrait ressembler à ce qui suit.

![Tableau Desktop après la transformation](../assets/uc14-tableau-final.png)

La transformation personnalisée entraîne une mise à jour des requêtes SQL. Consultez l’utilisation de la fonction `LOWER` dans l’exemple SQL ci-dessous :

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB Looker]

Les objets Customer Journey Analytics sont disponibles dans l’interface **[!UICONTROL Explorer]**. Les et sont récupérés dans le cadre de la configuration de votre connexion, projet et modèle dans Looker. Par exemple, **[!UICONTROL cc_data_view]**. Le nom de la vue est identique à l’ID externe que vous avez défini pour votre vue de données dans Customer Journey Analytics. Par exemple, la vue de données avec les **** Titre`C&C - Data View` **[!UICONTROL et]** ID externe`cc_data_view`.

**Dimensions**
Les dimensions de Customer Journey Analytics sont répertoriées sous la forme **[!UICONTROL DIMENSION]** dans le rail de gauche **[!UICONTROL Vue de données Cc]**. La dimension est définie dans la vue de données Customer Journey Analytics. Par exemple, la dimension **[!UICONTROL Nom du produit]** dans Customer Journey Analytics comporte un **[!UICONTROL DIMENSION]** **[!UICONTROL Nom du produit]**, qui est le nom de la dimension dans l’outil de recherche.
Les dimensions de période de Customer Journey Analytics, telles que **[!UICONTROL Jour]**, **[!UICONTROL Semaine]**, **[!UICONTROL Mois]**, etc. sont disponibles sous la forme **[!UICONTROL Date du jour de date]**, **[!UICONTROL Date de la semaine de date]**, **[!UICONTROL Date du mois de date]**, etc.  Lorsque vous utilisez une dimension de période, vous devez sélectionner une définition de date ou d’heure appropriée. Par exemple, **[!UICONTROL Année]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mois]**, **[!UICONTROL Date]**.

**Mesures**
Les mesures provenant de Customer Journey Analytics sont répertoriées sous la forme **[!UICONTROL DIMENSION]** dans le rail de gauche **[!UICONTROL Vue de données Cc]**. Par exemple, la mesure **[!UICONTROL Chiffre d’affaires d’achat]** dans Customer Journey Analytics comporte un **[!UICONTROL DIMENSION]** **[!UICONTROL Chiffre d’affaires d’achat]**. Pour utiliser réellement comme mesure, créez un champ de mesure personnalisé comme illustré dans les exemples ci-dessus ou utilisez le raccourci sur une dimension. Par exemple, **[!UICONTROL ⋮]**, sélectionnez **[!UICONTROL Agrégat]**, puis **[!UICONTROL Somme]**..

**Filtres**
Les filtres que vous définissez dans Customer Journey Analytics sont disponibles dans le champ **[!UICONTROL Nom du filtre]**. Lorsque vous utilisez un champ **[!UICONTROL Nom du filtre]** dans le Looker, vous pouvez spécifier le filtre à utiliser.

**Mesures calculées**
Les mesures calculées que vous définissez dans Customer Journey Analytics sont identifiées par le [!UICONTROL Titre] que vous avez défini pour la mesure calculée. Par exemple, la mesure calculée **[!UICONTROL Nom du produit (Nombre distinct)]** comporte [!UICONTROL Titre] **[!UICONTROL Nom du produit (Nombre distinct)]** et s’affiche sous la forme **[!UICONTROL Cm Nom du produit Nombre distinct]** dans l’outil de recherche.

**périodes**
Les périodes que vous définissez dans Customer Journey Analytics sont disponibles dans le champ **[!UICONTROL Nom de la période]**. Lorsque vous utilisez un champ **[!UICONTROL Nom de la période]**, vous pouvez spécifier la période à utiliser.

**Transformations personnalisées**
Looker fournit une fonctionnalité de transformation personnalisée à l’aide de créateurs de champs personnalisés, comme illustré ci-dessus. Par exemple, vous souhaitez exécuter le cas d’utilisation [Classement sur une seule dimension](#single-dimension-ranked) avec les noms de produits en minuscules.

1. Dans la section **[!UICONTROL Champs personnalisés]** dans le rail de gauche :
   1. Sélectionnez **[!UICONTROL Custom Dimension]** dans le menu déroulant **[!UICONTROL + Ajouter]**.
   1. Saisissez `lower(${cc_data_view.product_name})` dans la zone de texte **[!UICONTROL Expression]**. La syntaxe correcte vous est fournie lorsque vous commencez à saisir `Product Name`.
      ![Exemple de transformation de recherche](../assets/uc14-looker-transformation.png)
   1. Saisissez `product name` comme **[!UICONTROL Nom]**.
   1. Sélectionnez **[!UICONTROL Enregistrer]**.

Vous devriez voir un tableau similaire comme illustré ci-dessous.

![Résultat de la transformation de l’observateur](../assets/uc14-looker-result.png)


La transformation personnalisée entraîne une mise à jour des requêtes SQL. Consultez l’utilisation de la fonction `LOWER` dans l’exemple SQL ci-dessous :

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!TAB Notebook Jupyter]

Les objets Customer Journey Analytics (dimensions, mesures, filtres, mesures calculées et périodes) sont disponibles dans le cadre des requêtes Embedded SQL que vous créez. Voir les exemples précédents.

**Transformations personnalisées**

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   data = %sql SELECT LOWER(product_category) AS `Product Category`, COUNT(*) AS EVENTS \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc13-jupyter-results.png)

La requête est exécutée par l’extension BI, comme défini dans le notebook Jupyter.

>[!TAB RStudio]

Les composants Customer Journey Analytics (dimensions, mesures, filtres, mesures calculées et périodes) sont disponibles sous la forme d’objets nommés similaires dans la langue R. Reportez-vous aux composants qui utilisent le composant. Voir les exemples précédents.

**Transformations personnalisées**

1. Saisissez les instructions suivantes entre ` ```{r} ` et ` ``` ` dans un nouveau bloc.

   ```R
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange <= "2024-01-01") %>%
      mutate(d2=lower(product_category)) %>%
      group_by(d2) %>%
      count() %>%
      arrange(d2, .by_group = FALSE)
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc13-rstudio-results.png)

La requête générée par RStudio à l’aide de l’extension BI inclut `lower`, ce qui implique que la transformation personnalisée est exécutée par RStudio et l’extension BI.

```sql
SELECT "d2", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*, lower("product_category") AS "d2"
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" <= '2024-01-01')
) AS "q01"
GROUP BY "d2"
ORDER BY "d2"
LIMIT 1000
```

>[!ENDTABS]

+++

