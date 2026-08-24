---
description: Découvrez comment comparer les fonctionnalités des flux de données dans Customer Journey Analytics et Adobe Analytics
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Fonctionnalité Comparaison des flux de données dans Customer Journey Analytics et Adobe Analytics
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 82ccb1359540e5200641b33c3d4aef7f2447003f
workflow-type: tm+mt
source-wordcount: 1451
ht-degree: 1%

---

# Comparaison des flux de données dans Customer Journey Analytics et Adobe Analytics

{{release-limited-testing}}

Les flux de données dans Customer Journey Analytics et Adobe Analytics vous permettent d’exporter des données brutes vers des plateformes tierces.

Si vous avez déjà utilisé des flux de données dans Adobe Analytics, utilisez les informations suivantes pour comprendre les différences au niveau des fonctionnalités et des concepts disponibles :

## Fonctionnalités disponibles uniquement dans les flux de données Customer Journey Analytics

Si vous migrez depuis Adobe Analytics, les fonctionnalités suivantes sont nouvelles dans les flux de données Customer Journey Analytics :

* **Champs dérivés** : composants personnalisés créés à partir de transformations basées sur des règles qui peuvent être incluses dans votre schéma de flux.

* **Assemblage** : résolution d’identité entre appareils qui lie les événements sur plusieurs appareils à une seule personne.

* **Modèle de données structurées** : les flux sont créés et diffusés à l’aide de données structurées plutôt que de chaînes plates.

* **Rail des composants Analysis Workspace** : sélectionnez des dimensions et des mesures en utilisant le même rail de composants qu’Analysis Workspace, plutôt qu’une liste statique de noms de variables.

* **Segmentation** : les segments appliqués à la vue de données sont automatiquement hérités et des segments supplémentaires peuvent être appliqués directement au flux.

* **Fuseau horaire de la vue de données** : les fenêtres de diffusion de flux s’alignent sur le fuseau horaire de la vue de données.

* **Sortie Parquet** : les fichiers sont diffusés au format Parquet, prenant en charge de manière native les données imbriquées et structurées complexes.

* **Chemins de partition de style Hive** : les fichiers Output utilisent des chemins de style Hive pour des requêtes efficaces dans les environnements de lac de données.

* **Propagation de la mise à jour des composants** : les modifications apportées aux composants dans la vue de données se propagent automatiquement au flux.

<!-- * Web MCP when it's added -->

