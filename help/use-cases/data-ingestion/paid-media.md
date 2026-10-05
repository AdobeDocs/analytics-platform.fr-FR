---
title: Ingestion De Données De Médias Payants Dans Customer Journey Analytics
description: Découvrez comment ingérer des données de médias payants par le biais des connecteurs source Adobe Experience Platform et préparer des connexions, des vues de données et des mesures dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 4bb99471d256fe29dc54980a5da37cf2385b679f
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 0%
---

# Ingestion et utilisation de données de médias achetés

Les données de médias payants incluent les performances publicitaires et les métadonnées provenant de plateformes telles que [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok] et [!DNL LinkedIn]. Ce guide explique comment ingérer ces données dans Adobe Experience Platform et les rendre disponibles dans Customer Journey Analytics pour la création de rapports et l’analyse.

Les données multimédia payantes passent généralement par trois étapes :

1. Les plateformes Advertising fournissent des données de campagne, de publicité, de ressources et de performances.
1. Adobe Experience Platform ingère ces données par le biais d’un connecteur source et les stocke dans les jeux de données de médias achetés standard.
1. Customer Journey Analytics expose les jeux de données par le biais d’une connexion et d’une vue de données afin que vous puissiez analyser les données dans Workspace.

Les données de médias payants sont ingérées par le biais des connecteurs source Experience Platform. Par exemple, vous pouvez utiliser le connecteur [!DNL Meta Ads] dans la catégorie Advertising . Lorsque vous connectez une source prise en charge, Adobe met en service les jeux de données de médias achetés standard en fonction du schéma et des groupes de champs de médias achetés globaux.

## Conditions préalables

Vérifiez que vous disposez des droits d&#39;accès suivants dans Experience Platform :

* Autorisation d’affichage et de gestion des sources.
* Autorisation de créer des schémas, des jeux de données et des flux de données.
* Sandbox sélectionné pour fonctionner. Vous devez choisir le sandbox avant de poursuivre les étapes de configuration.

Si vous utilisez [!DNL Meta Ads] comme source, veillez également à respecter les conditions préalables suivantes :

* Compte [!DNL Meta Business Manager] avec au moins un compte publicitaire actif contenant des campagnes, des ensembles de publicités, des publicités et des ressources.
* Application [!DNL Meta] autorisée pour les [!DNL Graph API] et [!DNL Marketing API], configurée dans la Developer Console [!DNL Meta] et liée à [!DNL Business Manager].
* `ads_read` et portées de `ads_management` approuvées pour l’application.
* Accès de niveau annonceur ou supérieur pour l’utilisateur ou l’utilisatrice qui autorise la connexion.
* Accès vérifié aux comptes publicitaires prévus dans l’interface utilisateur d’[!DNL Meta].

L’authentification sur le connecteur utilise [!DNL OAuth 2.0]. Lors de la configuration, vous vous connectez et accordez l’accès au connecteur. Les jetons d’accès expirant, préparez-vous à réautoriser la connexion en cas de révocation de l’octroi.

## Modèle de données de média payant

