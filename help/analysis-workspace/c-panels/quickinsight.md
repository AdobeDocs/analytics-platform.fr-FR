---
description: Quick Insights est un outil destiné aux nouveaux utilisateurs de Workspace pour les aider à créer des tableaux de données et des visualisations.
title: Panneau Quick Insights
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 74%

---

# Panneau Quick Insights

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL Quick]** Insightspanel est actuellement en test limité. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights] fournit des conseils aux non-analystes et aux nouveaux utilisateurs d’[!UICONTROL Analysis Workspace] pour savoir comment répondre rapidement et facilement à des besoins professionnels. Il s’agit également d’un outil idéal pour les utilisateurs expérimentés qui souhaitent une réponse rapide à une question simple sans avoir à créer eux-mêmes un tableau.

Lorsque vous commencez à utiliser cette [!UICONTROL Analysis Workspace], vous pouvez vous demander quelles visualisations seraient les plus utiles, quelles dimensions et mesures pourraient faciliter les insights, où faire glisser et déposer des éléments, où créer un filtre, etc.

Pour ce faire, et en fonction de l’utilisation des composants de données par votre propre entreprise dans [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] utilise un algorithme qui vous présente les dimensions, mesures, filtres et périodes les plus populaires utilisés par votre entreprise. En fait, vous verrez des dimensions, des mesures et des filtres balisés comme [!UICONTROL Popular] dans la liste déroulante, comme illustré ici :

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] vous permet :

* de créer correctement un tableau de données et une visualisation correspondante dans [!UICONTROL Analysis Workspace] ;
* d’apprendre la terminologie et le vocabulaire des éléments et des composants de base d’[!UICONTROL Analysis Workspace] ;
* Effectuez des ventilations simples de dimensions, ajoutez plusieurs mesures ou comparez facilement des filtres dans une [!UICONTROL table à structure libre].
* de modifier ou de tester divers types de visualisation pour trouver rapidement et intuitivement l’outil de recherche pour votre analyse.

## Terminologie clé de base

Voici quelques-uns des termes de base que vous devez connaître. Chaque tableau de données se compose de deux blocs de construction (composants) ou plus que vous utilisez pour décrire vos données.

| Bloc de construction (composant) | Définition |
|---|---|
| [!UICONTROL Dimension] | Les dimensions sont des descriptions ou caractéristiques de données de mesure qui peuvent être affichées, ventilées et comparées dans un projet. Il s’agit de valeurs et de dates non numériques qui se ventilent en éléments de dimension. Par exemple, « navigateur » ou « page » sont des dimensions. |
| [!UICONTROL Élément de dimension] | Les éléments de dimension sont des valeurs individuelles d’une dimension. Par exemple, les éléments de dimension pour la dimension de navigateur seraient « Chrome », « Firefox », « Edge », etc. |
| [!UICONTROL Mesure] | Les mesures sont des informations quantitatives sur l’activité des visiteurs, telles que les affichages, les clics publicitaires, les actualisations, la durée moyenne de consultation, les unités, les commandes, le chiffre d’affaires, etc. |
| [!UICONTROL Visualisation] | Workspace offre [un certain nombre de visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) afin de créer des représentations visuelles de vos données, telles que des graphiques à barres, des graphiques en anneau, des histogrammes, des graphiques en courbes, des cartes, des tracés différés, etc. |
| [!UICONTROL Ventilation des dimensions] | Une ventilation de dimension est un moyen de ventiler une dimension en fonction d’autres dimensions. Dans notre exemple, vous pouvez ventiler les États américains en fonction des appareils mobiles pour obtenir les visites des appareils mobiles par État. Vous pouvez également ventiler les appareils mobiles en fonction des types d’appareils mobiles, des régions, des campagnes internes, etc. |
| [!UICONTROL filter] | Les filtres permettent d’identifier des sous-ensembles de visiteurs selon des caractéristiques ou des interactions web. Par exemple, vous pouvez créer des filtres [!UICONTROL Visiteur] en fonction d’attributs : type de navigateur, appareil, nombre de visites, pays, sexe ou selon les interactions : campagnes, recherche de mots-clés, moteur de recherche ou en fonction des sorties et des entrées : visiteurs provenant de Facebook, d’une page d’entrée définie, d’un domaine référent ou d’après des variables personnalisées : champ de formulaire, catégories définies, ID de client. |

## Prise en main de Quick Insights

