---
title: Plusieurs classements Dimension
description: Cas d’utilisation avec classement de dimensions multiples pour l’extension BI dans divers outils BI dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 1%

---

# Classement de plusieurs dimensions


Dans ce cas d’utilisation, vous souhaitez afficher un tableau qui répartit le chiffre d’affaires et les achats pour les noms de produits au sein des catégories de produits sur 2023. En outre, vous souhaitez utiliser des visualisations pour illustrer les contributions de la distribution par catégorie de produits et de nom de produit au sein de chaque catégorie de produits.

+++ Customer Journey Analytics

Exemple de panneau **[!UICONTROL Classement multiple par Dimension]** pour le cas d’utilisation :

![Panneau Customer Journey Analytics avec classement Dimension multiple](../assets/cja-multiple-dimension-ranked.png)

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

1. Pour vous assurer que la période s’applique à toutes les visualisations, effectuez un glisser-déposer de **[!UICONTROL daterangeday]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Filtres sur cette page]**.
   1. Sélectionnez le **[!UICONTROL daterangeday is (All)]** dans **[!UICONTROL Filtres sur cette page]**.
   1. Sélectionnez **[!UICONTROL Date relative]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL se trouve dans les dernières]** `1` **[!UICONTROL années civiles]**.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL datarangeday]**.
   1. Sélectionnez **[!UICONTROL product_category]**.
   1. Sélectionnez **[!UICONTROL product_name]**.
   1. Sélectionnez **[!UICONTROL sum purchase_revenue]**
   1. Sélectionnez **[!UICONTROL somme des achats]**

1. Pour modifier le graphique à barres verticales en tableau, assurez-vous que le tableau est sélectionné et sélectionnez **[!UICONTROL Matrice]** dans le volet **[!UICONTROL Visualisations]**.
   * Faites glisser **[!UICONTROL product_name]** depuis **[!UICONTROL Columns]** et déposez le champ sous **[!UICONTROL product_category]**y dans **[!UICONTROL Rows]** dans le volet **[!UICONTROL Visualisation]**.

1. Pour limiter le nombre de produits affichés dans le tableau, sélectionnez **[!UICONTROL product_name is (All)]** dans le volet **[!UICONTROL Filtres]**.

   1. Sélectionnez **[!UICONTROL Filtrage avancé]**.
   1. Sélectionnez **[!UICONTROL Type de filtre]** **[!UICONTROL Top N]** **[!UICONTROL Afficher les éléments]** **[!UICONTROL Top]** `15` **[!UICONTROL Par valeur]**.
   1. Faites glisser **[!UICONTROL purchases]** du volet **[!UICONTROL Données]** sur le **[!UICONTROL Ajouter des champs de données ici]**.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

1. Pour améliorer la lisibilité, sélectionnez **[!UICONTROL Affichage]** dans le menu supérieur, puis sélectionnez **[!UICONTROL Page vue]** > **[!UICONTROL Taille réelle]** et redimensionnez la visualisation du tableau.

1. Pour ventiler chaque catégorie dans le tableau, sélectionnez **[!UICONTROL +]** au niveau de la catégorie de produits. Votre bureau Power BI doit se présenter comme suit :

   ![Tableau de matrice de classement de plusieurs dimensions de bureau Power BI](../assets/uc6-powerbi-data.png)

1. Sélectionnez **[!UICONTROL Accueil]** dans le menu supérieur, puis sélectionnez **[!UICONTROL Nouveau visuel]**. Un nouvel élément visuel est ajouté à votre rapport.

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL product_category]**.
   1. Sélectionnez **[!UICONTROL product_name]**.
   1. Sélectionnez **[!UICONTROL chiffre_d’affaires_achat]**.

1. Pour modifier le visuel, sélectionnez le graphique à barres et sélectionnez **[!UICONTROL Treemap]** dans le volet **[!UICONTROL Visualisations]**.
1. Assurez-vous que **[!UICONTROL product_category]** est répertorié sous **[!UICONTROL Category]** et **[!UICONTROL product_name]** est répertorié sous **[!UICONTROL Details]** dans le volet **[!UICONTROL Visualisations]**.

   Votre bureau Power BI doit se présenter comme suit :

   ![Arborescence Classement de plusieurs dimensions de l’appli de bureau Power BI](../assets/uc6-powerbi-treemap.png)

1. Sélectionnez **[!UICONTROL Accueil]** dans le menu supérieur, puis sélectionnez **[!UICONTROL Nouveau visuel]**. Un nouvel élément visuel est ajouté à votre rapport.

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL product_category]**.
   1. Sélectionnez **[!UICONTROL chiffre_d’affaires_achat]**.
   1. Sélectionnez **[!UICONTROL achat]**.

