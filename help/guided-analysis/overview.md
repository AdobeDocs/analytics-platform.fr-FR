---
title: Aperçu des analyses guidées
description: Méthode d’analyse des données dans Customer Journey Analytics qui permet aux équipes produit de générer facilement des rapports et des informations.
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# Aperçu des analyses guidées

{{release-limited-testing}}

L’analyse guidée est un format de création de rapports qui permet aux équipes produit de répondre rapidement à leurs besoins de données de manière à ce qu’elles puissent prendre davantage de décisions liées aux données. Les équipes interfonctionnelles peuvent se connecter en temps réel pour utiliser et comprendre ces rapports.

Tout comme pour les Fiches d’évaluation Analysis Workspace et Mobile, un rapport d’analyse guidée utilise les données d’une [Vue des données](../data-views/data-views.md), qui référence les données dans Adobe Experience Platform au moyen d’une [Connexion](../connections/overview.md). Tous les rapports créés dans les analyses guidées peuvent facilement être transférés vers Analysis Workspace pour effectuer des recherches supplémentaires.

Les rapports d’analyse guidée présentent actuellement trois types d’analyse : [Entonnoir](analysis-types/funnel.md), [Tendances](analysis-types/trends.md), et [Croissance des utilisateurs](analysis-types/user-growth.md). Chacun de ces types d’analyse comporte plusieurs types de vues, qui fournissent des informations supplémentaires sur chacun de ces rapports.

## Attribution des privilèges d’accès

L’analyse guidée est un module complémentaire payant pour Customer Journey Analytics. Si votre entreprise souhaite commencer à utiliser cette fonctionnalité, contactez votre équipe de compte d’Adobe.

## Interface

L’interface d’analyse guidée, quel que soit le type d’analyse, comprend les éléments principaux suivants de l’interface utilisateur :

1. **Rail de requêtes**: Utilisez ce rail sur la gauche pour créer votre analyse.
1. **Graphique**: Une fois que vous avez sélectionné les événements, personnes ou étapes, un graphique s’affiche à droite pour visualiser les données.
1. **Tableau**: Tableau sous le graphique qui présente les nombres utilisés dans la visualisation.
1. **Paramètres et insights**: Plusieurs éléments de l’interface utilisateur situés au-dessus du graphique vous permettent de personnaliser les données renvoyées.

[Capture d’écran de l’interface utilisateur]

L’analyse guidée contient les parties de l’interface suivantes :

| Aperçu de l’interface | Élément de lʼinterface utilisateur | Description |
| --- | --- | --- |
| [Capture d’écran du rail de requête] | Rail de requêtes | Configurez les composants qui constituent un rapport. Les différents types d’analyse partagent plusieurs options de requête ; si deux types d’analyse partagent des options de requête, ils sont transférés lors du changement de type d’analyse. Voir [Types d’analyse](analysis-types/overview.md) pour plus d’informations sur les options de requête pour chaque type d’analyse respectif. |
| [Capture d&#39;écran du graphique] | Graphique | Visualisation des données renvoyées en fonction de vos entrées depuis le rail de requête et les paramètres. La visualisation que vous voyez dépend du type de vue au-dessus du graphique. Les types d’affichage disponibles dépendent du [Type d’analyse](analysis-types/overview.md) au-dessus du rail de requête. |
| [Capture d&#39;écran du tableau] | Tableau | Représentation sous forme de tableau des données renvoyées en fonction de l’entrée que vous avez reçue du rail de requête et des paramètres. Les colonnes du tableau dépendent du type d’affichage situé au-dessus du graphique. Les types d’affichage disponibles dépendent du [Type d’analyse](analysis-types/overview.md) au-dessus du rail de requête. |
| [Capture d’écran des paramètres] | Paramètres | Plusieurs options au-dessus du graphique qui vous permettent de personnaliser la manière dont le graphique et le tableau renvoient des données.<ul><li>**Type d’affichage**: Sélecteur déroulant qui permet de présenter des données pour un [Type d’analyse](analysis-types/overview.md) d&#39;une manière différente. Chaque type d’analyse possède au moins deux types de vues.</li><li>**Paramètres du graphique**: Ajustez à quoi ressemble votre graphique et quels événements vous souhaitez qu’il utilise. Les options disponibles dépendent du type de vue sélectionné.</li><li>**Période**: Sélecteur de calendrier qui vous permet de déterminer la période du rapport. Certains types d’analyse autorisent également des intervalles, par exemple, quotidiens, hebdomadaires ou mensuels.</li><li>**Insights**: Fournit des informations contextuelles en fonction du rapport que vous affichez. Vous pouvez afficher ou masquer ces informations à l’aide de l’icône d’ampoule située en haut à droite.</li></ul> |
| [Capture d’écran du menu Analyse] | Menu Analyse | Commandes en haut à droite de l’analyse guidée qui fournissent des actions générales.<ul><li>**Sélecteur de vue de données**: Modifiez la vue de données utilisée par cette analyse. Lorsque vous modifiez la vue de données, les composants disponibles dans le rail de requête changent également.</li><li>**Enregistrer**: Enregistre l’analyse. Si vous enregistrez une nouvelle analyse, une fenêtre modale s’affiche et vous demande un nom et une description.</li><li>**Enregistrer sous**: Enregistre l’analyse séparément de l’analyse actuelle, créant ainsi une copie. Une fenêtre modale s’affiche, qui demande un nouveau nom et une nouvelle description.</li><li>**Ouvrir dans Workspace**: Recrée l’analyse guidée actuelle dans Analysis Workspace. Le projet Workspace est créé dans un nouvel onglet afin d’éviter toute interruption lors de l’utilisation de l’analyse guidée. Utilisez cette commande lorsque l’analyse guidée ne vous donne pas tout à fait la flexibilité ou les informations spécifiques que vous recherchez. Par exemple, vous souhaitez qu’une [Tendances](analysis-types/trends.md) rapport qui utilise les sessions pour un segment et les personnes pour un autre segment.</li><li>**Télécharger PNG**: Télécharge le graphique sous la forme d’un graphique `.png`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.</li><li>**SVG de téléchargement**: Télécharge le graphique sous la forme d’un graphique `.svg`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.</li></ul> |

{style="table-layout:auto"}

## Autorisations

Adobe prévoit de fournir des autorisations spécifiques à l’analyse guidée à l’avenir.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
