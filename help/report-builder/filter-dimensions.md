---
title: Filtrage Des Dimensions Dans Report Builder
description: Découvrez comment filtrer les dimensions dans Report Builder.
role: User
feature: Report Builder
type: Documentation
exl-id: 5730d5f3-de76-429f-81f5-ebe6b62a9480
solution: Customer Journey Analytics
source-git-commit: a18b628f02889911c7663c32f31ef3c3bec3cf2e
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 34%

---


# Filtrer des dimensions

Par défaut, chaque élément de dimension du tableau renvoie les 10 premiers éléments de cette dimension.

Pour modifier les éléments de dimension renvoyés pour chaque dimension :

1. Sélectionnez une cellule dans le bloc de données.

1. Sélectionnez ![&#x200B; Modifier &#x200B;](/help/assets/icons/Edit.svg) **[!UICONTROL Modifier le bloc de données]** dans le panneau **[!UICONTROL Commandes]**.

1. Sélectionnez **[!UICONTROL Suivant]** pour afficher l’onglet **[!UICONTROL Dimensions]**.

1. Sélectionnez ![PlusPetit](/help/assets/icons/MoreSmall.svg) en regard d’un nom de composant dans le tableau.

   ![Options de l’icône représentant des points de suspension.](./assets/image27.png){zoomable="yes"}

1. Sélectionnez **[!UICONTROL Filtrer la dimension]** dans le menu pop-up pour afficher le volet **[!UICONTROL Filtrer la dimension]**.

1. Sélectionnez **Les plus populaires** ou **Spécifique** comme **[!UICONTROL Type]**.

   ![Option spécifique sélectionnée dans le volet Filtrer la dimension.](./assets/image28.png){zoomable="yes"}

1. Sélectionnez les options appropriées en fonction du [type de filtre](#filter-type) choisi.

1. Sélectionnez **[!UICONTROL Appliquer]** pour ajouter le filtre.

1. Report Builder affiche une notification pour confirmer le filtre ajouté.

Pour afficher les filtres appliqués, passez la souris sur une dimension. Les dimensions avec des filtres appliqués affichent une icône de filtre ![Filtre](/help/assets/icons/Filter.svg) en regard du nom de la dimension.

## Modification du filtre et de l’ordre de tri

Un ![ArrowUp](/help/assets/icons/ArrowUp.svg) ou ![ArrowDown](/help/assets/icons/ArrowDown.svg) s’affiche en regard de la mesure utilisée pour filtrer et trier le bloc de données. La direction de la flèche indique si la mesure est triée par ordre croissant ou décroissant.

Pour modifier l’ordre de tri :

- Sélectionnez ![ArrowUp](/help/assets/icons/ArrowUp.svg) ou ![ArrowDown](/help/assets/icons/ArrowDown.svg) en regard de la mesure pour activer/désactiver l’ordre de tri.

Pour modifier la mesure utilisée pour filtrer et trier le bloc de données :

1. Passez la souris sur le composant de mesure souhaité dans le générateur de tableau pour afficher d’autres options.

2. Sélectionnez ![ArrowDown](/help/assets/icons/ArrowDown.svg) pour la mesure souhaitée.

   ![Le créateur de tableaux et les mesures.](./assets/image30.png){zoomable="yes"}



## Type de filtre

Il existe deux façons de filtrer les éléments de dimension : [Les plus populaires](#most-popular) et [Spécifique](#specific-filtering)

### **[!UICONTROL Les plus populaires]**

L’option **[!UICONTROL Les plus populaires]** vous permet de filtrer les éléments de dimension de manière dynamique en fonction de valeurs de mesure. La plus populaire renvoie les éléments de dimension avec le meilleur classement en fonction des valeurs de mesure. Par défaut, les 10 premiers éléments de dimension sont répertoriés. Ils sont triés en fonction de la première mesure ajoutée au bloc de données.

![L&#39;option la plus populaire.](./assets/image29.png){zoomable="yes"}


#### Options Page et Lignes

Utilisez les champs **[!UICONTROL Page]** et **[!UICONTROL Lignes]** pour diviser les données en groupes ou pages séquentiel(le)s. Cette fonctionnalité vous permet d’extraire dans votre rapport des valeurs de ligne autres que les valeurs les mieux classées. Et est particulièrement utile pour extraire des données au-delà de la limite de 50 000 lignes.

La valeur par défaut pour Page est `1` et pour Lignes est `10`. Ces valeurs par défaut impliquent que chaque page comporte 10 lignes de données. La page 1 renvoie les 10 premiers éléments, la page 2 renvoie les 10 éléments suivants, etc.

Le tableau ci-dessous répertorie des exemples de valeurs de page et de lignes, ainsi que la sortie qui en résulte.

| Page | Ligne | Sortie |
|------|--------|----------------------|
| 1 | 10 | 10 premiers éléments |
| 2 | 10 | Éléments 11 à 20 |
| 1 | 100 | 100 premiers éléments |
| 2 | 100 | Éléments 101 à 200 |
| 2 | 50 000 | Éléments 50 001 à 100 000 |

Le tableau ci-dessous répertorie les valeurs minimales et maximales pour la page et les lignes.

|       | Valeurs minimales | Valeurs maximales |
|-------|---------------:|---------------:|
| Page de démarrage | 1 | 50 million |
| Nombre de lignes | 1 | 50 000 |


#### Inclure « Aucune valeur »

Dans Customer Journey Analytics, certaines dimensions collectent une entrée *Aucune valeur*. Le paramètre **[!UICONTROL Inclure « Aucune valeur »]** vous permet d’exclure ces valeurs des rapports. Par exemple, vous pouvez créer une classification telle que la classification Nom du produit en fonction de la clé SKU du produit. Si un SKU de produit spécifique n’a pas été configuré avec sa classification de nom de produit spécifique, sa valeur de nom de produit est définie sur *Aucune valeur*.

**[!UICONTROL Inclure « Aucune valeur »]** est sélectionné par défaut. Désélectionnez cette option pour exclure les entrées sans valeur.

#### Filtrage par critères

Vous pouvez filtrer les éléments de dimension en fonction du respect de tous les critères ou du respect d’au moins l’un d’entre eux.

Pour définir des critères de filtrage :

1. Sélectionnez un opérateur ou une opératrice dans le menu déroulant des opérateurs. Par défaut **[!UICONTROL Contient l’expression]** est sélectionné

   ![Liste des opérateurs.](./assets/image31.png){zoomable="yes"}

1. Saisissez un terme de recherche.

1. Sélectionnez ![Ajouter](/help/assets/icons/Add.svg) **[!UICONTROL Ajouter une ligne]** pour confirmer la sélection et ajouter un autre élément de critère.

1. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un élément de critère.

Vous pouvez inclure jusqu’à 10 éléments de critère.

### **[!UICONTROL spécifique]**

L’option **[!UICONTROL Spécifique]** vous permet de créer une liste fixe d’éléments de dimension pour chaque dimension. Utilisez le type de filtrage **[!UICONTROL Spécifique]** pour spécifier les éléments de dimension exacts à inclure dans votre filtre. Vous pouvez sélectionner des éléments dans une liste ou dans une plage de cellules.

![Options spécifiques et éléments sélectionnés.](./assets/image32.png){zoomable="yes"}

#### À partir de la liste

1. Sélectionnez l’option **[!UICONTROL À partir de la liste]** pour rechercher et sélectionner des éléments de dimension.

   Lorsque vous sélectionnez l’option **À partir de la liste**, la liste **[!UICONTROL Éléments de Dimension]** est renseignée avec des éléments de dimension triés par nombre d’événements.

   ![L’option À partir de la liste et les éléments disponibles.](./assets/image33.png){zoomable="yes"}

1. Saisissez un terme de recherche dans le champ ![Rechercher](/help/assets/icons/Search.svg) **[!UICONTROL _Ajouter un élément_]** pour effectuer une recherche dans la liste.

1. Pour rechercher un élément non inclus dans les 90 derniers jours de données, sélectionnez **[!UICONTROL Afficher les éléments des 6 derniers mois]** afin d’étendre la recherche. Une fois les données des 6 derniers mois chargées, Report Builder met à jour le lien vers **[!UICONTROL Afficher les éléments des 18 derniers mois]**.

1. Pour supprimer un élément de la liste **[!UICONTROL Éléments sélectionnés]**, sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg).

1. Pour déplacer un élément dans la liste **[!UICONTROL Éléments sélectionnés]**, faites glisser et déposez l’élément ou sélectionnez ![PlusPetit](/help/assets/icons/MoreSmall.svg) pour afficher le menu contextuel et sélectionnez l’une des options de déplacement.

1. Sélectionnez **[!UICONTROL Appliquer]**.

Report Builder met à jour la liste pour afficher le filtrage spécifique appliqué.

#### À partir de la plage de cellules

Sélectionnez l’option **À partir de la plage de cellules** pour choisir une plage de cellules contenant la liste des éléments de dimension à faire correspondre.

![L’option À partir de la plage de cellules et le champ pour sélectionner une plage de cellules.](./assets/image37.png){zoomable="yes"}

Lorsque vous sélectionnez une plage de cellules, tenez compte des restrictions suivantes :

- La plage doit comporter au moins une cellule.
- La plage ne peut pas contenir plus de 50 000 cellules.
- La plage doit se trouver dans une seule ligne ou colonne ininterrompue.

Votre sélection peut contenir des cellules vides ou des cellules avec des valeurs qui ne correspondent pas à un élément de dimension spécifique.


### Filtrer rapidement une dimension

Pour filtrer une dimension pour laquelle aucun filtre n’est actuellement appliqué :

1. Sélectionnez ![ChevronRight](/help/assets/icons/ChevronRight.svg) pour une dimension. Par exemple, **[!UICONTROL canal Interaction]**.

1. Sélectionnez deux fois un élément de dimension à ajouter au filtre. Vous pouvez également sélectionner un ou plusieurs éléments de dimension et faire glisser et déposer la sélection dans la section ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**.

   ![L’onglet Dimensions et la liste des dimensions.](./assets/quickly-filter.png){zoomable="yes"}

