---
title: Implémenter des informations de conversation
description: Découvrez comment instrumenter votre application ou service d’agent pour les informations de conversation.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 7%
---
# Implémenter des informations de conversation

Pour produire des données de conversation sous la forme d’événements d’expérience XDM et vous assurer que ces événements d’expérience de conversation aboutissent dans Adobe Experience Platform sous la forme de jeux de données, instrumentez votre application d’agent ou service pour utiliser des informations de conversation.

Cet article décrit les étapes de mise en œuvre requises.

>[!PREREQUISITES]
>
>* Vous devez disposer d’un environnement Experience Platform (organisation et sandbox) pour collecter les données.
>* Votre organisation Adobe doit être activée pour les groupes de champs agent expérimental et conversation.
>

## Schéma et jeux de données

Configurez des jeux de données pour les principaux événements de conversation : invite, réponse, retour d’informations. Ces jeux de données peuvent être basés sur le même schéma (par exemple, un schéma de conversation Insights générique) ou sur des schémas individuels.
Vous pouvez définir des jeux de données distincts pour les invites, les réponses et les commentaires ou combiner les données dans des jeux de données. Par exemple, utilisez un jeu de données pour les invites et les réponses et un autre pour les commentaires. Vous pouvez également utiliser un seul jeu de données pour tous les événements de conversation.

Le schéma utilisé pour les jeux de données d’invite, de réponse et de commentaires doit étendre le schéma de base Événement d’expérience XDM avec les groupes de champs obligatoires. Et peut étendre le schéma de base Événement d’expérience XDM à d’autres groupes de champs.

### Groupe de champs Informations sur l’agence

Le groupe de champs **[!UICONTROL Informations agentiques]** est un groupe de champs obligatoire qui utilise l’objet `agenticExperience`.

+++ Détails

