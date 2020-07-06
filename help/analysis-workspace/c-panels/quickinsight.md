---
description: Quick Insights est un outil destiné aux nouveaux utilisateurs de Workspace qui les guide dans la création de tableaux de données et de visualisations.
title: Panneau Quick Insights
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 6%

---


# Panneau Quick Insights

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL Le panneau Aperçu]** rapide est actuellement en cours de test limité. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights] fournit des conseils aux non-analystes et aux nouveaux utilisateurs d’[!UICONTROL Analysis Workspace] pour savoir comment répondre rapidement et facilement à des besoins professionnels. C&#39;est aussi un outil idéal pour les utilisateurs expérimentés qui veulent répondre rapidement à une question simple sans avoir à construire eux-mêmes un tableau.

Lorsque vous utilisez cet [!UICONTROL Analysis Workspace]pour la première fois, vous pouvez vous demander quelles visualisations seraient les plus utiles, quelles dimensions et mesures pourraient faciliter les statistiques, où faire glisser des éléments, où créer un segment, etc.

Pour y remédier, et en fonction de l’utilisation des composants de données par votre propre société dans l’ [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] utilise un algorithme qui vous présente les dimensions, mesures, segments et plages de dates les plus populaires que votre société utilise. En fait, vous verrez des dimensions, des mesures et des segments balisés comme [!UICONTROL populaires] dans la liste déroulante, comme indiqué ici :

![](assets/popular-tag.png)

[!UICONTROL Les statistiques] rapides vous aident à

* Créez correctement un tableau de données et une visualisation correspondante dans l’ [!UICONTROL Analysis Workspace].
* Apprenez la terminologie et le vocabulaire des composants de base et des éléments d&#39; [!UICONTROL Analysis Workspace].
* Effectuez des ventilations simples de dimensions, ajoutez plusieurs mesures ou comparez facilement des segments dans un tableau [!UICONTROL à structure]libre.
* Modifiez ou testez divers types de visualisation pour trouver rapidement et intuitivement l&#39;outil de recherche pour votre analyse.

## Terminologie clé de base

Voici quelques-uns des termes de base que vous devez connaître. Chaque tableau de données se compose de deux blocs fonctionnels (composants) ou plus que vous utilisez pour raconter l’historique de vos données.

