---
title: Comment gérer les blocs de données à l’aide de Report Builder dans Customer Journey Analytics
description: Décrit comment utiliser la fonction de gestion dans Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 57%

---

# Gérer les blocs de données dans Report Builder

Vous pouvez afficher et gérer tous les blocs de données d’un classeur à l’aide du Gestionnaire de blocs de données. Le Gestionnaire de blocs de données fournit des fonctionnalités de recherche, de filtrage et de tri qui vous permettent de localiser rapidement des blocs de données spécifiques. Après avoir sélectionné un ou plusieurs blocs de données, vous pouvez modifier, supprimer ou actualiser les blocs de données sélectionnés.

![Écran Gestionnaire de blocs de données.](./assets/image52.png)

## Afficher les blocs de données

Cliquez sur **Gérer** pour afficher la liste de tous les blocs de données d’un classeur.


![L’option Gérer permet d’afficher la liste de tous les blocs de données.](./assets/image53.png)

Le Gestionnaire de blocs de données répertorie tous les blocs de données présents dans un classeur. 

![Liste de tous les blocs de données présents dans un classeur.](./assets/image52.png)

## Trier la liste Blocs de données

Vous pouvez trier la liste Blocs de données par colonne affichée. Par exemple, vous pouvez trier la liste bloquée de données par vues de données, segments, période et autres variables.

Pour trier la liste Blocs de données, cliquez sur un en-tête de colonne.

![Tri des blocs de données.](./assets/image54.png)

## Rechercher dans la Liste Blocs de données

Utilisez le champ Rechercher pour localiser tout élément dans le tableau des blocs de données. Par exemple, vous pouvez rechercher les mesures contenues dans les blocs de données ou la vue de données. Vous pouvez également rechercher des dates apparaissant dans les colonnes de périodes, de date de modification ou de date de dernière exécution.

![À l’aide du champ Rechercher pour localiser tout élément dans le tableau des blocs de données.](./assets/image55.png)

## Modifier les blocs de données

Vous pouvez modifier la vue de données, la période ou les segments appliqués à un ou plusieurs blocs de données.

Par exemple, vous pouvez remplacer un segment existant par un nouveau segment dans un ou plusieurs blocs de données.

1. Sélectionnez les blocs de données à mettre à jour. Vous pouvez cocher la case de niveau supérieur pour sélectionner tous les blocs de données ou sélectionner des blocs de données individuels.

   ![Icône de modification de crayon](./assets/image56.png)

1. Cliquez sur l’icône d’édition pour afficher la fenêtre Modification rapide.

   ![Fenêtre Modification rapide](./assets/image58.png)

1. Sélectionnez un lien de segment pour mettre à jour les vues de données, les périodes ou les segments.

   ![Champ Ajouter un segment dans la fenêtre Modification rapide](./assets/image59.png)

## Actualiser les blocs de données

Cliquez sur l’icône d’actualisation pour actualiser les blocs de données de la liste.

<img src="./assets/refresh-icon.png" width="15%" alt="Icône Actualiser"/>

Pour vérifier si un bloc de données est actualisé, consultez l’icône de statut de l’actualisation.

Un bloc de données actualisé avec succès affiche une coche dans un cercle vert : <img src="./assets/refresh-success.png" width="5%" alt="Cercle vert avec icône de coche"/>.

Un bloc de données qui n’a pas été actualisé affiche une icône d’avertissement : <img src="./assets/refresh-failure.png" width="5%" alt="Triangle rouge avec icône de point d’exclamation"/>.Cela permet d’identifier facilement si des blocs de données comportent des erreurs.


![Gestionnaire de blocs de données affichant le statut d’actualisation pour chaque bloc de données répertorié.](./assets/image512.png)

## Supprimer un bloc de données

Cliquez sur l’icône représentant une corbeille pour supprimer un bloc de données sélectionné.

## Regrouper les blocs de données

Vous pouvez regrouper des blocs de données à l’aide de la variable **Grouper par** ou cliquer sur le titre d’une colonne. Pour trier les blocs de données par colonne, cliquez sur le titre de la colonne. Pour regrouper des blocs de données par groupes, sélectionnez un nom de groupe dans le menu déroulant **Grouper par**. Par exemple, la capture d’écran ci-dessous présente les blocs de données regroupés par feuille. Elle affiche les blocs de données regroupés par Feuille1 et Feuille2. Cela s’avère utile, par exemple, dans le cas du remplacement d’un segment. Si plusieurs segments sont appliqués à chaque bloc de données, il est utile de créer un groupe contenant tous les blocs de données à remplacer. Vous pouvez ensuite facilement les sélectionner et les modifier tous en même temps.

![Gestionnaire de blocs de données affichant la liste Regrouper par feuille.](./assets/group-data-blocks.png)

## Modifier la vue Gestionnaire de blocs de données

Vous pouvez modifier les colonnes visibles dans la fenêtre Gestionnaire de blocs de données.


Cliquez sur l’icône de la liste des colonnes <img src="./assets/image515.png" width="3%" alt="Icône Liste à colonnes"/> pour sélectionner les colonnes répertoriées dans le Gestionnaire de blocs de données. Sélectionnez le nom de la colonne à afficher. Désélectionnez le nom de la colonne pour la supprimer de la vue.

![Gestionnaire de blocs de données affichant la liste des colonnes](./assets/image516.png)