1. Connectez-vous à Adobe Analytics à l’aide des identifiants qui vous ont été fournis.
1. Accédez à [!UICONTROL Workspace], cliquez sur **[!UICONTROL Créer un projet]**, puis sur **[!UICONTROL Quick Insights]**. (Vous pouvez également accéder à ce panneau à partir du menu **[!UICONTROL Panneau]** dans le rail de gauche.)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. Lorsque vous commencez, consultez le petit tutoriel qui vous apprend quelques bases sur le [!UICONTROL Panneau Quick Insights]. Vous pouvez également cliquer sur **[!UICONTROL Ignorer le tutoriel]**.
1. Sélectionnez vos blocs de création (également appelés composants) : dimensions (orange), mesures (vert), filtres (bleu) ou plages de dates (violet). Vous devez sélectionner au moins une dimension et une mesure pour qu’un tableau soit automatiquement créé.

   ![](assets/qibuilder2.png)

   Vous pouvez sélectionner les blocs de construction de trois manières différentes :
   * Glissez et déposez-les à partir du rail de gauche.
   * Si vous savez ce que vous cherchez : commencez à taper et [!UICONTROL Quick Insights] complétera les informations pour vous.
   * Cliquez sur la liste déroulante pour effectuer une recherche dans la liste.

1. Lorsque vous avez ajouté au moins une dimension et une mesure, les éléments suivants sont créés pour vous :

   * Un tableau à structure libre avec la dimension (ici, États américains) à la verticale et la mesure (ici, Visites) en haut à l’horizontale. Consultez ce tableau :

   ![](assets/qibuilder3.png)

   * Une visualisation correspondante, dans ce cas un [graphique à barres](/help/analysis-workspace/visualizations/bar.md). La visualisation qui est générée dépend du type de données que vous avez ajoutées au tableau. Toutes les données temporelles (telles que [!UICONTROL Visites] par jour/mois) sont présentées sous forme de graphique [!UICONTROL en courbes]. Toutes les données non temporelles (telles que [!UICONTROL Visites] par [!UICONTROL Appareil]) sont présentées sous forme de graphique [!UICONTROL à barres]. Vous pouvez modifier le type de visualisation en cliquant sur la flèche déroulante en regard du type de visualisation.


1. (Facultatif) Examinez les dimensions et affichez les éléments de dimension en cliquant sur la flèche vers la droite > en regard de la dimension.

1. Essayez d’affiner un peu plus votre recherche comme décrit ci-dessous sous « Plus de conseils ».

1. Enregistrez votre projet en cliquant sur **[!UICONTROL Projet > Enregistrer]**.

## Plus de conseils

D’autres astuces utiles s’affichent dans le [!UICONTROL Créateur de Quick Insights], dont certaines dépendent de votre dernière action.

* Pour commencer, suivez le tutoriel **[!UICONTROL Plus de conseils]**. Vous pouvez y accéder via l’icône d’aide (?) en regard du titre [!UICONTROL Quick Insights]. Ce tutoriel s’affiche 24 heures après la création d’un projet avec au moins une dimension et une mesure.

   ![](assets/qibuilder4.png)

* **Ventilation par** : vous pouvez utiliser jusqu’à 3 niveaux de ventilations sur les dimensions pour analyser en détail les données dont vous avez réellement besoin.

   ![](assets/qibuilder5.png)

* **Ajouter d’autres mesures** : vous pouvez ajouter jusqu’à 2 mesures supplémentaires au tableau en utilisant l’opérateur AND.

   ![](assets/qibuilder6.png)

* **Ajouter d’autres filtres** : Vous pouvez ajouter jusqu’à 2 filtres supplémentaires en utilisant les opérateurs ET ou OU pour les ajouter au tableau. Observez ce qui se passe dans le tableau lorsque vous ajoutez Utilisateurs mobiles OR Visiteurs fidèles. Ils se trouvent les uns à côté des autres, au-dessus des mesures. Si vous ajoutiez Utilisateurs mobiles ET Visiteurs fidèles, les résultats des deux filtres s’afficheraient ensemble et ils seraient empilés les uns sur les autres dans le tableau.

   ![](assets/qibuilder7.png)

## Limites connues

Si vous essayez d’effectuer des modifications directement dans le tableau, le panneau [!UICONTROL Quick Insights] ne sera plus synchronisé. Vous pouvez rétablir les paramètres précédents de [!UICONTROL Quick Insights] en cliquant sur **[!UICONTROL Resynchroniser le créateur]** dans la partie supérieure droite du panneau.

![](assets/qibuilder9.png)

Vous recevrez un avertissement avant d’effectuer un ajout directement dans le tableau :

![](assets/qibuilder8.png)

Dans le cas contraire, si la création se fait directement, le tableau se comportera désormais comme un tableau à structure libre traditionnel, sans les fonctionnalités utiles pour les nouveaux utilisateurs.
