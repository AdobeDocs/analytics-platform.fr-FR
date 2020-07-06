---
title: Création d’une connexion
description: Décrit comment créer une connexion à un jeu de données Platform dans Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 68%

---


# Création d’une connexion

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

Cliquez [ici](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) pour une présentation vidéo.

>[!IMPORTANT]
>
>Vous pouvez combiner plusieurs jeux de données [!DNL Experience Platform] en une seule connexion.

1. Accédez à [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Cliquez sur **[!UICONTROL Créer une nouvelle connexion]** en haut à droite.

   ![Établissement d’une connexion](assets/create-connection.png)

1. Choisissez un sandbox dans l’Experience Platform qui contient le ou les jeux de données auxquels vous voulez créer une connexion.

   Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. Vous pouvez considérer les sandbox comme des &quot;silos de données&quot; contenant des ensembles de données. Les sandbox permettent de contrôler l’accès aux jeux de données. Vous ne pouvez pas accéder aux données dans les sandbox. Une fois que vous avez sélectionné le sandbox, le rail de gauche affiche tous les jeux de données de ce sandbox que vous pouvez extraire.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (Si vous avez le choix entre de nombreux jeux de données, vous pouvez rechercher les jeux de données appropriés à l’aide de la barre de recherche située au-dessus de la liste des jeux de données.)

1. Next, for each dataset that you added to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | Type de jeu de données | Description | Horodatage | Schéma | ID de personne |
   |---|---|---|---|---|
   | [!UICONTROL Événement] | Données qui représentent des événements dans le temps (par exemple, visites Web, interactions, transactions, données de point de vente, données de questionnaire, données d’impression, etc.). Par exemple, il peut s’agir de données standard de flux de clics, avec un ID de client ou un ID de cookie, et un horodatage. Avec les données d’événement, vous disposez d’une flexibilité quant à l’ID utilisé comme ID de personne. | Est automatiquement défini sur le champ d’horodatage par défaut à partir des schémas basés sur un événement dans [UICONTROL Experience Platform]. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Série temporelle ». Par exemple, « Événement d’expérience XDM » ou « Événement de décision XDM ». | Vous pouvez sélectionner l’ID de personne à inclure. Chaque schéma de jeux de données défini dans Experience Platform peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un Espace de nommage d’identité. N’importe lequel de ces paramètres peut être utilisé comme ID de personne. Par exemple, l’ID de cookie, l’ID regroupé, l’ID utilisateur, le code de suivi, etc. |
   | [!UICONTROL Recherche] | Analogue à un fichier de classifications. Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données d’événement ou de profil. Vous pouvez, par exemple, charger des données de recherche qui mettent en correspondance les ID numériques de vos données d’événement avec les noms de produits. | S.O. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Enregistrement (Record) », à l’exception de la classe « Profil XDM individuel ». | S.O. |
   | [!UICONTROL Profil] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. Vous permet, par exemple, de charger des données CRM à propos de vos clients. | S.O. | Tout schéma intégré ou personnalisé basé sur la classe « Profil XDM individuel ». | Vous pouvez sélectionner l’ID de personne à inclure. Chaque jeu de données défini dans [!DNL Experience Platform] a son propre jeu d’un ou plusieurs ID de personne définis, tels que l’ID de cookie, l’ID regroupé, l’ID d’utilisateur, le code de suivi, etc.<br>![ID de personne](assets/person-id.png)**Remarque :** Si vous créez une connexion qui comprend des jeux de données avec des ID différents, les rapports le reflèteront. Pour véritablement fusionner des jeux de données, vous devez utiliser le même ID de personne. |

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder à la boîte de dialogue [!UICONTROL Créer une connexion] .

   ![Établissement d’une connexion](assets/create-connection2.png)

1. In the [!UICONTROL Create Connection] dialog, define these settings:

   | Champ | Description |
   |---|---|
   | [!UICONTROL Nom de la connexion] | Attribuez un nom explicite à la connexion. Impossible d’enregistrer la connexion sans nom. |
   | [!UICONTROL Description] | Ajoutez plus de détails pour distinguer cette connexion des autres. |
   | [!UICONTROL Jeux de données] | Les jeux de données inclus dans cette connexion. |
   | [!UICONTROL Importez automatiquement tous les nouveaux jeux de données à partir d&#39;aujourd&#39;hui.] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL Importer toutes les données existantes] | Lorsque vous sélectionnez cette option et enregistrez la connexion, toutes les données existantes (historiques) provenant de [!DNL Experience Platform] pour tous les jeux de données présents dans cette connexion seront importées. A l’avenir, toutes les données historiques existantes pour tout nouveau jeu de données ajouté à cette connexion enregistrée seront également importées automatiquement. <br>**Notez qu’une fois cette connexion enregistrée, ce paramètre ne peut plus être modifié.** |

   **Gardez les éléments suivants à l’esprit :**

   * Si la taille cumulée des données historiques pour tous les jeux de données de la connexion dépasse 1,5 milliard de lignes, un message d’erreur indique que vous ne pouvez pas importer cette quantité de données historiques. Cependant, si vous ajoutez un jeu de données contenant 1 milliard de lignes de données historiques et importez ces données, et une semaine plus tard, ajoutez un autre jeu de données de la même taille et importez ses données historiques, cela fonctionnera.
   * Nous donnons la priorité aux nouvelles données ajoutées à un jeu de données dans la connexion, de sorte que ces données ont la latence la plus faible.
   * Les données de renvoi (historiques) sont importées plus lentement.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

L’étape suivante du processus consiste à [créer une vue de données](/help/data-views/create-dataview.md).
