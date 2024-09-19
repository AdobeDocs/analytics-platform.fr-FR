---
title: Ajout de données de compte en tant que jeu de données de recherche
description: Découvrez comment ajouter des données de compte en tant que jeu de données de recherche à Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 36%

---

# Ajout de données de compte en tant que jeu de données de recherche

Ce cas pratique B2B vous montre comment ajouter des données de compte à une analyse au niveau de la personne et au niveau de l’événement. Lorsque vous ajoutez des données de compte, vous pouvez répondre à des questions telles que :

* Quel nom de société est associé à ce compte ?
* Quels rôles sont représentés dans ce compte ?
* Certains rôles (tels que celui de responsable informatique) se comportent-ils différemment d’un compte à l’autre ?

Pour ajouter des informations sur les données de compte, vous ajoutez et utilisez un jeu de données [lookup](/help/technotes/glossary.md) qui contient ces informations.

Les étapes impliquées sont les suivantes :

1. [Créez un schéma de recherche](#create-lookup-schema) dans Experience Platform.
1. [Créez un jeu de données de recherche](#create-lookup-dataset) dans Experience Platform qui vous permet d’ingérer des données de compte au format CSV.
1. [Combinez des jeux de données dans une connexion](#combine-datasets-in-a-connection) en Customer Journey Analytics, y compris celui de recherche que vous avez créé.
1. [Créez une vue de données](#create-a-data-view-from-this-connection) en Customer Journey Analytics.
1. [Analysez ces données](#analyze-the-data-in-workspace) dans Workspace en Customer Journey Analytics.

>[!NOTE]
>
>La taille maximale des tables de recherche est de 1 Go.
>

## Création d’un schéma de recherche

Lorsque vous créez votre propre schéma pour la table [lookup](/help/technotes/glossary.md), ce schéma garantit que le jeu de données utilisé est disponible en Customer Journey Analytics avec la configuration correcte (type d’enregistrement). La bonne pratique consiste à [créer une classe de schéma personnalisée](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) qui peut être réutilisée pour toutes les tables de recherche.

![Créer une boîte de dialogue de nouvelle classe.](../assets/create-new-class.png)

## Création d’un jeu de données de recherche

Une fois le schéma créé, vous devez créer un jeu de données de recherche, basé sur ce schéma, dans Experience Platform. Ce jeu de données de recherche contient les informations de compte. Par exemple : nom de l’entreprise, nombre total d’employés, nom de domaine, secteur d’activité auquel appartient l’entreprise, chiffre d’affaires annuel, etc. Assurez-vous que les données contiennent un identifiant de personne qui peut être associé à l’identifiant de personne utilisé dans les données d’événement.

1. Dans Experience Platform, accédez à **[!UICONTROL Data Management > Jeux de données]**.
1. Cliquez sur **[!UICONTROL + Créer un jeu de données]**.
1. Cliquez sur **[!UICONTROL Créer un jeu de données à partir d’un schéma]**.
1. Sélectionnez la classe de schéma de recherche que vous avez créée.
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Nommez le jeu de données (par exemple, `B2B Info`) et décrivez-le.
1. Cliquez sur **[!UICONTROL Terminer]**.

## Ingestion de données

Les instructions sur la manière de [Mapper un fichier CSV à un schéma XDM](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) devraient être utile si vous utilisez un fichier CSV.

[D’autres méthodes](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) sont également disponibles.

L’intégration des données et la création de la table de recherche prennent environ 2 à 4 heures, en fonction de la taille de la table de recherche.

## Combiner des jeux de données dans une connexion

Pour cet exemple, vous combinez 3 jeux de données en une connexion de Customer Journey Analytics :

| Nom du jeu de données | Description | Classe de schéma Adobe Experience Platform | Informations sur le jeu de données |
| --- | --- | --- | --- |
| Impression B2B | Contient, au niveau du compte, des données au niveau de l’événement et du parcours de navigation. Par exemple, il contient l’identifiant de l’adresse email et l’identifiant de compte correspondant, ainsi que le nom marketing, pour la diffusion de publicités marketing. Il inclut également les impressions de ces publicités par utilisateur. | Basé sur la classe de schéma XDM ExperienceEvent | L’`emailID` est utilisé comme identité principale et se voit attribuer un espace de noms `Customer ID`. Par conséquent, il s’affiche comme **[!UICONTROL ID de personne]** par défaut en Customer Journey Analytics. ![Impressions](../assets/impressions-mixins.png) |
| Profil B2B | Ce jeu de données de profil vous en apprend davantage sur les utilisateurs d’un compte, comme leur fonction, le compte auquel ils sont associés, leur profil LinkedIn, etc. | Basé sur la classe de schéma Individual Profile d’XDM | Sélectionnez `emailID` comme ID principal dans ce schéma. |
| Informations B2B | Voir &quot;Création d’un jeu de données de recherche&quot; ci-dessus. | Compte B2B (classe de schéma de recherche personnalisée) | La relation entre `accountID` et le jeu de données d’impressions B2B est automatiquement créée lorsque vous connectez le jeu de données d’informations B2B au jeu de données d’impressions B2B en Customer Journey Analytics, comme décrit dans les étapes ci-dessous. ![Recherche](../assets/lookup-mixins.png) |

Voici comment combiner les jeux de données :

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Connexions]**.
1. Sélectionnez les jeux de données à combiner.
1. Pour le jeu de données d’informations B2B, sélectionnez la clé utilisée dans votre table de recherche (par exemple `personKey.sourceKey`). Sélectionnez ensuite sa clé correspondante (dimension correspondante), également dans votre jeu de données d’événement (par exemple p`ersonKey.sourceKey`).
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Nommez et décrivez la connexion, puis configurez-la en suivant de [ces instructions](/help/connections/create-connection.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Créer une vue de données à partir de cette connexion

Suivez les instructions de la section [création de vues de données](/help/data-views/create-dataview.md).

* Ajoutez tous les composants (dimensions et mesures) dont vous avez besoin dans les jeux de données. Assurez-vous que, pour les mesures nécessitant un dédoublonnage pour la surcomptage, vous configurez ces mesures en conséquence (voir la section [Paramètres du composant de déduplication des mesures](/help/data-views/component-settings/metric-deduplication.md)). Le nombre d’employés ou les recettes sont des exemples de ces mesures.

## Analyse des données dans Workspace

Vous pouvez désormais créer des projets Workspace à partir des données des trois jeux de données.

Vous pouvez par exemple trouver des réponses aux questions posées dans l’introduction :

* Ventilez l’identifiant d’email par l’identifiant de compte pour découvrir à quelle société appartient un identifiant d’email donné.
* Combien d’employés sont associés à un identifiant de compte donné ?
* À quel secteur d’activité est associé un identifiant de compte donné ?

>[!MORELIKETHIS]
>
>Pour plus d’informations, voir [Exemple de projet B2B](example.md) .

