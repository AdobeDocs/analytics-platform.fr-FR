---
title: Tri
description: Cas d’utilisation de tri pour l’extension BI dans divers outils BI de Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# Tri


Dans ce cas d’utilisation, vous souhaitez générer des rapports sur le chiffre d’affaires des achats et les achats pour les noms de produit au cours du mois de janvier 2023, triés par ordre de chiffre d’affaires d’achat décroissant.

+++ Customer Journey Analytics

Exemple de panneau **[!UICONTROL Tri]** pour le cas d’utilisation :

Panneau de tri de Customer Journey Analytics ![](../assets/cja-sort.png)

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL daterange]**.
   1. Sélectionnez **[!UICONTROL product_name]**.
   1. Sélectionnez **[!UICONTROL sum purchase_revenue]**.
   1. Sélectionnez **[!UICONTROL somme des achats]**.

1. Dans le volet **[!UICONTROL Filtres]** :
   1. Sélectionnez **[!UICONTROL daterange est (tout)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est activée ou ultérieure]** `1/1/2023` **[!UICONTROL Et]** **[!UICONTROL est antérieure]** `2/1/2023`.

1. Dans le volet Visualisations :
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer daterange des colonnes.
   1. Faites glisser **[!UICONTROL Somme des revenus_achat]** au bas des éléments **[!UICONTROL Colonne]**.

1. Dans le rapport, sélectionnez **[!UICONTROL Somme des revenus_d’achat]** pour trier le tableau par ordre décroissant de revenus d’achat.

   Votre bureau Power BI doit se présenter comme suit :

   ![Bureau Power BI Utilisant Des Noms De Plage De Dates À Filtrer](../assets/uc11-powerbi-final.png)

La requête exécutée par Power BI Desktop à l’aide de l’extension BI n’inclut pas d’instruction `sort`. L’absence d’instruction `sort` implique que le tri est exécuté côté client.

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** vers le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Période]**, puis sélectionnez `01/01/2023` - `1/2/2023`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser **[!UICONTROL Nom du produit]** de la liste **[!UICONTROL Tableaux]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**.
   1. Faites glisser l’entrée **[!UICONTROL Achats]** de la liste **[!UICONTROL Tableaux]** et déposez-la dans le champ en regard de **[!UICONTROL Colonnes]**. La valeur devient **[!UICONTROL SUM(Purchases)]**.
   1. Faites glisser l’entrée **[!UICONTROL Chiffre d’affaires d’achat]** de la liste **[!UICONTROL Tableaux]** et déposez-la dans le champ en regard de **[!UICONTROL Colonnes]**, en regard de **[!UICONTROL SOMME(Achats)]**. La valeur devient **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]**.
   1. Sélectionnez **[!UICONTROL Tableau de texte]** dans **[!UICONTROL Afficher]**.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.
   1. Sélectionnez l’en-tête de colonne **[!UICONTROL Chiffre d’affaires d’achat]** et triez le tableau de cette colonne par ordre décroissant.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop Sort](../assets/uc11-tableau-final.png)

La requête exécutée par Tableau Desktop à l&#39;aide de l&#39;extension BI n&#39;inclut pas d&#39;instruction `sort`. L’absence de cette instruction `sort` implique que le tri est exécuté côté client.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB Looker]

1. Dans l’interface **[!UICONTROL Explorer]** de la recherche, actualisez votre connexion. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Effacer le cache et actualiser]**.
1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2023/02/01]**.
1. Dans la section **[!UICONTROL Cc Vue des données]** du rail de gauche, sélectionnez **[!UICONTROL Nom du produit]**.
1. Dans la section **[!UICONTROL Champs personnalisés]** dans le rail de gauche :
   1. Sélectionnez **[!UICONTROL Mesure personnalisée]** dans le menu déroulant **[!UICONTROL + Ajouter]**.
   1. Dans la boîte de dialogue **[!UICONTROL Créer une mesure personnalisée]** :
      1. Sélectionnez **[!UICONTROL Chiffre d’affaires d’achat]** dans le menu déroulant **[!UICONTROL Champ à mesurer]**.
      1. Sélectionnez **[!UICONTROL Somme]** dans le menu déroulant **[!UICONTROL Type de mesure]**.
      1. Saisissez un nom de champ personnalisé pour **[!UICONTROL Nom]**. Par exemple : `Sum of Purchase Revenue`.
      1. Sélectionnez l’onglet **[!UICONTROL Détails du champ]**.
      1. Sélectionnez **[!UICONTROL Décimales]** dans le menu déroulant **[!UICONTROL Format]** et assurez-vous que `0` est saisi dans **[!UICONTROL Décimales]**.
         ![Champ de mesure personnalisé de recherche](../assets/uc5-looker-customfield.png)
      1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Veillez à sélectionner **[!UICONTROL ↓]** (**[!UICONTROL Décroissant, Ordre de tri : 1]**) dans la colonne **[!UICONTROL Chiffre d’affaires d’achat]**.
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]**.

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Nombre de recherches distinct](../assets/uc11-looker-result.png)


La requête générée par Looker à l’aide de l’extension BI inclut `ORDER BY`, ce qui implique que le tri est exécuté via Looker et l’extension BI.

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2024-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 5;
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc11-jupyter-results.png)

La requête est exécutée par l’extension BI, comme défini dans le notebook Jupyter.


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ` ``{r} ` et ` `` ` ` dans un nouveau bloc.

   ```R
   ## Dimension 1 Sorted
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc11-rstudio-results.png)

La requête générée par RStudio à l’aide de l’extension BI inclut `ORDER BY`, ce qui implique que la commande est appliquée via RStudio et l’extension BI.

```sql
SELECT
  "product_name",
  SUM("purchase_revenue") AS "purchase_revenue",
  SUM("purchases") AS "purchases"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2023-02-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "purchase_revenue" DESC
LIMIT 1000
```

>[!ENDTABS]

+++
