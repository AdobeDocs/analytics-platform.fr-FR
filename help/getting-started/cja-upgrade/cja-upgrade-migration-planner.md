---
title: Migration d’AppMeasurement ou des balises vers XDM
description: Découvrez comment migrer d’AppMeasurement ou des balises vers XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: db34e721f156b3eb0aab20b2dca57e194c83d6fb
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 5%

---

# Migration des balises vers XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="Présentation des migrations"
>abstract="Migrer une implémentation de balises vers Adobe Experience Platform Web SDK lors de la mise à niveau vers Customer Journey Analytics.<br/>Continuer avec une migration existante ou en démarrer une nouvelle."

<!-- markdownlint-enable MD034 -->

Le planificateur de migration fournit un assistant de migration qui automatise la migration des balises vers XDM, y compris la création de schémas. Il s’agit de certaines des tâches les plus complexes et les plus longues associées à une mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

## Implémentations Adobe Analytics prises en charge

Le planificateur de migration prend en charge les implémentations d’Adobe Analytics qui utilisent l’extension Analytics (balises).

Le planificateur de migration n’est pas disponible pour les implémentations d’Adobe Analytics qui utilisent AppMeasurement ou Experience Platform Web SDK.

## Tâches de mise à niveau incluses dans le planificateur de migration

Le planificateur de migration fournit un assistant de migration qui automatise les tâches de mise à niveau complexes et longues suivantes :

