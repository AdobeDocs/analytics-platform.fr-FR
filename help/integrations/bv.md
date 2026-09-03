---
title: Intégration de Brand Visibility
description: Intégration de Brand Visibility à Customer Journey Analytics
feature: Experience Platform Integration
role: User
source-git-commit: e90a8d978f8d910f426dcb0fbf28881724d0f5a7
workflow-type: tm+mt
source-wordcount: '2545'
ht-degree: 3%

---


# Intégration de Adobe Brand Visibility

[&#128279;](https://experienceleague.adobe.com/fr/docs/llm-optimizer/using/home){target="_blank"} est une application IA générative pour l&#39;optimisation du moteur de génération, conçue pour aider les marques à améliorer leur visibilité, leur précision et leur influence dans les environnements de recherche pilotés par l&#39;IA. Brand Visibility fournit des informations sur la présence des marques dans les réponses générées par l’IA, propose des recommandations de contenu prescriptives et automatise les correctifs d’optimisation.

L’IA est devenue un canal de découverte essentiel. Les agents de grands modèles linguistiques (LLM), tels que ChatGPT, Claude, Copilot et Perplexity, explorent le contenu de la marque.

>[!PREREQUISITES]
>
>Vous devez disposer d’une offre de paiement par Visibilité des marques configurée et connectée à votre configuration Experience Platform par le biais du connecteur géré.


>[!IMPORTANT]
>
>Dans le cadre de cette intégration, certains traitements temporaires des données de Brand Visibility sont effectués aux États-Unis. Les données sont finalement stockées dans la région désignée, telle que configurée dans votre contrat Customer Journey Analytics.


## Cas d’utilisation

L’intégration entre Customer Journey Analytics et Brand Visibility peut vous être bénéfique de deux manières :

* **Intégration entrante** : utilisez les données Brand Visibility dans Customer Journey Analytics pour mesurer le trafic piloté par LLM (robots d&#39;exploration de robots, requêtes RAG, activité d’agent) avec les données web, mobiles et autres types de données existantes. Par exemple, vous pouvez effectuer les opérations suivantes :

  * Mesurez le trafic piloté par LLM par la source de l’agent avec les canaux traditionnels.

  * Identifier le contenu fortement consommé par les LLM, mais dont les performances sont insuffisantes pour la conversion humaine.

  * Détecter où les requêtes LLM-agent échouent sur les chemins critiques.

  * Comparez la demande des robots LLM pour une page aux conversions et au chiffre d’affaires de cette page dans vos données web, mappées au niveau de l’URL et de l’hôte.

* **Intégration sortante** : envoyez les données de performances Customer Journey Analytics dans Brand Visibility afin d’optimiser la visibilité de l’IA pour les sources LLM qui vous envoient un trafic important, comme le ChatGPT ou la Perplexité. Par exemple, vous pouvez effectuer les opérations suivantes :

  * Découvrez les sources LLM qui envoient des visiteurs humains qui convertissent ou génèrent des recettes. Customer Journey Analytics le mesure à partir du trafic web référencé, et non du jeu de données de robots.
  * Classez les sources LLM par la valeur en aval des visiteurs humains qu’elles envoient, puis concentrez votre travail de visibilité de l’IA sur les sources qui présentent les meilleures performances.


## Intégration entrante

Le trafic LLM atteint votre site de deux façons. Customer Journey Analytics effectue des mesures dans chaque sens à partir d’une source de données différente.

La première méthode est celle d’une personne qui lit une réponse de l’IA, puis clique sur votre site. Cette visite exécute le même JavaScript qui collecte le reste de vos données web. Vos données web Customer Journey Analytics existantes incluent donc la visite et le domaine référent qui vous ont envoyé l’utilisateur, par exemple chatgpt.com. Customer Journey Analytics ne considère pas ces visites comme du trafic d’IA à part entière. Pour les identifier et les regrouper, vous créez un champ dérivé sur la connexion qui correspond aux domaines référents de l’IA, puis vous créez des segments et des rapports sur ce champ. Voir [Champs dérivés](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Vous n’avez pas besoin du jeu de données de Visibilité des marques pour ce trafic humain.

La seconde méthode consiste en un robot ou un agent qui demande directement vos pages. Cela inclut les robots d&#39;exploration qui créent un index IA et les récupérations dynamiques qui se produisent lorsqu’un utilisateur envoie une invite à un assistant IA. Ces requêtes n’exécutent aucun JavaScript. Par conséquent, vos données web existantes ne les enregistrent pas. Le jeu de données Visibilité des marques capture ce trafic à partir de la couche CDN. Le reste de cette section décrit ce jeu de données.

### Intégration du jeu de données dans Customer Journey Analytics

Le connecteur géré par la Visibilité des marques fournit les données à Experience Platform sous la forme d’un jeu de données de résumé. Pour le mesurer dans Customer Journey Analytics, vous effectuez vous-même deux étapes de configuration :

1. Créez une connexion qui inclut le jeu de données Brand Visibility. Voir [Créer ou modifier une connexion](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Créez une vue de données sur cette connexion. La vue de données rend les dimensions et mesures ci-dessous disponibles dans Analysis Workspace. Voir [Créer ou modifier une vue de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

Le jeu de données :

* Utilise des [jeux de données récapitulatifs](/help/data-views/summary-data.md) basés sur la classe Mesures récapitulatives XDM.
* Regroupe les données par URL et hôte, heure et caractéristiques de requête telles que le type de robot, le fournisseur de réseau CDN et le statut.

>[!NOTE]
>
>Le jeu de données Brand Visibility contient des données agrégées. Il ne contient aucune PII telle qu’un identifiant utilisateur, des invites ou des réponses.
>

Comme il s’agit d’un jeu de données de résumé, vous pouvez le traiter comme un jeu de données de recherche et le joindre à un jeu de données d’événement sur une clé URL complète.

Brand Visibility vous fournit cette clé dans la dimension **URL du réseau CDN**. Il combine l’hôte et le chemin d’accès demandé en une seule URL complète normalisée, comme le stocke Customer Journey Analytics pour les données web. Le succès de la jointure dépend de votre propre collecte de données. Votre jeu de données d’événement a besoin d’un champ d’URL complet équivalent, ou d’un champ que vous pouvez analyser et normaliser pour correspondre à l’URL fournie par Brand Visibility. Lorsque les deux côtés se résolvent sur la même URL complète, l’enregistrement de Visibilité des marques correspond à la page correspondante dans vos données web.

### À propos du jeu de données

Brand Visibility lit les journaux d’accès au réseau CDN côté serveur et extrait les enregistrements où la partie demandeuse est un robot ou un agent automatisé. Comme les données proviennent de la couche CDN, Brand Visibility capture les requêtes des robots qui ne déclenchent aucune balise JavaScript. Les outils d’analyse web standard manquent entièrement ce trafic.

Le jeu de données utilise le groupe de champs **Résumé des requêtes CDN**. Chaque champ se trouve sous un objet `cdn`. Par conséquent, les noms de champ dans les tableaux ci-dessous prennent la forme `cdn.<name>`, par exemple `cdn.url` et `cdn.botType`.

Chaque enregistrement décrit une combinaison d’hôte, de chemin d’URL, de type de robot, de fournisseur de réseau CDN, de code d’état, de référent, d’hôte transféré et de temps du premier octet pendant une heure. Lorsque la même combinaison apparaît plusieurs fois par heure, Customer Journey Analytics combine ces enregistrements en une seule ligne et augmente le nombre de requêtes. Utilisez la mesure **Nombre de requêtes CDN** pour mesurer le volume. N’utilisez pas le nombre de lignes.

### Dimensions

Les dimensions suivantes peuvent être utilisées comme composants dans une vue de données une fois que vous avez configuré une connexion qui inclut un jeu de données Brand Visibility. La colonne **Champ** affiche le champ source dans le groupe de champs Résumé des requêtes du réseau CDN.

| Dimension | Champ | Description |
|-----------|-------|-------------|
| URL DU RÉSEAU CDN | `cdn.url` | URL complète normalisée pour la requête, conçue comme clé de jointure. Brand Visibility combine l’hôte et le chemin d’accès demandé en une seule URL et la normalise pour qu’elle corresponde au formulaire URL complète que Customer Journey Analytics stocke pour les données web. Utilisez cette dimension pour joindre le jeu de données de recherche de Visibilité des marques à un jeu de données d’événement qui comporte un champ URL complète équivalent. Il inclut l’hôte et le chemin d’accès, mais pas le schéma. |
| Chemin d’accès à l’URL du réseau CDN | `cdn.path` | Le chemin d’URL brut et la chaîne de requête demandés par l’agent, tels qu’ils sont fournis par le réseau CDN. N’inclut pas le schéma ni l’hôte. Utilisez cette option lorsque vous avez besoin du chemin d’accès exact demandé plutôt que de la clé de jointure normalisée. |
| Hôte CDN | `cdn.host` | Le nom d’hôte qui a reçu la demande, par exemple www.example.com. Cet hôte fait également partie de la clé de jointure de l’URL du réseau CDN. Un jeu de données peut contenir plusieurs hôtes lorsqu’une organisation possède plusieurs sous-domaines sur le même compte CDN. |
| Type de robot CDN | `cdn.botType` | classification de l&#39;agent demandeur par la visibilité des marques. Les valeurs couvrent les robots d&#39;exploration de recherche classiques, les robots d&#39;exploration d’index d’IA et les agents d’extraction en direct d’IA. Consultez les [catégories d’agents robots](#bot-agent-categories) ci-dessous pour obtenir la taxonomie complète. |
| Agent utilisateur du réseau CDN | `cdn.userAgent` | Chaîne user-agent brute du journal CDN. Utile pour distinguer des sous-types au sein d’une classification de robots ou pour valider la classification attribuée par Brand Visibility. |
| Statut HTTP du réseau CDN | `cdn.status` | Code de statut de la réponse HTTP. Indique si le robot a reçu le contenu qu’il demandait. Consultez le [Codes d’état](#status-codes) ci-dessous pour obtenir des conseils d’interprétation spécifiques au trafic IA. |
| Fournisseur de réseau CDN | `cdn.cdnProvider` | Le réseau de diffusion de contenu qui a géré la requête. Les valeurs sont `akamai`, `byocdn-akamai`, `byocdn-fastly` et `byocdn-cloudfront`. Le préfixe `byocdn-` indique le chemin d’accès de la collecte de journaux, et non un fournisseur de réseau CDN différent. Un jeu de données peut contenir plusieurs valeurs lorsqu’une organisation dispose d’hôtes derrière différentes configurations de réseau CDN. |
| Référent CDN | `cdn.referer` | Valeur de l’en-tête du référent HTTP du journal du réseau CDN. Souvent vide pour le trafic de robots. Si présent, il peut indiquer quel produit ou domaine d’IA a déclenché la récupération. Par exemple, chat.openai.com. |
| Hôte transféré CDN | `cdn.xForwardedHost` | Valeur de l’en-tête X-Forwarded-Host, le cas échéant. Pertinent lorsque la requête a transité par une couche de proxy inverse ou de blindage de réseau CDN avant d’atteindre l’origine. |
| Date de l’événement CDN | Dérivé de la date et heure d’enregistrement | Partie de la date de l’horodatage par lots horaire pour cet enregistrement. |
| Heure de l’événement du réseau CDN | Dérivé de la date et heure d’enregistrement | Partie heure de l’horodatage par lots horaire pour cet enregistrement. |

### Catégories d’agents robots

La dimension **Type de robot CDN** organise les agents en trois catégories. Chaque catégorie répond à une question analytique différente.

robots d&#39;exploration de recherche classiques **indexez le contenu pour les moteurs de recherche traditionnels.** Utilisez cette catégorie pour mesurer la visibilité de votre contenu sur les moteurs de recherche traditionnels.

| Valeur du type de robot | Fournisseur | Description |
|---|---|---|
| `GoogleBot` | Google | robot d&#39;exploration d’index de recherche principal de Google. Elle diffuse également Google Discover et Google News. |
| `BingBot` | Microsoft | Robot d&#39;exploration d’index de recherche de Bing. Alimente également l&#39;index de mise à la terre Web de Microsoft Copilot. |

robots d&#39;exploration d’index AI **explorez au contenu pour créer ou mettre à jour le corpus de formation ou l’index de recherche d’un produit IA.** Ces robots d&#39;exploration préparent la base de connaissances d’un modèle et ne répondent pas à la demande d’un utilisateur en direct. Lorsqu’une URL présente un volume de robot d&#39;exploration élevé, les fournisseurs d’IA estiment que le contenu mérite d’être indexé. Lorsqu’une URL présente un faible volume de robot d&#39;exploration mais un volume de récupération en direct élevé, le modèle puise dans les connaissances mises en cache plutôt que de récupérer du contenu frais.

| Valeur du type de robot | Fournisseur | Description |
|---|---|---|
| `GPTBot` | OpenAI | Robot d&#39;exploration principal d’OpenAI pour les données d’entraînement de modèles et la création de bases de connaissances. |
| `OAI-SearchBot` | OpenAI | Robot d&#39;exploration d&#39;OpenAI pour le produit de recherche web de ChatGPT. Distinct de GPTBot. Cet agent crée l’index de recherche en temps réel, et non le corpus d’apprentissage. |
| `ClaudeBot` | Anthropique | Robot d&#39;exploration principal d’Anthropic pour les données d’entraînement de modèles. |
| `Claude-SearchBot` | Anthropique | Robot d&#39;exploration d&#39;Anthropic pour l&#39;index de recherche et de récupération de Claude. Distinct de ClaudeBot. |
| `PerplexityBot` | Perplexité | Le robot d&#39;exploration d&#39;index de la perplexité. La perplexité utilise cet agent pour construire le corpus pour sa génération de réponses. |

**Récupérations dynamiques de l’IA** se produisent lorsqu’un utilisateur réel envoie une invite à un assistant d’IA et que l’assistant récupère la page en direct avant de répondre. Utilisez cette catégorie pour mesurer la demande directe des utilisateurs et utilisatrices provenant des assistants d’IA.

| Valeur du type de robot | Fournisseur | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | Un utilisateur a posé une question à ChatGPT. ChatGPT a récupéré cette URL pour la lire et former sa réponse. |
| `ChatGPT Clients` | OpenAI | L’application mobile ChatGPT (iOS et Android) effectue une récupération en direct. La chaîne user-agent inclut la version de l’application et l’appareil. |
| `Claude-User` | Anthropique | Un utilisateur ou une application utilisant Claude a récupéré cette URL en direct. La chaîne user-agent peut identifier le produit Claude spécifique, par exemple, claude-code. |
| `Perplexity-User` | Perplexité | Un utilisateur a posé une question à Perplexity. Perplexity a récupéré cette URL pour fonder sa réponse. |
| `Google-NotebookLM` | Google | Un utilisateur a ouvert Google NotebookLM et a sourcé ce domaine. NotebookLM récupère chaque URL atteignable dans un domaine source. |
| `Google-ai-mode` | Google | La fonctionnalité Vues d’ensemble de l’IA de Google Search a récupéré cette URL pour l’inclure dans un panneau de réponses généré par l’IA dans les résultats de recherche. |
| `Gemini-Deep-Research` | Google | Un utilisateur a exécuté une session de recherche approfondie Gemini. Deep Research effectue de nombreuses récupérations séquentielles sur plusieurs sources pour compiler un rapport de recherche. |
| `GoogleAgent-URLContext` | Google | Un utilisateur a partagé une URL avec Gemini et a posé des questions sur cette page. Gemini a récupéré l’URL en direct pour répondre aux questions sur ce contenu spécifique. |
| `Amzn-User` | Amazon | Un agent Amazon Alexa ou Amazon AI a récupéré cette URL en direct. Apparaît généralement sur le contenu de référence et de documentation. |
| `MistralAI-User` | Mistral | Récupération en direct d’un produit ou d’un consommateur d’API optimisé par Mistral. |

Lorsque Brand Visibility ne peut pas faire correspondre un user-agent à un modèle reconnu, il affecte la valeur `Unknown`. Vous pouvez utiliser la dimension **Agent utilisateur du réseau CDN** pour identifier l’agent qui a effectué ces requêtes.

### Codes d’état

Les codes d’état HTTP de ce jeu de données indiquent si l’agent AI a reçu le contenu demandé.

| État | Nom | Interprétation |
|--------|------|----------------|
| 200 | OK | Le robot a reçu la réponse complète. Le contenu était disponible pour l’IA. |
| 304 | Non modifié | Le robot a confirmé que le contenu n’a pas été modifié et a utilisé sa version mise en cache. Le contenu était disponible. |
| 301 | Déplacé définitivement | Le robot a été redirigé vers une nouvelle URL. Chaque redirection ajoute un aller-retour supplémentaire. Un volume 301 élevé sur les URL fréquemment explorées signifie que la redirection doit être résolue au niveau du réseau CDN. |
| 302 | Trouvé (Redirection temporaire) | Même pénalité de latence que 301. Contrairement à 301, il n’indique pas de déplacement permanent, de sorte que les robots continuent à atteindre l’URL d’origine. |
| 403 | Interdit | Le réseau de diffusion de contenu ou l’origine a bloqué le robot. Cela peut être intentionnel, par exemple par le biais de règles robots.txt ou d’une politique WAF, ou non intentionnel, par exemple par le biais de limites de taux trop larges. Lorsque les récupérations d’IA sont bloquées, ce contenu ne peut pas apparaître dans les réponses d’IA. |
| 404 | Introuvable | L’URL n’existe pas. Un volume 404 élevé sur les types d’agents AI indique que l’index de l’IA contient des URL obsolètes. Utilisez le statut 410 pour indiquer aux robots d&#39;exploration de supprimer définitivement une URL de leur index. |
| 429 | Trop De Requêtes | Le réseau de diffusion de contenu a limité le robot. Des erreurs 429 persistantes sur les types d’agents de récupération en direct signifient que les utilisateurs qui posent des questions aux assistants d’IA sur votre contenu recevront des réponses incomplètes ou manquantes. |
| 504 | Délai d’expiration de la passerelle | Le réseau CDN a cessé d’attendre que l’origine réponde. Le contenu n’a pas atteint l’IA. Lorsqu’une page expire, l’IA ne peut pas accéder à son contenu et ne peut pas l’inclure dans une réponse. Un volume 504 élevé sur les types d’agents de récupération en direct est un risque de visibilité directe de l’IA. |

### Mesures

Les mesures suivantes peuvent être utilisées comme composants dans une vue de données une fois que vous avez configuré une connexion qui inclut un jeu de données Brand Visibility. La colonne **Champ** affiche le champ source dans le groupe de champs Résumé des requêtes du réseau CDN.

| Mesure | Champ | Description |
|--------|-------|-------------|
| Nombre de requêtes CDN | `cdn.requests` | Nombre total de requêtes de réseau CDN, additionné à partir du champ de requêtes sur toutes les lignes. Utilisez toujours cette mesure pour mesurer le volume. N’utilisez pas le nombre de lignes. |
| Nombre d’erreurs CDN | `cdn.status`, `cdn.requests` | Nombre de requêtes ayant renvoyé un code d’état HTTP 4xx ou 5xx. |
| Taux d’erreur du réseau CDN | Dérivé du nombre d’erreurs CDN | Le nombre d’erreurs est exprimé en pourcentage du nombre total de requêtes. |
| Temps moyen jusqu’au premier octet sur le réseau CDN | `cdn.timeToFirstByte` | Temps moyen en millisecondes entre le moment où le réseau CDN a reçu une requête et le premier octet de la réponse. Les réponses mises en cache par CDN sont généralement inférieures à 50 ms. Les réponses diffusées depuis l’origine sont généralement comprises entre 300 et 700 ms. Les agents d’extraction en direct de l’IA présentent souvent des valeurs beaucoup plus élevées, qui correspondent à des réponses d’origine expirées ou très lentes. Des valeurs moyennes élevées sur les types d’agents de récupération en direct méritent d’être étudiées en tant que risque de visibilité de l’IA. |

### Limites des jeux de données

Ce jeu de données capture uniquement le trafic des robots provenant des journaux d’accès CDN. Il ne contient pas les éléments suivants :

* **Sessions utilisateur, conversions ou données d’engagement.** Un utilisateur qui clique sur une réponse d’IA exécute le JavaScript sur votre page. Cette visite figure donc dans vos données web existantes, et non dans ce jeu de données. Vous pouvez importer les deux jeux de données dans Customer Journey Analytics et les comparer pour la même URL et le même hôte.
* **Identifiant de personne tel qu’ECID.** Vous ne pouvez pas effectuer de jointure au niveau de la personne à partir de ce jeu de données. La jointure fonctionne au niveau de l’URL et de l’hôte.
* **Granularité temporelle inférieure à la seconde.** La date et l’heure sont toutes les heures. Vous ne pouvez pas répartir le trafic au cours d’une heure en minutes ou secondes.
* **Contenu de la page ou rendu d’HTML.** Ce jeu de données enregistre le fait de la récupération et son résultat, et non pas ce que l’IA lit de la page.
* **Données de conversion.** Ce jeu de données ne vous indique pas si une réponse de l’IA a conduit une personne à visiter votre site ou à effectuer une conversion. Il contient des données de résumé CDN agrégées, et non des données d’événement basées sur une personne. Il ne lie donc aucune requête à une personne ou session individuelle.

## Intégration sortante

À déterminer.
