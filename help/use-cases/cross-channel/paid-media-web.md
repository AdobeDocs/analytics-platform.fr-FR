---
title: Joindre Des Données De Médias Payants À Des Données Web Dans Customer Journey Analytics
description: Rejoignez les données de résumé des médias achetés avec les événements de site web dans Adobe Customer Journey Analytics pour comparer les dépenses publicitaires, les clics, les commandes, le chiffre d’affaires et le retour sur dépenses publicitaires.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
role: Admin
source-git-commit: 3fc129c2eeb5fd86e8ef4d885a4682dd819fc481
workflow-type: tm+mt
source-wordcount: '3907'
ht-degree: 3%
---
# Joindre des données de média payantes à des données web

Ce guide de cas d’utilisation illustre comment joindre des données de résumé de médias achetés à des données d’événement comportemental de site web dans [!DNL Adobe Customer Journey Analytics].


La connexion de vos comptes publicitaires (Meta, Google Ads et autres) à Experience Platform fournit des données de résumé des médias achetés dans Customer Journey Analytics : impressions, clics, dépenses quotidiens et conversions signalées par le réseau publicitaire par compte, campagne, groupe publicitaire, publicité, expérience et ressource. Avec Customer Journey Analytics, vous collectez vos propres données comportementales d’événement sur site avec le SDK web : pages vues, commandes, chiffre d’affaires.

Lorsque vous joignez les deux types de données dans un seul tableau à structure libre Workspace, vous pouvez comparer les performances publicitaires à l’activité sur votre site web. Utilisez des identifiants de campagne, de groupe publicitaire et d’annonce publicitaire partagés pour créer des rapports sur les impressions, les clics et les dépenses avec les débarquements, commandes et recettes payés en [!DNL Analysis Workspace].

| Source de données | Exemples de mesures |
|---|---|
| Données de résumé du média payant | Les impressions, clics, dépenses, conversions et valeurs de conversion signalés par le réseau publicitaire. |
| Événements comportementaux de site web | Pages de destination payantes, pages vues, commandes et recettes mesurées sur votre site web |
| Mesures calculées | Taux de pages de destination, taux de conversion web, retour sur dépenses publicitaires, coût par commande web et écart de conversion réseau/web |

La combinaison de ces deux types de données vous permet de comparer les données de pré-clic (à partir de vos publicités) et de post-clic (à partir de votre site web).

Ce guide couvre les scénarios basés sur les connexions gérées par [!DNL Adobe Content Analytics] configurations et les connexions que vous configurez vous-même.

## Fonctionnement

Le diagramme ci-dessous illustre la manière dont les données de résumé des médias achetés et les données d’événement comportemental de site web sont ingérées par le biais d’une connexion Customer Journey Analytics.

La vue de données est chargée de l’analyse et de l’alignement des données. Vous pouvez ainsi utiliser Workspace pour créer des rapports appropriés sur les données.

![Jointures de médias payants](./assets/paid-media-web-join.png){zoomable="yes"}

Les jeux de données de résumé de médias payants contiennent des mesures quotidiennes sans ID de personne. Les jeux de données d’événements de site web contiennent des événements comportementaux horodatés et un identifiant de personne. Un groupe de données de synthèse associe les dimensions de ces jeux de données de sorte que des valeurs de dimension égales apparaissent dans la même ligne de rapport.

>[!IMPORTANT]
>
>Cette jointure aligne les données récapitulatives agrégées et les événements web pour le compte rendu des performances. Il ne lie pas une impression ou un clic publicitaire à une personne individuelle. Les conversions réseau publicitaire conservent la méthodologie de création de rapports du réseau. Les commandes et les recettes de site web utilisent les paramètres d’attribution que vous configurez dans ce guide.

## Comprendre la jointure par reporting

Vous ne pouvez adhérer qu’à des niveaux dont les ID apparaissent dans les URL de votre page de destination ou dans les champs d’événement existants. Par exemple, le balisage des campagnes uniquement prend en charge les rapports de campagne, mais pas les rapports au niveau des annonces. Les jointures au niveau de l’expérience et au niveau des ressources nécessitent des paramètres d’URL supplémentaires et sortent du cadre de ce guide.

Voir [Données récapitulatives](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/summary-data) et [Paramètres des composants du groupe de données récapitulatives](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/summary-data-group) pour référence.

### Choisir la clé de jointure

Les jeux de données de médias payants fournissent à la fois des identifiants réseau bruts et des identifiants globaux uniques (GUID) générés par Adobe.

| Identifiant | Exemple | Rôle |
|---|---|---|
| Identifiant réseau | `123456789` de l’identifiant de campagne | Faire correspondre un identifiant capturé à partir d’une URL de page de destination à une dimension de résumé de média payant |
| GUID | `meta_111111111_123456789` | Identifier une entité de média payant à l’aide de la hiérarchie de réseau, de compte et d’entité |

La structure du GUID est `{adNetwork}_{accountID}[_{campaignID}[_{adGroupID}[_{adID}]]]`. Les composants de médias payants gérés par [!DNL Adobe Content Analytics] utilisent ces GUID.

