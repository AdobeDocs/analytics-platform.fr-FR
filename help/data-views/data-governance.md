---
title: Étiquettes et politiques
description: Découvrez comment les libellés de données et les stratégies définis dans Adobe Experience Platform affectent les vues de données et la création de rapports dans Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 60%

---

# Étiquettes et politiques

Lorsque vous créez un jeu de données dans Experience Platform, vous pouvez créer des [libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=fr) pour certains éléments du jeu de données ou pour l’ensemble de ceux-ci. Vous pouvez afficher ces libellés et stratégies dans Customer Journey Analytics.

Les libellés suivants présentent un intérêt particulier pour Customer Journey Analytics :

* Le `C8` libellé - **[!UICONTROL Aucune mesure]**. Ce libellé signifie que les données ne peuvent pas être utilisées à des fins d’analyse sur les sites web ou les applications de votre entreprise.

* Le `C12` libellé - **[!UICONTROL Aucune exportation de données générale]**. Les champs de schéma ainsi étiquetés ne peuvent pas être exportés ou téléchargés depuis Customer Journey Analytics (via le reporting, l’export, l’API, etc.)

>[!NOTE]
>
>Les libellés d’utilisation des données ne sont pas propagés automatiquement aux jeux de données assemblés. Ils peuvent toutefois être ajoutés manuellement.

L’étiquetage en lui-même ne signifie pas que ces libellés d’utilisation des données sont appliqués. C&#39;est à cela que servent les politiques. Vous créez vos politiques en passant par [l’API du service de politique](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=fr) dans Experience Platform.

Deux stratégies définies par l’Adobe sont affichées dans Customer Journey Analytics et affectent la création de rapports et le téléchargement/partage :

* Politique **[!UICONTROL Application d’Analytics]**
* Politique **[!UICONTROL Application du téléchargement]**

## Affichage des libellés de données dans les vues de données Customer Journey Analytics

Les libellés de données créés dans Experience Platform sont affichés à trois emplacements dans l’interface utilisateur des vues de données :

| Emplacement | Description |
| --- | --- |
| Bouton Infos sur un champ de schéma | Cliquer sur ce bouton indique les [!UICONTROL libellés d’utilisation des données] qui s’appliquent actuellement à un champ :<p>![](assets/data-label-left.png) |
| Rail de droite sous [Paramètres des composants](/help/data-views/component-settings/overview.md) | Tous les [!UICONTROL libellés d’utilisation des données] sont répertoriés ici :<p>![](assets/data-label-right.png) |
| Ajouter des libellés de données sous forme d’une colonne | Vous pouvez ajouter les [!UICONTROL libellés d’utilisation des données] sous forme d’une colonne aux colonnes [!UICONTROL Composants inclus] dans les vues de données. Cliquez simplement sur l’icône du sélecteur de colonnes et sélectionnez **[!UICONTROL Libellés d’utilisation des données]** :<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrer les libellés de gouvernance des données dans les vues de données

Dans l’éditeur des vues de données, cliquez sur le [!UICONTROL filter] dans le rail de gauche et filtrez les composants des vues de données par **[!UICONTROL Gouvernance des données]** et type **[!UICONTROL Libellé]**:

![](assets/filter-labels.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir quels composants sont associés à des libellés.

## Filtrer les politiques de gouvernance des données dans les vues de données

Vous pouvez vérifier si une stratégie est activée qui bloque l’utilisation de certains éléments de vue de données de Customer Journey Analytics pour les analyses ou l’exportation prévue.

Cliquez de nouveau sur le [!UICONTROL filter] dans le rail de gauche et sous **[!UICONTROL Gouvernance des données]**, cliquez sur **[!UICONTROL Stratégies]**:

![](assets/filter-policies.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir les politiques activées.

## Comment les politiques activées affectent-elles les vues de données ?

Si les politiques **[!UICONTROL Application d’Analytics]** ou **[!UICONTROL Application du téléchargement]** sont activées, les composants de schéma associés à certains libellés de données (C8 ou C12, par exemple) ne peuvent pas être ajoutés aux vues de données.

Ces composants sont grisés dans la liste de rail de gauche [!UICONTROL Champs de schéma] :

![](assets/component-greyed.png)

Vous ne pouvez pas non plus enregistrer une vue de données qui contient des champs bloqués.

>[!MORELIKETHIS]
>[Télécharger des données sensibles](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Que sont les libellés restreints dans Report Builder ?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=fr)


