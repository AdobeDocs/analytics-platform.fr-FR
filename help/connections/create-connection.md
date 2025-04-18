---
title: Créer ou modifier une connexion
description: Décrit comment créer ou modifier une connexion à un jeu de données Experience Platform dans Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '4906'
ht-degree: 83%

---

# Créer ou modifier une connexion {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="Enregistrements ajoutés"
>abstract="Le nombre d’enregistrements (lignes) ajoutés à une connexion pendant l’intervalle de temps sélectionné pour les jeux de données sélectionnés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="Enregistrements ignorés"
>abstract="Le nombre d’enregistrements (lignes) ignorés pendant le transfert de données pour une connexion pendant l’intervalle de temps sélectionné pour les jeux de données sélectionnés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="Enregistrements supprimés"
>abstract="Le nombre d’enregistrements (lignes) supprimés d’une connexion pendant l’intervalle de temps sélectionné pour les jeux de données sélectionnés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="Dernier ajout"
>abstract="La date et l’heure du dernier lot de tout jeu de données transféré vers une connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="Activer la fenêtre dynamique de données"
>abstract="Définissez la conservation des données comme une fenêtre dynamique en mois au niveau de la connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="Nombre moyen d’utilisations quotidiennes"
>abstract="Sélectionnez une plage pour le nombre d’événements quotidiens attendus pour l’ensemble de la connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsadded"
>title="Enregistrements ajoutés"
>abstract="Le nombre d’enregistrements (lignes) ajoutés à une connexion pendant l’intervalle de temps sélectionné pour les jeux de données sélectionnés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsskipped"
>title="Enregistrements ignorés"
>abstract="Le nombre d’enregistrements (lignes) ignorés pendant le transfert de données pour une connexion pendant l’intervalle de temps sélectionné pour les jeux de données sélectionnés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsdeleted"
>title="Enregistrements supprimés"
>abstract="Le nombre d’enregistrements (lignes) supprimés d’une connexion pendant l’intervalle de temps sélectionné pour les jeux de données sélectionnés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_lastadded"
>title="Dernier ajout"
>abstract="La date et l’heure du dernier lot de tout jeu de données transféré vers une connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_enablerollingdatawindow"
>title="Activer la fenêtre dynamique de données"
>abstract="Définissez la conservation des données comme une fenêtre dynamique en mois au niveau de la connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_averagenumberofdailyuses"
>title="Nombre moyen d’utilisations quotidiennes"
>abstract="Sélectionnez une plage pour le nombre d’événements quotidiens attendus pour l’ensemble de la connexion."



L’expérience de workflow de création et de modification de connexion apporte tous les paramètres de configuration de jeu de données et de connexion au centre de l’écran avec le workflow d’assistance. Elle fournit une expérience détaillée de sélection, de configuration et de révision de jeux de données. Elle vous permet également de spécifier des informations essentielles telles que le type, la taille, le schéma, l’identifiant du jeu de données, le statut du lot, le statut de renvoi, les ID de personne, etc., afin de réduire le risque d’une mauvaise configuration de connexion. Voici une vue d’ensemble des nouvelles fonctionnalités :

* Vous pouvez activer une période de conservation des données variable lors de la création de la connexion.
* Vous pouvez ajouter et supprimer des jeux de données d’une connexion. (Supprimer un jeu de données le supprime de la connexion et affecte toutes les vues de données associées et les projets Analysis Workspace sous-jacents.)
* Vous pouvez activer et demander des données de renvoi par jeu de données.
* Vous pouvez modifier des jeux de données, par exemple pour demander un autre renvoi.
* Vous pouvez importer des données existantes par jeu de données.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Créer et modifier une connexion](https://video.tv.adobe.com/v/343044/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Conditions préalables

Le nombre maximum de jeux de données que vous pouvez ajouter à une connexion est plafonné à 100. Le mix dépend du package de Customer Journey Analytics acheté par votre société.

Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

| Package **Select** | Package **Foundation** |
| --- | --- |
| Toute combinaison de jeux de données d’événement/de profil/recherche/résumé, jusqu’à 100 | Un jeu de données d’événement par connexion |
|  | Jusqu’à 99 jeux de données de profil, de recherche ou de résumé par connexion |

{style="table-layout:auto"}

## Créer et configurer la connexion {#create-connection}

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Connexions]**, éventuellement à partir de **[!UICONTROL Gestion des données]**, dans le menu supérieur.
1. Sélectionnez **[!UICONTROL Créer une connexion]**.

>[!BEGINTABS]

>[!TAB Standard]

![Paramètres de connexion sans titre.](assets/create-conn1.png)

>[!TAB B2B edition]

![Paramètres de connexion sans titre.](assets/create-conn1-b2b.png)

>[!ENDTABS]

Sur l’écran **[!UICONTROL Connexions]** > **[!UICONTROL Connexion sans titre]** :