Ce guide utilise des identifiants de réseau pour les jointures web, car les macros de campagne, de groupe publicitaire et d&#39;URL de publicité ne fournissent pas toutes les informations nécessaires pour reconstruire un GUID. Utilisez les champs de résumé suivants :

| Niveau de reporting | Champ ID réseau | Champ GUID |
|---|---|---|
| Campagne | `paidMedia.campaignID` | `paidMedia.campaignGUID` |
| Groupe publicitaire | `paidMedia.adGroupID` | `paidMedia.adGroupGUID` |
| Publicité | `paidMedia.adID` | `paidMedia.adGUID` |

Le champ réseau est `paidMedia.adNetwork`. Les exemples de valeurs incluent `meta` et `google_ads`. Les sorties de champ dérivé doivent correspondre exactement aux valeurs de vos jeux de données.

>[!NOTE]
>
>Un groupe de données de synthèse correspond aux valeurs de dimension, et non à une combinaison de toutes les dimensions de votre tableau. Vérifiez que les identifiants sélectionnés identifient les entités sans ambiguïté sur les comptes et réseaux sur lesquels vous établissez des rapports. Les groupes basés sur des noms peuvent combiner des entités distinctes qui partagent un nom.

## Conditions préalables

Vérifiez que vous disposez des éléments suivants :

* [!DNL Customer Journey Analytics] Select ou une version ultérieure, avec accès aux fonctions de champ dérivé utilisées ici : [Analyse d’URL](/help/data-views/derived-fields/derived-fields.md#url-parse), [Casse quand](/help/data-views/derived-fields/derived-fields.md#case-when), [Remplacement d’expression régulière](/help/data-views/derived-fields/derived-fields.md#regex-replace) et, pour l’enrichissement du nom, [Recherche](/help/data-views/derived-fields/derived-fields.md#lookup).
* [!DNL Adobe Experience Platform] des autorisations pour gérer les schémas, les jeux de données et les flux de données dans le sandbox cible, ainsi que l’accès aux jeux de données et à Query Service à des fins de vérification.
* [!DNL Customer Journey Analytics] l’autorisation de modifier la connexion cible et la vue de données.
* Connecteurs source de médias payants configurés dans le même sandbox et ingérant des jeux de données de résumé et de recherche. Pour obtenir un exemple de connecteur, consultez [Source Meta Ads](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads).
* Événements de site web qui capturent l’URL complète de la page de destination, y compris sa chaîne de requête, ou des champs équivalents contenant les identifiants de réseau.


### Balisage des publicités

Identifiez les paramètres de requête qui contiennent votre campagne, votre groupe publicitaire et vos identifiants publicitaires. Le balisage existant basé sur les identifiants peut être utilisé sans modification des plateformes publicitaires.

| Modèle de balisage | Paramètre de la campagne | Paramètre du groupe publicitaire | Ajouter un paramètre |
|---|---|---|---|
| Meta ID dans l’URL du site web | <code>campaign_id={{campaign.id}}</code> | <code>adset_id={{adset.id}}</code> | <code>ad_id={{ad.id}}</code> |
| Identifiants Meta dans les paramètres UTM | <code>utm_campaign={{campaign.id}}</code> | <code>utm_term={{adset.id}}</code> | <code>utm_content={{ad.id}}</code> |
| Identifiants Google Ads dans les paramètres UTM | <code>utm_campaign={campaignid}</code> | <code>utm_term={adgroupid}</code> | <code>utm_content={creative}</code> |

Pour le balisage UTM de Meta, une valeur source telle que `utm_source=fb` peut identifier le réseau. Pour le balisage UTM Google Ads, utilisez une valeur source telle que `utm_source=google`.

Certaines intégrations [!DNL Adobe Advertising] utilisent une valeur `s_kwcid` avec cette disposition :

```text
AL!<id>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}!{campaignid}!{adgroupid}
```

Les règles d’analyse présentées plus loin dans ce guide s’appliquent uniquement à cette disposition. Inspectez les URL de destination réelles avant de les utiliser.

Si vous n’avez pas accès aux plateformes publicitaires, examinez les URL de destination dans votre jeu de données web. Vous pouvez également inspecter ces champs de recherche de médias achetés :

* Recherche de compte Google Ads : `additionalDetails` entrées nommées `google_ads_tracking_url_template` et `google_ads_final_url_suffix`.
* Recherche d’annonces Meta : `paidMedia.adDetails.creative.paidMediaCreative.destinationURL`.

Les macros des URL de destination stockées peuvent être codées en pourcentage. Validez les identifiants développés dans des événements de site web réels plutôt que de supposer qu’une URL stockée représente l’URL de destination finale.

>[!IMPORTANT]
>
>Les noms de campagne, tels que `utm_campaign=fall_sale`, ne correspondent pas aux identifiants de campagne. Rejoindre uniquement à des niveaux contenant des identifiants réels. En l’absence d’ID, collaborez avec votre équipe des opérations publicitaires pour mettre à jour le balisage pour le trafic futur. Cette configuration ne peut pas reconstruire les ID manquants pour les visites historiques.

### Point de départ

Ouvrez la vue de données que vous prévoyez d’utiliser et examinez les composants pour déterminer le point de départ.

| | Point de départ | Configuration existante | Étapes à suivre |
|---|---|---|---|
| A | Content Analytics avec web ou mobile et média payant | Jeux de données et composants de médias payants, ainsi que les jeux de données d’événement et de recherche Content Analytics | Ajoutez le jeu de données d’événement de votre site web si nécessaire, puis configurez les champs dérivés du web et les groupes de génération de rapports |
| B | Content Analytics avec médias achetés uniquement | Jeux de données et composants de médias payants ; les jeux de données de recherche de contenu partagé peuvent également être présents | Ajoutez le jeu de données d’événement de votre site web, puis configurez les champs dérivés du web et les groupes de rapports |
| C | Médias payants sans approvisionnement de Content Analytics | Les jeux de données de médias achetés existent dans Experience Platform, mais la connexion et la vue de données ne contiennent pas la configuration de médias achetés | Ajoutez le site web et les jeux de données de médias achetés, puis créez les composants web et de médias achetés |
| D | Content Analytics sans média payant | Composants Content Analytics uniquement | Activez le canal de média payant dans la configuration Content Analytics, puis suivez le chemin d’accès existing-configuration |

Ne supprimez ou ne modifiez pas les jeux de données ou les composants en lecture seule configurés par le système lors de l’extension d’une connexion gérée par Content Analytics.

## Collecter des événements comportementaux de site web

Ignorez la création du schéma, du jeu de données et du flux de données si votre site web envoie déjà les événements requis à un jeu de données utilisé dans Customer Journey Analytics. Vérifiez que `web.webPageDetails.URL` inclut la chaîne de requête de la page de destination.

### Création du schéma et du jeu de données

1. Dans Experience Platform, sélectionnez le sandbox cible.
1. Accédez à **[!UICONTROL Gestion des données]** > **[!UICONTROL Schémas]**, puis sélectionnez **[!UICONTROL Créer un schéma]**.
1. Choisissez **[!UICONTROL Manuel]** et la classe `XDM ExperienceEvent`.
1. Nommez le schéma, par exemple `Web Behavioral Events`.
1. Ajoutez les groupes de champs nécessaires à votre implémentation.

   | Groupe de champs | Données requises |
   |---|---|
   | ExperienceEvent AEP Web SDK | URL de page, pages vues, référent et autre contexte web |
   | Informations commerciales | Nombre d’achats, valeur de commande, devise, ID d’achat et détails du produit |
   | Détails marketing de la campagne, facultatif | Codes de suivi si votre implémentation les capture séparément |
   | IdentityMap, s’il n’est pas déjà présent | Identifiant de personne, tel qu’ECID |

1. Enregistrez le schéma. L’activation du profil n’est pas requise pour ce cas d’utilisation de création de rapports.
1. Accédez à **[!UICONTROL Gestion des données]** > **[!UICONTROL Jeux de données]** > **[!UICONTROL Créer un jeu de données]** > **[!UICONTROL Créer un jeu de données à partir d’un schéma]**.
1. Sélectionnez le schéma et créez un jeu de données nommé, par exemple, `Web Behavioral Events`. Laissez le **[!UICONTROL Profil]** désactivé, sauf si un autre cas d’utilisation le requiert.

### Configuration du flux de données et de Web SDK

1. Accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Flux de données]** > **[!UICONTROL Nouveau flux de données]**.
1. Nommez le flux de données et sélectionnez votre schéma d’événement comme schéma de mappage.
1. Enregistrez, puis sélectionnez **[!UICONTROL Ajouter un service]** > **[!UICONTROL Adobe Experience Platform]**.
1. Sélectionnez le sandbox et le jeu de données d’événement, puis **[!UICONTROL Enregistrer]**.
1. Utilisez l’identifiant du flux de données pour configurer [Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview).

