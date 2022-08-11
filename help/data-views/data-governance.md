---
title: Étiquettes et stratégies
description: Découvrez comment les étiquettes de données et les stratégies définies dans AEP affectent les vues de données et les rapports dans CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# Étiquettes et stratégies

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Lorsque vous créez un jeu de données dans Experience Platform, vous pouvez créer des [libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) pour certains ou tous les éléments du jeu de données. Jusqu’à présent, ces étiquettes n’étaient pas exposées dans CJA. Avec cette version, vous pouvez afficher ces libellés et stratégies dans CJA.

Les étiquettes suivantes présentent un intérêt particulier pour CJA :

* Le `C8` label - **[!UICONTROL Aucune mesure]**. Ce libellé signifie que les données ne peuvent pas être utilisées à des fins d’analyse sur les sites web ou les applications de votre entreprise.

* Le `C12` label - **[!UICONTROL Aucune exportation de données générale]**. Les champs de schéma ainsi étiquetés ne peuvent pas être exportés ou téléchargés à partir de CJA (via la création de rapports, l’exportation, l’API, etc.)

L’étiquetage en lui-même ne signifie pas que ces libellés d’utilisation des données sont appliqués. C’est à cela que servent les stratégies. Vous créez vos stratégies via le [API Policy Service](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) dans Experience Platform.

Deux stratégies définies par l’Adobe sont affichées dans CJA et affectent la création de rapports et le téléchargement/partage :

* **[!UICONTROL Application d’Analytics]** policy
* **[!UICONTROL Application du téléchargement]** policy

## Affichage des étiquettes de données dans les vues de données CJA

Les libellés de données créés dans Experience Platform sont affichés à trois emplacements dans l’interface utilisateur des vues de données :

| Emplacement | Description |
| --- | --- |
| Bouton Infos sur un champ de schéma | Cliquer sur ce bouton indique lequel [!UICONTROL Étiquettes d’utilisation des données] s’applique actuellement à un champ :<p>![](assets/data-label-left.png) |
| Rail de droite sous [Paramètres des composants](/help/data-views/component-settings/overview.md) | Quelconque [!UICONTROL Étiquettes d’utilisation des données] sont répertoriées ici :<p>![](assets/data-label-right.png) |
| Ajouter des étiquettes de données en tant que colonne | Vous pouvez ajouter [!UICONTROL Étiquettes d’utilisation des données] en tant que colonne au [!UICONTROL Composants inclus] dans les vues de données. Cliquez simplement sur l’icône du sélecteur de colonnes et sélectionnez **[!UICONTROL Étiquettes d’utilisation des données]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtrage des étiquettes de gouvernance des données dans les vues de données

Dans l’éditeur des vues de données, cliquez sur l’icône Filtrer dans le rail de gauche et filtrez les composants des vues de données par **[!UICONTROL Gouvernance des données]** et type **[!UICONTROL Libellé]**:

![](assets/filter-labels.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir quels composants sont associés à des étiquettes.

## Filtrage des stratégies de gouvernance des données dans les vues de données

Vous pouvez vérifier si une stratégie est activée qui bloque l’utilisation de certains éléments de vue de données CJA pour les analyses ou l’exportation prévue.

Cliquez à nouveau sur l’icône Filtrer dans le rail de gauche et sous **[!UICONTROL Gouvernance des données]**, cliquez sur **[!UICONTROL Stratégies]**:

![](assets/filter-policies.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir les stratégies activées.

## Comment les stratégies activées affectent-elles les vues de données ?

Si la variable **[!UICONTROL Application d’Analytics]** ou **[!UICONTROL Application du téléchargement]** Les stratégies sont activées, les composants de schéma associés à certains libellés de données (C8 ou C12, par exemple) ne peuvent pas être ajoutés aux vues de données.

Ces composants sont grisés dans le rail de gauche. [!UICONTROL Champs de schéma] list :

![](assets/component-greyed.png)

Vous ne pouvez pas non plus enregistrer une vue de données contenant des champs bloqués.

>[!MORELIKETHIS]
>[Téléchargement de données sensibles](/help/analysis-workspace/curate-share/download-send.md)
