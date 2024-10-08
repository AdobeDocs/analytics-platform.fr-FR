---
title: Appareils partagés
description: Explication de la gestion des appareils partagés à l’aide du groupement et d’autres techniques.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
source-git-commit: 1a5646700dba6362a35158890f2917fc472fbddd
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 5%

---


# Appareils partagés

Cet article fournit du contexte sur les appareils partagés, comment gérer et atténuer les données des appareils partagés à l’aide du groupement et comprendre l’exposition des appareils partagés dans vos données à l’aide de Query Service.

## Qu’est-ce qu’un appareil partagé ?

Un appareil partagé est un appareil utilisé par plusieurs personnes. Les scénarios courants sont les appareils tels que les tablettes, les appareils utilisés dans les kiosques ou les équipements informatiques partagés par les agents dans les centres d’appel.

Lorsque deux personnes utilisent le même appareil et effectuent tous deux un achat, les exemples de données d’événement peuvent se présenter comme suit :

| Horodatage | Nom de la page | ID d’appareil | Adresse électronique |
|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | |
| 2023-05-12 12:02 | Page de produit | `1234` | |
| 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` |
| 2023-05-12 12:07 | Page de produit | `1234` | |
| 2023-05-12 12:08 | Succès des commandes | `1234` | `cassidy@a.com` |

Les événements de succès de commande (achat) attribuent les données de manière précise au message électronique correct. L’impact de cette affectation sur votre analyse dépend de la manière dont vous effectuez l’analyse :

- Approche axée sur l’appareil : analyse effectuée à l’aide de l’identifiant de l’appareil. Grâce à cette approche, les données authentifiées et non authentifiées sont incluses dans l’analyse. Toutefois, cette approche ne permet pas d’effectuer une analyse basée sur des personnes supplémentaires.
- Approche axée sur la personne : analyse effectuée à l’aide de l’adresse électronique ou d’un autre identifiant de personne. Avec cette approche, seuls les événements authentifiés sont inclus dans l’analyse. Cette approche ne fournit pas une vue d’ensemble complète du parcours client, y compris l’acquisition.

## Améliorer l’analyse centrée sur les personnes

L’exemple de données est un mélange d’activité authentifiée et non authentifiée pour le même appareil. Le défi consiste à affecter une personne au trafic non authentifié, de sorte que vous puissiez effectuer une analyse centrée sur la personne et empêcher Customer Parcours Analytics de supprimer les activités qui n’ont pas de valeur d’identification de personne. Pour résoudre ce problème, vous disposez de deux options : vous pouvez utiliser l’assemblage ou mettre en oeuvre la fonctionnalité de réinitialisation d’ECID. Les deux options sont décrites plus en détail dans les sections ci-dessous.

### Groupement

Le processus d’assemblage résout le problème de l’approche axée sur la personne. L’assemblage ajoute l’identifiant de personne sélectionné (dans les exemples de données, l’email) aux événements dans lesquels cet identifiant n’existe pas. L’assemblage tire parti d’un mappage entre les ID d’appareil et les ID de personne pour s’assurer que le trafic authentifié et non authentifié peut être utilisé dans l’analyse, ce qui le rend centré sur les personnes. Voir [Assemblage](/help/stitching/overview.md) pour plus d’informations.

L’assemblage peut attribuer des données d’appareil partagées à l’aide de l’attribution Dernière authentification ou de l’attribution partagée par appareil. Cependant, les modifications de mise en oeuvre via la réinitialisation d’ECID peuvent également s’appliquer aux appareils partagés.


#### Attribution Dernière authentification

La dernière authentification attribue toutes les activités inconnues d’un appareil partagé à l’utilisateur qui s’est authentifié pour la dernière fois. La dernière authentification est utilisée dans l’Audience Manager. Il s’agit de l’approche privilégiée pour les cas d’utilisation de Real-time Customer Data Profile. Le service Identity Experience Platform crée le graphique en fonction de l’attribution Dernière authentification et, en tant que tel, est utilisé dans le groupement basé sur les graphiques. Pour plus d’informations, consultez la [présentation des règles de liaison de graphiques d’identités](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) .

Lors de l’utilisation de l’attribution de dernière authentification dans le groupement, les identifiants regroupés sont résolus comme illustré dans le tableau ci-dessous.

| Horodatage | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Page de produit | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Page de produit | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Succès des commandes | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Page d’accueil | `1234` | | `cassidy@a.com` |


#### Partage de l’appareil

Attributs de partage d’appareil : activité anonyme d’un appareil partagé à l’utilisateur le plus proche de l’activité anonyme. Le partage d’appareil est actuellement utilisé dans le groupement basé sur les champs. Le partage d’appareil est la méthode privilégiée pour les cas d’utilisation analytique, car le partage d’appareil accorde du crédit pour l’activité non authentifiée et authentifiée à la personne connue la plus proche. Le partage d’appareil est actuellement utilisé dans le groupement basé sur les champs.

Lors de l’utilisation de l’attribution fractionnée par l’appareil dans le groupement, les identifiants regroupés sont résolus comme illustré dans le tableau ci-dessous.

| Horodatage | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Page de produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Page de produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Succès des commandes | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Page d’accueil | `1234` | | `cassidy@a.com` |


### Réinitialisation ECID

Comme le nom l’implique, la réinitialisation d’ECID met en oeuvre une fonctionnalité qui réinitialise l’ECID sur un déclencheur prédéterminé, dans la plupart des cas un événement de connexion ou de déconnexion. Avec cette mise en oeuvre, un seul appareil obtient un nouvel ECID chaque fois que le déclencheur prédéterminé se déclenche. Essentiellement, cette réinitialisation force l’appareil à devenir un *nouveau périphérique* encore et encore du point de vue des données. La réinitialisation d’ECID permet également d’empêcher les appareils partagés de s’afficher dans les données. Aucun algorithme supplémentaire n’est requis, mais vous avez la responsabilité de mettre en oeuvre le signal de réinitialisation d’ECID dans le cadre de votre implémentation de collecte de données d’Adobe.


Lors de l’utilisation de la réinitialisation d’ECID, les identifiants regroupés sont résolus comme illustré dans le tableau ci-dessous.

| Horodatage | Nom de la page | ID d’appareil | Adresse électronique | ID regroupé |
|---|---|---|---|---|
| 2023-05-12 12:01 | Page d’accueil | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Page de produit | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Succès des commandes | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Page de produit | 5678 | | `cassidy@a.com` |
| 2023-05-12 12:08 | Succès des commandes | 5678 | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Page d’accueil | 5678 | | `cassidy@a.com` |

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

   Pour les appareils partagés identifiés, déterminez le nombre d’événements sur le total pouvant être attribués à ces appareils. Cela permet d’avoir un aperçu de l’impact des appareils partagés sur vos données et des implications pour l’analyse.

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

   Parmi les événements attribués aux appareils partagés, identifiez le nombre de personnes dépourvues d’un ID de personne, indiquant les événements anonymes. L’algorithme que vous choisissez (dernier algorithme, division d’appareil ou réinitialisation d’ECID, par exemple) pour améliorer la qualité des données affecte ces événements anonymes.

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


