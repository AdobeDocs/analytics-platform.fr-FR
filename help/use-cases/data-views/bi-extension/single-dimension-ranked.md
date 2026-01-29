---
title: Classement Dimension unique
description: Cas d’utilisation avec classement à une seule dimension pour l’extension BI dans divers outils de BI dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 1%

---

# Classement sur une seule dimension


Dans ce cas d’utilisation, vous souhaitez afficher un tableau et une visualisation simple à barres qui montre les achats et le chiffre d’affaires des achats pour les noms de produits sur 2023.

+++ Customer Journey Analytics

Exemple de panneau **[!UICONTROL Classement sur un seul Dimension]** pour le cas d’utilisation :

![Visualisation de classement sur une seule dimension de Customer Journey Analytics](../assets/cja-single-dimension-ranked.png)

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

   Un tableau vide n’affiche que les en-têtes de colonne pour l’élément sélectionné. Pour une meilleure visibilité, agrandissez la visualisation.

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez l’**[!UICONTROL daterange is (All)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Date relative]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL se trouve dans les dernières]** `1` **[!UICONTROL années civiles]**.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

   Le tableau est mis à jour avec le filtre **[!UICONTROL daterange]** appliqué.

1. Dans le volet **[!UICONTROL Visualisation]** :

   1. Utilisez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer **[!UICONTROL daterange]** de **[!UICONTROL Columns]**.
   1. Effectuez un glisser-déposer **[!UICONTROL Somme des achats_revenus]** sous **[!UICONTROL Somme des achats]** dans **[!UICONTROL Colonnes]**.

1. Dans la visualisation Tableau :

   1. Sélectionnez **[!UICONTROL Somme des revenus_d’achat]** pour trier les noms de produit dans l’ordre de revenus d’achat décroissant. Votre bureau Power BI doit se présenter comme suit :

   ![Statut du tableau du cas d’utilisation 5 de Power BI Desktop](../assets/uc5-pbi-table.png)

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez **[!UICONTROL product_name is (All)]**.
   1. Définissez **[!UICONTROL Type de filtre]** sur **[!UICONTROL N en haut]**.
   1. Définissez le filtre sur **[!UICONTROL Afficher les éléments]** **[!UICONTROL En haut]** `10` **[!UICONTROL Par valeur]**.
   1. Effectuez un glisser-déposer de **[!UICONTROL purchase_revenue]** dans **[!UICONTROL Par valeur]** **[!UICONTROL Ajoutez des champs de données ici]**.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

   Le tableau est mis à jour avec les valeurs des recettes d’achat en synchronisation avec la visualisation du tableau à structure libre dans Analysis Workspace.

1. Dans le volet **[!UICONTROL Visualisations]** :

   1. Sélectionnez la visualisation **[!UICONTROL Graphique en courbes et histogramme empilé]**.

   Une visualisation sous forme de graphiques en courbes et en colonnes empilées remplace le tableau tout en utilisant les mêmes données que le tableau.

1. Effectuez un glisser-déposer **[!UICONTROL achats]** sur **[!UICONTROL Axe Y de la ligne]** dans le volet **[!UICONTROL Visualisations]**.

   Le graphique en courbes et en colonnes empilées est mis à jour. Votre bureau Power BI doit se présenter comme suit :

   ![Graphique du cas d’utilisation 5 de Power BI Desktop](../assets/uc5-pbi-chart.png)

1. Dans la visualisation sous forme de graphique en courbes et histogramme empilé :

   1. Sélectionnez ![Plus](/help/assets/icons/More.svg).
   1. Dans le menu contextuel, sélectionnez **[!UICONTROL Afficher sous forme de tableau]**.

   La vue principale est mise à jour pour afficher à la fois une visualisation en ligne et un tableau.

   ![Visualisation quotidienne finale des tendances du cas d’utilisation 2 de Power BI Desktop](../assets/uc5-pbi-final.png)

