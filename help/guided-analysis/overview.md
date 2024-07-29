---
title: Vue d’ensemble des analyses guidées
description: Méthode d’analyse des données dans Customer Journey Analytics qui permet aux équipes produit d’obtenir rapidement des informations de qualité. Également appelé Product Analytics.
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 2addd3d17f62da69eb6636d987931fc21df07af5
workflow-type: ht
source-wordcount: '1399'
ht-degree: 100%

---

# Vue d’ensemble des analyses guidées

L’analyse guidée permet aux utilisateurs et utilisatrices d’obtenir des données et des informations en libre-service de haute qualité sur le parcours client au moyen de workflows guidés, reposant sur les mêmes données cross-canal de Customer Journey Analytics. Les équipes interfonctionnelles, du marketing au produit, peuvent se connecter en temps réel pour utiliser et comprendre ces rapports.

Tout comme Analysis Workspace et les cartes de performance mobiles, l’analyse guidée utilise les données d’une [Vue des données](../data-views/data-views.md), qui référence les données dans Adobe Experience Platform au moyen d’une [Connexion](../connections/overview.md). De nombreux rapports créés dans les analyses guidées peuvent facilement être transférés vers Analysis Workspace pour effectuer des recherches supplémentaires.

Les vues d’analyse guidée suivantes sont disponibles :

| Type d’analyse | Type de vue | Description |
| --- | --- | --- |
| [!UICONTROL Matrice des fonctionnalités] | [Engagement](types/engagement.md) | Comprendre l’étendue et la profondeur de l’engagement des fonctionnalités. |
| [!UICONTROL Entonnoir] | [Friction](types/friction.md) | Comparez les taux de conversion entre les étapes. |
| [!UICONTROL Entonnoir] | [Tendances de conversion](types/conversion-trends.md) | Suivez l’évolution des taux de conversion au fil du temps. |
| [!UICONTROL Impact] | [Version](types/release.md) | Comparez les performances sur des périodes égales avant et après le lancement. |
| [!UICONTROL Impact] | [Première utilisation](types/first-use.md) | Mesurez l’impact de la première utilisation des fonctionnalités sur les indicateurs clés. |
| [!UICONTROL Rétention] | [Taux de fidélisation](types/retention-rates.md) | Mesurez les habitudes de retour de vos utilisateurs et de vos utilisatrices. |
| [!UICONTROL Tendances] | [Utilisation](types/usage.md) | Mesurez l’interaction client au fil du temps. |
| [!UICONTROL Tendances] | [Fréquence](types/frequency.md) | Mesurez l’engagement par la fréquence d’utilisation. |
| [!UICONTROL Croissance des utilisateurs et des utilisatrices] | [Actif](types/active.md) | Identifiez les nouvelles personnes, celles qui ont été conservées, celles qui reviennent ou celles qui sont inactives. |
| [!UICONTROL Croissance des utilisateurs et des utilisatrices] | [Croissance nette](types/net-growth.md) | Êtes-vous en train de gagner ou de perdre des utilisateurs et utilisatrices ? |
| [!UICONTROL Flux d’utilisateur ou d’utilisatrice] | [Journal](types/timeline.md) | Explorez les modèles de l’activité de la session. |

{style="table-layout:auto"}

## Accéder à

Si votre entreprise est configurée pour l’analyse guidée, vous pouvez y accéder à partir de la page d’accueil de Customer Journey Analytics.

