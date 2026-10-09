---
title: Configuration automatique des médias payants Content Analytics
description: Découvrez la configuration automatique des jeux de données, de la connexion, des vues de données, etc.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 2%
---
# Configuration automatique des médias payants

Lorsque vous activez le canal média payant dans Content Analytics et enregistrez la configuration, Adobe met à jour la connexion et les vues de données sélectionnées avec la configuration de création de rapports pour les jeux de données de médias payants. Vous n’avez pas besoin de recréer vous-même les dimensions, mesures, logique de recherche ou groupes de données de résumé par défaut.

Trois couches d’objets sont créées :

| Objets | Contient | Rôle |
| --- | --- | --- |
| Jeux de données de résumé | Données de performances du réseau Advertising au niveau de l’annonce publicitaire, de l’emplacement de l’expérience ou des ressources, avec des répartitions démographiques/géographiques distinctes lorsqu’elles sont prises en charge. | Permet de mesurer la diffusion, les clics, les dépenses et les résultats signalés par le réseau publicitaire |
| Jeux de données de recherche de métadonnées et d’attributs | Détails du compte, de la campagne, du groupe publicitaire, de l’annonce, de l’expérience et de la ressource ; attributs créatifs Content Analytics. | Permet de créer des rapports à l’aide de noms reconnaissables, de détails créatifs, de miniatures et d’attributs de contenu plutôt que d’utiliser des identifiants. |
| Composants et configuration de la vue de données | Dimensions, mesures, mesures calculées, champs dérivés et groupes de données de résumé. | Permet de construire des analyses Workspace sans recréer manuellement les relations entre ces jeux de données. |

L’activation des médias achetés ne connecte pas automatiquement les données des médias achetés aux commandes, aux réservations ou au chiffre d’affaires de votre site. La corrélation entre les données d’événement d’expérience et les données de médias achetés nécessite une configuration de mappage des clés de suivi et de création de rapports spécifique au client.

## Jeux de données de résumé

L’illustration ci-dessous montre comment les jeux de données de résumé sont générés lorsque vous activez le canal média payant dans Content Analytics pour un ou plusieurs de vos réseaux publicitaires. Les API appropriées des réseaux publicitaires disponibles sont utilisées pour télécharger et transformer les données d’expérience, de ressources et d’annonces en six jeux de données de résumé.