>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Période]** et spécifiez une période de `01/01/2023` - `31/12/2023`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.

      ![Filtre Tableau Desktop](../assets/uc5-tableau-filter.png)

   1. Effectuez un glisser-déposer de **[!UICONTROL Nom du produit]** depuis la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**.
   1. Effectuez un glisser-déposer **[!UICONTROL Achats]** depuis la liste **[!UICONTROL Tableaux (*Noms des mesures*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**. La valeur est automatiquement convertie en **[!UICONTROL SUM(Purchases)]**.
   1. Effectuez un glisser-déposer **[!UICONTROL Chiffre d’affaires d’achat]** depuis la liste **[!UICONTROL Tableaux (*Noms de mesures*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ à côté de **[!UICONTROL Colonnes]** et à gauche de **[!UICONTROL SUM(Achats)]**. La valeur est automatiquement convertie en **[!UICONTROL SOMME(chiffre d’affaires d’achat)]**.
   1. Pour classer les deux graphiques dans l’ordre décroissant des recettes d’achat, placez le curseur sur le titre **[!UICONTROL Recettes d’achat]** et sélectionnez l’icône de tri.
   1. Pour limiter le nombre d’entrées dans les graphiques, sélectionnez **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]** dans **[!UICONTROL Lignes]**, puis dans le menu déroulant, sélectionnez **[!UICONTROL Filtrer]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Chiffre d’affaires d’achat\]]**, sélectionnez **[!UICONTROL Plage de valeurs]** et saisissez les valeurs appropriées. Par exemple : `1,000,000` - `2,000,000`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Pour convertir les deux graphiques à barres en graphique à double combinaison, sélectionnez **[!UICONTROL SOMME(Achats)]** dans **[!UICONTROL Lignes]** et dans le menu déroulant, sélectionnez **[!UICONTROL Axe double]**. Les graphiques à barres se transforment en graphique de dispersion.
   1. Pour modifier le graphique de dispersion en graphique à barres :
      1. Sélectionnez **[!UICONTROL SOMME(Achats)]** dans la zone **[!UICONTROL Marques]** et sélectionnez **[!UICONTROL Ligne]** dans le menu déroulant.
      1. Sélectionnez **[!UICONTROL SOMME(Chiffre d’affaires d’achat)]** dans la zone **[!UICONTROL Marques]** et sélectionnez **[!UICONTROL Barre]** dans le menu déroulant.

   Votre Tableau Desktop devrait ressembler à ce qui suit.

   ![Graphique Tableau Desktop](../assets/uc5-tableau-graph.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une deuxième feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Data`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l&#39;onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Graph`.
1. Assurez-vous que la feuille **[!UICONTROL Data]** est sélectionnée.
   1. Sélectionnez **[!UICONTROL Afficher]** en haut à droite, puis sélectionnez **[!UICONTROL Tableau de texte]** (visualisation en haut à gauche) pour modifier le contenu des deux graphiques en tableau.
   1. Pour commander les recettes d’achat par ordre décroissant, passez la souris sur **[!UICONTROL Recettes d’achat]** dans le tableau, puis sélectionnez ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Sélectionnez **[!UICONTROL Vue entière]** dans le menu déroulant **[!UICONTROL Ajuster]**.

   Votre Tableau Desktop devrait ressembler à ce qui suit.

   ![Données Tableau Desktop](../assets/uc5-tableau-data.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Graph]** de l’étagère **[!UICONTROL Feuilles]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Données]** de l’étagère **[!UICONTROL Feuilles]** sous la feuille **[!UICONTROL Graphique]** vers la vue **[!UICONTROL Tableau de bord 1]**.
   1. Sélectionnez la feuille **[!UICONTROL Données]** dans la vue et modifiez **[!UICONTROL Vue entière]** en **[!UICONTROL Fixe largeur]**.

   La vue de votre **[!UICONTROL Tableau de bord 1]** doit se présenter comme suit :

   ![Tableau de bord Tableau Desktop 1](../assets/uc5-tableau-dashboard.png)



>[!TAB Looker]

1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2024/01/01]**.
1. Dans la section **[!UICONTROL Cc Vue des données]** du rail de gauche, sélectionnez **[!UICONTROL Nom du produit]**.
1. Dans la section **[!UICONTROL Champs personnalisés]** dans le rail de gauche :
   1. Sélectionnez **[!UICONTROL Mesure personnalisée]** dans le menu déroulant **[!UICONTROL + Ajouter]**.
   1. Dans la boîte de dialogue **[!UICONTROL Créer une mesure personnalisée]** :
      1. Sélectionnez **[!UICONTROL Chiffre d’affaires d’achat]** dans le menu déroulant **[!UICONTROL Champ à mesurer]**.
      1. Sélectionnez **[!UICONTROL Somme]** dans le menu déroulant **[!UICONTROL Type de mesure]**.
      1. Saisissez un nom de champ personnalisé pour **[!UICONTROL Nom]**. Par exemple : `Purchase Revenue`.
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
1. Sélectionnez **[!UICONTROL + Filtre]** pour ajouter un autre **[!UICONTROL Filtres]** et pour limiter les données.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]**, sélectionnez **[!UICONTROL Champs personnalisés]**, puis **[!UICONTROL Chiffre d’affaires d’achat]**.
1. Effectuez les sélections appropriées et saisissez les valeurs proposées afin que le filtre lise **[!UICONTROL est compris entre inclusifs]** `1000000` **[!UICONTROL ET]** `2000000`.
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]** pour afficher la visualisation Ligne.
1. Sélectionnez **[!UICONTROL Modifier]** dans **[!UICONTROL Visualisation]** pour mettre à jour la visualisation. Dans la boîte de dialogue contextuelle, réalisez les actions suivantes :
   1. Sélectionnez l’onglet **[!UICONTROL Série]**.
   1. Faites défiler la page vers le bas pour afficher **[!UICONTROL Achats]** et remplacez **[!UICONTROL Type]** par **[!UICONTROL Ligne]**.
   1. Sélectionnez l’onglet **[!UICONTROL Y]**.
   1. Faites glisser **[!UICONTROL Achats]** du conteneur **[!UICONTROL Gauche 1]** jusqu’à l’emplacement où il est indiqué **[!UICONTROL *Faites glisser la série ici pour créer un nouvel axe gauche *]**. Cette action crée un conteneur**[!UICONTROL  Left 2 ]**.
      ![Configuration de la visualisation de recherche](../assets/uc5-looker-visualization.png)
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) en regard de **[!UICONTROL Modifier]** pour masquer la boîte de dialogue contextuelle

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Tendance quotidienne des résultats de recherche](../assets/uc5-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Purchase Revenue', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc5-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ```{r} ` et ` ``` ` dans un nouveau bloc.

   ```R
   library(tidyr)
   
   ## Single dimension ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases)) %>%
      arrange(product_name, .by_group = FALSE)
   dfV <- df %>%
      head(5)
   ggplot(dfV, aes(x = purchase_revenue, y = product_name)) +
      geom_col(position = "dodge") +
      geom_text(aes(label = purchase_revenue), vjust = -0.5)
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc5-rstudio-results.png)

>[!ENDTABS]

+++

