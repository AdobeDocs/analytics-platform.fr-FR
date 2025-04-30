---
description: Découvrez comment exporter un projet Analysis Workspace vers un emplacement cloud.
keywords: Analysis Workspace
title: Exporter des rapports Customer Journey Analytics vers le cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 158d75f81490edca2b5219a9b3ede2fbcdcc5901
workflow-type: tm+mt
source-wordcount: '2285'
ht-degree: 98%

---

# Exporter des rapports Customer Journey Analytics vers le cloud {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Créer des exports de tableaux complets pour obtenir des fonctionnalités similaires à celles de Data Warehouse"
>abstract="Les export de tableaux complets sont disponibles dès que vous voyez des données dans Analysis Workspace. Vous pouvez créer ou planifier des exports de tableaux complets selon vos besoins.<br><br>La création d’exports de tableaux complets ne prend que quelques minutes si vous savez déjà quelles données inclure dans l’export."

<!-- markdownlint-enable MD034 -->

Vous pouvez exporter des tableaux complets Workspace à partir de Customer Journey Analytics et envoyer des exports vers des destinations cloud désignées.

D’autres méthodes d’export de rapports Customer Journey Analytics sont également disponibles, comme décrit dans la section [Vue d’ensemble de l’export](/help/analysis-workspace/export/export-project-overview.md).

## Comprendre les exports de tableaux complets

Vous pouvez exporter des tableaux complets d’Analysis Workspace vers des fournisseurs cloud tels que Google, Azure, Amazon et Adobe.