1. Configurez les paramètres de connexion.

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Nom de la connexion]** | Saisissez un nom unique pour la connexion. |
   | **[!UICONTROL Description de la connexion]** | Décrivez l’objectif de cette connexion. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL ID DE Principal ]** | Sélectionnez l’identifiant principal approprié pour votre connexion : <ul><li>![Utilisateur](/help/assets/icons/User.svg) **[!UICONTROL Personne]** pour un scénario B2C</li><li> ![Création](/help/assets/icons/Building.svg) **[!UICONTROL Compte]** pour un scénario B2B.</li></ul> |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Conteneurs facultatifs ]** | Sélectionnez des conteneurs supplémentaires.<ul><li>**[!UICONTROL Compte global]** : permet la configuration de comptes globaux dans une connexion.</li><li>**[!UICONTROL Opportunité]** : permet la configuration des opportunités dans une connexion.</li><li>**[!UICONTROL Groupe d’achat]** : permet la configuration des groupes d’achat dans une connexion.</li><ul> |
   | **[!UICONTROL Sandbox]** | Dans Experience Platform, choisissez une sandbox qui contient le ou les jeux de données auxquels vous voulez créer une connexion.<p>Adobe Experience Platform fournit des [sandbox](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) qui divisent une instance de plateforme unique en environnements virtuels distincts pour favoriser le développement et l’évolution d’applications d’expérience digitale. Vous pouvez considérer les sandbox comme des « silos de données » contenant des jeux de données. Les sandbox permettent de contrôler l’accès aux jeux de données.<p>Une fois que vous avez sélectionné la sandbox, le rail de gauche affiche tous les jeux de données de cette sandbox que vous pouvez extraire. |
   | **[!UICONTROL Activer la fenêtre dynamique de conservation des données]** | Si vous cochez cette case, elle vous permet de définir la conservation des données Customer Journey Analytics sous la forme d’une fenêtre dynamique en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion.<p>La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Cependant, si votre connexion inclut un profil ou des jeux de données de recherche (en plus d’un ou plusieurs jeux de données d’événement), ces données sont conservées pendant la même période.<p> Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.<p>Si vous laissez la valeur par défaut (non cochée), le paramètre de conservation des données d’Adobe Experience Platform remplace la période de conservation. Si vous avez 25 mois de données dans Experience Platform, Customer Journey Analytics obtient 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, Customer Journey Analytics conserve les 15 mois restants. |
   | **[!UICONTROL Ajouter des jeux de données]** (voir ci-dessous) | Ajoutez des jeux de données si aucun jeu de données n’apparaît dans le tableau du jeu de données. Sinon, vous verrez une liste des jeux de données que vous avez déjà ajoutés dans le cadre de la création de la connexion. |


   Pour les jeux de données que vous avez configurés, le tableau des jeux de données affiche les colonnes suivantes :

   | Colonne | Description |
   |---|---|
   | **[!UICONTROL Nom du jeu de données]** | Sélectionnez un ou plusieurs jeux de données à extraire dans Customer Journey Analytics et choisissez **[!UICONTROL Ajouter]**.<p>(Si vous avez le choix entre de nombreux jeux de données, vous pouvez les rechercher à l’aide de la barre de recherche située au-dessus de la liste des jeux de données.) |
   | **[!UICONTROL Dernière mise à jour]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. « S/O » signifie que ce jeu de données ne contient aucune donnée. |
   | **[!UICONTROL Nombre d’enregistrements]** | Total des enregistrements du mois précédent pour le jeu de données dans Experience Platform. |
   | **[!UICONTROL Schéma]** | Le [schéma](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition) à partir duquel le jeu de données a été créé dans Adobe Experience Platform. |
   | **[!UICONTROL Type de jeu de données]** | Pour chaque jeu de données que vous avez ajouté à cette connexion, Customer Journey Analytics définit automatiquement le type de jeu de données en fonction des données qui y sont entrées. Il existe trois types de jeux de données différents : les données Événement, les données Profil et les données de Recherche. Consultez le tableau ci-dessous pour obtenir une explication des types de jeux de données. |
   | **[!UICONTROL Granularité]** | Granularité des données du jeu de données, applicable uniquement aux jeux de données de résumé. |
   | **[!UICONTROL Type de source de données]** | Type de source de données du jeu de données. Non applicable pour les jeux de données de résumé. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL ID de compte ]** | Identifiant de compte utilisé pour prendre en charge le compte rendu des performances basé sur les comptes pour le jeu de données. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL ID de compte global ]** | Identifiant de compte global utilisé pour rechercher les données de compte globales. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL ID de groupe d&#39;achat ]** | Identifiant du groupe d&#39;achat utilisé pour rechercher les données du groupe d&#39;achat. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Opportunity ID ]** | Identifiant de l’opportunité utilisé pour rechercher des données d’opportunité. |
   | **[!UICONTROL ID de personne]** | ID de personne utilisé pour prendre en charge les rapports basés sur les personnes pour le jeu de données. |
   | **[!UICONTROL Clé]** | Pour les jeux de données de recherche uniquement (tels que _id). |
   | **[!UICONTROL Clé correspondante]** | Pour les jeux de données de recherche uniquement (tels que _id). |
   | **[!UICONTROL Importer de nouvelles données]** | Définissez cette option sur Activé ou Désactivé. |
   | **[!UICONTROL Renvoyer les données]** | Vous pouvez demander de renvoyer les données dans un jeu de données. Vous pouvez, par exemple, demander le renvoi des 7 derniers jours de données. Configurez correctement le jeu de données et testez votre connexion. Si tout semble correct, vous pouvez renvoyer facilement toutes les données restantes.<p>En outre, vous pouvez activer l’import de nouvelles données par jeu de données. |
   | **[!UICONTROL Statut de renvoi]** | Ce statut indique si des données de renvoi sont en cours de traitement. |

   Vous pouvez rechercher un jeu de données spécifique à l’aide du champ ![Rechercher](/help/assets/icons/Search.svg).


