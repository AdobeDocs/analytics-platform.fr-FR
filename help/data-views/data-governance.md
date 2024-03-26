---
title: Libellés et politiques
description: Découvrez de quelle manière les étiquettes et les politiques de données définies dans Adobe Experience Platform affectent les vues de données et les rapports dans Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '493'
ht-degree: 100%

---

# Libellés et politiques

Lorsque vous créez un jeu de données dans Experience Platform, vous pouvez créer des [libellés d’utilisation des données](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=fr) pour certains éléments du jeu de données ou pour l’ensemble de ceux-ci. Vous pouvez afficher ces libellés et politiques dans Customer Journey Analytics.

Les libellés suivants présentent un intérêt particulier pour Customer Journey Analytics :

* Libellé `C8` : **[!UICONTROL Aucune mesure]**. Ce libellé signifie que les données ne peuvent pas être utilisées à des fins d’analyse sur les sites web ou les applications de votre entreprise.

* Libellé `C12` : **[!UICONTROL Aucun export de données générale]**. Les champs de schéma ainsi libellés ne peuvent pas être exportés ou téléchargés à partir de Customer Journey Analytics (via la création de rapports, l’export, l’API, etc.).

>[!NOTE]
>
>Les libellés d’utilisation des données ne sont pas propagés automatiquement aux jeux de données regroupés. Ils peuvent toutefois être ajoutés manuellement.

L’étiquetage en lui-même ne signifie pas que ces libellés d’utilisation des données sont appliqués. C’est à cela que servent les politiques. Vous créez vos politiques en passant par l’[UI d’Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html) ou via l’[API Policy Service](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html) dans Experience Platform.

Deux politiques définies par Adobe sont affichées dans Customer Journey Analytics et affectent la création de rapports et le téléchargement/partage :

* Politique **[!UICONTROL Application d’Analytics]**
* Politique **[!UICONTROL Application du téléchargement]**

## Afficher les étiquettes de données dans les vues de données de Customer Journey Analytics

Les étiquettes de données créées dans Experience Platform sont affichées à trois emplacements dans l’interface utilisateur des vues de données :

| Emplacement | Description |
| --- | --- |
| Bouton Infos sur un champ de schéma | Cliquer sur ce bouton indique les [!UICONTROL libellés d’utilisation des données] qui s’appliquent actuellement à un champ :<p>![](assets/data-label-left.png) |
| Rail de droite sous [Paramètres des composants](/help/data-views/component-settings/overview.md) | Tous les [!UICONTROL libellés d’utilisation des données] sont répertoriés ici :<p>![](assets/data-label-right.png) |
| Ajouter des étiquettes de données sous la forme d’une colonne | Vous pouvez ajouter les [!UICONTROL libellés d’utilisation des données] sous forme d’une colonne aux colonnes [!UICONTROL Composants inclus] dans les vues de données. Cliquez simplement sur l’icône du sélecteur de colonnes et sélectionnez **[!UICONTROL Libellés d’utilisation des données]** :<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrer les libellés de gouvernance des données dans les vues de données

Dans l’éditeur des vues de données, cliquez sur l’icône [!UICONTROL Filtrer] dans le rail de gauche et filtrez les composants des vues de données en fonction de la **[!UICONTROL Gouvernance des données]** et du type de **[!UICONTROL Libellé]** :

![](assets/filter-labels.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir quels composants sont associés à des libellés.

## Filtrer les politiques de gouvernance des données dans les vues de données

Vous pouvez vérifier si une politique activée bloque l’utilisation de certains éléments de vue de données Customer Journey Analytics pour les analyses ou les exports prévus.

Cliquez à nouveau sur l’icône [!UICONTROL Filtrer] dans le rail de gauche, puis sous **[!UICONTROL Gouvernance des données]**, cliquez sur **[!UICONTROL Politiques]** :

![Filtrer les composants inclus par liste affichant l’option Application d’Analytics sélectionnée.](assets/filter-policies.png)

Cliquez sur **[!UICONTROL Appliquer]** pour voir les politiques activées.

## Comment les politiques activées affectent-elles les vues de données ?

Si la politique **[!UICONTROL Application d’Analytics]** est activée, les composants de schéma associés à certains libellés de données (tels que C8) ne peuvent pas être ajoutés aux vues de données.

Ces composants sont grisés dans la liste de rail de gauche [!UICONTROL Champs de schéma] :

![Composants grisés et message Politiques indiquant que des politiques ont été appliquées à ce champ pour limiter l’utilisation des données.](assets/component-greyed.png)

Vous ne pouvez pas non plus enregistrer une vue de données qui contient des champs bloqués.

>[!MORELIKETHIS]
>[Télécharger des données sensibles](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>[Que sont les libellés restreints dans Report Builder ?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html)


