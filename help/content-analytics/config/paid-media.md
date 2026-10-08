---
title: Configuration automatique des médias payants Content Analytics
description: Découvrez la configuration automatique des jeux de données, de la connexion, des vues de données, etc.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: 684fef6a5e007d6dabe6518d7c7ec93a41dc6cdd
workflow-type: tm+mt
source-wordcount: '2179'
ht-degree: 3%
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

![Génération de médias payants de jeux de données de résumé](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

Les jeux de données de résumé créés sont déterminés par le réseau publicitaire spécifique. Tous les réseaux publicitaires pour lesquels vous avez configuré un connecteur source ne génèrent pas les six jeux de données de résumé possibles. Consultez le tableau ci-dessous pour obtenir un aperçu des jeux de données de résumé avec les informations suivantes :

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


* ce que représente chaque ligne dans un jeu de données de résumé.

| Résumé du jeu de données<br/>Type d’événement<br/>Suffixe de composant | Entité | Répartition | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![](/help/assets/icons2/TikTok.svg) | Chaque ligne représente |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Publicité | aucun | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes d’une publicité sans répartition démographique ou géographique. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Publicité | âge, sexe | ![Coche](/help/assets/icons2/Checkmark.svg) | | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | La performance quotidienne d&#39;une publicité est ventilée par âge et par sexe. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Publicité | pays, région | ![Coche](/help/assets/icons2/Checkmark.svg) | | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | La performance quotidienne d’une publicité, ventilée par pays et par région. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Expérience | plate-forme, position | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes associées à l’expérience créative d’une publicité, ventilées par plateforme et position. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Ressource | aucun | ![Coche](/help/assets/icons2/Checkmark.svg) | ![Coche](/help/assets/icons2/Checkmark.svg) | | | ![Coche](/help/assets/icons2/Checkmark.svg) | Performances quotidiennes au niveau des ressources dans son contexte d’annonce/de campagne, sans répartition démographique ou géographique. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Ressource | âge, sexe | ![Coche](/help/assets/icons2/Checkmark.svg) | | | | | Performances quotidiennes au niveau des ressources dans son contexte d’annonce publicitaire/de campagne, ventilées par âge et par sexe. |


Ce tableau décrit la couverture du jeu de données, et ne garantit pas que chaque mesure ou champ de métadonnées est renseigné par un réseau particulier. Vérifiez les champs nécessaires à votre analyse. Un champ non disponible ou une répartition non prise en charge n’est pas identique à une valeur nulle mesurée pour un champ.

Des jeux de données de recherche distincts décrivent le compte, la campagne, le groupe publicitaire, la publicité, l’expérience et la ressource. Ils fournissent des noms et des métadonnées à l’aide de GUID d’entité. Il n’existe aucune association un-à-un entre les jeux de données de résumé et les six jeux de données de recherche.

Le regroupement de données récapitulatives rassemble des dimensions équivalentes ; le regroupement ne totalise pas les six totaux des mesures de performances.

## Composants

Une fois activé, le canal média payant Content Analytics génère également un certain nombre de composants de vue de données. Ces composants sont fournis avec un suffixe de composant pour séparer les composants nommés similaires les uns des autres.

### Mesures

Différents réseaux publicitaires renvoient différentes répartitions de performances. Content Analytics conserve ces distinctions au lieu de traiter chaque version d’une mesure comme interchangeable.

Par exemple :

| Composant | Signification | Analyse initiale appropriée |
| --- | --- | --- |
| Clics \| Résumé de l’annonce | Clics signalés au niveau sans répartition de la publicité | Performances des campagnes ou des publicités |
| Clics \| Résumé des ressources | Clics signalés au niveau de la ressource | Performances des ressources Creative |
| Clics \| Ajouter une zone géographique | Clics provenant du rapport de géographie des annonces | Performances par pays ou région |
| Clics \| Emplacement d’expérience | Clics provenant du rapport d’emplacement d’expérience | Performances de Creative par emplacement |

Chaque composant de mesure des clics sert un contexte de création de rapports différent. Vous ne pouvez pas simplement totaliser ces composants de mesure en un total général. La même activité publicitaire sous-jacente peut être représentée dans plusieurs jeux de données de résumé.

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

### Exemple de performances de campagne publicitaire

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

### Exemple de publicités présentant les meilleures performances réseau

Vous souhaitez savoir où vos publicités Meta ont les meilleures performances ?

Pour effectuer des recherches, utilisez des répartitions supplémentaires pour la géographie et les données démographiques. Utilisez le Nom de la campagne ou le Nom de l’annonce comme dimension et utilisez les mesures comme indiqué dans le tableau ci-dessous. Chaque mesure comporte le même suffixe de composant.

| Mesures | Niveau de reporting |
| --- | --- |
| Impressions | Ajouter géo |
| Clics | Ajouter géo |
| Dépense | Résumé de la publicité |
| Taux De Clic Publicitaire | Ajouter géo |
| Coût par clic | Résumé de la publicité |


### Corrélation des données de médias achetés avec les données d’événement d’expérience

Combinez la performance des médias payants avec les données comportementales sur site pour comprendre comment les campagnes et les annonces sont associées à l’engagement, aux conversions et au chiffre d’affaires du site web. Par exemple, comparez les clics et les dépenses publicitaires du réseau avec les commandes attribuées aux visites de la même campagne.

Pour configurer ces rapports, incluez les jeux de données de résumé de média payant et votre jeu de données d’événement sur site dans la même connexion Customer Journey Analytics. Capturez des identifiants de campagne, d’annonce publicitaire ou de ressource pris en charge à partir des paramètres d’URL de page de destination ou de champs d’événement existants. Utilisez les champs dérivés selon les besoins pour analyser et mapper ces valeurs sur les identifiants de médias achetés correspondants, en préservant le contexte réseau et de compte requis. Conserver les identifiants sous forme de chaînes. Configurez un groupe de données de résumé dans la vue de données pour associer l&#39;événement correspondant et les dimensions de résumé. L’activation du canal Média payant ne configure pas automatiquement ce suivi et ce mappage d’URL spécifiques à l’implémentation.


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
* Validez la source des visites balisées par la campagne, en particulier lorsque les paramètres de tracking sont réutilisés sur plusieurs canaux.


### Exemple de comparaison des performances d&#39;une campagne avec des commandes sur site

Une URL de page de destination peut contenir plusieurs paramètres de tracking. Dans cet exemple, nous utilisons l’identifiant de campagne dans `utm_id` pour comparer les dépenses de campagne aux commandes de site web.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

Paramètre utilisé pour cette comparaison : `utm_id=120218706543980215`. Les autres paramètres décrivent la source, le support et le libellé de la campagne, mais ne sont pas utilisés comme champ correspondant utilisé dans cet exemple.

Si l’URL est capturée dans les données d’événement de site web et que les jeux de données d’événement de site web et de médias achetés font partie de la même connexion Customer Journey Analytics :

1. Identifiez la campagne. Utilisez un champ dérivé pour lire le `utm_id` à partir de l’URL et mapper sa valeur sur l’identifiant de campagne correspondant dans les données de médias achetés.
1. Regroupez les dimensions correspondantes. Dans la vue de données, ajoutez la dimension de campagne du site web à la `Summary Data Group` de la dimension de campagne payante, en conservant tous les membres existants.
1. Comparez les dépenses et les commandes. Dans Analysis Workspace, utilisez la dimension de campagne groupée comme lignes d’un tableau à structure libre. Ajoutez `Ad Summary` dépenses et les `Orders` de site web sous forme de colonnes. Définissez le modèle d’attribution et l’intervalle de recherche en amont pour `Orders`.


Le tableau présente les dépenses publicitaires réseau ainsi que les commandes de sites web attribuées à chaque campagne. Deux campagnes avec des dépenses publicitaires similaires peuvent avoir des nombres différents d’actions de site web attribuées en aval. Utilisez cette comparaison pour identifier les campagnes et les expériences de page de destination à des fins d’enquête ou de test plus approfondi, plutôt que d’évaluer les performances à partir des seules mesures publicitaires.

L’exemple utilise un identifiant de campagne, mais la même approche peut utiliser des identifiants de groupe publicitaire, d’annonce ou de ressource lors de la capture de valeurs correspondantes. Les attributs Content Analytics, tels que **[!UICONTROL Couleurs de premier plan des ressources]**, vous permettent de comparer les caractéristiques créatives aux performances des médias achetés. Avec le suivi spécifique aux ressources et les dimensions d’attributs correspondantes configurées sur les deux sources, vous pouvez étendre cette comparaison aux commandes de sites web attribuées et utiliser les résultats pour guider les tests créatifs.