## Ajouter des jeux de données {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_primaryid"
>title="ID principal"
>abstract="Sélectionnez l’ID principal approprié à votre connexion : Personne pour un scénario B2C. Compte pour un scénario B2B."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_optionalcontainers"
>title="Conteneurs facultatifs"
>abstract="Sélectionnez des conteneurs supplémentaires.<br/><br/>**[!UICONTROL Compte global ]** : permet la configuration de comptes globaux dans une connexion.<br/>**[!UICONTROL Opportunité]** : permet la configuration des opportunités dans une connexion.<br/>**[!UICONTROL Groupe d’achat ]** : permet la configuration des groupes d’achat dans une connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_personid"
>title="ID de personne"
>abstract="Sélectionnez un ID de personne parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountid"
>title="ID de compte"
>abstract="Sélectionnez un ID de compte (l’identifiant unique d’un compte) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountfield"
>title="Champ de compte"
>abstract="Sélectionnez un champ qui représente l’identifiant de compte (identifiant unique d’un compte)."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_globalaccountid"
>title="Identifiant de compte global"
>abstract="Sélectionnez un ID de compte global (l’identifiant unique d’un compte) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityid"
>title="ID de l’opportunité"
>abstract="Sélectionnez un ID d’opportunité (l’identifiant unique d’une d’opportunité) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_buyinggroupid"
>title="ID du groupe d’achat"
>abstract="Sélectionnez un ID de groupe d’achat (l’identifiant unique d’un groupe d’achat) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="Clé correspondante"
>abstract="Sélectionnez le mode de jointure : en fonction d’une clé ou d’un conteneur correspondants.<br/><br/>**[!UICONTROL Clé correspondante ]** : sélectionnez un champ à joindre à l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas ajouté ni configuré de jeu de données d’événement.<br/>**[!UICONTROL Conteneur correspondant]** : sélectionnez un conteneur à utiliser à joindre à l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas configuré un ou plusieurs conteneurs."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="Importer de nouvelles données"
>abstract="Tout nouveau lot ajouté au jeu de données Experience Platform sera automatiquement ajouté à cette connexion et mis à disposition pour analyse."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="Renvoi du jeu de données"
>abstract="Cette option renverra les données existantes (historiques) dʼExperience Platform pour ce jeu de données dans la connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="Transformer le jeu de données"
>abstract="Cette option transforme le jeu de données de manière à ce qu’il puisse être utilisé pour des recherches basées sur les personnes dans des scénarios B2B. Une fois activée, la transformation du jeu de données est irréversible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_connectionmap"
>title="Carte de connexion"
>abstract="La carte de connexion visualise les relations entre les jeux de données d’événement, de personne, de compte et de recherche pertinents (tels que les opportunités, les membres des campagnes, etc.)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_primaryid"
>title="ID principal"
>abstract="Sélectionnez l’ID principal approprié à votre connexion : Personne pour un scénario B2C. Compte pour un scénario B2B."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_optionalcontainers"
>title="Conteneurs facultatifs"
>abstract="Sélectionnez des conteneurs supplémentaires.<br/><br/>**[!UICONTROL Compte global ]** : permet la configuration de comptes globaux dans une connexion.<br/>**[!UICONTROL Opportunité]** : permet la configuration des opportunités dans une connexion.<br/>**[!UICONTROL Groupe d’achat ]** : permet la configuration des groupes d’achat dans une connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_personid"
>title="ID de personne"
>abstract="Sélectionnez un ID de personne parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountid"
>title="ID de compte"
>abstract="Sélectionnez un ID de compte (l’identifiant unique d’un compte) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountfield"
>title="Champ de compte"
>abstract="Sélectionnez un champ qui représente l’identifiant de compte (identifiant unique d’un compte)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_globalaccountid"
>title="Identifiant de compte global"
>abstract="Sélectionnez un ID de compte global (l’identifiant unique d’un compte) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_opportunityid"
>title="ID de l’opportunité"
>abstract="Sélectionnez un ID d’opportunité (l’identifiant unique d’une d’opportunité) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_buyinggroupid"
>title="ID du groupe d’achat"
>abstract="Sélectionnez un ID de groupe d’achat (l’identifiant unique d’un groupe d’achat) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_matchingkey"
>title="Clé correspondante"
>abstract="Sélectionnez le mode de jointure : en fonction d’une clé ou d’un conteneur correspondants.<br/><br/>**[!UICONTROL Clé correspondante ]** : sélectionnez un champ à joindre à l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas ajouté ni configuré de jeu de données d’événement.<br/>**[!UICONTROL Conteneur correspondant]** : sélectionnez un conteneur à utiliser à joindre à l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas configuré un ou plusieurs conteneurs."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_importnewdata"
>title="Importer de nouvelles données"
>abstract="Tout nouveau lot ajouté au jeu de données Experience Platform sera automatiquement ajouté à cette connexion et mis à disposition pour analyse."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_datasetbackfill"
>title="Renvoi du jeu de données"
>abstract="Cette option renverra les données existantes (historiques) dʼExperience Platform pour ce jeu de données dans la connexion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_transformdataset"
>title="Transformer le jeu de données"
>abstract="Cette option transforme le jeu de données de manière à ce qu’il puisse être utilisé pour des recherches basées sur les personnes dans des scénarios B2B. Une fois activée, la transformation du jeu de données est irréversible."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_connectionmap"
>title="Carte de connexion"
>abstract="La carte de connexion visualise les relations entre les jeux de données d’événement, de personne, de compte et de recherche pertinents (tels que les opportunités, les membres des campagnes, etc.)."