[Les avantages de l’exports de tableaux complets vers le cloud](#advantages-of-exporting-to-the-cloud) incluent la possibilité d’exporter des millions de lignes, d’inclure des mesures calculées, de structurer la sortie des données en valeurs concaténées, etc.

Lorsque vous exportez des tableaux complets, tenez compte des points suivants :

* Avant d’exporter des données vers le cloud, assurez-vous que vos tableaux, votre environnement et vos autorisations répondent aux [exigences d’export](#export-requirements).

* Certains [fonctionnalités](#unsupported-features) et certains [composants](#unsupported-components) ne sont pas pris en charge lors de l’export de tableaux complets vers le cloud.

Procédez comme suit lors de l’export de tableaux complets vers le cloud :

1. [Configurer un compte cloud](/help/components/exports/cloud-export-accounts.md)

1. [Configurer un emplacement sur le compte](/help/components/exports/cloud-export-locations.md)

1. [Exporter un tableau complet depuis Workspace](#export-full-tables-from-analysis-workspace)

1. [Accéder aux données dans le cloud](#view-exported-data-and-manifest-file) et [Gérer les exports dans Adobe](/help/components/exports/manage-exports.md)

![Processus d’export de tableau complet décrit dans les étapes 1 à 4.](assets/export-full-table-process.png)

## Exporter des tableaux complets depuis Analysis Workspace

>[!NOTE]
>
>Avant d’exporter des données comme décrit dans cette section, pour en savoir plus sur l’export de tableaux complets, consultez la section [Comprendre l’export de tableaux complets](#understand-full-table-export) ci-dessus.

Pour exporter des tableaux complets à partir d’Analysis Workspace, procédez comme suit :

1. Si ce n’est pas déjà fait, configurez un compte et un emplacement d’export, comme décrit dans la section [Configurer des comptes d’export cloud](/help/components/exports/cloud-export-accounts.md).

1. Dans Analysis Workspace, cliquez avec le bouton droit sur le tableau à structure libre contenant les données à exporter.

1. Sélectionnez [!UICONTROL **Exporter le tableau complet**].

   ![Menu déroulant du tableau à structure libre avec Exporter le tableau complet en surbrillance.](assets/export-full-table.png)

1. Dans la boîte de dialogue [!UICONTROL **Nouvel export de tableau complet**], spécifiez les informations suivantes :

   | Nom du champ | Fonction |
   |---------|----------|
   | Nom | Spécifiez le nom de l’export. Ce nom s’affiche dans la liste des exports. |
   | Balises | Vous pouvez appliquer une balise existante à l’export ou créer une balise et l’appliquer. <p>Pour appliquer une balise existante à l’export, sélectionnez une balise dans le menu déroulant. Toutes les balises de votre société peuvent être appliquées<!-- double-check this -->.</p> <p>Pour créer une balise, saisissez son nom, puis appuyez sur Entrée.</p><p>Tenez compte des points suivants lors de l’application de balises à un export : <ul><li>Les balises que vous appliquez peuvent être filtrées ou recherchées dans le tableau des exports.</li> <li>Les balises appliquées à un projet ne sont pas automatiquement appliquées lors de l’export d’un tableau complet, comme décrit dans la section « Configurer les colonnes sur la page des exports » de la section [Gérer les exports](/help/components/exports/manage-exports.md). (Lorsque vous [planifiez un projet complet pour l’export](/help/analysis-workspace/export/t-schedule-report.md), toutes les balises appliquées au projet sont également automatiquement appliquées à l’export.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Description | Ajoutez une description à l’export. Vous pouvez choisir d’afficher les descriptions sous forme d’une colonne dans la [page Exports](/help/components/exports/manage-exports.md) lors de l’affichage des exports. |
   | Vue de données | Sélectionnez la vue de données qui contient les composants que vous souhaitez inclure dans l’export. Le menu déroulant Vue des données se trouve dans le coin supérieur gauche de la boîte de dialogue et peut être identifié par l’icône de vue de données ![icône de vue de données](assets/data-view-icon.png).  <p>**Note :** si vous choisissez une vue de données à laquelle il manque des composants déjà inclus dans votre tableau de données, on vous invite à effacer le tableau de données et à le recréer à l’aide des composants inclus dans la vue de données sélectionnée. </p> |
   | Intervalle de recherche en amont | Sélectionnez la période de création de rapports à inclure dans chaque fichier d’export. Les options incluent [!UICONTROL **Aujourd’hui**], [!UICONTROL **Hier**], [!UICONTROL **Les 7 derniers jours**], [!UICONTROL **Les 30 derniers jours**], [!UICONTROL **Cette semaine**] et [!UICONTROL **Ce mois-ci**]. <p>Cette option ne s’affiche pas lorsque la variable [!UICONTROL **Fréquence d’export**] est définie sur [!UICONTROL **Envoyer maintenant (une seule fois)**]. |
   | Tableau des données | Affiche le tableau à structure libre que vous exportez. Vous pouvez modifier le tableau de données en faisant glisser des composants du panneau de gauche vers le tableau. Le projet se met à jour dynamiquement lorsque vous ajoutez des composants à la zone de travail.  <p>Tous les segments qui ont été appliqués au tableau complet du projet s’affichent en haut de chaque colonne individuelle du tableau.</p> |
   | Effacer | Efface le contenu du tableau de données. Vous pouvez ainsi commencer à créer un tableau directement dans la boîte de dialogue d’export du nouveau tableau complet. |
   | Fréquence des exportations | Définissez la planification de la fréquence d’export. <p>Vous pouvez choisir [!UICONTROL **Envoyer maintenant (une seule fois)**] pour envoyer l’export une seule fois. Lorsque vous sélectionnez cette option, l’export est lancé immédiatement.<p>Vous pouvez également choisir d’envoyer l’export selon un planning défini. Lors d’un envoi selon un planning, les options comprennent [!UICONTROL **Quotidien**], [!UICONTROL **Hebdomadaire**], [!UICONTROL **Mensuel par jour de la semaine**], [!UICONTROL **Mensuel par jour du mois**], [!UICONTROL **Annuel par jour du mois**] et [!UICONTROL **Annuel par date spécifique**]. </p><p>Lors de la sélection d’une fréquence d’export, tenez compte des points suivants :</p><ul><li>Les options du champ [!UICONTROL **Intervalle de recherche en amont**] changent en fonction de ce que vous sélectionnez ici.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>D’autres champs de configuration s’affichent en fonction de l’option choisie.</li></ul> |
   | Début le | Jour et heure auxquels l’export planifié doit commencer. <p>Cette option n’est disponible que lors du choix d’une fréquence d’export planifié.</p> |
   | Se termine le | Jour et heure d’expiration de l’export planifié. L’export planifié ne s’exécute plus après la date et l’heure que vous avez définies. <p>Cette option n’est disponible que lors du choix d’une fréquence d’export planifié.</p> |
   | Format du fichier | Choisissez si les données exportées doivent être au format .csv ou .json. |
   | Compte | Sélectionnez le compte d’export dans le cloud où vous souhaitez que les données soient envoyées. <p>Si vous n’avez pas encore configuré de compte cloud à utiliser, vous pouvez également configurer un nouveau compte :<ol><li>Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :<ul><li>[!UICONTROL **Nom du compte d’emplacement**] : spécifiez un nom pour le compte d’emplacement. Ce nom apparaît lors de la création d’un emplacement. </li><li>[!UICONTROL **Description de compte d’emplacement**] : fournissez une brève description du compte pour le différencier des autres comptes du même type de compte.</li><li>[!UICONTROL **Type de compte**] : sélectionnez le type de compte cloud vers lequel vous exportez. Les types de compte disponibles sont Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake et Zone de destination des données AEP.</li></ul><li>Pour terminer la configuration de votre compte, sélectionnez le lien ci-dessous, correspondant au [!UICONTROL **type de compte**] sélectionné :<ul><li>[Zone de destination des données AEP](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[RBAC Azure](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Nom de l’emplacement | Sélectionnez l’emplacement sur le compte où vous souhaitez que les données d’export soient envoyées.<p>Si vous n’avez pas encore configuré l’emplacement que vous souhaitez utiliser sur le compte que vous avez sélectionné, vous pouvez configurer un nouvel emplacement :<ol><li>Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes : <ul><li>[!UICONTROL **Nom**] : nom de l’emplacement.</li><li>[!UICONTROL **Description**] : fournissez une brève description de l’emplacement pour le différencier des autres emplacements sur le compte compte.</li><li>[!UICONTROL **Compte d’emplacement**] : sélectionnez le compte sur lequel vous souhaitez créer l’emplacement.</li></ul><li>Pour terminer la configuration de votre emplacement, sélectionnez le lien ci-dessous, qui correspond au type de compte que vous avez sélectionné dans le champ [!UICONTROL **Compte d’emplacement**] :<ul><li>[Zone de destination des données AEP](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[RBAC Azure](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Enregistrer**] pour enregistrer l’export.

   Les données sont envoyées au compte cloud que vous avez spécifié à la fréquence que vous avez spécifiée.

1. (Facultatif) Après avoir créé l’export, que vous ayez choisi de l’envoyer maintenant ou selon un planning défini, vous pouvez l’afficher et le gérer sur la [page Exports](/help/components/exports/manage-exports.md) et l’afficher dans les [journaux d’export](/help/components/exports/manage-export-logs.md).</p>

## Gérer des exports

Une fois les données exportées à partir d’Analysis Workspace, vous pouvez modifier, exporter à nouveau, dupliquer, baliser ou supprimer des exports existants, comme décrit dans la section [Gérer les exports](/help/components/exports/manage-exports.md).

## Afficher les données exportées et le fichier manifeste

### Données exportées

Les données exportées sont disponibles sous la forme d’un fichier compressé dans la destination cloud que vous avez configurée, comme décrit dans [Configuration des comptes d’export cloud](/help/components/exports/cloud-export-accounts.md) et [Configuration des emplacements d’export cloud](/help/components/exports/cloud-export-locations.md).

Le nom du fichier compressé est le suivant, selon que vous avez choisi le format CSV ou JSON :

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>Vous choisissez le format de fichier dans le champ [!UICONTROL **Format de fichier**] lors de l’export du tableau, comme décrit dans la section [Exporter des tableaux complets à partir d’Analysis Workspace](#export-full-tables-from-analysis-workspace).

### Fichier de manifeste 

Un fichier manifeste dont le nom de fichier est `cja-export-{reportInstanceId}-{idx}.json.gz` est inclus dans toute diffusion d’export réussie contenant au moins un fichier. Le fichier manifeste vous permet de confirmer que tous les fichiers ont bien été diffusés. Il comprend les informations suivantes :

* Liste de tous les fichiers diffusés

* Somme de contrôle MD5 de chaque fichier

<!-- add in  what the file name, structure, and file format will be -->

## Avantages de l’export vers le cloud

L’export de données Customer Journey Analytics vers le cloud vous permet d’effectuer les opérations suivantes :

* Exportez vers un emplacement partagé, tel que la Zone de destination des données Adobe Experience Platform, Google Cloud Platform, Microsoft Azure, Amazon S3 ou Snowflake.

* Stockez de grandes quantités de données historiques.

  Ce type de données peut être utilisé pour détecter des tendances à long terme afin d’obtenir des renseignements commerciaux (informatique décisionnelle) et, au bout du compte, conduire à une meilleure prise de décisions commerciales.

* Exportez les tableaux complets qui contiennent des milliers ou des millions de lignes (3 millions, 30 millions, 150 millions ou 300 millions de lignes, selon le type de licence). Les autres méthodes d’export autorisent un maximum de 50 000 lignes.

* Incluez les mesures calculées dans les données Customer Journey Analytics exportées.

* Structure la sortie des données en tant que valeurs concaténées.

* Exportez une fois ou selon un planning. (Également disponible avec [autres options d’export](/help/analysis-workspace/export/export-project-overview.md).)

* Exportez les fichiers au format CSV ou JSON. (Également disponible avec [autres options d’export](/help/analysis-workspace/export/export-project-overview.md).)

* Exporter les tableaux contenant plusieurs dimensions.

## Exigences d’export {#export-requirements}

### Configuration minimale requise

Assurez-vous que vos tableaux, votre environnement et vos autorisations répondent aux exigences suivantes :

* **Tableaux :** tous les tableaux doivent inclure au moins une dimension dans la ligne et une mesure dans chaque colonne pour être pris en charge avec un export de tableau complet.

* **Environnement :** assurez-vous que les [adresses IP](/help/technotes/ip-addresses.md) et [domaines](/help/technotes/domains.md) utilisés par Customer Journey Analytics sont autorisés via le pare-feu de leur entreprise.

* **Autorisations :** dans Adobe Admin Console, un profil de produit disposant de l’autorisation [!UICONTROL **Export de tableau complet**] doit être affecté aux utilisateurs et utilisatrices pour pouvoir exporter des tableaux complets. Pour plus d’informations sur l’attribution d’une autorisation à un profil de produits dans Admin Console, consultez [Autorisation Customer Journey Analytics dans Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Les personnes dotées du rôle [Administrateur ou administratrice de produit](/help/technotes/access-control.md#product-admin-role) ont toujours accès à l’export de tableaux complets ; il n’est pas nécessaire de leur attribuer l’autorisation [!UICONTROL **Export de tableau complet**].


### Fonctionnalités non prises en charge

Les fonctionnalités suivantes ne sont pas prises en charge et sont automatiquement supprimées des exports de tableaux complets :

* Pourcentages
* Totaux
* Filtrage de la recherche
* Lignes statiques
* Alignement des dates
* Mesures issues de jeux de données de résumé
* Dimensions dynamiques

  Pour plus d’informations, consultez [Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Les dimensions de la première répartition sont converties et ajoutées en tant que dimension secondaire dans la ligne du tableau exporté ; les autres répartitions ne sont pas incluses dans le tableau.
* Le tri n’est pas pris en charge pour la plupart des jeux de données ; il peut être utilisé pour les petits jeux de données.

### Composants non pris en charge

Les composants suivants ne sont pas pris en charge et Analysis Workspace vous invite à les supprimer de votre tableau lors d’un export de tableau complet :

* Mesures calculées utilisant des fonctions de base ou avancées dans la définition de mesure (voir [Fonctions de base](/help/components/calc-metrics/cm-functions.md) et [Fonctions avancées](/help/components/calc-metrics/cm-adv-functions.md) pour plus d’informations)
* Composants dont l’exportation a été restreinte par un administrateur (voir la section *Segment sur les politiques de gouvernance des données dans les vues de données* dans [Libellés et politiques](/help/data-views/data-governance.md) pour plus d’informations)
* Toute dimension répondant à l’ensemble des critères suivants :
   * A été créé à partir d’un champ qui fait partie d’un [tableau d’objets](/help/use-cases/object-arrays.md) (similaire aux variables à plusieurs valeurs dans Adobe Analytics).
   * A la [persistance activée](/help/data-views/component-settings/persistence.md).
   * N’utilise pas de [dimension de liaison](/help/use-cases/data-views/binding-dimensions-metrics.md).
* Dimensions multiples provenant de champs faisant référence à différents [tableaux d’objets](/help/use-cases/object-arrays.md). (Plusieurs dimensions référençant le même tableau d’objets sont autorisées.)
* Plus de 10 dimensions et 10 mesures par rapport (jusqu’à 10 dimensions et 10 mesures sont prises en charge).
* Dans les colonnes de tableau :
   * Périodes
   * Dimensions
* Dans les lignes de tableau :
   * Mesures calculées
   * Mesures
   * Périodes
   * Segments

### Comportement d’attribution

L’export de tableau complet prend en charge les mesures calculées qui n’utilisent pas un modèle d’attribution par défaut (comme décrit dans la section *Utiliser un modèle d’attribution autre que celui par défaut* dans [Paramètres de colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Si un modèle d’attribution autre que celui par défaut est utilisé dans un rapport, le modèle d’attribution utilisé dans le rapport est ignoré ou conservé, selon que le rapport comporte une ou plusieurs dimensions :

* **Pour les rapports qui incluent l’attribution de mesure dans une seule dimension :** [Attribution de mesure](/help/data-views/component-settings/attribution.md) remplace le [modèle d’attribution](/help/data-views/component-settings/persistence.md) comme cela est normalement fait lors de l’utilisation de l’attribution de mesure.

  Par exemple, une attribution de mesure « première touche » remplace une attribution de dimension « le plus récent ».

* **Pour les rapports qui incluent l’attribution de mesures sur plusieurs dimensions en même temps :** [Attribution de mesure](/help/data-views/component-settings/attribution.md) est appliquée en plus de la dimension [modèle d’attribution](/help/data-views/component-settings/persistence.md).

  Par exemple, une attribution de mesure « première touche » est appliquée en plus d’une attribution de dimension « le plus récent ». En outre, l’attribution de mesure sera appliquée aux paires d’éléments de dimension attribuées ultérieurement comme s’il s’agissait d’éléments de dimension uniques, plutôt qu’à chaque élément de dimension indépendamment comme cela est normalement fait dans un tableau à structure libre.

  >[!NOTE]
  >
  >Les rapports multidimensionnels ne sont pris en charge que lors de l’export de données vers le cloud, comme décrit dans cet article.

## Comparaison de l’export de tableaux complets (dans Customer Journey Analytics) vers Data Warehouse (dans Adobe Analytics)

Si vous utilisiez auparavant Data Warehouse pour exporter des données Adobe Analytics, le tableau suivant peut vous aider à comprendre les différences entre l’export de tableaux complets dans Customer Journey Analytics et l’export de données avec Data Warehouse dans Adobe Analytics.


| Fonctionnalité | Export de tableau complet dans Customer Journey Analytics | Data Warehouse dans Adobe Analytics |
|---------|----------|---------|
| Créer un rapport personnalisé | Oui | Oui |
| Mesures calculées | Oui | Non |
| Segments | Oui | Limitées |
| Dimensions | Limite de 10 | Illimitées |
| Mesures | Limite de 10 | Illimitées |
| Lignes de rapport | Limite de 3 millions, 30 millions, 150 millions ou 300 millions, selon le niveau | Illimitées |
| Nombre de rapports | Illimitées | Illimitées |
| Diffusion ad hoc (unique) | Oui | Oui |
| Planifier une diffusion récurrente | Oui | Oui |
| Diffusion par e-mail | Non | Oui |
| FTP/SFTP | Non | Ancienne prise en charge |
| Azure | Oui | Oui |
| Amazon S3 | Oui | Oui |
| Google Cloud Platform | Oui | Oui |
| Snowflake | Oui | Non |
| Fréquence de diffusion | Quotidien | Toutes les heures |