| Chemin Du Champ (Notation Par Points) | Type | Exemple de valeur | Notes |
|---|---|---|---|
| `conciergeID` | string | `"concierge-abc123"` | **Nouveau.** Identifiant unique de concierge |
| `name` | string | `"Brand Concierge"` | Nom de concierge combinant un ensemble d’agentes et d’agents |
| `version` | string | `"1.0.0"` | Version de concierge combinant un ensemble d’agentes et d’agents |
| `environment` | string | `"prod"` | Environnement d’origine de cet événement (développement, évaluation, production) |
| `mode` | string | `"release"` | Mode dans lequel se trouve l’agent (test, aperçu, version finale) |
| `agents[]` | tableau | Voir l’objet agent ci-dessous | Tableau des agents utilisés |
| `agents[].agentID` | string | `"agent-001"` | **Nouveau.** Identifiant unique de l’agent, référencé par le `skills[].agentID` ci-dessous |
| `agents[].name` | string | `"Chatbot Assistant"` | Nom de l’agent |
| `agents[].version` | string | `"2.1.3"` | Version de l’agent |
| `agents[].score` | number | `0.92` | Score de confiance de l’agent dans ses valeurs renvoyées |
| `agents[].skills[]` | tableau | Voir objet de compétence ci-dessous | **Obsolète** — Utilisez plutôt le tableau de `skills[]` de niveau supérieur ci-dessous, qui possède la liste complète ordonnée des appels de compétences et les lie chacun à son agent via `agentID` |
| `agents[].skills[].name` | string | `"Intent Recognition"` | Nom de la compétence (tableau obsolète) |
| `agents[].skills[].version` | string | `"1.0.0"` | Version de la compétence (tableau obsolète) |
| `agents[].skills[].score` | number | `0.95` | Score de confiance des compétences (0-1) (tableau obsolète) |
| `agents[].skills[].parameters[]` | tableau | Voir les paramètres ci-dessous | Paramètres envoyés à la compétence (paires clé-valeur) (tableau obsolète) |
| `agents[].skills[].parameters[].key` | string | `"language"` | Clé paramètre |
| `agents[].skills[].parameters[].value` | string | `"en-US"` | Valeur du paramètre |
| `skills[]` | tableau | Voir l’objet d’appel de compétence ci-dessous | **Nouveau, expérimental.** Liste complète et ordonnée des appels de compétences pour cette expérience, pour tous les agents. Remplace le tableau de `agents[].skills[]` par agent obsolète |
| `skills[].skillID` | string | `"skill-intent-recognition"` | Identifiant de la définition de compétence appelée |
| `skills[].skillInvocationID` | string | `"inv-9f2a-001"` | Identifiant unique de cet appel de compétence individuel, cohérent même avec les rediffusions. Clé de déduplication lors de la fusion de tableaux de compétences en aval |
| `skills[].name` | string | `"Intent Recognition"` | Nom de la compétence appelée |
| `skills[].version` | string | `"1.0.0"` | Version de la compétence appelée |
| `skills[].agentID` | string | `"agent-001"` | Identifiant de l’agent qui a invoqué cette compétence, en corrélation avec `agents[].agentID`. Regroupement des consommateurs clés utilisés pour classer les compétences au sein d’un agent, puisque les sous-agents s’exécutent en parallèle |
| `skills[].invocationSource` | string | `"main"` | Appelée par la boucle agentic principale (`main`) ou par un sous-agent (`subagent`) |
| `skills[].score` | number | `0.95` | Score résultant de la mise en correspondance de la compétence |
| `skills[].failed` | booléen | `false` | Indicateur signalant l’échec de l’exécution de la compétence |
| `skills[].errorReason` | string | `"timeout"` | Motif de l’échec de la compétence, lorsque `failed` est vrai |
| `skills[].sequenceNumber` | entier | `1` | Augmentation monotone de l’index de cette compétence au sein d’une exécution d’agent unique, et non globale, car les sous-agents s’exécutent en parallèle. Les consommateurs commandent par `agentID`, puis par `sequenceNumber`, puis `timestamp` comme brise-égalité. Facultatif |
| `skills[].timestamp` | chaîne (date-heure) | `"2026-09-11T00:03:15Z"` | Heure à laquelle la compétence a été invoquée, ISO 8601 UTC. Clé de classement utilisée après `sequenceNumber`. Les producteurs doivent toujours remplir ce champ |
| `skills[].skillSource` | string | `"inline"` | Comment la définition de compétence a été diffusée au moment de l’exécution : `inline` (chargée en ligne dans le contexte) ou `deferred` (chargée à la demande) |
| `skills[].executionContext` | string | `"inline"` | Où la compétence s’exécute par rapport à l’agent appelant : `inline` ou `forked` (s’exécute dans un contexte de sous-agent dupliqué) |
| `skills[].reasoning.narration` | string | `"Recognized an intent to verify a geography fact"` | Explication en langage naturel du nom de cette compétence |
| `skills[].parameters[]` | tableau | Voir les paramètres ci-dessous | Paramètres transmis à la compétence |
| `skills[].parameters[].key` | string | `"language"` | Clé paramètre |
| `skills[].parameters[].value` | string | `"en-US"` | Valeur du paramètre |

+++

Pour implémenter des événements qui propagent le groupe de champs Informations sur l’agence avec des données, vous devez vérifier les points suivants :

* Configuration de l’agent

  * Chaque agent possède une combinaison unique d’agentID, de nom et de version.
  * Les scores des agents sont normalisés entre `0.0` et `1.0`.
  * Utilisez l’`agentID` pour référencer les agents par appel de compétence.

* Appels de compétences

  * Émettez une seule entrée par appel de compétence, sur tous les agents, au lieu d’imbriquer les compétences sous chaque agent.
  * Renseignez skillInvocationID afin que la fusion en aval puisse supprimer les événements rediffusés en double.
  * Commander correctement les consommateurs. Regroupez par `agentID`, puis triez par `sequenceNumber`, en revenant à `timestamp`. Un ordre est nécessaire, car les sous-agents peuvent s’exécuter en parallèle
  * Utilisez `invocationSource` et `executionContext` pour distinguer les compétences principales des compétences de sous-agent et l’exécution en ligne des exécutions dupliquées.
  * Évitez d’utiliser le tableau de `agents[].skills[]` obsolète. Si vous avez utilisé le tableau dans le passé, traitez-le comme un objet en lecture seule.