Le workflow permet d’ajouter un ou plusieurs jeux de données Experience Platform lors de la création d’une connexion.


1. Dans la boîte de dialogue Paramètres de connexion, cliquez sur **[!UICONTROL Ajouter des jeux de données]**.

1. À l’étape ➊ **[!UICONTROL Sélectionner des jeux de données]**, une liste des jeux de données Experience Platform s’affiche.

   ![Sélection de jeux de données](assets/select-datasets.png)

   Pour chaque jeu de données, la liste affiche les éléments suivants :

   | Colonne | Description |
   |---|---|
   | **[!UICONTROL Jeu de données]** | Nom du jeu de données. Sélectionnez le nom pour vous diriger vers le jeu de données dans Experience Platform. Sélectionnez ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) pour afficher une fenêtre contextuelle contenant plus de détails sur le jeu de données. Vous pouvez sélectionner **[!UICONTROL Modifier dans Platform]** pour modifier le jeu de données directement dans Experience Platform. |
   | **[!UICONTROL Type de jeu de données]** | Type de jeu de données : Événement, Profil, Recherche ou Résumé. |
   | **[!UICONTROL Nombre d’enregistrements]** | Total des enregistrements du mois précédent pour le jeu de données dans Experience Platform. |
   | **[!UICONTROL Schéma]** | Schéma du jeu de données. Sélectionnez le nom pour vous diriger vers le schéma dans Experience Platform. |
   | **[!UICONTROL Dernier lot]** | État du dernier lot ingéré dans Experience Platform. Voir [États des lots](https://experienceleague.adobe.com/fr/docs/experience-platform/ingestion/batch/troubleshooting#batch-states) pour plus d’informations. |
   | **[!UICONTROL Identifiant du jeu de données]** | ID du jeu de données. |
   | **[!UICONTROL Dernière mise à jour]** | Dernier horodatage mis à jour du jeu de données. |

   * Pour modifier les colonnes affichées de la liste des jeux de données, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) et sélectionnez les colonnes à afficher dans la boîte de dialogue [!UICONTROL Personnaliser le tableau].
   * Pour rechercher un jeu de données spécifique, utilisez le champ de recherche ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Pour basculer entre l’affichage ou le masquage des jeux de données sélectionnés, sélectionnez ![Sélectionner](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg), **[!UICONTROL Masquer la sélection]** ou **[!UICONTROL Afficher la sélection]**.
   * Pour supprimer un jeu de données de la liste des jeux de données sélectionnés, utilisez ![Fermer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Pour supprimer tous les jeux de données sélectionnés, sélectionnez **[!UICONTROL Effacer tout]**.


1. Sélectionnez un ou plusieurs jeux de données, puis cliquez sur **[!UICONTROL Suivant]**. Vous allez [configurer](#configure-datasets) chacun des jeux de données. Au moins un jeu de données d’événement doit faire partie de la connexion.


## Configurer des jeux de données

Vous configurez chacun des jeux de données sélectionnés, un par un, à l’étape ➋ **[!UICONTROL Paramètres des jeux de données]** de la boîte de dialogue **[!UICONTROL Ajouter des jeux de données]**.

>[!BEGINTABS]

>[!TAB Standard]

![Ajouter des jeux de données](assets/add-dataset.png)

>[!TAB B2B edition]

![Ajouter un jeu de données B2B](assets/add-dataset-b2b.png)

>[!ENDTABS]

| Paramètre | Description |
| --- | --- |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL ID de compte ]** | Disponible uniquement pour les jeux de données d’événement et pour les jeux de données de recherche [associés par conteneur](/help/getting-started/cja-b2b-concepts-features.md#match-by-container-or-field). Sélectionnez un ID de compte (l’identifiant unique d’un compte) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Opportunity ID ]** | Disponible uniquement pour les jeux de données d’événement. Sélectionnez un ID d’opportunité (l’identifiant unique d’une d’opportunité) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL ID de groupe d&#39;achat ]** | Disponible uniquement pour les jeux de données d’événement. Sélectionnez un ID de groupe d’achat (l’identifiant unique d’un groupe d’achat) parmi les identités disponibles définies dans le schéma du jeu de données d’Experience Platform. |
| **[!UICONTROL ID de personne]** | Disponible uniquement pour les jeux de données d’événement et de profil. Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>Si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations. <p>La valeur de l’ID de personne sélectionné est considérée comme sensible à la casse. Par exemple : `abc123` et `ABC123` sont deux valeurs différentes. |
| **[!UICONTROL Date et heure]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. |
| **[!UICONTROL Clé]** | Disponible uniquement pour les jeux de données de recherche. Clé à utiliser pour un jeu de données de recherche. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} **[!UICONTROL Type de clé correspondant]** | Sélectionnez le mode de jointure des jeux de données : en fonction d’une **[!UICONTROL Correspondance par champ]** ou d’une **[!UICONTROL Correspondance par conteneur]**. Pour plus d’informations, voir [Correspondance par conteneur de champ](/help/getting-started/cja-b2b-concepts-features.md#match-by-container-or-field). |
| **[!UICONTROL Clé correspondante]** | Disponible uniquement pour les jeux de données de recherche ou de profil. Clé correspondante à joindre à l’un des jeux de données d’événement. Si cette liste est vide, il est probable que vous n’ayez pas ajouté ou configuré de jeu de données d’événement. <br/><br/>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>En fonction du **[!UICONTROL type de clé correspondant]** sélectionné, sélectionnez la valeur appropriée :<ul><li>**[!UICONTROL Correspondance par champ]** : sélectionnez un champ pour joindre l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas ajouté ni configuré de jeu de données d’événement.</li><li>**[!UICONTROL Correspondance par conteneur]** : sélectionnez un conteneur à utiliser pour se joindre à l’un des jeux de données d’événement. Les conteneurs disponibles à sélectionner sont déterminés par les conteneurs que vous avez inclus dans le cadre de la configuration de la connexion. Si cette liste est vide, vous n’avez probablement pas configuré un ou plusieurs conteneurs.</li></ul> |
| [!BADGE Champ B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Account ]** | Identifiant de compte à utiliser pour le compte-rendu des performances basé sur les comptes. |
| **[!UICONTROL Fuseau horaire]** | Disponible uniquement pour les données de résumé. Sélectionnez le fuseau horaire approprié pour les données de résumé de série temporelle. |
| **[!UICONTROL Type de source de données]** | Sélectionnez un type de source de données. <br/>Les types de sources de données incluent les éléments suivants : <ul><li>[!UICONTROL Données web]</li><li>[!UICONTROL Données d’application mobile]</li><li>[!UICONTROL Données de point de vente]</li><li>[!UICONTROL Données CRM]</li><li>[!UICONTROL Données de l’enquête]</li><li>[!UICONTROL Données du centre d’appels]</li><li>[!UICONTROL Données du produit]</li><li> [!UICONTROL Données des comptes]</li><li> [!UICONTROL Données de transaction]</li><li>[!UICONTROL Données de commentaires client]</li><li> [!UICONTROL Autre]</li></ul>Ce champ est utilisé pour interroger les types de sources de données en cours d’utilisation. |
| **[!UICONTROL Importer de nouvelles données]** | Activez cette option si vous souhaitez établir une connexion continue. Avec une connexion continue, les nouveaux lots de données ajoutés aux jeux de données sont automatiquement disponibles dans Workspace. |
| **[!UICONTROL Renvoi du jeu de données]** | Activez **[!UICONTROL Renvoyer toutes les données existantes]** pour vous assurer que toutes les données existantes sont renvoyées.<br/><br/>Sélectionnez **[!UICONTROL Renvoi de la demande]** pour renvoyer des données historiques pour une période spécifique. Vous pouvez définir jusqu’à 10 périodes de renvoi de jeux de données.<ol><li>Définissez la période en saisissant les données de début et de fin ou en sélectionnant des dates à l’aide du ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Sélectionnez **[!UICONTROL Renvoi de la file dʼattente]** pour ajouter le renvoi à la liste, ou bien **[!UICONTROL Annuler]** pour annuler.</li></ol>Pour chaque entrée, sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) pour modifier la période, ou sélectionnez ![Supprimer](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) pour supprimer l’entrée.<br/><br/>À propos des renvois :<ul><li>Vous pouvez renvoyer chaque jeu de données individuellement.</li><li>Vous donnez la priorité aux nouvelles données ajoutées à un jeu de données dans la connexion, de sorte que ces nouvelles données ont la latence la plus faible.</li><li>Les données de renvoi (historiques) sont importées plus lentement. La quantité de données historiques influence la latence.</li><li>Le connecteur source Analytics importe jusquʼà 13 mois de données pour les sandbox de production, et ce quelle que soit leur taille. Le renvoi dans les sanbox hors production est limité à 3 mois.</li></ul> |
| **[!UICONTROL Transformer le jeu de données]** | Pour des jeux de données de recherche B2B spécifiques, vous pouvez activer la transformation d’un jeu de données pour des scénarios de rapports individuels B2B appropriés. Voir [Transformer des jeux de données pour les recherches B2B](transform-datasets-b2b-lookups.md) pour plus d’informations. |
| **[!UICONTROL Statut du lot]** | Les indicateurs de statut possibles sont les suivants :<ul><li>Réussite</li><li>Traitement de X renvoi(s)</li><li>Off</li></ul> |
| **[!UICONTROL Identifiant du jeu de données]** | Cet identifiant est généré automatiquement. |
| **[!UICONTROL Description]** | Description donnée à ce jeu de données lors de sa création. |
| **[!UICONTROL Nombre d’enregistrements]** | La taille du jeu de données. |
| **[!UICONTROL Schéma]** | Le schéma à partir duquel le jeu de données a été créé dans Adobe Experience Platform. |
| **[!UICONTROL Jeu de données]** | Nom du jeu de données. |
| **[!UICONTROL Aperçu : *nom du jeu de données *]** | Prévisualise le jeu de données pour les 10 premières lignes et les 10 premières colonnes. |
| **[!UICONTROL Supprimer]** | Vous pouvez supprimer le jeu de données et modifier le [!UICONTROL ID de personne] ou le [!UICONTROL ID de compte] [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} sans supprimer l’ensemble de la connexion. Cette suppression permet de réduire les coûts liés à l’ingestion des données et le processus laborieux de recréation de l’ensemble de la connexion et des vues de données associées. |

{style="table-layout:auto"}

## Vue d’ensemble de la connexion {#preview}

Pour prévisualiser la connexion que vous avez créée, sélectionnez ![PageSearch](/help/assets/icons/PageSearch.svg) **[!UICONTROL Aperçu de la connexion]** dans la boîte de dialogue Paramètres de connexion.

![Vue d’ensemble de la connexion](assets/create-conn4.png)

Cet aperçu contient certaines colonnes répertoriant la configuration de la connexion. Les types de colonnes affichés dépendent de vos jeux de données individuels.


## Carte de connexion

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

Pour afficher une carte des relations entre les jeux de données qui font partie de votre connexion, sélectionnez ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Carte de connexion]** dans la boîte de dialogue Paramètres de connexion.

