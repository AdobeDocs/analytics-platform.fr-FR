---
description: Aperçu rapide est un outil destiné aux nouveaux utilisateurs de Workspace pour les aider à créer des tableaux de données et des visualisations.
title: Panneau d’Aperçu rapide
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 100%

---

# Panneau d’Aperçu rapide

[!UICONTROL Aperçu rapide] fournit des conseils aux non-analystes et aux nouveaux utilisateurs d’[!UICONTROL Analysis Workspace] pour savoir comment répondre rapidement et facilement à des besoins professionnels. Il s’agit également d’un outil idéal pour les utilisateurs expérimentés qui souhaitent une réponse rapide à une question simple sans avoir à créer eux-mêmes un tableau.

Lorsque vous commencez à utiliser [!UICONTROL Analysis Workspace], il se peut que vous vous interrogiez sur les visualisations les plus utiles, sur les dimensions et les mesures susceptibles de faciliter les informations, sur l’emplacement dans lequel il convient de glisser et de déposer des éléments, de créer un filtre, etc.

Pour ce faire, et en fonction de l’utilisation des composants de données par votre propre société dans [!UICONTROL Analysis Workspace], [!UICONTROL Aperçu rapide] se sert d’un algorithme qui vous présente les dimensions, mesures, filtres et périodes les plus populaires utilisés par votre société. Les dimensions, mesures et filtres désignés comme [!UICONTROL populaires] dans la liste déroulante sont indiqués ici :

![Paneau Aperçu rapide.](assets/popular-tag.png)

[!UICONTROL Aperçu rapide] vous permet :

* de créer correctement un tableau de données et une visualisation correspondante dans [!UICONTROL Analysis Workspace] ;
* d’apprendre la terminologie et le vocabulaire des éléments et des composants de base d’[!UICONTROL Analysis Workspace] ;
* d’effectuer des répartitions simples de dimensions, d’ajouter plusieurs mesures ou de comparer facilement des filtres dans un [!UICONTROL tableau à structure libre].
* de modifier ou de tester divers types de visualisation pour trouver rapidement et intuitivement l’outil de recherche pour votre analyse.

## Terminologie clé de base

Voici quelques-uns des termes de base que vous devez connaître. Chaque tableau de données se compose de deux blocs de construction (composants) ou plus que vous utilisez pour décrire vos données.

| Bloc de construction (composant) | Définition |
|---|---|
| [!UICONTROL Dimension] | Les dimensions sont des descriptions ou caractéristiques de données de mesure qui peuvent être affichées, ventilées et comparées dans un projet. Il s’agit de valeurs et de dates non numériques qui se ventilent en éléments de dimension. Par exemple, « navigateur » ou « page » sont des dimensions. |
| [!UICONTROL Élément de dimension] | Les éléments de dimension sont des valeurs individuelles d’une dimension. Par exemple, les éléments de dimension pour la dimension de navigateur seraient « Chrome », « Firefox », « Edge », etc. |
| [!UICONTROL Mesure] | Les mesures sont des informations quantitatives sur l’activité des individus, telles que les affichages, les clics publicitaires, les actualisations, la durée moyenne de consultation, les unités, les commandes, le chiffre d’affaires, etc. |
| [!UICONTROL Visualisation] | Workspace offre [un certain nombre de visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) afin de créer des représentations visuelles de vos données, telles que des graphiques à barres, des graphiques en anneau, des histogrammes, des graphiques en courbes, des cartes, des tracés différés, etc. |
| [!UICONTROL Répartition des dimensions] | Une répartition de dimension est un moyen de répartir une dimension en fonction d’autres dimensions. Dans notre exemple, vous pouvez ventiler les États américains en fonction des appareils mobiles pour obtenir les visites des appareils mobiles par État. Vous pouvez également ventiler les appareils mobiles en fonction des types d’appareils mobiles, des régions, des campagnes internes, etc. |
| [!UICONTROL Filtre] | Les filtres vous permettent d’identifier des sous-ensembles d’individus selon des caractéristiques ou des interactions web. Par exemple, vous pouvez créer des filtres [!UICONTROL Visiteur] en fonction des attributs (type de navigateur, appareil, nombre de visites, pays, genre), des interactions (campagnes, recherche de mots-clés, moteur de recherche), des sorties et des entrées (individus venus de Facebook, d’une page de destination définie, d’un domaine référent) ou des variables personnalisées (champ de formulaire, catégories définies, ID de client). |

## Prise en main d’Aperçu rapide

1. Connectez-vous à Customer Journey Analytics à l’aide des identifiants qui vous ont été fournis.
1. Accédez à [!UICONTROL Workspace], cliquez sur **[!UICONTROL Créer un projet]**, puis sur **[!UICONTROL Aperçu rapide]**. (Vous pouvez également accéder à ce panneau à partir du menu **[!UICONTROL Panneau]** dans le rail de gauche.)

   ![Vue Tous les modèles affichant l’option Aperçu rapide.](assets/qibuilder.png)

   ![Liste Panneaux affichant l’option Aperçu rapide.](assets/qi-panel.png)