![Génération de médias payants de jeux de données de résumé](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

Le réseau publicitaire spécifique détermine les jeux de données de résumé qui sont créés. Tous les réseaux publicitaires pour lesquels vous avez configuré un connecteur source ne génèrent pas les six jeux de données de résumé possibles. Consultez le tableau ci-dessous pour obtenir un aperçu des jeux de données de résumé avec les informations suivantes :

* Nom du jeu de données de résumé, type d’événement et suffixe de composant
* Entité
* Répartitions
* Les jeux de données renseignés ![coche](/help/assets/icons2/Checkmark.svg) pour les réseaux suivants :
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat et TikTok sont dans la phase de tests limités de la publication et peuvent ne pas encore être disponibles dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication de Customer Journey Analytics, consultez [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md)
    >


* Ce que représente chaque ligne dans un jeu de données de résumé.

| Résumé du jeu de données<br/>Type d’événement<br/>Suffixe de composant | Entity<br/>Breakdown | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![](/help/assets/icons2/TikTok.svg) | Chaque ligne représente |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | <br/> | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes d’une publicité sans répartition démographique ou géographique. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Ad<br/>age, genre | ![Coche](/help/assets/icons2/Checkmark.svg) | | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes d’une publicité<br/>ventilées par âge et par sexe. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/>country, region | ![Coche](/help/assets/icons2/Checkmark.svg) | | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes d’une publicité<br/>ventilées par pays et par région. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>platform, position | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes associées<br/>à l’expérience créative d’une publicité, <br/>ventilées par plateforme et position. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Asset<br/>none | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | | | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes au niveau des ressources<br/> dans le contexte de l’annonce ou de la campagne<br/>sans répartition démographique ou géographique. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Ressource<br/>âge, sexe | ![Coche](/help/assets/icons2/Checkmark.svg) | | | | | Performances quotidiennes au niveau des ressources<br/> dans le contexte de l’annonce publicitaire/de la campagne<br/>ventilées par âge et par sexe. |

Ce tableau décrit la couverture du jeu de données, et ne garantit pas qu’un réseau particulier renseigne chaque mesure ou champ de métadonnées. Vérifiez les champs nécessaires à votre analyse. Un champ non disponible ou une répartition non prise en charge n’est pas identique à une valeur nulle mesurée pour un champ.

Le regroupement de données récapitulatives rassemble des dimensions équivalentes ; le regroupement ne totalise pas les six totaux des mesures de performances.

## Jeux de données de recherche

Des jeux de données de recherche distincts décrivent le compte, la campagne, le groupe publicitaire, la publicité, l’expérience et la ressource. Ils fournissent des noms et des métadonnées à l’aide de GUID d’entité. Il n’existe aucune association un-à-un entre les jeux de données de résumé et les six jeux de données de recherche.

Les jeux de données de recherche partagent deux blocs de création communs :

* **Objet ID d’entité** : stocke les objets compte, annonce, groupe publicitaire, ressource, campagne et expérience. Chaque objet contient une clé globale générée par Adobe et un identifiant natif de la plateforme.
* **Métadonnées de base des médias payants** : stocke des champs descriptifs courants tels que le nom, le statut, l’objectif, l’objectif d’optimisation, la stratégie d’enchères, le type de budget, les valeurs de budget, la devise, le fuseau horaire, le statut de diffusion, les dates, le réseau publicitaire, le canal, le chemin d’accès à la hiérarchie, le réseau et les identifiants de portfolio.

| Jeu de données de recherche | Contenus clés |
|---|---|
| Recherche de compte | Métadonnées au niveau du compte telles que le nom, la devise, le fuseau horaire, le statut, la limite de dépense et les dates de création |
| Recherche de campagne | Paramètres de la campagne pour le budget, la planification, le ciblage, le suivi des conversions, l’attribution, les emplacements, les objets promus, l’objectif et les ID de catalogue ou de boutique |
| Recherche de groupe publicitaire | Métadonnées du groupe publicitaire telles que le lien de la campagne, le statut, le budget, les objectifs d’optimisation et le ciblage |
| Recherche de publicité | Ajoutez des détails créatifs tels que des ressources, des variantes, des dimensions, des URL de suivi, call to action, du corps de texte, des titres, l’URL de destination, le statut de diffusion et le statut de révision |
| Recherche de ressources | Propriétés de la ressource telles que les dimensions, les détails de fichier, les propriétés d’image, les URL de média, les métadonnées d’utilisation, les métadonnées vidéo, la description, le sous-type, le titre et le type |
| Recherche d’expérience | Regroupements créatifs de niveau expérience tels que l’Experience ID, les ressources, le titre, la description et call to action |


## Composants

Une fois activé, le canal média payant Content Analytics génère également un certain nombre de composants de vue de données. Ces composants sont fournis avec un suffixe de composant pour distinguer les composants nommés similaires les uns des autres.

### Mesures

Différents réseaux publicitaires renvoient différentes répartitions de performances. Content Analytics conserve ces distinctions au lieu de traiter chaque version d’une mesure comme interchangeable.

Par exemple :

| Composant | Signification | Analyse initiale appropriée |
| --- | --- | --- |
| Clics \| Résumé de l’annonce | Clics signalés au niveau sans répartition de la publicité | Performances des campagnes ou des publicités |
| Clics \| Résumé des ressources | Clics signalés au niveau de la ressource | Performances des ressources Creative |
| Clics \| Ajouter une zone géographique | Clics provenant du rapport de géographie des annonces | Performances par pays ou région |
| Clics \| Emplacement d’expérience | Clics provenant du rapport d’emplacement d’expérience | Performances de Creative par emplacement |

Chaque composant de mesure des clics sert un contexte de création de rapports différent. Vous ne pouvez pas totaliser ces composants de mesure dans un total général. La même activité publicitaire sous-jacente peut être représentée dans plusieurs jeux de données de résumé.

### Dimensions

Chaque jeu de données de résumé contient des identifiants et des GUID. L’identifiant est l’identité (pour le compte, la campagne, le groupe publicitaire, la publicité, l’expérience et la ressource) fournie par le réseau publicitaire et est unique **dans** les données du réseau publicitaire. Le GUID est une identité fournie par Adobe (pour le compte, la campagne, le groupe publicitaire, la publicité, l’expérience et la ressource) et est unique **sur** les réseaux publicitaires. Les identifiants et les GUID sont utilisés pour rechercher les noms et métadonnées correspondants.

### Champs dérivés

Les champs dérivés font partie de la configuration de création de rapports automatique. Les champs dérivés traduisent les identifiants en noms et en métadonnées, exposent les attributs créatifs et prennent en charge les dimensions équivalentes utilisées dans les sources de création de rapports. Ils ne créent pas d’activité publicitaire supplémentaire et n’attribuent pas automatiquement de conversion de site web.

Utilisez la même répartition pour les mesures d’une analyse et les dimensions prises en charge par cette répartition. Gardez à l’esprit que les totaux démographiques et géographiques ne sont pas nécessairement égaux aux totaux sans répartition pour un réseau publicitaire et n’impliquent pas un échec d’ingestion.

## Rapports et analyses

Une fois que vous avez terminé la configuration et l’ingestion des médias payants Content Analytics, vous pouvez commencer à créer des rapports et des analyses. Consultez le tableau ci-dessous pour consulter quelques exemples. Utilisez les dimensions regroupées canoniques, le cas échéant, et choisissez les mesures à partir du niveau de création de rapports correspondant.

| Question commerciale | Niveau de départ | Lignes et répartitions | Mesures de démarrage | Limite importante |
| --- | --- | --- | --- | --- |
| Quelles sont les performances de mes campagnes et publicités ? | Résumé de la publicité | Nom de la campagne, nom du groupe publicitaire, nom de l’annonce ; éventuellement, nom du réseau publicitaire et nom du compte | Impressions \| Résumé de l’annonce, Clics \| Résumé de l’annonce, Dépenses \| Résumé de l’annonce, CTR et CPC correspondants | Utiliser un niveau pour les totaux de diffusion/dépenses ; valider la devise avant de combiner les comptes |
| Quelles ressources créatives rencontrent le plus de succès ? | Résumé des ressources | Nom de la ressource (média payant), identité de la ressource ; éventuellement, réseau publicitaire | Impressions \| Résumé Des Ressources, Clics \| Résumé Des Ressources, Taux De Clics Publicitaires \| Résumé Des Ressources | Il s’agit des performances des ressources signalées par le réseau, et non d’une preuve d’une conversion ultérieure sur site |
| Quelles caractéristiques d’image sont associées aux performances ? | Résumé des ressources | Balises de ressources, objets de ressource, catégories de personnes associées aux ressources, scènes de ressource ou autres attributs de ressource disponibles | Impressions, clics et taux de clics du résumé des ressources | L’extraction des attributs doit être disponible ; les catégories d’attributs à plusieurs valeurs peuvent se chevaucher |
| Quelles sont les caractéristiques de messagerie associées aux performances payantes ? | Emplacement de l’expérience | Mots-clés d’expérience, tonalités d’expérience, stratégies de persuasion d’expérience ou autres attributs d’expérience disponibles ; éventuellement Platform et positionnement | Impressions \| Emplacement d’expérience, Clics \| Emplacement d’expérience, CTR correspondant | Requiert des attributs d’expérience renseignés ; les résultats sont spécifiques à l’emplacement et décrivent l’association, et non l’impact causal |
| Quels emplacements sont les plus performants ? | Emplacement de l’expérience | Nom De L’Expérience, Plateforme, Emplacement | Impressions \| Emplacement d’expérience, Clics \| Emplacement d’expérience, CTR correspondant | Les définitions d’emplacement et les valeurs disponibles varient selon le réseau publicitaire |
| Comment se comparent les annonces/ressources/expériences Meta et Google ? | Résumé de l’annonce publicitaire, Résumé des ressources ou Emplacement d’expérience, choisis pour la question | Ajouter un réseau avec la dimension de campagne, de ressource ou d’expérience appropriée | Même niveau et définition de mesure pour les deux réseaux | Comparez uniquement les champs renseignés par les deux réseaux ; Google ne renseigne pas les trois résumés démographiques/géographiques dans ce modèle |

Ces rapports peuvent révéler des associations entre les attributs créatifs et les performances, sans prouver qu’un attribut a provoqué un résultat.

Évitez les combinaisons incompatibles : le nom de ressource (médias payants) avec les mesures Résumé de l’annonce ne remplace pas un rapport de ressources. Utilisez les mesures Résumé des ressources pour l’analyse des ressources et les mesures Géographie des annonces pour l’analyse des régions. Les cellules vides ou nulles d&#39;un appariement incompatible ne doivent pas être interprétées comme une preuve d&#39;absence d&#39;activité.

### Exemples

Vous trouverez ci-dessous des exemples de création de rapports et d’analyse de la performance des médias achetés et de combinaison des données d’expérience et de ressources Content Analytics avec les données de médias achetés.

#### Performances des campagnes publicitaires

Vous souhaitez générer des rapports sur les performances de la campagne au niveau des annonces. Dans Analysis Workspace, utilisez Nom de la campagne comme dimension (lignes) et les mesures comme indiqué dans le tableau ci-dessous. Chaque mesure comporte le même suffixe de composant.

| Mesures | Niveau de reporting |
| --- | --- |
| Impressions | Résumé de la publicité |
| Clics | Résumé de la publicité |
| Dépense | Résumé de la publicité |
| Taux De Clic Publicitaire | Résumé de la publicité |
| Coût par clic | Résumé de la publicité |

Vous pouvez éventuellement ventiler le nom de la campagne par nom d’annonce, mais conserver les cinq colonnes au niveau du résumé de l’annonce.

Pour examiner des ressources individuelles, utilisez un tableau distinct avec le Nom de la ressource (Média payant) et les colonnes Résumé de la ressource correspondantes. Ne pas additionner les totaux des deux tables.

#### Identification des publicités les plus performantes

Vous souhaitez savoir où vos publicités Meta ont les meilleures performances ?

Pour effectuer des recherches, utilisez des répartitions supplémentaires pour la géographie et les données démographiques. Utilisez le Nom de la campagne ou le Nom de l’annonce comme dimension et utilisez les mesures comme indiqué dans le tableau ci-dessous. Chaque mesure comporte le même suffixe de composant.

| Mesures | Niveau de reporting |
| --- | --- |
| Impressions | Ajouter géo |
| Clics | Ajouter géo |
| Dépense | Résumé de la publicité |
| Taux De Clic Publicitaire | Ajouter géo |
| Coût par clic | Résumé de la publicité |


#### Joindre des données de média payantes à des données d’événement d’expérience

Rejoignez la performance des médias payants avec des données comportementales sur site pour comprendre comment les campagnes et les annonces sont associées à l’engagement, aux conversions et aux recettes des sites web. Par exemple, comparez les clics et les dépenses publicitaires du réseau avec les commandes attribuées aux visites de la même campagne.

Pour configurer ces rapports, incluez les jeux de données de résumé de média payant et votre jeu de données d’événement sur site dans la même connexion Customer Journey Analytics. Capturez des identifiants de campagne, d’annonce publicitaire ou de ressource pris en charge à partir des paramètres d’URL de page de destination ou de champs d’événement existants. Utilisez les champs dérivés selon les besoins pour analyser et mapper ces valeurs sur les identifiants de médias achetés correspondants, en préservant le contexte réseau et de compte requis. Conserver les identifiants sous forme de chaînes. Pour associer les dimensions Événement et Résumé correspondantes, configurez un Groupe de données Résumé dans la vue de données. L’activation du canal Média payant ne configure pas automatiquement ce suivi et ce mappage d’URL spécifiques à l’implémentation.


| Option de tracking | Considérations |
|---|---|
| Meta Ads | Configurez les paramètres d’URL de destination à l’aide d’identifiants dynamiques tels que `campaign.id`, `adset.id` et `ad.id`, le cas échéant. Capturez les valeurs résolues sur votre site web. L’activation du connecteur n’ajoute pas automatiquement ces paramètres à vos URL de publicité. |
| Google Ads | |
| Ressources individuelles | La création de rapports au niveau des ressources pour les résultats en aval nécessite un identifiant capturé qui mappe à la ressource spécifique associée au clic. Un paramètre d’URL personnalisé peut prendre en charge cette fonction lorsque le format d’annonce autorise le suivi spécifique aux ressources. Un identifiant d’annonce publicitaire ne peut pas distinguer plusieurs ressources dans une annonce publicitaire et un paramètre de ressource statique appliqué à une annonce publicitaire multi-ressources entière n’identifie pas la ressource associée au clic. |

Dans Analysis Workspace, utilisez les mesures **[!UICONTROL Résumé de l’annonce]** pour les comparaisons de campagnes ou d’annonces et les mesures **[!UICONTROL Résumé des ressources]** pour les comparaisons de ressources prises en charge. Appliquez un modèle d’attribution et un intervalle de recherche en amont aux mesures de conversion sur site qui reflètent votre question de création de rapports.

Tenez compte des éléments suivants :

* Les données de médias payantes sont des données récapitulatives agrégées sans ID de personne. Le comportement sur site correspond aux données d’événement.
* Le regroupement de dimensions correspondantes prend en charge le compte rendu des performances sur ces sources, mais ne correspond pas aux conversions réseau et individuelles en conversions de sites web ou n’effectue pas de regroupement au niveau de la personne.
* La comparaison montre une association, et non un effet élévateur causal.
* Les résultats peuvent différer en raison des définitions de conversion, des fenêtres d’attribution, des conversions d’affichage publicitaire ou modélisées, du consentement et des dates ou fuseaux horaires de création de rapports.
* Validez la source des visites balisées par la campagne lorsque les paramètres de tracking sont réutilisés sur l’ensemble des canaux.


#### Comparer les performances de la campagne avec les commandes sur site

Une URL de page de destination peut contenir plusieurs paramètres de tracking. Dans cet exemple, l’identifiant de campagne dans `utm_id` est utilisé pour comparer les dépenses de campagne aux commandes de site web.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

Paramètre utilisé pour cette comparaison : `utm_id=120218706543980215`. Les autres paramètres décrivent la source, le support et le libellé de la campagne, mais ne sont pas utilisés comme champ correspondant utilisé dans cet exemple.

Si l’URL est capturée dans les données d’événement de site web et que les jeux de données d’événement de site web et de médias achetés font partie de la même connexion Customer Journey Analytics :

1. Identifiez la campagne. Utilisez un champ dérivé pour lire le `utm_id` à partir de l’URL et mapper sa valeur sur l’identifiant de campagne correspondant dans les données de médias achetés.
1. Regroupez les dimensions correspondantes. Dans la vue de données, ajoutez la dimension de campagne du site web à la `Summary Data Group` de la dimension de campagne payante, en conservant tous les membres existants.
1. Comparez les dépenses et les commandes. Dans Analysis Workspace, utilisez la dimension de campagne groupée comme lignes d’un tableau à structure libre. Ajoutez `Ad Summary` dépenses et les `Orders` de site web sous forme de colonnes. Définissez le modèle d’attribution et l’intervalle de recherche en amont pour `Orders`.


Le tableau à structure libre affiche les dépenses liées au réseau publicitaire ainsi que les commandes de site web attribuées à chaque campagne. Deux campagnes avec des dépenses publicitaires similaires ont des nombres différents d’actions de site web attribuées en aval. Utilisez cette comparaison pour identifier les campagnes et les expériences de page de destination à des fins d’enquête ou de test plus approfondi, plutôt que d’évaluer les performances à partir des seules mesures publicitaires.

L’exemple utilise un identifiant de campagne, mais la même approche peut utiliser des identifiants de groupe publicitaire, d’annonce ou de ressource lors de la capture de valeurs correspondantes. Les attributs Content Analytics, tels que **[!UICONTROL Couleurs de premier plan des ressources]**, vous permettent de comparer les caractéristiques créatives aux performances des médias achetés. Avec le suivi spécifique aux ressources et les dimensions d’attributs correspondantes configurées sur les deux sources, vous pouvez étendre cette comparaison aux commandes de sites web attribuées et utiliser les résultats pour guider les tests créatifs.

#### Combiner les performances des ressources avec les données web

Si vous souhaitez générer des rapports et des analyses sur les performances des ressources liées à vos investissements dans les médias achetés, pensez à ajouter un paramètre UTM de ressource spécifique dans la configuration des médias achetés de votre réseau publicitaire. Par exemple, en plus des paramètres dynamiques standard tels que s`ite_source_name`, `campaign.id`, `adset.id` ou `placement`, ajoutez des paramètres personnalisés statiques tels que `aca_asset_id=999999`.

Ce paramètre personnalisé est ajouté à l’URL de votre page de destination. Par exemple : https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&aca_id_2=8888888&utm_medium=paid&utm_source=fb&utm_id=120241705099830539&utm_term=120241705099840539&utm_campaign=120241705099830539

Vous disposez désormais d’une relation entre une ressource sur une page et vos données de médias achetés. Utilisez cette relation dans Analysis Workspace pour voir comment les métadonnées des ressources Content Analytics (par exemple, **[!UICONTROL Couleurs de premier plan des ressources]**) contribuent au succès des campagnes de médias achetés.


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
