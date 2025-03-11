---
title: 'Paramètres des composants : valeurs dʼinclusion/exclusion'
description: Incluez ou excluez de façon conditionnelle un élément de dimension en fonction de sa valeur.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 74%

---

# Paramètres des composants : valeurs dʼinclusion/exclusion {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="Inclure/Exclure les valeurs"
>abstract="Filtrez une mesure pour ne comptabiliser que les valeurs correspondant à des critères spécifiques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="Inclure/Exclure les valeurs"
>abstract="Précisez une dimension afin de n’inclure que les valeurs correspondant à des critères spécifiques. Les inclusions et les exclusions se produisent avant l’attribution et les filtres dans les rapports. Déterminez si la logique de filtre spécifiée respecte la casse."

<!-- markdownlint-enable MD034 -->

Les valeurs dʼinclusion/exclusion vous permettent de créer des règles qui dépendent de la valeur dʼun élément de dimension. Les valeurs qui ne correspondent pas aux critères définis sont traités dans Analysis Workspace comme si elles nʼavaient jamais existé, bien que les données existent toujours dans le jeu de données sous-jacent.

![Fenêtre Vues de données mettant en surbrillance les valeurs Inclure et exclure](../assets/include-exclude.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Définir les valeurs d’inclusion/exclusion] | Case à cocher permettant dʼactiver les conditions dans lesquelles les données sont incluses dans une vue de données. |
| [!UICONTROL Respect de la casse] | Visible sur les types de données du schéma de chaîne. La valeur par défaut est « activé ». Ce paramètre sʼapplique uniquement à la logique [!UICONTROL Valeurs dʼinclusion/exclusion], et non à la valeur obtenue. Il vous permet dʼindiquer si la règle est sensible à la casse. |
| [!UICONTROL Correspond à] | Permet de définir les valeurs à prendre en compte pour le compte rendu des performances avant lʼaffectation et les filtres (par exemple, utilisez uniquement les valeurs contenant le mot « erreur »). Vous pouvez indiquer **[!UICONTROL Si tous les critères sont satisfaits]** ou **[!UICONTROL Si au moins l’un d’entre eux est satisfait]**. Séparez chaque valeur à l’aide d’un espace. |
| [!UICONTROL Critères] | Permet de définir la logique correspondante qui doit être appliquée à une règle de filtrage spécifique.<ul><li>**Chaîne** : [!UICONTROL Contient l’expression], [!UICONTROL Contient n’importe quel terme], [!UICONTROL Contient tous les termes], [!UICONTROL Ne contient aucun terme], [!UICONTROL Ne contient pas l’expression], [!UICONTROL Est différent de ], [!UICONTROL Commence par], [!UICONTROL Se termine par] </li><li>**Double/Entier** : [!UICONTROL Est égal à], [!UICONTROL N’est pas égal à], [!UICONTROL Est supérieur à], [!UICONTROL Est inférieur à], [!UICONTROL Est supérieur ou égal à], [!UICONTROL Est inférieur ou égal à]</li><li>**Date** : [!UICONTROL Est égal à], [!UICONTROL N’est pas égal à], [!UICONTROL Est ultérieur à], [!UICONTROL Est antérieur à], [!UICONTROL Se produit dans ]</li></ul> |
| [!UICONTROL Opérande correspondant] | Permet de définir lʼopérande correspondant auquel lʼopérateur correspondant doit être appliqué.<ul><li>**Chaîne** : champ de texte</li><li>**Doublon/Entier** : champ de texte avec des flèches haut/bas pour les valeurs numériques</li><li>**Date** : sélecteur de granularité journalière (calendrier)</li><li>**Date/heure** : sélecteur de granularité de la date et de lʼheure</li></ul> |
| [!UICONTROL Ajouter une règle] | Permet de définir un opérateur et un opérande correspondant supplémentaire. |

{style="table-layout:auto"}
