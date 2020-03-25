---
title: Création d’une connexion
description: Décrit comment créer une connexion à un jeu de données de plateforme dans les analyses de parcours du client.
translation-type: tm+mt
source-git-commit: 41029fb428308a247df65072af4e419a90098a15

---


# Création d’une connexion

Une connexion vous permet d’intégrer des jeux de données d’Adobe Experience Platform dans Workspace. Pour générer des rapports sur les jeux de données de la plateforme, vous devez d’abord établir une connexion entre les jeux de données dans la plateforme et Workspace.

Cliquez [ici](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) pour une présentation vidéo.

>[!IMPORTANT] Vous pouvez combiner plusieurs jeux de données de plateformes en une seule connexion.

1. Rendez-vous sur [https://analytics.adobe.com](https://analytics.adobe.com).

1. Cliquez sur l’ **[!UICONTROL Connections]** onglet.

1. Cliquez sur **[!UICONTROL Create new connection]** en haut à droite.

![Établir une connexion](assets/create-connection.png)

1. Le rail de gauche affiche tous les jeux de données de Plateforme à partir desquels vous pouvez extraire. Sélectionnez un ou plusieurs jeux de données à extraire dans les analyses de parcours du client, puis cliquez sur **[!UICONTROL Add]**. (Si vous avez le choix entre de nombreux jeux de données, vous pouvez en rechercher un ou plusieurs dans la barre de recherche située au-dessus du  des jeux de données.)

1. Ensuite, pour chaque jeu de données que vous avez ajouté à cette connexion, l’analyse du parcours du client définit automatiquement le type de jeu de données en fonction des données qui y arrivent. Il existe trois types de jeux de données différents : Données , données  et données de recherche.

   | Type de jeu de données | Description | Horodatage | Schéma | ID de personne |
   |---|---|---|---|---|
   | Événement | Données qui représentent des  dans le temps (par exemple, visites Web, interactions, transactions, données POS, données de , données d’impression, etc.). Il s’agit généralement de données de parcours de navigation, avec un ID de client ou un ID de cookie, ainsi qu’un horodatage. Avec les données de , nous vous permettons d&#39;utiliser n&#39;importe quel ID. | Sera défini sur Horodatage. | Le de plateformes  que ce type de jeu de données est basé. | S.O. |
   | Recherche | Analogique avec un fichier de classifications. Ces données sont utilisées pour rechercher des valeurs ou des clés trouvées dans vos données de  ou de. Vous pouvez, par exemple, télécharger des données de recherche qui mappent des ID numériques dans vos données de  aux noms de produits. | S.O. | Le de plateformes  que ce type de jeu de données est basé. | S.O. |
   | Profil | Analogique aux attributs du client - pour les attributs non modifiables et non temporels. Données appliquées à vos, utilisateurs ou clients dans les données  du. Vous permet, par exemple, de transférer des données CRM sur vos clients. | S.O. | Le de plateformes  que ce type de jeu de données est basé. | Vous pouvez sélectionner l’ID de personne à inclure. Chaque jeu de données défini dans Adobe Experience Platform comporte son propre jeu d’un ou de plusieurs ID de personne définis, tels que l’ID de cookie, l’ID avec titrage, l’ID utilisateur, le code de suivi, etc.<br>![Personne](assets/person-id.png)**IDNote **: Si vous créez une connexion qui inclut des jeux de données avec des ID différents, le  le reflétera. Pour vraiment fusionner des jeux de données, vous devez utiliser le même ID de personne. |

1. Cliquez sur **[!UICONTROL Next]**.

1. Dans la boîte de dialogue Créer une connexion, définissez les paramètres suivants :

   | Champ | Description |
   |---|---|
   | Nom | Attribuez un nom explicite à la connexion. La connexion ne peut pas être enregistrée sans nom. |
   | Description | Ajouter plus de détails pour distinguer cette connexion des autres. |
   | Taille | Taille collective des jeux de données dans la connexion aux données. |
   | Jeux de données | Jeu de données inclus dans cette connexion. |
   | Transmission de données en continu | Pour commencer la diffusion en flux continu des données pour cette connexion, activez la diffusion en flux continu des données. Lorsque la diffusion en flux continu des données est activée pour cette connexion, votre compte est facturé pour la quantité de données que cette connexion est en flux continu. (Notez que vous pouvez également activer la diffusion en continu des données dans le Gestionnaire de connexions.) |

1. Cliquez sur **[!UICONTROL Save]**. Lorsque vous enregistrez cette connexion, deux choses se produisent :

   * Vous récupérez toutes les données historiques de la plateforme pour tous les jeux de données qui se trouvent dans cette connexion.
   * Si vous avez activé la diffusion en flux continu, vous établissez une connexion permanente, de sorte que toutes les nouvelles données qui sont ajoutées aux jeux de données dans cette connexion s’enchaînent automatiquement dans Workspace.

L’étape suivante du processus consiste à [créer un](/help/data-views/create-dataview.md)de données.
