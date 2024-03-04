---
title: Créer ou modifier une connexion
description: Décrit comment créer ou modifier une connexion à un jeu de données Experience Platform dans Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 2be283e0abd32229be1921b106d166f47fb410a8
workflow-type: tm+mt
source-wordcount: '2763'
ht-degree: 98%

---

# Créer ou modifier une connexion

L’expérience de workflow de création et de modification de connexion apporte tous les paramètres de configuration de jeu de données et de connexion au centre de l’écran avec le workflow d’assistance. Elle fournit une expérience détaillée de sélection, de configuration et de révision de jeux de données avec des informations essentielles telles que le type, la taille, le schéma, l’identifiant du jeu de données, le statut du lot, le statut de renvoi, les ID de personne, etc., afin de réduire le risque d’une mauvaise configuration de connexion. Voici une vue d’ensemble des nouvelles fonctionnalités :

* Vous pouvez activer une période de conservation des données variable lors de la création de la connexion.
* Vous pouvez ajouter et supprimer des jeux de données d’une connexion. (Supprimer un jeu de données le supprime de la connexion et affecte toutes les vues de données associées et les projets Analysis Workspace sous-jacents.)
* Vous pouvez activer et demander des données de renvoi par jeu de données.
* Vous pouvez modifier des jeux de données, par exemple pour demander un autre renvoi.
* Vous pouvez importer des données existantes par jeu de données.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Conditions préalables

Vous devez disposer de la variable **Sélectionner** afin d’ajouter un nombre illimité de jeux de données d’événement à une connexion. La variable **Foundation** Le module est limité à un jeu de données d’événement. Vous pouvez ajouter un nombre illimité de jeux de données de profil ou de recherche à une connexion. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package de Customer Journey Analytics vous disposez.

## Créer et configurer la connexion {#create-connection}

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Connexions]**.
1. Cliquez sur **[!UICONTROL Créer une connexion]**.

   ![Paramètres de connexion sans titre.](assets/create-conn1.png)

