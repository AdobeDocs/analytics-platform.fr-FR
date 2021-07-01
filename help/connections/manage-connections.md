---
title: Gestion des connexions
description: Décrit comment gérer des connexions à des jeux de données Experience Platform dans Customer Journey Analytics (CJA).
mini-toc-levels: 3
source-git-commit: fb0b35173d7a2b0daa17c34272b2b2b271095f4a
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# Gestion des connexions

Une fois que [les utilisateurs administrateurs ont créé une ou plusieurs connexions](/help/connections/create-connection.md), ils peuvent les gérer dans le Gestionnaire de [!UICONTROL connexions]. La dernière mise à jour de l’expérience de connexion ajoute deux fonctionnalités importantes dans la page Détails de la connexion, décrite plus bas dans cette page :

* Il vous permet de vérifier l’état **des jeux de données de votre connexion et du processus d’ingestion**. Cette vérification de l’état vous permet de savoir quand vos données sont disponibles afin que vous puissiez accéder à Analysis Workspace et lancer l’analyse.

* Il vous permet **d’identifier les incohérences de données** dues à une mauvaise configuration. Vous manque-t-il des lignes ? Si oui, quelles lignes sont manquantes et pourquoi ? Avez-vous mal configuré les connexions et généré des données manquantes dans CJA ?

>[!NOTE]
> Cette fonctionnalité sera disponible en général le 26 juillet 2021.

## Gestionnaire de connexions {#connections-manager}

Le gestionnaire de connexions vous permet d’effectuer les opérations suivantes :

* Affichez en un coup d’oeil toutes vos connexions, y compris le propriétaire, l’environnement de test, ainsi que la date à laquelle elles ont été créées et modifiées.
* Afficher tous les jeux de données dans une connexion
* Vérifiez l’état d’une connexion.
* Supprimer une connexion.
* Renommer une connexion.
* Créer une vue de données à partir d’une connexion.

![Gestion des connexions](assets/conn-manager.png)

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Nom] | Nom convivial de la connexion. Lorsque vous cliquez sur le nom de l’hyperlien, vous accédez à la page Détails de la connexion décrite ci-dessous. |
| Informations sur la connexion | Cliquez sur l’icône d’information en regard du nom de la connexion pour afficher les informations suivantes :![Afficher les informations de connexion](assets/conn-info.png) |
| Modifier une connexion | Cliquez sur les points de suspension (...) en regard du nom de la connexion, puis cliquez sur [!UICONTROL Modifier].![Modifier ](assets/conn-edit-delete.png) la connexionPour plus d’informations, voir &quot;Modifier la connexion&quot; ci-dessous. |
| Supprimer une connexion | Cliquez sur les points de suspension (...) en regard du nom de la connexion, puis cliquez sur [!UICONTROL Supprimer]. Pour plus d’informations, reportez-vous à l’en-tête &quot;Supprimer les connexions&quot; ci-dessous. |
| Créer une vue de données | Cliquez sur les points de suspension (...) en regard du nom de la connexion, puis cliquez sur [!UICONTROL Créer une vue de données]. Cette action crée une vue de données basée sur cette connexion. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Jeux de données] | Les jeux de données qui font partie de la connexion. Vous pouvez cliquer sur l’hyperlien pour afficher tous les jeux de données de la connexion. Cliquer sur un jeu de données ouvre ce jeu de données dans Adobe Experience Platform, dans un nouvel onglet. |
| [!UICONTROL Environnement de test] | [Environnement de test Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) à partir duquel cette connexion dessine ses jeux de données. Cet environnement de test a été sélectionné lors de la première création de la connexion. Il ne peut pas être modifié. |
| [!UICONTROL Propriétaire] | Personne qui a créé la connexion. |
| [!UICONTROL Importer des jeux de données] | Permet d’activer ou de désactiver ce qui était appelé &quot;diffusion de données&quot;. |
| [!UICONTROL Date de création ] | Date à laquelle la connexion a été créée pour la première fois. |
| [!UICONTROL Dernière modification] | Date de la dernière mise à jour de la connexion. |

### Suppression des connexions {#connections-delete}

Seuls les administrateurs sont autorisés à supprimer une connexion. Cette action ne s’affiche pas pour les non-administrateurs.

1. Cliquez sur les points de suspension (...) en regard du nom de la connexion.
1. Cliquez sur [!UICONTROL Supprimer].

