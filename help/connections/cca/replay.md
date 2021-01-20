---
title: Fonctionnement des relectures
description: Comprendre le concept de "relecture" dans Analytics sur plusieurs Canaux
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 16%

---


# Fonctionnement des relectures

Analytics sur plusieurs Canaux effectue deux passes de données sur une connexion donnée :

* **Densité** en direct : Le CCA tente d&#39;associer chaque accès au moment où il intervient. Les nouveaux périphériques réseau du jeu de données qui ne se sont jamais connectés ne sont généralement pas assemblés à ce niveau. Les appareils reconnus sont groupés immédiatement.
* **Réexécuter** : La DPA &quot;relaie&quot; les données en fonction des identifiants uniques qu&#39;elle a appris. C&#39;est à cette étape que les nouveaux périphériques de la connexion sont assemblés. Adobe offres deux intervalles de relecture :
   * Quotidien : Les données sont relayées chaque jour avec une fenêtre de recherche 24 heures sur 24. Cette option présente un avantage car les réexécutions sont beaucoup plus fréquentes, mais les visiteurs non authentifiés doivent s’authentifier le jour même où ils visitent votre site.
   * Hebdomadaire : Les données sont relayées une fois par semaine avec une fenêtre de recherche de 7 jours. Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup plus court. Toutefois, les données de moins d’une semaine ne sont pas assemblées.

## Étape 1 : Accrochage en direct

L&#39;ACC tente d&#39;assembler chaque événement au moment de la collecte sur des dispositifs et des canaux connus. Prenons l’exemple suivant, où Bob utilise deux canaux différents.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Horodatage | ID persistant du jeu de données Web | ID temporaire de jeu de données Web | ID de personne du centre d&#39;appels | Identifiant de personne utilisé | Explication de l’accès | Mesure Personnes (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visite votre site sur son bureau, sans authentification | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob se connecte sur le bureau | `2` (246 et Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob appelle le service à la clientèle | `2` (246 et Bob) |
| `4` | `3579` | - | - | `3579` | Bob accède à votre site sur son périphérique mobile, sans authentification | `3` (246, Bob et 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob se connecte via mobile | `3` (246, Bob et 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob appelle de nouveau le service à la clientèle | `3` (246, Bob et 3579) |
| `7` | `246` | - | - | `Bob` | Bob se rend à nouveau sur votre site sur son bureau, sans s’authentifier | `3` (246, Bob et 3579) |

Les événements non authentifiés et authentifiés sur les nouveaux périphériques sont comptabilisés comme des personnes distinctes (temporairement). Les événements non authentifiés sur les périphériques reconnus sont assemblés en direct.

L’attribution fonctionne dès que la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements à l’exception des événements 1 et 4 sont assemblés en direct (ils utilisent tous l’identifiant `Bob`). L’attribution fonctionne sur les événements 1 et 4 après l’assemblage de relecture.

## Étape 2 : Relancer l’assemblage

À intervalles réguliers (une fois par semaine ou une fois par jour selon la fenêtre de recherche choisie), la DPA recalcule les données historiques en fonction des dispositifs qu&#39;elle reconnaît maintenant. Si un dispositif envoie initialement des données alors qu&#39;il n&#39;est pas authentifié, puis se connecte, CCA lie ces événements non authentifiés à la bonne personne. Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Horodatage | ID persistant du jeu de données Web | ID temporaire de jeu de données Web | ID de personne du centre d&#39;appels | Identifiant de personne utilisé | Explication de l’accès | Mesure Personnes (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visite votre site sur son bureau, sans authentification | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob se connecte sur le bureau | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob appelle le service à la clientèle | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accède à votre site sur son périphérique mobile, sans authentification | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob se connecte via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob appelle de nouveau le service à la clientèle | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob se rend à nouveau sur votre site sur son bureau, sans s’authentifier | `1` (Bob) |

## Résumé

* L&#39;ACC pivote immédiatement les dispositifs connus, mais ne rassemble pas immédiatement les dispositifs nouveaux ou non reconnus.
* Les données sont relues à intervalles réguliers et modifient les données historiques de la connexion en fonction des périphériques qu’elle a appris à identifier.