1. Configurez les paramètres de connexion.

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Nom de la connexion]** | Saisissez un nom unique pour la connexion. |
   | **[!UICONTROL Description de la connexion]** | Décrivez l’objectif de cette connexion. |
   | **[!UICONTROL Sandbox]** | Dans Experience Platform, choisissez une sandbox qui contient le ou les jeux de données auxquels vous voulez créer une connexion.<p>Adobe Experience Platform fournit des [sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=fr) qui divisent une instance de plateforme unique en environnements virtuels distincts pour favoriser le développement et l’évolution d’applications d’expérience digitale. Vous pouvez considérer les sandbox comme des « silos de données » contenant des jeux de données. Les sandbox permettent de contrôler l’accès aux jeux de données.<p>Une fois que vous avez sélectionné la sandbox, le rail de gauche affiche tous les jeux de données de cette sandbox que vous pouvez extraire. |
   | **[!UICONTROL Activer la fenêtre dynamique de conservation des données]** | Si vous cochez cette case, elle vous permet de définir la conservation des données Customer Journey Analytics sous la forme d’une fenêtre dynamique en mois (1 mois, 3 mois, 6 mois, etc.), au niveau de la connexion.<p>La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de fenêtre dynamique de conservation des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable. Cependant, si votre connexion inclut un profil ou des jeux de données de recherche (en plus d’un ou plusieurs jeux de données d’événement), ces données sont conservées pendant la même période.<p> Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.<p>Si vous laissez la valeur par défaut (non cochée), la période de conservation est remplacée par le paramètre de conservation des données d’Adobe Experience Platform. Si vous avez 25 mois de données dans Experience Platform, Customer Journey Analytics obtient 25 mois de données par renvoi. Si vous avez supprimé 10 de ces mois dans Platform, Customer Journey Analytics conserve les 15 mois restants. |
   | **[!UICONTROL Ajouter des jeux de données]** (voir ci-dessous) | Ajoutez des jeux de données si aucun jeu de données n’apparaît dans votre liste de jeux de données. |
   | **[!UICONTROL Nom du jeu de données]** | Sélectionnez un ou plusieurs jeux de données à extraire dans Customer Journey Analytics et cliquez sur **[!UICONTROL Ajouter]**.<p>(Si vous avez le choix entre de nombreux jeux de données, vous pouvez les rechercher à l’aide de la barre de recherche située au-dessus de la liste des jeux de données.) |
   | **[!UICONTROL Dernière mise à jour]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. « S/O » signifie que ce jeu de données ne contient aucune donnée. |
   | **[!UICONTROL Schéma]** | Le [schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=fr) à partir duquel le jeu de données a été créé dans Adobe Experience Platform. |
   | **[!UICONTROL Type de jeu de données]** | Pour chaque jeu de données que vous avez ajouté à cette connexion, Customer Journey Analytics définit automatiquement le type de jeu de données en fonction des données qui y sont entrées. Il existe trois types de jeux de données différents : les données Événement, les données Profil et les données de Recherche. Consultez le tableau ci-dessous pour obtenir une explication des types de jeux de données. |
   | **[!UICONTROL ID de personne]** | Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>IMPORTANT : si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Consultez [cette vidéo](https://www.youtube.com/watch?v=G_ttmGl_LRU) sur la façon de définir une identité dans Experience Platform. |
   | **[!UICONTROL Clé]** | Pour les jeux de données de recherche uniquement (tels que _id). |
   | **[!UICONTROL Clé correspondante]** | Pour les jeux de données de recherche uniquement (tels que _id). |
   | **[!UICONTROL Importer de nouvelles données]** | Définissez cette option sur Activé ou Désactivé. |
   | **[!UICONTROL Renvoyer les données]** | Vous pouvez demander de renvoyer les données dans un jeu de données en fonction des horodatages d’événement. Par exemple, vous pouvez demander de renvoyer l’équivalent de 7 jours de données, configurer l’ID de personne approprié et tester votre connexion pour une configuration correcte. Si tout semble correct, vous pouvez renvoyer facilement toutes les données restantes.<p>En outre, vous pouvez activer l’importation de nouvelles données par jeu de données. Par exemple, vous pouvez activer l’importation de nouvelles données pour les données de recherche uniquement. |
   | **[!UICONTROL Statut de renvoi]** | Indique si des données de renvoi sont en cours de traitement. |

   {style="table-layout:auto"}

## Ajouter et configurer des jeux de données {#add-dataset}

Le nouveau workflow permet d’ajouter un jeu de données Experience Platform lors de la création d’une connexion.

1. Dans la boîte de dialogue Paramètres de connexion, cliquez sur **[!UICONTROL Ajouter des jeux de données]**.

2. À l’étape [!UICONTROL Sélectionner des jeux de données], sélectionnez un ou plusieurs jeux de données, puis sélectionnez **[!UICONTROL Suivant]**. Au moins un jeu de données d’événement doit faire partie de la connexion.
   * Pour modifier les colonnes affichées de la liste des jeux de données, sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) et sélectionnez les colonnes à afficher dans la boîte de dialogue [!UICONTROL Personnaliser le tableau].
   * Pour rechercher un jeu de données spécifique, utilisez le champ de recherche ![Rechercher](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).
   * Pour basculer entre l’affichage ou le masquage des jeux de données sélectionnés, sélectionnez ![Sélectionner](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg), **[!UICONTROL Masquer la sélection]** ou **[!UICONTROL Afficher la sélection]**.
   * Pour supprimer un jeu de données de la liste des jeux de données sélectionnés, utilisez ![Fermer](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg). Pour supprimer tous les jeux de données sélectionnés, sélectionnez **[!UICONTROL Effacer tout]**.

   ![Sélection de jeux de données](assets/select-datasets.png)