Lorsque vous supprimez une connexion dans [!UICONTROL Customer Journey Analytics], un message d’erreur indique que :

* Les vues de données créées à partir de la connexion supprimée ne fonctionnent plus.
* De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.

[En savoir ](/help/getting-started/cja-deletion.md) plus sur les implications de suppression.

### Recherche d’une connexion ou d’un jeu de données

Vous pouvez rechercher des connexions à l’aide de la barre de recherche située en haut, sous le titre [!UICONTROL Connexions].

### Tri des connexions

Vous pouvez trier les connexions en cliquant sur l’en-tête de chaque colonne et en les triant vers le haut ou vers le bas.

## Page Détails de la connexion {#connection-detail}

La nouvelle page Détails des connexions vous donne une vue très détaillée de l’état d’une connexion.

Elle vous offre les possibilités suivantes :

* Vérifiez l’état des jeux de données de votre connexion et du processus d’ingestion.
* Identifiez les problèmes de configuration qui conduisent à des enregistrements ignorés ou supprimés.
* Voir quand les données sont disponibles pour la création de rapports.

Voici les widgets et les paramètres expliqués :

![Afficher le détail de la connexion](assets/conn-details.png)

| Widget/Paramètre | Description |
| --- | --- |
| Jeu de données selector | Permet de sélectionner un ou tous les jeux de données dans la connexion. Vous ne pouvez pas sélectionner plusieurs jeux de données. La valeur par défaut est [!UICONTROL Tous les jeux de données]. |
| Calendrier/plages de dates | La période indique quand vous avez ajouté des données à la connexion. Tous les paramètres prédéfinis de calendrier standard sont inclus. Vous pouvez personnaliser la période, mais aucune période personnalisée ne s’affiche dans la liste déroulante. |
| [!UICONTROL Enregistrements ] disponibles, widget | Représente le nombre total de lignes disponibles pour la création de rapports, **pour l’ensemble de la connexion**. Ce nombre est indépendant des paramètres du calendrier. Cela change si vous sélectionnez un jeu de données à partir du sélecteur de jeux de données ou en sélectionnant un jeu de données dans le tableau. ( Notez qu’une latence de 1 à 2 heures s’affiche pour que les données apparaissent dans les rapports une fois qu’elles sont ajoutées.) |
|  Metricswidget | Résume les enregistrements ajoutés/ignorés/supprimés et le nombre de lots ajoutés, **pour le jeu de données et la période que vous avez sélectionnés**. |
| [!UICONTROL Enregistrements ] addedwidget | Indique le nombre de lignes ajoutées au cours de la période sélectionnée, **pour le jeu de données et la période que vous avez sélectionnés**. Mise à jour toutes les 10 minutes. |
| [!UICONTROL Records ] skippedwidget | Indique le nombre de lignes qui ont été ignorées au cours de la période sélectionnée, **pour le jeu de données et la période que vous avez sélectionnés**. Les raisons pour ignorer les enregistrements sont les suivantes : Horodatages manquants, ID de personne manquant, etc. Mise à jour toutes les 10 minutes. |
| [!UICONTROL Enregistrements ] deletedwidget | Indique le nombre de lignes supprimées au cours de la période sélectionnée, **pour le jeu de données et la période que vous avez sélectionnés**. Quelqu’un peut avoir supprimé un jeu de données dans Experience Platform, par exemple. Mise à jour toutes les 10 minutes. |
| Zone de recherche des jeux de données | Vous pouvez effectuer une recherche par nom de jeu de données ou [!UICONTROL identifiant de jeu de données]. |
| [!UICONTROL Jeux de données] | Affiche les jeux de données qui font partie de la connexion. Vous pouvez cliquer sur l’hyperlien pour afficher tous les jeux de données de la connexion. |
| [!UICONTROL Identifiant du jeu de données] | Cet identifiant est généré automatiquement par Adobe Experience Platform. |
| [!UICONTROL Lots] | Indique le nombre de lots de données ajoutés à ce jeu de données. |
| [!UICONTROL Dernier ajout] | Affiche l’horodatage du dernier lot ajouté à ce jeu de données. |
| [!UICONTROL Type de jeu de données] | Le type de jeu de données pour ce jeu de données peut être [!UICONTROL Evénement], [!UICONTROL Recherche] ou [!UICONTROL Profil]. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| Schéma | Schéma Adobe Experience Platform sur lequel reposent les jeux de données dans cette connexion. |
| **Rail droit au niveau de la connexion** |  |
| [!UICONTROL Actualiser] | Actualisez la connexion pour permettre la prise en compte des enregistrements récemment ajoutés. |
| [!UICONTROL Supprimer] | Supprimez cette connexion. |
| [!UICONTROL Créer une vue de données] | Créez une nouvelle vue de données basée sur cette connexion. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Nom de la connexion] | Affiche le nom convivial de la connexion. |
| [!UICONTROL Description de la connexion] | Affiche une description plus détaillée qui décrit idéalement l’objectif de cette connexion. |
| [!UICONTROL ID de personne] | Affiche une identité qui a été définie dans le schéma du jeu de données de l’Experience Platform. Il s’agit de l’[!UICONTROL ID de personne] que vous avez choisi lors de la création de la connexion. Si vous créez une connexion qui inclut des jeux de données avec des identifiants différents, les rapports le reflèteront. Pour réellement fusionner des jeux de données, vous devez utiliser le même [!UICONTROL ID de personne]. |
| [!UICONTROL Environnement de test] | [Environnement de test Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) à partir duquel cette connexion dessine son ou ses jeux de données. Cet environnement de test a été sélectionné lors de la première création de la connexion. Il ne peut pas être modifié. |
| [!UICONTROL ID de connexion] | Cet identifiant est généré par le système dans Adobe Experience Platform. |
| [!UICONTROL Identifiant de l’organisation IMS] | [ID d’organisation](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en) associé à votre société Experience Cloud configurée. Anciennement appelée &quot;société de connexion&quot;. |
| [!UICONTROL Vues de données utilisant la connexion] | Répertorie toutes les vues de données qui utilisent cette connexion. |
| [!UICONTROL Importer de nouvelles données] | Indique si de nouveaux lots de données doivent ou non être ajoutés aux données historiques (de renvoi). |
| **Rail droit au niveau du jeu de données** |  |
| [!UICONTROL Description du jeu de données] | Décrit les paramètres de chaque jeu de données dans cette connexion. |
| [!UICONTROL Enregistrements disponibles] | Représente le nombre total de lignes ingérées pour ce jeu de données, pour la période particulière sélectionnée dans le calendrier. Une fois ajoutées, les données n’apparaissent pas dans les rapports. (L’exception est que lorsque vous créez une nouvelle connexion, il y aura [latence](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-getting-data-into-customer-parcours-analytics). |
| [!UICONTROL Enregistrements ajoutés] | Nombre de lignes ajoutées au cours de la période sélectionnée. |
| [!UICONTROL Enregistrements ignorés] | Nombre de lignes ignorées lors de l’ingestion au cours de la période sélectionnée. |
| [!UICONTROL Enregistrer les erreurs ignorées] | La raison pour laquelle les enregistrements ont été ignorés est indiquée ici. Ils peuvent inclure des horodatages manquants, un ID de personne manquant, etc. |
| [!UICONTROL Lots ingérés] | Nombre de lots de données ajoutés à ce jeu de données. |
| [!UICONTROL Dernier ajout] | Lorsque le dernier lot a été ajouté. |
| [!UICONTROL Type de jeu de données] | [!UICONTROL Événement], [!UICONTROL Recherche] ou [!UICONTROL Profil]. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL Schéma] | Schéma Adobe Experience Platform sur lequel ce jeu de données est basé. |
| [!UICONTROL Identifiant du jeu de données] | Cet identifiant est généré par le système dans Adobe Experience Platform. |
| [!UICONTROL Renvoyer les données] | Les données de renvoi (historiques) sont suivies dans 3 états : [!UICONTROL Dans la file], [!UICONTROL En cours] (avec le pourcentage de progression indiqué) et [!UICONTROL Complète]. |

### Modifier la connexion

Permet aux administrateurs de modifier la connexion. Sélectionnez une connexion, puis cliquez sur [!UICONTROL Modifier la connexion] pour accéder à cette boîte de dialogue. Vous pouvez effectuer les opérations suivantes :

* Démarrez et arrêtez d’importer de nouvelles données. Ce processus était auparavant connu sous le nom de &quot;diffusion de données&quot;.
* Renommer une connexion.
