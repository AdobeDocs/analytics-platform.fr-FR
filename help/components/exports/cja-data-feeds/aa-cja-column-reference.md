---
title: Mapper les colonnes de flux de données d’Adobe Analytics à Customer Journey Analytics
description: Déterminez comment prendre une colonne de flux de données Adobe Analytics donnée et déterminer son équivalent approximatif dans votre implémentation Customer Journey Analytics.
feature: Components
hide: true
hidefromtoc: true
source-git-commit: fbd48b74505e18c24260b87b715ad036a6a60020
workflow-type: tm+mt
source-wordcount: '3236'
ht-degree: 65%

---

# Mapper les colonnes de flux de données d’Adobe Analytics à Customer Journey Analytics

Adobe Analytics et Customer Journey Analytics fonctionnant de manière fondamentalement différente, un mappage de 1 :1 de colonne n’est pas possible. Ces différences sont exacerbées par le fait que chaque mise en œuvre d’Adobe Analytics et de Customer Journey Analytics diffère considérablement.

Cette référence est conçue pour aider les ingénieurs de données à ajuster leurs workflows de flux de données axés sur Adobe Analytics colonne par colonne à un workflow basé sur les flux de données Customer Journey Analytics.

>[!NOTE]
>
>Cette référence inclut uniquement les colonnes considérées comme actuelles par Adobe, en fonction de la [référence des colonnes de flux de données Analytics](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Si vous utilisez activement une colonne de flux de données Analytics qui ne figure pas dans ce tableau, consultez le document de conception de solution de votre entreprise pour déterminer son meilleur équivalent dans Customer Journey Analytics.

+++**`accept_language`**

Liste toutes les langues acceptées, comme indiqué dans l’en-tête HTTP Accept-Language lors d’une demande d’image.

+++

+++**`adload`**

Chargements des publicités multimédia

{{cja-df-post}}

+++

+++**`aemassetid`**

Variable à plusieurs valeurs correspondant aux ID de ressource (identificateurs globaux uniques) d’un ensemble de ressources Adobe Experience Manager Assets. Incrémente l’événement Impression.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifie la source de l’événement de ressources. Utilisée dans Adobe Experience Manager.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

ID de ressource d’une ressource Adobe Experience Manager. Incrémente l’événement Click.

{{cja-df-post}}

+++

+++**`amo_cid`**

La dimension ID AMO, utilisée dans les intégrations Adobe Advertising.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

La dimension ID de l’EF AMO, utilisée dans les intégrations Adobe Advertising.

{{cja-df-post}}

+++

+++**`browser`**

Identifiant numérique qui représente le navigateur. Fait référence à la table de recherche `browser.tsv`.

+++

+++**`browser_height`**

La dimension Hauteur du navigateur .

{{cja-df-post}}

+++

+++**`browser_width`**

Largeur du navigateur

{{cja-df-post}}

+++

+++**`campaign`**

La dimension Code de suivi .

{{cja-df-post}}

+++

+++**`carrier`**

Variable d’intégration Adobe Advertising. Définit l’opérateur de téléphonie mobile. Valeur de clé pour `carrier.tsv` recherche dynamique.

+++

+++**`channel`**

La dimension Sections du site .

{{cja-df-post}}

+++

+++**`ch_hdr`**

Indications du client collectées via l’en-tête de requête HTTP.

+++

+++**`ch_js`**

Indications du client collectées via l’API JavaScript User-Agent Client Hints.

+++

+++**`clickmaplink`**

La dimension Lien d’Activity Map .

{{cja-df-post}}

+++

+++**`clickmaplinkbyregion`**

La dimension Lien Activity Map par région .

{{cja-df-post}}

+++

+++**`clickmappage`**

La dimension Page d’Activity Map .

{{cja-df-post}}

+++

+++**`clickmapregion`**

La dimension Région d’Activity Map .

{{cja-df-post}}

+++

+++**`code_ver`**

Version du SDK client ou de l’API utilisée pour compiler et envoyer la demande d’image.

+++

+++**`color`**

Identifiant d’intensité des couleurs basé sur la valeur de la colonne `c_color`. Fait référence à la table de recherche `color_depth.tsv`.

+++

+++**`connection_type`**

Identifiant numérique représentant la dimension Type de connexion . Fait référence à la table de recherche `connection_type.tsv`.

+++

+++**`cookies`**

La dimension Prise en charge des cookies .<br>Y : activé<br>N : désactivé<br>U : inconnu

{{cja-df-post}}

+++

+++**`country`**

Identifiant numérique qui représente le pays du visiteur ou de la visiteuse. Fait référence à la table de recherche `country.tsv`.

+++

+++**`currency`**

Le code de devise qui a été utilisé pendant la transaction. Définissez avec `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

Liée à la colonne `connection_type`. Les valeurs les plus courantes sont LAN/Wi-Fi, Opérateur de téléphonie mobile et Modem.

+++

+++**`curr_factor`**

Détermine la place décimale de la devise. Utilisé pour la conversion des devises. Par exemple, le dollar américain (USD) utilise deux décimales, donc cette valeur de colonne serait `2`.

+++

+++**`curr_rate`**

Taux de change au moment de la transaction. Adobe travaille en partenariat avec XE pour déterminer le taux de change du jour.

+++

+++**`customer_perspective`**

Détermine si l’accès est un accès en arrière-plan mobile.

{{cja-df-post}}

+++

+++**`cust_hit_time_gmt`**

Suites de rapports avec horodatage uniquement. Date et l’heure envoyées avec l’accès, basées sur l’heure UNIX®.

{{cja-df-post}}

+++

+++**`cust_visid`**

Identifiant visiteur ou visiteuse personnalisé, si défini avec `visitorID`.

{{cja-df-post}}

+++

+++**`c_color`**

Codage en bits de la palette de couleurs. Utilisé dans le cadre du calcul de la dimension Profondeur de la couleur . AppMeasurement utilise la fonction JavaScript `screen.colorDepth()`.

+++

+++**`daily_visitor`**

Indicateur qui détermine si l’accès est un nouveau visiteur quotidien ou une nouvelle visiteuse quotidienne.

+++

+++**`dataprivacyconsentoptin`**

La dimension Accord préalable de gestion du consentement . Plusieurs valeurs peuvent être présentes par accès, séparées par une barre verticale (`\|`). Les valeurs valides comprennent `DMP` et `SELL`.

+++

+++**`dataprivacyconsentoptout`**

La dimension Droit d’opposition de gestion du consentement . Plusieurs valeurs peuvent être présentes par accès, séparées par une barre verticale (`\|`). Les valeurs valides comprennent `SSF`, `DMP` et `SELL`.

+++

+++**`date_time`**

Heure de l’accès dans un format lisible, basée sur le fuseau horaire de la suite de rapports.

+++

+++**`domain`**

La dimension Domaine . Basée sur le point dʼaccès Internet du visiteur ou de la visiteuse.

+++

+++**`duplicated_from`**

Utilisée uniquement dans les suites de rapports contenant les règles VISTA de la copie de l’accès. Indique la suite de rapports à partir de laquelle l’accès a été copié.

+++

+++**`duplicate_events`**

Répertorie chaque événement compté comme double.

+++

+++**`duplicate_purchase`**

Indicateur signifiant que l’événement d’achat pour cet accès doit être ignoré, car il s’agit d’un double.

+++

+++**`ef_id`**

Identifiant EF, utilisé dans les intégrations Adobe Advertising.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Variables personnalisées 1-250. Utilisé dans les dimensions eVar. Chaque organisation utilise les eVars différemment. Le meilleur outil pour obtenir plus d’informations sur la façon dont votre organisation renseigne les eVars respectifs serait un document de conception de solution spécifique à votre organisation.

{{cja-df-post}}

+++

+++**`event_list`**

Liste séparée par des virgules d’identifiants numériques représentant les événements déclenchés lors de l’accès. Inclut les événements Commerce et les événements personnalisés 1-1000. Utilise la recherche de `event.tsv`.

Cette colonne correspond probablement à des dizaines de mesures distinctes, selon votre implémentation. Adobe recommande le processus suivant pour mapper chaque mesure respective dans Customer Journey Analytics à sa valeur numérique représentée dans cette colonne de flux de données Analytics :

1. Utilisez la recherche `event.tsv` pour mapper chaque valeur numérique à son nom de mesure.
1. Utilisez le document de conception de votre solution pour mapper chaque nom d’événement Analytics au nom de mesure correspondant dans Customer Journey Analytics.
1. Sélectionnez le composant mappé dans l’interface utilisateur des vues de données et notez son identifiant de composant. Si l’identifiant du composant est trop difficile à gérer, vous pouvez renseigner le champ d’identifiant d’alias de flux de données et l’utiliser à la place.
1. Répétez l’opération pour chaque mesure utilisée par votre organisation.

{{cja-df-post}}

+++

+++**`exclude_hit`**

Indicateur qui détermine si l’accès est exclu de la création de rapports. La colonne `visit_num` nʼest pas incrémentée pour les accès exclus.<br>1 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>2 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>3 : n’est plus utilisée. Exclusion de lʼagent utilisateur<br>4 : Exclusion basée sur lʼadresse IP<br>5 : Information indispensable sur lʼaccès manquante telle que `page_url`, `pagename`, `page_event`, ou `event_list`<br>6 : JavaScript nʼa pas traité lʼaccès correctement<br>7 : Exclusion spécifique au compte, comme dans les règles VISTA<br>8 : Inutilisée. Autre exclusion spécifique au compte.<br>9 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>10 : Code de devise invalide<br>11 : Horodatage manquant sur un accès pour une suite de rapport avec horodatage ou l’accès contenait un horodatage sur une suite de rapport sans horodatage<br>12 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>13 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>14 : Accès cible qui ne correspondait pas à un accès Analytics<br>15 : Inutilisé pour le moment.<br>16 : Accès Advertising Cloud qui ne correspondait pas à un accès Analytics

+++

+++**`first_hit_pagename`**

La dimension d’origine Page d’entrée . Le nom de la page d’entrée d’origine du visiteur.

+++

+++**`first_hit_page_url`**

La toute première URL du visiteur.

+++

+++**`first_hit_referrer`**

La toute première URL de référence du visiteur.

+++

+++**`first_hit_ref_domain`**

La dimension Domaine référent d’origine . Basée sur `first_hit_referrer`. Le tout premier domaine référent du visiteur.

+++

+++**`first_hit_ref_type`**

Identifiant numérique représentant le type de référent du tout premier référent du visiteur ou de la visiteuse. Fait référence à la table de recherche `referrer_type.tsv`.

+++

+++**`first_hit_time_gmt`**

Date et heure du tout premier accès du visiteur ou de la visiteuse (heure UNIX®).

+++

+++**`geo_city`**

Nom de la ville d’où provient l’accès, basé sur l’adresse IP. Utilisé dans la dimension Villes .

+++

+++**`geo_country`**

Abréviation du pays d’où provient l’accès, basé sur l’adresse IP. Utilisé dans la dimension Pays .

+++

+++**`geo_dma`**

Identifiant numérique de la zone démographique d’où provient l’accès, basé sur l’adresse IP. Utilisé dans la dimension DMA US.

+++

+++**`geo_region`**

Nom de l’État ou de la région d’où provient l’accès, basé sur l’adresse IP. Utilisé dans la dimension Régions .

+++

+++**`geo_zip`**

Code postal d’où provient l’accès, basé sur l’adresse IP. Permet de renseigner la dimension Code postal . Voir également `zip`.

+++

+++**`hitid_high`**

Utilisée en combinaison avec `hitid_low` pour identifier un accès.

+++

+++**`hitid_low`**

Utilisée en combinaison avec `hitid_high` pour identifier un accès.

+++

+++**`hit_source`**

Indique la source de l’accès. Les sources 1 et 2 sont facturées. <br>1 : demande d’image standard sans horodatage <br>2 : demande d’image standard avec horodatage <br>3 : chargement de la source de données active avec horodatage <br>4 : non utilisée <br>5 : chargement de la source de données générique <br>6 : plus utilisée ; chargement de la source de données à traitement complet <br>7 : chargement de la source de données TransactionID <br>8 : plus utilisée ; versions précédentes des sources de données Adobe Advertising <br>9 : plus utilisée ; mesures de résumé des réseaux sociaux Adobe <br>10 : transfert côté serveur Audience Manager utilisé

+++

+++**`hit_time_gmt`**

Date et l’heure des serveurs de collecte de données Adobe ayant reçu l’accès, basé sur l’heure UNIX®.

+++

+++**`hourly_visitor`**

Indicateur qui détermine si l’accès est un nouveau visiteur ou une nouvelle visiteuse horaire.

+++

+++**`ip`**

L’adresse IPv4, basée sur l’en-tête HTTP de la demande d’image. Mutuellement exclusif à `ipv6`. Si cette colonne contient une adresse IP non masquée, `ipv6` est vide.

+++

+++**`ipv6`**

L’adresse IPv6 compressée, si disponible. Mutuellement exclusif à `ip`. Si cette colonne contient une adresse IP non masquée, `ip` est vide.

+++

+++**`javascript`**

Identifiant de recherche de la version JavaScript, basé sur `j_jscript`. Fait référence à la table de recherche `javascript_version`.

+++

+++**`java_enabled`**

La dimension Compatible Java . <br>Y : activé <br>N : désactivé <br>U : inconnu

{{cja-df-post}}

+++

+++**`j_jscript`**

Version de JavaScript prise en charge par le navigateur.

+++

+++**`language`**

Identifiant numérique représentant la langue du visiteur ou de la visiteuse. Fait référence à la table de recherche `languages.tsv`.

+++

+++**`last_hit_time_gmt`**

Date et heure (en heure UNIX®) de l’accès précédent. Utilisé pour calculer la dimension Jours depuis la dernière visite .

+++

+++**`last_purchase_num`**

La dimension Fidélisation des clients . Indique le nombre dʼachats précédents effectués par le visiteur. <br>0 : Aucun achat auparavant (n’est pas client) <br>1 : 1 achat précédent (nouveau client) <br>2 : 2 achats précédents (client de retour) <br>3 : 3 achats précédents ou plus (client fidèle)

+++

+++**`last_purchase_time_gmt`**

Utilisé dans la dimension Jours depuis le dernier achat . Date et heure (en heure UNIX®) du dernier achat effectué. Pour les premiers achats et les visiteurs qui n’avaient jamais effectué d’achat auparavant, cette valeur est de `0`.

+++

+++**`latlon1`**

Lieu (jusqu’à 10 km)

+++

+++**`latlon23`**

Lieu (jusqu’à 100 m)

+++

+++**`latlon45`**

Lieu (jusqu’à 1 m)

+++

+++**`mcvisid`**

Identifiant visiteur Experience Cloud. Nombre 128 bits constitué de deux nombres 64 bits concaténés complétés par 19 chiffres.

+++

+++**`mc_audiences`**

Liste des identifiants de segment Audience Manager auxquels le visiteur appartient. La colonne `post_mc_audiences` change le délimiteur en `--**--`.

{{cja-df-post}}

+++

+++**`mobileaction`**

Action mobile. Collectée automatiquement lors dʼun appel `trackAction` dans les implémentations mobiles. Permet le cheminement d’action automatique dans l’application.

{{cja-df-post}}

+++

+++**`mobileappid`**

ID de l’application mobile Stocke le nom et la version de l’application au format suivant : `[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Utilisé dans le connecteur de données Aptelignent. L’identifiant d’application utilisé dans Apteligent.

+++

+++**`mobileappperformancecrashid`**

Utilisé dans le connecteur de données Aptelignent. L’identifiant de plantage utilisé dans Apteligent.

+++

+++**`mobileappstoreobjectid`**

Utilisé dans le connecteur de données [!DNL Appfigures]. Identifiant de l’objet de la boutique d’applications.

+++

+++**`mobilebeaconmajor`**

Relais Mobile Services majeur

+++

+++**`mobilebeaconminor`**

Relais Mobile Services mineur

+++

+++**`mobilebeaconproximity`**

Proximité du relais Mobile Services

+++

+++**`mobilebeaconuuid`**

UUID du relais Mobile Services

+++

+++**`mobilecampaigncontent`**

Le nom ou l’identifiant du contenu qui a affiché le lien. Renseigné par l’acquisition des applications mobiles.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Support marketing, une bannière ou un courrier électronique par exemple. Renseigné par l’acquisition des applications mobiles.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

Nom de la campagne, également stocké dans la variable de campagne. Renseigné par l’acquisition des applications mobiles.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Référent original, comme la newsletter ou les médias sociaux. Renseigné par l’acquisition des applications mobiles.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Mots-clés ou autres termes payés dont vous souhaitez effectuer le suivi avec cette acquisition. Renseigné par l’acquisition des applications mobiles.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Numéro du jour de la semaine où l’application a été lancée.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Nombre de jours depuis que l’application a été lancée pour la première fois.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Nombre de jours depuis la dernière exécution de l’application.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Collecté à partir de la variable des données de contexte `a.deeplink.id`. Utilisé dans les rapports d’acquisition comme identifiant du lien d’acquisition mobile.

+++

+++**`mobiledevice`**

Nom de l’appareil mobile. Sous iOS, il est stocké sous la forme d’une chaîne de 2 chiffres séparés par des virgules. Le premier chiffre représente la génération de l’appareil, le second la famille d’appareils.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Définit l’heure du jour où l’application a été lancée. Suit un format numérique de 24 heures.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Date de l’installation mobile. Indique la date de la première ouverture d’une application mobile par un utilisateur ou une utilisatrice.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Est incrémentée d’une unité chaque fois que l’application mobile est lancée.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Collecté à partir de la variable des données de contexte `a.message.button.id`. Utilisé pour la messagerie au sein de l’application afin d’identifier le bouton qui a fermé le message.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

Identifiant de message au sein de l’application

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

Message en ligne dans l’application

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Collecté à partir de la variable des données de contexte `a.push.optin`. Définissez cette valeur sur « true » lorsque l’utilisateur s’inscrit à la messagerie push ; dans le cas contraire, la valeur qui apparaît est « false ».

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Collecté à partir de la variable des données de contexte `a.push.payloadid`. Utilisé comme identifiant de paiement dans la messagerie push.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Version du système d’exploitation Mobile Services

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

Collecté à partir de la variable des données de contexte `a.loc.acc`. Indique la précision du GPS en mètres au moment de la collecte des données.

+++

+++**`mobileplacecategory`**

Collecté à partir de la variable des données de contexte `a.loc.category`. Décrit la catégorie d’un lieu en particulier.

+++

+++**`mobileplaceid`**

Collecté à partir de la variable des données de contexte `a.loc.id`. Identifiant d’un point ciblé donné.

+++

+++**`mobilepushoptin`**

Abonnement push de Mobile Services

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

ID de payload push Mobile Services

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Contenu du lancement Mobile Services

+++

+++**`mobilerelaunchcampaignmedium`**

Moyen de lancement de Mobile Services

+++

+++**`mobilerelaunchcampaignsource`**

Source de lancement de Mobile Services

+++

+++**`mobilerelaunchcampaignterm`**

Conditions de lancement de Mobile Services

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Collecté à partir de la variable des données de contexte `a.launch.campaign.trackingcode`. Utilisé au moment de l’acquisition comme code de suivi de la campagne de lancement.

+++

+++**`mobileresolution`**

Résolution de l’appareil mobile. `[Width] x [Height]` en pixels.

{{cja-df-post}}

+++

+++**`mobile_id`**
Si l’utilisateur ou l’utilisatrice a recours à un appareil mobile, il s’agit alors de l’identifiant numérique de l’appareil. Valeur de clé pour `mobile_attributes.tsv` recherche dynamique.

+++

+++**`monthly_visitor`**

Indicateur signifiant que le visiteur ou la visiteuse est unique pour le mois en cours.

+++

+++**`mvvar1`** - **`mvvar3`**

Valeurs des variables de liste. Contient une liste délimitée de valeurs personnalisées en fonction de l’implémentation. Les colonnes `post_mvvar1` - `post_mvvar3` remplacent le délimiteur dʼorigine par `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

Les valeurs de la variable de liste qui ont été définies sur l’accès actuel. Remplace le délimiteur d’origine par `--**--`. Les colonnes `post` ne contiennent généralement pas de données.

{{cja-df-post}}

+++

+++**`new_visit`**

Indicateur qui détermine si l’accès actif est une nouvelle visite. Valeur définie par Adobe après 30 minutes d’inactivité au niveau de la visite.

+++

+++**`os`**

Identifiant numérique représentant le système d’exploitation du visiteur ou de la visiteuse. Basé sur la colonne `user_agent`. Valeur de clé pour `operating_system.tsv` recherche standard et `operating_system_type.tsv` recherche dynamique.

+++

+++**`pagename`**

La dimension Page . Si la variable `pagename` est vide, Analytics utilise la variable `page_url` en remplacement.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Similaire à `pagename`, sauf qu’il ne retourne pas à `page_url`. Seule la colonne `post` est disponible.

{{cja-df-post}}

+++

+++**`page_event`**

Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien personnalisé, lien de sortie). Voir Recherche d’événement de page.

{{cja-df-post}}

+++

+++**`page_event_var1`**

Uniquement utilisée dans les demandes d’image de suivi des liens. URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Uniquement utilisée dans les demandes d’image de suivi des liens. Nom personnalisé (le cas échéant) du lien. Définit le lien personnalisé, le lien de téléchargement ou le lien de sortie en fonction de la valeur dans `page_event`.

{{cja-df-post}}

+++

+++**`page_type`**

La dimension Pages introuvables , généralement utilisée pour les pages 404.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`** : URL de l’accès. Utilise un type de données de texte.<br>**`post_page_url`**: supprimé pour les demandes d’image de suivi de liens (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

Indicateur qui détermine si l’accès correspond à la détection des référencements payants.

+++

+++**`persistent_cookie`**

Utilisé dans la dimension Prise en charge des cookies persistants . Indique si le visiteur prend en charge les cookies qui ne sont pas ignorés après chaque accès.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Nom du point ciblé Mobile Services

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Distance du centre du point ciblé Mobile Services

{{cja-df-post}}

+++

+++**`product_list`**

Variable de page `products`. Permet de renseigner plusieurs dimensions et mesures, y compris la catégorie, le produit, les unités et le chiffre d’affaires.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

Variables de trafic personnalisées 1 - 75. Utilisé dans les dimensions prop.

{{cja-df-post}}

+++

+++**`purchaseid`**

Identifiant unique pour un achat, tel qu’il est défini à l’aide de la variable `purchaseID`. Utilisé par la colonne `duplicate_purchase`.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

Indicateur qui détermine si l’accès est un nouveau visiteur trimestriel ou une nouvelle visiteuse trimestrielle.

+++

+++**`referrer`**

La dimension Référent . Notez que, bien que `referrer` utilise un type de données varchar(255), `post_referrer` utilise un type de données varchar(244).

{{cja-df-post}}

+++

+++**`ref_domain`**

La dimension Domaine référent . Basé sur la colonne `referrer`.

+++

+++**`ref_type`**


Identifiant numérique représentant le type de référence pour l’accès. Utilisé dans la dimension Type de référent .<br>1 : à l’intérieur de votre site<br>2 : autres sites web<br>3 : moteurs de recherche<br>4 : disque dur<br>5 : USENET<br>6 : dactylographié/mis en signet (pas de référent)<br>7 : e-mail<br>8 : pas de JavaScript<br>9 : réseaux sociaux<br>10 : outils d’IA conversationnelle

+++

+++**`resolution`**

Identifiant numérique représentant la résolution du moniteur. Utilisé dans la dimension Résolution du moniteur . Utilise la table de recherche `resolution.tsv`.

+++

+++**`search_engine`**

Identifiant numérique représentant le moteur de recherche qui a renvoyé le visiteur ou la visiteuse sur votre site. Utilisé dans les dimensions du moteur de recherche. Fait référence à la table de recherche `search_engines.tsv`.

{{cja-df-post}}

+++

+++**`search_page_num`**

Variable utilisée par la dimension Classification globale des pages de recherche. Indique sur quelle page de résultats de recherche votre site est apparu avant que l’utilisateur ou l’utilisatrice ne clique sur votre site.

+++

+++**`secondary_hit`**

Indicateur qui détermine si l’accès est un accès secondaire. Normalement, l’indicateur provient du balisage multisuite et des règles VISTA qui copient les accès.

+++

+++**`sourceid`**

ID Source

+++

+++**`stats_server`**

Inutilisable. Serveur interne d’Adobe qui a traité l’accès.

+++

+++**`s_kwcid`**

Identifiant du mot-clé dans les intégrations Adobe Advertising.

{{cja-df-post}}

+++

+++**`s_resolution`**

Valeur brute de la résolution de l’écran. Collecté à l’aide de la fonction JavaScript `screen.width x screen.height`.

+++

+++**`tnt`**

Utilisée dans les intégrations Adobe Target. Représente tous les tests actuellement autorisés. Le format est : `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Utilisée dans les intégrations Adobe Target. Représente tous les tests pour lesquels lʼaccès est qualifié.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Utilisée dans les intégrations Adobe Target. Variable d’instances Target.

+++

+++**`transactionid`**

Identifiant unique dans lequel divers points de données peuvent être chargés ultérieurement par le biais de sources de données. Collecté à l’aide de la variable `transactionID`.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

Indicateur signalant que la demande d’image a été tronquée (un accès partiel a été reçu). <br>Y : l’accès a été tronqué ; accès partial reçu <br>N : l’accès n’a pas été tronqué ; accès complet reçu

+++

+++**`t_time_info`**

Heure locale pour le visiteur. Le format est : `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

Inutilisable. Identifiant numérique pour l’identifiant de suite de rapports. Utilisez `username` à la place.

+++

+++**`username`**

Identifiant de suite de rapports pour l’accès.

+++

+++**`user_agent`**

Chaîne de l’agent utilisateur envoyée dans l’en-tête HTTP de la demande d’image.

+++

+++**`user_hash`**

Inutilisable. Hachage de l’identifiant de suite de rapports. Utilisez `username` à la place.

+++

+++**`user_server`**

Utilisé dans la dimension Serveur .

{{cja-df-post}}

+++

+++**`va_closer_detail`**

La dimension Détails de la dernière touche .

+++

+++**`va_closer_id`**

Identifiant numérique qui identifie la dimension du canal Dernière touche . La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing.

+++

+++**`va_finder_detail`**

La dimension Détail Première touche .

+++

+++**`va_finder_id`**

Identifiant numérique qui identifie la dimension du canal Première touche. La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing.

+++

+++**`va_instance_event`**

Indicateur qui identifie les instances de canal marketing.

+++

+++**`va_new_engagement`**

Indicateur qui identifie les nouveaux engagements de canal marketing.

+++

+++**`video`**

La dimension Services de médias en flux continu de contenu .

{{cja-df-post}}

+++

+++**`videoad`**

La dimension Ajouter des services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videoadinpod`**

La dimension Annonce dans la capsule position services de streaming multimédia .

{{cja-df-post}}

+++

+++**`videoadlength`**

La dimension Longueur de l’annonce (variable) des services de streaming multimédia.

{{cja-df-post}}

+++

+++**`videoadname`**

La dimension Nom de l’annonce (variable) des services de streaming multimédia.

{{cja-df-post}}

+++

+++**`videoadplayername`**

La dimension Services de médias en flux continu Nom du lecteur de publicité .

{{cja-df-post}}

+++

+++**`videoadpod`**

La dimension des services de médias en flux continu AdPod .

{{cja-df-post}}

+++

+++**`videoadvertiser`**

La dimension Services de médias en flux continu des annonceurs .

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

La dimension Services de médias en flux continu dans Album .

+++

+++**`videoaudioartist`**

La dimension Services de médias en flux continu pour les artistes .

+++

+++**`videoaudioauthor`**

La dimension Créer des services de médias en flux continu .

+++

+++**`videoaudiolabel`**

La dimension Étiqueter les services de médias en flux continu .

+++

+++**`videoaudiopublisher`**

La dimension Services de streaming multimédia de Publisher .

+++

+++**`videoaudiostation`**

La dimension Services de médias en flux continu de la station .

+++

+++**`videocampaign`**

La dimension Services de médias en flux continu de l’identifiant de campagne .

{{cja-df-post}}

+++

+++**`videochannel`**

La dimension Services de médias en flux continu du canal de contenu .

{{cja-df-post}}

+++

+++**`videochapter`**

La dimension Chapitre sur les services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videocontenttype`**

La dimension Type de contenu des services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videodaypart`**

La dimension Services de médias en flux continu de la partie Jour .

{{cja-df-post}}

+++

+++**`videoepisode`**

La dimension des services de médias en flux continu d’épisodes .

{{cja-df-post}}

+++

+++**`videofeedtype`**

La dimension Services de médias en flux continu de type Flux multimédia .

{{cja-df-post}}

+++

+++**`videogenre`**

La dimension Genre des services de streaming multimédia . Cette dimension autorise plusieurs valeurs dans le même accès, délimitées par une virgule.

{{cja-df-post}}

+++

+++**`videolength`**

La dimension Longueur du contenu (variable) des services de médias en streaming .

{{cja-df-post}}

+++

+++**`videomvpd`**

La dimension Services de médias en flux continu MVPD .

{{cja-df-post}}

+++

+++**`videoname`**

La dimension Nom du contenu (variable) des services de streaming multimédia.

{{cja-df-post}}

+++

+++**`videonetwork`**

La dimension Services de médias en flux continu réseau .

{{cja-df-post}}

+++

+++**`videopath`**

La dimension Chemin d’accès aux médias - Services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videoplayername`**

La dimension Nom du lecteur de contenu des services de médias en flux continu.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

La dimension Débit moyen des services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

Le débit modifie la dimension des services de streaming multimédia.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

La dimension Services de médias en flux continu des événements de mémoire tampon .

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

La dimension Durée totale de la mémoire tampon des services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

La dimension Images perdues des services de streaming multimédia.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

La dimension Erreurs des services de streaming multimédia.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

La dimension Identifiants d’erreur externe des services de médias en flux continu . Cette dimension autorise plusieurs valeurs dans le même accès.

+++

+++**`videoqoeplayersdkerrors`**

La dimension Services de médias en flux continu des identifiants d’erreur du SDK du lecteur . Cette dimension autorise plusieurs valeurs dans le même accès.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

La dimension Heure de début des services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videoseason`**

La dimension Saison des services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videosegment`**

La dimension Services de médias en flux continu de segment de contenu .

{{cja-df-post}}

+++

+++**`videosessionid`**

La dimension Services de médias en flux continu d’ID de session multimédia .

{{cja-df-post}}

+++

+++**`videoshow`**

La dimension Afficher les services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videoshowtype`**

La dimension Afficher le type de services de médias en flux continu .

{{cja-df-post}}

+++

+++**`videostreamtype`**

La dimension Services de médias en flux continu de type Flux .

+++

+++**`visid_high`**

Utilisé en combinaison avec `visid_low` pour identifier un visiteur ou une visiteuse de manière unique.

{{cja-df-post}}

+++

+++**`visid_low`**

Utilisé en combinaison avec `visid_high` pour identifier un visiteur ou une visiteuse de manière unique.

{{cja-df-post}}

+++

+++**`visid_new`**

Indicateur pour identifier si l’accès contient un identifiant visiteur ou visiteuse nouvellement généré.

+++

+++**`visid_timestamp`**

Si l’identifiant visiteur ou visiteuse a été récemment généré, fournit la date et l’heure (en heure UNIX®) de la génération de l’identifiant.

+++

+++**`visid_type`**

Uniquement destinée à un usage interne. Utilisée en interne par Adobe pour les optimisations de traitement. Identifiant numérique représentant la méthode utilisée pour identifier le visiteur ou la visiteuse.<br>`0` : identifiant visiteur personnalisé ou inconnu/non applicable <br>`1` : solution de secours de l’IP et de l’agent utilisateur <br>`2` : en-tête de l’abonné mobile HTTP <br>`3` : valeur du cookie hérité (`s_vi`) <br>`4` : valeur du cookie de secours (`s_fid`) <br>`5` : Service d’identités

{{cja-df-post}}

+++

+++**`visit_keywords`**

La dimension Mot-clé de recherche . Cette colonne utilise une limite de caractères non standard de varchar(244) pour s’adapter à la logique d’arrière-plan utilisée par Adobe. La colonne post-traitée est `**post_keywords**` et non `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

La dimension Nombre de visites . Commence à 1, et est incrémentée chaque fois qu’une nouvelle visite commence par visiteur.

+++

+++**`visit_page_num`**

La dimension Profondeur de l’accès . Augmente de 1 pour chaque accès que le visiteur ou la visiteuse génère. Réinitialise chaque visite.

+++

+++**`visit_referrer`**

Premier référent de la visite.

+++

+++**`visit_ref_domain`**

Basé sur la colonne `visit_referrer`. Le premier domaine référent de la visite.

+++

+++**`visit_ref_type`**

Identifiant numérique, représentant le type de référent du tout premier référent de la visite. Fait référence à la table de recherche `referrer_type.tsv`.

+++

+++**`visit_search_engine`**

Identifiant numérique du premier moteur de recherche de la visite. Fait référence à la table de recherche `search_engines.tsv`.

+++

+++**`visit_start_pagename`**

Page du premier accès de la visite.

+++

+++**`visit_start_page_url`**

URL du premier accès de la visite.

+++

+++**`visit_start_time_gmt`**

Date et heure (en heure UNIX®) du premier accès de la visite.

+++

+++**`weekly_visitor`**

Indicateur qui détermine si l’accès est un nouveau visiteur ou une nouvelle visiteuse hebdomadaire.

+++

+++**`yearly_visitor`**

Indicateur qui détermine si l’accès est un nouveau visiteur annuel ou une nouvelle visiteuse annuelle.

+++

+++**`zip`**

Permet de renseigner la dimension Code postal . Voir également `geo_zip`.

{{cja-df-post}}

+++