3. Maintenant, configurez les jeux de données un par un.

   ![Configurer les jeux de données](assets/add-dataset.png)

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL ID de personne]** | Disponible uniquement pour les jeux de données d’événement et de profil. Sélectionnez un ID de personne dans la liste déroulante des identités disponibles. Ces identités ont été définies dans le schéma du jeu de données d’Experience Platform. Pour plus d’informations sur l’utilisation de la carte des identités en tant qu’ID de personne, reportez-vous à la section ci-dessous.<p>Si aucun ID de personne n’est disponible, cela signifie qu’un ou plusieurs ID de personne n’ont pas été définis dans le schéma. Consultez cette vidéo sur la façon de définir une identité dans Experience Platform. |
   | **[!UICONTROL Horodatage]** | Pour les jeux de données d’événements uniquement, ce paramètre est automatiquement défini sur le champ d’horodatage par défaut des schémas basés sur un événement dans Experience Platform. |
   | **[!UICONTROL Clé]** | Disponible uniquement pour les jeux de données de recherche. Clé à utiliser pour un jeu de données de recherche. |
   | **[!UICONTROL Clé correspondante]** | Disponible uniquement pour les jeux de données de recherche. Clé correspondante à joindre à l’un des jeux de données d’événement. Si cette liste est vide, vous n’avez probablement pas ajouté ni configuré de jeu de données d’événement. |
   | **[!UICONTROL Type de source de données]** | Sélectionnez un type de source de données. <br/>Les types de sources de données incluent les éléments suivants : <ul><li>[!UICONTROL Données web]</li><li>[!UICONTROL Données d’application mobile]</li><li>[!UICONTROL Données de point de vente]</li><li>[!UICONTROL Données CRM]</li><li>[!UICONTROL Données de l’enquête]</li><li>[!UICONTROL Données du centre d’appels]</li><li>[!UICONTROL Données du produit]</li><li> [!UICONTROL Données des comptes]</li><li> [!UICONTROL Données de transaction]</li><li>[!UICONTROL Données de commentaires client]</li><li> [!UICONTROL Autre]</li></ul>Ce champ est utilisé pour interroger les types de sources de données en cours d’utilisation. |
   | **[!UICONTROL Importer de nouvelles données]** | Sélectionnez cette option si vous souhaitez établir une connexion en cours, de sorte que tous les nouveaux lots de données qui sont ajoutés aux jeux de données dans cette connexion soient automatiquement transférés dans Espace de travail. Peut être défini sur [!UICONTROL Activé] ou [!UICONTROL Désactivé]. |
   | **[!UICONTROL Renvoi du jeu de données]** | Cliquez sur **[!UICONTROL Demander un renvoi]** pour renvoyer des données historiques.<ul><li>Vous pouvez renvoyer chaque jeu de données individuellement.</li><li>Vous donnez la priorité aux nouvelles données ajoutées à un jeu de données dans la connexion, de sorte que ces nouvelles données ont la latence la plus faible.</li><li>Les données de renvoi (historiques) sont importées plus lentement. La latence est influencée par la quantité de données historiques dont vous disposez.</li><li>Le connecteur source Analytics importe jusquʼà 13 mois de données pour les sandbox de production, et ce quelle que soit leur taille. Le renvoi dans les sanbox hors production est limité à 3 mois.</li></ul> |
   | **[!UICONTROL Statut de renvoi]** | Les indicateurs de statut possibles sont les suivants :<ul><li>Réussite</li><li>Traitement de X renvoi(s)</li><li>Off</li></ul> |
   | **[!UICONTROL Identifiant du jeu de données]** | Cet identifiant est généré automatiquement. |
   | **[!UICONTROL Description]** | Description donnée à ce jeu de données lors de sa création. |
   | **[!UICONTROL Taille du jeu de données]** | La taille du jeu de données. |
   | **[!UICONTROL Schéma]** | Le schéma à partir duquel le jeu de données a été créé dans Adobe Experience Platform. |
   | **[!UICONTROL Jeu de données]** | Nom du jeu de données. |
   | **[!UICONTROL Aperçu : *nom du jeu de données *]** | Permet d’obtenir un aperçu du jeu de données avec les colonnes Date, mon ID et Identifiant. |
   | **[!UICONTROL Supprimer]** | Vous pouvez supprimer le jeu de données et modifier l’ID de personne sans supprimer l’ensemble de la connexion. Cette suppression permet de réduire les coûts liés à l’ingestion des données et le processus laborieux de recréation de l’ensemble de la connexion et des vues de données associées. |

   {style="table-layout:auto"}

## Aperçu de la connexion {#preview}

Pour prévisualiser la connexion que vous avez créée, cliquez sur **[!UICONTROL Aperçu de la connexion]** dans la boîte de dialogue Paramètres de connexion.

![Aperçu de la connexion](assets/create-conn4.png)

Cet aperçu contient certaines colonnes répertoriant la configuration de la connexion. Les types de colonnes affichés dépendent de vos jeux de données individuels.

## Types de jeux de données {#dataset-types}

Pour chaque jeu de données que vous avez ajouté à cette connexion, [!UICONTROL Customer Journey Analytics] définit automatiquement le type de jeu de données en fonction des données qui y sont entrées.

>[!IMPORTANT]
>
>Vous devez ajouter au moins un jeu de données d’événement dans le cadre d’une connexion.

Il existe trois types de jeux de données différents : les données [!UICONTROL Événement], les données [!UICONTROL Profil] et les données de [!UICONTROL Recherche].