* Paramètres de compétence

  * Les paramètres utilisent le type de données clé-valeur XDM d’Adobe ainsi que des types de paramètres courants pour les paramètres de langue, les seuils et les configurations de modèle. Par exemple : `"key":"language", "value":"en-US"`.

+++ Exemple d’utilisation du groupe de champs Informations sur l’agence 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### Groupe de champs Événement de conversation

Le groupe de champs **[!UICONTROL Événement de conversation]** est un groupe de champs obligatoire qui utilise l’objet `conversation`.

L’objet de conversation capture les données pour :

#### Conversation

Un `conversationID` unique identifie une conversation. Par exemple : `conversationID = "conv-001"`. Le schéma prend également en charge `conversationName`. Nom lisible par l’utilisateur qui décrit le contexte global de la conversation, tel que : `France Geography Q&A`.

Le `conversationID` permet de regrouper tous les événements de rotation associés dans la même expérience de conversation.

#### Tourner

Un virage est un cycle d’interaction au sein d’une conversation.

`turnID` Un `turnID` unique identifie un virage. Par exemple :

`conversationID = "conv-001"`
`turnID = "turn-001"`

Les mêmes `conversationID` et `turnID` sont utilisés pour corréler l’invite, la réponse et le retour d’informations associés à ce virage. Cette corrélation fonctionne entre les enregistrements diffusés séparément ou qui se retrouvent dans différents jeux de données.


#### Invite

Une invite correspond à l’entrée envoyée à l’agent. Dans la plupart des scénarios client, cette entrée correspond à la question, à la requête, à l’instruction ou au message de l’utilisateur ou de l’utilisatrice.

L&#39;invite utilise la représentation suivante : `conversation.prompt`

Les champs d’invite importants sont les suivants :

| Champ | Signification |
|---|---|
| `prompt.source` | Qui ou quoi a généré l’invite, généralement l’utilisateur final. |
| `prompt.raw[]` | Un ou plusieurs segments de contenu brut. |
| `prompt.raw[].text` | Le texte ou le contenu réel de l’invite. |
| `prompt.raw[].purpose` | Objet du contenu, tel que l’entrée utilisateur ou le lien. |

Une invite peut contenir plusieurs segments bruts. Par exemple, un utilisateur ou une utilisatrice saisit du texte et inclut une URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### Réponse

Une réponse correspond au contenu renvoyé par l’agent ou une autre partie répondant.

`conversation.response` Un `responseID` unique représente la réponse.

Les champs de réponse importants sont les suivants :

| Champ | Signification |
|---|---|
| `response.source` | Qui ou quoi a produit la réponse. |
| `response.raw[]` | Un ou plusieurs segments de contenu de réponse |
| `response.raw[].text` | Texte ou contenu de la réponse. |
| `response.raw[].purpose` | Objet du segment de contenu. |

Les types de sources documentés sont les suivants :

| Source | Signification |
|---|----|
| `bot` | Réponse automatisée de l’agent. |
| `canned` | Réponse prédéfinie ou modélisée. |
| `concierge` | Réponse de l’agent humain. |
| `end-user` | Contenu généré par l’utilisateur humain, le cas échéant. |

#### Commentaires

Le retour d’informations est l’évaluation ou la réaction explicite de l’utilisateur ou de l’utilisatrice à l’interaction.

La structure de rétroaction comprend : `conversation.feedback`.

Exemples :

* `feedback.raw[].text: "Great help"`
* feedback.rating.score : 1
* feedback.rating.classification : « Thumbs Up »
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

La plage de notes documentée va de `-1.0` à `1.0`.

Un événement de retour peut être représenté en tant qu’événement de retour uniquement à l’aide de : `eventType = "conversation.feedback"`.

Lorsque la rétroaction s&#39;applique à un virage particulier, conservez les `conversationID` et `turnID` appropriés afin que le mélangeur de conversation puisse associer la rétroaction à l&#39;interaction pertinente.


#### Signal

Un signal est une observation analytique structurée du contenu de la conversation. Le service d&#39;extraction de signaux extrait des signaux.