| Bloc de création (composant) | Définition |
|---|---|
| [!UICONTROL Dimension] | Les dimensions sont des descriptions ou des caractéristiques des données de mesure qui peuvent être visualisées, ventilées et comparées dans un projet. Il s’agit de valeurs et de dates non numériques qui se divisent en éléments de dimension. Par exemple, &quot;navigateur&quot; ou &quot;page&quot; sont des dimensions. |
| [!UICONTROL Élément de dimension] | Les éléments de dimension sont des valeurs individuelles pour une dimension. Par exemple, les éléments de dimension pour la dimension de navigateur seraient &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| [!UICONTROL Mesure] | Les mesures sont des informations quantitatives sur l’activité des visiteurs, telles que les affichages, les clics publicitaires, les actualisations, la durée moyenne de consultation, les unités, les commandes, les recettes, etc. |
| [!UICONTROL Visualisation] | Workspace offers [a number of visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others. |
| [!UICONTROL Ventilation des dimensions] | Une ventilation de dimension est un moyen de ventiler une dimension selon d’autres dimensions. Dans notre exemple, vous pouvez ventiler les États américains en fonction des périphériques mobiles pour obtenir les visites des périphériques mobiles par état, ou vous pouvez ventiler les périphériques mobiles en fonction des types de périphériques mobiles, des régions, des campagnes internes, etc. |
| [!UICONTROL Segment] | Les segments vous permettent d’identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d’interactions sur le site Web. Par exemple, vous pouvez créer des segments de [!UICONTROL Visiteurs] en fonction d’attributs : type de navigateur, périphérique, nombre de visites, pays, sexe ou selon les interactions : campagnes, recherche de mots-clés, moteur de recherche ou en fonction des sorties et des entrées : visiteurs de Facebook, d’un landing page défini, d’un domaine référent ou basés sur des variables personnalisées : champ de formulaire, catégories définies, ID de client. |

## Prise en main de Quick Insights

1. Connectez-vous à Adobe Analytics à l’aide des informations d’identification qui vous ont été fournies.
1. Accédez à [!UICONTROL Workspace] et cliquez sur **[!UICONTROL Créer un nouveau projet]** , puis cliquez sur **[!UICONTROL Quick Insights]**(Statistiques rapides). (Vous pouvez également accéder à ce panneau à partir du menu **[!UICONTROL Panneau]** dans le rail de gauche.)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. Lors de votre premier début, passez en revue le court didacticiel qui vous apprend quelques-uns des concepts de base du panneau  Aperçu rapide. Ou cliquez sur pour **[!UICONTROL Ignorer le didacticiel]**.
1. Sélectionnez vos blocs de création (également appelés composants) : dimensions (orange), mesures (vert), segments (bleu) ou plages de dates (violet) Vous devez sélectionner au moins une dimension et une mesure pour qu’un tableau soit automatiquement créé.

   ![](assets/qibuilder2.png)

   Vous pouvez sélectionner les blocs de création de trois manières différentes :
   * Faites-les glisser depuis le rail de gauche.
   * Si vous savez ce que vous cherchez : Si vous tapez un Début et [!UICONTROL Quick Insights] , vous n&#39;aurez qu&#39;à remplir les champs vides.
   * Cliquez sur la liste déroulante et recherchez la liste.

1. Lorsque vous avez ajouté au moins une dimension et une mesure, les éléments suivants sont créés pour vous :

   * Tableau à structure libre avec la dimension (ici, Etats-Unis) verticalement et la mesure (ici, Visites) horizontalement en haut. Consultez ce tableau :
   ![](assets/qibuilder3.png)

   * Visualisation connexe, dans ce cas un graphique [à](/help/analysis-workspace/visualizations/bar.md)barres. La visualisation qui est générée dépend du type de données que vous avez ajoutées au tableau. Par défaut, toutes les données temporelles (telles que [!UICONTROL Visites] par jour/mois) correspondent à un graphique [!UICONTROL linéaire] . Par défaut, toutes les données non temporelles (telles que [!UICONTROL Visites] par [!UICONTROL périphérique]) correspondent à un graphique à [!UICONTROL barres] . Vous pouvez modifier le type de visualisation en cliquant sur la flèche de liste déroulante en regard du type de visualisation.


1. (Facultatif) Recherchez les dimensions et affichez les éléments de dimension en cliquant sur la flèche > à droite en regard de la dimension.

1. Essayez d&#39;ajouter d&#39;autres perfectionnements comme décrit ci-dessous sous &quot;Autres conseils&quot;.

1. Enregistrez votre projet en cliquant sur **[!UICONTROL Projet > Enregistrer]**.

## Plus de conseils

D’autres conseils utiles s’affichent dans le créateur [!UICONTROL d’aperçus]rapides, certains en fonction de votre dernière action.

* Pour commencer, suivez le didacticiel **[!UICONTROL Plus de conseils]** : Accédez-y via l’aide (?) en regard du titre [!UICONTROL Quick Insights] . Ce didacticiel s’affiche 24 heures après la création d’un projet avec au moins une dimension et une mesure.

   ![](assets/qibuilder4.png)

* **Ventilation par**: Vous pouvez utiliser jusqu’à 3 niveaux de ventilations sur les dimensions pour analyser en détail les données dont vous avez réellement besoin.

   ![](assets/qibuilder5.png)

* **Ajouter d’autres mesures**: Vous pouvez ajouter jusqu’à 2 mesures supplémentaires en utilisant l’opérateur ET pour les ajouter au tableau.

   ![](assets/qibuilder6.png)

* **Ajouter d’autres segments**: Vous pouvez ajouter jusqu’à 2 segments supplémentaires en utilisant les opérateurs ET ou OU pour les ajouter au tableau. Regardez ce qui se passe dans le tableau lorsque vous ajoutez des utilisateurs mobiles OU des Visiteurs fidèles. Ils sont situés les uns à côté des autres, au-dessus des mesures. Si vous ajoutiez Utilisateurs mobiles ET Visiteurs fidèles, les résultats des deux segments s’afficheraient ensemble et ils seraient empilés les uns sur les autres dans le tableau.

   ![](assets/qibuilder7.png)

## Limites connues

Si vous essayez de modifier directement dans le tableau, le panneau [!UICONTROL Aperçu] rapide ne sera plus synchronisé. Vous pouvez rétablir les paramètres [!UICONTROL Quick Insights] précédents en cliquant sur **[!UICONTROL Resync Builder]** dans la partie supérieure droite du panneau.

![](assets/qibuilder9.png)

Vous recevrez un avertissement avant d’ajouter quelque chose directement au tableau :

![](assets/qibuilder8.png)

Dans le cas contraire, la création directe entraînera le comportement du tableau en tant que tableau à structure libre traditionnel, sans les fonctionnalités utiles pour les nouveaux utilisateurs.