| Type de jeu de données | Description | Horodatage | Schéma | ID de personne |
|---|---|---|---|---|
| **[!UICONTROL Événement]** | Données qui représentent des événements dans le temps (par exemple, visites Web, interactions, transactions, données de point de vente, données d’enquête, données d’impression, etc). Par exemple, il peut s’agir de données de flux de clics typiques, avec un ID de client ou un ID de cookie et un horodatage. Avec les données d’événement, vous disposez d’une flexibilité quant à l’ID utilisé comme ID de personne. | Est automatiquement défini sur le champ d’horodatage par défaut à partir des schémas basés sur un événement dans [!UICONTROL Experience Platform]. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Série temporelle ». Par exemple, « Événement d’expérience XDM » ou « Événement de décision XDM ». | Vous pouvez sélectionner l’ID de personne à inclure. Chaque schéma du jeu de données défini dans Experience Platform peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un espace de noms d’identité. N’importe laquelle de ces identité peut être utilisée comme ID de personne. Par exemple, l’ID de cookie, l’ID groupé, l’ID utilisateur, le code de suivi, etc. |
| **[!UICONTROL Rechercher]** | Vous pouvez désormais ajouter des jeux de données en tant que recherches de champs dans tous les types de jeux de données : Profil, Recherche et Événement (ce dernier a toujours été pris en charge). Cette fonctionnalité supplémentaire accroît la capacité de CJA à prendre en charge des modèles de données complexes, y compris la plateforme de données clients B2B. Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données d’événement, de profil ou de recherche. Vous pouvez ajouter jusqu’à deux niveaux de recherche. (Notez que [Champs dérivés](/help/data-views/derived-fields/derived-fields.md) ne peut pas être utilisé comme clés correspondantes pour les recherches dans les connexions.) Vous pouvez, par exemple, charger des données de recherche qui font correspondre les ID numériques de vos données d’événement aux noms de produits. Voir l’exemple [Cas d’utilisation B2B](/help/use-cases/b2b/b2b.md). | S.O. | Tout schéma intégré ou personnalisé basé sur une classe XDM avec le comportement « Enregistrement (Record) », à l’exception de la classe « Profil XDM individuel ». | S.O. |
| **[!UICONTROL Profil]** | Données appliquées à vos personnes, utilisateurs/utilisatrices ou clients/clientes dans les données [!UICONTROL Événement]. Vous permet, par exemple, de charger des données CRM à propos de vos clients. | S.O. | Tout schéma intégré ou personnalisé basé sur la classe « Profil XDM individuel ». | Vous pouvez sélectionner l’ID de personne à inclure. Chaque jeu de données défini dans [!DNL Experience Platform] a son propre jeu d’un ou plusieurs ID de personne définis, tels que l’ID de cookie, l’ID groupé, l’ID d’utilisateur, le code de suivi, etc.<br>![ID de personne ](assets/person-id.png)**Remarque** : si vous créez une connexion qui comprend des jeux de données avec des ID différents, les rapports le reflèteront. Pour véritablement fusionner des jeux de données, vous devez utiliser le même ID de personne. |

{style="table-layout:auto"}

## Utilisation des champs numériques comme clés et valeurs de recherche {#numeric}

Cette fonctionnalité de recherche est utile si vous souhaitez ajouter un champ numérique, comme un coût ou une marge, à un champ clé reposant sur une chaîne. Les valeurs numériques feront ainsi partie des recherches sous forme de clés ou de valeurs. Dans votre schéma de recherche, il se peut que des valeurs numériques soient liées, par exemple, à vos noms de produit, au COGS, à vos coûts de campagne marketing ou à vos marges. Voici un exemple de schéma de recherche dans Adobe Experience Platform :

![Schéma de recherche](assets/schema.png)

Vous prenez désormais en charge l’inclusion de ces valeurs sous forme de mesures ou de dimensions dans la création de rapports Customer Journey Analytics. Lorsque vous configurez votre connexion et extrayez des jeux de données de recherche, vous pouvez modifier les jeux de données de manière à sélectionner la [!UICONTROL Clé] et la [!UICONTROL Clé correspondante] :

![Edit-dataset](assets/lookup-dataset.png)

Lorsque vous configurez une vue de données reposant sur cette connexion, vous ajoutez les valeurs numériques en tant que composants de la vue de données. Tout projet basé sur cette vue de données peut alors créer des rapports sur ces valeurs numériques.

## Utiliser la carte des identités comme ID de personne {#id-map}

