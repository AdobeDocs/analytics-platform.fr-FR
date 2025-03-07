---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 22d3e7b8-4a4d-48a8-a98d-5172a9876286
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '1629'
ht-degree: 94%

---

# Créez et configurez une connexion à utiliser avec Customer Journey Analytics. {#upgrade-create-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-connection"
>title="Créer une connexion dans Customer Journey Analytics"
>abstract="Une connexion permet de traduire les données d’Adobe Experience Platform dans un format optimisé pour les rapports Customer Journey Analytics. La création d’une connexion dans Customer Journey Analytics est simple et ne prend que quelques minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

Les informations suivantes expliquent comment créer et configurer une connexion, ainsi que comment ajouter des jeux de données Experience Platform à la connexion que vous créez. Pour plus d’informations sur la création et la configuration d’une connexion, voir [Créer ou modifier une connexion](/help/connections/create-connection.md).

## Créer et configurer la connexion {#create-connection}

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Connexions]**.
1. Sélectionnez **[!UICONTROL Créer une connexion]**.

   ![Paramètres de connexion sans titre.](assets/create-conn1.png)

1. Configurez les paramètres de connexion.

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Nom de la connexion]** | Saisissez un nom unique pour la connexion. |
   | **[!UICONTROL Description de la connexion]** | Décrivez l’objectif de cette connexion. |
   | **[!UICONTROL Sandbox]** | Dans Experience Platform, choisissez une sandbox qui contient le ou les jeux de données auxquels vous voulez créer une connexion.<p>Adobe Experience Platform fournit des [sandbox](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) qui divisent une instance de plateforme unique en environnements virtuels distincts pour favoriser le développement et l’évolution d’applications d’expérience digitale. Vous pouvez considérer les sandbox comme des « silos de données » contenant des jeux de données. Les sandbox permettent de contrôler l’accès aux jeux de données.<p>Une fois que vous avez sélectionné la sandbox, le rail de gauche affiche tous les jeux de données de cette sandbox que vous pouvez extraire. |
   | **[!UICONTROL Activer la fenêtre dynamique de conservation des données]** | Si vous cochez cette case, elle vous permet de définir la conservation des données Customer Journey Analytics sous la forme d’une fenêtre dynamique en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion.<p>La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Cependant, si votre connexion inclut un profil ou des jeux de données de recherche (en plus d’un ou plusieurs jeux de données d’événement), ces données sont conservées pendant la même période.<p> Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.<p>Si vous laissez la valeur par défaut (non cochée), le paramètre de conservation des données d’Adobe Experience Platform remplace la période de conservation. Si vous avez 25 mois de données dans Experience Platform, Customer Journey Analytics obtient 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, Customer Journey Analytics conserve les 15 mois restants. |
   | **[!UICONTROL Ajouter des jeux de données]** (voir ci-dessous) | Ajoutez des jeux de données si aucun jeu de données n’apparaît dans votre liste de jeux de données. |
   | **[!UICONTROL Nom du jeu de données]** | Sélectionnez un ou plusieurs jeux de données à extraire dans Customer Journey Analytics et choisissez **[!UICONTROL Ajouter]**.<p>(Si vous avez le choix entre de nombreux jeux de données, vous pouvez les rechercher à l’aide de la barre de recherche située au-dessus de la liste des jeux de données.) |
   | **[!UICONTROL Dernière mise à jour]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. « S/O » signifie que ce jeu de données ne contient aucune donnée. |
   | **[!UICONTROL Nombre d’enregistrements]** | Total des enregistrements du mois précédent pour le jeu de données dans Experience Platform. |
   | **[!UICONTROL Schéma]** | Le [schéma](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition) à partir duquel le jeu de données a été créé dans Adobe Experience Platform. |
   | **[!UICONTROL Type de jeu de données]** | Pour chaque jeu de données que vous avez ajouté à cette connexion, Customer Journey Analytics définit automatiquement le type de jeu de données en fonction des données qui y sont entrées. Il existe trois types de jeux de données différents : les données Événement, les données Profil et les données de Recherche. Consultez le tableau ci-dessous pour obtenir une explication des types de jeux de données. |
   | **[!UICONTROL Granularité]** | Granularité des données du jeu de données, applicable uniquement aux jeux de données de résumé. |
   | **[!UICONTROL Type de source de données]** | Type de source de données du jeu de données. Non applicable pour les jeux de données de résumé. |
   | **[!UICONTROL ID de personne]** | Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>IMPORTANT : si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Consultez [cette vidéo](https://www.youtube.com/watch?v=G_ttmGl_LRU) sur la façon de définir une identité dans Experience Platform. |
   | **[!UICONTROL Clé]** | Pour les jeux de données de recherche uniquement (tels que _id). |
   | **[!UICONTROL Clé correspondante]** | Pour les jeux de données de recherche uniquement (tels que _id). |
   | **[!UICONTROL Importer de nouvelles données]** | Définissez cette option sur Activé ou Désactivé. |
   | **[!UICONTROL Renvoyer les données]** | Vous pouvez demander de renvoyer les données dans un jeu de données. Vous pouvez, par exemple, demander le renvoi des 7 derniers jours de données. Configurez correctement le jeu de données et testez votre connexion. Si tout semble correct, vous pouvez renvoyer facilement toutes les données restantes.<p>En outre, vous pouvez activer l’import de nouvelles données par jeu de données. |
   | **[!UICONTROL Statut de renvoi]** | Ce statut indique si des données de renvoi sont en cours de traitement. |

   {style="table-layout:auto"}

## Ajouter et configurer des jeux de données {#add-dataset}

Vous pouvez ajouter un jeu de données Experience Platform lors de la création d’une connexion.

1. Dans la boîte de dialogue Paramètres de connexion, cliquez sur **[!UICONTROL Ajouter des jeux de données]**.

1. À l’étape [!UICONTROL Sélectionner les jeux de données], une liste des jeux de données Experience Platform s’affiche.

   ![Sélection de jeux de données](assets/select-datasets.png)

   Pour chaque jeu de données, la liste affiche les éléments suivants :

   | Colonne | Description |
   |---|---|
   | Jeu de données  | Nom du jeu de données. Sélectionnez le nom pour vous diriger vers le jeu de données dans Experience Platform. Sélectionnez ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) pour afficher une fenêtre contextuelle contenant plus de détails sur le jeu de données. Vous pouvez sélectionner **[!UICONTROL Modifier dans Platform]** pour modifier le jeu de données directement dans Experience Platform. |
   | Type de jeu de données | Type de jeu de données : Événement, Profil, Recherche ou Résumé. |
   | Nombre d’enregistrements | Total des enregistrements du mois précédent pour le jeu de données dans Experience Platform. |
   | Schéma | Schéma du jeu de données. Sélectionnez le nom pour vous diriger vers le schéma dans Experience Platform. |
   | Dernier lot | État du dernier lot ingéré dans Experience Platform. Voir [États des lots](https://experienceleague.adobe.com/fr/docs/experience-platform/ingestion/batch/troubleshooting#batch-states) pour plus d’informations. |
   | Identifiant du jeu de données | ID du jeu de données. |
   | Dernière mise à jour | Dernier horodatage mis à jour du jeu de données. |


1. Sélectionnez un ou plusieurs jeux de données, puis cliquez sur **[!UICONTROL Suivant]**. Au moins un jeu de données d’événement doit faire partie de la connexion.
   * Pour modifier les colonnes affichées de la liste des jeux de données, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) et sélectionnez les colonnes à afficher dans la boîte de dialogue [!UICONTROL Personnaliser le tableau].
   * Pour rechercher un jeu de données spécifique, utilisez le champ de recherche ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Pour basculer entre l’affichage ou le masquage des jeux de données sélectionnés, sélectionnez ![Sélectionner](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg), **[!UICONTROL Masquer la sélection]** ou **[!UICONTROL Afficher la sélection]**.
   * Pour supprimer un jeu de données de la liste des jeux de données sélectionnés, utilisez ![Fermer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Pour supprimer tous les jeux de données sélectionnés, sélectionnez **[!UICONTROL Effacer tout]**.




1. Configurez maintenant les jeux de données un par un.

   ![Configurer les jeux de données](assets/add-dataset.png)

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL ID de personne]** | Disponible uniquement pour les jeux de données d’événement et de profil. Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>Si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Voir [Définir des champs d’identité dans l’interface utilisateur](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/identity) pour plus d’informations. <p>La valeur de l’ID de personne sélectionné est considérée comme sensible à la casse. Par exemple : `abc123` et `ABC123` sont deux valeurs différentes. |
   | **[!UICONTROL Date et heure]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. |
   | **[!UICONTROL Clé]** | Disponible uniquement pour les jeux de données de recherche. Clé à utiliser pour un jeu de données de recherche. |
   | **[!UICONTROL Clé correspondante]** | Disponible uniquement pour les jeux de données de recherche. Clé correspondante à joindre à l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas ajouté ni configuré de jeu de données d’événement. |
   | **[!UICONTROL Fuseau horaire]** | Disponible uniquement pour les données de résumé. Sélectionnez le fuseau horaire approprié pour les données de résumé de série temporelle. |
   | **[!UICONTROL Type de source de données]** | Sélectionnez un type de source de données. <br/>Les types de sources de données incluent les éléments suivants : <ul><li>[!UICONTROL Données web]</li><li>[!UICONTROL Données d’application mobile]</li><li>[!UICONTROL Données de point de vente]</li><li>[!UICONTROL Données CRM]</li><li>[!UICONTROL Données de l’enquête]</li><li>[!UICONTROL Données du centre d’appels]</li><li>[!UICONTROL Données du produit]</li><li> [!UICONTROL Données des comptes]</li><li> [!UICONTROL Données de transaction]</li><li>[!UICONTROL Données de commentaires client]</li><li> [!UICONTROL Autre]</li></ul>Ce champ est utilisé pour interroger les types de sources de données en cours d’utilisation. |
   | **[!UICONTROL Importer de nouvelles données]** | Activez cette option si vous souhaitez établir une connexion continue. Avec une connexion continue, les nouveaux lots de données ajoutés aux jeux de données sont automatiquement disponibles dans Workspace. |
   | **[!UICONTROL Renvoi du jeu de données]** | Activez **[!UICONTROL Renvoyer toutes les données existantes]** pour vous assurer que toutes les données existantes sont renvoyées.<br/><br/>Sélectionnez **[!UICONTROL Renvoi de la demande]** pour renvoyer des données historiques pour une période spécifique. Vous pouvez définir jusqu’à 10 périodes de renvoi de jeux de données.<ol><li>Définissez la période en saisissant les données de début et de fin ou en sélectionnant des dates à l’aide du ![Calendrier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).</li><li>Sélectionnez **[!UICONTROL Renvoi de la file dʼattente]** pour ajouter le renvoi à la liste, ou bien **[!UICONTROL Annuler]** pour annuler.</li></ol>Pour chaque entrée, sélectionnez ![Modifier](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) pour modifier la période, ou sélectionnez ![Supprimer](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) pour supprimer l’entrée.<br/><br/>À propos des renvois :<ul><li>Vous pouvez renvoyer chaque jeu de données individuellement.</li><li>Vous donnez la priorité aux nouvelles données ajoutées à un jeu de données dans la connexion, de sorte que ces nouvelles données ont la latence la plus faible.</li><li>Les données de renvoi (historiques) sont importées plus lentement. La quantité de données historiques influence la latence.</li><li>Le connecteur source Analytics importe jusquʼà 13 mois de données pour les sandbox de production, et ce quelle que soit leur taille. Le renvoi dans les sanbox hors production est limité à 3 mois.</li></ul> |
   | **[!UICONTROL Transformer le jeu de données]** | Pour des jeux de données de recherche B2B spécifiques, vous pouvez activer la transformation d’un jeu de données pour des scénarios de création de rapports basés sur la personne B2B appropriés. |
   | **[!UICONTROL Statut de renvoi]** | Les indicateurs de statut possibles sont les suivants :<ul><li>Réussite</li><li>Traitement de X renvoi(s)</li><li>Off</li></ul> |
   | **[!UICONTROL Identifiant du jeu de données]** | Cet identifiant est généré automatiquement. |
   | **[!UICONTROL Description]** | Description donnée à ce jeu de données lors de sa création. |
   | **[!UICONTROL Taille du jeu de données]** | La taille du jeu de données. |
   | **[!UICONTROL Schéma]** | Le schéma à partir duquel le jeu de données a été créé dans Adobe Experience Platform. |
   | **[!UICONTROL Jeu de données]** | Nom du jeu de données. |
   | **[!UICONTROL Aperçu : *nom du jeu de données *]** | Permet d’obtenir un aperçu du jeu de données avec les colonnes Date, mon ID et Identifiant. |
   | **[!UICONTROL Supprimer]** | Vous pouvez supprimer le jeu de données et modifier l’ID de personne sans supprimer l’ensemble de la connexion. Cette suppression permet de réduire les coûts liés à l’ingestion des données et le processus laborieux de recréation de l’ensemble de la connexion et des vues de données associées. |

   {style="table-layout:auto"}

{{upgrade-final-step}}
