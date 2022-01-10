---
title: 'Paramètres des composants : valeurs dʼinclusion/exclusion'
description: Incluez ou excluez de façon conditionnelle un élément de dimension en fonction de sa valeur.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: ht
source-wordcount: '300'
ht-degree: 100%

---

# Paramètres des composants : valeurs dʼinclusion/exclusion

Les valeurs dʼinclusion/exclusion vous permettent de créer des règles qui dépendent de la valeur dʼun élément de dimension. Les valeurs qui ne correspondent pas aux critères définis sont traités dans Analysis Workspace comme si elles nʼavaient jamais existé, bien que les données existent toujours dans le jeu de données sous-jacent.

![Inclure/exclure](../assets/include-exclude.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Définir les valeurs d’inclusion/exclusion] | Case à cocher permettant dʼactiver les conditions dans lesquelles les données sont incluses dans une vue de données. |
| [!UICONTROL Respect de la casse] | Visible sur les types de données du schéma de chaîne. La valeur par défaut est « activé ». Ce paramètre sʼapplique uniquement à la logique [!UICONTROL Valeurs dʼinclusion/exclusion], et non à la valeur obtenue. Il vous permet dʼindiquer si la règle est sensible à la casse. |
| [!UICONTROL Correspond à] | Permet de définir les valeurs à prendre en compte pour le compte rendu des performances avant lʼaffectation et les filtres (par exemple, utilisez uniquement les valeurs contenant le mot « erreur »). Vous pouvez définir **[!UICONTROL si tous les critères sont remplis]**, ou **[!UICONTROL si lʼun dʼeux est rempli]**. |
| [!UICONTROL Critères] | Permet de définir la logique correspondante qui doit être appliquée à une règle de filtrage spécifique.<ul><li>**Chaîne** : contient lʼexpression, contient nʼimporte quel terme, contient tous les termes, ne contient pas nʼimporte quel terme, ne contient pas lʼexpression, est égal à, nʼest pas égal à, commence par, se termine par</li><li>**Doublon/Entier** : est égal à, nʼest pas égal à, est supérieur à, est inférieur à, est supérieur ou égal à, est inférieur ou égal à</li><li>**Date** : est égal à, nʼest pas égal à, est plus récent que, est antérieur à, se produit au niveau de</li></ul> |
| [!UICONTROL Opérande correspondant] | Permet de définir lʼopérande correspondant auquel lʼopérateur correspondant doit être appliqué.<ul><li>**Chaîne** : champ de texte</li><li>**Doublon/Entier** : champ de texte avec des flèches haut/bas pour les valeurs numériques</li><li>**Date** : sélecteur de granularité journalière (calendrier)</li><li>**Date/heure** : sélecteur de granularité de la date et de lʼheure</li></ul> |
| [!UICONTROL Ajouter une règle] | Permet de définir un opérateur et un opérande correspondant supplémentaire. |