1. Dans le volet **[!UICONTROL Visualisations]** :
   1. Pour modifier la visualisation, sélectionnez **[!UICONTROL Graphique linéaire et histogramme empilé]**.
   1. Faites glisser **[!UICONTROL sum_of_purchases]** de **[!UICONTROL axe Y de colonne]** vers **[!UICONTROL axe Y de ligne]**.

1. Dans le rapport, redistribuer les visualisations individuelles.

   Votre bureau Power BI doit se présenter comme suit :

   ![Power BI Desktop Multiple Dimensions Classé final](../assets/uc6-powerbi-final.png)


>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Dates relatives]**, **[!UICONTROL Années]** et spécifiez **[!UICONTROL Année précédente]**. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc6-tableau-filter.png)

   1. Faites glisser **[!UICONTROL Catégorie de produits]** et déposez-la en regard de **[!UICONTROL Colonnes]**.
   1. Faites glisser **[!UICONTROL Chiffre d’affaires d’achat]** et déposez-le en regard de **[!UICONTROL Lignes]**. La valeur devient **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]**.
   1. Faites glisser Achats et déposez-les en regard de **[!UICONTROL Lignes]**. La valeur devient **[!UICONTROL SUM(Purchases)]**.
   1. Sélectionnez **[!UICONTROL SOMME(Achats)]** puis, dans le menu déroulant, sélectionnez **[!UICONTROL Axe double]**.
   1. Sélectionnez **[!UICONTROL SOMME(Achats)]** dans **[!UICONTROL Marques]** et sélectionnez **[!UICONTROL Ligne]** dans le menu déroulant.
   1. Sélectionnez **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]** dans **[!UICONTROL Marques]** et sélectionnez **[!UICONTROL Barre]** dans le menu déroulant.
   1. Sélectionnez **[!UICONTROL Vue entière]** dans le menu **[!UICONTROL Ajuster]**.
   1. Sélectionnez le titre **[!UICONTROL Chiffre d’affaires d’achat]** dans le graphique et assurez-vous que le chiffre d’affaires d’achat est dans l’ordre croissant.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Catégorie Classement Multidimensionnel Tableau Desktop](../assets/uc6-tableau-category.png)

1. Renommez la feuille **[!UICONTROL Feuille 1]** actuelle en `Category`.
1. Sélectionnez **[!UICONTROL Nouvelle feuille de calcul]** pour créer une feuille et la renommer en `Data`.

   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Dates relatives]**, **[!UICONTROL Années]** et spécifiez **[!UICONTROL Année précédente]**. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser **[!UICONTROL Chiffre d’affaires d’achat]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Colonnes]**. La valeur devient **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]**.
   1. Faites glisser **[!UICONTROL Achat]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Colonnes]**, en regard de **[!UICONTROL Chiffre d’affaires d’achat]**. La valeur devient **[!UICONTROL SUM(Purchases)]**.
   1. Faites glisser **[!UICONTROL Catégorie de produits]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Lignes]**.
   1. Faites glisser **[!UICONTROL Nom du produit]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Lignes]**, en regard de **[!UICONTROL Catégorie de produits]**.
   1. Pour transformer les deux barres horizontales en tableau, sélectionnez **[!UICONTROL Tableau de texte]** dans **[!UICONTROL Afficher]**.
   1. Pour limiter le nombre de produits, sélectionnez **[!UICONTROL Achats]** dans **[!UICONTROL Valeurs de mesure]**. Dans le menu déroulant, sélectionnez **[!UICONTROL Filtrer]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Achats\]]**, sélectionnez **[!UICONTROL Au moins]** et saisissez `7000`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop - Données à classement Dimension multiple](../assets/uc6-tableau-data.png)