Un signal possède les champs suivants.

| Champ | Signification |
|---|----|
| `scope` | Plage d’entrée utilisée pour dériver le signal, telle que le virage ou la conversation en cours. |
| `name` | Identifiant du signal, tel que les sujets, les modes, les tonalités ou le sentiment. Les noms de signal définis par le producteur sont également pris en charge. |
| `type` | Type de valeur : chaîne, nombre ou valeur booléenne. |
| `values[]` | Une ou plusieurs valeurs associées au signal. |
| `stringValue` | Valeur de signal de chaîne, telle qu’une intention, une tonalité ou un objet. |
| `numberValue` | Valeur de signal numérique, telle qu’un score de sentiment. |
| `booleanValue` | Valeur de signal true/false. |
| `confidence` | Facultatif confiance du producteur dans la valeur du signal, normalement entre 0 et 1. |
| `qualifiers[]` | Descripteurs facultatifs qui ajoutent du contexte à une valeur de signal. |
| `metadata[]` | Métadonnées clé/valeur définies par le producteur facultatives. |


Le service d&#39;extraction de signaux renseigne l&#39;objet `signals` pour le jeu de données de signaux.

Le conteneur de `signals[].attributes.{subjects,intents,tones,sentiment}` précédent est obsolète.

#### Conversation

Consultez ci-dessous les détails complets d’un objet de conversation.

+++ Détails 