![Mappage de connexion](assets/connectionmap.png)

Cette carte vous permet de mieux comprendre comment vous avez défini votre connexion et configuré la relation entre vos jeux de données d’événement, de profil et de recherche à l’aide d’identifiants.

## Types de jeux de données {#dataset-types}

Pour chaque jeu de données que vous avez ajouté à cette connexion, [!UICONTROL Customer Journey Analytics] définit automatiquement le type de jeu de données en fonction des données qui y sont entrées.

>[!IMPORTANT]
>
>Ajoutez au moins un jeu de données d’événement ou de résumé dans le cadre d’une connexion.

Il existe différents types de jeux de données : les données [!UICONTROL Événement], les données [!UICONTROL Profil], les données [!UICONTROL Recherche] et les données [!UICONTROL Résumé].

| Type de jeu de données | Description | Horodatage | Schéma | ID de personne <br/> ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} |
|---|---|---|---|---|
| **[!UICONTROL Événement]** | Données qui représentent les événements dans le temps. Par exemple, visites web, interactions, transactions, données de point de vente, données d’enquête, données d’impression, etc. Ces données peuvent être des données de flux de clics typiques, avec un ID client ou un ID de cookie et un horodatage. Avec les données d’événement, vous disposez d’une flexibilité quant à l’ID utilisé comme ID de personne. | Automatiquement défini sur le champ d’horodatage par défaut à partir des schémas basés sur un événement dans [!UICONTROL Experience Platform]. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Série temporelle ». Par exemple, « Événement d’expérience XDM » ou « Événement de décision XDM ». | Vous pouvez choisir l&#39;ID de personne ou l&#39;ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} à inclure. Chaque schéma du jeu de données défini dans Experience Platform peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un espace de noms d’identité. N’importe laquelle de ces identités peut être utilisée comme ID de personne ou ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} . Par exemple, l’ID de cookie, l’ID regroupé, l’ID utilisateur, le code de suivi, l’ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} , etc. |
| **[!UICONTROL Rechercher]** | Vous pouvez ajouter des jeux de données en tant que recherches de champs dans tous les types de jeux de données : Profil, Recherche et Événement (ce dernier a toujours été pris en charge). Cette fonctionnalité supplémentaire accroît la capacité de Customer Journey Analytics à prendre en charge des modèles de données complexes, y compris B2B. Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données d’événement, de profil ou de recherche. Vous pouvez ajouter jusqu’à deux niveaux de recherche. (Notez que les [champs dérivés](/help/data-views/derived-fields/derived-fields.md) ne peuvent pas être utilisés comme clés de correspondance pour les recherches dans les connexions.) Vous pouvez, par exemple, charger des données de recherche qui mappent les identifiants numériques de vos données d’événement avec des noms de produits. Voir l’[exemple B2B](/help/use-cases/b2b/example.md). | S.O. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Enregistrement (Record) », à l’exception de la classe « Profil XDM individuel ». | S.O. |
| **[!UICONTROL Profil]** | Données appliquées à votre compte, personnes, utilisateurs ou clients dans les données [!UICONTROL Événement]. Vous permet, par exemple, de charger des données CRM à propos de vos clients. | S.O. | Tout schéma intégré ou personnalisé basé sur la classe « Profil XDM individuel ». | Vous pouvez choisir l’ID de personne/l’ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} à inclure. Chaque jeu de données (à l’exception des jeux de données de résumé), défini dans [!DNL Experience Platform], possède son propre jeu d’un ou plusieurs ID de personne ou de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} définis. Par exemple, l’ID de cookie, l’ID regroupé, l’ID utilisateur, l’ID de compte de code de suivi, etc.<br>![ID de personne ](assets/person-id.png)**Note** : si vous créez une connexion qui comprend des jeux de données avec des ID différents, les rapports le reflèteront. Pour fusionner des jeux de données, vous devez utiliser le même ID de personne ou ID de compte [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}. |
| **Résumé** | Données de série temporelle qui ne sont pas liées à un ID de personne individuel. Les données de résumé représentent des données agrégées à un niveau d’agrégation différent, par exemple des campagnes. Vous pouvez utiliser ces données dans Customer Journey Analytics pour prendre en charge divers cas d’utilisation. Voir la section [Données de résumé](/help/data-views/summary-data.md) pour plus d’informations. | Automatiquement défini sur le champ d’horodatage par défaut à partir des schémas de mesure de résumé basés sur un événement dans Experience Platform. Seule la granularité horaire ou quotidienne est prise en charge. | Tout schéma intégré ou personnalisé basé sur la classe « Mesure de résumé XDM ». | S.O. |

