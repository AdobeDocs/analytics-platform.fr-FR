---
title: Ingestion et utilisation de données à partir d’Adobe Analytics traditionnel
description: Expliquer comment ingérer des données à partir d’Adobe Analytics traditionnel
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
source-git-commit: 325dcd0862b8ac06b3b26c3ae349a8fce757cb6c
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 11%

---

# Ingestion et utilisation de données à partir d’Adobe Analytics traditionnel

Ce guide de démarrage rapide explique comment utiliser les données collectées par Adobe Analytics dans Customer Journey Analytics.

>[!PREREQUISITES]
>
>Adobe Analytics est sous licence et déployé sur un ou plusieurs de vos sites web, à l’aide de l’une des méthodes de mise en oeuvre documentées :
>
>- [Mise en œuvre d’Analytics à l’aide d’Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=fr)
>
>- [Mise en oeuvre d’Analytics à l’aide de l’extension Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=fr)
>
>- [Mise en œuvre d’Analytics avec JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


Pour ce faire, vous devez :

- **Configuration d’un connecteur source Adobe Analytics** dans Adobe Experience Platform. Cela permet d’ingérer vos données Adobe Analytics actuelles dans un jeu de données de Adobe Experience Platform.

- **Configurer une connexion** en Customer Journey Analytics. Cette connexion doit (au moins) inclure votre jeu de données Adobe Experience Platform.

- **Configuration d’une vue de données** dans Customer Journey Analytics pour définir les mesures et les dimensions à utiliser dans Analysis Workspace.

- **Configuration d’un projet** dans Customer Journey Analytics pour créer des rapports et des visualisations.


>[!NOTE]
>
>Il s’agit d’un guide simplifié sur la manière d’ingérer des données à l’aide du connecteur source Adobe Analytics et d’utiliser ces données dans Customer Journey Analytics. Il est vivement recommandé d’étudier les informations supplémentaires lorsqu’elles y sont référencées.


## Configuration d’un connecteur source Adobe Analytics

Le connecteur source Adobe Analytics vous permet d’importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform.

Pour créer un connecteur source Adobe Analytics :

1. Dans l’interface utilisateur de Platform, sélectionnez **[!UICONTROL Sources]**, depuis le rail de gauche.

2. Sélectionner **[!UICONTROL Adobe des applications]** de la liste de [!UICONTROL CATÉGORIES].

3. Sélectionner **[!UICONTROL Configuration]** ou **[!UICONTROL Ajouter des données]** dans la mosaïque Adobe Analytics.

   ![Sources](./assets/sources-overview.png)

4. Sélectionner **[!UICONTROL Suite de rapports]**. Dans la liste des suites de rapports, sélectionnez celle que vous souhaitez utiliser.

   ![Suites de rapports](./assets/report-suites.png)

   Sélectionnez **[!UICONTROL Suivant]**.

5. Sélectionner **[!UICONTROL Schéma par défaut]** comme la propriété [!UICONTROL Schéma cible]. Adobe Experience Platform crée automatiquement le schéma et le jeu de données correspondant pour mapper tous les champs standard de la suite de rapports Adobe Analytics sélectionnée.

   ![Schéma par défaut](./assets/default-schema.png)

   Sélectionnez **[!UICONTROL Suivant]**.

6. Nommez le flux de données et (éventuellement) décrivez-le.

   ![Détails du flux de données](./assets/dataflow-detail.png)

   Sélectionnez **[!UICONTROL Suivant]**.

7. Vérifiez la connexion et sélectionnez **[!UICONTROL Terminer]**.

   ![Révision](./assets/review.png)


Une fois la connexion créée, le flux de données est automatiquement créé pour renseigner un jeu de données avec les données Adobe Analytics de votre suite de rapports, y compris l’ingestion de 13 mois maximum de données historiques.

Une fois l’ingestion initiale terminée, vos données de suite de rapports Adobe Analytics sont prêtes à être utilisées par Customer Journey Analytics.

Voir [Création d’une connexion source Adobe Analytics dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) pour un tutoriel beaucoup plus complet.


## Configurer une connexion

Pour utiliser les données Adobe Experience Platform dans Customer Journey Analytics, vous créez une connexion qui inclut les données résultant de la configuration de votre schéma, de votre jeu de données et de votre workflow.

Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Espace de travail. Pour générer des rapports sur ces jeux de données, vous devez d’abord établir une connexion entre les jeux de données dans Adobe Experience Platform et Workspace.

Pour créer votre connexion :

1. Dans l’interface utilisateur du Customer Journey Analytics, sélectionnez **[!UICONTROL Connexions]** dans le volet de navigation supérieur.

2. Sélectionner **[!UICONTROL Créer une connexion]**.

3. Dans le [!UICONTROL Connexion sans titre] écran :

   Nommez et décrivez votre connexion dans [!UICONTROL Paramètres de connexion].

   Sélectionnez l’environnement de test approprié dans la [!UICONTROL Sandbox] list in [!UICONTROL Paramètres des données] et sélectionnez le nombre d’événements quotidiens dans la [!UICONTROL Nombre moyen d’événements quotidiens] liste.

   ![Paramètres de connexion](./assets/cja-connections-1.png)

   Sélectionner **[!UICONTROL Ajout de jeux de données]**.

   Dans le [!UICONTROL Sélectionner des jeux de données] étape [!UICONTROL Ajout de jeux de données]:

   - Sélectionnez le jeu de données automatiquement créé par le connecteur source Adobe Analytics et tout autre jeu de données que vous souhaitez inclure dans votre connexion.

      ![Ajouter des jeux de données](./assets/cja-connections-2a.png)

   - Sélectionnez **[!UICONTROL Suivant]**.
   Dans le [!UICONTROL Paramètres des jeux de données] étape [!UICONTROL Ajout de jeux de données]:

   - Pour chaque jeu de données :

      - Sélectionnez une [!UICONTROL ID de personne] à partir des identités disponibles définies dans les schémas du jeu de données dans Adobe Experience Platform.

      - Sélectionnez la source de données appropriée dans la [!UICONTROL Type de source de données] liste. Si vous spécifiez **[!UICONTROL Autre]**, puis ajoutez une description pour votre source de données.

      - Définir **[!UICONTROL Importer toutes les nouvelles données]** et **[!UICONTROL Renvoi de données existantes]** selon vos préférences.

      ![Configurer les jeux de données](./assets/cja-connections-3a.png)

   - Sélectionner **[!UICONTROL Ajout de jeux de données]**.
   Sélectionnez **[!UICONTROL Enregistrer]**.

Voir [Présentation des connexions](../connections/overview.md) pour plus d’informations sur la création et la gestion d’une connexion, ainsi que sur la sélection et la combinaison de jeux de données.

## Configuration d’une vue de données

Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion. Elle spécifie toutes les dimensions et mesures disponibles dans Analysis Workspace et les colonnes dont ces dimensions et mesures obtiennent leurs données. Les vues de données sont définies en vue de la création de comptes rendus des performances dans Analysis Workspace.

Pour créer votre vue de données :

1. Dans l’interface utilisateur du Customer Journey Analytics, sélectionnez **[!UICONTROL Vues des données]** dans le volet de navigation supérieur.

2. Sélectionner **[!UICONTROL Créer une vue de données]**.

3. Dans le [!UICONTROL Configurer] étape :

   Sélectionnez votre connexion dans le [!UICONTROL Connexion] liste.

   Nom et (éventuellement) description de la connexion.

   ![Configuration de la vue des données](./assets/cja-dataview-1.png)

   Sélectionner **[!UICONTROL Enregistrer et continuer]**.

4. Dans le [!UICONTROL Composants] étape :

   Ajoutez tout champ de schéma et/ou composant standard que vous souhaitez inclure au [!UICONTROL MESURES] ou [!UICONTROL Dimensions] des zones de composant.

   ![Composants de vue de données](./assets/cja-dataview-2.png)

   Sélectionner **[!UICONTROL Enregistrer et continuer]**.

5. Dans le [!UICONTROL Paramètres] étape :

   Paramètres de la ![vue de données](./assets/cja-dataview-3.png)

   Laissez les paramètres tels quels et sélectionnez **[!UICONTROL Enregistrer et terminer]**.

Voir [Présentation des vues des données](../data-views/data-views.md) pour plus d’informations sur la création et la modification d’une vue de données, sur les composants que vous pouvez utiliser dans votre vue de données et sur l’utilisation des paramètres de filtre et de session.


## Configuration d’un projet

Analysis Workspace est un outil de navigation flexible qui vous permet de créer rapidement des analyses et de partager des informations en fonction de vos données. Vous utilisez des projets Workspace pour combiner des composants de données, des tableaux et des visualisations afin de concevoir votre analyse et de la partager avec toute personne de votre entreprise.

Pour créer votre projet :

1. Dans l’interface utilisateur du Customer Journey Analytics, sélectionnez **[!UICONTROL Projets]** dans le volet de navigation supérieur.

2. Sélectionner **[!UICONTROL Projets]** dans le volet de navigation de gauche.

3. Sélectionner **[!UICONTROL Créer un projet]**.

   ![Projet Workspace](./assets/cja-projects-1.png)

   Sélectionner **[!UICONTROL Projet vierge]**.

   ![Workspace - Projet vierge](./assets/cja-projects-2.png)

4. Sélectionnez votre vue de données dans la liste.

   ![Workspace Select Data view](./assets/cja-projects-3.png).

5. Commencez à faire glisser et à déposer des dimensions et des mesures sur le [!UICONTROL Tableau à structure libre] dans le [!UICONTROL Panneau] pour créer votre premier rapport. À titre d’exemple, faites glisser `Program Points Balance` et `Page View` comme mesures et `email` comme dimension pour obtenir un aperçu rapide des profils qui ont visité votre site web et font partie du programme de fidélité collectant des points de fidélité.

   ![Workspace - Premier rapport](./assets/cja-projects-5.png)

Voir [Présentation d’Analysis Workspace](../analysis-workspace/home.md) pour plus d’informations sur la création de projets et la création de votre analyse à l’aide de composants, de visualisations et de panneaux.


>[!SUCCESS]
>
>Vous avez terminé toutes les étapes. Tout d’abord, en configurant le connecteur de source de données Adobe Analytics et en le configurant pour votre suite de rapports, vos données Adobe Analytics sont automatiquement chargées dans Adobe Experience Platform. Vous avez défini une connexion dans Customer Journey Analytics pour utiliser les données Adobe Analytics ingérées et d’autres données. Votre définition de vue de données vous a permis de spécifier la dimension et les mesures à utiliser. Vous avez enfin créé votre premier projet qui visualise et analyse vos données.

