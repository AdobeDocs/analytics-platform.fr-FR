---
title: Comment obtenir des données Google Analytics dans Adobe Experience Platform pour analyse en Customer Journey Analytics (CJA)
description: 'Explique comment tirer parti du Customer Journey Analytics (CJA) pour intégrer vos Google Analytics et vos données de base de feu dans Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 58842436ab3388ba10ad0df0b35c78f68b02f0a3
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 2%

---


# Envoi de données Google Analytics dans Adobe Experience Platform

Ce cas d’utilisation se concentre sur la manière d’assimiler vos données Google Analytics en tant que jeu de données dans Adobe Experience Platform. Nous expliquerons comment ingérer des données historiques et vivantes. Une fois cette opération terminée, vous pouvez combiner les deux jeux de données dans le Customer Journey Analytics pour obtenir une vue sur plusieurs périphériques du parcours de votre utilisateur.

Les jeux de données de l&#39;Experience Platform sont composés de deux éléments : un schéma et les enregistrements réels dans le jeu de données. Le schéma (nous l’appelons le modèle de données d’expérience ou XDM pour faire court) est semblable aux colonnes du jeu de données et est semblable au modèle ou aux règles qui décrivent les données elles-mêmes. Au sein de la plate-forme, Adobe fournit deux types de schémas :

* Schémas prêts à l’emploi auxquels vous pouvez associer automatiquement vos données Google Analytics (appelés schéma de Événement d’expérience)
* Schémas personnalisés que vous pouvez créer et associer facilement aux données Google Analytics

L’un des aspects les plus puissants du modèle de données d’Adobe est qu’il vous permet de normaliser toutes vos données d’interaction avec la clientèle en un seul schéma commun, ce qui facilite considérablement la mise en jonction des données dans CJA.

## Conditions préalables

Pour accomplir ces tâches, vous devez disposer des autorisations et des droits d’accès suivants :

* Un accès à Adobe Experience Platform
* Accès aux Google Analytics universels (version Google Analytics 360) ou aux Google Analytics 4 (version gratuite ou version Google Analytics 360)
* Accès au Customer Journey Analytics et à ses [autorisations d’administrateur](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=fr-FR#admin-access-permissions).

La manière d&#39;importer les données Google Analytics dans Adobe Experience Platform dépend de la version de Google Analytics que vous utilisez :

| Si vous utilisez... | Vous avez aussi besoin de cette licence... | Et fais ça... |
| --- | --- | --- |
| **Google Analytics universel** | Google Analytics 360 | Exécutez les étapes 1 à 5 des instructions ci-dessous |
| **Google Analytics 4** | Version GA gratuite ou Google Analytics 360 | Exécutez les étapes 1 et 3 à 5 des instructions ci-dessous. Pas besoin de passer à l&#39;étape 2. |

## Incorporer des données historiques

### 1. Connectez vos données Google Analytics à BigQuery.

Notez que les instructions suivantes sont basées sur le Google Analytics universel. Elles s’appliquent aux données historiques. Pour obtenir des instructions sur les données de diffusion en flux continu en direct, consultez la section Intégration de données de diffusion en flux continu en direct dans AEP.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3416092?hl=en).

### 2. Transformez les sessions Google Analytics en événements dans BigQuery

>[!IMPORTANT]
>
>Cette étape s’applique uniquement aux clients d’Universal Analytics.

Les données GA stockent chaque enregistrement dans leurs données sous la forme d’une session d’utilisateur plutôt que de événements individuels. Vous devez créer une requête SQL pour transformer les données Universal Analytics en un format compatible Experience Platform. Vous appliquez la fonction &quot;unnest&quot; au champ &quot;hits&quot; dans le schéma GA. Voici l&#39;exemple SQL que vous pouvez utiliser :

`SQL sample`

Une fois la requête terminée, enregistrez les résultats complets dans un tableau BigQuery.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3437618?hl=en).

Ou vue cette vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Exportez des événements Google Analytics au format JSON dans l’Enregistrement Google Cloud et enregistrez-les dans un compartiment.