>[!MORELIKETHIS]
>
>Blog : [Utilisation des jeux de données d’événement, de recherche et de profil dans Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-to-leverage-event-lookup-and-profile-datasets-in-adobe/ba-p/681478)

## Utilisation des champs numériques comme clés et valeurs de recherche {#numeric}

Cette fonctionnalité de recherche est utile si vous souhaitez ajouter un champ numérique, comme un coût ou une marge, à un champ clé reposant sur une chaîne. Les valeurs numériques feront ainsi partie des recherches sous forme de clés ou de valeurs. Dans votre schéma de recherche, il se peut que des valeurs numériques soient liées, par exemple, à vos noms de produit, au COGS, à vos coûts de campagne marketing ou à vos marges. Voici un exemple de schéma de recherche dans Adobe Experience Platform :

![Schéma de recherche](assets/schema.png)

Vous prenez désormais en charge l’inclusion de ces valeurs sous forme de mesures ou de dimensions dans la création de rapports Customer Journey Analytics. Lorsque vous configurez votre connexion et extrayez des jeux de données de recherche, vous pouvez modifier les jeux de données de manière à sélectionner la [!UICONTROL Clé] et la [!UICONTROL Clé correspondante] :

![Edit-dataset](assets/lookup-dataset.png)

Lorsque vous configurez une vue de données reposant sur cette connexion, vous ajoutez les valeurs numériques en tant que composants de la vue de données. Tout projet basé sur cette vue de données peut alors créer des rapports sur ces valeurs numériques.

