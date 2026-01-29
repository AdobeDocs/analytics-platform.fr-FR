---
title: Utilisation Des Noms De Période Pour Le Filtrage
description: Utilisez les noms de période pour filtrer les cas d’utilisation de l’extension BI dans divers outils BI de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# Utilisation de noms de périodes pour le filtrage

Dans ce cas d’utilisation, vous souhaitez utiliser une période que vous avez définie dans Customer Journey Analytics pour filtrer et générer des rapports sur les occurrences (événements) de l’année dernière.

+++ Customer Journey Analytics

Pour générer des rapports à l’aide d’une période, configurez une période dans Customer Journey Analytics, avec l’**&#x200B;** Titre`Last Year 2023`.

![Customer Journey Analytics Utilisez des noms de périodes pour filtrer](../assets/cja-daterange.png)

Vous pouvez ensuite utiliser cette période dans un exemple **[!UICONTROL Utilisation des noms de période pour le filtrage]** panneau pour le cas d’utilisation :

![Valeurs De Nombre Distinct Customer Journey Analytics](../assets/cja-using-date-range-filter-names-to-filter.png)

Notez que la période définie dans la visualisation de tableau à structure libre prévaut sur la période appliquée au panneau.

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

1. Dans le volet **[!UICONTROL Données]** :
   1. Sélectionnez **[!UICONTROL daterangemonth]**.
   1. Sélectionnez **[!UICONTROL daterangeName]**.
   1. Sélectionnez **[!UICONTROL somme des occurrences]**.

   Une visualisation s’affiche **[!UICONTROL Erreur de récupération des données pour ce visuel]**.

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez le **[!UICONTROL daterangeName is (All)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage de base]** comme **[!UICONTROL type de filtre]**.
   1. Sous le champ **[!UICONTROL Rechercher]**, sélectionnez **[!UICONTROL Année dernière 2023]**, qui est le nom de votre période définie dans Customer Journey Analytics.
   1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer **[!UICONTROL daterangeName]** de **[!UICONTROL Columns]**.

   Le tableau est mis à jour avec le filtre **[!UICONTROL daterangeName]** appliqué. Votre bureau Power BI doit se présenter comme suit :

   ![Bureau Power BI Utilisant Des Noms De Plage De Dates À Filtrer](../assets/uc8-powerbi-final.png)

>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Nom de la plage de dates]** de la liste **[!UICONTROL Tables]** vers le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Nom de la plage de données\]]**, assurez-vous que **[!UICONTROL Sélectionner dans la liste]** est sélectionné, puis sélectionnez **[!UICONTROL Dernière année 2023]** dans la liste. Sélectionnez **[!UICONTROL Appliquer]** et **[!UICONTROL OK]**.
   1. Faites glisser l’entrée **[!UICONTROL Daterangemonth]** de la liste **[!UICONTROL Tables]** et déposez-la dans le champ en regard de **[!UICONTROL Lignes]**. Sélectionnez **[!UICONTROL Daterangemonth]** puis **[!UICONTROL Month]**. La valeur devient **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Faites glisser l’entrée **[!UICONTROL Occurrences]** de la liste **[!UICONTROL Tableaux]** et déposez-la dans le champ en regard de **[!UICONTROL Colonnes]**. La valeur devient **[!UICONTROL SUM(Occurrences)]**.
   1. Sélectionnez **[!UICONTROL Tableau de texte]** dans **[!UICONTROL Afficher]**.
   1. Sélectionnez **[!UICONTROL Permuter les lignes et les colonnes]** dans la barre d’outils.
   1. Sélectionnez **[!UICONTROL Ajuster la largeur]** dans le menu déroulant **[!UICONTROL Ajuster]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc8-tableau-final.png)

>[!TAB Looker]

1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL ‣ Daterange Name]**.
1. Spécifiez le filtre **[!UICONTROL Nom de plage de dates de la vue de données Cc]** tel quel **&#x200B;**&#x200B;et sélectionnez **[!UICONTROL Année dernière 2023]** dans la liste de valeurs.
1. Dans la section **[!UICONTROL ‣ Cr Vue des données]** rail de gauche :
   1. Sélectionnez **[!UICONTROL Mois de la période]**, puis **[!UICONTROL Mois]**.
   1. Sélectionnez **[!UICONTROL Nombre]** sous **[!UICONTROL MESURES]** dans le rail de gauche (en bas).
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]**.

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Nombre de recherches distinct](../assets/uc8-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc8-jupyter-input.png)

1. Sélectionnez **[!UICONTROL Produits de la pêche]** dans le menu déroulant.

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc8-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ` ``{r} ` et ` `` ` ` dans un nouveau bloc. Veillez à utiliser le nom de période approprié. Par exemple : `Last Year 2023`.

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

