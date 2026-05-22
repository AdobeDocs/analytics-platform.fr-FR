---
title: AAID, ECID, AACUSTOMID et le connecteur source Analytics
description: Découvrez comment le connecteur source Analytics traite les champs d’identité dans Adobe Analytics.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
autotag-review: '2026-05-19T07:16:36.730Z'
TQID: 'https://experienceleague.adobe.com/8ijMa5NbkCx0H48qSZkYrgTDRaVCSBmO9twZvWFJ83o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 624
ht-degree: 96%

---

# AAID, ECID, AACUSTOMID et le connecteur source Analytics

Les données Adobe Analytics contiennent plusieurs champs d’identité. Le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) traite de manière distincte trois champs d’identité importants : AAID, ECID et AACUSTOMID.

## AAID

L’ID Adobe Analytics (AAID) représente l’identifiant principal de l’appareil dans Adobe Analytics. Il existe systématiquement dans chaque événement transmis par le biais du connecteur source Analytics. L’AAID est parfois appelé l’« ID Analytics hérité » ou l’ID de cookie `s_vi`. Cependant, un AAID est créé même en absence du cookie `s_vi`. L’AAID est représenté par les colonnes `post_visid_high/post_visid_low` dans les [flux de données Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr#columns%2C-descriptions%2C-and-data-types).

L’AAID est transformé en `HEX(post_visid_high) + "-" + HEX(post_visid_low)` dans le connecteur source Analytics. Le champ AAID d’un événement donné contient une identité unique qui peut être de l’un des types décrits dans l’[ordre des opérations pour les ID Analytics](https://experienceleague.adobe.com/fr/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations). (Dans une suite de rapports entière, l’AAID peut contenir plusieurs types parmi les événements. Le type de chaque événement est indiqué dans la colonne `post_visid_type` des flux de données Analytics.) Voir aussi : [Référence des colonnes de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html).

## ECID

L’ECID (ID Experience Cloud), également parfois appelé MCID (ID Marketing Cloud), est un champ d’identifiant de l’appareil distinct qui est renseigné dans Adobe Analytics lorsqu’Analytics est implémenté à l’aide du [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=fr). L’ECID est représenté par la colonne `mcvisid` dans les flux de données Adobe Analytics.

Si un ECID existe sur un événement, l’AAID peut être basé sur l’ECID selon que le [délai de grâce](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html) d’Analytics est configuré ou non. Voir également : [Requêtes d’ID Analytics et Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html).

## AACUSTOMID

L’AACUSTOMID est un champ d’identifiant distinct qui est renseigné dans Adobe Analytics en fonction de l’utilisation de la variable `s.VisitorID` dans l’implémentation d’Analytics. L’AACUSTOMID est représenté par la colonne `cust_visid` dans les flux de données Adobe Analytics. En présence de l’AACUSTOMID, l’AAID sera basé sur l’AACUSTOMID. (L’AACUSTOMID surpasse tous les autres identifiants comme déterminé par l’ordre des opérations mentionné ci-dessus.)

## Traitement de ces identités par le connecteur source Analytics

Le connecteur source Analytics transmet ces identités à Adobe Experience Platform en tant que XDM sous la forme suivante :

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Ces champs ne sont pas marqués comme des identités. À la place, les mêmes identités sont copiées dans le **_mappage d’identité_** de XDM en tant que paires clé-valeur de la façon suivante :

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

Les éléments situés entre &lt;> chevrons représentent les endroits où les valeurs réelles devraient apparaître.

Dans le mappage d’identité :

* En présence d’un ECID, l’identité est marquée comme l’identité principale de l’événement. Remarque : dans ce cas, l’AAID peut se baser sur l’ECID conformément aux informations ci-dessus.
Dans le cas contraire, l’AAID est marqué comme étant l’identité principale de l’événement.
* L’AACUSTOMID n’est jamais marqué comme l’ID principal de l’événement. Cependant, en présence d’un AACUSTOMID, l’AAID est basé sur l’AACUSTOMID conformément au processus décrit ci-dessus.

Lorsque l’identité ou les identités sont copiées dans `identityMap`, `endUserIDs._experience.mcid.namespace.code` est également défini sur le même événement :

* Si AAID est présent, `endUserIDs._experience.aaid.namespace.code` est définie sur « AAID ».
* Si ECID est présent, `endUserIDs._experience.mcid.namespace.code` est définie sur « ECID ».
* Si AACUSTOMID est présent, `endUserIDs._experience.aacustomid.namespace.code` est définie sur « AACUSTOMID ».

## Customer Journey Analytics et ID principal

En ce qui concerne Customer Journey Analytics, la définition de l’ID principal n’importe que si vous décidez d’utiliser l’ID principal comme ID de personne. Une telle utilisation n’est cependant pas obligatoire. Vous pouvez choisir une autre colonne d’identité comme ID de personne.