## Utiliser la carte des identités comme ID de personne {#id-map}

Customer Journey Analytics prend en charge la possibilité d’utiliser la carte des identités pour son ID de personne. La carte des identités est une structure de données de carte qui vous permet de télécharger des paires clé -> valeur. Les clés sont des espaces de noms d’identité et la valeur est une structure qui contient la valeur de l’identité. La carte des identités existe sur chaque ligne/événement téléchargé et est renseignée pour chaque ligne en conséquence.

La carte des identités est disponible pour tout jeu de données qui utilise un schéma basé sur la classe [XDM ExperienceEvent](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home). Lorsque vous sélectionnez un jeu de données à inclure dans une connexion Customer Journey Analytics, vous avez la possibilité de sélectionner un champ comme ID principal ou la carte des identités :

![](assets/idmap1.png)

Si vous sélectionnez Carte des identités, vous disposez de deux options de configuration supplémentaires :

| Option | Description |
|---|---|
| **[!UICONTROL Utiliser l’espace de noms des ID principaux]** | Cette option indique à Customer Journey Analytics de trouver l’identité dans le mappage d’identité signalée par un attribut `primary=true` et de l’utiliser comme ID de personne pour cette ligne. Cette identité est la clé primaire utilisée dans Experience Platform pour le partitionnement. Cette identité est également le candidat idéal pour l’utilisation en tant qu’ID de personne Customer Journey Analytics (selon la manière dont le jeu de données est configuré dans une connexion Customer Journey Analytics). |
| **[!UICONTROL Espace de noms]** | (Cette option n’est disponible que si vous n’utilisez pas l’espace de noms d’ID principal.) Les espaces de noms d’identité sont un composant du [service d’identités Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/namespaces). Les espaces de noms servent d’indicateurs pour le contexte auquel une identité se rapporte. Si vous spécifiez un espace de noms, Customer Journey Analytics recherche la carte des identités pour cette clé d’espace de noms dans chaque ligne et utilise l’identité sous cet espace de noms comme ID de personne pour cette ligne. Étant donné que Customer Journey Analytics ne peut pas effectuer d’analyse complète des jeux de données de toutes les lignes pour déterminer les espaces de noms présents, tous les espaces de noms possibles sont affichés dans la liste déroulante. Sachez quels espaces de noms sont spécifiés dans les données ; ces derniers ne sont pas détectés automatiquement. |

