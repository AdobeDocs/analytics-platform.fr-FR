---
title: Périphériques partagés
description: Explication de la gestion des appareils partagés à l’aide du groupement et d’autres techniques.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
autotag-review: '2026-05-19T09:47:24.777Z'
TQID: 'https://experienceleague.adobe.com/8Xq8mUchtogMLiEuPVv-DWpkWtD5ubJGSQm2SRaZmps'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 726
ht-degree: 16%

---

# Périphériques partagés

Cet article fournit du contexte sur les appareils partagés, explique comment gérer et atténuer les données des appareils partagés à l’aide du [groupement](/help/stitching/overview.md) et comprend l’exposition des appareils partagés dans vos données à l’aide de Query Service.

## Qu’est-ce qu’un appareil partagé ?

Un appareil partagé est un appareil utilisé par plusieurs personnes. Les scénarios courants sont les appareils tels que les tablettes, les appareils utilisés dans les kiosques ou les équipements informatiques partagés par les agents dans un centre d’appels.

Lorsque deux personnes utilisent le même appareil et effectuent toutes deux un achat authentifié, les exemples de données d’événement peuvent ressembler à ceci :

| Événement | Date et heure | Nom de la page | ID d’appareil | Adresse électronique |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | Page d’accueil | `1234` | |
| 2 | 2023-05-12 12:02 | Page produit | `1234` | |
| 3 | 2023-05-12 12:03 | Succès de la commande | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Page produit | `1234` | |
| 5 | 2023-05-12 12:08 | Succès de la commande | `1234` | `cassidy@a.com` |

Comme vous pouvez le voir dans ce tableau, une fois que l’authentification se produit sur les événements 3 et 5, un lien commence à se former entre un identifiant d’appareil et un identifiant de personne. Pour comprendre l’impact de tout effort marketing au niveau d’une personne, ces événements non authentifiés doivent être attribués à la bonne personne.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Améliorer l’analyse centrée sur la personne

Le processus de groupement résout ce problème d’attribution en ajoutant l’identifiant de personne sélectionné (dans l’exemple de données, l’e-mail) aux événements où cet identifiant n’existe pas. L’assemblage tire parti d’un mappage entre les ID d’appareil et les ID de personne pour s’assurer que le trafic authentifié et non authentifié peut être utilisé dans l’analyse, en restant centré sur la personne. Voir [&#x200B; Assemblage &#x200B;](/help/stitching/overview.md) pour plus d’informations.

L’assemblage peut attribuer des données d’appareil partagées à l’aide de l’attribution dernière authentification ou de l’attribution partage d’appareil. Toutes les tentatives d’assemblage d’événements non authentifiés à un utilisateur connu sont non déterministes.


### Attribution de dernière authentification

Last-auth attribue toutes les activités inconnues d’un appareil partagé à l’utilisateur qui s’est authentifié pour la dernière fois. Experience Platform Identity Service crée le graphique en fonction de l’attribution de la dernière authentification et, à ce titre, est utilisé dans le groupement basé sur le graphique. Pour plus d’informations, consultez [Règles de liaison des graphiques d’identités](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details) .

Lorsque l’attribution Dernière authentification est utilisée dans le groupement, les identifiants groupés se résolvent comme illustré dans le tableau ci-dessous.

| Date et heure | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Page produit | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Succès de la commande | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Page produit | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Succès de la commande | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Page d’accueil | `1234` | | `cassidy@a.com` |


### Device-split

La division de l’appareil attribue une activité anonyme d’un appareil partagé à l’utilisateur connu le plus récent, en vérifiant le passé. La division de l’appareil est actuellement utilisée dans le groupement basé sur les champs.

Lorsque l’attribution fractionnée de l’appareil est utilisée dans le groupement, les identifiants groupés se résolvent comme illustré dans le tableau ci-dessous.

| Date et heure | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Page produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Succès de la commande | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Page produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Succès de la commande | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Page d’accueil | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`|
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` |
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` |
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Exposition partagée de l’appareil

Tenez compte de plusieurs facteurs pour comprendre correctement l’omniprésence des appareils partagés dans votre organisation. En outre, comprendre la contribution globale des événements provenant des appareils partagés peut vous aider à comprendre l’impact sur les données d’événement globales utilisées pour l’analyse.

Pour comprendre l’exposition des appareils partagés, vous pouvez envisager d’effectuer les requêtes suivantes.

1. **Identification des appareils partagés**

   Pour comprendre le nombre d’appareils partagés, effectuez une requête qui comptabilise les ID d’appareil associés à deux ID de personne ou plus. Cela permet d’identifier les appareils utilisés par plusieurs personnes.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **Attribution d’événements aux appareils partagés**

   Pour les appareils partagés identifiés, déterminez le nombre total d’événements qui peuvent être attribués à ces appareils. Cette attribution permet à insight de comprendre l’impact des appareils partagés sur vos données et les implications pour l’analyse.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **Identifier les événements anonymes sur les appareils partagés**

   Parmi les événements attribués aux appareils partagés, identifiez ceux pour lesquels il manque un ID de personne, ce qui indique les événements anonymes. L’algorithme que vous choisissez (par exemple, last-auth, device-split ou ECID-reset) pour améliorer la qualité des données affecte ces événements anonymes.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **Calculer l’exposition à partir d’une mauvaise classification d’événement**

   Enfin, évaluez l’exposition à laquelle chaque client peut être confronté en raison d’une mauvaise classification de l’événement. Calculer le pourcentage d&#39;événements anonymes sur le total des événements pour chaque appareil partagé. Cela permet de comprendre l’impact potentiel sur la précision des données client.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
