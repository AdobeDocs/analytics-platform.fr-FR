---
title: AAID, ECID, AACUSTOMID et le connecteur source Analytics
description: Découvrez comment le connecteur source Analytics traite les champs d’identité dans Adobe Analytics.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
source-git-commit: 4c9d87b6c6b7859ffac4cd2d26e8c89d12fe1285
workflow-type: ht
source-wordcount: '560'
ht-degree: 100%

---

# AAID, ECID, AACUSTOMID et le connecteur source Analytics

Les données Adobe Analytics contiennent plusieurs champs d’identité. Le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) traite de manière distincte trois champs d’identité importants : AAID, ECID et AACUSTOMID.

## AAID

L’ID Adobe Analytics (AAID) représente l’identifiant principal de l’appareil dans Adobe Analytics. Il existe systématiquement dans chaque événement transmis par le biais du connecteur source Analytics. L’AAID est parfois appelé l’« ID Analytics hérité » ou l’ID de cookie `s_vi`. Cependant, un AAID est créé même en absence du cookie `s_vi`. L’AAID est représenté par les colonnes `post_visid_high/post_visid_low` dans les [flux de données Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr#columns%2C-descriptions%2C-and-data-types).

L’AAID est transformé en `HEX(post_visid_high) + "-" + HEX(post_visid_low)` dans le connecteur source Analytics. Le champ AAID d’un événement donné contient une identité unique qui peut être de l’un des types décrits dans l’[ordre des opérations pour les ID Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=fr%5B%5D). (Dans une suite de rapports entière, l’AAID peut contenir plusieurs types parmi les événements. Le type de chaque accès est indiqué dans la colonne `post_visid_type` des flux de données Analytics.) Voir également : [Référence des colonnes de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr).

## ECID

L’ECID (ID Experience Cloud), également parfois appelé MCID (ID Marketing Cloud), est un champ d’identifiant de l’appareil distinct qui est renseigné dans Adobe Analytics lorsqu’Analytics est implémenté à l’aide du [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=fr). L’ECID est représenté par la colonne `mcvisid` dans les flux de données Adobe Analytics.

Si un ECID existe sur un événement, l’AAID peut être basé sur l’ECID selon que le [délai de grâce](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=fr) d’Analytics est configuré ou non. Voir également : [Requêtes d’ID Analytics et Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=fr).

## AACUSTOMID

L’AACUSTOMID est un champ d’identifiant distinct qui est renseigné dans Adobe Analytics en fonction de l’utilisation de la variable `s.VisitorID` dans l’implémentation d’Analytics. L’AACUSTOMID est représenté par la colonne `cust_visid` dans les flux de données Adobe Analytics. En présence de l’AACUSTOMID, l’AAID sera basé sur l’AACUSTOMID. (L’AACUSTOMID surpasse tous les autres identifiants comme déterminé par l’ordre des opérations mentionné ci-dessus.)

## Traitement de ces identités par le connecteur source Analytics

Le connecteur source Analytics transmet ces identités à Adobe Experience Platform en tant que XDM sous la forme suivante :

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Ces champs ne sont pas marqués comme des identités. À la place, les mêmes identités sont copiées dans le **_mappage d’identité_** de XDM en tant que paires clé-valeur de la façon suivante :

* `{ “key”: “AAID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “<identity>”, “primary”: false } ] }`

Les éléments entre crochets

Dans le mappage d’identité :

* En présence d’un ECID, l’identité est marquée comme l’identité principale de l’événement. Remarque : dans ce cas, l’AAID peut se baser sur l’ECID conformément aux informations ci-dessus.
Dans le cas contraire, l’AAID est marqué comme étant l’identité principale de l’événement.
* L’AACUSTOMID n’est jamais marqué comme l’ID principal de l’événement. Cependant, en présence d’un AACUSTOMID, l’AAID est basé sur l’AACUSTOMID conformément au processus décrit ci-dessus.

## CJA et ID principal

En ce qui concerne CJA, la définition de l’ID principal n’importe que si vous décidez d’utiliser l’ID principal comme ID de personne. Une telle utilisation n’est cependant pas obligatoire. Vous pouvez choisir une autre colonne d’identité comme ID de personne.
