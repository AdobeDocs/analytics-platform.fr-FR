---
title: Création d’une connexion
description: Décrit comment créer une connexion à un jeu de données Platform dans Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 756c6e7c187b76636cf96d18c949908a97db51ed
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 38%

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

   ![Établissement d’une connexion](assets/create-connection0.png)

1. Choisissez un sandbox dans l’Experience Platform qui contient le ou les jeux de données auxquels vous voulez créer une connexion.

   Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/fr-FR/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. Vous pouvez considérer les sandbox comme des &quot;silos de données&quot; contenant des ensembles de données. Les sandbox permettent de contrôler l’accès aux jeux de données. Vous ne pouvez pas accéder aux données dans les sandbox. Une fois que vous avez sélectionné le sandbox, le rail de gauche affiche tous les jeux de données de ce sandbox que vous pouvez extraire.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (If you have a lot of datasets to choose from, you can search for the right one(s) using the **[!UICONTROL Search datasets]** search bar above the list of datasets.)

## Configuration d’un jeu de données

Sur le côté droit, vous pouvez désormais configurer le jeu de données que vous avez ajouté.

![Configurer un jeu de données](assets/create-connection.png)

1. **[!UICONTROL Type]** de jeu de données : Pour chaque jeu de données que vous avez ajouté à cette connexion, [!UICONTROL Customer Journey Analytics] définit automatiquement le type de jeu de données en fonction des données entrantes.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | Type de jeu de données | Description | Horodatage | Schéma | ID de personne |
   |---|---|---|---|---|
   | [!UICONTROL Événement] | Données qui représentent des événements dans le temps (par exemple, visites Web, interactions, transactions, données de point de vente, données de questionnaire, données d’impression, etc.). Par exemple, il peut s’agir de données standard de flux de clics, avec un ID de client ou un ID de cookie, et un horodatage. Avec les données d’événement, vous disposez d’une flexibilité quant à l’ID utilisé comme ID de personne. | Est automatiquement défini sur le champ d’horodatage par défaut à partir des schémas basés sur un événement dans [UICONTROL Experience Platform]. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Série temporelle ». Par exemple, « Événement d’expérience XDM » ou « Événement de décision XDM ». | Vous pouvez sélectionner l’ID de personne à inclure. Chaque schéma de jeux de données défini dans Experience Platform peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un Espace de nommage d’identité. N’importe lequel de ces paramètres peut être utilisé comme ID de personne. Par exemple, l’ID de cookie, l’ID regroupé, l’ID utilisateur, le code de suivi, etc. |
   | [!UICONTROL Recherche] | Analogue à un fichier de classifications. Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données d’événement ou de profil. Vous pouvez, par exemple, charger des données de recherche qui mettent en correspondance les ID numériques de vos données d’événement avec les noms de produits. | S.O. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Enregistrement (Record) », à l’exception de la classe « Profil XDM individuel ». | S.O. |
   | [!UICONTROL Profil] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. Vous permet, par exemple, de charger des données CRM à propos de vos clients. | S.O. | Tout schéma intégré ou personnalisé basé sur la classe « Profil XDM individuel ». | Vous pouvez sélectionner l’ID de personne à inclure. Chaque jeu de données défini dans [!DNL Experience Platform] a son propre jeu d’un ou plusieurs ID de personne définis, tels que l’ID de cookie, l’ID regroupé, l’ID d’utilisateur, le code de suivi, etc.<br>![ID de personne](assets/person-id.png)**Remarque :** Si vous créez une connexion qui comprend des jeux de données avec des ID différents, les rapports le reflèteront. Pour véritablement fusionner des jeux de données, vous devez utiliser le même ID de personne. |

1. **[!UICONTROL ID]** du jeu de données : Cet identifiant est généré automatiquement.

1. **[!UICONTROL Horodatage]**: ajouter du contenu ici

1. **[!UICONTROL Schéma]**: Il s’agit du [schéma](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/schema/composition.html) sur lequel le jeu de données a été créé dans l’Adobe Experience Platform.

