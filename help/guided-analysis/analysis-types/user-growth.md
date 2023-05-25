---
title: Croissance des utilisateurs et des utilisatrices
description: Suivre la croissance de la base d‘utilisateurs de votre produit.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 2%

---

# Croissance des utilisateurs et des utilisatrices

{{release-limited-testing}}

Le **Croissance des utilisateurs** [Type d’analyse](overview.md) fournit des informations sur la croissance et l’acquisition d’utilisateurs au cours d’une période spécifique. L’axe horizontal est toujours une granularité temporelle, tandis que l’axe vertical est toujours une mesure des utilisateurs. Les utilisateurs sont analysés depuis le début de la période, répartis en quatre catégories :

* **Nouveau**: Il s’agit de la première fois que l’utilisateur apparaît dans la période spécifiée. Le premier point de données correspond toujours à 100 % des nouveaux utilisateurs, car l’analyse ne s’effectue pas en dehors de la période.
* **Répéter**: L’utilisateur apparaissait dans le point de données précédent immédiatement et dans le point de données actif.
* **Retour**: L’utilisateur n’apparaissait pas dans le point de données précédent immédiatement, mais n’est pas un nouvel utilisateur. Les utilisateurs réguliers ne peuvent pas apparaître dans le premier ou le second point de données, car ils doivent d’abord apparaître en tant que nouvel utilisateur, puis en tant qu’utilisateur inactif.
* **Dormant**: L’utilisateur n’apparaissait pas dans le point de données actif, mais dans le point de données précédent immédiatement. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs principaux.

Tous les utilisateurs principaux (nouveaux + répétition + retour) apparaissent sous la forme d’une nuance de teint au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange sous l’axe horizontal.

Voici quelques cas pratiques de ce type d’analyse :

* **Évaluation des performances**: La croissance des utilisateurs vous permet d’évaluer les performances globales de votre produit en termes d’acquisition de nouveaux utilisateurs. En suivant les tendances de croissance, vous pouvez mieux comprendre si votre produit attire et conserve les utilisateurs à un rythme souhaité.
* **Rétention et perte de clientèle :** La croissance des utilisateurs offre une visualisation claire des périodes de forte ou faible rétention des utilisateurs. La reconnaissance de ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions sur les produits pour encourager la rétention élevée ou contribuer à réduire l’attrition.
* **Évaluation des campagnes**: L’affichage de la croissance des utilisateurs spécifique à une campagne spécifique peut vous aider à comprendre non seulement le volume de trafic généré, mais également la manière dont la campagne a aidé les utilisateurs à rester engagés.

[Capture d’écran de la croissance des utilisateurs]

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: L’événement que vous souhaitez mesurer. Ce type d’analyse étant basé sur l’utilisateur, l’utilisateur peut toucher l’événement une seule fois dans la granularité de date définie pour être compté en tant qu’utilisateur principal. Vous ne pouvez inclure qu’un seul événement.
* **Personnes**: Le segment que vous souhaitez mesurer. Vous ne pouvez inclure qu’un seul segment.

## Types d’affichage

La croissance des utilisateurs offre les types de vue suivants. Vous pouvez modifier le type de vue à partir du menu déroulant situé en haut à gauche du graphique.

* **Principal :** Mesurez la croissance de votre base d’utilisateurs.

## Paramètres du graphique

La croissance des utilisateurs propose les paramètres de graphique suivants. Vous pouvez ajuster les paramètres du graphique à l’aide du menu entre le type d’affichage et le sélecteur de calendrier.

* **Mesure**: Mesure que vous souhaitez mesurer. Les options disponibles sont Nombre d’utilisateurs et Pourcentage d’utilisateurs.
* **Type de graphique**: Type de visualisation que vous souhaitez utiliser. Les options disponibles sont Barre empilée et Zone empilée.

## Période

Période souhaitée. Ce paramètre comporte deux composants importants :

* **Intervalle**: Granularité de la date dans laquelle vous souhaitez afficher les données. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
