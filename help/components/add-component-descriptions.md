---
description: Découvrez comment les administrateurs et administratrices peuvent ajouter des descriptions aux composants à l’aide d’une vue de données ou du dictionnaire de données.
title: Ajouter des descriptions des composants
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# Ajouter des descriptions des composants

Les descriptions permettent aux utilisateurs et utilisatrices de savoir comment utiliser les différents composants lors de la création de projets dans Analysis Workspace ou lors de l’affichage de rapports.

Les administrateurs et administratrices de Customer Journey Analytics peuvent ajouter des descriptions pour les composants (dimensions, mesures, segments et périodes) dans une vue de données ou à l’aide du dictionnaire de données.

## Vue de données

Vous pouvez ajouter une description à un composant que vous avez ajouté à votre vue de données. Voir [ Paramètres des composants ](/help/data-views/component-settings/overview.md).

## Dictionnaire de données

Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices, et aux administrateurs et administratrices, de suivre et de mieux comprendre les composants dans leur environnement Customer Journey Analytics. Le dictionnaire de données permet aux administrateurs et administratrices d’ajouter des descriptions de composant directement dans Analysis Workspace.

Pour plus d’informations sur la modification d’une description de composant dans le dictionnaire de données, voir [Modifier les entrées de composant dans le dictionnaire de données](/help/components/data-dictionary/edit-entries-data-dictionary.md).

Pour obtenir des informations générales sur le dictionnaire de données, consultez la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Paramètres des composants de la vue de données](/help/data-views/component-settings/overview.md)
>[Entrées du composant Dictionnaire de données](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Génération automatique de descriptions

{{release-limited-testing-section}}

Au lieu d’écrire chaque description manuellement, Customer Journey Analytics peut utiliser l’IA générative pour écrire des descriptions pour vous. Vous pouvez générer une description pour un seul composant ou générer des descriptions pour de nombreux composants en même temps.

Descriptions générées :

* Ne contiennent pas plus de 3 phrases.
* Terminez par le texte **[!UICONTROL Généré par Adobe à l’aide de l’IA]** afin que les utilisateurs et utilisatrices sachent que la description a été générée.
* Modifiables une fois qu’ils ont été générés.

### Conditions préalables

Avant de pouvoir générer des descriptions, votre entreprise doit accepter certains termes juridiques d’IA générative. Si votre entreprise n’a pas accepté ces conditions, l’option permettant de générer des descriptions est grisée. Sélectionnez l’icône d’information ![Infos](/help/assets/icons/InfoOutline.svg) en regard de l’option pour savoir comment activer la fonctionnalité, ou contactez l’administrateur ou l’administratrice de votre organisation ou l’équipe du compte Adobe.

### Comment sont générées les descriptions ?

Les descriptions générées sont basées sur la définition du composant et sur un contexte supplémentaire sur la manière dont le composant est utilisé dans votre vue de données, tel que :

* Éléments principaux d’une dimension
* Composants fréquemment utilisés avec le composant

Lorsqu’une mesure calculée ou un segment fait référence à un autre segment, la description générée explique la définition du segment référencé.

### Générer des descriptions à partir de divers emplacements

Vous pouvez générer des descriptions dans les zones suivantes de Customer Journey Analytics. Certains emplacements vous permettent de générer des descriptions pour plusieurs composants, d’autres non.

Sélectionnez un emplacement pour savoir comment y générer des descriptions.

| Emplacement | Composants pris en charge | Un seul composant | Composants multiples |
| --- | --- | --- | --- |
| [Dictionnaire de données](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensions</li><li>Mesures</li><li>Mesures calculées</li><li>Segments</li><li>Périodes</li></ul> | Oui | Oui |
| [Vue de données](/help/data-views/component-settings/overview.md) | <ul><li>Dimensions</li><li>Mesures</li><li>Champs dérivés</li><li>Mesures et dimensions partagées (pour plus d’informations, voir [Mesures et dimensions partagées](#generate-descriptions-for-shared-metrics-and-dimensions).)</li></ul> | Oui | Oui |
| [Créateur de segments](/help/components/segments/seg-builder.md) | Segments | Oui | Non |
| [ Gestionnaire de segments ](/help/components/segments/seg-manage.md#action-bar) | Segments | Non | Oui |
| [Créateur de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | Mesures calculées | Oui | Non |
| [Gestionnaire de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | Mesures calculées | Non | Oui |
| [Créateur de périodes](/help/components/date-ranges/create.md#date-range-builder) | Périodes | Oui | Non |
| [Gestionnaire de périodes](/help/components/date-ranges/manage.md#action-bar) | Périodes | Non | Oui |

{style="table-layout:auto"}

### Générer des descriptions pour les mesures et dimensions partagées

Vous ne pouvez générer des descriptions pour les mesures et dimensions partagées qu’à partir d’une vue de données, comme indiqué dans le tableau de la section [ Générer des descriptions à partir de différents emplacements ](#generate-descriptions-from-various-locations). Vous ne pouvez pas générer de descriptions à partir du [gestionnaire des mesures et dimensions partagées](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager).

Tenez compte des points suivants lorsque vous générez une description pour une mesure ou une dimension partagée dans une vue de données :

* La description s’applique à toutes les vues de données où le composant est partagé et remplace toute description existante pour ce composant dans toutes les autres vues de données et dans le gestionnaire des Mesures et dimensions partagées.

* La description est basée sur le contexte de la vue de données dans laquelle vous la générez (comme les principaux éléments de dimension de la vue de données).


