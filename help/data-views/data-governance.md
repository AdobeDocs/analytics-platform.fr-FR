---
title: Prise en charge de CJA pour la gouvernance des données Adobe Experience Platform
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# Prise en charge de CJA pour la gouvernance des données Adobe Experience Platform

L’intégration entre CJA et [Gouvernance des données Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) permet l’étiquetage des données CJA sensibles et l’application des politiques de confidentialité.

Les étiquettes de confidentialité et les stratégies créées sur les jeux de données consommés par l’Experience Platform peuvent être affichées dans le workflow des vues de données CJA. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles.

En outre, lorsque des données sont exportées à partir de CJA (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des étiquettes sont ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des stratégies pour restreindre l’utilisation de . Par conséquent, vos utilisateurs CJA peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux stratégies définies par les gestionnaires de données.

## Étiquetage et stratégies dans Adobe Experience Platform

Lorsque vous créez un jeu de données dans Experience Platform, vous pouvez créer des [libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) pour certains ou tous les éléments du jeu de données. Jusqu’à présent, ces étiquettes n’étaient pas exposées dans CJA. Avec cette version, vous pouvez afficher ces étiquettes dans CJA. CJA s’intéresse particulièrement à l’étiquette C8, qui indique &quot;Les données ne peuvent pas être utilisées pour mesurer les sites web ou les applications de votre organisation&quot;.

L’étiquetage en lui-même ne signifie pas que ces libellés d’utilisation des données sont appliqués. C’est à cela que servent les stratégies. Vous créez vos stratégies via le [API Policy Service](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) dans Experience Platform.

Les stratégies comportent deux composants : le libellé des données et une action marketing que les consommateurs de données peuvent entreprendre dans le cadre de stratégies d’utilisation des données limitées. Dans le contexte de CJA, deux Adobes définis [actions marketing](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) sont importantes :

* Analytics : utilisation des données à des fins d’analyse, telles que la mesure, l’analyse et la création de rapports sur l’utilisation par les consommateurs des sites ou applications de votre entreprise.

* Exporter ces données hors de l’environnement de l’Adobe, par exemple en exportant des données vers un tiers.

Vous liez les libellés et les actions marketing à une stratégie, puis vous activez la stratégie. La stratégie prend le libellé et l’action marketing et indique : appliquez cette restriction. Deux stratégies définies par l’Adobe sont affichées dans CJA :

* Stratégie Analytics
* Stratégie de téléchargement

## Affichage des étiquettes de données dans les vues de données CJA

Les libellés de données créés dans Experience Platform s’affichent à trois emplacements dans l’interface utilisateur des vues de données :

| Emplacement | Description |
| --- | --- |
| Bouton Infos sur un champ de schéma | Cliquez sur ce bouton pour indiquer quelles étiquettes d’utilisation des données s’appliquent actuellement à un champ :<p>![](assets/data-label-left.png) |
| Rail de droite sous [Paramètres des composants](/help/data-views/component-settings/overview.md) | Toutes les étiquettes d’utilisation des données sont répertoriées ici :<p>![](assets/data-label-right.png) |
| Ajouter des étiquettes de données en tant que colonne | Vous pouvez ajouter des libellés de données en tant que colonne aux colonnes Composants inclus dans les vues de données. Cliquez simplement sur l’icône du sélecteur de colonnes et sélectionnez Étiquettes d’utilisation des données :<p>![](assets/data-label-column.png) |

### Filtre sur les étiquettes de gouvernance des données dans CJA

Dans l’éditeur des vues de données, cliquez sur l’icône Filtrer dans le rail de gauche et filtrez les composants des vues de données par étiquettes de gouvernance des données :

![](assets/filter-labels.png)

### Filtre sur les stratégies de gouvernance des données dans CJA

Vous pouvez vérifier si une stratégie est activée qui bloque l’utilisation de certains éléments de vue de données CJA pour les analyses ou l’exportation prévue.

Cliquez à nouveau sur l’icône Filtrer dans le rail de gauche, puis, sous Gouvernance des données, cliquez sur Stratégies :

![](assets/filter-policies.png)

Si la stratégie est activée, les champs de schéma auxquels sont associés certains libellés de données (C8, par exemple) ne peuvent pas être utilisés à des fins d’analyse ou de téléchargement (comme l’envoi d’emails ou le partage de fichiers PDF) dans CJA Workspace.

Notez que

* Vous n’êtes pas autorisé à les ajouter aux vues de données. Ces champs seront grisés dans la liste des champs de schéma du rail gauche.
* Vous ne pouvez pas enregistrer une vue de données contenant des champs bloqués.


