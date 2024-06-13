---
title: Libellés et politiques
description: Découvrez de quelle manière les étiquettes et les politiques de données définies dans Adobe Experience Platform affectent les vues de données et les rapports dans Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 45%

---

# Libellés et politiques

Lorsque vous créez un jeu de données dans Experience Platform, vous pouvez créer des [libellés d’utilisation des données](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) pour certains éléments ou tous les éléments du jeu de données. Vous pouvez afficher ces libellés et politiques dans Customer Journey Analytics.

Les libellés suivants présentent un intérêt particulier pour Customer Journey Analytics :

* Libellé `C8` : **[!UICONTROL Aucune mesure]**. Ce libellé signifie que les données ne peuvent pas être utilisées à des fins d’analyse sur les sites web ou les applications de votre entreprise.

* La variable `C12` label - **[!UICONTROL Pas d&#39;export général de données]**. Les champs de schéma ainsi libellés ne peuvent pas être exportés ou téléchargés à partir de Customer Journey Analytics (via la création de rapports, l’export, l’API, etc.).

>[!NOTE]
>
>Les libellés d’utilisation des données ne sont pas propagés automatiquement aux jeux de données regroupés. Ils peuvent toutefois être ajoutés manuellement.

L’étiquetage en lui-même ne signifie pas que ces libellés d’utilisation des données sont appliqués. C’est à cela que servent les politiques. Vous pouvez créer vos stratégies à l’aide de l’option [Interface utilisateur Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) ou via le [API Policy Service](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) dans Experience Platform.

Dans Experience Platform, deux stratégies définies par l’Adobe peuvent apparaître dans Customer Journey Analytics et affecter la création de rapports et l’exportation de données :

* **[!UICONTROL Limitation des analyses d’utilisation et des mesures basées sur les utilisateurs]** stratégie, à l’aide de `C8` libellé, et
* **[!UICONTROL Limitation de l’exportation des données]** stratégie, à l’aide de `C12` libellé.

## Afficher les étiquettes de données dans les vues de données de Customer Journey Analytics

Les étiquettes de données que vous ou d’autres ont créées dans Experience Platform sont affichées à trois emplacements dans l’interface utilisateur des vues de données :

| Emplacement | Description |
| --- | --- |
| Bouton Infos sur un champ de schéma | Cliquer sur ce bouton indique les [!UICONTROL libellés d’utilisation des données] qui s’appliquent actuellement à un champ :<p>![](assets/data-label-left.png) |
| Rail de droite sous [Paramètres des composants](/help/data-views/component-settings/overview.md) | Tous les [!UICONTROL libellés d’utilisation des données] sont répertoriés ici :<p>![](assets/data-label-right.png) |
| Ajouter des étiquettes de données sous la forme d’une colonne | Vous pouvez ajouter les [!UICONTROL libellés d’utilisation des données] sous forme d’une colonne aux colonnes [!UICONTROL Composants inclus] dans les vues de données. Sélectionnez simplement l’icône du sélecteur de colonnes et choisissez **[!UICONTROL Étiquettes d’utilisation des données]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrer les libellés de gouvernance des données dans les vues de données

Dans l’éditeur des vues de données, sélectionnez la variable [!UICONTROL filter] dans le rail de gauche et filtrez les composants des vues de données par **[!UICONTROL Gouvernance des données]** et type de **[!UICONTROL Libellé]**:

![](assets/filter-labels.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir quels composants sont associés à des libellés.

## Filtrer les politiques de gouvernance des données dans les vues de données

Vous pouvez vérifier si une stratégie (par exemple, une stratégie que vous avez créée, nommée **[!UICONTROL Application d’Analytics]**) est activé. Et si cette stratégie bloque l’utilisation de certains éléments de vue de données de Customer Journey Analytics pour les analyses ou l’exportation de données.

Sélectionnez à nouveau le [!UICONTROL filter] dans le rail de gauche et sous **[!UICONTROL Gouvernance des données]**, sélectionnez **[!UICONTROL Stratégies]**:

![Filtrage des composants inclus par liste affichant l’option Limiter l’analyse de l’utilisation et la mesure basée sur les utilisateurs sélectionnée](assets/filter-policies.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir les stratégies activées.

## Comment les politiques activées affectent-elles les vues de données ?

Si une ou plusieurs stratégies sont activées avec des étiquettes C8 ou C12, les composants de schéma auxquels certains libellés de données sont appliqués ne peuvent pas être ajoutés aux vues de données.

Ces composants sont grisés dans le rail de gauche. [!UICONTROL Champs de schéma] list :

![Composants grisés et message Politiques indiquant que des politiques ont été appliquées à ce champ pour limiter l’utilisation des données.](assets/component-greyed.png)

Vous ne pouvez pas non plus enregistrer une vue de données qui contient des champs bloqués.

Soyez prudent lorsque vous essayez d’appliquer des étiquettes d’accès et de gouvernance des données (par le biais de stratégies) sur des champs ou des groupes de champs dans Experience Platform, pour lesquels des composants sont déjà définis dans votre vue de données. Cette boîte de dialogue peut s’afficher.

![Violation](assets/violation.png)

Vous devez d’abord résoudre la violation (par exemple, supprimer les composants de la vue de données).


>[!MORELIKETHIS]
>
>[Télécharger des données sensibles](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Que sont les libellés restreints dans Report Builder ?](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


