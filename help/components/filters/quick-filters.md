---
description: Utilisation de filtres rapides dans Analysis Workspace pour Customer Journey Analytics
title: Filtres rapides
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: ht
source-wordcount: '1170'
ht-degree: 100%

---

# Filtres rapides

Les filtres rapides vous permettent d’explorer rapidement les données d’un projet Workspace, sans avoir à créer de filtre dans le [créateur de filtres](/help/components/filters/create-filters.md).



>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segments rapides dans Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


Lorsque vous souhaitez utiliser des filtres rapides, notez ce qui suit :

* Les filtres rapides sont créés directement dans un projet Workspace. Par conséquent, un filtre rapide s’applique uniquement au projet Workspace dans lequel vous le créez. Les filtres rapides de votre projet Workspace ne sont pas disponibles dans d’autres projets et ne peuvent pas être partagés avec d’autres utilisateurs et utilisatrices.
* Vous pouvez uniquement spécifier trois conditions dans le cadre d’un filtre rapide.
* Les filtres rapides ne prennent pas en charge les conteneurs imbriqués ni les conditions séquentielles.
* Vous pouvez modifier des filtres rapides dans un projet Workspace partagé. Ainsi, d’autres utilisateurs et utilisatrices peuvent modifier les filtres rapides dans un projet Workspace que vous avez partagé avec ces utilisateurs et utilisatrices.

## Créer

Les filtres rapides s’appliquent aux panneaux. Vous pouvez créer un ou plusieurs filtres rapides pour chaque panneau de votre projet Workspace. Toute personne utilisant Analysis Workspace peut créer des filtres rapides.

Pour créer un filtre rapide, procédez comme suit :

