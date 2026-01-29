---
title: Tendance mensuelle
description: Cas d’utilisation de tendance mensuelle pour l’extension BI dans divers outils BI de Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---

# Tendance mensuelle


Dans ce cas d’utilisation, vous souhaitez afficher un tableau et une visualisation en ligne simple qui montre une tendance mensuelle d’occurrence (événements) pour 2023.

+++ Customer Journey Analytics

Exemple de panneau **[!UICONTROL Tendance mensuelle]** pour le cas d’utilisation :

![Visualisation des tendances mensuelles de Customer Journey Analytics](../assets/cja_monthly_trend.png)

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
   1. Sélectionnez **[!UICONTROL somme des occurrences]**.

   Un tableau affiche les occurrences du mois en cours. Pour une meilleure visibilité, agrandissez la visualisation.

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez le **[!UICONTROL daterangemonth is (All)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre pour **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est égale ou postérieure]** `1/1/2023` **[!UICONTROL Et]** **[!UICONTROL est antérieure]** `1/1/2024.` Vous pouvez utiliser l’icône de calendrier pour sélectionner des dates.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

   Le tableau est mis à jour avec le filtre **[!UICONTROL daterangemonth]** appliqué.

1. Dans le volet **[!UICONTROL Visualisations]** :

   1. Sélectionnez la visualisation **[!UICONTROL Graphique en courbes]**.

   Un graphique en courbes remplace le tableau tout en utilisant les mêmes données que le tableau. Votre bureau Power BI doit se présenter comme suit :

   ![Filtre de période pour le cas d’utilisation 2 de Power BI Desktop](../assets/uc4-pbi-filter-daterange.png)

1. Dans la visualisation sous forme de graphique en courbes :

   1. Sélectionnez ![Plus](/help/assets/icons/More.svg).
   1. Dans le menu contextuel, sélectionnez **[!UICONTROL Afficher sous forme de tableau]**.

   La vue principale est mise à jour pour afficher à la fois une visualisation en ligne et un tableau. Votre bureau Power BI doit se présenter comme suit :

   ![Visualisation quotidienne finale des tendances du cas d’utilisation 2 de Power BI Desktop](../assets/uc4-pbi-filter-final.png)

>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Période]** et spécifiez une période de `01/01/2023` - `01/01/2024`.

      ![Filtre Tableau Desktop](../assets/uc4-tableau-filter.png)

   1. Effectuez un glisser-déposer de **[!UICONTROL Daterangeday]** depuis la liste **[!UICONTROL Tables]** dans le volet **[!UICONTROL Données]** et déposez l&#39;entrée dans le champ en regard de **[!UICONTROL Colonnes]**.
      * Sélectionnez **[!UICONTROL MONTH]** dans le menu déroulant **[!UICONTROL Daterangeday]** afin que la valeur soit mise à jour sur **[!UICONTROL MONTH(Daterangeday)]**.
   1. Effectuez un glisser-déposer **[!UICONTROL Occurrences]** depuis la liste **[!UICONTROL Tableaux (*Noms des mesures*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**. La valeur est automatiquement convertie en **[!UICONTROL SUM(Occurrences)]**.
   1. Modifiez **[!UICONTROL Standard]** en **[!UICONTROL Vue entière]** dans le menu déroulant **[!UICONTROL Ajuster]** de la barre d’outils.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Graphique Tableau Desktop](../assets/uc4-tableau-graph.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une deuxième feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Graph`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l&#39;onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Data`.
1. Assurez-vous que la feuille **[!UICONTROL Data]** est sélectionnée. Dans la vue de données :
   1. Sélectionnez **[!UICONTROL Afficher]** en haut à droite, puis sélectionnez **[!UICONTROL Tableau de texte]** (visualisation en haut à gauche) pour modifier le contenu de la vue de données en tableau.
   1. Faites glisser **[!UICONTROL MONTH(Daterangeday)]** de **[!UICONTROL Columns]** vers **[!UICONTROL Rows]**.
   1. Modifiez **[!UICONTROL Standard]** en **[!UICONTROL Vue entière]** dans le menu déroulant **[!UICONTROL Ajuster]** de la barre d’outils.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Données Tableau Desktop](../assets/uc4-tableau-data.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Graph]** de l’étagère **[!UICONTROL Feuilles]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Données]** de l’étagère **[!UICONTROL Feuilles]** sous la feuille **[!UICONTROL Graphique]** vers la vue **[!UICONTROL Tableau de bord 1]**.
   1. Sélectionnez la feuille **[!UICONTROL Données]** dans la vue et modifiez **[!UICONTROL Vue entière]** en **[!UICONTROL Fixe largeur]**.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Tableau de bord Tableau Desktop 1](../assets/uc4-tableau-dashboard.png)


>[!TAB Looker]

1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2024/01/01]**.
1. Sur le rail de gauche **[!UICONTROL Cc Data View]**,
   1. Sélectionnez **[!UICONTROL ‣ Date du mois de la date]** puis **[!UICONTROL Mois]** dans la liste **[!UICONTROL DIMENSIONS]**.
   1. Sélectionnez **[!UICONTROL Nombre]** sous **[!UICONTROL MESURES]** dans le rail de gauche (en bas).
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]** pour afficher la visualisation Ligne.

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Tendance quotidienne des résultats de recherche](../assets/uc4-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
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

   ![Résultats du notebook Jupyter](../assets/uc4-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ```{r} ` et ` ``` ` dans un nouveau bloc.

   ```R
   ## Hourly Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-01-02") %>%
      group_by(daterangehour) %>%
      count() %>%
      arrange(daterangehour, .by_group = FALSE)
   ggplot(df, aes(x = daterangehour, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Exécutez le bloc. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats RStudio](../assets/uc4-rstudio-results.png)

>[!ENDTABS]

+++