Customer Journey Analytics prend en charge la possibilité d’utiliser la carte des identités pour son ID de personne. La carte des identités est une structure de données de carte qui vous permet de télécharger des paires clé -> valeur. Les clés sont des espaces de noms d’identité et la valeur est une structure qui contient la valeur de l’identité. La carte des identités existe sur chaque ligne/événement téléchargé et est renseignée pour chaque ligne en conséquence.

La carte des identités est disponible pour tout jeu de données qui utilise un schéma basé sur la classe [XDM ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr). Lorsque vous sélectionnez un jeu de données à inclure dans une connexion Customer Journey Analytics, vous avez la possibilité de sélectionner un champ comme ID principal ou la carte des identités :

![](assets/idmap1.png)

Si vous sélectionnez Carte des identités, vous disposez de deux options de configuration supplémentaires :

| Option | Description |
|---|---|
| **[!UICONTROL Utiliser l’espace de noms des ID principaux]** | Cette option indique à Customer Journey Analytics, par ligne, de trouver l’identité dans la carte des identités signalée par un attribut primary=true et de l’utiliser comme ID de personne pour cette ligne. Cette identité est la clé primaire utilisée dans Experience Platform pour le partitionnement. Cette identité est également le candidat idéal pour l’utilisation en tant qu’ID de personne Customer Journey Analytics (selon la manière dont le jeu de données est configuré dans une connexion Customer Journey Analytics). |
| **[!UICONTROL Espace de noms]** | (Cette option n’est disponible que si vous n’utilisez pas l’espace de noms des ID principaux.) Les espaces de noms d’identité sont des composants du [ Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=fr) qui servent d’indicateurs du contexte auquel une identité se rapporte. Si vous spécifiez un espace de noms, Customer Journey Analytics recherche la carte des identités pour cette clé d’espace de noms dans chaque ligne et utilise l’identité sous cet espace de noms comme ID de personne pour cette ligne. Étant donné que Customer Journey Analytics ne peut pas effectuer d’analyse complète des jeux de données de toutes les lignes pour déterminer les espaces de noms présents, tous les espaces de noms possibles sont affichés dans la liste déroulante. Vous devez savoir quels espaces de noms sont spécifiés dans les données ; ces derniers ne sont pas détectés automatiquement. |

{style="table-layout:auto"}

### Cas extrême de la carte des identités {#id-map-edge}

Ce tableau présente les deux options de configuration lorsque des cas extrêmes sont présents et indique comment ils sont gérés :

| Option | Aucun ID n’est présent dans la carte des identités | Plusieurs ID, dont aucun n’est marqué comme principal | Plusieurs ID sont marqués comme principaux | ID unique, marqué comme principal ou non | Espace de noms non valide avec un ID marqué comme principal |
|---|---|---|---|---|---|
| **[!UICONTROL Utiliser l’espace de noms des ID principaux] coché** | La ligne est supprimée par Customer Journey Analytics. | La ligne est supprimée par Customer Journey Analytics, car aucun ID principal n’est spécifié. | Tous les identifiants marqués comme principaux, sous tous les espaces de noms, sont extraits dans une liste. Ils sont ensuite triés par ordre alphabétique. Avec ce nouveau tri, le premier espace de noms avec son premier ID est utilisé comme ID de personne. | L’ID unique est utilisé comme ID de personne. | Même si l’espace de noms peut être non valide (il n’est pas présent dans Adobe Experience Platform), Customer Journey Analytics utilise l’ID principal sous cet espace de noms comme ID de personne. |
| **[!UICONTROL Espace de noms de carte des identités spécifique] sélectionné** | La ligne est supprimée par Customer Journey Analytics. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. | Tous les identifiants sous l’espace de noms sélectionné sont extraits dans une liste et le premier est utilisé comme ID de personne. (Seul un espace de noms valide peut être sélectionné au moment de la création de la connexion. Il n’est donc pas possible qu’un espace de noms/ID non valide soit utilisé comme ID de personne). |

{style="table-layout:auto"}

## Calculer le nombre moyen dʼévénements quotidiens {#average-number}

Ce calcul est effectué pour chaque jeu de données de la connexion.

1. Accédez aux [services de requête d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) et créez une nouvelle requête.

   La requête ressemblerait à ceci :

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   Dans cet exemple, « analytics_demo_data » est le nom du jeu de données.

2. Pour afficher tous les jeux de données qui existent dans Adobe Experience Platform, exécutez la requête `Show Tables`.
