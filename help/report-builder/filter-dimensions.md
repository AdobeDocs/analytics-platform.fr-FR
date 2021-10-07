---
title: Utilisation des filtres dans Report Builder en Customer Journey Analytics
description: Décrit comment utiliser des filtres dans Report Builder pour CJA.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: dc6317bc754218c03d78145be1c8681ad202bcb8
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 2%

---


# Filtrage des dimensions

Par défaut, chaque élément de dimension du tableau renvoie les 10 premiers éléments de cette dimension.

Pour modifier les éléments de dimension renvoyés pour chaque dimension

1. Sélectionnez un bloc de données et cliquez sur Modifier le bloc de données dans le panneau COMMANDES .

1. Cliquez sur Suivant pour afficher l’onglet Dimensions .

1. Cliquez sur le **...** icône en regard du nom d’un composant dans le tableau.

   ![](./assets/image27.png)

1. Sélectionnez **Filtrer la dimension** dans le menu contextuel pour afficher le volet **Filtrer la dimension**.

1. Sélectionnez **La** ou **Spécifique**.

   ![](./assets/image28.png)

1. Sélectionnez les options appropriées en fonction du type de filtre choisi.

1. Cliquez sur **Appliquer** pour ajouter le filtre.

   Report Builder affiche une notification pour confirmer le filtrage ajouté.

Pour afficher les filtres appliqués, passez la souris sur une dimension. Les Dimensions avec filtres appliqués affichent une icône de filtre à droite du nom de la Dimension.

## Type de filtre

Il existe deux manières de filtrer les éléments de dimension : Les plus populaires et les plus spécifiques.

## Les plus populaires

L’option La plus populaire vous permet de filtrer dynamiquement les éléments de dimension en fonction des valeurs de mesure. Le filtrage le plus populaire renvoie les éléments de dimension avec le meilleur classement en fonction des valeurs de mesure. Par défaut, les 10 premiers éléments de dimension sont répertoriés, triés par la première mesure ajoutée au bloc de données.

![fichiers image](./assets/image29.png)


### Options Page et Lignes

Utilisez les champs **Page** et **Lignes** pour diviser les données en groupes ou en pages séquentiels. Vous pouvez ainsi extraire dans votre rapport des valeurs de ligne avec classement autres que les valeurs les plus élevées. Cette fonctionnalité est particulièrement utile pour extraire des données au-delà de la limite de 50 000 lignes.

#### Paramètres par défaut Page et Lignes

- Page = 1
- Lignes = 10

Les paramètres par défaut Page et Lignes identifient que chaque page comporte 10 lignes de données. La page 1 renvoie les 10 premiers éléments, la page 2 renvoie les 10 éléments suivants, etc.

Le tableau ci-dessous répertorie des exemples de valeurs de page et de ligne, ainsi que la sortie qui en résulte.

| Page | Ligne | Sortie |
|------|--------|----------------------|
| 1 | 10 | 10 premiers éléments |
| 2 | 10 | Points 11 à 20 |
| 1 | 100 | 100 premiers éléments |
| 2 | 100 | Points 101 à 200 |
| 2 | 50 000 | Éléments 50 001 à 100 000 |

#### Valeurs minimales et maximales

- Page de début : Min = 1, Max : 50 millions
- Nombre de lignes : Min = 1, Max : 50 000

### Inclure &quot;Aucune valeur&quot;

Dans Customer Journey Analytics, certaines dimensions collectent une entrée &quot;aucune valeur&quot;. Ce filtre permet d’exclure ces valeurs des rapports. Par exemple, vous pouvez créer une classification telle que la classification Nom du produit en fonction de la clé SKU du produit. Si un SKU de produit spécifique n’a pas été configuré avec sa classification de nom de produit spécifique, sa valeur de nom de produit est définie sur &quot;aucune valeur&quot;.

Include &quot;**Aucune valeur**&quot; est sélectionnée par défaut. Désélectionnez cette option pour exclure les entrées sans valeur.

### Filtrage par critère