1. Sélectionnez **[!UICONTROL Nouvelle feuille de calcul]** pour créer une feuille et la renommer en **[!UICONTROL Treemap]**.
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Dates relatives]**, **[!UICONTROL Années]** et spécifiez **[!UICONTROL Année précédente]**. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser **[!UICONTROL Chiffre d’affaires d’achat]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Lignes]**. Les valeurs sont remplacées par **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]**.
   1. Faites glisser **[!UICONTROL Achat]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Lignes]**, en regard de **[!UICONTROL Chiffre d’affaires d’achat]**. La valeur devient **[!UICONTROL SUM(Purchases)]**.
   1. Faites glisser **[!UICONTROL Catégorie de produits]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Colonnes]**.
   1. Faites glisser **[!UICONTROL Nom du produit]** du volet **[!UICONTROL Données]** vers **[!UICONTROL Colonnes]**.
   1. Pour remplacer les deux graphiques à barres verticales par un Treemap, sélectionnez **[!UICONTROL Treemap]** dans **[!UICONTROL Afficher]**.
   1. Pour limiter le nombre de produits, sélectionnez **[!UICONTROL Achats]** dans **[!UICONTROL Valeurs de mesure]**. Dans le menu déroulant, sélectionnez **[!UICONTROL Filtrer]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Achats\]]**, sélectionnez **[!UICONTROL Au moins]** et saisissez `7000`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop - Données à classement Dimension multiple](../assets/uc6-tableau-treemap.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Catégorie]** de l&#39;étagère **[!UICONTROL Feuilles]** vers la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Treemap]** de l’étagère **[!UICONTROL Feuilles]** sous la feuille **[!UICONTROL Catégorie]** dans la vue **[!UICONTROL Tableau de bord 1]**.
   1. Faites glisser et déposez la feuille **[!UICONTROL Data]** de l’étagère **[!UICONTROL Sheets]** sous la feuille **[!UICONTROL Treemap]** dans la vue **[!UICONTROL Tableau de bord 1]**.
   1. Redimensionnez chacune des feuilles de la vue.

   La vue de votre **[!UICONTROL Tableau de bord 1]** doit se présenter comme suit :

   ![Tableau de bord Tableau Desktop 1](../assets/uc6-tableau-final.png)


>[!TAB Looker]

1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2024/01/01]**.
1. Dans la section **[!UICONTROL ‣ Cr Vue des données]** rail de gauche :
   1. Sélectionnez **[!UICONTROL Catégorie de produits]**.
   1. Sélectionnez **[!UICONTROL Nom du produit]**.
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
   1. Sélectionnez **[!UICONTROL Mesure personnalisée]** une fois de plus dans le menu déroulant **[!UICONTROL + Ajouter]**. Dans la boîte de dialogue **[!UICONTROL Créer une mesure personnalisée]** :
      1. Sélectionnez **[!UICONTROL Achats]** dans le menu déroulant **[!UICONTROL Champ à mesurer]**.
      1. Sélectionnez **[!UICONTROL Somme]** dans le menu déroulant **[!UICONTROL Type de mesure]**.
      1. Saisissez un nom de champ personnalisé pour **[!UICONTROL Nom]**. Par exemple : `Sum of Purchases`.
      1. Sélectionnez l’onglet **[!UICONTROL Détails du champ]**.
      1. Sélectionnez **[!UICONTROL Décimales]** dans le menu déroulant **[!UICONTROL Format]** et assurez-vous que `0` est saisi dans **[!UICONTROL Décimales]**.
      1. Sélectionnez **[!UICONTROL Enregistrer]**.
   1. Les deux champs sont automatiquement ajoutés à la vue de données.
1. Dans la section **[!UICONTROL Filtres]**, sélectionnez **[!UICONTROL + Filtre]**. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]**. Sélectionnez **[!UICONTROL Champs personnalisés]** puis **[!UICONTROL Chiffre d’affaires d’achat]**.
1. Sélectionnez **[!UICONTROL est >]** et saisissez `800000` pour limiter les résultats.
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]** pour afficher la visualisation Ligne.
1. Sélectionnez **[!UICONTROL Modifier]** dans **[!UICONTROL Visualisation]** pour mettre à jour la visualisation. Dans la boîte de dialogue contextuelle, réalisez les actions suivantes :
   1. Sélectionnez l’onglet **[!UICONTROL Tracer]**.
   1. Faites défiler vers le bas et sélectionnez **[!UICONTROL Modifier la configuration du graphique]**.
   1. Modifiez le fichier JSON dans **[!UICONTROL Configuration du graphique (remplacement)]** comme dans la capture d’écran ci-dessous, puis sélectionnez **[!UICONTROL Aperçu]**.

      ![Configuration de la visualisation de recherche](../assets/uc6-looker-visualization.png)

   1. Sélectionnez **[!UICONTROL Appliquer]**.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) en regard de **[!UICONTROL Modifier]** pour masquer la boîte de dialogue contextuelle

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Tendance quotidienne des résultats de recherche](../assets/uc6-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_category AS `Product Category`, product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1, 2 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby(['Product Category', 'Product Name'], as_index=False).sum()
   plt.figure(figsize=(8, 8))
   sns.scatterplot(x='Product Category', y='Product Name', size='Purchase Revenue', sizes=(10, 200), hue='Purchases', palette='husl', data=df)
   plt.show()
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc6-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ```{r} ` et ` ``` ` dans un nouveau bloc.

   ```R
   ## Multiple dimensions ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_category, product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc6-rstudio-results.png)


>[!ENDTABS]

+++
