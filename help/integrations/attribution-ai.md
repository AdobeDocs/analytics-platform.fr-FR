---
description: Découvrez comment AEP Attribution AI s’intègre à Workspace dans CJA.
title: Intégration d’Attribution AI à CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: c1e9fdb0e6d62da91b2b5c81eb21462890945b62
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 11%

---

# Intégration d’Attribution AI à CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), dans le cadre des services intelligents de Adobe Experience Platform, est un service d’attribution algorithmique à plusieurs canaux qui calcule l’influence et l’impact incrémentiel des interactions des clients par rapport à des résultats spécifiés. Grâce à Attribution AI, les marketeurs peuvent mesurer et optimiser les dépenses publicitaires et marketing en comprenant l’impact de chaque interaction client sur chaque phase des parcours clients.

Attribution AI s’intègre à Customer Journey Analytics (CJA) dans la mesure où Attribution AI exécute des modèles par rapport aux points de contact marketing et aux sources de données de conversion des clients. CJA importe ensuite la sortie de ces modèles en tant qu’ensemble de données ou peut être intégré au reste de vos jeux de données CJA. Les jeux de données activés pour Attribution AI peuvent ensuite être utilisés dans les vues de données et les rapports dans CJA.

Attribution AI prend en charge 3 schémas Experience Platform : Événement d’expérience, Adobe Analytics et Événement d’expérience client.

Attribution AI prend en charge deux catégories de scores : algorithmique et basé sur des règles.

## Scores algorithmiques

Les scores algorithmiques incluent les scores incrémentiels et influencés.

* **[!UICONTROL Influencé] scores** divise 100 % du crédit de conversion entre les canaux marketing.
* **[!UICONTROL Incrémentiel] scores** prenez tout d’abord en compte une ligne de base de conversion que vous auriez atteinte, même sans marketing. Cette référence dépend des observations de l’IA sur les motifs, le caractère saisonnier, etc., en raison de la reconnaissance de marque, de la fidélité et du bouche à oreille actuels. Le crédit restant est divisé entre les canaux marketing.

## Scores basés sur des règles

Les scores basés sur des règles incluent :

* **[!UICONTROL Première touche]** accorde un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont des attributions.
* **[!UICONTROL Dernière touche]** accorde un crédit de 100 % au point de contact le plus récent avant la conversion.
* **[!UICONTROL Linéaire]** accorde le même crédit à chaque point de contact affiché menant à une conversion.
* **[!UICONTROL En forme de U]** accorde un crédit de 40 % à la première interaction, de 40 % à la dernière interaction et divise les 20 % restants entre tous les points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est attribué aux deux.
* **[!UICONTROL Décroissance temporelle]** suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de 7 jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2^(-t/halflife)`, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont alors normalisés à 100 %.

## Processus

Certaines des étapes sont effectuées dans Adobe Experience Platform avant d’utiliser la sortie dans CJA. La sortie se compose d’un jeu de données avec un modèle Attribution AI appliqué.

### Étape 1 : Création d’une instance Attribution AI

Dans Experience Platform, créez une instance Attribution AI en sélectionnant et en associant les données, en définissant des événements et en formant vos données, comme décrit. [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Étape 2 : Configurer une connexion CJA à des jeux de données Attribution AI

Dans CJA, vous pouvez désormais [créer une ou plusieurs connexions](/help/connections/create-connection.md) aux jeux de données Experience Platform créés pour Attribution AI. Ces jeux de données s’affichent avec le préfixe &quot;Scores Attribution AI&quot;, comme illustré ici :

![Scores AAI](assets/aai-scores.png)

### Étape 3 : Créer des vues de données basées sur ces connexions

Dans CJA, [créer une ou plusieurs vues de données ;](/help/data-views/create-dataview.md) qui contiennent les champs XDM Attribution AI. (Ce serait génial d&#39;avoir une capture d&#39;écran ici.)

### Étape 4 : Rapport sur les données AAI dans CJA Workspace

Dans un projet Workspace CJA, vous pouvez extraire des mesures telles que &quot;Commandes AAI&quot; et des dimensions telles que &quot;Nom de campagne AAI&quot; ou &quot;Canal marketing AAI&quot;, par exemple.

![Dimensions AAI](assets/aai-dims.png)

>[!IMPORTANT]
>
>Ces dimensions et mesures ne sont pas nommées nativement de cette manière. Ce sont des &quot;noms conviviaux&quot;. Le [convention de dénomination dans Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/input-output.html?lang=en#attribution-ai-output-data) suit le chemin du schéma. Nous vous recommandons de renommer les longs noms de chemin de schéma dans AAI en noms courts et plus conviviaux (dimensions/mesures) dans CJA. Vous pouvez le faire dans **[!UICONTROL Vues des données]** > **[!UICONTROL Modifier la vue des données]** > **[!UICONTROL Composants]** onglet > **[!UICONTROL Champs de schéma]** -> Cliquez sur un champ de schéma -> **[!UICONTROL Nom du composant]**.


**Commandes avec scores influencés et incrémentiels**

Nous voyons ici un projet Workspace avec des données AAI qui affiche les commandes avec des scores influencés et incrémentiels. Explorez n’importe quelle dimension pour comprendre l’attribution en : campagne, groupe de produits, segment d’utilisateurs, zone géographique, etc.

![Projet AAI](assets/aai-project.png)

![Projet AAI](assets/aai-project2.png)

**Performances marketing**

Comparer et comparer l’attribution du point de contact entre différents modèles d’attribution :

![Comparer](assets/compare.png)

**Interaction des canaux**

Comprendre l’interaction des canaux pour savoir quel canal peut être le plus efficacement utilisé avec d’autres canaux à l’aide d’un diagramme de Venn :

![Chevauchement des canaux marketing](assets/mc-overlap.png)

**Chemins principaux vers la conversion**

Ce tableau présente les principaux chemins vers la conversion (dédupliqués) afin de vous aider à concevoir et optimiser des points de contact :

![Canaux principaux](assets/top-channels.png)

**Délai d’avance vers la conversion**

Nous voyons ici le délai d’avance vers la conversion lorsqu’un point de contact est présent dans le mélange. Cela permet d’optimiser le délai d’avance :

![Délai d’avance](assets/lead-time.png)

## Différences entre Attribution AI et Attribution IQ

Ainsi, quand utiliser les données Attribution AI au lieu de [Attribution IQ](/help/analysis-workspace/attribution/overview.md), une fonctionnalité native de CJA ? Ce tableau présente certaines des différences de fonctionnalités :

| Fonction | IA dédiée à l’attribution | Attribution IQ |
| --- | --- | --- |
| L’attribution incrémentielle | Oui | Non |
| Permet aux utilisateurs d’ajuster le modèle | Oui | Oui |
| L’attribution s’effectue-t-elle sur plusieurs canaux (Remarque : AAI n’utilise pas les mêmes données assemblées que CJA.) | Oui | Oui |
| Inclut des scores influencés | Oui | Oui |
| Création d’une modélisation ML | Oui | Oui |
| Modèles d’attribution basés sur une région | Oui | Oui |
| Peut configurer les points de contact marketing dans le modèle | Oui | Non |

{style=&quot;table-layout:auto&quot;}
