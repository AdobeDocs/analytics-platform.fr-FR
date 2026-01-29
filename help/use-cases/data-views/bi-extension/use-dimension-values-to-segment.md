---
title: Utilisation Des Valeurs Dimension Pour Segmenter
description: Utilisez des valeurs de dimension pour segmenter le cas d’utilisation de l’extension BI dans divers outils BI de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# Utilisation des valeurs de dimension pour segmenter

Utilisez la valeur dynamique **[!UICONTROL Chasse]** pour **[!UICONTROL Catégorie de produits]** pour segmenter les produits de la catégorie de chasse. Pour les outils de BI qui ne prennent pas en charge la récupération dynamique des valeurs de catégorie de produits, vous pouvez également créer un segment dans Customer Journey Analytics qui segmente les produits de la catégorie de produits de chasse.
Ensuite, vous souhaitez utiliser le nouveau segment pour générer des rapports sur les noms de produit et les occurrences (événements) pour les produits de la catégorie chasse en janvier 2023.

+++ Customer Journey Analytics

Créez un segment avec la **** Titre`Hunting Products` dans Customer Journey Analytics.

![Customer Journey Analytics Utilise Des Valeurs Dimension Pour Segmenter](../assets/cja-hunting-products.png)

Vous pouvez ensuite utiliser ce segment dans un exemple **[!UICONTROL Utilisation des valeurs Dimension à filtrer]** panneau pour le cas d’utilisation :

![Valeurs De Nombre Distinct Customer Journey Analytics](../assets/cja-using-dimension-values-to-filter.png)

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

1. Sélectionnez **[!UICONTROL Accueil]** dans le menu, puis sélectionnez **[!UICONTROL Actualiser]** dans la barre d’outils. Vous devez actualiser la connexion pour sélectionner le nouveau filtre que vous venez de définir dans Customer Journey Analytics.

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL daterange]**.
   1. Sélectionnez **[!UICONTROL product_category]**.
   1. Sélectionnez **[!UICONTROL product_name]**.
   1. Sélectionnez **[!UICONTROL somme des occurrences]**.

Une visualisation s’affiche **[!UICONTROL Erreur de récupération des données pour ce visuel]**.

1. Dans le volet **[!UICONTROL Filtres]** :
   1. Sélectionnez **[!UICONTROL filterName is (All)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage de base]** comme **[!UICONTROL type de filtre]**.
   1. Sélectionnez **[!UICONTROL daterange est (tout)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est activée ou ultérieure]** `1/1/2023` **[!UICONTROL Et]** **[!UICONTROL est antérieure]** `2/1/2023`.
   1. Sélectionnez **[!UICONTROL Filtre de base]** comme **[!UICONTROL Type de filtre]** pour **[!UICONTROL product_category]**, puis sélectionnez **[!UICONTROL Chasse]** dans la liste des valeurs possibles.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer **[!UICONTROL filterName]** de **[!UICONTROL Columns]**.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer **[!UICONTROL daterange]** de **[!UICONTROL Columns]**.

   Le tableau est mis à jour avec le filtre **[!UICONTROL product_category]** appliqué. Votre bureau Power BI doit se présenter comme suit :

   ![Bureau Power BI Utilisant Des Noms De Plage De Dates À Filtrer](../assets/uc10-powerbi-final.png)



>[!TAB  Tableau Desktop ]

![AlertRed](/help/assets/icons/AlertRed.svg) Tableau Desktop ne prend pas en charge la récupération de la liste dynamique des catégories de produits depuis Customer Journey Analytics. À la place, ce cas d’utilisation utilise le filtre nouvellement créé pour **[!UICONTROL Produits de chasse]** et utilise les critères de nom du filtre.

1. Dans la vue **[!UICONTROL Source de données]**, sous **[!UICONTROL Données]**, dans le menu contextuel de **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, sélectionnez **[!UICONTROL Actualiser]**. Vous devez actualiser la connexion pour sélectionner le nouveau filtre que vous venez de définir dans Customer Journey Analytics.
1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Nom du filtre]** de la liste **[!UICONTROL Tableaux]** dans le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Nom du filtre\]]**, assurez-vous que **[!UICONTROL Sélectionner dans la liste]** est sélectionné, puis sélectionnez **[!UICONTROL Produits de chasse]** dans la liste. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** vers le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Période]**, puis sélectionnez `01/01/2023` - `1/2/2023`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser **[!UICONTROL Product Name]** de la liste **[!UICONTROL Tables]** vers **[!UICONTROL Rows]**.
   1. Faites glisser l’entrée **[!UICONTROL Occurrences]** de la liste **[!UICONTROL Tableaux]** et déposez-la dans le champ en regard de **[!UICONTROL Colonnes]**. La valeur devient **[!UICONTROL SUM(Occurrences)]**.
   1. Sélectionnez **[!UICONTROL Tableau de texte]** dans **[!UICONTROL Afficher]**.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc10-tableau-final.png)

>[!TAB Looker]

1. Dans le 1. Dans l’interface **[!UICONTROL Explorer]** de la recherche, actualisez votre connexion. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Effacer le cache et actualiser]**.
1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2023/02/01]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL Filtres]** pour ajouter un autre filtre.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Catégorie de produits]**.
1. Assurez-vous que **[!UICONTROL est]** est sélectionné pour le filtre.

![AlertRed](/help/assets/icons/AlertRed.svg) Recherche n&#39;affiche pas la liste des valeurs possibles pour **[!UICONTROL Catégorie de produits]**.

![Nombre de recherches distinct](../assets/uc10-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   data = %sql SELECT DISTINCT product_category FROM cc_data_view WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01';
   style = {'description_width': 'initial'}
   category_filter = widgets.Dropdown(
      options=[d for d, in data],
      description='Product Category:',
      style=style
   )
   display(category_filter)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc10-jupyter-input.png)

1. Sélectionnez **[!UICONTROL Chasse]** dans le menu déroulant.

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               AND product_category = '{category_filter.value}' \
               GROUP BY 1 \
               ORDER BY Events DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc10-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ```{r} ` et ` ``` ` dans un nouveau bloc. Veillez à utiliser une catégorie appropriée. Par exemple, `Hunting`.

   ```R
   ## Dimension 1 Filtered by Dimension 2 value
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & product_category == "Hunting") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++

