---
title: Prise en charge de CJA pour la gouvernance des données Adobe Experience Platform
description: Découvrez comment les étiquettes de données et les stratégies définies dans AEP affectent la création de rapports dans CJA.
mini-toc-levels: 3
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 1%

---


# Prise en charge de CJA pour la gouvernance des données Adobe Experience Platform

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

L’intégration entre CJA et [Gouvernance des données Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) permet l’étiquetage des données CJA sensibles et l’application des politiques de confidentialité.

Les étiquettes de confidentialité et les stratégies créées sur les jeux de données consommés par l’Experience Platform peuvent être affichées dans le workflow des vues de données CJA. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles.

En outre, lorsque des données sont exportées à partir de CJA (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des étiquettes sont ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des stratégies pour restreindre l’utilisation de . Par conséquent, vos utilisateurs CJA peuvent utiliser les données de manière plus sécurisée, tout en sachant qu’elles sont conformes aux stratégies définies par les gestionnaires de données.

## Étiquetage et stratégies dans Adobe Experience Platform

Lorsque vous créez un jeu de données dans Experience Platform, vous pouvez créer des [libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) pour certains ou tous les éléments du jeu de données. Jusqu’à présent, ces étiquettes n’étaient pas exposées dans CJA. Avec cette version, vous pouvez afficher ces étiquettes dans CJA. Les étiquettes suivantes présentent un intérêt particulier pour CJA :

* Le `C8` label - **[!UICONTROL Aucune mesure]**. Ce libellé signifie que les données ne peuvent pas être utilisées à des fins d’analyse sur les sites web ou les applications de votre entreprise.

* Le `C12` label - **[!UICONTROL Aucune exportation de données générale]**. Les champs de schéma ainsi étiquetés ne peuvent pas être exportés ou téléchargés à partir de CJA (via la création de rapports, l’exportation, l’API, etc.)

L’étiquetage en lui-même ne signifie pas que ces libellés d’utilisation des données sont appliqués. C’est à cela que servent les stratégies. Vous créez vos stratégies via le [API Policy Service](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) dans Experience Platform.

Les stratégies comportent deux composants : le libellé des données et une action marketing que les consommateurs de données peuvent entreprendre dans le cadre de stratégies d’utilisation des données limitées. Dans le contexte de CJA, deux Adobes définis [actions marketing](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) sont importantes :

* Analytics : utilisation des données à des fins d’analyse, telles que la mesure, l’analyse et la création de rapports sur l’utilisation par les consommateurs des sites ou applications de votre entreprise.

* Exporter des données, c’est-à-dire hors de l’environnement d’Adobe.

Vous liez les libellés et les actions marketing à une stratégie, puis vous activez la stratégie. La stratégie prend le libellé et l’action marketing et indique : appliquez cette restriction. Deux stratégies définies par l’Adobe sont affichées dans CJA et affectent la création de rapports et le téléchargement/partage :

* [!UICONTROL Application d’Analytics] policy
* [!UICONTROL Application du téléchargement] policy

### Affichage des étiquettes de données dans les vues de données CJA

Les libellés de données créés dans Experience Platform sont affichés à trois emplacements dans l’interface utilisateur des vues de données :

| Emplacement | Description |
| --- | --- |
| Bouton Infos sur un champ de schéma | Cliquez sur ce bouton pour indiquer quelles étiquettes d’utilisation des données s’appliquent actuellement à un champ :<p>![](assets/data-label-left.png) |
| Rail de droite sous [Paramètres des composants](/help/data-views/component-settings/overview.md) | Toutes les étiquettes d’utilisation des données sont répertoriées ici :<p>![](assets/data-label-right.png) |
| Ajouter des étiquettes de données en tant que colonne | Vous pouvez ajouter des libellés de données en tant que colonne aux colonnes Composants inclus dans les vues de données. Cliquez simplement sur l’icône du sélecteur de colonnes et sélectionnez Étiquettes d’utilisation des données :<p>![](assets/data-label-column.png) |

### Filtrage des étiquettes de gouvernance des données dans les vues de données

Dans l’éditeur des vues de données, cliquez sur l’icône Filtrer dans le rail de gauche et filtrez les composants des vues de données par libellé(s) de gouvernance des données :

![](assets/filter-labels.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir quels composants sont associés à des étiquettes.

### Filtrage des stratégies de gouvernance des données dans les vues de données

Vous pouvez vérifier si une stratégie est activée qui bloque l’utilisation de certains éléments de vue de données CJA pour les analyses ou l’exportation prévue.

Cliquez à nouveau sur l’icône Filtrer dans le rail de gauche, puis, sous Gouvernance des données, cliquez sur Stratégies :

![](assets/filter-policies.png)

Cliquez sur **[!UICONTROL Appliquer]** pour identifier les stratégies activées _pour cette vue de données ?_

### Comment [!UICONTROL Application d’Analytics] la stratégie affecte les projets Workspace

Si cette stratégie est activée, les champs de schéma associés à certains libellés de données (C8, par exemple) ne peuvent pas être utilisés à des fins d’analyse dans CJA Workspace.

Pour les rapports, cela signifie que :

* Vous ne pouvez pas ajouter ces champs aux vues de données et ils sont grisés dans le rail de gauche. [!UICONTROL Champs de schéma] liste.
* Vous ne pouvez pas enregistrer une vue de données contenant des champs bloqués.

Si vous essayez d’effectuer une analyse Workspace sur les vues de données qui contiennent des éléments interdits pour les analyses, vous recevrez une notification similaire à celle-ci :

![](assets/policy-enforce.png)

Sur des composants individuels, le message serait similaire à ceci :

![](assets/policy-enforce2.png)

### Comment [!UICONTROL Application du téléchargement] la stratégie affecte les projets Workspace

Si cette stratégie est activée, tout export ou téléchargement (par exemple, envoi ou partage de fichiers PDF) de projets Workspace hachera les champs sensibles. Vous pouvez toujours effectuer une analyse sur ces champs dans Workspace, mais si vous tentez d’envoyer un courrier électronique ou de partager un projet, les champs bloqués apparaîtront sous la forme d’éléments hachés dans le fichier .pdf.

Ajoutez une capture d’écran ici.

### Affichage des libellés dans le Report Builder

Voir _cette section_ pour plus d’informations. (lien vers le doc Christine)