{style="table-layout:auto"}

### Cas extrême de la carte des identités {#id-map-edge}

Ce tableau présente les deux options de configuration lorsque des cas extrêmes sont présents et indique comment ils sont gérés :

| Option | Aucun ID n’est présent dans la carte des identités | Plusieurs ID, dont aucun n’est marqué comme principal | Plusieurs ID sont marqués comme principaux | ID unique, marqué comme principal ou non | Espace de noms non valide avec un ID marqué comme principal |
|---|---|---|---|---|---|
| **[!UICONTROL Utiliser l’espace de noms des ID principaux] coché** | Customer Journey Analytics supprime la ligne. | Customer Journey Analytics supprime la ligne, car aucun ID principal n’est spécifié. | Tous les identifiants marqués comme principaux, sous tous les espaces de noms, sont extraits dans une liste. Ils sont ensuite triés par ordre alphabétique. Avec ce nouveau tri, le premier espace de noms avec son premier ID est utilisé comme ID de personne. | L’ID unique est utilisé comme ID de personne. | Même si l’espace de noms peut être non valide (il n’est pas présent dans Adobe Experience Platform), Customer Journey Analytics utilise l’ID principal sous cet espace de noms comme ID de personne. |
| **[!UICONTROL Espace de noms de carte des identités spécifique] sélectionné** | Customer Journey Analytics supprime la ligne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. (Seul un espace de noms valide peut être sélectionné au moment de la création de la connexion. Il n’est donc pas possible qu’un espace de noms/ID non valide soit utilisé comme ID de personne). |

{style="table-layout:auto"}

## Calculer le nombre moyen dʼévénements quotidiens {#average-number}

Ce calcul est effectué pour chaque jeu de données de la connexion.

1. Accédez aux [services de requête d’Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/query/home) et créez une nouvelle requête.

   La requête ressemblerait à ceci :

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   Dans cet exemple, « analytics_demo_data » est le nom du jeu de données.

2. Pour afficher tous les jeux de données qui existent dans Adobe Experience Platform, exécutez la requête `Show Tables`.


## Optimisation algorithmique des jeux de données de recherche volumineux

Lors de la création d’une connexion, vous pouvez ajouter des jeux de données volumineux à des fins de recherche. Par exemple, un jeu de données représentant un catalogue de produits peut faire l’objet d’une recherche d’informations descriptives sur les produits lors de la création de rapports et de visualisations. Un jeu de données de recherche aussi volumineux peut dépasser la limite maximale de 10 millions de recherches uniques actuellement mise en œuvre en tant que mécanisme de sécurisation, ce qui entraîne l’absence de données supplémentaires.

Vous pouvez demander l’optimisation algorithmique d’un jeu de données de recherche volumineux. Cette optimisation algorithmique conserve uniquement les données dans le jeu de données de recherche qui correspondent aux clés de votre jeu de données d’événement. Ainsi, vous n’avez pas besoin de charger l’intégralité du jeu de données de recherche non optimisé. Les éléments anciens ou moins fréquemment utilisés sont supprimés, ce qui peut légèrement affecter les rapports, mais présente des avantages significatifs. L’algorithme prend en compte les 90 derniers jours et se met à jour chaque semaine.

Contactez votre équipe d’assistance Adobe pour plus d’informations et pour activer cette fonctionnalité.
