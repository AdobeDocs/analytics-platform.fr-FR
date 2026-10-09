---
title: Intégration de Brand Visibility
description: Intégration de Brand Visibility à Customer Journey Analytics
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Intégration de Adobe Brand Visibility

[&#128279;](https://experienceleague.adobe.com/fr/docs/brand-visibility/using/home){target="_blank"} est une application IA générative pour l&#39;optimisation du moteur de génération, conçue pour aider les marques à améliorer leur visibilité, leur précision et leur influence dans les environnements de recherche pilotés par l&#39;IA. Brand Visibility fournit des informations sur la présence des marques dans les réponses générées par l’IA, propose des recommandations de contenu prescriptives et automatise les correctifs d’optimisation.

L’IA est devenue un canal de découverte essentiel. Les agents de grands modèles linguistiques (LLM), tels que ChatGPT, Claude, Copilot et Perplexity, explorent le contenu de la marque.

>[!NOTE]
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


### Intégration du jeu de données

Le connecteur géré par la Visibilité des marques fournit les données à Experience Platform sous la forme d’un jeu de données de résumé. Pour le mesurer dans Customer Journey Analytics, vous effectuez vous-même deux étapes de configuration :

1. Créez une connexion qui inclut le jeu de données Brand Visibility.
2. Créez une vue de données sur cette connexion. La vue de données rend les dimensions et mesures ci-dessous disponibles dans Analysis Workspace.

Le jeu de données :

* Utilise des [jeux de données récapitulatifs](/help/data-views/summary-data.md) basés sur la classe Mesures récapitulatives XDM.
* Regroupe les données par URL et hôte, heure et caractéristiques de requête telles que le type de robot, le fournisseur de réseau CDN et le statut.

>[!NOTE]
>
>Le jeu de données Brand Visibility contient des données agrégées. Il ne contient aucune PII telle qu’un identifiant utilisateur, des invites ou des réponses.
>

Comme il s’agit d’un jeu de données de résumé, vous pouvez l’utiliser comme jeu de données de recherche et le joindre à un jeu de données d’événement sur une clé URL complète.

Brand Visibility vous fournit cette clé dans la dimension **URL du réseau CDN**. Il combine l’hôte et le chemin d’accès demandé en une seule URL complète normalisée, comme le stocke Customer Journey Analytics pour les données web. Le succès de la jointure dépend de votre propre collecte de données. Votre jeu de données d’événement a besoin d’un champ d’URL complet équivalent, ou d’un champ que vous pouvez analyser et normaliser pour correspondre à l’URL fournie par Brand Visibility. Lorsque les deux côtés se résolvent sur la même URL complète, l’enregistrement de Visibilité des marques correspond à la page correspondante dans vos données web.

Voir pour plus d’informations :

* [Installation et configuration de l’intégration entrante](/help/integrations/bv/configure.md)
* [Référence du jeu de données](/help/integrations/bv/reference.md)

## Intégration sortante

Pour plus d’informations sur l’intégration sortante, consultez la section [Intégration de &#x200B;](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"} dans la documentation de Adobe Brand Visibility.