| Chemin Du Champ (Notation Par Points) | Type | Exemple de valeur | Notes |
|---|---|---|---|
| `conversationID` | string | `"conv-001"` | Regroupe plusieurs tours ensemble |
| `conversationName` | string | `"France Geography Q&A"` | **Nouveau.** Nom donné à une conversation représentant son contexte global |
| `turnID` | string | `"turn-001"` | ID unique pour ce tour |
| `prompt.source` | string | `"end-user"` | Source de l’invite, d’autres options peuvent inclure une valeur mise en cache, une valeur en conserve, etc. |
| `prompt.raw[]` | tableau | Voir objet brut ci-dessous | Données d&#39;invite brutes |
| `prompt.raw[].text` | string | `"What is the capital of France?"` | Contenu textuel réel |
| `prompt.raw[].purpose` | string | `"User Input"` | Objectif de ce segment de texte |
| `response.source` | string | `"bot"` | Source de la réponse |
| `response.raw[]` | tableau | Voir objet brut ci-dessous | Données brutes de réponse |
| `response.raw[].text` | string | `"The capital of France is Paris."` | Contenu du texte de réponse |
| `response.raw[].purpose` | string | `"main"` | Objectif du segment de réponse. Les autres options peuvent inclure des liens, des images, etc. |
| `feedback.source` | string | `"end-user"` | Source des retours |
| `feedback.raw[]` | tableau | Voir objet brut ci-dessous | Données brutes des commentaires |
| `feedback.raw[].text` | string | `"Great help"` | Texte du retour d’informations |
| `feedback.raw[].purpose` | string | `"free-form text"` | Objectif du segment de commentaires. Les autres options peuvent inclure des captures d’écran, des médias, etc. |
| `feedback.rating.score` | number | `1` | Score numérique de -1.0 à 1.0 |
| `feedback.rating.classification` | string | `"Thumbs Up"` | Classification de notation |
| `feedback.rating.reasons[]` | tableau | `["Accurate", "Quick response"]` | Tableau des raisons de l’évaluation |
| `signals[]` | tableau | Voir l’objet de signal ci-dessous | Signaux dérivés basés sur cet événement et la conversation à ce jour. Chaque entrée est un signal nommé unique avec sa propre portée |
| `signals[].scope` | string | `"turn"` | Portée des entrées à partir desquelles cet ensemble de signaux est dérivé (tour, conversation à ce jour, n derniers tours, retour) |
| `signals[].attributes` | objet | Voir les attributs ci-dessous | **Obsolète.** Conteneur pour les attributs de signal. Chaque attribut est un objet contenant une ou plusieurs valeurs. Cela permet de répondre au besoin anticipé de prendre en charge la population d’informations ML/agent utilisées pour générer le signal. |
| `signals[].attributes.subjects` | objet | Voir les sujets ci-dessous | **Obsolète.** Conteneur d&#39;objets |
| `signals[].attributes.subjects.values[]` | tableau | Voir les valeurs de l’objet ci-dessous | **Obsolète.** Tableau de valeurs d’objet |
| `signals[].attributes.subjects.values[].phrase` | string | `"product pricing"` | **Obsolète.** Expression ou mot clé extrait de l’entrée délimitée |
| `signals[].attributes.subjects.values[].qualifiers[]` | tableau | `["important", "urgent"]` | **Obsolète.** Liste des qualificateurs de l’expression |
| `signals[].attributes.intents` | objet | Voir les intentions ci-dessous | **Obsolète.** Conteneur d’intentions |
| `signals[].attributes.intents.values[]` | tableau | `["make a purchase", "learn more"]` | **Obsolète.** Intentions dérivées de l’entrée étendue |
| `signals[].attributes.tones` | objet | Voir les tons ci-dessous | **Obsolète.** Conteneur de tons |
| `signals[].attributes.tones.values[]` | tableau | `["thrilled", "contemplative"]` | **Obsolète.** Tones dérivées de l’entrée étendue |
| `signals[].attributes.sentiment` | objet | Voir le sentiment ci-dessous | **Obsolète.** conteneur de sentiment |
| `signals[].attributes.sentiment.value` | number | `0.71` | **Obsolète.** Score de -1 (négatif) à 1 (positif) indiquant un sentiment |
| `signals[].name` | string | `"sentiment"` | **Nouveau** (remplace le conteneur `attributes` obsolète). Identifiant de ce signal, par exemple « sujets », « intentions », « tonalités », « sentiment » ou tout nom défini par le producteur — les producteurs peuvent ajouter de nouveaux types de signaux sans modifier le schéma |
| `signals[].type` | string | `"number"` | **Nouveau.** Type de données des valeurs de ce signal (`string`, `number` ou `boolean`) — indique aux consommateurs quel champ de valeur saisi est renseigné à chaque entrée de `values[]` |
| `signals[].values[]` | tableau | Voir l’objet de valeurs ci-dessous | Une ou plusieurs valeurs pour ce signal |
| `signals[].values[].stringValue` | string | `"curious"` | Renseigné lorsque la `type` est « chaîne » — une valeur catégorielle telle qu’une intention, un ton ou une expression extraite |
| `signals[].values[].numberValue` | number | `0.71` | Renseigné lorsque `type` est « nombre » ; par exemple, un score de sentiment compris entre -1 et 1, ou une intensité |
| `signals[].values[].booleanValue` | booléen | `true` | Renseigné lorsque `type` est « booléen » — indicateur true/false |
| `signals[].values[].confidence` | number | `0.9` | **Nouveau.** Confiance que le producteur attribue à cette valeur, de 0 à 1 |
| `signals[].values[].qualifiers[]` | tableau | `["important", "urgent"]` | Descripteurs supplémentaires pour cette valeur, similaires aux mots-clés, mais plus significatifs |
| `signals[].values[].metadata[]` | tableau | Voir les paramètres ci-dessous | **Nouveau.** Métadonnées définies par le producteur pour cette valeur sous la forme de paires clé/valeur, par exemple le contexte à propos du ML/agent qui a généré le signal |

+++




### Groupes de champs supplémentaires

Vous pouvez ajouter des groupes de champs facultatifs au schéma que vous utilisez pour les jeux de données d’invite, de réponse et de commentaires. Par exemple :

* Groupe de champs **Détails web**. Pour capturer les détails de la page web dans laquelle la conversation a été incorporée.
* Groupe de champs Détails du Commerce **&#x200B;**. Pour capturer les détails du produit recommandé mentionné dans le cadre de la conversation.



Le client est chargé de produire les événements de conversation source. Adobe Platform effectue ensuite l’extraction du signal et le mélange des données. Le client n’a pas besoin de mettre en œuvre les services d’extraction ou de mélange de signaux.

