---
title: Périphériques partagés
description: Explication de la gestion des appareils partagés à l’aide du groupement et d’autres techniques.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: c0dae5f1255a986df5ab2551aabdf1bd0727e949
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 7%

---

# Périphériques partagés

Cet article fournit du contexte sur les appareils partagés, comment gérer et atténuer les données des appareils partagés à l’aide de [assemblage](/help/stitching/overview.md) et comprendre l’exposition des appareils partagés dans vos données à l’aide de Query Service.

## Qu’est-ce qu’un appareil partagé ?

Un appareil partagé est un appareil utilisé par plusieurs personnes. Les scénarios courants sont les appareils tels que les tablettes, les appareils utilisés dans les kiosques ou les équipements informatiques partagés par les agents dans les centres d’appel.

Lorsque deux personnes utilisent le même appareil et effectuent tous deux un achat, les exemples de données d’événement peuvent se présenter comme suit :

| Événement | Horodatage | Nom de la page | ID d’appareil | Adresse électronique |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | Page d’accueil | `1234` | |
| 2 | 2023-05-12 12:02 | Page de produit | `1234` | |
| 3 | 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Page de produit | `1234` | |
| 5 | 2023-05-12 12:08 | Succès des commandes | `1234` | `cassidy@a.com` |

Comme vous pouvez le voir dans ce tableau, une fois l’authentification effectuée sur les événements 3 et 5, un lien commence à se former entre un identifiant d’appareil et un identifiant de personne. Pour comprendre l’impact de toute action marketing au niveau d’une personne, ces événements non authentifiés doivent être attribués à la bonne personne.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Améliorer l’analyse centrée sur les personnes

Le processus de groupement résout ce problème d’attribution en ajoutant l’identifiant de personne sélectionné (dans les données d’exemple, l’email) aux événements où cet identifiant n’existe pas. L’assemblage tire parti d’un mappage entre les ID d’appareil et les ID de personne pour s’assurer que le trafic authentifié et non authentifié peut être utilisé dans l’analyse, ce qui le rend centré sur les personnes. Voir [Assemblage](/help/stitching/overview.md) pour plus d’informations.

L’assemblage peut attribuer des données d’appareil partagées à l’aide de l’attribution Dernière authentification ou de l’attribution partagée par appareil. Toutes les tentatives de regroupement d’événements non authentifiés à un utilisateur connu sont non déterministes.


### Attribution Dernière authentification

La dernière authentification attribue toutes les activités inconnues d’un appareil partagé à l’utilisateur qui s’est authentifié pour la dernière fois. Le service Identity Experience Platform crée le graphique en fonction de l’attribution Dernière authentification et, en tant que tel, est utilisé dans le groupement basé sur les graphiques. Pour plus d’informations, consultez la [présentation des règles de liaison de graphiques d’identités](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) .

Lorsque l’attribution Dernière authentification est utilisée dans le groupement, les identifiants regroupés sont résolus comme illustré dans le tableau ci-dessous.

| Horodatage | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Page de produit | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Page de produit | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Succès des commandes | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Page d’accueil | `1234` | | `cassidy@a.com` |


### Partage de l’appareil

Attributs de partage d’appareil : activité anonyme d’un appareil partagé à l’utilisateur le plus proche de l’activité anonyme. Le partage d’appareil est la méthode privilégiée pour les cas d’utilisation analytique, car le partage d’appareil accorde du crédit pour l’activité non authentifiée et authentifiée à la personne connue la plus proche. Le partage d’appareil est actuellement utilisé dans le groupement basé sur les champs.

Lorsque l’attribution fractionnée par l’appareil est utilisée dans le groupement, les identifiants regroupés sont résolus comme illustré dans le tableau ci-dessous.

| Horodatage | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Page de produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Page de produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Succès des commandes | `1234` | `cassidy@a.com` | `cassidy@a.com` |
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

## Exposition des appareils partagés

Tenez compte de plusieurs facteurs pour comprendre correctement l’omniprésence des appareils partagés dans votre entreprise. En outre, la compréhension de la contribution globale des événements provenant d’appareils partagés peut vous aider à comprendre l’impact sur les données d’événement globales utilisées pour l’analyse.

Pour comprendre l’exposition de l’appareil partagé, vous pouvez envisager d’exécuter les requêtes suivantes.

1. **Identification des appareils partagés**

   Pour comprendre le nombre d’appareils partagés, effectuez une requête qui comptabilise les identifiants d’appareil associés à deux ou plusieurs identifiants de personne. Cela permet d’identifier les périphériques utilisés par plusieurs individus.

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


2. **Attribution des événements aux appareils partagés**

   Pour les appareils partagés identifiés, déterminez le nombre d’événements sur le total pouvant être attribués à ces appareils. Cette attribution fournit des informations sur l’impact des appareils partagés sur vos données et sur les implications pour l’analyse.

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

   Parmi les événements attribués aux appareils partagés, identifiez le nombre de personnes dépourvues d’un ID de personne, indiquant les événements anonymes. L’algorithme que vous choisissez (dernier authentification, division d’appareil ou réinitialisation d’ECID, par exemple) pour améliorer la qualité des données affecte ces événements anonymes.

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

4. **Calcul de l&#39;exposition à partir d&#39;une mauvaise classification d&#39;événement**

   Enfin, évaluez l’exposition que chaque client peut rencontrer en raison d’une mauvaise classification des événements. Calculez le pourcentage d’événements anonymes par rapport au total des événements pour chaque appareil partagé. Cela permet de comprendre l’impact potentiel sur la précision des données client.

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