Ensuite, vous allez importer les événements Google Analytics dans l’Enregistrement Google Cloud au format JSON. Puis vous l&#39;amenez dans l&#39;Experience Platform.

Reportez-vous à [ces instructions](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

### 4. Intégrer les données de l’Enregistrement Google Cloud dans l’Experience Platform

Dans l’Experience Platform, sélectionnez **[!UICONTROL Sources]** et recherchez l’option **[!UICONTROL Enregistrement Google Cloud]**. A partir de là, vous n&#39;avez qu&#39;à trouver le jeu de données que vous avez enregistré à partir de Big Requête.

Vue de cette vidéo pour obtenir des instructions :

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5. Importez des événements GCS dans Adobe Experience Platform et faites correspondre les données au schéma XDM.

Ensuite, vous pouvez mapper les données du événement GA dans un jeu de données existant que vous avez créé précédemment, ou créer un nouveau jeu de données à l&#39;aide du schéma XDM de votre choix. Une fois que vous avez sélectionné le schéma, l’Experience Platform applique l’apprentissage automatique pour mapper automatiquement chacun des champs des données Google Analytics à votre propre schéma.

Les mappages sont très faciles à modifier et vous pouvez même créer des champs dérivés ou calculés à partir des données Google Analytics. Une fois que vous avez terminé de mapper les champs dans votre schéma XDM, vous pouvez planifier cette importation de manière récurrente et appliquer une validation d&#39;erreur pendant le processus d&#39;assimilation. Cela permet de s’assurer qu’il n’y a aucun problème avec les données que vous avez importées.

## Envoi de données Google Analytics en flux continu en direct

Vous pouvez également capturer des événements de flux continu en direct depuis Google Tag Manager directement vers Adobe Experience Platform.

### Ajouter des variables personnalisées

Après vous être connecté au compte Google Tag Manager, vous devez ajouter des variables constantes personnalisées liées aux ID d’organisation et d’ensembles de données d’Adobe. Vous disposez probablement déjà de variables dans Google Tag Manager qui sont envoyées à Google Analytics, telles que l’adresse électronique du client, le nom du client, la langue et l’état de connexion du client. Vous devez définir 5 nouvelles variables personnalisées :

* ID d’organisation Adobe Experience Cloud
* Point de terminaison DCS Streaming
* ID de jeu de données Experience Platform
* Schéma de référence
* Horodatage de la page.

L’obtention de ces valeurs permet de s’assurer que toutes les données Google Analytics sont envoyées au jeu de données correct et qu’elles disposent du schéma approprié. Si vous ne connaissez pas votre organisation d’Experience Cloud ou l’une des autres variables que nous venons de mentionner, votre gestionnaire de compte d’Adobe peut vous aider à effectuer le suivi.

Une fois que vous avez défini ces variables personnalisées, nous pouvons configurer un déclencheur pour envoyer également à l&#39;Experience Platform toutes les données que vous envoyez déjà aux Google Analytics.

### Configuration d’un déclencheur dans Google Tag Manager

Dans cet exemple, le déclencheur &quot;Création de compte&quot; a été défini, où `pageUrl equals account-creation` est défini. En ajoutant des informations à ce déclencheur, vous pouvez vous assurer que lorsque l’utilisateur s’authentifie et que la page de création de compte se charge, les données sont envoyées aux Google Analytics et aux AEP.

Pour obtenir des instructions, vue cette vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/332668)

### Étapes suivantes

Une fois que le Adobe Experience Platform a commencé à recevoir les données Google Analytics en direct, et que vous avez renvoyé les données Google Analytics historiques de BigQuery, vous êtes prêt à passer à la CJA et

1. [Créez votre première ](/help/connections/create-connection.md) connexion qui rassemble les données GA avec toutes les autres données client à l’aide d’un &quot;ID client&quot; commun.
1. Faites une analyse étonnante dans Workspace, par exemple...

*Est-ce là que ce sujet devrait s&#39;arrêter ou devons-nous aller dans les détails sur la connexion ?*