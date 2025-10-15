---
title: Jeux de données d’exportation Customer Journey Analytics
description: Décrit comment utiliser les jeux de données d’exportation pour sauvegarder vos données.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 7%

---

# Exporter les jeux de données

Cet article décrit comment le [!DNL Customer Journey Analytics Export datasets] peut être utilisé pour implémenter le cas d’utilisation d’exportation de données [&#x200B; suivant &#x200B;](overview.md) :

- Sauvegarde des données

## Introduction

L’exportation de données à l’aide de [!DNL Experience Platform Export datasets] vous permet d’exporter des données de vos vues de données Customer Journey Analytics vers n’importe quelle destination d’espace de stockage.

Extension ![BI](../assets/export-datasets.svg)

## Informations supplémentaires

Vous pouvez exporter des jeux de données bruts du lac de données dans Experience Platform vers des destinations d’espace de stockage. Cette exportation figure dans la terminologie des destinations Experience Platform, appelée destinations d’exportation de jeu de données. Consultez [&#x200B; Exporter des jeux de données vers des destinations d’espace de stockage &#x200B;](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/ui/activate/export-datasets) pour une présentation.

Les destinations suivantes de stockage dans le cloud sont prises en charge :

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Zone d’atterrissage des données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Interface utilisateur d’Experience Platform

Vous pouvez exporter et planifier l’exportation de vos jeux de données via l’interface utilisateur d’Experience Platform. Cette section décrit les étapes à suivre.

#### Sélectionner la destination

Lorsque vous avez déterminé la destination d’espace de stockage vers laquelle vous souhaitez exporter le jeu de données, [sélectionnez la destination](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Lorsque vous n’avez pas encore configuré de destination pour votre espace de stockage dans le cloud préféré, vous devez [créer une connexion de destination](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Dans le cadre de la configuration d’une destination, vous pouvez définir :

- le type de fichier (JSON ou Parquet),
- si le fichier résultant doit être compressé ou non, et
- si un fichier manifeste doit être inclus ou non.


#### Sélectionner le jeu de données

Lorsque vous avez sélectionné la destination, à l’étape suivante **[!UICONTROL Sélectionner des jeux de données]** vous devez sélectionner votre jeu de données dans la liste des jeux de données. Si vous avez créé plusieurs requêtes planifiées et que vous souhaitez que les jeux de données soient envoyés à la même destination d’espace de stockage, vous pouvez sélectionner les jeux de données correspondants. Voir [Sélectionner vos jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) pour plus d’informations.

#### Planifier l’exportation des jeux de données

Enfin, vous souhaitez planifier l’exportation de votre jeu de données dans le cadre de l’étape **[!UICONTROL Planification]**. Au cours de cette étape, vous pouvez définir le planning et déterminer si l’exportation du jeu de données doit être incrémentielle ou non. Voir [Planifier l’exportation de jeux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) pour plus d’informations.


#### Dernières étapes

[Vérifiez](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) votre sélection et, une fois qu’elle est correcte, commencez à exporter votre jeu de données vers la destination d’espace de stockage.

Tout d’abord, vous devez [vérifier](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform crée un ou plusieurs fichiers `.json` ou `.parquet` à l’emplacement de stockage défini dans la destination. Attendez-vous à ce que de nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous avez configuré. Experience Platform crée une structure de dossiers à l’emplacement de stockage que vous avez spécifié dans le cadre de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, en suivant le modèle : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.

### API Flow Service

Vous pouvez également exporter et planifier l’exportation des jeux de données à l’aide d’API. Les étapes impliquées sont documentées dans [Exporter des jeux de données à l’aide de l’API Flow Service](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Commencer

Pour exporter des jeux de données, vérifiez que vous disposez des [autorisations requises](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Vérifiez également que la destination vers laquelle vous souhaitez envoyer votre jeu de données prend en charge l’exportation de jeux de données. Vous devez ensuite [rassembler les valeurs des en-têtes obligatoires et facultatifs](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que vous utilisez dans les appels API. Vous devez également [identifier la spécification de connexion et les identifiants de spécification de flux de la destination](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) vers lesquels vous envisagez d’exporter des jeux de données.

#### Récupérer des jeux de données éligibles

Vous pouvez [récupérer une liste de jeux de données éligibles](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) pour l’exportation et vérifier si votre jeu de données fait partie de cette liste à l’aide de l’API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets).


#### Créer une connexion source

Ensuite, vous devez [créer une connexion source](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) pour le jeu de données, à l’aide de son identifiant unique, que vous souhaitez exporter vers la destination d’espace de stockage. Vous utilisez l’API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection).

#### S’authentifier auprès de la destination (créer une connexion de base)

Vous devez maintenant [créer une connexion de base](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) pour authentifier et stocker en toute sécurité les informations d’identification vers votre destination d’espace de stockage dans le cloud à l’aide de l’API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection).


#### Fournir des paramètres d’exportation

Ensuite, vous devez [créer une connexion cible supplémentaire qui stocke les paramètres d’exportation](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) pour votre jeu de données à l’aide, une fois de plus, de l’API [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection). Ces paramètres d’exportation incluent l’emplacement, le format de fichier, la compression, etc.

#### Configurer le flux de données

Enfin, vous [configurez le flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) pour vous assurer que votre jeu de données est exporté vers votre destination d’espace de stockage à l’aide de l’API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow). Au cours de cette étape, vous pouvez définir le planning de l’exportation à l’aide du paramètre `scheduleParams` .

#### Valider le flux de données

Pour [vérifier les exécutions réussies de votre flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilisez l’API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) en spécifiant l’identifiant du flux de données comme paramètre de requête. Cet identifiant de flux de données est un identifiant renvoyé lorsque vous configurez le flux de données.

[Vérifier](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) une exportation de données réussie. Lors de l’exportation de jeux de données, Experience Platform crée un ou plusieurs fichiers `.json` ou `.parquet` à l’emplacement de stockage défini dans la destination. Attendez-vous à ce que de nouveaux fichiers soient déposés dans votre emplacement de stockage en fonction du planning d’exportation que vous avez configuré. Experience Platform crée une structure de dossiers à l’emplacement de stockage que vous avez spécifié dans le cadre de la destination sélectionnée, où il dépose les fichiers exportés. Un nouveau dossier est créé pour chaque heure d’exportation, en suivant le modèle : `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. Le nom de fichier par défaut est généré de manière aléatoire pour garantir que les noms de fichier exportés soient uniques.
