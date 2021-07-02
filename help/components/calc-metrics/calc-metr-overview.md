---
title: Présentation des mesures calculées
description: En savoir plus sur les
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 98%

---

# Présentation des mesures calculées

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=fr). [En savoir plus...](/help/getting-started/cja-aa.md)

Les mesures calculées ou calculées avancées (ou dérivées) sont des mesures personnalisées que vous pouvez créer à partir de mesures existantes. Nos outils de mesures calculées offrent un moyen bien plus souple pour créer, gérer et organiser les mesures. Ils vous permettent, en tant que responsables du marketing, chefs de produits et analystes, de poser des questions relatives aux données sans avoir à modifier votre implémentation. 

Vous pouvez

* Créer des mesures filtrées qui sont dérivées au moment de l’exécution du rapport, sans avoir à modifier l’implémentation. Elles peuvent être consultées de manière historique car elles sont basées sur des filtres.
* (Mesures calculées avancées uniquement) Filtre sur les mesures. Par exemple, vous pouvez créer une mesure « Nouveaux visiteurs », avec un décompte des personnes pour lesquelles il s’agit de la première session.
* (Mesures calculées avancées uniquement) Incorporer les fonctions statistiques afin de vous aider à mieux décrire les données. Par exemple, vous pouvez comptabiliser le nombre d’éléments d’un rapport ou ajouter le nombre d’écarts types pour chaque élément.

## Mesures calculées par rapport aux mesures calculées avancées

Dans le tableau ci-dessous, vous trouverez une comparaison des fonctionnalités des mesures calculées et des mesures calculées avancées :

| Options du créateur | Mesures calculées | Mesures calculées avancées (dérivées) |
|---|---|---|
| Types de format (décimal, heure, pourcentage, devise) | Oui | Oui |
| Modifications d’attribution (par défaut, linéaire, participation, etc.) | Oui | Oui |
| Types de mesure (standard, total) | Oui | Oui |
| Opérateurs de base (ajouter, soustraire, multiplier, diviser) | Oui | Oui |
| Filtres appliqués | Non | Oui |
| [Fonctions de base (décompte, valeur absolue, moyenne, etc.)](/help/components/calc-metrics/cm-functions.md) | Non | Oui |
| [Fonctions avancées (régression, si/alors, score normalisé, etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Non | Oui |

## Outils

| Outil | Fonctionnalités |
|--- |--- |
| Créateur de mesures calculées | <ul><li>Créer des mesures calculées et calculées avancées à l’aide des modèles d’affectation avancés.</li><li>Ajouter des filtres insérés aux formules de mesure.</li><li>Comparer des filtres dans le même rapport. Par exemple, comparer les visiteurs locaux et les visiteurs internationaux.</li><li>Utiliser les fonctions statistiques.</li><li> Fournir des descriptions de mesure détaillées (indiquer ce que la mesure fait, où l’utiliser, où NE PAS l’utiliser).</li><li>Copier des définitions dans les nouvelles mesures.</li><li>Fournir un aperçu des mesures insérées.</li><li>Définir la polarité de la mesure qui indique si, lorsqu’un événement personnalisé (mesure) donné s’accroît, il s’agit un événement positif ou négatif.</li><li>Baliser les mesures.</li></ul> |
| Gestionnaire de mesures calculées | <ul><li>Partager des mesures avec les autres.</li><li>Approuver et organiser les mesures.</li><li>Organiser (baliser) vos mesures afin que les personnes puissent les trouver.</li><li>Supprimer des mesures.</li><li>Renommer des mesures.</li></ul> |
| API pour les mesures calculées | Partie du jeu d’API CJA. |

## Modèles de mesures calculées dans CJA

| Nom de la mesure calculée | Description de la mesure calculée |
| --- | --- |
| Sessions par personne | Nombre moyen de sessions par personne |
| Taux de début de session | Pourcentage de fois où un élément de dimension sʼest produit lors du premier événement dʼune session. |
| Taux de fin de session | Pourcentage de fois où un élément de dimension sʼest produit lors du dernier événement dʼune session. |
| Durée par personne | Durée moyenne passée par une personne sur un élément de dimension donné. |
| Durée par session | Durée moyenne passée par personne et par session sur un élément de dimension donné. |