Le tableau [comparaison des fonctionnalités](#functionality-comparison) ci-dessous présente chacune de ces fonctionnalités en détail, ainsi que les différences entre les fonctionnalités présentes dans les deux produits.


## Comparaison des fonctionnalités

| **concepts et options de configuration** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **Saisie de données**<br/> Type de données qui peut être collecté et inclus dans les flux de données. | Prend en charge l’entrée de données cross-canal, y compris les données web, les données de centre d’appels, les données de point de vente, etc. | Prend principalement en charge l’entrée de données web et mobile. D’autres types de données (tels que les données des centres d’appels ou des points de vente) peuvent être ingérés par le biais de sources de données, mais avec des capacités de traitement très limitées. |
| **Traitement des données**<br/> Les données sont traitées à différentes étapes, en fonction du produit que vous utilisez. | Les données sont traitées au **moment du rapport** et de nombreuses fonctionnalités de création de rapports peuvent donc être utilisées pour modifier les données historiques, comme le groupement, les champs dérivés et la segmentation. | Les données sont traitées au **moment de la collecte**. Par conséquent, les fonctionnalités de création de rapports telles que les règles de traitement et les règles VISTA n’affectent pas les données historiques. |
| **Assemblage**<br/> résolution d’identité entre appareils et canaux qui lie les événements à une seule personne. | Pris en charge. Les identités groupées peuvent être incluses dans les exportations de flux de données lorsque le groupement est configuré sur la connexion. | Non pris en charge. L’identité du visiteur est déterminée au moment de la collecte à partir des cookies d’ID de visiteur ; aucune résolution entre appareils post-collecte n’est disponible. |
| **Fréquence de diffusion**<br/> Détermine la fréquence d’envoi du flux de données et la période incluse dans le flux. | **Quotidien** (de minuit à minuit dans le fuseau horaire de la vue de données) ou **Horaire**. | **Quotidien** (de minuit à minuit dans le fuseau horaire de la suite de rapports) ou **Horaire**. <p>Les flux de 15 minutes sont possibles, mais ne sont pas disponibles par défaut.</p> |
| **Accès en retard**<br/> Accès dont l’horodatage appartient à une fenêtre de fréquence de diffusion précédente, mais qui arrivent après l’expiration de cette fenêtre. <p>Par exemple, les accès tardifs peuvent provenir d’une application mobile qui met en mémoire tampon les événements hors ligne et les envoie lorsqu’elle se reconnecte.</p> | Le paramètre **Délai de traitement** contrôle la durée pendant laquelle le système attend la fermeture de la fenêtre de fréquence avant de déclencher l’exportation, ce qui laisse un temps supplémentaire pour l’arrivée des données retardées. | Les accès en retard peuvent être **inclus ou exclus** via l’option de configuration **Accès en retard**. <p>Le paramètre **Intervalle de recherche en amont** contrôle l’intervalle de temps écoulé par le système pour inclure les données différées.</p> |
| **Accès dans le désordre**<br/> Accès dont les horodatages ne correspondent pas à l’ordre dans lequel ils ont été reçus. | Étant donné que Customer Journey Analytics accepte les données en flux continu et par lots, il n’existe aucune garantie que les événements pour une personne donnée arriveront dans l’ordre d’horodatage. Bien que Customer Journey Analytics réorganise les données par horodatage et par personne, il ne peut exporter que les données qui sont arrivées. Cela signifie que les accès en retard peuvent être exportés après les accès avec un horodatage ultérieur.<p>Le paramètre **Délai de traitement** permet de réduire les événements dans le désordre dans la sortie du flux de données en donnant plus de temps aux données par lots d’arriver avant l’exportation. L’ordre des événements dans la diffusion n’est pas garanti.</p><p>**Important** : le consommateur final des données de votre flux de données doit être en mesure de gérer les horodatages dans le désordre, par personne, car la commande des accès dans la diffusion du flux de données n’est pas garantie.</p> | Adobe Analytics exige que les données arrivent dans l’ordre par visiteur au moment de la collecte, mais l’ordre des accès dans la diffusion du flux de données n’est pas garanti.</p> |
| **Fenêtre de renvoi**<br/> Exporte les données historiques comprises entre deux dates antérieures. | Limité à la fenêtre dynamique de données de la connexion. | Limité à la limite de conservation des données de la suite de rapports : **25 mois** par défaut. |
| **Schéma**<br/> Le schéma de flux de données détermine les colonnes disponibles à inclure dans un flux de données. | Le schéma de flux de données est basé sur la configuration de la vue de données.  Les composants qui peuvent être inclus dans le schéma de flux de données sont un sous-ensemble des composants disponibles dans la configuration des vues de données. | Une liste statique prédéfinie de plus de 1 100 variables. De nombreuses colonnes sont exportées sous la forme de **paires prétraitées et post-traitées** (par exemple, `eVar1`/`post_eVar1`), ce qui représente une grande partie du nombre de colonnes. |
| **Créateur de flux de données**<br/> interface utilisée pour configurer les colonnes incluses dans un flux de données. | Utilise un rail de composants avec les mêmes dimensions et mesures nommées disponibles dans la vue de données, correspondant à l’expérience Analysis Workspace. | Utilise une liste plate de noms de variables brutes (tels que `eVar1`, `prop5`) sélectionnés à partir d’un ensemble prédéfini de plus de 1 100 colonnes. Les composants ne sont pas nommés ni décrits au-delà de leur identifiant de variable. |
| **Champs dérivés**<br/> Composants personnalisés définis à l’aide de transformations basées sur des règles appliquées au moment du rapport. | Pris en charge. Les composants de champ dérivés peuvent être inclus dans le schéma de flux de données avec les dimensions et mesures standard. | Non pris en charge. |
| **Mises à jour des composants**<br/> Indique si les modifications apportées à la configuration des composants sont répercutées dans les futures sorties du flux de données. | Les modifications apportées aux composants dans la vue de données (comme le changement de nom ou la suppression d’une dimension) se propagent automatiquement aux futurs flux de données. | Sans objet. Le schéma des colonnes est prédéfini et statique ; aucun composant au niveau de la vue de données ne doit être mis à jour. |
| **Recherches**<br/> Les recherches dynamiques vous permettent de recevoir des fichiers de recherche supplémentaires dans votre flux de données qui ne seraient pas disponibles autrement. | Non nécessaire, car les recherches et les classifications sont toutes deux disponibles en tant que dimensions traitées directement dans la vue de données. Lorsque vous traitez une recherche ou une classification en tant que dimension dans la vue de données, les valeurs résolues apparaissent sous la forme de colonnes régulières dans la sortie Parquet, en ligne avec les données d’événement, et non sous la forme de fichiers de référence distincts. | Utilisé pour faire correspondre un nombre d’une colonne de flux de données à une valeur réelle. Spécifiques à un certain ensemble d’éléments (navigateur, système d’exploitation, appareil mobile) et appliqués sous la forme d’un fichier distinct fourni avec le flux de données. |
| **Définition de session**<br/> Définition d’une visite ou d’une limite de session, qui affecte la manière dont les événements sont regroupés et attribués. | Défini dans la vue de données. | Défini au moment de la collecte. |
| **Segmentation**<br/> La possibilité de filtrer la sortie des flux de données à l’aide de segments. | Les segments appliqués à la vue de données sont automatiquement hérités par le flux de données. Des segments supplémentaires peuvent également être appliqués directement à un flux de données individuel. | Non pris en charge. Les flux de données exportent toutes les données collectées sans filtrage de segment. |
| **Mesures calculées**<br/> mesures personnalisées que vous pouvez créer à partir de mesures existantes. | Non disponible | Non disponible |
| **Modèle de persistance**<br/> si ou comment les valeurs de dimension persistent d’un événement à l’autre. | Flexible. Les paramètres de persistance de la vue de données (attribution et expiration) sont appliqués au moment du rapport lorsque le flux est généré. Prend en charge tous les paramètres d’attribution disponibles dans une vue de données : **Original**, **Le plus récent**, **Tous**, **Premier connu** et **Dernier connu**. | Seuls les modèles d’attribution **la plus récente (dernière touche)** et **valeur d’origine (première touche)** sont représentés. L’affectation linéaire est gérée de la même manière que la dernière touche. |
| **Format de fichier de sortie**<br/> format utilisé pour les fichiers de sortie de flux de données diffusés vers votre destination cloud. | Parquet<p>Prend en charge de manière native des données imbriquées et structurées complexes. Les listes de produits sont représentées sous la forme de tableaux structurés/objets imbriqués. </p><p>Nécessite un outil de lecture prenant en compte le parquet, tel que BigQuery, Snowflake ou Apache Spark.</p> | TSV<p>Lignes plates et lisibles par l’utilisateur. ne prend pas en charge les données structurées de manière native ; les champs complexes tels que les listes de produits doivent être codés en tant que chaînes délimitées propriétaires nécessitant une logique d’analyse personnalisée ;</p> |
| **Chemins d’accès aux fichiers de sortie**<br/> structure de répertoires utilisée pour les fichiers de sortie diffusés. | Utilise des **chemins de partition de type ruche** (par exemple, `year=2024/month=01/day=15/`), permettant un nettoyage efficace des partitions lors de l’interrogation de données dans des environnements de lac de données tels que Databricks ou Apache Spark. | Utilise une structure de répertoires plate. Les chemins de style Hive ne sont pas pris en charge. |
| **Destinations de diffusion**<br/> Emplacements de stockage dans le cloud où les fichiers de sortie des flux de données peuvent être envoyés. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. <p>Prend également en charge **SFTP**.</p> |

{style="table-layout:auto"}