* **création de schéma XDM** : crée automatiquement un schéma XDM en fonction des variables de votre suite de rapports Adobe Analytics. Le planificateur de migration analyse intelligemment les variables de votre suite de rapports Adobe Analytics, puis utilise ces informations pour créer les champs nécessaires dans XDM. Le schéma XDM qui en résulte inclut uniquement les champs nécessaires dans votre schéma Customer Journey Analytics.

  Vous pouvez également pointer vers un schéma XDM existant ou créer un schéma XDM à partir de zéro.

  +++ Si vous choisissez de créer un schéma XDM à partir de zéro, vous pouvez développer cette section pour obtenir des informations sur les ressources utiles.

  * [Planifiez l’architecture de votre schéma XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

  * [Créez le schéma personnalisé souhaité dans Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

    Tenez compte des options suivantes lors de la création de votre schéma :

    * Si vous souhaitez intégrer Customer Journey Analytics à RTCDP, vous devez activer l’option **[!UICONTROL Profil]** sur votre schéma, comme décrit dans la section [Création d’un schéma XDM à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}. Une fois cette option activée, lorsque les données sont ingérées dans des jeux de données basés sur ce schéma, ces données sont fusionnées dans le profil client en temps réel.

    * Si vous souhaitez inclure des données de médias en streaming, vous devez [configurer votre schéma pour ingérer et utiliser des données en streaming](/help/data-ingestion/streaming.md){target="_blank"}.

    +++

  * **Migration de votre implémentation Adobe Analytics vers le Web SDK** : que votre implémentation Adobe Analytics utilise des balises ou JavaScript, le planificateur de migration vous guide tout au long de la migration vers le Web SDK d’Experience Platform.

    * **Migrez les propriétés de balise d’AppMeasurement vers le SDK Web** :

    * **Migration d’une implémentation JavaScript d’AppMeasurement vers la bibliothèque JavaScript de Web SDK**

  * **Création de vues de données dans Customer Journey Analytics** : crée automatiquement des vues de données et les remplit avec des composants, en fonction des champs de schéma XDM créés.


## Avant de commencer

Avant de créer une migration, vérifiez que vous disposez des éléments suivants :

* Implémentation d’Adobe Analytics prise en charge (extension Analytics pour les balises). Voir [Implémentations Adobe Analytics prises en charge](#supported-adobe-analytics-implementations).

* Accès à la propriété Adobe Tags à migrer, dans l’organisation Experience Cloud à laquelle vous êtes connecté.

* Accès à la suite de rapports Adobe Analytics dont vous souhaitez mapper les variables à XDM.

* Autorisation de créer des schémas dans Adobe Experience Platform.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Migration d’une implémentation Analytics vers Web SDK

Une migration passe par trois étapes : [!UICONTROL **Audit**], [!UICONTROL **Mappage**] et [!UICONTROL **Implémentation**]. Procédez comme suit pour créer une migration, puis continuez avec [Valider et déployer une migration](#validate-and-deploy-a-migration) pour terminer chaque étape.

1. Dans Customer Journey Analytics, ouvrez le [!UICONTROL **Planificateur de migration**].

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. Dans le Planificateur de migration, dans l’onglet [!UICONTROL **Migrations**], sélectionnez [!UICONTROL **Nouveau**].

   ![Boîte de dialogue Nouvelle migration, dans laquelle vous choisissez un type de migration et saisissez un nom de migration.](assets/migration-planner-new-migration.png)

1. Indiquez les informations suivantes :

   | Nom du champ | Fonction |
   | --------- | ---------- |
   | [!UICONTROL **Nom**] | Spécifiez un nom pour cette migration. |
   | [!UICONTROL **Description**] | Spécifiez une description facultative pour cette migration. |
   | [!UICONTROL **Propriété Tags**] | Sélectionnez la propriété Adobe Tags à migrer. Pour plus d’informations, voir [Propriétés](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"} dans la documentation d’Experience Platform. |
   | [!UICONTROL **Bibliothèque de balises**] | Sélectionnez l’instantané de bibliothèque de balises sur lequel la migration est basée. L’instantané détermine la version de votre bibliothèque de balises utilisée. Pour plus d’informations, voir [Présentation de la publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"} dans la documentation d’Experience Platform. |

1. Dans le champ [!UICONTROL **Nom de la migration**], indiquez un nom pour cette migration, puis sélectionnez [!UICONTROL **Suivant**].

1. Sélectionnez la propriété de balise à migrer, puis sélectionnez [!UICONTROL **Suivant**].

   Seules les propriétés de balise disponibles pour votre organisation Experience Cloud connectée s’affichent.

1. Sélectionnez l’instantané de bibliothèque de balises à migrer, puis sélectionnez [!UICONTROL **Suivant**].

   L’instantané détermine la version de votre bibliothèque de balises sur laquelle la migration est basée. Chaque instantané montre son environnement (par exemple, [!UICONTROL **Développement**], [!UICONTROL **Évaluation**] ou [!UICONTROL **Production**]).

1. Sélectionnez le jeu de mappages pour déterminer comment les variables Analytics seront mappées aux champs de schéma XDM.

   Effectuez l’une des opérations suivantes :

   * Sélectionnez [!UICONTROL **Créer un jeu de mappages**].

   * Sélectionnez un jeu de mappages existant.

     Les jeux de mappages créés lors d’une migration précédente ou en tant que jeux de mappages autonomes peuvent être sélectionnés.

     La réutilisation d’un jeu de mappages sur plusieurs migrations applique les mêmes mappages à chaque migration.

1. Sélectionnez [!UICONTROL **Créer une migration**].

1. Passez à la section suivante, [&#x200B; Validation et déploiement d’une migration &#x200B;](#validate-and-deploy-a-migration).

## Validation et déploiement d’une migration

Après avoir créé une migration, ouvrez-la pour en terminer les trois étapes : [!UICONTROL **Audit**], [!UICONTROL **Mappage**] et [!UICONTROL **Implémentation**].

1. Dans le Planificateur de migration, sélectionnez l’onglet [!UICONTROL **Migrations**].

1. En regard de la migration à valider, sélectionnez [!UICONTROL **Ouvrir**].

   La page d’aperçu de la migration présente les trois étapes à effectuer, ainsi qu’un résumé de votre migration et de ses artefacts.

   ![Page Aperçu de la migration avec les cartes Étape d’audit, de mappage et d’implémentation.](assets/migration-planner-overview.png)

1. Effectuez l’étape [!UICONTROL **Audit**] :

   1. Dans la carte d’audit ([!UICONTROL **Audit de l’extension de balises**] ou [!UICONTROL **Audit JavaScript**], en fonction du type de migration), sélectionnez [!UICONTROL **Démarrer l’audit**] pour passer en revue les règles et les éléments de données inclus dans la migration.

      ![La page d’audit, où vous sélectionnez des règles et des éléments de données et résolvez les résultats.](assets/migration-planner-audit.png)

   1. Sur les onglets [!UICONTROL **Règles**] et [!UICONTROL **Éléments de données**], sélectionnez les éléments à inclure dans la migration.

      Les règles marquées [!UICONTROL **Dans la bibliothèque**] sont publiées. Les règles marquées [!UICONTROL **Propriété uniquement**] existent dans la propriété mais ne font pas partie de la bibliothèque sélectionnée.

   1. Passez en revue tous les résultats concernant les règles sélectionnées. Pour chaque résultat, sélectionnez [!UICONTROL **Vérifier**] pour le résoudre ou [!UICONTROL **Ignorer**] pour ne pas le résoudre.

      Par exemple, lorsque deux règles comportent des événements et des conditions identiques, le résultat [!UICONTROL **Dupliquer des événements de règle**] vous permet de conserver une règle et de supprimer l’autre, ou de sélectionner [!UICONTROL **Ne rien faire**] pour accuser réception du résultat sans le modifier.

      La résolution des résultats est facultative avant de continuer. Pour obtenir la liste complète des types de résultats et la façon de les résoudre, voir [Vérifier et résoudre les résultats d’audit](#review-and-resolve-audit-findings).

   1. Sélectionnez [!UICONTROL **Enregistrer et continuer**].

1. Terminez l’étape [!UICONTROL **Mappage**] :

   1. Dans la vignette [!UICONTROL **Mappage XDM → Analytics**], sélectionnez [!UICONTROL **Créer un mappage**].

   1. Choisissez de créer un schéma basé sur vos variables Analytics ou de le mapper à un schéma Experience Platform existant, puis suivez les invites pour sélectionner votre suite de rapports, mapper les champs et passer en revue le schéma.

      Pour obtenir des instructions détaillées, voir [Mappage de variables Analytics à des champs XDM](#map-analytics-variables-to-xdm-fields). Pour réutiliser un ensemble de mappages entre des migrations, voir [Création et gestion des jeux de mappages](#create-and-manage-mapping-sets).

1. Effectuez l’étape [!UICONTROL **Implémentation**] :

   1. Dans la vignette [!UICONTROL **Générer l’implémentation de Web SDK**], utilisez les résultats de l’audit et du mappage pour générer le package d’implémentation de Web SDK, puis déployez-le sur votre site.

      Pour obtenir des instructions détaillées, voir [&#x200B; Générer et déployer l’implémentation de Web SDK &#x200B;](#generate-and-deploy-the-web-sdk-implementation).


## Examiner et résoudre les constatations d&#39;audit

Au cours de l’étape [!UICONTROL **Audit**], le planificateur de migration signale les résultats concernant les règles que vous avez sélectionnées. La résolution des résultats est facultative avant de continuer, mais leur résolution permet d’assurer une migration propre.

Pour chaque résultat, sélectionnez [!UICONTROL **Vérifier**] pour ouvrir le résultat et choisir comment le résoudre, ou sélectionnez [!UICONTROL **Ignorer**] pour ne pas y remédier.

Le planificateur de migration peut signaler les types de résultats suivants :

* [!UICONTROL **Événements de règle en double**] : plusieurs règles comportent des événements et des conditions identiques. Lorsque vous passez en revue le résultat, comparez les règles principales et les règles en double, conservez une règle et supprimez l’autre, ou sélectionnez [!UICONTROL **Ne rien faire**] pour accuser réception du résultat sans le modifier.

* [!UICONTROL **Logique de règle en double**] : les règles partagent la même logique. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **Actions de règle désordonnées**] : les actions d’une règle s’exécutent dans un ordre qui peut entraîner des problèmes lors de la migration. <!-- Confirm the exact remediation options for this finding type. -->

Si un résultat ne comporte aucune résolution guidée, le planificateur de migration affiche [!UICONTROL **Aucun détail de résolution disponible**]. Passez en revue le résultat manuellement et ignorez-le lorsqu’il est résolu.

Le panneau [!UICONTROL **Résultats**] indique le nombre de résultats que vous avez traités et le nombre de résultats qui sont toujours ouverts. Lorsque vous avez terminé, sélectionnez [!UICONTROL **Enregistrer et continuer**].

## Mappage de variables Analytics à des champs XDM

Au cours de l’étape [!UICONTROL **Mappage**], vous mappez vos variables Analytics aux champs XDM et générez ou sélectionnez le schéma cible. Dans la vignette [!UICONTROL **Mappage XDM → d’Analytics**], sélectionnez [!UICONTROL **Créer un mappage**], puis effectuez les étapes suivantes :

1. **Choix du schéma** : choisissez de créer un schéma en fonction de vos variables Analytics ou de le mapper à un schéma Experience Platform existant.

1. **Suite de rapports** : sélectionnez la suite de rapports Analytics dont vous souhaitez mapper les variables.

1. **Schéma Experience Platform** : créez le schéma XDM cible ou sélectionnez le schéma existant à mapper.

1. **Mappage manuel** : passez en revue les mappages automatiques et ajustez la manière dont les variables Analytics individuelles sont mappées sur les champs XDM.

1. **Vérifier le schéma** : vérifiez les mappages et le schéma résultants, puis confirmez.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

Pour réutiliser un ensemble de mappages entre des migrations, voir [Création et gestion des jeux de mappages](#create-and-manage-mapping-sets).

## Comparer les sorties de migration

Utilisez [!UICONTROL **Comparer les sorties**] sur la page d’aperçu de la migration pour valider votre migration avant de la déployer.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Générer et déployer l’implémentation de Web SDK

Au cours de l’étape [!UICONTROL **Implémentation**], le planificateur de migration utilise les résultats de votre audit et de votre mappage pour créer le package d’implémentation de Web SDK.

1. Sur la page d’aperçu de la migration, dans la vignette [!UICONTROL **Générer l’implémentation de Web SDK**], générez le package d’implémentation.

1. Créez la bibliothèque de balises pour la migration en sélectionnant [!UICONTROL **Créer la bibliothèque de balises**].

1. Configurez le déploiement double, puis déployez l’implémentation de Web SDK sur votre site.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

Pour connaître les artefacts générés par cette étape, voir [Exporter les artefacts de migration](#export-migration-artifacts).

## Exporter les artefacts de migration

La page d’aperçu de la migration fournit les artefacts générés par le planificateur de migration. Vous pouvez télécharger des artefacts individuels à partir du panneau [!UICONTROL **Artefacts de projet**] ou sélectionner [!UICONTROL **Tout exporter**] pour tout exporter en même temps.

Les artefacts suivants sont disponibles :

* [!UICONTROL **Mapping JSON**] : mappage entre vos variables Analytics et vos champs XDM.

* [!UICONTROL **Schéma XDM (JSON)**] : schéma XDM cible créé pour la migration.

* [!UICONTROL **Bibliothèque de développement de balises**] : bibliothèque de balises créée pour l’implémentation de Web SDK.

Chaque artefact affiche son statut, par exemple [!UICONTROL **Prêt**] ou [!UICONTROL **Non créé**]. Un artefact peut être téléchargé après avoir été généré à l’étape correspondante.

## Créer et gérer des jeux de mappages {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="Jeux de mappages"
>abstract="Les jeux de mappages déterminent la manière dont les variables Analytics sont mappées sur des champs XDM.<br/>Créez un jeu de mappages ou choisissez-en un existant pour appliquer les mêmes mappages sur plusieurs migrations. Vous pouvez également référencer des jeux de mappages dans d’autres tâches de migration."

<!-- markdownlint-enable MD034 -->

Les jeux de mappages déterminent la manière dont les variables Analytics sont mappées aux champs de schéma XDM.

Vous pouvez créer un nouveau jeu de mappages [pendant le processus de migration](#migrate-an-analytics-implementation-to-the-web-sdk). Vous pouvez également créer un jeu de mappages autonome à utiliser avec une migration ultérieure ou avec d’autres tâches de migration.

### Création d’un jeu de mappages autonome {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="Choisir un schéma"
>abstract="Les jeux de mappages déterminent la manière dont les variables Analytics sont mappées sur des champs XDM.<br/>Créez un jeu de mappages ou choisissez-en un existant pour appliquer les mêmes mappages sur plusieurs migrations. Vous pouvez également référencer des jeux de mappages dans d’autres tâches de migration."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="Préférence du groupe de champs"
>abstract="Choisissez des groupes de champs standard pour utiliser, si possible, les groupes de champs Adobe publiés. Cela favorise une cohérence maximale et revient aux champs du client personnalisé lorsqu’aucun champ standard n’est disponible.<br/>Choisissez des groupes de champs personnalisés pour utiliser, si possible, les champs personnalisés de l’espace de noms du client. Cela favorise une flexibilité maximale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="Période de recherche en amont"
>abstract="Contrôle la période à prendre en compte lors de la détermination des variables qui reçoivent activement des données. Les variables qui incluent des données au cours de la période de recherche en amont sont incluses dans le schéma."

<!-- markdownlint-enable MD034 -->

1. Dans le planificateur de migration, sélectionnez l’onglet [!UICONTROL **Jeux de mappages**].

1. Sélectionnez [!UICONTROL **Nouveau jeu de mappages**].

1. Dans le champ [!UICONTROL **Nom**], saisissez un nom explicite afin de pouvoir identifier ce jeu de mappages ultérieurement, puis sélectionnez [!UICONTROL **Suivant**].

1. Dans le menu [!UICONTROL **Suite de rapports**], sélectionnez la suite de rapports dont vous souhaitez mapper les variables aux champs XDM, puis sélectionnez [!UICONTROL **Suivant**].

1. Dans la section [!UICONTROL **Choisir un schéma pour votre mappage XDM**], choisissez de créer un nouveau schéma basé sur vos variables Analytics ou de le mapper à un schéma Experience Platform existant.

   Le choix de la création d’un schéma vous guide tout au long du processus de mappage de vos variables Analytics aux champs XDM. Choisir d’utiliser un schéma existant permet de mapper manuellement vos variables à un schéma préenregistré dans le registre des schémas d’Experience Platform.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **Créer un schéma**] : exécutez les analyses de base et avancées pour suggérer automatiquement des mappages de champs XDM pour vos variables Analytics, puis passez en revue le schéma obtenu.

   * [!UICONTROL **Utiliser un schéma existant**] : recherchez et sélectionnez un schéma déjà enregistré dans le registre des schémas d’Experience Platform, puis faites glisser manuellement les variables Analytics sur les champs XDM.

1. Dans le menu déroulant [!UICONTROL **Préférence de groupe de champs**] choisissez comment organiser les variables personnalisées en groupes de champs :

   * [!UICONTROL **Standard en premier**] : utilisez, si possible, les groupes de champs Adobe publiés. Cela favorise une cohérence maximale et revient aux champs du client personnalisé lorsqu’aucun champ standard n’est disponible.

   * [!UICONTROL **Personnalisé d’abord**] : utilisez si possible des champs personnalisés d’espace de noms du client. Cela favorise une flexibilité maximale.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. Dans le champ [!UICONTROL **Période de recherche en amont**], sélectionnez la période de recherche en amont à examiner lors de la détermination des variables qui reçoivent activement des données. Les variables qui incluent des données au cours de la période de recherche en amont sont incluses dans le schéma.

1. Sélectionnez [!UICONTROL **Créer un jeu de mappages**].

Le nouveau jeu de mappages apparaît dans l’onglet [!UICONTROL **Jeux de mappages**] où vous pouvez l’ouvrir pour en consulter les détails.

### Exportation d’un jeu de mappages

Vous pouvez exporter un jeu de mappages pour l’utiliser avec d’autres tâches de migration ou dans d’autres outils.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### Publication de jeux de mappages de versions et

Chaque jeu de mappages possède un statut et une version. Dans l’onglet [!UICONTROL **Jeux de mappages**], un jeu de mappages peut apparaître comme suit :

* [!UICONTROL **brouillon**] : le jeu de mappages est toujours en cours de modification.

* [!UICONTROL **publié**] : le jeu de mappages a été finalisé.

* [!UICONTROL **en migration**] : le jeu de mappages est lié à une ou plusieurs migrations.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### Modification d’un jeu de mappages <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### Suppression d’un jeu de mappages <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## Gestion des migrations existantes

### Recherche et suivi des migrations

L’onglet [!UICONTROL **Migrations**] répertorie vos migrations et leur progression. Utilisez-le pour rechercher une migration à poursuivre ou pour vérifier le statut des migrations en cours.

* **Rechercher** : utilisez le champ de recherche pour rechercher une migration par nom ou propriété.

* **Filtrer** : filtrez la liste par type de migration ou par statut.

* **Suivre la progression** : chaque migration affiche sa progression au cours des trois étapes (par exemple, 1/3) et un statut global :

  * [!UICONTROL **Non démarrée**] : la migration a été créée, mais aucune étape n’est terminée.

  * [!UICONTROL **En cours**] : au moins une étape est terminée.

  * [!UICONTROL **Terminé**] : les trois étapes sont terminées.

Pour poursuivre une migration, sélectionnez [!UICONTROL **Ouvrir**] en regard de celle-ci.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