Capturez les éléments suivants :

* Capturez une page vue sur chaque page, avec l’URL complète dans `web.webPageDetails.URL` et `web.webPageDetails.pageViews.value` définie sur `1`.
* Événements d’achat avec `commerce.purchases.value` défini sur `1`, plus `commerce.order.priceTotal`, `commerce.order.currencyCode` et `commerce.order.purchaseID`.
* Identifiant de personne adapté à votre connexion Customer Journey Analytics.

Vous n’avez pas besoin d’analyser les paramètres UTM dans le code du site web. Les champs dérivés de ce guide analysent les URL au moment du rapport. Si votre implémentation capture déjà les identifiants dans les champs dédiés, utilisez plutôt ces champs.

### Vérifier l’ingestion

Vérifiez que l’activité du jeu de données a bien été ingérée. Dans Query Service, exécutez la requête suivante, en remplaçant `web_behavioral_events` par le nom de la table SQL de votre jeu de données :

```sql
SELECT timestamp, eventType, web.webPageDetails.URL
FROM web_behavioral_events
WHERE web.webPageDetails.URL RLIKE '[?&](campaign_id|utm_campaign|s_kwcid)='
ORDER BY timestamp DESC
LIMIT 20;
```

Vérifiez que les URL renvoyées contiennent des identifiants réseau étendus. S’il existe du trafic payant mais que la requête ne renvoie aucune ligne, examinez les URL de destination récentes et adaptez le modèle de paramètre à votre balisage.