1. Cliquez sur **[!UICONTROL Analyse guidée]** dans la page d’accueil, qui vous permet d’accéder directement à la [Vue des tendances d’utilisation](types/usage.md).

   ![Vignette Page de destination](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Cliquez sur **[!UICONTROL Créer]** pour afficher les différentes options d’affichage et choisir un point de départ différent pour votre analyse.

   ![Créer une boîte de dialogue modale](assets/create-new-modal.png){style="border:1px solid gray"}

Si votre entreprise n’est pas encore configurée pour l’analyse guidée, contactez l’équipe Adobe en charge des comptes.

## Interface

L’interface d’analyse guidée se présente sous la forme de question et de réponse. Formulez votre question dans le rail de requête, puis obtenez une réponse avec des informations écrites, un graphique et un tableau. Vous pouvez ensuite poser la question suivante avec les types de vues et les paramètres de visualisation.

L’analyse guidée utilise les éléments suivants de l’interface utilisateur :

| Aperçu de l’interface | Élément de lʼinterface utilisateur | Description |
| --- | --- | --- |
| ![Rail de requête](assets/query-rail.png){style="border:1px solid gray"} | Rail de requête | Configurez votre « question » en sélectionnant les composants (événements, propriétés et segments) qui constituent une analyse. Les options suivantes sont disponibles pour tous les types de vues, avec des paramètres supplémentaires disponibles par vue. <ul><li>**Sélecteur d’analyse** : liste déroulante qui permet de basculer vers un nouveau type d’analyse. Les sélections de requêtes sont conservées dans les limites autorisées pour le nouveau type d’analyse.</li><li>**Sélecteur de vue** : liste déroulante qui permet de basculer vers une nouvelle vue (« réponse ») pour la requête que vous avez formulée. Vos sélections de requêtes sont conservées dans les limites autorisées pour le nouveau type de vue.</li><li>**Événements** : événements que vous souhaitez mesurer. Chaque type de vue applique différentes limites quant au nombre d’événements que vous pouvez configurer.</li><li>**Filtres** : utilisez l’icône ![Filtre](assets/filter.png) dans la section Événements ou Segments pour préciser des propriétés spécifiques. Lorsqu’une propriété est sélectionnée, les deux critères de filtre standard (tels que [!UICONTROL Est égal à], [!UICONTROL Contient] ou [!UICONTROL Se termine par]) et les 1 000 premières valeurs de propriété sont disponibles.</li><li>**Compté comme** : méthode de comptage à appliquer aux événements sélectionnés.</li><li>**Segments** : segments que vous souhaitez mesurer. Chaque type de vue applique différentes limites quant au nombre de segments que vous pouvez configurer.</li></ul> |
| ![Graphique](assets/chart.png){style="border:1px solid gray"} | Graphique | Visualisation des données renvoyées en fonction de vos entrées dans le rail de requête et les paramètres. La visualisation que vous voyez dépend de la vue et des paramètres au-dessus du graphique. Le graphique comprend également les éléments suivants : <ul><li>**Info-bulles** : passez la souris sur un point de données de graphique pour afficher une info-bulle contenant plus d’informations.</li><li>**Légende** : passez la souris sur la série de légendes du graphique pour afficher les définitions lorsqu’elles sont disponibles, vous concentrer sur cette série et masquer temporairement d’autres séries. Masquez une série dans la légende en cliquant dessus.</li><li>**Annotations** : les [annotations](../components/annotations/overview.md) applicables sont visibles entre la visualisation et la légende. Elles s’affichent sous la forme d’une icône ![Icône Annotation](assets/annotation.png) dans la couleur configurée de l’annotation. Les types de vues qui affichent des données au fil du temps placent l’icône ![Icône Annotation](assets/annotation.png) sous la date ou la période configurée. Les types de vues qui n’affichent pas des données au fil du temps affichent l’icône ![Icône Annotation](assets/annotation.png) dans le coin inférieur droit du graphique.</li><li>**Actions de clic** : affichez les actions disponibles suivantes en cliquant avec le bouton gauche de la souris sur un point de données. Les options incluent **Enregistrer le segment**.</li></ul> |
| ![Tableau](assets/table.png){style="border:1px solid gray"} | Tableau | Représentation sous forme de tableau des données renvoyées en fonction de votre entrée dans le rail de requête et les paramètres. Les colonnes du tableau dépendent du type de vue situé au-dessus du graphique. Le tableau comprend également : <ul><li>**Actions de clic** : masquez ou affichez une série de graphiques en faisant basculer l’icône ![Icône Afficher/Masquer](assets/hide-in-chart.png) de chaque ligne. Pour accéder à d’autres actions, cliquez sur le menu **[!UICONTROL Plus]**. Les options incluent **Enregistrer le segment**.</li></ul> |
| ![Paramètres de visualisation](assets/visualization-settings.png){style="border:1px solid gray"} | Paramètres de visualisation | Options au-dessus du graphique vous permettant de poser la question suivante et de personnaliser la manière dont le graphique et le tableau renvoient des données. Les options suivantes sont disponibles pour tous les types de vues, avec des paramètres supplémentaires disponibles par vue. <ul><li>**Paramètres du graphique** : affinez l’affichage de votre graphique et de votre tableau. Les options disponibles dépendent de la vue sélectionnée.</li><li>**Période** : sélecteur de calendrier qui permet de déterminer la période de l’analyse. Vous pouvez également sélectionner un intervalle pour les vues de tendances, par exemple, quotidiennes, hebdomadaires ou mensuelles.</li><li>**Informations** : informations contextuelles selon l’analyse que vous affichez. Ces informations fournissent des observations pour l’analyse actuelle. Si plusieurs informations sont disponibles, vous pouvez les afficher à l’aide des flèches situées à droite. Vous pouvez activer/désactiver la visibilité de cette zone à l’aide de l’icône d’ampoule située en haut à droite.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | Menu | Commandes en haut à droite de l’analyse guidée qui fournissent des actions globales pour votre analyse.<ul><li>**Sélecteur de vue de données** : modifiez la vue de données utilisée par l’analyse. Lorsque vous modifiez la vue de données, les composants disponibles dans le rail de requête changent également.</li><li>**Copier le lien** : copie un lien vers l’analyse dans le presse-papiers. Vous recevez une invitation à enregistrer avant de partager.</li><li>**Partager** : ouvre la boîte de dialogue modale de partage, qui contient d’autres options de partage pour des utilisateurs et utilisatrices individuels ou des groupes. Vous pouvez partager une analyse avec d’autres personnes ou générer un lien de partage avec n’importe qui.</li><li>**Enregistrer** : enregistre l’analyse. Si vous enregistrez une nouvelle analyse, une fenêtre modale s’affiche et vous demande un nom et une description.</li><li>**Enregistrer sous** : enregistre l’analyse séparément de l’analyse actuelle, en créant une copie. Une fenêtre modale s’affiche et vous demande un nouveau nom et une nouvelle description.</li><li>**Ouvrir dans Workspace** : recrée l’analyse guidée actuelle dans Analysis Workspace. Le projet Workspace est créé dans un nouvel onglet afin d’éviter toute interruption lors de l’utilisation de l’analyse guidée. Il s’agit d’une copie de l’analyse qui, une fois ouverte, n’est pas synchronisée avec l’analyse guidée d’origine. Utilisez cette commande lorsque vous souhaitez transmettre à votre équipe d’analyse ou approfondir les données dans la mesure permise par l’analyse guidée.</li><li>**Copier dans le presse-papiers** : copie les éléments graphiques du graphique dans le presse-papiers, pour pouvoir les coller dans d’autres applications. Le rail de requête et le tableau ne sont pas inclus dans le graphique.</li><li>**Télécharger PNG** : télécharge les éléments graphiques du graphique sous forme de `.png`. Le rail de requête et le tableau ne sont pas inclus dans le graphique.</li><li>**Télécharger un CSV** : télécharge les données du tableau sous forme de `.csv`. Le rail de requête et le graphique ne sont pas inclus dans le fichier.</li></ul> |

{style="table-layout:auto"}

## Approvisionnement

Les vues d’analyse guidée sont incluses dans les packages Customer Journey Analytics de la manière suivante :

| Package | Vues disponibles |
| --- | --- |
| [!UICONTROL Modules complémentaires CJA] | Tendances : utilisation, tendances : fréquence, entonnoir : friction, entonnoir : tendances de conversion, rétention : taux de rétention, croissance des utilisateurs et des utilisatrices : actifs, croissance des utilisateurs et des utilisatrices : croissance nette |
| [!UICONTROL CJA Foundation] | Tendances : utilisation |
| [!UICONTROL CJA Select] | Vues Foundation + Tendances : fréquence, entonnoir : friction, entonnoir : tendances de conversion, rétention : taux de rétention, croissance des utilisateurs et des utilisatrices : actifs, croissance des utilisateurs et des utilisatrices : croissance nette |
| [!UICONTROL CJA Prime] | Vues Select + Flux des utilisateurs et des utilisatrices : chronologie, matrice des fonctionnalités : engagement, impact : publication, impact : première utilisation |
| [!UICONTROL CJA Ultimate] | Vues Prime |

{style="table-layout:auto"}

Les administrateurs et les administratrices de profil de produit peuvent ajouter ou supprimer l’accès à l’analyse guidée dans Adobe Admin Console.

1. Connectez-vous à [Adobe Admin Console](https://adminconsole.adobe.com).
1. Sélectionnez **[!UICONTROL Customer Journey Analytics]** dans la liste des produits.
1. Sélectionnez le profil de produit souhaité pour les autorisations que vous souhaitez modifier.
1. Cliquez sur l’onglet **[!UICONTROL Autorisations]**, puis sur **[!UICONTROL Modifier]** sous [!UICONTROL Outils de création de rapports].
1. Cliquez sur l’icône Plus en regard d’**[!UICONTROL Accès aux analyses guidées]** dans la liste des [!UICONTROL Éléments d’autorisation disponibles], ce qui l’ajoute à la liste des [!UICONTROL Éléments d’autorisation inclus].
1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!TIP]
>
>Certains administrateurs et administratrices préfèrent activer l’analyse guidée et désactiver Analysis Workspace pour les nouveaux utilisateurs et utilisatrices dans Customer Journey Analytics. Une fois que ces utilisateurs et utilisatrices se seront familiarisés avec le produit et vos données organisationnelles, vous pourrez alors activer l’accès à Analysis Workspace.
