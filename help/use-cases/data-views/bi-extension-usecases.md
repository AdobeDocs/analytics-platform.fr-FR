---
title: Cas d’utilisation de l’extension BI dans Customer Journey Analytics
description: Plusieurs cas d’utilisation qui montrent comment utiliser l’extension BI dans divers outils de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '2575'
ht-degree: 1%

---

# Cas d’utilisation de l’extension BI

Cet article fournit un certain nombre de cas d’utilisation qui illustrent l’utilisation de la fonctionnalité de l’extension de BI sur différents outils de BI.

Les cas d’utilisation suivants sont documentés :

1. [Connectez-vous et répertoriez les vues de données](#connect-and-list-data-views).
1. [Tendance quotidienne](#daily-trend).
1. [Tendance horaire](#hourly-trend).
1. [ Tendance mensuelle ](#monthly-trend).
1. [Dimension unique classée](#single-dimension-ranked).
1. [Plusieurs dimensions classées](#multiple-dimension-ranked).
1. [Compter des valeurs de dimension distinctes](#count-distinct-dimension-values).
1. [Utilisez les noms de période pour filtrer](#use-date-range-names-to-filter).
1. [Utilisez les noms de filtre pour filtrer](#use-filter-names-to-filter).
1. [Utilisez des valeurs de dimension pour filtrer](#use-dimension-values-to-filter).
1. [Trier](#sort).
1. [Limites](#limits).
1. [Pour corriger ou non](#to-flatten-or-not).
1. [transformations de Dimension et de mesure](#dimension-and-metric-transformations).
1. [Visualisations et interactions](#visualizations-and-interactions).

Pour chaque cas d’utilisation, des instructions sont disponibles pour les outils de BI suivants dans la section **Détails** :

* Bureau Power BI (version 2.136.1478.0 64 bits (septembre 2024))
* Tableau Desktop (version 2024.1.5 (20241.24.0705.0334) 64 bits)

Les instructions se rapportent à un exemple de vue de données nommé **[!UICONTROL public.cc_data_view]**, à deux exemples de dimensions (**[!UICONTROL Nom du produit]** et **[!UICONTROL Catégorie de produit]**) et à deux exemples de mesures (**[!UICONTROL Achats]** et **[!UICONTROL Recettes d’achats]**). Lorsque vous suivez les instructions, modifiez ces exemples d’objets pour votre environnement spécifique, le cas échéant.


## Connexion et énumération des vues de données

Ce cas pratique configure la connexion de l’outil de BI à Customer Journey Analytics et répertorie les vues de données disponibles pour tester la connexion avec succès.

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

1. Accédez aux informations d’identification et aux paramètres requis à partir de l’interface utilisateur de Query Service Experience Platform.

   1. Accédez à votre environnement de test Experience Platform.
   1. Sélectionnez ![Requêtes](/help/assets/icons/DataSearch.svg) **[!UICONTROL Requêtes]** dans le rail de gauche.
   1. Sélectionnez l&#39;onglet **[!UICONTROL Credentials]** dans l&#39;interface **[!UICONTROL Queries]**.
   1. Sélectionnez `prod:cja` dans le menu déroulant **[!UICONTROL Base de données]**.

      ![Informations d’identification du service de requête](assets/queryservice-credentials.png)

1. Ouvrez Power BI Desktop.
1. Dans l&#39;interface principale, sélectionnez **[!UICONTROL Obtenir des données d&#39;autres sources]**.
1. Dans la boîte de dialogue **[!UICONTROL Obtenir des données]** :
   ![Base de données PowerBI PostgreSQL](assets/powerbi-postgresql.png)
   1. Recherchez et sélectionnez **[!UICONTROL Base de données PostgreSQL]**.
   1. Sélectionnez **[!UICONTROL Connect]**.
1. Dans la boîte de dialogue **[!UICONTROL Base de données PostgreSQL]** :
   ![Paramètres du serveur de bureau et de la base de données PowerBI](assets/powerbi-serverdatabase.png)
   1. Utilisez ![Copy](/help/assets/icons/Copy.svg) pour copier et coller les valeurs **[!UICONTROL Host]** et **[!UICONTROL Port]** de l’Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**, séparées par `:` comme valeur de **[!UICONTROL Server]**. Par exemple : `examplecompany.platform-query.adobe.io:80`.
   1. Utilisez ![Copy](/help/assets/icons/Copy.svg) pour copier et coller la valeur **[!UICONTROL Database]** de l’Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**. Ajoutez `?FLATTEN` à la valeur que vous collez. Par exemple : `prod:cja?FLATTEN`.
   1. Sélectionnez **[!UICONTROL DirectQuery]** comme [!UICONTROL  mode de connectivité des données ].
   1. Sélectionnez **[!UICONTROL OK]**.
1. Dans la boîte de dialogue **[!UICONTROL Base de données PostgreSQL]** - **[!UICONTROL Base de données]** :
   ![Utilisateur de bureau PowerBI et mot de passe](assets/powerbi-userpassword.png)
   1. Utilisez ![Copier](/help/assets/icons/Copy.svg) pour copier les valeurs **[!UICONTROL Nom d’utilisateur]** et **[!UICONTROL Mot de passe]** du panneau **[!UICONTROL Requête]** **[!UICONTROL Informations d’identification d’expiration]** de l’Experience Platform dans les champs **[!UICONTROL Nom d’utilisateur]** et **[!UICONTROL Mot de passe]**. Si vous utilisez des [informations d’identification non expirantes](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), utilisez le mot de passe de vos informations d’identification non arrivant à expiration.
   1. Assurez-vous que le menu déroulant de **[!UICONTROL Sélectionner le niveau auquel appliquer ces paramètres à]** est défini sur le **[!UICONTROL serveur]** que vous avez défini précédemment.
   1. Sélectionnez **[!UICONTROL Connect]**.
1. Dans la boîte de dialogue **[!UICONTROL Navigator]**, les vues de données sont récupérées. Cette récupération peut prendre du temps. Une fois récupéré :
   ![Données de chargement du serveur de Power BI](assets/powerbi-navigator-load.png)
   1. Sélectionnez **[!UICONTROL public.cc_data_view]** dans la liste du panneau de gauche.
   1. Sélectionnez **[!UICONTROL Load]**.
1. Au bout d’un certain temps, les mesures et dimensions disponibles s’affichent dans le volet **[!UICONTROL Données]**.
   ![Données de serveur de Power BI chargées](assets/powerbi-navigator-loaded.png)


>[!TAB Tableau Desktop]

1. Accédez aux informations d’identification et aux paramètres requis à partir de l’interface utilisateur de Query Service Experience Platform.

   1. Accédez à votre environnement de test Experience Platform.
   1. Sélectionnez ![Requêtes](/help/assets/icons/DataSearch.svg) **[!UICONTROL Requêtes]** dans le rail de gauche.
   1. Sélectionnez l&#39;onglet **[!UICONTROL Credentials]** dans l&#39;interface **[!UICONTROL Queries]**.
   1. Sélectionnez `prod:cja` dans le menu déroulant **[!UICONTROL Base de données]**.

      ![Informations d’identification du service de requête](assets/queryservice-credentials.png)

1. Ouvrez Tableau.
1. Sélectionnez **[!UICONTROL PostgreSQL]** dans le rail de gauche en dessous de **[!UICONTROL Sur un serveur]**. Si ce n&#39;est pas le cas, sélectionnez **[!UICONTROL Plus...]** et **[!UICONTROL PostgreSQL]** dans la liste **[!UICONTROL Connecteurs installés]**.
   ![Connecteurs Tableau](assets/tableau-connectors.png)
1. Dans la boîte de dialogue **[!UICONTROL PostgreSQL]**, dans l’onglet **[!UICONTROL Général]** :
   ![Boîte de dialogue de connexion Tableau](assets/tableau-signin.png)
   1. Utilisez ![Copier](/help/assets/icons/Copy.svg) pour copier et coller l’**[!UICONTROL hôte]** de l’Experience Platform **[!UICONTROL Requête]** **[!UICONTROL Informations d’identification d’expiration]** sur le **[!UICONTROL serveur]**.
   1. Utilisez ![Copier](/help/assets/icons/Copy.svg) pour copier et coller le **[!UICONTROL port]** de l’Experience Platform **[!UICONTROL Requête]** **[!UICONTROL Informations d’identification d’expiration]** vers le **[!UICONTROL port]**.
   1. Utilisez ![Copier](/help/assets/icons/Copy.svg) pour copier et coller la **[!UICONTROL base de données]** de la **[!UICONTROL requête]** **[!UICONTROL des informations d’identification d’expiration]** dans la **[!UICONTROL base de données]** Experience Platform. Ajoutez `%3FFLATTEN` à la valeur que vous collez. Par exemple : `prod:cja%3FFLATTEN`.
   1. Sélectionnez **[!UICONTROL Nom d’utilisateur et mot de passe]** dans le menu déroulant **[!UICONTROL Authentification]** .
   1. Utilisez ![Copier](/help/assets/icons/Copy.svg) pour copier et coller le **[!UICONTROL nom d’utilisateur]** de la **[!UICONTROL requête]** **[!UICONTROL informations d’identification d’expiration]** de l’Experience Platform dans le **[!UICONTROL nom d’utilisateur]**.
   1. Utilisez ![Copier](/help/assets/icons/Copy.svg) pour copier et coller le **[!UICONTROL mot de passe]** de la **[!UICONTROL requête]** **[!UICONTROL Informations d’identification d’expiration]** de l’Experience Platform **[!UICONTROL mot de passe]**. Si vous utilisez des [informations d’identification non expirantes](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), utilisez le mot de passe de vos informations d’identification non arrivant à expiration.
   1. Vérifiez que **[!UICONTROL Require SSL]** est coché.
   1. Sélectionnez **[!UICONTROL Se connecter]**.

   Une boîte de dialogue **[!UICONTROL Requête de progression]** s’affiche alors que Tableau Desktop valide la connexion.
1. Dans la fenêtre principale, vous pouvez voir dans la vue Data Source, dans le volet de gauche :
   * Nom de la connexion, sous **[!UICONTROL Connexions]**.
   * Nom de la base de données, sous **[!UICONTROL Database]**.
   * Une liste de tables, sous **[!UICONTROL Table]**.
     ![Tableau connecté](assets/tableau-connected.png)
   1. Faites glisser l’entrée **[!UICONTROL cc_data_view]** et déposez l’entrée sur la vue principale qui indique **[!UICONTROL Faire glisser les tables]** ici.
1. La fenêtre principale affiche désormais les détails de la vue de données **[!UICONTROL cc_data_view]**.
   ![Tableau connecté](assets/tableau-validation.png)

>[!ENDTABS]

+++


## Tendance quotidienne

Dans ce cas d’utilisation, vous souhaitez afficher un tableau et une visualisation en ligne simple qui présente une tendance quotidienne des occurrences entre le 1er janvier 2023 et le 31 janvier 2023.

+++ Détails

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé une [connexion réussie et que vous pouvez répertorier les vues de données](#connect-and-list-data-views) pour l’outil de BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

1. Dans le volet **[!UICONTROL Data]** :
   1. Sélectionnez la dimension **[!UICONTROL daterangeday]** .
   1. Sélectionnez la mesure **[!UICONTROL occurrences]**.

   Un tableau s’affiche pour les occurrences du mois en cours. Pour une meilleure visibilité, agrandissez la visualisation du tableau.

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez **[!UICONTROL daterangeday is (All)]** dans **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre sur **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est activée ou après]** `1/1/2023` **** **[!UICONTROL est antérieure à]** `1/2/2023.` Vous pouvez utiliser l’icône de calendrier pour sélectionner des dates.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

   La table est mise à jour avec le filtre **[!UICONTROL daterangeday]** appliqué.

1. Dans le volet **[!UICONTROL Visualisations]** :

   1. Sélectionnez la visualisation **[!UICONTROL Graphique en courbes]** .

   Une visualisation en graphique linéaire remplace le tableau tout en utilisant les mêmes données que le tableau.

   ![Power BI Cas d’utilisation 2 : filtre de plage de dates](assets/uc2-pbi-filter-daterange.png)

1. Dans la visualisation en graphique en courbes :

   1. Sélectionnez ![Plus](/help/assets/icons/More.svg).
   1. Dans le menu contextuel, sélectionnez **[!UICONTROL Afficher en tant que table]**.

   L’affichage principal est mis à jour afin d’afficher à la fois une visualisation par ligne et un tableau.

   ![Cas d’utilisation de bureau Power BI 2 Visualisation des tendances quotidiennes finales](assets/uc2-pbi-filter-final.png)

>[!TAB Tableau Desktop]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer de **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Sheet 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Daterange]** de la liste **[!UICONTROL Tables]** dans le volet **[!UICONTROL Données]** et déposez l’entrée sur le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filters Field \[Daterange\]]**, sélectionnez **[!UICONTROL Plage de dates]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtre \[Daterange]]**, sélectionnez **[!UICONTROL Plage de dates]** et spécifiez une période de `01/01/2023` à `01/02/2023`.

      ![Filtre de bureau Tableau](assets/uc2-tableau-filter.png)

   1. Faites glisser **[!UICONTROL Daterangeday]** depuis la liste **[!UICONTROL Tables]** du volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Colonnes]**.
      * Sélectionnez **[!UICONTROL Day]** dans le menu déroulant **[!UICONTROL Daterangeday]**, de sorte que la valeur soit mise à jour vers **[!UICONTROL DAY(Daterangeday)]**.
   1. Faites glisser **[!UICONTROL Occurrences]** depuis la liste **[!UICONTROL Tables (*Mesurer les noms*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**.
      * Les valeurs sont automatiquement converties en **[!UICONTROL SUM(Occurrences)]**.
   1. Remplacez **[!UICONTROL Standard]** par **[!UICONTROL Vue entière]** dans le menu déroulant de la barre d’outils.

      Votre vue Feuille 1 doit ressembler à ce qui suit.

      ![Graphique de bureau Tableau](assets/uc2-tableau-graph.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une seconde feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Graph`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Data`.
1. Assurez-vous que la feuille **[!UICONTROL Data]** est sélectionnée. Dans la vue Data :
   1. Sélectionnez **[!UICONTROL Afficher]** en haut à droite et sélectionnez **[!UICONTROL Tableau de texte]** (visualisation en haut à gauche) pour modifier le contenu de la vue de données en tableau.
   1. Faites glisser **[!UICONTROL DAY(Daterangeday)]** de **[!UICONTROL Colonnes]** vers **[!UICONTROL Lignes]**.
   1. Remplacez **[!UICONTROL Standard]** par **[!UICONTROL Vue entière]** dans le menu déroulant de la barre d’outils.

      Votre vue **[!UICONTROL Data]** doit ressembler à ce qui suit.

      ![Données de bureau Tableau](assets/uc2-tableau-data.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une nouvelle vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Graph]** de l’étagère **[!UICONTROL Sheets]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Data]** de l’étagère **[!UICONTROL Sheets]** sous la feuille **[!UICONTROL Graph]** sur la vue **[!UICONTROL Tableau de bord 1]**.
   1. Sélectionnez la feuille **[!UICONTROL Data]** dans la vue et modifiez la **[!UICONTROL vue entière]** en **[!UICONTROL largeur du correctif]**.

      Votre vue **[!UICONTROL Tableau de bord 1]** doit ressembler à ce qui suit.

      ![Tableau de bord de bureau Tableau 1](assets/uc2-tableau-dashboard.png)

>[!ENDTABS]

+++


## Tendance horaire

Dans ce cas pratique, vous souhaitez afficher un tableau et une visualisation en ligne simple qui affichent une tendance horaire des occurrences pour le 1er janvier 2023.

+++ Détails

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé une [connexion réussie et que vous pouvez répertorier les vues de données](#connect-and-list-data-views) pour l’outil de BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Le Power BI ![Alert](/help/assets/icons/Alert.svg) ne comprend **pas** comment gérer les colonnes de date et heure. Par conséquent, les dimensions telles que **[!UICONTROL daterangehour]** et **[!UICONTROL daterangeminute]** ne sont pas prises en charge.

>[!TAB Tableau Desktop]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer de **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Sheet 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Daterange]** de la liste **[!UICONTROL Tables]** dans le volet **[!UICONTROL Données]** et déposez l’entrée sur le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filters Field \[Daterange\]]**, sélectionnez **[!UICONTROL Plage de dates]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtre \[Daterange]]**, sélectionnez **[!UICONTROL Plage de dates]** et spécifiez une période de `01/01/2023` à `02/01/2023`.

      ![Filtre de bureau Tableau](assets/uc3-tableau-filter.png)

   1. Faites glisser **[!UICONTROL Daterangehour]** depuis la liste **[!UICONTROL Tables]** du volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Colonnes]**.
      * Sélectionnez **[!UICONTROL Plus]** > **[!UICONTROL Heures]** dans le menu déroulant **[!UICONTROL Daterangeday]**, de sorte que la valeur soit mise à jour vers **[!UICONTROL HOUR(Daterangeday)]**.
   1. Faites glisser **[!UICONTROL Occurrences]** depuis la liste **[!UICONTROL Tables (*Mesurer les noms*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**.
      * Les valeurs sont automatiquement converties en **[!UICONTROL SUM(Occurrences)]**.
   1. Remplacez **[!UICONTROL Standard]** par **[!UICONTROL Vue entière]** dans le menu déroulant de la barre d’outils.

      Votre vue Feuille 1 doit ressembler à ce qui suit.

      ![Graphique de bureau Tableau](assets/uc3-tableau-graph.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une seconde feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Graph`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Data`.
1. Assurez-vous que la feuille **[!UICONTROL Data]** est sélectionnée. Dans la vue Data :
   1. Sélectionnez **[!UICONTROL Afficher]** en haut à droite et sélectionnez **[!UICONTROL Tableau de texte]** (visualisation en haut à gauche) pour modifier le contenu de la vue de données en tableau.
   1. Faites glisser **[!UICONTROL HOUR(Daterangeday)]** de **[!UICONTROL Colonnes]** vers **[!UICONTROL Lignes]**.
   1. Remplacez **[!UICONTROL Standard]** par **[!UICONTROL Vue entière]** dans le menu déroulant de la barre d’outils.

      Votre vue **[!UICONTROL Data]** doit ressembler à ce qui suit.

      ![Données de bureau Tableau](assets/uc3-tableau-data.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une nouvelle vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Graph]** de l’étagère **[!UICONTROL Sheets]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Data]** de l’étagère **[!UICONTROL Sheets]** sous la feuille **[!UICONTROL Graph]** sur la vue **[!UICONTROL Tableau de bord 1]**.
   1. Sélectionnez la feuille **[!UICONTROL Data]** dans la vue et modifiez la **[!UICONTROL vue entière]** en **[!UICONTROL largeur du correctif]**.

      Votre vue **[!UICONTROL Tableau de bord 1]** doit ressembler à ce qui suit.

      ![Tableau de bord de bureau Tableau 1](assets/uc3-tableau-dashboard.png)


>[!ENDTABS]

+++


## Tendance mensuelle

Dans ce cas pratique, vous souhaitez afficher un tableau et une visualisation en ligne simple qui affichent une tendance mensuelle des occurrences pour la période du 1er janvier 2023 au 1er janvier 2024.

+++ Détails

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé une [connexion réussie et que vous pouvez répertorier les vues de données](#connect-and-list-data-views) pour l’outil de BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

1. Dans le volet **[!UICONTROL Data]** :
   1. Sélectionnez la dimension **[!UICONTROL daterangemonth]** .
   1. Sélectionnez la mesure **[!UICONTROL occurrences]**.

   Un tableau s’affiche pour les occurrences du mois en cours. Pour une meilleure visibilité, agrandissez la visualisation du tableau.

1. Dans le volet **[!UICONTROL Filtres]** :

   1. Sélectionnez le **[!UICONTROL daterangemonth is (All)]** de **[!UICONTROL Filtres sur ce visuel]**.
   1. Sélectionnez **[!UICONTROL Filtrage avancé]** comme **[!UICONTROL Type de filtre]**.
   1. Définissez le filtre sur **[!UICONTROL Afficher les éléments lorsque la valeur]** **[!UICONTROL est activée ou après]** `1/1/2023` **** **[!UICONTROL est antérieure à]** `1/1/2024.` Vous pouvez utiliser l’icône de calendrier pour sélectionner des dates.
   1. Sélectionnez **[!UICONTROL Appliquer le filtre]**.

   La table est mise à jour avec le filtre **[!UICONTROL daterangeday]** appliqué.

1. Dans le volet **[!UICONTROL Visualisations]** :

   1. Sélectionnez la visualisation **[!UICONTROL Graphique en courbes]** .

   Une visualisation en graphique linéaire remplace le tableau tout en utilisant les mêmes données que le tableau.

   ![Power BI Cas d’utilisation 2 : filtre de plage de dates](assets/uc4-pbi-filter-daterange.png)

1. Dans la visualisation en graphique en courbes :

   1. Sélectionnez ![Plus](/help/assets/icons/More.svg).
   1. Dans le menu contextuel, sélectionnez **[!UICONTROL Afficher en tant que table]**.

   L’affichage principal est mis à jour afin d’afficher à la fois une visualisation par ligne et un tableau.

   ![Cas d’utilisation de bureau Power BI 2 Visualisation des tendances quotidiennes finales](assets/uc4-pbi-filter-final.png)

>[!TAB Tableau Desktop]

1. Sélectionnez l’onglet **[!UICONTROL Feuille 1]** en bas pour basculer de **[!UICONTROL Source de données]**. Dans la vue **[!UICONTROL Sheet 1]** :
   1. Faites glisser l’entrée **[!UICONTROL Daterange]** de la liste **[!UICONTROL Tables]** dans le volet **[!UICONTROL Données]** et déposez l’entrée sur le plateau **[!UICONTROL Filtres]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filters Field \[Daterange\]]**, sélectionnez **[!UICONTROL Plage de dates]** et sélectionnez **[!UICONTROL Suivant >]**.
   1. Dans la boîte de dialogue **[!UICONTROL Filtre \[Daterange]]**, sélectionnez **[!UICONTROL Plage de dates]** et spécifiez une période de `01/01/2023` à `01/01/2024`.

      ![Filtre de bureau Tableau](assets/uc4-tableau-filter.png)

   1. Faites glisser **[!UICONTROL Daterangeday]** depuis la liste **[!UICONTROL Tables]** du volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Colonnes]**.
      * Sélectionnez **[!UICONTROL MONTH]** dans le menu déroulant **[!UICONTROL Daterangeday]**, de sorte que la valeur soit mise à jour sur **[!UICONTROL MONTH(Daterangeday)]**.
   1. Faites glisser **[!UICONTROL Occurrences]** depuis la liste **[!UICONTROL Tables (*Mesurer les noms*)]** dans le volet **[!UICONTROL Données]** et déposez l’entrée dans le champ en regard de **[!UICONTROL Lignes]**.
      * Les valeurs sont automatiquement converties en **[!UICONTROL SUM(Occurrences)]**.
   1. Remplacez **[!UICONTROL Standard]** par **[!UICONTROL Vue entière]** dans le menu déroulant de la barre d’outils.

      Votre vue Feuille 1 doit ressembler à ce qui suit.

      ![Graphique de bureau Tableau](assets/uc4-tableau-graph.png)

1. Sélectionnez **[!UICONTROL Dupliquer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour créer une seconde feuille.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1]** pour renommer la feuille en `Graph`.
1. Sélectionnez **[!UICONTROL Renommer]** dans le menu contextuel de l’onglet **[!UICONTROL Feuille 1 (2)]** pour renommer la feuille en `Data`.
1. Assurez-vous que la feuille **[!UICONTROL Data]** est sélectionnée. Dans la vue Data :
   1. Sélectionnez **[!UICONTROL Afficher]** en haut à droite et sélectionnez **[!UICONTROL Tableau de texte]** (visualisation en haut à gauche) pour modifier le contenu de la vue de données en tableau.
   1. Faites glisser **[!UICONTROL MONTH(Daterangeday)]** de **[!UICONTROL Colonnes]** vers **[!UICONTROL Lignes]**.
   1. Remplacez **[!UICONTROL Standard]** par **[!UICONTROL Vue entière]** dans le menu déroulant de la barre d’outils.

      Votre vue **[!UICONTROL Data]** doit ressembler à ce qui suit.

      ![Données de bureau Tableau](assets/uc4-tableau-data.png)

1. Sélectionnez le bouton d’onglet **[!UICONTROL Nouveau tableau de bord]** (en bas) pour créer une nouvelle vue **[!UICONTROL Tableau de bord 1]**. Dans la vue **[!UICONTROL Tableau de bord 1]** :
   1. Faites glisser et déposez la feuille **[!UICONTROL Graph]** de l’étagère **[!UICONTROL Sheets]** sur la vue **[!UICONTROL Tableau de bord 1]** qui indique *Déposez les feuilles ici*.
   1. Faites glisser et déposez la feuille **[!UICONTROL Data]** de l’étagère **[!UICONTROL Sheets]** sous la feuille **[!UICONTROL Graph]** sur la vue **[!UICONTROL Tableau de bord 1]**.
   1. Sélectionnez la feuille **[!UICONTROL Data]** dans la vue et modifiez la **[!UICONTROL vue entière]** en **[!UICONTROL largeur du correctif]**.

      Votre vue **[!UICONTROL Tableau de bord 1]** doit ressembler à ce qui suit.

      ![Tableau de bord de bureau Tableau 1](assets/uc4-tableau-dashboard.png)

>[!ENDTABS]

+++


## Classement d’une seule dimension

Synopsis du cas d’utilisation

+++ Détails

>[!PREREQUISITES]
>
>Vérifiez que vous avez validé une [connexion réussie et que vous pouvez répertorier les vues de données](#connect-and-list-data-views) pour l’outil de BI pour lequel vous souhaitez tester ce cas d’utilisation.
>

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++


## Classement de plusieurs dimensions

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++


## Compter les valeurs de dimension distinctes

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Utilisation des noms de période pour le filtrage

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Utiliser les noms de filtre pour filtrer

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Utiliser les valeurs de dimension pour le filtrage

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Tri

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Limites

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## À ALABOUTER ou non

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Conversion des Dimensions et des mesures

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++



## Visualisations et interactions

Synopsis du cas d’utilisation

+++ Détails

>[!BEGINTABS]

>[!TAB Bureau de Power BI]

Étapes

>[!TAB Tableau Desktop]

Étapes

>[!ENDTABS]

+++