## Configurer la connexion

Pour ingérer le jeu de données d’événement web dans Customer Journey Analytics, vous devez ajouter le jeu de données à la connexion appropriée. Cela permet de s’assurer que les événements comportementaux web sont disponibles avec vos jeux de données de médias payants pour analyse.

### Ajouter le jeu de données d’événement de site web

1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Gestion des données]** > **[!UICONTROL Connexions]**.
1. Modifiez la connexion qui contient vos jeux de données de médias achetés.
1. Sélectionnez **[!UICONTROL Ajouter des jeux de données]** et choisissez le jeu de données d’événement de site web.
1. Configurez le jeu de données :

   | Paramètre | Valeur |
   |---|---|
   | ID de personne | `identityMap` avec l’espace de noms ECID ou le champ d’ID de personne de votre implémentation |
   | Date et heure | `timestamp` |
   | Type de source de données | Données web |
   | Importer toutes les nouvelles données | Activé |
   | Renvoyer toutes les données existantes | Activé pour la période historique dont vous avez besoin |

1. Ajoutez le jeu de données et enregistrez la connexion.

### Ajouter des jeux de données de médias achetés s’ils ne sont pas déjà configurés

>[!IMPORTANT]
>
>Ignorez cette section pour les connexions pour lesquelles Content Analytics gère les jeux de données de médias achetés.


Ajoutez au moins le résumé de l’annonce publicitaire pour médias payants et les jeux de données Compte de médias payants, Campagne médiatique payante, Groupe d’annonces pour médias payants et Recherche d’annonces publicitaires pour médias payants .

| Jeu de données | Type | Configuration de la clé |
|---|---|---|
| Résumé de l’annonce publicitaire médias payants | Résumé | Utilisez la configuration d’horodatage quotidien du schéma ; activez l’importation de nouvelles données et le renvoi requis. |
| Recherche de compte média payant | Recherche | Clé : `paidMedia.accountGUID` ; champ correspondant dans le résumé publicitaire : `paidMedia.accountGUID`. |
| Recherche de campagne multimédia payante | Recherche | Clé : `paidMedia.campaignGUID` ; champ correspondant dans le résumé publicitaire : `paidMedia.campaignGUID`. |
| Recherche de groupe publicitaire de médias payants | Recherche | Clé : `paidMedia.adGroupGUID` ; champ correspondant dans le résumé publicitaire : `paidMedia.adGroupGUID`. |
| Recherche de publicité multimédia payante | Recherche | Clé : `paidMedia.adGUID` ; champ correspondant dans le résumé publicitaire : `paidMedia.adGUID`. |

Vérifiez que l’éditeur de connexion expose les champs correspondants prévus avant d’enregistrer. L’enrichissement du nom décrit plus loin dans ce guide utilise explicitement les règles de recherche de champs dérivés.

Ajoutez d’autres jeux de données de résumé disponibles uniquement lorsque vous avez besoin de leurs répartitions, telles que la géographie, les données démographiques, l’emplacement ou les performances.

## Configurer la vue de données

Ouvrez **[!UICONTROL Gestion des données]** > **[!UICONTROL Vues de données]** et sélectionnez votre vue de données. Si nécessaire, créez une vue de données à l’aide de la connexion que vous avez configurée.

Pour une nouvelle vue de données, utilisez GMT pour aligner les événements du site web sur les jours de média payant UTC et conserver le délai d’expiration par défaut de la session de 30 minutes, sauf si vos exigences en matière de création de rapports diffèrent. La modification du fuseau horaire d’une vue de données existante affecte ses autres rapports ; évaluez cet impact avant de le modifier.

### Ajouter des mesures de médias achetés si elles ne sont pas déjà configurées

Ignorer cette étape si ces mesures ou dimensions existent déjà. Ajoutez les champs suivants à partir de **[!UICONTROL Résumé de l’annonce publicitaire pour médias payants]** :

| Nom du composant | Champ de schéma | Mise en forme |
|---|---|---|
| **Mesures** | | |
| Impressions \| Résumé de l’annonce | `paidMedia.metrics.impressions` | Décimal |
| Clics \| Résumé de l’annonce | `paidMedia.metrics.clicks` | Décimal |
| Dépenses \| Résumé de l’annonce | `paidMedia.metrics.spend` | Devise |
| Conversions \| Résumé des publicités | `paidMedia.metrics.conversions` | Décimal |
| Valeur de conversion \| Résumé de l’annonce | `paidMedia.metrics.conversionValue` | Devise |
| **Dimensions** | | |
| Réseau publicitaire | `paidMedia.adNetwork` | Chaîne |
| GUID de compte | `paidMedia.accountGUID` | Chaîne |
| GUID de campagne | `paidMedia.campaignGUID` | Chaîne |
| GUID de groupe publicitaire | `paidMedia.adGroupGUID` | Chaîne |
| GUID d’annonce publicitaire | `paidMedia.adGUID` | Chaîne |

Le formatage de devise ne permet pas de réconcilier différentes devises sources. Confirmez la base de devise avant de comparer les dépenses et les revenus.

