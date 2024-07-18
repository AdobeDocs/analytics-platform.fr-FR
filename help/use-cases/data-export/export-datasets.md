---
title: Exportation de jeux de données Customer Journey Analytics
description: Décrit comment utiliser les jeux de données Exporter pour sauvegarder vos données.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 6%

---

# Exporter les jeux de données

Cet article décrit comment [!DNL Customer Journey Analytics Export datasets] peut être utilisé pour mettre en oeuvre le [cas d’utilisation d’exportation de données](overview.md) suivant :

- Sauvegarde des données

## Introduction

L&#39;export de données à l&#39;aide de [!DNL Experience Platform Export datasets] vous permet d&#39;exporter des données de vos vues de données de Customer Journey Analytics vers n&#39;importe quelle destination de stockage dans le cloud.

![Extension BI](../assets/export-datasets.svg)

## Informations supplémentaires

Vous pouvez exporter des jeux de données bruts, du lac de données en Experience Platform, vers des destinations de stockage dans le cloud. Cette exportation est conforme à la terminologie des destinations Experience Platform appelée destinations d’exportation de jeux de données. Voir [Exportation de jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) pour obtenir un aperçu.

Les destinations de stockage dans le cloud suivantes sont prises en charge :

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Zone d’atterrissage des données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Interface utilisateur Experience Platform

Vous pouvez exporter et planifier l’exportation de vos jeux de données via l’interface utilisateur de l’Experience Platform. Cette section décrit les étapes à suivre.

#### Sélectionner la destination

Lorsque vous avez déterminé la destination de stockage dans le cloud vers laquelle vous souhaitez exporter le jeu de données, [sélectionnez la destination](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Lorsque vous n&#39;avez pas encore configuré de destination pour l&#39;espace de stockage de votre choix dans le cloud, vous devez [créer une nouvelle connexion de destination](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Dans le cadre de la configuration d’une destination, vous pouvez définir :

- le type de fichier (JSON ou Parquet),
- si le fichier obtenu doit être compressé ou non, et
- si un fichier de manifeste doit être inclus ou non.


#### Sélectionner le jeu de données

Lorsque vous avez sélectionné la destination, à l’étape suivante **[!UICONTROL Sélectionner les jeux de données]** , vous devez sélectionner votre jeu de données dans la liste des jeux de données. Si vous avez créé plusieurs requêtes planifiées et que vous souhaitez que les jeux de données soient envoyés vers la même destination de stockage dans le cloud, vous pouvez sélectionner les jeux de données correspondants. Voir [Sélectionner vos jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) pour plus d’informations.

#### Planifier l’exportation des jeux de données

Enfin, vous souhaitez planifier l’exportation de votre jeu de données dans le cadre de l’étape **[!UICONTROL Planification]** . Au cours de cette étape, vous pouvez définir le planning et déterminer si l’exportation du jeu de données doit être incrémentielle ou non. Pour plus d’informations, voir [Planification de l’exportation des jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) .


#### Étapes finales

[Vérifiez](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) votre sélection et, lorsque cela est correct, commencez à exporter votre jeu de données vers la destination de stockage dans le cloud.

Tout d’abord, vous devez [vérifier](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) que l’exportation des données a réussi. Lors de l’exportation de jeux de données, Experience Platform crée un ou plusieurs fichiers `.json` ou `.parquet` à l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

### API de service de flux

Vous pouvez également exporter et planifier l’exportation des jeux de données à l’aide d’API. Les étapes impliquées sont documentées dans [Export des jeux de données à l’aide de l’API Flow Service](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Commencer

Pour exporter des jeux de données, assurez-vous de disposer des [autorisations requises](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Vérifiez également que la destination vers laquelle vous souhaitez envoyer votre jeu de données prend en charge l’exportation de jeux de données. Vous devez ensuite [ rassembler les valeurs des en-têtes requis et facultatifs](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que vous utilisez dans les appels API. Vous devez également [identifier les spécifications de connexion et les identifiants de spécification de flux de la destination](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) vers laquelle vous envisagez d’exporter des jeux de données.

#### Récupération des jeux de données éligibles

Vous pouvez [récupérer une liste de jeux de données éligibles](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) pour l’exportation et vérifier si votre jeu de données fait partie de cette liste à l’aide de l’API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Création d’une connexion source

Ensuite, vous devez [créer une connexion source](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) pour le jeu de données, à l’aide de son identifiant unique, que vous souhaitez exporter vers la destination de stockage dans le cloud. Vous utilisez l’API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### Authentification à la destination (créer une connexion de base)

Vous devez maintenant [créer une connexion de base](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) pour vous authentifier et stocker en toute sécurité les informations d’identification vers votre destination de stockage dans le cloud à l’aide de l’API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Fournir des paramètres d’exportation

Ensuite, vous devez [ créer une connexion cible supplémentaire qui stocke les paramètres d’exportation](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) pour votre jeu de données à l’aide, une fois de plus, de l’API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection). Ces paramètres d’exportation incluent l’emplacement, le format de fichier, la compression, etc.

#### Configuration du flux de données

Enfin, vous [ configurez le flux de données ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) pour vous assurer que votre jeu de données est exporté vers votre destination de stockage dans le cloud à l’aide de l’API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). Au cours de cette étape, vous pouvez définir la planification de l’exportation à l’aide du paramètre `scheduleParams` .

#### Validation du flux de données

Pour [vérifier les exécutions réussies de votre flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilisez l’API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns), en spécifiant l’identifiant du flux de données comme paramètre de requête. Cet identifiant de flux de données est un identifiant renvoyé lors de la configuration du flux de données.

[Vérifiez](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) qu’une exportation de données a réussi. Lors de l’exportation de jeux de données, Experience Platform crée un ou plusieurs fichiers `.json` ou `.parquet` à l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.