1. Lorsque vous commencez, consultez le petit tutoriel qui vous apprend quelques bases sur le [!UICONTROL Panneau d’Aperçu rapide]. Vous pouvez également cliquer sur **[!UICONTROL Ignorer le tutoriel]**.
1. Sélectionnez vos blocs de construction (également appelés composants) : dimensions (orange), mesures (vert), filtres (bleu) ou périodes (violet). Vous devez sélectionner au moins une dimension et une mesure pour qu’un tableau soit automatiquement créé.

   ![Composants, y compris les dimensions, les mesures, les filtres, les segments et les périodes.](assets/qibuilder2.png)

   Vous pouvez sélectionner les blocs de construction de trois manières différentes :
   * Glissez et déposez-les à partir du rail de gauche.
   * Si vous savez ce que vous cherchez : commencez à taper votre texte, et [!UICONTROL Aperçu rapide] complétera les informations pour vous.
   * Cliquez sur la liste déroulante pour effectuer une recherche dans la liste.

1. Lorsque vous avez ajouté au moins une dimension et une mesure, les éléments suivants sont créés pour vous :

   * Un tableau à structure libre avec la dimension (ici, États américains) à la verticale et la mesure (ici, Visites) en haut à l’horizontale. Consultez ce tableau :

   ![Tableau à structure libre présentant la dimension verticalement et la mesure horizontalement.](assets/qibuilder3.png)

   * Une visualisation correspondante, dans ce cas un [graphique à barres](/help/analysis-workspace/visualizations/bar.md). La visualisation qui est générée dépend du type de données que vous avez ajoutées au tableau. Toutes les données temporelles (telles que [!UICONTROL Visites] par jour/mois) sont présentées sous forme de graphique [!UICONTROL en courbes]. Toutes les données non temporelles (telles que [!UICONTROL Visites] par [!UICONTROL Appareil]) sont présentées sous forme de graphique [!UICONTROL à barres]. Vous pouvez modifier le type de visualisation en cliquant sur la flèche déroulante en regard du type de visualisation.

1. (Facultatif) Examinez les dimensions et affichez les éléments de dimension en cliquant sur la flèche vers la droite > en regard de la dimension.

1. Essayez d’affiner un peu plus votre recherche comme décrit ci-dessous sous « Plus de conseils ».

1. Enregistrez votre projet en cliquant sur **[!UICONTROL Projet > Enregistrer]**.

## Plus de conseils

D’autres astuces utiles s’affichent dans le [!UICONTROL Créateur d’Aperçu rapide], dont certaines dépendent de votre dernière action.

* Pour commencer, suivez le tutoriel **[!UICONTROL Plus de conseils]**. Vous pouvez y accéder via l’icône d’aide (?) en regard du titre [!UICONTROL Aperçu rapide]. Ce tutoriel s’affiche 24 heures après la création d’un projet avec au moins une dimension et une mesure.

  ![Affichage de la notification du Panneau Aperçu rapide après avoir cliqué sur l’icône Aide.](assets/qibuilder4.png)

* **Répartition par** : vous pouvez utiliser jusqu’à 3 niveaux de répartitions sur les dimensions pour analyser en détail les données dont vous avez réellement besoin.

  ![Sous-niveaux de répartitions.](assets/qibuilder5.png)

* **Ajouter d’autres mesures** : vous pouvez ajouter jusqu’à 2 mesures supplémentaires au tableau en utilisant l’opérateur AND (ET).

  ![Plusieurs mesures, notamment Visites et Appareils.](assets/qibuilder6.png)

* **Ajouter d’autres filtres** : vous pouvez ajouter jusqu’à 2 filtres supplémentaires au tableau en utilisant les opérateurs AND ou OR. Observez ce qui se passe dans le tableau lorsque vous ajoutez Utilisateurs mobiles OR Visiteurs fidèles. Ils se trouvent les uns à côté des autres, au-dessus des mesures. Si vous ajoutez Utilisateurs mobiles ET Visiteurs fidèles, les résultats des deux filtres s’affichent ensemble et ils sont empilés les uns sur les autres dans le tableau.

  ![Diagramme présentant les utilisateurs et utilisatrices mobiles et les visiteurs et visiteuses fidèles ajoutés.](assets/qibuilder7.png)

## Limites connues

Si vous essayez d’effectuer des modifications directement dans le tableau, le panneau d’[!UICONTROL Aperçu rapide] ne sera plus synchronisé. Vous pouvez rétablir les paramètres précédents d’[!UICONTROL Aperçu rapide] en cliquant sur **[!UICONTROL Resynchroniser le créateur]** dans la partie supérieure droite du panneau.

![Panneau Aperçu rapide avec l’option Resynchroniser le créateur.](assets/qibuilder9.png)

Vous recevrez un avertissement avant d’effectuer un ajout directement dans le tableau :

![Avertissement concernant l’option Resynchroniser le créateur.](assets/qibuilder8.png)

Dans le cas contraire, si la création se fait directement, le tableau se comportera désormais comme un tableau à structure libre traditionnel, sans les fonctionnalités utiles pour les nouveaux utilisateurs et utilisatrices.