Utilisez des champs dérivés pour créer des noms descriptifs pour la dimension GUID. Utilisez une règle [Recherche](/help/data-views/derived-fields/derived-fields.md#lookup) pour appliquer un nom explicite à la dimension des GUID.  Par exemple : recherchez **[!UICONTROL payMedia.accountGUID (Paid Media Ad Summary)]** à l’aide du jeu de données de recherche **[!UICONTROL Paid Media Account Lookup]** avec la `paidMedia.accountGUID` de clé correspondante et la valeur à renvoyer : `paidMedia.accountDetails.accountName`.


### Créer le champ dérivé du réseau web

Sélectionnez **[!UICONTROL Créer un champ dérivé]** et attribuez un nom au `PM Network (Web)` du champ. Toutes les règles [Analyse d’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) ci-dessous lisent le champ `web.webPageDetails.URL` du jeu de données du site web, appelé ici URL de la page.

Ajoutez des règles dans cet ordre :

| Composants de | Fonction | Configuration |
|---|---|---|
| 1 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL de la page. Obtenez la valeur de la chaîne de requête pour `utm_source`. |
| 2 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL de la page. Obtenez la valeur de la chaîne de requête pour `s_kwcid`. |
| 3 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL de la page. Obtenez la valeur de la chaîne de requête pour `gclid`. |
| 4 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | URL de la page. Obtenez la valeur de la chaîne de requête pour `fbclid`. |
| 5 | [Cas si](/help/data-views/derived-fields/derived-fields.md#case-when) | Appliquez les conditions ci-dessous. |

Configurez la dernière règle [Cas où](/help/data-views/derived-fields/derived-fields.md#case-when) :

1. Si la règle 2 ou la règle 3 est définie, renvoyez `google_ads`.
1. Sinon, si la règle 4 est définie ou la règle 1 est égale à `fb`, `facebook`, `ig`, `instagram` ou `meta`, renvoyez `meta`.
1. Sinon, si la règle 1 est égale à `google`, renvoyez `google_ads`.
1. Ajoutez des mappages pour d&#39;autres réseaux uniquement après avoir confirmé leurs valeurs dans `paidMedia.adNetwork`.
1. Sinon, ne renvoie aucune valeur.

Pour saisir une sortie fixe, ouvrez le sélecteur de valeurs, sélectionnez **[!UICONTROL Valeur de chaîne personnalisée]**, puis saisissez la chaîne.

Ces règles de classification sont basées sur le balisage et non sur la preuve qu’une visite provient d’une publicité payée. Par exemple, un paramètre source seul peut également apparaître sur les liens non payants. Adaptez les conditions à vos conventions de balisage avant d’utiliser le champ comme classificateur de trafic payant.

### Créer les champs dérivés de l’identifiant web

Créez un champ dérivé par niveau de reporting. La structure suivante gère les trois modèles de balisage décrits précédemment :

| Composants de | Fonction | Configuration |
|---|---|---|
| 1 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | Lire le paramètre Meta spécifique au niveau dans l’URL de la page |
| 2 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | Lire le paramètre UTM spécifique au niveau à partir de l’URL de la page |
| 3 | [Analyse de l’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) | Lire le `s_kwcid` depuis l’URL de la page |
| 4 | [Remplacement d’expression régulière](/help/data-views/derived-fields/derived-fields.md#regex-replace) | Appliquez l’expression spécifique au niveau à la règle 3 ; sortie `$1` |
| 5 | [Cas si](/help/data-views/derived-fields/derived-fields.md#case-when) | Si la règle 3 est définie, renvoyez la règle 4 ; sinon, si la règle 1 est définie, renvoyez la règle 1 ; dans le cas contraire, renvoyez la règle 2 |

Utilisez les valeurs suivantes :

| Champs dérivés | Paramètre Meta | Paramètre UTM | Expression Regex |
|---|---|---|---|
| **ID de campagne PM (Web)** | `campaign_id` | `utm_campaign` | `^.*!([^!]*)![^!]*$` |
| **ID de groupe publicitaire PM (Web)** | `adset_id` | `utm_term` | `^.*!([^!]*)$` |
| **ID d’annonce publicitaire PM (Web)** | `ad_id` | `utm_content` | `^[^!]*![^!]*![^!]*!([^!]*)!.*$` |

Dans la dernière règle [Case When](/help/data-views/derived-fields/derived-fields.md#case-when), sélectionnez les sorties de règle antérieures à partir du sélecteur de valeurs au lieu de les saisir sous la forme de chaînes littérales.

L’expression de campagne extrait l’avant-dernière valeur de `s_kwcid`, l’expression de groupe publicitaire extrait la dernière valeur et l’expression de publicité extrait la quatrième valeur. Ces positions dépendent de la mise en page exacte affichée précédemment.

Utilisez **[!UICONTROL Sortie finale]** pour confirmer que les résultats correspondent aux identifiants dans le résumé de l’annonce publicitaire médias payants. Ne conservez pas de branche d’analyse `s_kwcid` si vos URL utilisent une disposition différente. Si vos URL utilisent uniquement des paramètres UTM, omettez les règles inutilisées et mettez à jour les références de règle suivantes en conséquence.

Chaque champ dérivé prend en charge jusqu’à cinq [règles d’analyse d’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) et une [règle de remplacement d’expression régulière](/help/data-views/derived-fields/derived-fields.md#regex-replace). Conservez un identifiant par champ dérivé.

### Créer la mesure des atterrissages payants

Créez un champ dérivé nommé `Paid Media Landings (Web)` en utilisant `PM Campaign ID (Web)` comme entrée.

Le créateur développe les règles du champ de saisie dans le nouveau champ. Après ces règles, ajoutez une règle [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) qui renvoie la valeur numérique personnalisée `1` lorsque la sortie de l’identifiant de campagne est définie, et aucune valeur dans le cas contraire. Ajoutez le résultat en tant que mesure.

Cette mesure comptabilise les événements portant un identifiant de campagne. Cette mesure représente les destinations uniquement lorsque votre implémentation envoie cette URL portant l’ID sur l’événement de destination plutôt que sur des événements répétés ou non liés.

>[!NOTE]
>
>Les règles de champs dérivés développés sont des copies. Si vous modifiez un champ d’ID, inspectez et mettez à jour les champs de nom et d’atterrissage correspondants. Si vous avez omis des règles d’analyse, référencez la règle ID finale réelle plutôt que de supposer qu’il s’agit de la règle 5.

### Ajouter des champs de nom web facultatifs

Pour générer des rapports par nom, créez les champs dérivés suivants avec une [règle de recherche](/help/data-views/derived-fields/derived-fields.md#lookup) après les règles d’ID web étendues :

| Champs dérivés | Entrée | Jeu de données de recherche | Champ correspondant | Champ de retour |
|---|---|---|---|---|
| Nom de la campagne PM (Web) | Sortie finale de l&#39;identifiant de campagne PM (Web) | Recherche de campagne multimédia payante | `paidMedia.campaignID` | `paidMedia.metadata.name` |
| Nom du groupe publicitaire PM (Web) | Sortie finale de l&#39;ID de groupe publicitaire PM (Web) | Recherche de groupe publicitaire de médias payants | `paidMedia.adGroupID` | `paidMedia.metadata.name` |
| Nom de l&#39;annonce publicitaire PM (Web) | Sortie finale de l’ID d’annonce publicitaire PM (Web) | Recherche de publicité multimédia payante | `paidMedia.adID` | `paidMedia.metadata.name` |

Sélectionnez la règle d’ID finale comme champ auquel appliquer la recherche. Vérifiez les noms dans l’aperçu de sortie final avant d’ajouter les champs en tant que dimensions. Si le champ correspondant obligatoire n’est pas disponible, utilisez plutôt le compte rendu des performances basé sur les identifiants .

Les noms correspondent sous forme de texte. Utilisez des dimensions d’ID lorsque différentes entités partagent un nom.

### Ajout de composants web et configuration de l’attribution

Ajoutez les champs d’ID web et dérivés du réseau en tant que dimensions. Ajoutez les champs de nom facultatifs si vous les avez créés. Conservez les paramètres par défaut des composants afin qu’ils correspondent aux dimensions récapitulatives que vous ajoutez à leurs groupes.

Vérifiez que votre vue de données inclut les composants web dont vous avez besoin :

| Composant | Type | Champ de schéma |
|---|---|---|
| URL de la page | Dimension | `web.webPageDetails.URL` |
| Nom de la page | Dimension | `web.webPageDetails.name` |
| URL du référent | Dimension | `web.webReferrer.URL` |
| Type d’événement | Dimension | `eventType` |
| SKU du produit | Dimension | `productListItems.SKU` |
| Nom du produit | Dimension | `productListItems.name` |
| Pages vues | Mesure | `web.webPageDetails.pageViews.value` |
| Ajouter aux paniers | Mesure | `commerce.productListAdds.value` |
| Commandes | Mesure | `commerce.purchases.value` |
| Chiffre dʼaffaires | Mesure | `commerce.order.priceTotal` |

Ajoutez le champ dérivé des atterrissages payants en tant que mesure, puis configurez des mesures de commande et de chiffre d’affaires distinctes :

1. Dupliquez **[!UICONTROL Commandes]** et nommez le `Orders (Web)` de copie. Si **[!UICONTROL Commandes]** n’existe pas, ajoutez-`commerce.purchases.value` directement.
1. Dupliquez **[!UICONTROL Revenu]** et nommez le `Revenue (Web)` de copie. Si **[!UICONTROL Revenue]** n’existe pas, ajoutez-`commerce.order.priceTotal` directement.
1. Format **[!UICONTROL Commandes (Web)]** comme une décimale avec zéro décimale et **[!UICONTROL Chiffre d’affaires (Web)]** comme devise.
1. Pour les deux mesures, ouvrez **[!UICONTROL Attribution]** et activez **[!UICONTROL Remplacer l’attribution par défaut]**.
1. Sélectionnez le modèle **[!UICONTROL Dernière touche]** et le conteneur **[!UICONTROL Session]**.

Conservez les mesures **[!UICONTROL Commandes]** et **[!UICONTROL Chiffre d’affaires]** d’origine inchangées pour conserver les rapports existants. L’activation explicite du remplacement est requise pour cette configuration, même si les valeurs par défaut affichées semblent correspondre.

Pour obtenir un crédit de conversion entre des visites récurrentes, envisagez plutôt un conteneur **[!UICONTROL Personne]** et un intervalle de recherche en amont approprié. Voir le [cas d’utilisation des données de résumé](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-views/summary-data).

Utilisez l’attribution de mesures plutôt que d’ajouter de la persistance aux dimensions d’ID web. Pour éviter de gonfler les décomptes interprétés comme des destinations, ne conservez pas les identifiants d’événements ultérieurs, car cela modifie les événements qui apparaissent sous les lignes de la campagne.

### Créer des dimensions de jointure côté résumé

Ajoutez des dimensions distinctes de Paid Media Ad Summary pour les jointures web :

| Nom du composant | Champ de schéma |
|---|---|
| Ad Network (Joint) | `paidMedia.adNetwork` |
| Identifiant de la campagne (réseau) | `paidMedia.campaignID` |
| ID de groupe publicitaire (réseau) | `paidMedia.adGroupID` |
| ID d’annonce publicitaire (réseau) | `paidMedia.adID` |

Ne modifiez pas et ne dupliquez pas les composants de médias achetés gérés par modèle en lecture seule. Créez les composants distincts ci-dessus à partir des champs de schéma.

Si vous avez créé des champs de nom web facultatifs, créez également ces champs dérivés de recherche côté résumé :

| Nom du composant | Entrée du résumé de l’annonce publicitaire | Jeu de données de recherche | Champ correspondant | Champ de retour |
|---|---|---|---|---|
| Nom De La Campagne (Joint) | `paidMedia.campaignGUID` | Recherche de campagne multimédia payante | `paidMedia.campaignGUID` | `paidMedia.metadata.name` |
| Nom du groupe publicitaire (joint) | `paidMedia.adGroupGUID` | Recherche de groupe publicitaire de médias payants | `paidMedia.adGroupGUID` | `paidMedia.metadata.name` |
| Nom de l’annonce publicitaire (jointe) | `paidMedia.adGUID` | Recherche de publicité multimédia payante | `paidMedia.adGUID` | `paidMedia.metadata.name` |

Utilisez un GUID du jeu de données de résumé comme entrée de chaque recherche. Une dimension provenant directement d’un jeu de données de recherche ne répond pas à l’exigence d’une dimension de synthèse dans un groupe de données de synthèse.

### Créer des groupes de données de résumé

Créez chaque groupe sur la dimension web que vous prévoyez d’utiliser dans les rapports. Ajoutez la dimension de résumé correspondante et masquez ce membre ajouté dans les rapports.

| Dimension web : créez le groupe ici | Dimension de résumé : ajoutée en tant que membre masqué |
|---|---|
| Réseau PM (Web) | Ad Network (Joint) |
| ID de campagne PM (Web) | Identifiant de la campagne (réseau) |
| ID de groupe publicitaire PM (Web) | ID de groupe publicitaire (réseau) |
| ID de publicité PM (Web) | ID d’annonce publicitaire (réseau) |
| Nom de la campagne PM (Web), facultatif | Nom De La Campagne (Joint) |
| Nom du groupe publicitaire PM (Web), facultatif | Nom du groupe publicitaire (joint) |
| Nom de l&#39;annonce publicitaire PM (Web), facultatif | Nom de l’annonce publicitaire (jointe) |

Pour chaque ligne :

1. Sélectionnez la dimension web.
1. Ouvrez **[!UICONTROL Groupe de données de résumé]** et activez **[!UICONTROL Créer un regroupement]**.
1. Ajoutez la dimension de résumé .
1. Activez l’option **[!UICONTROL Masquer dans les rapports]** pour le membre de résumé ajouté. Conserver la dimension web visible.
1. Vérifiez que les paramètres des composants, y compris les minuscules, les sous-chaînes et les règles d’inclusion/exclusion, correspondent entre les membres.

Chaque groupe prend en charge jusqu’à 10 dimensions. Pour inclure des mesures provenant d’un autre jeu de données de résumé, ajoutez la dimension de résumé équivalente de ce jeu de données au même groupe qu’un membre masqué.

>[!IMPORTANT]
>
>Utilisez la dimension web comme dimension de compte rendu des performances et créez le groupe sur cette dimension. La disposition inverse peut afficher des mesures récapitulatives sans les mesures web correspondantes.

Enregistrez la vue de données.

## Créer des mesures calculées

Dans Workspace, accédez à **[!UICONTROL Composants]** > **[!UICONTROL Mesures calculées]** et créez les mesures suivantes à l’aide de la vue de données configurée :

| Nom | Définition | Mise en forme |
|---|---|---|
| Taux de débarquement | Destinations médias payantes (Web) / Clics \| Résumé de l’annonce publicitaire | Pourcentage |
| Taux de conversion web | Destinations Commandes (Web) / Médias payants (Web) | Pourcentage |
| Retour sur dépenses publicitaires Web | Chiffre D’Affaires (Web) / Dépenses \| Résumé Publicitaire | Décimale, deux endroits |
| Coût par commande web | Dépenses \| Résumé de l’annonce / Commandes (Web) | Devise |
| Écart entre la conversion réseau et web | Conversions \| Résumé des publicités - Commandes (Web) | Nombre de décimales, zéro emplacement |

Examinez les lignes avec des dénominateurs nuls avant d’interpréter les mesures de ratio. Un écart de conversion réseau/web n’indique pas en soi une erreur : les deux sources peuvent différer en termes de fenêtres d’attribution, de mesure et de création de rapports.

## Créer et valider le rapport

1. Créez un projet Workspace à l’aide de la vue de données configurée.
1. Choisissez une période avec des données provenant des deux sources. Prévoyez des retards d’ingestion de médias payants ; les données récapitulatives peuvent être en retard d’un jour sur les événements du site Web.
1. Ajoutez un tableau à structure libre avec **[!UICONTROL Identifiant de campagne PM (Web)]** comme dimension de ligne, ou **[!UICONTROL Nom de campagne PM (Web)]** si vous avez configuré des groupes de noms.
1. Ajoutez **[!UICONTROL Impressions | Résumé de l’annonce]**, **[!UICONTROL Clics | Résumé de l’annonce]**, **[!UICONTROL Dépenses | Résumé de l’annonce]**, **[!UICONTROL Conversions | Résumé de l’annonce]**, **[!UICONTROL Paid Media Landings | Résumé de l’annonce]**, **[!UICONTROL Orders (Web)]**, **[!UICONTROL Revenue (Web)]** et les mesures calculées.
1. Ventilez une ligne de campagne par groupe d’annonces web et dimensions d’annonces. Vérifiez que les mesures récapitulatives et web sont renseignées à chaque niveau configuré.
1. Ajoutez un second tableau à l’aide de **[!UICONTROL PM Network (Web)]** pour passer en revue les totaux au niveau du réseau et la ligne sans valeur.

   ![ Projet d’espace de travail de données web et de médias payants ](./assets/paid-media-and-web-data-workspace.png)

   ![Projet d’espace de travail de données web et de médias payants sans données](./assets/paid-media-and-web-data-workspace-no-value.png)

Vérifiez les points suivants avant de partager le rapport :

* Les ID d’événement de destination correspondent aux ID de résumé et de média payants.
* Les mesures de médias payants et les mesures web sont renseignées sur les mêmes lignes.
* Les commandes et le chiffre d’affaires reçoivent l’attribution de session ou de personne prévue.
* Aucune ligne de valeur n’est comprise. Ils peuvent contenir des données de résumé ou une activité web sans identifiants de médias achetés.
* Les différences d’atterrissage/clic sont cohérentes avec la configuration de votre collecte, la gestion du consentement et les fenêtres de création de rapports. Il n’existe pas de taux de correspondance attendu universel.

### Résolution des problèmes de correspondance

| Symptôme | Vérifier et prendre des mesures correctives |
|---|---|
| Les mesures récapitulatives sont renseignées, mais toutes les mesures web sont nulles | Vérifiez que les lignes utilisent des dimensions web et que des groupes ont été créés sur ces dimensions. Ensuite, recherchez des ID réels plutôt que des noms dans les URL de destination. |
| Les mesures web sont renseignées, mais un niveau de résumé est vide | Vérifiez que la dimension de synthèse du niveau se trouve dans le groupe correspondant et que les données de médias payants correspondantes existent pour les dates sélectionnées. |
| Les noms ne figurent pas sur les lignes web | Vérifiez les champs d’entrée de recherche et de correspondance dans l’aperçu de sortie final. Utilisez des groupes d’identifiants si l’enrichissement du nom n’est pas disponible. |
| Les identifiants web contiennent des macros codées ou littérales. | Demandez à l’équipe des opérations publicitaires d’inspecter l’URL de destination et de confirmer que le réseau étend les macros avant d’atterrir. |
| Les ID Google Ads ne correspondent pas | Inspectez la disposition réelle du `s_kwcid` ou les paramètres UTM et mettez à jour les règles d’analyse. |
| Les valeurs réseau sont fractionnées, par exemple `facebook` et `meta` | Faites en sorte que la sortie du champ dérivé du réseau corresponde exactement `paidMedia.adNetwork`. |
| Un identifiant apparaît dans des lignes distinctes | Vérifiez que les paramètres correspondent entre les dimensions regroupées et examinez les valeurs de chaîne sous-jacentes. |
| L’activité du site web semble décalée d’un jour | Comparez le fuseau horaire de la vue de données aux limites des jours de résumé UTC. |
| Les commandes ou les recettes sont nulles ou anormalement basses sous les campagnes | Activez explicitement le remplacement de l’attribution de mesure et confirmez son modèle, son conteneur et ses paramètres de recherche en amont. |
| Les débarquements payés sont étonnamment élevés | Vérifiez que seuls les événements de destination comportent le paramètre de campagne comptabilisé. Des événements répétés portant des identifiants contribuent également à cette mesure. |
| Les campagnes distinctes partagent une ligne de nom. | Utilisez la création de rapports basée sur les identifiants pour distinguer les entités portant des noms identiques. |
