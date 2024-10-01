---
description: Utilisation de filtres rapides dans Analysis Workspace pour Customer Journey Analytics
title: Filtres rapides
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 2%

---

# Filtres rapides

Les filtres rapides vous permettent d’explorer rapidement les données d’un projet Workspace, sans avoir à créer un filtre dans le [Créateur de filtres](/help/components/filters/create-filters.md).


+++ La vidéo suivante explique comment utiliser les filtres rapides.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

Si vous souhaitez utiliser des filtres rapides, veuillez noter que :

* Les filtres rapides sont créés directement dans un projet Workspace. Par conséquent, un filtre rapide s’applique uniquement au projet Workspace dans lequel vous créez le filtre rapide. Les filtres rapides de votre projet Workspace ne sont pas disponibles dans d’autres projets et ne peuvent pas être partagés avec d’autres utilisateurs.
* Vous ne pouvez spécifier que trois conditions dans le cadre d’un filtre rapide.
* Les filtres rapides ne prennent pas en charge les conteneurs imbriqués ni les conditions séquentielles.
* Vous pouvez modifier des filtres rapides dans un projet Workspace partagé. Ainsi, d’autres utilisateurs peuvent modifier les filtres rapides dans un projet Workspace que vous avez partagé avec ces utilisateurs.

## Créer

Les filtres rapides s’appliquent aux panneaux. Vous pouvez créer un ou plusieurs filtres rapides pour chaque panneau de votre projet Workspace. Tout utilisateur d’Analysis Workspace peut créer des filtres rapides.

Pour créer un filtre rapide :

