---
title: Tendance horaire
description: Cas d’utilisation de tendance horaire pour l’extension BI dans divers outils de BI dans Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---

# Tendance horaire


## Tendance horaire

Dans ce cas d’utilisation, vous souhaitez afficher un tableau et une visualisation en ligne simple qui affiche une tendance horaire des occurrences (événements) pour le 1er janvier 2023.

+++ Customer Journey Analytics

Exemple de panneau **[!UICONTROL Tendance horaire]** pour le cas d’utilisation :

![Visualisations des tendances horaires de Customer Journey Analytics](../assets/cja_hourly_trend.png)

+++

+++ Outils de BI

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé [une connexion réussie, que vous pouvez répertorier les vues de données et utiliser une vue de données](connect-and-validate.md) pour l’outil BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau Power BI]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BI ne comprend **pas** comment gérer les champs date-heure. Par conséquent, les dimensions telles que **[!UICONTROL daterangehour]** et **[!UICONTROL daterangeminute]** ne sont pas prises en charge.

>[!TAB  Tableau Desktop ]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer depuis **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Feuille 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Période]** de la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez-la sur l’étagère **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Champ de filtre \[Période\]]**, sélectionnez **[!UICONTROL Période]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtrer \[Période\]]**, sélectionnez **[!UICONTROL Période]** et spécifiez une période de `01/01/2023` - `02/01/2023`.

      ![Filtre Tableau Desktop](../assets/uc3-tableau-filter.png)

   1. Effectuez un glisser-déposer de **[!UICONTROL Daterangehour]** depuis la liste **[!UICONTROL Tableaux]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Colonnes]**.
      * Sélectionnez **[!UICONTROL Plus]** > **[!UICONTROL Heures]** dans le menu déroulant **[!UICONTROL Daterangeday]** afin que la valeur soit mise à jour sur **[!UICONTROL HEURE(Daterangeday)]**.
   1. Effectuez un glisser-déposer **[!UICONTROL Occurrences]** depuis la liste **[!UICONTROL Tableaux (*Noms des mesures*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**. La valeur est automatiquement convertie en **[!UICONTROL SUM(Occurrences)]**.
   1. Modifiez **[!UICONTROL Standard]** en **[!UICONTROL Vue entière]** dans le menu déroulant **[!UICONTROL Ajuster]** de la barre d’outils.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Graphique Tableau Desktop](../assets/uc3-tableau-graph.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une deuxième feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Graph`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l&#39;onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Data`.
1. Assurez-vous que la feuille **[!UICONTROL Data]** est sélectionnée. Dans la vue **[!UICONTROL Data]** :
   1. Sélectionnez **[!UICONTROL Afficher]** en haut à droite, puis sélectionnez **[!UICONTROL Tableau de texte]** (visualisation en haut à gauche) pour modifier le contenu de la vue de données en tableau.
   1. Faites glisser **[!UICONTROL HOUR(Daterangeday)]** de **[!UICONTROL Columns]** vers **[!UICONTROL Rows]**.
   1. Modifiez **[!UICONTROL Standard]** en **[!UICONTROL Vue entière]** dans le menu déroulant **[!UICONTROL Ajuster]** de la barre d’outils.

      Votre Tableau Desktop devrait ressembler à ce qui suit.

      ![Données Tableau Desktop](../assets/uc3-tableau-data.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Graph]** de l’étagère **[!UICONTROL Feuilles]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Données]** de l’étagère **[!UICONTROL Feuilles]** sous la feuille **[!UICONTROL Graphique]** vers la vue **[!UICONTROL Tableau de bord 1]**.
   1. Sélectionnez la feuille **[!UICONTROL Données]** dans la vue et modifiez **[!UICONTROL Vue entière]** en **[!UICONTROL Fixe largeur]**.

      La vue de votre **[!UICONTROL Tableau de bord 1]** doit se présenter comme suit :

      ![Tableau de bord Tableau Desktop 1](../assets/uc3-tableau-dashboard.png)


>[!TAB Looker]


1. Dans l’interface **[!UICONTROL Explorer]** de Looker, assurez-vous que vous disposez d’une configuration propre. Sinon, sélectionnez ![Paramétrage](/help/assets/icons/Setting.svg) **[!UICONTROL Supprimer les champs et les filtres]**.
1. Sélectionnez **[!UICONTROL + filtre]** sous **[!UICONTROL filtres]**.
1. Dans la boîte de dialogue **[!UICONTROL Ajouter un filtre]** :
   1. Sélectionnez **[!UICONTROL ‣ Cc Vue De Données]**
   1. Dans la liste des champs, sélectionnez **[!UICONTROL Date de période]** puis **[!UICONTROL Date de période]**.
      ![Filtre de recherche](../assets/uc2-looker-filter.png)
1. Spécifiez le filtre **[!UICONTROL Date de plage de dates de la vue de données Cc]** tel que **[!UICONTROL est dans la plage]** **[!UICONTROL 2023/01/01]** **[!UICONTROL jusqu’au (avant)]** **[!UICONTROL 2023/01/02]**.
1. Dans la section **[!UICONTROL Vue de données Cc]** du rail de gauche,
   1. Sélectionnez **[!UICONTROL ‣ Date de l’heure du tableau de bord]** puis **[!UICONTROL Heure]** dans la liste des **[!UICONTROL DIMENSIONS]**.
   1. Sélectionnez **[!UICONTROL Nombre]** sous **[!UICONTROL MESURES]** dans le rail de gauche (en bas).
1. Sélectionnez **[!UICONTROL Exécuter]**.
1. Sélectionnez **[!UICONTROL ‣ Visualisation]** pour afficher la visualisation Ligne.

Vous devriez voir une visualisation et un tableau similaires à ceux présentés ci-dessous.

![Tendance quotidienne des résultats de recherche](../assets/uc3-looker-result.png)


>[!TAB Notebook Jupyter]

1. Saisissez les instructions suivantes dans une nouvelle cellule.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangehour AS Hour, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-01-02' \
               GROUP BY 1 \
                ORDER BY Hour ASC
   df = data.DataFrame()
   df = df.groupby('Hour', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Hour', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Exécutez la cellule. Vous devriez voir une sortie similaire à la capture d’écran ci-dessous.

   ![Résultats du notebook Jupyter](../assets/uc3-jupyter-results.png)


>[!TAB RStudio]

1. Saisissez les instructions suivantes entre ` ` ``{r} ` et ` `` ` ` dans un nouveau bloc.

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

   ![Résultats RStudio](../assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++
