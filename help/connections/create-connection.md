---
title: Création d’une connexion
description: Décrit comment créer une connexion à un jeu de données de plateforme dans les analyses de parcours client.
translation-type: tm+mt
source-git-commit: b81116bba59c4b52dfe5b8b628c581e332a05c48
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 4%

---


# Création d’une connexion

Une connexion vous permet d’intégrer des jeux de données [!DNL Adobe Experience Platform] dans [!UICONTROL Workspace]. Pour générer des rapports sur [!DNL Experience Platform] les jeux de données, vous devez d’abord établir une connexion entre les jeux de données dans [!DNL Experience Platform] et [!UICONTROL Workspace].

Cliquez [ici](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) pour une présentation vidéo.

>[!IMPORTANT] Vous pouvez combiner plusieurs [!DNL Experience Platform] jeux de données en une seule connexion.

1. Go to [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Cliquez sur **[!UICONTROL Créer une nouvelle connexion]** en haut à droite.

![Établir une connexion](assets/create-connection.png)

1. Tout d’abord, sélectionnez un sandbox dans la plateforme d’expérience qui contient le ou les jeux de données auxquels vous souhaitez créer une connexion. Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. Vous pouvez considérer les sandbox comme des &quot;silos de données&quot; contenant des ensembles de données. Les sandbox permettent de contrôler l’accès aux jeux de données. Vous ne pouvez pas accéder aux données dans les sandbox.

1. Une fois que vous avez sélectionné le sandbox, le rail de gauche affiche tous les jeux de données dans ce sandbox à partir desquels vous pouvez extraire. Sélectionnez un ou plusieurs jeux de données à extraire dans les analyses [!UICONTROL de parcours] client, puis cliquez sur **[!UICONTROL Ajouter]**. (Si vous avez le choix entre de nombreux jeux de données, vous pouvez rechercher les bons jeux de données à l&#39;aide de la barre de recherche située au-dessus de la liste des jeux de données.)

1. Ensuite, pour chaque jeu de données que vous avez ajouté à cette connexion, [!UICONTROL Customer Journey Analytics] définit automatiquement le type de jeu de données en fonction des données entrées. Il existe trois types de jeux de données différents : [!UICONTROL Données de Événement] , de [!UICONTROL Profil] et de [!UICONTROL recherche] .

   | Type de jeu de données | Description | Horodatage | Schéma | ID de personne |
   |---|---|---|---|---|
   | [!UICONTROL Événement] | Données qui représentent les événements dans le temps (par exemple, visites Web, interactions, transactions, données POS, données de questionnaire, données d’impression, etc.). Par exemple, il peut s’agir de données de parcours de navigation standard, avec un ID de client ou un ID de cookie et un horodatage. Avec les données de Événement, vous disposez d’une souplesse quant à l’ID utilisé comme ID de personne. | Est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans la plate-forme [d’expérience]UICONTROL. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement &quot;Time Series&quot;. Par exemple, &quot;Événement d’expérience XDM&quot; ou &quot;Événement de décision XDM&quot;. | Vous pouvez sélectionner l’ID de personne à inclure. Chaque schéma de jeux de données défini dans la plateforme d’expérience peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un Espace de nommage d’identité. N’importe lequel de ces paramètres peut être utilisé comme ID de personne. Par exemple, l’ID de cookie, l’ID avec titre, l’ID utilisateur, le code de suivi, etc. |
   | [!UICONTROL Recherche] | Analogique à un fichier de classifications. Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données de Événement ou de Profil. Vous pouvez, par exemple, télécharger des données de recherche qui mappent les identifiants numériques de vos données de événement aux noms de produits. | S.O. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement &quot;Record&quot;, à l’exception de la classe &quot;XDM Individuel Profil&quot;. | S.O. |
   | [!UICONTROL Profil] | Analogue aux attributs  du client - pour les attributs non modifiables et non temporels. Données appliquées à vos visiteurs, utilisateurs ou clients dans les données du [!UICONTROL Événement] . Vous permet, par exemple, de transférer des données de gestion de la relation client sur vos clients. | S.O. | Tout schéma intégré ou personnalisé basé sur la classe &quot;Profil individuel XDM&quot;. | Vous pouvez sélectionner l’ID de personne à inclure. Chaque jeu de données défini dans le [!DNL Experience Platform] a son propre jeu d’un ou plusieurs ID de personne définis, tels que l’ID de cookie, l’ID avec titre, l’ID d’utilisateur, le code de suivi, etc.<br>![Personne](assets/person-id.png)**IDNote **: Si vous créez une connexion qui comprend des jeux de données avec des ID différents, le rapports en tiendra compte. Pour vraiment fusionner des jeux de données, vous devez utiliser le même ID de personne. |

1. Cliquez sur **[!UICONTROL Suivant]** pour accéder à la boîte de dialogue [!UICONTROL Créer une connexion] .

   ![Établir une connexion](assets/create-connection2.png)

1. Dans la boîte de dialogue [!UICONTROL Créer une connexion] , définissez les paramètres suivants :

   | Champ | Description |
   |---|---|
   | [!UICONTROL Nom de la connexion] | Attribuez un nom descriptif à la connexion. Impossible d&#39;enregistrer la connexion sans nom. |
   | [!UICONTROL Description] | Ajouter plus de détails pour distinguer cette connexion des autres. |
   | [!UICONTROL Jeux de données] | Jeu de données inclus dans cette connexion. |
   | [!UICONTROL Importez automatiquement tous les nouveaux jeux de données à partir d&#39;aujourd&#39;hui.] | Sélectionnez cette option si vous souhaitez établir une connexion permanente, de sorte que tous les nouveaux lots de données qui sont ajoutés aux jeux de données dans cette connexion soient automatiquement acheminés vers [!UICONTROL Workspace]. |
   | [!UICONTROL Importer toutes les données existantes] | Lorsque vous sélectionnez cette option et enregistrez la connexion, toutes les données existantes (historiques) de [!DNL Experience Platform] tous les jeux de données présents dans cette connexion seront importées. A l&#39;avenir, toutes les données historiques existantes pour tout nouveau jeu de données ajouté à cette connexion enregistrée seront également importées automatiquement. <br>**Notez qu&#39;une fois cette connexion enregistrée, ce paramètre ne peut plus être modifié.** |

   **Gardez les éléments suivants à l’esprit :**

   * Si la taille cumulée des données historiques pour tous les jeux de données de la connexion dépasse 1,5 milliard de lignes, un message d’erreur indique que vous ne pouvez pas importer cette quantité de données historiques. Cependant, si vous deviez ajouter un jeu de données contenant 1 milliard de lignes de données historiques et importer ces données, et une semaine plus tard, ajouter un autre jeu de données de la même taille et importer ses données historiques, cela fonctionnerait.
   * Nous donnons la priorité aux nouvelles données ajoutées à un jeu de données dans la connexion, de sorte que ces données ont la latence la plus faible.
   * Les données de renvoi (historiques) sont importées plus lentement.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

L’étape suivante du processus consiste à [créer une vue](/help/data-views/create-dataview.md)de données.