* Sélectionnez ![FilterAdd](/help/assets/icons/FilterAdd.svg) en haut du panneau. <br/>Ensuite, modifiez directement le filtre dans le [Créateur de filtres rapides](#quick-filter-builder).
* Faites glisser un composant du panneau Composant vers la zone de dépôt de filtre dans l’en-tête du panneau. Une fois le filtre déposé, passez la souris sur le filtre et sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier le filtre dans le [Créateur de filtres rapides](#quick-filter-builder).

Lorsque vous créez un filtre rapide par glisser-déposer, notez que :

* Tous les types de composants ne sont pas pris en charge. Les mesures calculées ne sont pas prises en charge et seules les dimensions et mesures à partir desquelles vous pouvez créer des filtres sont prises en charge.
* Pour les composants de dimensions et de mesures, le [Créateur de filtres rapides](#quick-filter-builder) crée automatiquement une condition `exists`. Par exemple, si vous effectuez un glisser-déposer de `City`, la condition `City exists` est créée.
* Pour les valeurs de dimension, le [Créateur de filtres rapides](#quick-filter-builder) crée automatiquement une condition `equals`. Par exemple, si vous faites glisser `amsterdam` depuis la dimension `City`, la condition `City equals amsterdam` est créée.
* Si vous effectuez un glisser-déposer de `unspecified` ou `none`, le [générateur de filtre rapide](#quick-filter-builder) crée automatiquement une condition `does not exist`.

Les filtres rapides que vous créez apparaissent en haut du panneau. Les filtres rapides ont une fine barre de gauche bleu clair. Lorsqu’un filtre rapide est en mode d’édition à l’aide du [Créateur de filtres rapides](#quick-filter-builder), l’arrière-plan du filtre rapide est bleu clair.

Les résultats des filtres rapides que vous créez dans un panneau sont appliqués (à l’aide de la logique ET) à toutes les visualisations qui font partie du panneau.


## Gérer

Pour gérer un filtre rapide, passez la souris sur le **[!UICONTROL filtre rapide]** spécifique.

* Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour ouvrir le [Créateur de filtres rapides](#quick-filter-builder) et modifier le filtre rapide.
* Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour ouvrir une fenêtre contextuelle. La fenêtre contextuelle affiche des informations sur le filtre. Vous pouvez sélectionner **[!UICONTROL Rendre disponible pour tous les projets et l’ajouter à votre liste de composants]** Pour ajouter le filtre à la liste de composants ![Filtre](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtres]** dans le panneau du composant. Une boîte de dialogue **[!UICONTROL Enregistrer le filtre rapide]** s’affiche, vous invitant à spécifier un nom pour le filtre. Sélectionnez **[!UICONTROL Enregistrer]** pour continuer. Votre [!UICONTROL filtre rapide] se transforme en **[!UICONTROL filtre]**. Vous ne pouvez plus modifier le filtre à l’aide du [Créateur de filtres rapides](#quick-filter-builder). Au lieu de cela, vous devez modifier le filtre comme un filtre normal, à l’aide du [Créateur de filtres](filter-builder.md).

## Créateur de filtres rapides

Voir ci-dessous un exemple du créateur de filtres rapides. Dans cet exemple, le créateur est ouvert pour un filtre rapide intitulé `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Les deux filtres rapides en haut s’appliquent au panneau [!UICONTROL Tableau de bord Valeur de commande moyenne] et à toutes les visualisations dans, telles que le tableau à structure libre [!UICONTROL  Valeur de commande moyenne par pays].

![Créateur de filtres rapides](assets/quick-filter-builder.png)

Le créateur de filtres rapides se compose des zones et boutons suivants.

### Zone d’en-tête

La zone d’en-tête détermine le nom, le type et la portée du filtre rapide. Il affiche également un visuel pour les résultats du filtre rapide.

| Élément | Description |
|---|---|
| **[!UICONTROL Nom]** | Le nom est automatiquement dérivé de la définition de filtre rapide. |
| **[!UICONTROL Personnes]** <br/>![CercleCoche](/help/assets/icons/CheckmarkCircle.svg) ![Alerte](/help/assets/icons/Alert.svg) | Prévisualisez le visuel des données issues du filtre rapide. Une barre et un pourcentage fournissent des informations sur la quantité totale de données qui fait partie du résultat du filtre rapide. Une ![alerte](/help/assets/icons/Alert.svg) rouge indique que le filtre rapide ne renvoie pas de données. |
| **[!UICONTROL Inclure]**<br/>**[!UICONTROL Exclure]** | Choisissez dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg) si vous souhaitez inclure ou exclure les résultats du filtre rapide des données du panneau. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Sélectionnez dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg) la portée du filtre rapide. |

### Zone de condition

La zone de condition spécifie les conditions (trois au maximum). Pour chaque condition, vous pouvez spécifier les éléments suivants :

| Élément | Description |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Mesure]**<br/>**[!UICONTROL Plage de dates]** | Choisissez dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg) si vous souhaitez spécifier une condition pour une dimension, une mesure ou une période. |
| **[!UICONTROL *component *]** | Champ de composant de la condition. Vous pouvez [!UICONTROL *Type pour ajouter*] un composant, sélectionner un composant dans la liste ou faire glisser un composant depuis le panneau du composant. Vous pouvez uniquement déposer des composants similaires sur le champ de composant de la condition. Par exemple, vous pouvez uniquement déposer un composant de dimension à partir du panneau du composant sur une condition de dimension. <br/>Vous pouvez également faire glisser et déposer pour remplacer un composant existant.<br/>Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer le composant du champ de composant. |
| **[!UICONTROL *operator *]** | L’opérateur pour le composant. Voir [Opérateurs](operators.md) pour plus d’informations. Disponible uniquement pour les dimensions et les mesures. |
| **[!UICONTROL *value *]** | La valeur de la condition. Selon l’opérateur sélectionné, la valeur peut être sélectionnée dans une liste ou vous pouvez saisir une valeur. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Sélectionnez cette option pour supprimer une condition du filtre rapide. |

### Boutons

| Bouton | Description |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Disponible uniquement lorsque vous définissez plusieurs conditions. Sélectionnez dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg) entre les conditions. La sélection détermine la logique booléenne du filtre rapide. Vous ne pouvez pas mélanger la logique lorsque vous avez trois conditions. La logique booléenne est **[!UICONTROL AND]** ou **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Ajoute une autre condition à votre filtre rapide. Ce bouton n’est disponible que lorsque vous avez défini une ou deux conditions pour le filtre rapide. |
| **[!UICONTROL Appliquer]** | Appliquez les modifications au filtre rapide. |
| **[!UICONTROL Ouvrir le créateur]** | Vous êtes invité à confirmer avec un **[!UICONTROL Êtes-vous sûr ?]**. Si vous sélectionnez **[!UICONTROL OK]**, vous ne pouvez plus modifier votre filtre dans le [Créateur de filtres rapides](#quick-filter-builder). Votre filtre rapide est renommé **[!UICONTROL Filtre]** et comporte désormais une fine barre de gauche bleue plus foncée.<br/>Le [Créateur de filtres](filter-builder.md) s’ouvre avec l’option **[!UICONTROL Rendre ce filtre disponible pour tous vos projets et l’ajouter à votre liste de composants]**. <ul><li>Si vous sélectionnez cette option et sélectionnez **[!UICONTROL Appliquer]**, le filtre est ajouté à la liste des composants ![Filtre](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtres]** dans le panneau du composant.</li><li>Si vous ne sélectionnez pas cette option et sélectionnez **[!UICONTROL Appliquer]**, le filtre reste un filtre réservé au projet Workspace.</li></ul> |
| **[!UICONTROL Annuler]** | Sélectionnez cette option pour annuler la création ou l’édition d’un filtre rapide. |

## Filtres rapides et filtres

Les filtres rapides sont exactement ce qu’ils sont appelés. Vous pouvez créer et modifier des filtres rapides en ligne rapidement et voir les effets immédiatement dans votre panneau.

Les filtres présentent les avantages suivants par rapport aux filtres rapides.

* Les filtres peuvent être rendus disponibles dans tous vos projets Workspace.
* Les filtres prennent en charge une plus grande complexité à l’aide de conteneurs imbriqués et hiérarchiques et de séquences (à l’aide de filtres de séquence).


