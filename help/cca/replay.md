---
title: Fonctionnement des relectures
description: Comprendre le concept de « relecture » dans l’Analyse cross-canal
exl-id: 1100043a-4e4f-4dbc-9cfc-9dcba5db5f67
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: 4c6e968272b554188243b772bd159fe8174b3c3b
workflow-type: ht
source-wordcount: '578'
ht-degree: 100%

---


# Fonctionnement des relectures

L’Analyse cross-canal effectue deux transmissions de données sur une connexion donnée :

* **Assemblage en direct** :l’AAC tente d’assembler les événements au fur et à mesure qu’ils arrivent. Les nouveaux appareils connectés au jeu de données qui ne se sont jamais connectés ne sont généralement pas assemblés à ce niveau. Les appareils reconnus sont groupés immédiatement.
* **Relire** : l’CCA « relit » les données en fonction des identifiants uniques qu’elle a appris. C’est à ce stade que les nouveaux appareils de la connexion sont assemblés. Adobe offre deux intervalles de relecture :
   * Quotidien : les données sont relues chaque jour avec une période de recherche arrière 24 heures sur 24. Cette option présente un avantage, car les relectures sont beaucoup plus fréquentes, mais les personnes non authentifiées doivent s’authentifier le jour même où elles visitent votre site.
   * Hebdomadaire : les données sont lues une fois par semaine avec une période de recherche arrière de 7 jours. Cette option présente un avantage qui permet aux sessions non authentifiées de disposer d’un temps d’authentification beaucoup moins stricte. Toutefois, les données de moins d’une semaine ne sont pas assemblées.

Les données au-delà de l’intervalle de recherche en amont ne sont pas relues. Une personne doit s’authentifier dans un intervalle de recherche en amont donné pour qu’une visite non authentifiée et une visite authentifiée soient identifiées ensemble. Une fois reconnu, un appareil est assemblé en direct à partir de ce moment.

## Étape 1 : Assemblage en direct

L’CCA tente d’assembler chaque événement au moment de la collecte sur des appareils et des canaux connus. Prenons l’exemple suivant, où Bob utilise deux canaux différents.

*Données telles qu’elles apparaissent le jour de leur collecte :*

| Horodatage | Identifiant persistant du jeu de données web | Identifiant temporaire de jeu de données web | Identifiant d’agent du centre d’appel | Identifiant d’agent utilisé | Explication de l’événement | Mesure Personnes (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visite votre site sur son ordinateur de bureau, non authentifié | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob se connecte sur son ordinateur de bureau | `2` (246 et Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob appelle le service client | `2` (246 et Bob) |
| `4` | `3579` | - | - | `3579` | Bob accède à votre site sur son appareil mobile, non authentifié | `3` (246, Bob et 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob se connecte sur son appareil mobile | `3` (246, Bob et 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob rappelle le service client | `3` (246, Bob et 3579) |
| `7` | `246` | - | - | `Bob` | Bob accède à nouveau à votre site depuis son ordinateur de bureau, non authentifié | `3` (246, Bob et 3579) |

Les accès authentifiés et non authentifiés sur les nouveaux appareils sont (temporairement) comptabilisés comme des personnes distinctes. Les événements non authentifiés sur les appareils reconnus sont assemblés en direct.

L’attribution fonctionne dès que la variable personnalisée d’identification est liée à un appareil. Dans l’exemple ci-dessus, tous les événements, à l’exception des événements 1 et 4, sont assemblés en direct (ils utilisent tous l’identifiant `Bob`). L’attribution fonctionne sur les événements 1 et 4 après l’assemblage de lectures.

## Étape 2 : assemblage de lectures

À intervalles réguliers (une fois par semaine ou une fois par jour selon la période de recherche arrière choisie), l’CCA recalcule les données historiques en fonction des appareils qu’elle reconnaît maintenant. Si un appareil envoie initialement des données alors qu’il n’est pas authentifié et se connecte ensuite, l’CCA lie ces événements non authentifiés à la bonne personne. Le tableau suivant représente les mêmes données que ci-dessus, mais affiche des nombres différents à cause de la relecture des données.

*Les mêmes données après relecture :*

| Horodatage | Identifiant persistant du jeu de données web | Identifiant temporaire de jeu de données web | Identifiant d’agent du centre d’appel | Identifiant d’agent utilisé | Explication de l’événement | Mesure Personnes (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visite votre site sur son ordinateur de bureau, non authentifié | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob se connecte sur son ordinateur de bureau | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob appelle le service client | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accède à votre site sur son appareil mobile, non authentifié | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob se connecte sur son appareil mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob rappelle le service client | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob accède à nouveau à votre site depuis son ordinateur de bureau, non authentifié | `1` (Bob) |

>[!NOTE]
>
>Seules les données du jeu de données du site Web sont relues. Le jeu de données du centre dʼappel reste inchangé, mais correspond lorsque le bon identifiant de personne est utilisé.

## Résumé

* L’CCA assemble immédiatement les appareils connus, mais n’assemble pas immédiatement les appareils nouveaux ou non reconnus.
* Les données sont relues à intervalles réguliers, et modifient les données historiques de la connexion en fonction des appareils qu’elles ont appris à identifier.
