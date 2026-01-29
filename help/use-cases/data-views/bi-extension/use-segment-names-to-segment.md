---
title: Utilisation Des Noms De Segment Pour Le Segment
description: Utilisez des noms de segment pour segmenter le cas d’utilisation de l’extension BI dans divers outils BI de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# Utiliser des noms de segment pour segmenter

Dans ce cas d’utilisation, vous souhaitez utiliser un segment existant pour la catégorie de produits de pêche, que vous avez définie dans Customer Journey Analytics. Pour segmenter et générer des rapports sur les noms de produit et les occurrences (événements) au cours du mois de janvier 2023.

+++ Customer Journey Analytics

Examinez le segment que vous souhaitez utiliser dans Customer Journey Analytics.

![Customer Journey Analytics Utilisez Des Noms De Filtre Pour Filtrer](../assets/cja-fishing-products.png)

Vous pouvez ensuite utiliser ce segment dans un exemple **[!UICONTROL Utilisation des noms de segment pour le segment]** panneau pour le cas d’utilisation :

![Valeurs De Nombre Distinct Customer Journey Analytics](../assets/cja-using-filter-names-to-filter.png)

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
   1. Sélectionnez **[!UICONTROL filterName]**.
   1. Sélectionnez **[!UICONTROL product_name]**.
   1. Sélectionnez **[!UICONTROL somme des occurrences]**.

Une visualisation s’affiche **[!UICONTROL Erreur de récupération des données pour ce visuel]**.

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez **[!UICONTROL filterName is (All)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage de base]** comme **[!UICONTROL type de filtre]**.
   1. Sous le champ **[!UICONTROL Rechercher]**, sélectionnez **[!UICONTROL Produits de la pêche]**, qui est le nom du filtre existant défini dans Customer Journey Analytics.
   1. Sélectionnez **[!UICONTROL daterange est (tout)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est activée ou ultérieure]** `1/1/2023` **[!UICONTROL Et]** **[!UICONTROL est antérieure]** `2/1/2023`.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer **[!UICONTROL filterName]** de **[!UICONTROL Columns]**.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer **[!UICONTROL daterange]** de **[!UICONTROL Columns]**.

   Le tableau est mis à jour avec le filtre **[!UICONTROL filterName]** appliqué. Votre bureau Power BI doit se présenter comme suit :

   ![Bureau Power BI Utilisant Des Noms De Plage De Dates À Filtrer](../assets/uc9-powerbi-final.png)


>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Nom du filtre]** de la liste **[!UICONTROL Tableaux]** dans le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Nom du filtre\]]**, assurez-vous que **[!UICONTROL Sélectionner dans la liste]** est sélectionné, puis sélectionnez **[!UICONTROL Produits de pêche]** dans la liste. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** vers le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Daterang\]]**, sélectionnez **[!UICONTROL Plage de dates]**, puis sélectionnez `01/01/2023` - `01/02/2023`. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser **[!UICONTROL Product Name]** de la liste **[!UICONTROL Tables]** vers **[!UICONTROL Rows]**.
   1. Faites glisser l’entrée **[!UICONTROL Occurrences]** de la liste **[!UICONTROL Tableaux]** et déposez-la dans le champ en regard de **[!UICONTROL Colonnes]**. La valeur devient **[!UICONTROL SUM(Occurrences)]**.
   1. Sélectionnez **[!UICONTROL Tableau de texte]** dans **[!UICONTROL Afficher]**.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc9-tableau-final.png)

>[!TAB Looker]

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
   1. Dans la liste des champs, sélectionnez **[!UICONTROL nom du filtre]**.
1. Assurez-vous que **[!UICONTROL est]** la sélection pour le filtre.
1. Sélectionnez **[!UICONTROL Produits de la pêche]** dans la liste des valeurs possibles.
1. Dans la section **[!UICONTROL ‣ Cr Vue des données]** rail de gauche :
   1. Sélectionnez **[!UICONTROL Nom du produit]**.
   1. Sélectionnez **[!UICONTROL Nombre]** sous **[!UICONTROL MESURES]** dans le rail de gauche (en bas).
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]**.

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Nombre de recherches distinct](../assets/uc9-looker-result.png)



>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   data = %sql SELECT filterName FROM cc_data_view;
   style = {'description_width': 'initial'}
   filter_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Filter Name:',
      style=style
   )
   display(filter_name)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc9-jupyter-input.png)

1. Sélectionnez **[!UICONTROL Produits de la pêche]** dans le menu déroulant.

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
                  AND filterName = '{filter_name.value}' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc9-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ```{r} ` et ` ``` ` dans un nouveau bloc. Veillez à utiliser le nom de filtre approprié. Par exemple : `Fishing Products`.

   ```R
   ## Dimension filtered by name
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & filterName == "Fishing Products") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++
