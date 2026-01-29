---
title: Compter les dimensions de valeurs distinctes
description: Cas d’utilisation des dimensions Comptage de valeurs distinctes pour l’extension BI dans divers outils BI de Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# Compter les dimensions de valeurs distinctes


Dans ce cas d’utilisation, vous souhaitez obtenir le nombre distinct de noms de produits qui ont fait l’objet de rapports en janvier 2023.

+++ Customer Journey Analytics

Pour générer des rapports sur un nombre distinct de noms de produit, configurez une mesure calculée dans Customer Journey Analytics, avec les **&#x200B;**&#x200B;Titre`Product Name (Count Distinct)` **[!UICONTROL et]** Id externe`product_name_count_distinct`.

![Mesure calculée Nom du produit Customer Journey Analytics (nombre distinct)](../assets/cja-calc-metric-distinct-count-product-names.png)

Vous pouvez ensuite utiliser cette mesure dans un exemple de panneau **[!UICONTROL Compter les valeurs Dimension distinctes]** pour le cas d’utilisation :

![Valeurs De Nombre Distinct Customer Journey Analytics](../assets/cja-count-distinct-dimension-values.png)

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

1. Pour vous assurer que la période s’applique à toutes les visualisations, effectuez un glisser-déposer de **[!UICONTROL daterangeday]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Filtres]** sur cette page.
   1. Sélectionnez le **[!UICONTROL daterangeday is (All)]** dans **[!UICONTROL Filtres sur cette page]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est activée ou ultérieure]** `1/1/2023` **[!UICONTROL Et]** **[!UICONTROL est antérieure]** `2/1/2023`.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL datarangeday]**.
   1. Sélectionnez **[!UICONTROL sum cm_product_name_count_distinct]**, qui est la mesure calculée définie dans Customer Journey Analytics.

1. Pour modifier le graphique à barres verticales en tableau, assurez-vous que le graphique est sélectionné et sélectionnez **[!UICONTROL Tableau]** dans le volet **[!UICONTROL Visualisations]**.

   Votre bureau Power BI doit se présenter comme suit :

   ![Tableau distinct de décompte multiple de bureau Power BI](../assets/uc7-powerbi-table.png)

1. Sélectionnez la visualisation du tableau. Dans le menu contextuel, sélectionnez **[!UICONTROL Copier]** > **[!UICONTROL Copier visuel]**.
1. Collez la visualisation à l’aide de **[!UICONTROL ctrl+v]**. La copie exacte de la visualisation chevauche la visualisation originale. Déplacez-le vers la droite dans la zone du rapport.
1. Pour modifier la visualisation copiée d’un tableau en carte, sélectionnez **[!UICONTROL Carte]** dans **[!UICONTROL Visualisations]**.

   Votre bureau Power BI doit se présenter comme suit :

   ![Tableau distinct de décompte multiple de bureau Power BI](../assets/uc7-powerbi-final.png)

Vous pouvez également utiliser la fonctionnalité Comptage distinct de Power BI.

1. Sélectionnez la dimension **[!UICONTROL product_name]**.
1. Appliquez la fonction **[!UICONTROL Count (Distinct)]** sur la dimension **[!UICONTROL product_name]** dans **[!UICONTROL Columns]**.

   ![Nombre de Power BI distinct](../assets/uc7-powerbi-alternative.png)



>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Période]**, puis sélectionnez `01/01/2023` - `31/1/2023`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser **[!UICONTROL Cm Product Name Count Distinct]** vers **[!UICONTROL Rows]**. La valeur devient **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Ce champ correspond à la mesure calculée que vous avez définie dans Customer Journey Analytics.
   1. Faites glisser **[!UICONTROL Daterangeday]** et déposez-le en regard de **[!UICONTROL Columns]**. Sélectionnez **[!UICONTROL Daterangeday]** et dans le menu déroulant, sélectionnez **[!UICONTROL Day]**.
   1. Pour modifier la visualisation des lignes en tableau, sélectionnez **[!UICONTROL Tableau de texte]** dans **[!UICONTROL Me montrer]**.
   1. Sélectionnez **[!UICONTROL Permuter les lignes et les colonnes]** dans la barre d’outils.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc7-tableau-data.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une deuxième feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Data`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l&#39;onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Card`.

1. Vérifiez que vous avez sélectionné la vue **[!UICONTROL Carte]**.
1. Sélectionnez **[!UICONTROL DAY(Daterangeday)]** puis, dans le menu déroulant, sélectionnez **[!UICONTROL Month]**. La valeur devient **[!UICONTROL MONTH(Daterangeday)]**.
1. Sélectionnez **[!UICONTROL SOMME(Nombre de noms de produits Cm distincts)]** dans **[!UICONTROL Marques]**, puis dans le menu déroulant, sélectionnez **[!UICONTROL Format]**.
1. Pour modifier la taille de la police, dans le volet **[!UICONTROL Format SUM(CM Product Name Count Distinct)]**, sélectionnez **[!UICONTROL Font]** dans **[!UICONTROL Default]** et sélectionnez **[!UICONTROL 72]**.
1. Pour aligner le nombre, sélectionnez **[!UICONTROL Automatique]** en regard de **[!UICONTROL Alignement]** et définissez **[!UICONTROL Horizontal]** sur centré.
1. Pour utiliser des nombres entiers, sélectionnez **[!UICONTROL 123.456]** en regard de **[!UICONTROL Nombres]** et sélectionnez **[!UICONTROL Nombre (Personnalisé)]**. Définissez **[!UICONTROL Nombre de décimales]** sur `0`.

   Votre Tableau Desktop devrait ressembler à ce qui suit.

   ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc7-tableau-card.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Carte]** de l’étagère **[!UICONTROL Feuilles]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Data]** de l’étagère **[!UICONTROL Sheets]** sous la feuille **[!UICONTROL Card]** dans la vue **[!UICONTROL Dashboard 1]**.

   La vue de votre **[!UICONTROL Tableau de bord 1]** doit se présenter comme suit :

   ![Tableau de bord Tableau Desktop 1](../assets/uc7-tableau-final.png)


Vous pouvez également utiliser la fonctionnalité Comptage distinct de Tableau Desktop.

1. Utilisez **[!UICONTROL Nom du produit]** au lieu de **[!UICONTROL Nombre de noms de produit Cm distincts]**.
1. Appliquez **[!UICONTROL Mesure]** > **[!UICONTROL Nombre (distinct)]** sur **[!UICONTROL Nom du produit]** en **[!UICONTROL Marques]**.

   ![Nombre de tableaux distinct](../assets/uc7-tableau-alternative.png)


>[!TAB Looker]

1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2023/02/01]**.
1. Dans la section **[!UICONTROL ‣ Cr Vue des données]** rail de gauche :
   1. Sélectionnez **[!UICONTROL Date de plage]**, puis **[!UICONTROL Date]**.
   1. Sélectionnez **[!UICONTROL Agréger ‣ Comptage distinct]** dans le menu contextuel **⋮ Plus** sur **[!UICONTROL Nom du produit]**.
      ![Menu contextuel du nom du produit de recherche](../assets/uc7-looker-count-distinct.png)
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]** puis sélectionnez 6︎⃣ dans la barre d’outils pour afficher une visualisation à une seule valeur.

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Nombre de recherches distinct](../assets/uc7-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc7-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ` ``{r} ` et ` `` ` ` dans un nouveau bloc.

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++