1. **[!UICONTROL ID]** de personne : Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma de jeux de données de l’Experience Platform. Pour plus d&#39;informations sur l&#39;utilisation de la carte d&#39;identité en tant qu&#39;ID de personne, reportez-vous à la section ci-dessous.

   >[!IMPORTANT]
   >
   >S’il n’y a pas d’ID de personne à choisir, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Vue [cette vidéo](https://youtu.be/G_ttmGl_LRU) sur la façon de définir une identité en Experience Platform.

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder à la boîte de dialogue [!UICONTROL Activer la connexion] .

### Utiliser la carte d&#39;identité comme identifiant de personne

Le Customer Journey Analytics prend désormais en charge la possibilité d’utiliser la carte d’identité pour son ID de personne. La carte d’identité est une structure de données de mappage qui permet à quelqu’un de télécharger des paires clé -> valeur. Les clés sont des espaces de nommage d&#39;identité et la valeur est une structure qui contient la valeur d&#39;identité. La carte d’identité existe sur chaque ligne/événement téléchargée et est renseignée pour chaque ligne en conséquence.

La carte d’identité est disponible pour tout jeu de données qui utilise un schéma basé sur la classe XDM [](https://docs.adobe.com/content/help/fr-FR/experience-platform/xdm/home.html) ExperienceEvent. Lorsque vous sélectionnez un jeu de données à inclure dans une connexion CJA, vous avez la possibilité de sélectionner un champ comme identifiant principal ou la carte d’identité :

![](assets/idmap1.png)

Si vous sélectionnez Carte d’identité, vous disposez de deux options de configuration supplémentaires :

| Option | Description |
|---|---|
| [!UICONTROL Utiliser l’espace de noms des ID principaux] | Ceci indique à CJA, par ligne, de trouver l’identité dans la carte d’identité marquée par un attribut primary=true et de l’utiliser comme ID de personne pour cette ligne. Cela signifie qu’il s’agit de la clé principale qui sera utilisée dans l’Experience Platform pour le partitionnement. Il est également le candidat idéal pour l’utilisation en tant qu’identifiant visiteur de la CJA (selon la façon dont le jeu de données est configuré dans une connexion de la CJA). |
| [!UICONTROL Espace de noms] | (Cette option n’est disponible que si vous n’utilisez pas l’Espace de nommage d’ID de Principal.) Identity namespaces are a component of [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) that serve as indicators of the context to which an identity relates. Si vous spécifiez un espace de nommage, CJA recherche la clé d’espace de nommage dans la carte d’identité de chaque ligne et utilise l’identité sous cet espace de nommage comme identifiant de personne pour cette ligne. Notez que, puisque CJA ne peut pas effectuer une analyse complète des jeux de données de toutes les lignes pour déterminer quels espaces de nommage sont réellement présents, tous les espaces de nommage possibles sont répertoriés dans la liste déroulante. Vous devez savoir quels espaces de nommage sont spécifiés dans les données ; cela ne peut pas être détecté automatiquement. |

### Cas de bord de la carte d’identité

Ce tableau présente les deux options de configuration lorsque des bordures sont présentes et indique comment elles sont gérées :

| Option | Aucun ID n&#39;est présent dans la carte d&#39;identité | Aucun ID n’est marqué comme principal | Plusieurs ID sont marqués comme principaux | L’ID unique est marqué comme principal | espace de nommage non valide avec un ID marqué comme principal |
|---|---|---|---|---|---|
| **Cochez la case &quot;Utiliser l’Espace de nommage d’ID d’Principal&quot;.** | La ligne est abandonnée par la CJA. | La ligne est ignorée par la CJA, car aucun ID principal n’est spécifié. | Tous les identifiants marqués comme principaux, sous tous les espaces de nommage, sont extraits dans une liste. Ils sont ensuite triés par ordre alphabétique. avec ce nouveau tri, le premier espace de nommage avec son premier identifiant est utilisé comme identifiant de personne. | L’ID unique marqué comme principal est utilisé comme ID de personne. | Même si l&#39;espace de nommage peut être non valide (il n&#39;est pas présent dans AEP), CJA utilisera l&#39;ID principal sous cet espace de nommage comme ID de personne. |
| **espace de nommage de carte d&#39;identité spécifique sélectionné** | La ligne est abandonnée par la CJA. | Tous les identifiants sous l’espace de nommage sélectionné sont extraits dans une liste et le premier est utilisé comme identifiant de personne. | Tous les identifiants sous l’espace de nommage sélectionné sont extraits dans une liste et le premier est utilisé comme identifiant de personne. | Tous les identifiants sous l’espace de nommage sélectionné sont extraits dans une liste et le premier est utilisé comme identifiant de personne. | Tous les identifiants sous l’espace de nommage sélectionné sont extraits dans une liste et le premier est utilisé comme identifiant de personne. (Seul un espace de nommage valide peut être sélectionné au moment de la création de la connexion. Il n’est donc pas possible qu’un espace de nommage/ID non valide soit utilisé comme ID de personne) |

## Activer la connexion

![Activer la connexion](assets/create-connection2.png)

1. Pour activer une connexion, définissez les paramètres suivants :

   | Option | Description |
   |---|---|
   | [!UICONTROL Nommer la connexion] | Attribuez un nom explicite à la connexion. Impossible d’enregistrer la connexion sans nom. |
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
