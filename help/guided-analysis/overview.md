---
title: Aperçu des analyses guidées
description: Méthode d’analyse des données dans Customer Journey Analytics qui permet aux équipes produit de générer facilement des rapports et des informations.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 10%

---

# Aperçu des analyses guidées

{{release-limited-testing}}

L’analyse guidée est un format de création de rapports qui permet aux équipes produit de répondre rapidement à leurs besoins de données de manière à ce qu’elles puissent prendre davantage de décisions liées aux données. Les équipes interfonctionnelles peuvent se connecter en temps réel pour utiliser et comprendre ces rapports.

Tout comme pour les Fiches d’évaluation Analysis Workspace et Mobile, un rapport d’analyse guidée utilise les données d’une [Vue des données](../data-views/data-views.md), qui référence les données dans Adobe Experience Platform au moyen d’une [Connexion](../connections/overview.md). Tous les rapports créés dans les analyses guidées peuvent facilement être transférés vers Analysis Workspace pour effectuer des recherches supplémentaires.

L’analyse guidée offre plusieurs méthodes d’analyse des données. Ces types d’affichage peuvent afficher les mêmes données de différentes manières, ce qui génère différentes informations à l’aide des mêmes événements et segments. Vous obtenez différents rails de requête et options de visualisation en fonction du type d’affichage que vous choisissez. Vous pouvez basculer librement entre les types de vue et tout composant de rail de requête applicable peut être transféré si le type de vue les prend en charge.

L’analyse guidée classe les types de vues dans **Types d’analyse**. Les types d’analyse et d’affichage suivants sont disponibles :

| Type d’analyse | Type de vue | Description |
| --- | --- | --- |
| Impact | [Version](types/release.md) | Comparer les performances sur des périodes égales avant et après le lancement. |
| Impact | [Première utilisation](types/first-use.md) | Mesurer l’impact de la première utilisation des fonctionnalités sur les indicateurs clés. |
| Entonnoir | [Friction](types/friction.md) | Comparer les taux de conversion entre les étapes. |
| Entonnoir | [Tendances de conversion](types/conversion-trends.md) | Suivre l’évolution des taux de conversion au fil du temps. |
| Croissance des utilisateurs et des utilisatrices | [Actif](types/active.md) | Mesurer la croissance de la base d’utilisateurs et utilisatrices de votre produit. |
| Croissance des utilisateurs et des utilisatrices | [Croissance nette](types/net-growth.md) | Gains et pertes de l’utilisateur du solde. |
| Tendances | [Utilisation](types/usage.md) | Mesurer l’interaction client au fil du temps. |

{style="table-layout:auto"}

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
| ![Rail de requêtes](assets/query-rail.png) | Rail de requêtes | Configurez les composants qui constituent un rapport. Les différents types d’analyse partagent plusieurs options de requête ; si deux types d’analyse partagent des options de requête, ils sont transférés lors du changement de type d’analyse. |
| ![Graphique](assets/chart.png) | Graphique | Visualisation des données renvoyées en fonction de vos entrées depuis le rail de requête et les paramètres. La visualisation que vous voyez dépend du type de vue au-dessus du graphique. Les types d’affichage disponibles dépendent du type d’analyse situé au-dessus du rail de requête. |
| ![Tableau](assets/table.png) | Tableau | Représentation sous forme de tableau des données renvoyées en fonction de l’entrée que vous avez reçue du rail de requête et des paramètres. Les colonnes du tableau dépendent du type d’affichage situé au-dessus du graphique. Les types d’affichage disponibles dépendent du type d’analyse situé au-dessus du rail de requête. |
| ![Paramètres de visualisation](assets/visualization-settings.png) | Paramètres de visualisation | Plusieurs options au-dessus du graphique qui vous permettent de personnaliser la manière dont le graphique et le tableau renvoient des données.<ul><li>**Type d’affichage**: Sélecteur de liste déroulante qui permet de présenter différemment les données d’un type d’analyse donné. Chaque type d’analyse possède au moins deux types de vues.</li><li>**Paramètres du graphique**: Ajustez à quoi ressemble votre graphique et quels événements vous souhaitez qu’il utilise. Les options disponibles dépendent du type de vue sélectionné.</li><li>**Période**: Sélecteur de calendrier qui vous permet de déterminer la période du rapport. Certains types d’analyse autorisent également des intervalles, par exemple, quotidiens, hebdomadaires ou mensuels.</li><li>**Insights**: Fournit des informations contextuelles en fonction du rapport que vous affichez. Vous pouvez afficher ou masquer ces informations à l’aide de l’icône d’ampoule située en haut à droite.</li></ul> |
| ![Menu](assets/menu.png) | Menu Analyse | Commandes en haut à droite de l’analyse guidée qui fournissent des actions générales.<ul><li>**Sélecteur de vue de données**: Modifiez la vue de données utilisée par cette analyse. Lorsque vous modifiez la vue de données, les composants disponibles dans le rail de requête changent également.</li><li>**Enregistrer**: Enregistre l’analyse. Si vous enregistrez une nouvelle analyse, une fenêtre modale s’affiche et vous demande un nom et une description.</li><li>**Enregistrer sous**: Enregistre l’analyse séparément de l’analyse actuelle, créant ainsi une copie. Une fenêtre modale s’affiche, qui demande un nouveau nom et une nouvelle description.</li><li>**Ouvrir dans Workspace**: Recrée l’analyse guidée actuelle dans Analysis Workspace. Le projet Workspace est créé dans un nouvel onglet afin d’éviter toute interruption lors de l’utilisation de l’analyse guidée. Utilisez cette commande lorsque l’analyse guidée ne vous donne pas tout à fait la flexibilité ou les informations spécifiques que vous recherchez. Par exemple, vous souhaitez qu’une [Utilisation](types/usage.md) rapport qui utilise les sessions pour un segment et les personnes pour un autre segment.</li><li>**Télécharger PNG**: Télécharge le graphique sous la forme d’un graphique `.png`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.</li><li>**SVG de téléchargement**: Télécharge le graphique sous la forme d’un graphique `.svg`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.</li></ul> |

{style="table-layout:auto"}

## Attribution des privilèges d’accès

L’analyse guidée fait partie de l’Adobe Product Analytics, qui est un module complémentaire payant de Customer Journey Analytics. Si votre entreprise souhaite commencer à utiliser cette fonctionnalité, contactez votre équipe de compte d’Adobe.

Une fois que votre entreprise a été configurée pour utiliser l’analyse guidée, les administrateurs de profil de produit peuvent lui accorder l’accès dans Adobe Admin Console.

1. Connectez-vous au [Adobe Admin Console](https://adminconsole.adobe.com).
1. Sélectionner **[!UICONTROL Customer Journey Analytics]** dans la liste des produits.
1. Sélectionnez le profil de produit souhaité pour modifier les autorisations.
1. Cliquez sur le bouton **[!UICONTROL Autorisations]** , puis cliquez sur **[!UICONTROL Modifier]** under [!UICONTROL Outils de création de rapports].
1. Cliquez sur l’icône Plus en regard de **[!UICONTROL Accès aux analyses guidées]** dans la liste de [!UICONTROL Éléments d’autorisation disponibles] pour l’ajouter à la liste de [!UICONTROL Éléments d’autorisation inclus].
1. Cliquez sur **[!UICONTROL Enregistrer]**.