* Sélectionnez ![FilterAdd](/help/assets/icons/FilterAdd.svg) en haut du panneau. <br/>Ensuite, modifiez directement le filtre dans le [créateur de filtres rapides](#quick-filter-builder).
* Faites glisser un composant du panneau des composants vers la zone de dépôt des filtres dans l’en-tête du panneau. Une fois le filtre déposé, pointez sur le filtre et sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier le filtre dans le [créateur de filtres rapides](#quick-filter-builder).

Lorsque vous créez un filtre rapide par glisser-déposer, notez ce qui suit :

* Tous les types de composants ne sont pas pris en charge. Les mesures calculées ne sont pas prises en charge. Seules les dimensions et mesures à partir desquelles vous pouvez créer des filtres sont prises en charge.
* Pour les composants de dimensions et de mesures, le [créateur de filtres rapides](#quick-filter-builder) crée automatiquement des conditions `exists`. Par exemple, si vous effectuez un glisser-déposer de `City`, la condition `City exists` est créée.
* Pour les valeurs de dimension, le [créateur de filtres rapides](#quick-filter-builder) crée automatiquement une condition `equals`. Par exemple, si vous effectuez un glisser-déposer de `amsterdam` à partir de la dimension `City`, la condition `City equals amsterdam` est créée.
* Si vous effectuez un glisser-déposer de `unspecified` ou de `none`, le [créateur de filtres rapides](#quick-filter-builder) crée automatiquement une condition `does not exist`.

Les filtres rapides que vous créez s’affichent en haut du panneau. Les filtres rapides présentent une fine barre de gauche bleu clair. Lorsqu’un filtre rapide est en mode d’édition à l’aide du [créateur de filtres rapides](#quick-filter-builder), l’arrière-plan du filtre rapide est bleu clair.

Les résultats des filtres rapides que vous créez dans un panneau sont appliqués (avec une logique ET) à toutes les visualisations qui font partie du panneau.


## Gérer

Pour gérer un filtre rapide, passez la souris sur un **[!UICONTROL filtre rapide]** spécifique.

* Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour ouvrir le [créateur de filtres rapides](#quick-filter-builder) et modifier le filtre rapide.
* Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour ouvrir une fenêtre contextuelle. La fenêtre contextuelle affiche des informations sur le filtre. Vous pouvez sélectionner **[!UICONTROL Rendre cet élément disponible pour tous vos projets et l’ajouter à votre liste de composants]** Pour ajouter le filtre à la liste de composants ![Filtre](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtres]** dans le panneau des composants. Une boîte de dialogue **[!UICONTROL Enregistrer le filtre rapide]** s’affiche, vous invitant à spécifier un nom pour le filtre. Sélectionnez **[!UICONTROL Enregistrer]** pour continuer. Votre [!UICONTROL filtre rapide] se transforme en **[!UICONTROL filtre]**. Vous ne pouvez plus modifier le filtre à l’aide du [créateur de filtres rapides](#quick-filter-builder). Au lieu de cela, vous devez modifier le filtre en tant que filtre normal, à l’aide du [créateur de filtres](filter-builder.md).

## Créateur de filtres rapides

Consultez ci-dessous un exemple du créateur de filtres rapides. Dans cet exemple, le créateur est ouvert pour un filtre rapide intitulé `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Les deux filtres rapides situés en haut s’appliquent au panneau [!UICONTROL Tableau de bord de la valeur moyenne des commandes] et à toutes les visualisations contenues dans le tableau à structure libre [!UICONTROL Valeur moyenne des commandes par pays].

![Créateur de filtres rapides](assets/quick-filter-builder.png)

Le créateur de filtres rapides se compose des zones et boutons suivants.

### Zone d’en-tête

La zone d’en-tête détermine le nom, le type et la portée du filtre rapide. Il affiche également un visuel pour les résultats du filtre rapide.

| Élément | Description |
|---|---|
| **[!UICONTROL Nom]** | Le nom est automatiquement dérivé de la définition du filtre rapide. |
| **[!UICONTROL Personnes]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alerte](/help/assets/icons/Alert.svg) | Prévisualisez les données issues du filtre rapide. Une barre et un pourcentage permettent de déterminer la quantité de données globales qui fait partie du résultat du filtre rapide. Une ![alerte](/help/assets/icons/Alert.svg) rouge indique que le filtre rapide ne renvoie pas de données. |
| **[!UICONTROL Inclure]**<br/>**[!UICONTROL Exclure]** | Dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg) choisissez d’inclure ou d’exclure les résultats du filtre rapide des données du panneau. |
| **[!UICONTROL Événement]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Personne]** | Dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg), sélectionnez la portée du filtre rapide. |

### Zone de condition

La zone de condition spécifie les conditions (trois au maximum). Pour chaque condition, vous pouvez spécifier les éléments suivants :

| Élément | Description |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Mesure]**<br/>**[!UICONTROL Période]** | Dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg), choisissez si vous souhaitez spécifier une condition pour une dimension, une mesure ou une période. |
| **[!UICONTROL *Composant *]** | Champ de composant de la condition. Vous pouvez [!UICONTROL *Saisir pour ajouter*] un composant, sélectionner un composant dans la liste ou faire glisser et déposer un composant depuis le panneau des composants. Vous pouvez uniquement déposer des composants similaires dans le champ de composant de la condition. Par exemple, vous pouvez uniquement déposer un composant de dimension à partir du panneau des composants sur une condition de dimension. <br/>Vous pouvez également effectuer un glisser-déposer pour remplacer un composant existant.<br/>Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer le composant du champ de composant. |
| **[!UICONTROL *Opérateur *]** | Opérateur du composant. Consultez [Opérateurs](operators.md) pour plus d’informations. Disponible uniquement pour les dimensions et les mesures. |
| **[!UICONTROL *value *]** | Valeur de la condition. Selon l’opérateur sélectionné, la valeur peut être sélectionnée dans une liste ou vous pouvez saisir une valeur. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Sélectionnez cette option pour supprimer une condition du filtre rapide. |

### Boutons

| Bouton | Description |
|---|---|
| **[!UICONTROL ET]**<br/>**[!UICONTROL OU]** | Disponible uniquement lorsque vous définissez plusieurs conditions. Faites votre choix dans la liste déroulante ![ChevronDown](/help/assets/icons/ChevronDown.svg) entre les conditions. La sélection détermine la logique booléenne du filtre rapide. Il n’est pas possible de mélanger la logique avec trois conditions. La logique booléenne est soit **[!UICONTROL ET]** soit **[!UICONTROL OU]**. |
| ![Cercle d’ajout](/help/assets/icons/AddCircle.svg) | Ajoute une autre condition à votre filtre rapide. Ce bouton n’est disponible que lorsque vous avez défini une ou deux conditions pour le filtre rapide. |
| **[!UICONTROL Appliquer]** | Appliquez les modifications au filtre rapide. |
| **[!UICONTROL Ouvrir le créateur]** | Vous recevez une invitation à confirmer l’opération à l’aide d’une boîte de dialogue **[!UICONTROL En êtes-vous sûr(e) ?]**. Si vous sélectionnez **[!UICONTROL OK]**, vous ne pouvez plus modifier votre filtre dans le [créateur de filtres rapides](#quick-filter-builder). Votre filtre rapide est renommé **[!UICONTROL Filtre]** et présente désormais d’une fine barre de gauche bleu foncé.<br/>Le [créateur de filtres](filter-builder.md) normal s’ouvre avec la possibilité de **[!UICONTROL Rendre ce filtre disponible pour tous vos projets et l’ajouter à votre liste de composants]**. <ul><li>Si vous sélectionnez cette option et sélectionnez **[!UICONTROL Appliquer]**, le filtre est ajouté à la liste de composants ![Filtre](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtres]** dans le panneau des composants.</li><li>Si vous ne sélectionnez pas cette option et sélectionnez **[!UICONTROL Appliquer]**, le filtre reste un filtre uniquement pour le projet Workspace.</li></ul> |
| **[!UICONTROL Annuler]** | Sélectionnez cette option pour annuler la création ou la modification d’un filtre rapide. |

## Filtres rapides et filtres

Les filtres rapides portent bien leur nom. Vous pouvez créer et modifier des filtres rapides rapidement intégrés et voir immédiatement les effets dans votre panneau.

Les filtres présentent les avantages suivants par rapport aux filtres rapides.

* Les filtres peuvent être disponibles dans tous vos projets Workspace.
* Les filtres prennent en charge une plus grande complexité à l’aide de conteneurs et de séquences imbriqués et hiérarchiques (à l’aide de filtres de séquence).