Vous pouvez filtrer les éléments de dimension selon que tous les critères sont satisfaits ou si l’un d’eux est satisfait.

Pour définir des critères de filtrage

1. Sélectionnez un opérateur dans la liste déroulante.

   ![](./assets/image31.png)

1. Saisissez une valeur dans le champ de recherche.

1. Cliquez sur Ajouter une ligne pour confirmer la sélection et ajouter un autre élément de critère.

1. Cliquez sur l’icône Supprimer pour supprimer un élément de critère.

   Vous pouvez inclure jusqu’à 10 éléments de critère.

### Modifier le filtre et l’ordre de tri

Une flèche s’affiche en regard de la mesure utilisée pour filtrer et trier le bloc de données. La direction de la flèche indique si la mesure est triée du plus grand au moins ou du moins au plus grand.

Pour modifier la direction du tri, cliquez sur la flèche en regard de la mesure. 

Pour modifier la mesure utilisée pour filtrer et trier le bloc de données,

1. Passez la souris sur le composant de mesure souhaité dans le Générateur de tableau pour afficher d’autres options.

2. Cliquez sur la flèche pour la mesure souhaitée. 

   ![](./assets/image30.png)


## Filtrage spécifique

L’option Spécifique vous permet de créer une liste fixe d’éléments de dimension pour chaque dimension. Utilisez le type de filtrage **Spécifique** pour spécifier les éléments de dimension exacts à inclure dans votre filtre. Vous pouvez sélectionner des éléments dans une liste ou dans une plage de cellules.

![](./assets/image32.png)

### À partir de la liste

1. Sélectionnez l’option **Dans la liste** pour rechercher et sélectionner des éléments de dimension.

   Lorsque vous sélectionnez l’option **A partir de la liste**, la liste est remplie avec les éléments de dimension avec le plus d’événements en premier.

   ![](./assets/image33.png)

   La liste **Éléments disponibles** est classée des éléments de dimension comportant le plus d’événements à ceux comportant le moins d’événements.

1. Saisissez un terme de recherche dans le champ **Ajouter un élément** pour effectuer une recherche dans la liste.

1. Pour rechercher un élément non inclus dans les 90 derniers jours de données, cliquez sur **Afficher les éléments pour les 6 derniers mois** pour étendre la recherche.

   ![](./assets/image34.png)

   Une fois les données des six derniers mois chargées, Report Builder met à jour le lien vers **Afficher les éléments pour les 18 derniers mois**.

1. Sélectionnez un élément de dimension.

   Les éléments de dimension sélectionnés sont automatiquement ajoutés à la liste **Éléments sélectionnés**.

   ![](./assets/image35.png)

   Pour supprimer un élément de la liste, cliquez sur l’icône de suppression pour le supprimer de la liste.

   Pour déplacer un élément dans la liste, faites glisser et déposez l’élément ou cliquez sur ... pour afficher le menu de déplacement.

   ![](./assets/image36.png)

1. Cliquez sur **Appliquer**

   Report Builder met à jour la liste pour afficher le filtrage spécifique appliqué.

### À partir de la plage de cellules

Sélectionnez l’option **À partir de la plage de cellules** pour choisir une plage de cellules contenant la liste des éléments de dimensions à faire correspondre.

![](./assets/image37.png)

Lorsque vous sélectionnez une plage de cellules, tenez compte des restrictions suivantes :

- La plage doit comporter au moins une cellule.
- La plage ne peut pas contenir plus de 50 000 cellules.
- La plage doit se trouver dans une seule ligne, ou colonne ininterrompue.

Votre sélection peut contenir des cellules vides ou des cellules avec des valeurs qui ne correspondent pas à un élément de dimension spécifique.

### Onglet Dimensions du Générateur de tableau

Dans l’onglet **Dimensions**, cliquez sur l’icône chevron en regard d’un nom de dimension pour afficher la liste des éléments de dimension.

![](./assets/dimensions_chevron.png)

Vous pouvez faire glisser et déposer des éléments sur le **tableau** ou double-cliquer sur le nom d’un élément pour l’ajouter au générateur de **tableau**.