[Les jeux de données de mesures récapitulatives](#summary-metrics-datasets) servent de tables de faits, et les jeux de données de recherche fournissent les dimensions associées. Les jeux de données de recherche se joignent aux jeux de données de mesures récapitulatives par `GUID` d’entité et valeurs d’identifiant natives pour les comptes, les campagnes, les groupes publicitaires, les annonces, les ressources et les expériences.

Les jeux de données de recherche partagent deux blocs de création communs :

* **Objet ID d’entité** : stocke les objets compte, annonce, groupe publicitaire, ressource, campagne et expérience. Chaque objet contient une clé globale générée par Adobe et un identifiant natif de la plateforme.
* **Métadonnées de base des médias payants** : stocke des champs descriptifs courants tels que le nom, le statut, l’objectif, l’objectif d’optimisation, la stratégie d’enchères, le type de budget, les valeurs de budget, la devise, le fuseau horaire, le statut de diffusion, les dates, le réseau publicitaire, le canal, le chemin d’accès à la hiérarchie, le réseau et les identifiants de portfolio.

Le tableau suivant résume les six jeux de données de recherche.

| Jeu de données de recherche | Contenus clés |
|---|---|
| Recherche de compte | Métadonnées au niveau du compte telles que le nom, la devise, le fuseau horaire, le statut, la limite de dépense et les dates de création |
| Recherche de campagne | Paramètres de la campagne pour le budget, la planification, le ciblage, le suivi des conversions, l’attribution, les emplacements, les objets promus, l’objectif et les ID de catalogue ou de boutique |
| Recherche de groupe publicitaire | Métadonnées du groupe publicitaire telles que le lien de la campagne, le statut, le budget, les objectifs d’optimisation et le ciblage |
| Recherche de publicité | Ajoutez des détails créatifs tels que des ressources, des variantes, des dimensions, des URL de suivi, call to action, du corps de texte, des titres, l’URL de destination, le statut de diffusion et le statut de révision |
| Recherche de ressources | Propriétés de la ressource telles que les dimensions, les détails de fichier, les propriétés d’image, les URL de média, les métadonnées d’utilisation, les métadonnées vidéo, la description, le sous-type, le titre et le type |
| Recherche d’expérience | Regroupements créatifs de niveau expérience tels que l’Experience ID, les ressources, le titre, la description et call to action |

### Jeux de données de mesures récapitulatives

Les jeux de données de mesures de résumé du média payant sont les jeux de données de résumé centraux. Chaque ligne d’un jeu de données de résumé représente généralement une entité pour un jour et comprend un horodatage, un identifiant, un type d’événement, des identifiants d’entité et des noms dénormalisés pour la création de rapports.

Chaque jeu de données de mesures récapitulatives peut inclure les groupes de mesures suivants :

* **Performances de base** : impressions, clics, taux de clics, engagements, taux d’engagement, conversions, taux de conversion, valeur de conversion, prospects, clics sur les liens, téléchargements et installations ou ouvertures d’applications.
* **Coût et budget** : dépenses quotidiennes, budget alloué et restant, fréquence, dépassement ou sous-exécution, mesures de coût moyen et montants des enchères.
* **Vidéo** : vues vidéo, jalons de taux d’affichage et temps de visionnage moyen.
* **Partage d’impression** : partage d’impression, partage des impressions les plus importantes et mesures de partage d’impression perdues.
* **Détails de conversion** : types de conversion, actions d’ajout au panier, passages en caisse, appels, demandes d’itinéraire, activité de formulaire de prospect et autres événements liés à la conversion.
* **Engagement social** : mentions J’aime, commentaires et suivis.
* **Attribution et chemin** : détails du modèle d’attribution, degré de confiance, poids, mesures de chemin et contribution du canal.
* **Qualité et fraude** : scores de qualité, indicateurs de fraude, taux de trafic non valides et mesures de sécurité de la marque.
* **Répartitions dimensionnelles** : les données peuvent être ventilées par canal, réseau publicitaire, type d’appareil, tranche d’âge, sexe, pays, ville, langue, jour de la semaine, catégorie d’audience, format de contenu créatif et d’autres dimensions selon la plateforme source.

### Jeux de données standard

Lorsque vous connectez une source de médias achetés, Adobe fournit 12 jeux de données de médias achetés standard en fonction des classes de schéma et des groupes de champs de médias achetés globaux. Ces jeux de données comprennent six jeux de données de mesures récapitulatives, six jeux de données de recherche et des jeux de données annexes. Les 12 jeux de données de résumé et de recherche doivent être présents pour que les données de médias achetés soient correctement résolues en aval.

#### Jeux de données requis

* Résumé du compte de média payant
* Résumé de la campagne média payante
* Résumé du groupe publicitaire du média payant
* Résumé de l’annonce publicitaire médias payants
* Résumé de l’expérience de média payant
* Résumé des ressources multimédia payantes
* Recherche de compte média payant
* Recherche de campagne multimédia payante
* Recherche de groupe publicitaire média payant
* Recherche de publicité multimédia payante
* Recherche d’expérience de média payante
* Recherche de ressources multimédias payantes

#### Prise en charge des jeux de données

Par exemple :

* Média payant et recherche démographique
* Résumé de l’emplacement de l’expérience multimédia payante
* Résumé géographique et médias payants
* Résumé de l’annonce publicitaire pour médias payants (mesures récapitulatives)
* Résumé démographique des ressources multimédias payantes

## Ingestion de données de médias achetés dans Adobe Experience Platform

Procédez comme suit pour connecter une source et ingérer des données de médias achetés dans Experience Platform :

1. Vérifiez que vous disposez des autorisations source Experience Platform requises et d’un accès à la plateforme publicitaire.
1. Dans Experience Platform, accédez à **[!UICONTROL Sources]** > **[!UICONTROL Catalogue]** > **[!UICONTROL Advertising]**.
1. Assurez-vous que vous vous trouvez dans le sandbox qui contient les jeux de données de médias achetés.
1. Sélectionnez le connecteur à utiliser, par exemple **[!DNL Meta Ads]**. Sélectionnez **[!UICONTROL Configurer]** pour créer une connexion ou sélectionnez **[!UICONTROL Ajouter des données]** pour ajouter plus de données à une connexion existante.
1. Authentifiez-vous avec [!DNL OAuth 2.0] en vous connectant avec un utilisateur disposant de l’accès requis au niveau de l’annonceur.
1. Sélectionnez les comptes publicitaires, les entités et les données insight à ingérer.
1. Vérifiez que les jeux de données de recherche et de mesures récapitulatives sont correctement configurés.
1. Saisissez les paramètres du flux de données, confirmez les jeux de données cibles et configurez le planning d’ingestion.
1. Enregistrez le flux de données et surveillez les exécutions dans **[!UICONTROL Sources]** > **[!UICONTROL Flux de données]**.
1. Vérifiez que les jeux de données de médias achetés standard existent et contiennent des données.

Avant de passer à Customer Journey Analytics, validez les données ingérées :

* Vérifiez que les `GUID` d’entité et les valeurs d’ID natives sont renseignées de manière cohérente sur les mesures récapitulatives et les jeux de données de recherche.
* Vérifiez que chaque ligne de mesures récapitulatives comprend un horodatage.
* Vérifiez que les champs de création de rapports clés tels que les dimensions (par exemple : `channel`, `adNetwork`) et les mesures (par exemple : `impressions`, `clicks`, `spend`) contiennent des valeurs. Notez que certains champs tels que `region` peuvent ne pas être renseignés par toutes les plateformes sources.
* Vérifiez que les valeurs de devise et de fuseau horaire sont cohérentes entre les comptes concernés.

## Importation de données de médias achetés dans Customer Journey Analytics

Customer Journey Analytics ne crée pas de rapports directement sur les jeux de données Experience Platform. Au lieu de cela, vous exposez les jeux de données par le biais d’une connexion, puis vous créez une vue de données qui définit les dimensions, les mesures et la logique utilisées dans les rapports.

### Créer ou mettre à jour une connexion

Pour créer ou mettre à jour une connexion, procédez comme suit :

1. Dans Customer Journey Analytics, [créez ou modifiez une connexion existante](/help/connections/create-connection.md).
1. Veillez à sélectionner le sandbox qui contient les jeux de données de médias achetés dans le cadre de la configuration de la connexion.
1. Ajoutez les jeux de données de mesures récapitulatives en tant que données récapitulatives. Si plusieurs jeux de données de mesures récapitulatives sont disponibles, utilisez [search](/help/connections/create-connection.md#add-datasets) pour filtrer selon les classes `Paid Media` afin d’identifier les jeux de données corrects.
1. Ajoutez chaque jeu de données de recherche en tant que jeu de données de recherche. Joignez le jeu de données de recherche aux données de résumé à l’aide des identifiants GUID d’entité correspondants (les clés globales générées par Adobe) pour le compte, la campagne, le groupe publicitaire, la publicité, la ressource et l’expérience. Certaines plateformes sources peuvent également prendre en charge les jointures sur les valeurs d’identifiant natives.
1. Vous pouvez éventuellement ajouter des données d’événement de parcours de navigation si vous souhaitez mettre en relation des données de médias achetés agrégées avec des métadonnées partagées telles que des identifiants, des codes de suivi ou des paramètres de `UTM`.
1. Examinez les [paramètres spécifiques au jeu de données](/help/connections/create-connection.md#dataset-settings) pour chaque jeu de données.
1. Enregistrez la connexion et confirmez que la connexion commence à renvoyer des données.

Les données de médias payantes sont des données agrégées et ne dépendent pas de l’assemblage d’identités au niveau de la personne. Les identifiants d’entité dans la table de résumé sont utilisés pour joindre des identités similaires dans les tables de recherche.

### Création d’une vue de données

Une fois la connexion prête, vous devez créer ou modifier une ou plusieurs vues de données pour la connexion :


1. Dans Customer Journey Analytics, [créez ou modifiez une ou plusieurs vues de données](/help/data-views/create-dataview.md) :
1. Définissez les paramètres par défaut tels que le fuseau horaire et la devise.
1. Ajoutez les composants dont vous avez besoin pour l’analyse de médias achetés.

Inclure des composants, tels que :

* **Dimensions** : campagne, canal, réseau publicitaire, groupe publicitaire, publicité, ressource, compte, région et type d’appareil.
* **Mesures** : impressions, clics, taux de clic publicitaire, dépenses, conversions, valeur de conversion, engagements et mesures vidéo ou de partage d’impression pertinentes.
* **Champs dérivés** : normalisez ou classifiez les dimensions à l’aide de la logique [analyse](/help/data-views/derived-fields/derived-fields.md#url-parse), [expressions régulières](/help/data-views/derived-fields/derived-fields.md#regex-replace) ou [recherche](/help/data-views/derived-fields/derived-fields.md#lookup) pour produire des valeurs de canal et de campagne cohérentes sur les réseaux publicitaires.
* **Regroupement récapitulatif** : [combinez les valeurs associées de plusieurs jeux de données en une seule dimension de rapport](/help/data-views/component-settings/summary-data-group.md), telle qu’une dimension de canal payant unifié.
* **Mesures calculées** : définissent des mesures d’efficacité réutilisables telles que le CPC, le CPM, le CPA, le CTR et le taux de conversion.

## Validation

Utilisez la liste de contrôle suivante pour valider l’implémentation.

### Vérifications Adobe Experience Platform

* Vérifiez que les autorisations source et l’accès à la plateforme publicitaire sont en place.
* Vérifiez que le connecteur est authentifié et que le flux de données s’exécute selon le calendrier.
* Vérifiez que les 12 jeux de données standard sont présents et renseignés.
* Vérifiez que les schémas utilisent les classes et groupes de champs de médias payants globaux.
* Vérifiez que les clés de jointure, les horodatages et les champs de rapport clés sont renseignés.

### Vérifications Customer Journey Analytics

* Vérifiez que la connexion inclut le jeu de données de mesures récapitulatives et les six jeux de données de recherche.
* Vérifiez que la vue de données inclut les dimensions publicitaires et les mesures de médias payants requises.
* Vérifiez que les champs dérivés normalisent les valeurs de canal et de campagne comme prévu.
* Vérifiez que le regroupement récapitulatif consolide les données multi-réseau si nécessaire.
* Vérifiez que les mesures calculées sont définies pour les ratios utilisés par votre organisation.
* Vérifiez que la création de rapports Workspace s’aligne sur la création de rapports source sur la plateforme publicitaire.


>[!MORELIKETHIS]
>
>[Connecteur source Meta Ads](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/advertising/meta-ads)
>
