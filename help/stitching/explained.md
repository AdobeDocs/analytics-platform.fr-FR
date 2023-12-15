---
title: Fonctionnement de l’assemblage
description: Comprendre le concept de groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
source-git-commit: 2c650cf688112be1e6bf16c0863e743d61f9c35c
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 20%

---

# Fonctionnement de l’assemblage

L’assemblage effectue au moins deux transmissions de données dans un jeu de données donné :

* **Groupement en direct**: tente de grouper chaque accès (événement) au fur et à mesure. Les accès provenant des appareils &quot;nouveaux&quot; au jeu de données (qui ne sont jamais authentifiés) ne sont généralement pas regroupés à ce niveau. Les accès provenant d’appareils déjà reconnus sont immédiatement regroupés.

* **Groupement de relecture**: &quot;relit&quot; les données en fonction des identifiants uniques (identifiants transitoires) appris. Cette étape est l’endroit où les accès provenant d’appareils précédemment inconnus (identifiants persistants) sont regroupés (en identifiants transitoires). Adobe offre deux intervalles de relecture :
   * **Qualité**: les données sont relues chaque jour avec un intervalle de recherche en amont de 24 heures. Cette option présente un avantage car les relectures sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   * **Hebdomadaire**: les données sont lues une fois par semaine avec un intervalle de recherche en amont de 7 jours. Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données désassemblées datant de moins d’une semaine ne sont pas retraitées avant la relecture hebdomadaire suivante.

* **Confidentialité (facultatif)**: lorsque des demandes liées à la confidentialité sont reçues, en plus de la suppression de l’identité demandée, tout regroupement de cette identité entre des événements non authentifiés doit être annulé.

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Un visiteur doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois reconnu, un appareil est assemblé en direct à partir de ce moment.

## Étape 1 : assemblage en direct

L’assemblage en direct tente de regrouper chaque événement au moment de la collecte sur des appareils et canaux connus. Prenons l’exemple suivant, où Bob enregistre différents événements dans le cadre d’un jeu de données d’événement.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après groupement dynamique) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3 périphériques** | | **4 personnes**:<br/>246, Bob, 3579, 81911 |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes. Les événements non authentifiés sur les appareils reconnus sont assemblés en direct.

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements, à l’exception des événements 1, 8, 9 et 10, sont assemblés en direct (ils utilisent tous la variable `Bob` ). L’assemblage en direct &quot;résout&quot; l’identifiant assemblé pour les événements 4, 6 et 12.

Les données différées (données avec un horodatage de plus de 24 heures) sont traitées sur la base du &quot;meilleur effort&quot;, tout en privilégiant l’assemblage de données actives pour une qualité optimale.

## Étape 2 : assemblage de lectures

À intervalles réguliers (une fois par semaine ou une fois par jour, selon l’intervalle de recherche en amont choisi), l’assemblage de relecture recalcule les données historiques en fonction des appareils qu’il reconnaît maintenant. Si un appareil envoie initialement des données alors qu’il n’est pas authentifié, puis se connecte, la réexécution du regroupement lie ces événements non authentifiés à la bonne personne. Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après groupement dynamique) | Identifiant assemblé (après relecture) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **3 périphériques** | | **4 personnes**:<br/>246, Bob, 3579, 81911 | **2 personnes**:<br/>Bob, 3579 |

{style="table-layout:auto"}

L’attribution fonctionne lorsque la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, les événements 1 et 10 sont assemblés à la suite de la relecture, laissant uniquement les événements 8 et 9 désassemblés. Et réduire la mesure des personnes (cumulée) à 2.

## Étape 3 : demande d’accès à des informations personnelles

Lorsque vous recevez une demande d’accès à des informations personnelles, la ligne contenant les informations sur l’utilisateur d’origine est supprimée, ainsi que les identifiants assemblés qui contiennent ces mêmes informations sur la personne. Le tableau suivant représente les mêmes données que ci-dessus, mais montre l’effet qu’a une demande d’accès à des informations personnelles pour Bob sur les données après leur traitement. Les lignes où Bob s’est authentifié sont supprimées (2, 3, 5, 7 et 11), ainsi que la suppression de Bob en tant qu’identifiant transitoire pour les autres lignes.

*Les mêmes données après une demande d’accès à des informations personnelles pour Bob :*

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après groupement dynamique) | Identifiant assemblé (après relecture) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après demande d’accès à des informations personnelles) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Flèche vers la droite](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Flèche vers le bas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Flèche vers le haut](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3 périphériques** | | **4 personnes**:<br/>246, Bob, 3579, 81911 | **2 personnes**:<br/>Bob, 3579 |  | **3 personnes**:<br/>246, 3579, 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## Résumé

* L’assemblage regroupe immédiatement les événements des appareils connus, mais ne regroupe pas immédiatement les événements des appareils nouveaux ou non reconnus.
* Les données sont relues à intervalles réguliers, et modifient les données historiques de la connexion en fonction des appareils qu’elles ont appris à identifier.
* Le groupement et le groupement de relecture en direct sont exécutés sur un jeu de données. Il en résulte un nouveau jeu de données élevé qui est mieux adapté à l’utilisation lorsqu’il est combiné à d’autres jeux de données (par exemple, les données du centre d’appel) pour effectuer des analyses cross-canal.
* Les demandes d’accès à des informations personnelles suppriment les identités qui ont été diffusées aux lignes non authentifiées.
