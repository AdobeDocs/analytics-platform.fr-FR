---
title: Exportation de jeux de données Customer Journey Analytics
description: Décrit comment utiliser les jeux de données Exporter pour sauvegarder vos données.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 6%

---


# Exportation de jeux de données

Cet article décrit la manière dont le [!DNL Customer Journey Analytics Export datasets] peut être utilisé pour implémenter les éléments suivants : [cas d’utilisation d’exportation de données](overview.md):

- Sauvegarde des données

## Introduction

Exporter des données à l’aide de [!DNL Experience Platform Export datasets] vous permet d’exporter des données de vos vues de données de Customer Journey Analytics vers n’importe quelle destination de stockage dans le cloud.

![Extension BI](../assets/export-datasets.svg)

## Informations supplémentaires

Vous pouvez exporter des jeux de données bruts, du lac de données en Experience Platform, vers des destinations de stockage dans le cloud. Cette exportation est conforme à la terminologie des destinations Experience Platform appelée destinations d’exportation de jeux de données. Voir [Exportation des jeux de données vers des destinations de stockage dans le cloud](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) pour une vue d’ensemble.

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

Lorsque vous avez déterminé la destination de stockage dans le cloud vers laquelle vous souhaitez exporter le jeu de données, [sélectionner la destination ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Lorsque vous n’avez pas encore configuré de destination pour votre espace de stockage préféré dans le cloud, vous devez [créer une connexion de destination ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Dans le cadre de la configuration d’une destination, vous pouvez définir :

- le type de fichier (JSON ou Parquet),
- si le fichier obtenu doit être compressé ou non, et
- si un fichier de manifeste doit être inclus ou non.


#### Sélectionner le jeu de données

Lorsque vous avez sélectionné la destination, dans la **[!UICONTROL Sélectionner des jeux de données]** vous devez sélectionner votre jeu de données dans la liste des jeux de données. Si vous avez créé plusieurs requêtes planifiées et que vous souhaitez que les jeux de données soient envoyés vers la même destination de stockage dans le cloud, vous pouvez sélectionner les jeux de données correspondants. Voir [Sélectionner vos jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) pour plus d’informations.

#### Planifier l’exportation des jeux de données

Enfin, vous souhaitez planifier l’exportation de votre jeu de données dans le cadre du **[!UICONTROL Planification]** étape . Au cours de cette étape, vous pouvez définir le planning et déterminer si l’exportation du jeu de données doit être incrémentielle ou non. Voir [Planification de l’exportation des jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) pour plus d’informations.


#### Étapes finales

[Réviser](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) votre sélection, et lorsque cela est correct, commencez à exporter votre jeu de données vers la destination de stockage dans le cloud.

Tout d’abord, vous devez [verify](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform en crée un ou plusieurs `.json` ou `.parquet` dans l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle suivant : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

### API de service de flux

Vous pouvez également exporter et planifier l’exportation des jeux de données à l’aide d’API. Les étapes à suivre sont décrites dans la section [Exportation de jeux de données à l’aide de l’API Flow Service](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Prise en main

Pour exporter des jeux de données, assurez-vous que vous disposez de la variable [autorisations requises](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Vérifiez également que la destination vers laquelle vous souhaitez envoyer votre jeu de données prend en charge l’exportation de jeux de données. Vous devez alors [rassembler les valeurs des en-têtes requis et facultatifs ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que vous utilisez dans les appels API. Vous devez également [identifier les spécifications de connexion et les identifiants de spécification de flux de la destination ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) vous envisagez d’exporter des jeux de données vers .

#### Récupération des jeux de données éligibles

Vous pouvez [récupérer une liste de jeux de données éligibles ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) pour l’exportation et vérifiez si votre jeu de données fait partie de cette liste à l’aide de la variable [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Création d’une connexion source

Ensuite, vous devez [créer une connexion source ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) pour le jeu de données, à l’aide de son identifiant unique, que vous souhaitez exporter vers la destination de stockage dans le cloud. Vous utilisez la variable [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Authentification à la destination (créer une connexion de base)

Vous devez maintenant [créer une connexion de base ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) pour vous authentifier et stocker en toute sécurité les informations d’identification dans votre destination de stockage dans le cloud à l’aide de la variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fournir des paramètres d’exportation

Ensuite, vous devez [créer une connexion cible supplémentaire qui stocke les paramètres d’exportation ;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) pour votre jeu de données en utilisant, une fois de plus, la variable [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Ces paramètres d’exportation incluent l’emplacement, le format de fichier, la compression, etc.

#### Configuration du flux de données

Enfin, vous [Configuration du flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) pour vous assurer que votre jeu de données est exporté vers votre destination de stockage dans le cloud à l’aide de la variable [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. Au cours de cette étape, vous pouvez définir le planning de l&#39;export, à l&#39;aide du `scheduleParams` .

#### Validation du flux de données

À [vérifier les exécutions réussies de votre flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilisez le [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, spécifiant l’identifiant de flux de données comme paramètre de requête. Cet identifiant de flux de données est un identifiant renvoyé lors de la configuration du flux de données.

[Vérifier](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform en crée un ou plusieurs `.json` ou `.parquet` dans l’emplacement de stockage défini dans votre destination. Attendez-vous à ce que les nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous configurez. Experience Platform crée une structure de dossiers dans l’emplacement de stockage que vous avez spécifié comme faisant partie de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, selon le modèle suivant : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.