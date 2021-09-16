---
title: Inclure les paramètres du composant Exclure les valeurs
description: Inclure ou exclure de manière conditionnelle un élément de dimension en fonction de sa valeur.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 56%

---


# Inclure les paramètres du composant Exclure les valeurs

L’option Inclure les valeurs d’exclusion permet de créer des règles qui dépendent de la valeur d’un élément de dimension. Les valeurs qui ne répondent pas aux critères définis sont traitées dans Analysis Workspace comme si elles n’avaient jamais existé, bien que les données existent toujours dans le jeu de données sous-jacent.

![Exclusion d’inclusion](../assets/include-exclude.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Définir les valeurs d&#39;inclusion/exclusion] | Case à cocher permettant d’activer les conditions dans lesquelles les données sont incluses dans une vue de données. |
| [!UICONTROL Respect de la casse] | Visible sur les types de données de schéma de chaîne. La valeur par défaut est activée. Ce paramètre s’applique uniquement à la logique [!UICONTROL Inclure/Exclure les valeurs], et non à la valeur obtenue. Il vous permet de spécifier si la règle est sensible à la casse. |
| [!UICONTROL Correspond à] | Permet de définir les valeurs à prendre en compte pour le compte rendu des performances avant lʼaffectation et les filtres (par exemple, utilisez uniquement les valeurs contenant le mot « erreur »). Vous pouvez spécifier **[!UICONTROL Si tous les critères sont satisfaits]** ou **[!UICONTROL Si l’un d’eux est satisfait]**. |
| [!UICONTROL Critères] | Permet de définir la logique correspondante qui doit être appliquée à une règle de filtrage spécifique.<ul><li>**Chaîne** : contient lʼexpression, contient nʼimporte quel terme, contient tous les termes, ne contient pas nʼimporte quel terme, ne contient pas lʼexpression, est égal à, nʼest pas égal à, commence par, se termine par</li><li>**Doublon/Entier** : est égal à, nʼest pas égal à, est supérieur à, est inférieur à, est supérieur ou égal à, est inférieur ou égal à</li><li>**Date** : est égal à, nʼest pas égal à, est plus récent que, est antérieur à, se produit au niveau de</li></ul> |
| [!UICONTROL Opérande correspondant] | Permet de définir lʼopérande correspondant auquel lʼopérateur correspondant doit être appliqué.<ul><li>**Chaîne** : champ de texte</li><li>**Doublon/Entier** : champ de texte avec des flèches haut/bas pour les valeurs numériques</li><li>**Date** : sélecteur de granularité journalière (calendrier)</li><li>**Date/heure** : sélecteur de granularité de la date et de lʼheure</li></ul> |
| [!UICONTROL Ajouter une règle] | Permet de définir un opérateur et un opérande correspondant supplémentaire. |
