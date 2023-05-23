---
title: Interface d’analyse guidée
description: Découvrez la structure globale de l’interface utilisateur du projet d’analyse guidée.
source-git-commit: d73dc0eb1740f28c0cd0b7b64fee86069c402b63
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Interface de l’analyse des guides

{{release-limited-testing}}

L’interface d’un projet d’analyse guidée, quel que soit le type d’analyse, comprend les éléments principaux suivants de l’interface utilisateur :

* **Rail de requêtes**: Utilisez ce rail à gauche de votre projet pour créer votre analyse.
* **Graphique**: Une fois que vous avez sélectionné les événements, personnes ou étapes, un graphique s’affiche à droite pour visualiser les données.
* **Tableau**: Tableau sous le graphique qui présente les nombres utilisés dans la visualisation.
* **Paramètres et insights**: Plusieurs éléments de l’interface utilisateur situés au-dessus du graphique vous permettent de personnaliser les données renvoyées.

[Capture d’écran de l’interface utilisateur]

## Rail de requêtes

[Capture d’écran du rail de requête]

Le rail de requête est l’emplacement dans lequel vous configurez les composants qui constituent un rapport. Les différents types d’analyse partagent plusieurs options de requête ; si deux types d’analyse partagent des options de requête, ils sont transférés lors du changement de type d’analyse. Voir [Types d’analyse](analysis-types/overview.md) pour plus d’informations sur les options de requête pour chaque type d’analyse respectif.

## Graphique

[Capture d&#39;écran du graphique]

Visualisation des données renvoyées en fonction de vos entrées depuis le rail de requête et les paramètres. La visualisation que vous voyez dépend du type de vue au-dessus du graphique. Les types d’affichage disponibles dépendent du [Type d’analyse](analysis-types/overview.md) au-dessus du rail de requête.

## Tableau

[Capture d&#39;écran du tableau]

Représentation sous forme de tableau des données renvoyées en fonction de l’entrée que vous avez reçue du rail de requête et des paramètres. Les colonnes du tableau dépendent du type d’affichage situé au-dessus du graphique. Les types d’affichage disponibles dépendent du [Type d’analyse](analysis-types/overview.md) au-dessus du rail de requête.

## Paramètres

[Capture d’écran des paramètres]

Plusieurs options au-dessus du graphique qui vous permettent de personnaliser la manière dont le graphique et le tableau renvoient des données.

* **Type d’affichage**: Sélecteur déroulant qui permet de présenter des données pour un [Type d’analyse](analysis-types/overview.md) d&#39;une manière différente. Chaque type d’analyse possède au moins deux types de vues.
* **Paramètres du graphique**: Ajustez à quoi ressemble votre graphique et quels événements vous souhaitez qu’il utilise. Les options disponibles dépendent du type de vue sélectionné.
* **Période**: Sélecteur de calendrier qui vous permet de déterminer la période du rapport. Certains types d’analyse autorisent également des intervalles, par exemple, quotidiens, hebdomadaires ou mensuels.
* **Insights**: Fournit des informations contextuelles en fonction du rapport que vous affichez. Vous pouvez afficher ou masquer ces informations à l’aide de l’icône d’ampoule située en haut à droite.

## Menu Projet

[Capture d’écran du menu du projet]

Commandes en haut à droite du projet qui fournissent des actions globales.

* **Sélecteur de vue de données**: Modifiez la vue de données utilisée par ce projet. Lorsque vous modifiez la vue de données, les composants disponibles dans le rail de requête changent également.
* **Enregistrer**: Enregistre le projet. Si vous enregistrez un nouveau projet, une fenêtre modale s’affiche et vous demande un nom et une description.
* **Enregistrer sous**: Enregistre le projet séparément du projet en cours, en créant une copie. Une fenêtre modale s’affiche, qui demande un nouveau nom et une nouvelle description.
* **Ouvrir dans Workspace**: Recrée le projet d’analyse guidée actuel dans Analysis Workspace. Le projet Workspace est créé dans un nouvel onglet afin d’éviter toute interruption lors de l’utilisation de votre projet d’analyse guidée. Utilisez cette commande lorsque l’analyse guidée ne vous donne pas tout à fait la flexibilité ou les informations spécifiques que vous recherchez. Par exemple, vous souhaitez qu’une [Tendances](analysis-types/trends.md) rapport qui utilise les sessions pour un segment et les personnes pour un autre segment.
* **Télécharger PNG**: Télécharge le graphique sous la forme d’un graphique `.png`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.
* **SVG de téléchargement**: Télécharge le graphique sous la forme d’un graphique `.svg`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.
