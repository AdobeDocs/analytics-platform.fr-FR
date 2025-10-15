---
title: Utilisez des champs dérivés pour créer des rapports sur le trafic généré par LLM et IA.
description: Découvrez comment utiliser les champs dérivés comme base pour créer des rapports sur le trafic généré par LLM et l’IA dans Workspace.
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 39b3e0eb43e69c81c12e56fc7605e5746c2d650c
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 1%

---


# Créer un rapport sur le trafic généré par LLM et IA

Cet article de cas d’utilisation explique comment utiliser la fonctionnalité de champs dérivés de Customer Journey Analytics comme base pour créer des rapports sur le trafic LLM (Large Language Model) et généré par l’IA.

>[!NOTE]
>
>L’efficacité des [méthodes de détection](#detection-methods), [signatures de détection](#detection-signatures) et [stratégies d’implémentation](#implementation) dépend de votre méthode de collecte de données spécifique, de la couverture du jeu de données Experience Platform et de l’implémentation de Customer Journey Analytics. Les résultats peuvent varier en fonction de votre environnement technique, des politiques de gouvernance des données et de votre approche de mise en œuvre. Lors de l’utilisation d’Experience Edge, vous devez choisir entre enregistrer la chaîne brute de l’agent utilisateur ou collecter des informations sur l’appareil.
>

## Méthodes de détection

Pour détecter le trafic généré par LLM et par l’IA, faites la distinction entre :

* **robots LLM** : collectez des données pour l’entraînement et la récupération de la génération augmentée (RAG).
* **Agents AI** : fonctionnent comme des interfaces qui exécutent des tâches au nom de l’homme. Les agents d’IA préfèrent interagir par le biais d’API, qui contournent les méthodes de suivi Web Analytics. Néanmoins, vous pouvez toujours analyser une partie significative du trafic généré par l’IA via les sites web.

Trois méthodes de détection principales courantes pour identifier et surveiller le trafic généré par LLM et par l’IA sont les suivantes :

* **Identification de l’agent utilisateur** : lorsqu’une requête est envoyée à votre serveur, l’en-tête User-Agent HTTP est extrait et analysé par rapport aux modèles d’agent et de robot d’exploration AI connus. Cette méthode côté serveur nécessite l’accès aux en-têtes HTTP et est plus efficace lorsqu’elle est implémentée au niveau de la couche de collecte de données.
* **Classification de référent** : l’en-tête référent HTTP contient l’URL de la page web précédente qui pointait vers la requête en cours. Cet en-tête s’affiche lorsque les utilisateurs cliquent sur votre site à partir d’interfaces web telles que ChatGPT ou Perplexity.
* **Détection des paramètres de requête** : les services d’IA peuvent ajouter des paramètres d’URL (en particulier des paramètres UTM) aux liens. Ces paramètres persistent dans l’URL et peuvent être détectés par le biais d’implémentations d’analyse standard, ce qui rend ces paramètres d’URL des indicateurs précieux même dans les scénarios de suivi côté client.


Le tableau suivant illustre la manière dont les méthodes de détection peuvent être utilisées dans différents scénarios d’interaction LLM et AI.

| Scénario | Identification de l&#39;agent utilisateur | Classification de référent | Détection des paramètres de requête |
|---|---|---|---|
| **Formation d&#39;un modèle** | L’agent (`GPTBot`, `ClaudeBot`, etc.) peut être identifié lors de l’implémentation de la journalisation côté serveur. | Aucune classification n’est possible. Les robots d’exploration AI ne génèrent pas de référents pendant la formation. | La détection est impossible. Les robots d’exploration AI n’ajoutent pas de paramètres pendant l’entraînement. |
| **Navigation de l’agent** | L’agent (`ChatGPT-User`, `claude-web`) peut être identifié lorsque la journalisation côté serveur capture les en-têtes. | La classification est possible si l’agent navigue depuis une interface d’IA avec la conservation des référents. | La détection est parfois possible si le service d’IA ajoute des paramètres de tracking. |
| **Récupération de la génération augmentée (RAG) pour répondre à la requête** | L’agent (`OAI-SearchBot`, `PerplexityBot`) peut être identifié à l’aide de la journalisation côté serveur. | Aucune classification n’est généralement possible, car les opérations RAG contournent souvent les mécanismes référents. | La détection est rarement possible, sauf si elle est spécifiquement mise en œuvre par le fournisseur d’IA. |
| **L’utilisateur clique jusqu’au** | L’agent ne peut pas être identifié. L’agent AI apparaît comme un agent utilisateur normal. | La classification est possible lorsque les utilisateurs cliquent sur des liens à partir des interfaces d’IA ([chatgpt.com](https://chatgpt.com), [claude.ai](https://claude.ai), etc.). | La détection est possible lorsque les services d’IA ajoutent des paramètres UTM aux liens sortants. |
| **Conditions de visibilité du trafic** | Nécessite une intégration de journalisation côté serveur avec Customer Journey Analytics ou le balisage côté serveur pour l’identification de l’agent. | La classification dépend des politiques de référent de la plateforme AI et de la transmission correcte des en-têtes HTTP. | La détection nécessite la conservation des paramètres par le biais de redirections et la collecte appropriée des paramètres d’URL. |

### Les défis

Les agents LLM et AI démontrent des comportements complexes et en évolution lors de l’interaction avec des propriétés numériques. Ces technologies fonctionnent de manière incohérente sur les différentes plateformes et versions. Cette incohérence crée des défis uniques pour les professionnels des données. Les modèles de comportement varient considérablement et dépendent de la plateforme d’IA, de la version et du mode d’interaction spécifiques utilisés. Cette diversité opérationnelle complique les efforts de suivi et de catégorisation du trafic généré par LLM et par l’IA dans les cadres d’analyse standard. La nature complexe de ces interactions, combinée à leur évolution rapide, nécessite des méthodes de détection et de classification nuancées pour maintenir l’intégrité des données :

* **Collecte de données partielle** : certains agents d’IA plus récents exécutent des JavaScript limitées, ce qui entraîne des données d’analyse incomplètes pour les implémentations côté client. Par conséquent, certaines interactions sont suivies tandis que d’autres sont manquantes.
* **Données de session incohérentes** : les agents AI peuvent exécuter JavaScript différemment selon les sessions ou les types de page. Cette différence d’exécution crée des parcours utilisateur fragmentés dans Customer Journey Analytics pour les implémentations côté client.
* **Défis liés à la détection** : avec un suivi partiel, la détection devient non fiable, car certains points de contact peuvent être invisibles pour les analyses.


## Signatures de détection

Depuis août 2025, les signaux spécifiques suivants peuvent être identifiés pour chacune des méthodes de détection.

### Identification de l&#39;agent utilisateur

<table>
<thead>
<tr>
<th>Crawler</th>
<th>Chaîne de l’agent utilisateur</th>
<th>Objectif/Comportement</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>GPTBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.1; +<a href="https://openai.com/gptbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/gptbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Robot d’exploration web principal d’OpenAI pour la formation au ChatGPT et aux modèles de langue</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Utilisé lorsque ChatGPT navigue sur des sites Web pour le compte d'utilisateurs (hérité)</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User v2</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/2.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Version mise à jour de ChatGPT pour la récupération à la demande et les recherches en réponse</a></td>
</tr>
<tr>
<td><strong>OAI-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; OAI-SearchBot/1.0; +<a href="https://openai.com/searchbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/searchbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">L'explorateur de recherche de ChatGPT pour découvrir du contenu</a></td>
</tr>
<tr>
<td><strong>ClaudeBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ClaudeBot/1.0; +claudebot@anthropic.com</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Robot d'Anthropic pour la formation et la mise à jour de l'assistant Claude AI</a></td>
</tr>
<tr>
<td><strong>Claude-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-User/1.0; +Claude-User@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Prend en charge les utilisateurs de Claude AI lorsque des individus posent des questions à Claude, il peut accéder aux sites web en utilisant un...</a></td>
</tr>
<tr>
<td><strong>Claude-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-SearchBot/1.0; +Claude-SearchBot@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Naviguer sur le web pour améliorer la qualité des résultats de recherche pour les utilisateurs de Claude AI en analysant le contenu en ligne...</a></td>
</tr>
<tr>
<td><strong>PerplexityBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; PerplexityBot/1.0; +<a href="https://www.perplexity.ai/perplexitybot" target="_blank" rel="noopener nofollow noreferrer">https://perplexity.ai/perplexitybot</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Explorateur Perplexity.ai pour l’indexation des données web en temps réel</a></td>
</tr>
<tr>
<td><strong>Perplexity-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Perplexity-User/1.0; +<a href="https://www.perplexity.ai/useragent" target="_blank" rel="noopener nofollow noreferrer">https://www.perplexity.ai/useragent</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Charge les pages quand les utilisateurs cliquent sur Citations de complexité (contourne robots.txt)</a></td>
</tr>
<tr>
<td><strong>Google-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Google-Extended/1.0; +<a href="https://support.google.com/webmasters/answer/182072" target="_blank" rel="noopener nofollow noreferrer">http://www.google.com/bot.html</a>)</code></td>
<td><a href="https://blog.google/technology/ai/an-update-on-web-publisher-controls/" target="_blank" rel="noopener nofollow noreferrer">Robot de recherche centré sur l’IA pour Google pour Gemini distinct de Google standard</a></td>
</tr>
<tr>
<td><strong>BingBot</strong></td>
<td><code>Mozilla/5.0 (compatible; BingBot/1.0; +<a href="http://www.bing.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bing.com/bot.html</a>)</code></td>
<td>Robot de recherche Microsoft alimentant la recherche Bing et le chat Bing (copilote)</td>
</tr>
<tr>
<td><strong>DuckAssistBot</strong></td>
<td><code>Mozilla/5.0 (compatible; DuckAssistBot/1.0; +<a href="https://duckduckgo.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.duckduckgo.com/bot.html</a>)</code></td>
<td><a href="https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot" target="_blank" rel="noopener nofollow noreferrer">Récupère le contenu pour DuckAssist, la fonctionnalité de réponse d'IA privée de DuckDuckGo</a></td>
</tr>
<tr>
<td><strong>YouBot</strong></td>
<td><code>Mozilla/5.0 (compatible; YouBot (+<a href="http://www.you.com" target="_blank" rel="noopener nofollow noreferrer">http://www.you.com</a>))</code></td>
<td>Explorateur derrière l’assistant de recherche et de navigateur d’IA de You.com</td>
</tr>
<tr>
<td><strong>meta-externalagent</strong></td>
<td><code>Mozilla/5.0 (compatible; meta-externalagent/1.1 (+<a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers" target="_blank" rel="noopener nofollow noreferrer">https://developers.facebook.com/docs/sharing/webmasters/crawler</a>))</code></td>
<td><a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers#identify-2" target="_blank" rel="noopener nofollow noreferrer">Robot de Meta pour la collecte de données pour entraîner ou affiner les LLM</a></td>
</tr>
<tr>
<td><strong>Amazonbot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/600.2.5 (KHTML, like Gecko) Version/8.0.2 Safari/600.2.5 (Amazonbot/0.1; +<a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">https://developer.amazon.com/support/amazonbot</a>)</code></td>
<td><a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">Explorateur Amazon pour les applications de recherche et d’IA</a></td>
</tr>
<tr>
<td><strong>Applebot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Safari/605.1.15 (Applebot/0.1; +<a href="https://support.apple.com/kb/HT6619" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/go/applebot</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Robot d’exploration Apple pour Spotlight, Siri et Safari</a></td>
</tr>
<tr>
<td><strong>Applebot-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Applebot-Extended/1.0; +<a href="https://www.apple.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/bot.html</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Robot d’exploration axé sur l’IA d’Apple pour les futurs modèles d’IA (opt-in)</a></td>
</tr>
<tr>
<td><strong>Bytespider</strong></td>
<td><code>Mozilla/5.0 (compatible; Bytespider/1.0; +<a href="https://www.bytedance.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bytedance.com/bot.html</a>)</code></td>
<td>Le collecteur de données IA de ByteDance pour TikTok et d’autres services</td>
</tr>
<tr>
<td><strong>MistralAI-User</strong></td>
<td><code>Mozilla/5.0 (compatible; MistralAI-User/1.0; +<a href="https://mistral.ai/bot" target="_blank" rel="noopener nofollow noreferrer">https://mistral.ai/bot</a>)</code></td>
<td><a href="https://docs.mistral.ai/robots/" target="_blank" rel="noopener nofollow noreferrer">Récupérateur de citations en temps réel de Mistral pour l'assistant « Le Chat »</a></td>
</tr>
<tr>
<td><strong>cohere-ai</strong></td>
<td><code>Mozilla/5.0 (compatible; cohere-ai/1.0; +<a href="http://www.cohere.ai/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.cohere.ai/bot.html</a>)</code></td>
<td>Collecte des données textuelles pour les modèles de langue de Cohere</td>
</tr>
</tbody>
</table>


### Classification de référent

<table>
<thead>
<tr>
<th><strong>Source</strong></th>
<th><strong>Référent</strong></th>
<th><strong>Type de trafic</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td>chatgpt.com</td>
<td>Trafic direct depuis l’interface ChatGPT</td>
</tr>
<tr>
<td>Claude</td>
<td>claude.ai</td>
<td>Trafic provenant de l'interface Claude d'Anthropic</td>
</tr>
<tr>
<td>Google Gemini</td>
<td>gemini.google.com</td>
<td>Trafic provenant de l’assistant d’IA Google</td>
</tr>
<tr>
<td>Copilote Microsoft</td>
<td>copilot.microsoft.com</td>
<td>Trafic provenant de l’assistant d’IA Microsoft</td>
</tr>
<tr>
<td>Copilote Microsoft</td>
<td>m365.cloud.microsoft</td>
<td>Trafic provenant de l’assistant d’IA Microsoft (services cloud Microsoft 365)</td>
</tr>
<tr >
<td>Perplexity AI</td>
<td>perplexity.ai</td>
<td>Trafic provenant de la recherche par l’IA avec des citations</td>
</tr>
<tr>
<td>META AI</td>
<td>meta.ai</td>
<td>Trafic provenant de l’assistant d’IA Meta</td>
</tr>
</tbody>
</table>

### Détection des paramètres de requête

<table>
<thead>
<tr>
<th><strong>Service LLM</strong></th>
<th>Exemple d’URL</th>
<th><strong>Paramètre de requête</strong></th>
<th><strong>Exemple de valeur</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td ><a href="https://www.yoursite.com/product?utm_source=chatgpt.com" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/product?utm_source=chatgpt.com</a></td>
<td>utm_source</td>
<td>chatgpt.com</td>
</tr>
<tr>
<td>Perplexité</td>
<td><a href="https://www.yoursite.com/article?utm_source=perplexity" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/article?utm_source=perplexity</a></td>
<td>utm_source</td>
<td>perplexité</td>
</tr>
</tbody>
</table>


## Implémentation

Vous pouvez créer des rapports sur le trafic généré par LLM et par l’IA dans une configuration Customer Journey Analytics standard ([connexion](/help/connections/overview.md), [vues de données](/help/data-views/data-views.md) et [projets d’espace de travail](/help/analysis-workspace/home.md)) par le biais de la configuration spécifique des [champs dérivés](#derived-fields), [segments](#segments) et [projets d’espace de travail](#workspace-project).


### Champs dérivés

Pour configurer les méthodes de détection et les signaux de détection, utilisez les champs dérivés comme base. Par exemple, définissez les champs dérivés pour [identification de l’agent utilisateur](#user-agent-identification), [détection des paramètres de requête](#query-parameter-detection) et [classification du référent](#referrer-classification).

#### Identification de l’agent utilisateur LLM/AI

Utilisez les fonctions de champ dérivé [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) pour définir un champ dérivé qui identifie les agents utilisateur LLM/AI.

![&#x200B; Identification de l’agent utilisateur LLM/AI &#x200B;](assets/aitraffic-useragents.png){zoomable="yes"}


#### Détection des paramètres de requête LLM/AI

Utilisez les fonctions de champ dérivé [Analyse d’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) et [Classifier](/help/data-views/derived-fields/derived-fields.md#classify) pour définir un champ dérivé qui détecte les paramètres de requête.

![Détection des paramètres UTM LLM/AI](assets/aitraffic-utmparams.png){zoomable="yes"}


#### Classification de référent LLM/AI

Utilisez les fonctions de champ dérivé [Analyse d’URL](/help/data-views/derived-fields/derived-fields.md#url-parse) et [Classifier](/help/data-views/derived-fields/derived-fields.md#classify) pour définir un champ dérivé qui classe les référents.

![Classification de référent LLM/AI](assets/aitraffic-referrers.png){zoomable="yes"}


### Segments

Configurez des segments dédiés qui vous aident à identifier les événements, sessions ou personnes liés au trafic généré par LLM et IA. Par exemple, utilisez les champs dérivés que vous avez créés précédemment pour définir un segment qui identifie le trafic généré par LLM et par l’IA.

![Segment de trafic généré par LLM et AI](assets/aitraffic-segment.png){zoomable="yes"}


### projet Workspace

Utilisez les champs dérivés et les segments pour générer des rapports et des analyses sur le trafic généré par LLM et par l’IA. Par exemple, consultez le projet annoté ci-dessous.

![&#x200B; Projet de Workspace du trafic généré par LLM et l’IA &#x200B;](assets/aitraffic-workspace.png){zoomable="yes"}



>[!MORELIKETHIS]
>
>Cet article de cas d’utilisation est basé sur l’article de blog [Tracking et analyse du trafic généré par LLM et par l’IA dans Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/tracking-and-analyzing-llm-and-ai-generated-traffic-in-adobe/ba-p/771967).
>
>