Ce document couvre les exigences d’entrée du MVP Insights de conversation et la mise à jour actuelle du schéma agent. Il n’inclut pas les fonctionnalités Insights de conversation 1.0 ni les exigences de versions ultérieures.

### Type d’événement

Vous devez définir l’une des valeurs suivantes pour `eventType` (chaîne) pour chaque événement de conversation :

| Valeur | Explication |
|---|---|
| `conversation turn` | Tourner la conversation avec invite et réponse |
| `conversation recommendation` | Recommandation basée sur la conversation |
| `conversation feedback` | Événement de retour uniquement |


### Type de source

Vous devez définir l’une des valeurs suivantes pour `source` pour chaque objet `prompt`, `response` ou `feedback` d’un événement :

| Valeur | Description |
|---|---|
| `end-user` | Entrée utilisateur |
| `bot` | Réponse automatisée de l’agent |
| `canned` | Réponse prédéfinie/modélisée |
| `concierge` | Réponse de l&#39;agent humain |

### Type d’objectif (texte brut)

Vous devez définir l’une des valeurs suivantes pour l’attribut `purpose` sur tout élément de l’objet `raw` dans un objet `prompt`, `response` ou `feedback`.

| Valeur | Description |
|---|---|
| `User Input` | Principal des entrées utilisateur |
| `main` | Contenu de la réponse principale |
| `advertisement` | Contenu promotionnel |
| `citation` | Liens de référence/source |
| `link` | Liens externes |
| `image` | Références d’image |
| `enum picker` | Sélection structurée de commentaires |


### Exemple

Vous trouverez ci-dessous un exemple d’utilisation du groupe de champs Événement de conversation dans divers scénarios.

+++ Détails 

>[!BEGINTABS]

>[!TAB Exemple d’événement de transformation]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB Exemple d’événement de réponse]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB Exemple d’événement de retour]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB Exemple d’événement de recommandations de produits]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## Collecte de données

Utilisez la stratégie de collecte de données suivante pour Conversation Insights.


### Types d’événements

Votre application ou service d’agent envoie un événement dès que possible. Assurez-vous que l’application ou le service n’attend pas de réponse avant d’envoyer l’invite avec les informations disponibles au moment de l’événement.

Cette recommandation implique que :

* Les objets d’invite, de réponse et de commentaires sont renseignés indépendamment et ne doivent pas être forcés à faire partie d’un seul événement.
* Plusieurs événements avec les mêmes `conversationID` et `turnID` sont attendus dans les jeux de données.

### Corrélation des événements

L’application ou le service de l’agent doit conserver des identifiants stables pour tous les événements associés.

| Chemin du champ | Description |
|---|---|
| `conversation.conversationID` | Identifiant unique de la conversation globale. |
| `conversation.turnID` | Identifiant unique d’un tour individuel dans la conversation. |
| `_id` | Identifiant d’enregistrement de l’événement d’expérience. |
| `timestamp` | Heure à laquelle l’événement s’est produit. |
| `eventType` | Identifie le type d’événement de conversation. |

* Le même `conversationID` doit être utilisé pour tous les événements appartenant à la même conversation.

* Le même `turnID` doit être utilisé pour l&#39;invite, la réponse et tout retour associé au même tour. Plusieurs événements avec le même `turnID` peuvent exister dans les jeux de données d’invite, de réponse et de commentaires.

L’application ou le service de l’agent génère des identifiants qui restent stables lors des reprises ou de la rediffusion. Cela permet au traitement en aval d’associer correctement les événements et d’éviter les événements en double involontaires.

## Extraction de signal

L&#39;extraction du signal a lieu après la collecte des données. Votre application ou service d&#39;agent ne renseigne pas de signaux supplémentaires.

+++ Exemple d’événement de virage avec signaux

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## Fusion de données

Le service de mélangeur de conversation fusionne les événements des jeux de données d’événements d’invite, de réponse, de retour et de signal en un jeu de données d’événements de conversation mixte dédié. Ce jeu de données est utilisé dans Customer Journey Analytics dans le cadre d’une connexion. Les composants de ce jeu de données sont ajoutés aux vues de données que vous avez spécifiées pour une configuration Insights de conversation.
