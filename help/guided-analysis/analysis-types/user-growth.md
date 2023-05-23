---
title: Croissance des utilisateurs et des utilisatrices
description: Suivre la croissance de la base d‘utilisateurs de votre produit.
source-git-commit: c47c4364cbf027c24a355bb306ee786c3e2446a9
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Croissance des utilisateurs et des utilisatrices

{{release-limited-testing}}

Le **Croissance des utilisateurs** [Type d’analyse](overview.md) fournit des informations sur la croissance et l’acquisition d’utilisateurs au cours d’une période spécifique. L’axe horizontal est toujours une granularité temporelle, tandis que l’axe vertical est toujours une mesure des utilisateurs. Les utilisateurs sont analysés depuis le début de la période, répartis en quatre catégories :

* **Nouveau**: Il s’agit de la première fois que l’utilisateur apparaît dans la période spécifiée. Le premier point de données d’un rapport comporte toujours 100 % de nouveaux utilisateurs, puisque le rapport ne tient pas compte des dates en dehors de la plage de rapports.
* **Répéter**: L’utilisateur apparaissait dans le point de données précédent immédiatement et dans le point de données actif.
* **Retour**: L’utilisateur n’apparaissait pas dans le point de données précédent immédiatement, mais n’est pas un nouvel utilisateur. Les utilisateurs réguliers ne peuvent pas apparaître dans le premier ou le second point de données, car ils doivent d’abord apparaître en tant que nouvel utilisateur, puis en tant qu’utilisateur inactif.
* **Dormant**: L’utilisateur n’apparaissait pas dans le point de données actif, mais dans le point de données précédent immédiatement. Les utilisateurs inactifs ne sont pas pris en compte dans le nombre total d’utilisateurs principaux.

Tous les utilisateurs principaux (nouveaux + répétition + retour) apparaissent sous la forme d’une nuance de teint au-dessus de l’axe horizontal, tandis que tous les utilisateurs inactifs apparaissent en orange sous l’axe horizontal.

Voici quelques cas pratiques de ce type d’analyse :

* **Évaluation des performances**: La croissance des utilisateurs vous permet d’évaluer les performances globales de votre produit en termes d’acquisition de nouveaux utilisateurs. En suivant les tendances de croissance, vous pouvez mieux comprendre si votre produit attire et conserve les utilisateurs à un rythme souhaité.
* **Rétention et perte de clientèle :** Ce rapport présente une visualisation claire des périodes de forte ou faible rétention des utilisateurs. La reconnaissance de ces périodes de rétention élevée ou faible peut vous aider à prendre des décisions sur les produits pour encourager la rétention élevée ou contribuer à réduire l’attrition.
* **Évaluation des campagnes**: L’affichage d’un rapport de croissance des utilisateurs spécifique à une campagne spécifique peut vous aider à comprendre non seulement le volume de trafic généré, mais également la manière dont la campagne a aidé les utilisateurs à rester engagés.

[Capture d’écran de la croissance des utilisateurs]

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **Événements**: Définit l’événement que vous souhaitez mesurer dans votre rapport. Ce rapport étant basé sur les utilisateurs, un utilisateur peut toucher l’événement une seule fois dans la granularité de date définie pour être compté en tant qu’utilisateur principal. Un seul événement est pris en charge.
* **Personnes**: Définit le segment que vous souhaitez mesurer dans votre rapport. Un seul segment est pris en charge.

## Types d’affichage

La croissance des utilisateurs offre les types de vue suivants. Vous pouvez modifier le type de vue à partir du menu déroulant situé en haut à gauche du graphique.

* **Principal :** Mesurez la croissance de votre base d’utilisateurs.

## Paramètres du graphique

La croissance des utilisateurs propose les paramètres de graphique suivants. Vous pouvez ajuster les paramètres du graphique à l’aide du menu entre le type d’affichage et le sélecteur de calendrier.

* **Mesure**: Définit la mesure que vous souhaitez mesurer. Les options disponibles sont Nombre d’utilisateurs et Pourcentage d’utilisateurs.
* **Type de graphique**: Définit le type de visualisation à utiliser. Les options disponibles sont Barre empilée et Zone empilée.

## Période

Définit la période souhaitée. Ce paramètre comporte deux composants importants :

* **Intervalle**: Granularité de la date dans laquelle vous souhaitez afficher les données. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Une même période peut comporter des intervalles différents qui affectent le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’un rapport couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’un rapport couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **Date**: Les dates de début et de fin du projet. Des paramètres prédéfinis de période sont disponibles à des fins pratiques ou vous pouvez utiliser le sélecteur de calendrier pour définir la date exacte de votre choix.
