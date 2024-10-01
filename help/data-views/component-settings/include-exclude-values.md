---
title: 'Paramètres des composants : valeurs dʼinclusion/exclusion'
description: Incluez ou excluez de façon conditionnelle un élément de dimension en fonction de sa valeur.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 94%

---

# Paramètres des composants : valeurs dʼinclusion/exclusion {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_includeexcludevalues"
>title="Inclure/Exclure les valeurs"
>abstract="Filtrer une mesure pour qu’elle compte uniquement des valeurs correspondant à des critères spécifiques."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_includeexcludevalues"
>title="Inclure/Exclure les valeurs"
>abstract="Modifier une dimension pour qu’elle ne contienne que des valeurs correspondant à des critères spécifiques. Les inclusions et les exclusions ont lieu avant l’affectation et les filtres dans les rapports.<br/><br/>**Paramètres **<br/>**Sensible à la casse** : déterminez si la logique de filtre ci-dessous est sensible à la casse."

<!-- markdownlint-enable MD034 -->



Les valeurs dʼinclusion/exclusion vous permettent de créer des règles qui dépendent de la valeur dʼun élément de dimension. Les valeurs qui ne correspondent pas aux critères définis sont traités dans Analysis Workspace comme si elles nʼavaient jamais existé, bien que les données existent toujours dans le jeu de données sous-jacent.

![ Fenêtre de vues de données mettant en surbrillance les valeurs d’exclusion d’inclusion ](../assets/include-exclude.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Définir les valeurs d’inclusion/exclusion] | Case à cocher permettant dʼactiver les conditions dans lesquelles les données sont incluses dans une vue de données. |
| [!UICONTROL Respect de la casse] | Visible sur les types de données du schéma de chaîne. La valeur par défaut est « activé ». Ce paramètre sʼapplique uniquement à la logique [!UICONTROL Valeurs dʼinclusion/exclusion], et non à la valeur obtenue. Il vous permet dʼindiquer si la règle est sensible à la casse. |
| [!UICONTROL Correspond à] | Permet de définir les valeurs à prendre en compte pour le compte rendu des performances avant lʼaffectation et les filtres (par exemple, utilisez uniquement les valeurs contenant le mot « erreur »). Vous pouvez définir **[!UICONTROL si tous les critères sont remplis]**, ou **[!UICONTROL si lʼun dʼeux est rempli]**. |
| [!UICONTROL Critères] | Permet de définir la logique correspondante qui doit être appliquée à une règle de filtrage spécifique.<ul><li>**Chaîne** : contient lʼexpression, contient nʼimporte quel terme, contient tous les termes, ne contient pas nʼimporte quel terme, ne contient pas lʼexpression, est égal à, nʼest pas égal à, commence par, se termine par</li><li>**Doublon/Entier** : est égal à, nʼest pas égal à, est supérieur à, est inférieur à, est supérieur ou égal à, est inférieur ou égal à</li><li>**Date** : est égal à, nʼest pas égal à, est plus récent que, est antérieur à, se produit au niveau de</li></ul> |
| [!UICONTROL Opérande correspondant] | Permet de définir lʼopérande correspondant auquel lʼopérateur correspondant doit être appliqué.<ul><li>**Chaîne** : champ de texte</li><li>**Doublon/Entier** : champ de texte avec des flèches haut/bas pour les valeurs numériques</li><li>**Date** : sélecteur de granularité journalière (calendrier)</li><li>**Date/heure** : sélecteur de granularité de la date et de lʼheure</li></ul> |
| [!UICONTROL Ajouter une règle] | Permet de définir un opérateur et un opérande correspondant supplémentaire. |

{style="table-layout:auto"}
