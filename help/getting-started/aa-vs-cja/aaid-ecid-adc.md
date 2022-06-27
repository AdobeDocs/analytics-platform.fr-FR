---
title: AAID, ECID, AACUSTOMID et Analytics Source Connector
description: Découvrez comment le connecteur source Analytics traite les champs d’identité Adobe Analytics.
source-git-commit: 348f4e8596146f7ff4234535fa76a54f7be33171
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 9%

---


# AAID, ECID, AACUSTOMID et Analytics Source Connector

Les données Adobe Analytics contiennent plusieurs champs d’identité. Trois champs d&#39;identité importants sont traités de manière spéciale par la [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr): AAID, ECID, AACUSTOMID.

## AAID

L’Adobe Analytics ID (AAID) est l’identifiant Principal de l’appareil dans Adobe Analytics. Il est garanti qu’il existe sur chaque événement transmis par le biais du connecteur source Analytics. AAID est parfois appelé &quot;identifiant Analytics hérité&quot; ou `s\_vi cookie id`. Cependant, un AAID est créé même si la variable `s\_vi` n’est pas présent. AAID est représenté par la variable `_post\_visid\_high/post\_visid\_low_` colonnes dans [Flux de données Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr#columns%2C-descriptions%2C-and-data-types).

Dans Analytics Source Connector, AAID est transformé en `HEX(post_visid_high) + "-" + HEX(host_visid_low)`. Le champ AAID d’un événement donné contient une identité unique qui peut être l’un de plusieurs types différents, comme décrit dans la section [Ordre des opérations pour les Analytics ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Dans une suite de rapports entière, AAID peut contenir un mélange de types entre les événements. Le type de chaque accès est indiqué dans la variable `_[post\_]visid\_type_` dans les flux de données Analytics.) Voir aussi : [Référence des colonnes de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr).

## ECID

L’ECID (identifiant Experience Cloud), également parfois appelé MCID (identifiant de Marketing Cloud), est un champ d’identifiant d’appareil distinct qui est renseigné dans Adobe Analytics lorsque Analytics est mis en oeuvre à l’aide de la variable [Service Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=fr). L’ECID est représenté par `_mcvisid_` dans les flux de données Adobe Analytics.

Si un ECID existe sur un événement, AAID peut être basé sur ECID selon que l’événement [période de grâce](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=fr) est configuré. Voir aussi : [Requêtes d’Analytics et d’ID d’Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID est un champ d’identifiant distinct renseigné dans Adobe Analytics en fonction de l’utilisation de la variable `s.VisitorID` dans la mise en oeuvre d’Analytics. AACUSTOMID est représenté par le `_cust_visid_` dans les flux de données Adobe Analytics. Si AACUSTOMID est présent, AAID sera basé sur AACUSTOMID. (AACUSTOMID remplace tous les autres identifiants comme défini par l’ordre des opérations mentionné ci-dessus.)

## Comment Analytics Source Connector traite ces identités

Le connecteur source Analytics transmet ces identités à Adobe Experience Platform sous la forme XDM :

* `endUserIDs.\_experience.aaid.id`
* `endUserIDs.\_experience.mcid.id`
* `endUserIDs.\_experience.aacustomid.id`

Ces champs ne sont pas marqués comme identités. Les mêmes identités sont copiées dans les XDM. **_identityMap_** comme paires clé-valeur comme suit :

* `{ “key”: “AAID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_**} ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_** } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **false** } ] }`

Dans identityMap :

* Si ECID est présent, il est marqué comme identité Principale de l’événement. Notez que dans ce cas, AAID peut être basé sur ECID selon la discussion ci-dessus.
Dans le cas contraire, AAID est marqué comme identité Principale de l’événement.
* AACUSTOMID n’est jamais marqué comme ID Principal de l’événement. Cependant, si AACUSTOMID est présent, AAID est basé sur AACUSTOMID comme indiqué dans la discussion ci-dessus.

En ce qui concerne CJA, la définition de l’ID Principal n’est importante que si l’utilisateur final décide d’utiliser l’ID Principal comme ID de personne. Il n’est toutefois pas obligatoire de le faire. L’utilisateur peut choisir une autre colonne d’identité comme ID de personne.

