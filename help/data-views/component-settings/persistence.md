---
title: Paramètres des composants de persistance
description: Ils établissent si et comment les valeurs des dimensions persistent dʼun événement à lʼautre.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 79%

---


# Paramètres de composant de [!UICONTROL persistance] {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="Persistance"
>abstract="Configurez le modèle d’attribution par défaut appliqué à une dimension. L’attribution s’applique avant les segments dans les rapports."

<!-- markdownlint-enable MD034 -->



La [!UICONTROL persistance] est la possibilité, pour une valeur de dimension donnée, d’établir une relation avec une mesure au-delà de l’événement sur lequel elle est définie. Elle recourt à une combinaison d’attribution et d’expiration.

![Fenêtre Vues de données mettant en surbrillance les options de persistance](../assets/persistence.png)

* L’**attribution** vous permet de déterminer la valeur conservée lorsque plusieurs éléments de dimension peuvent persister à la fois dans une seule colonne.

  >[!NOTE]
  >
  >Si un [modèle d’attribution différent du modèle par défaut](/help/data-views/component-settings/attribution.md) est défini sur une mesure dans un rapport, le modèle d’attribution ignore l’attribution que vous avez définie sur la dimension pour le même rapport.
  >
  >Cependant, lors de l’[export d’un tableau complet](/help/analysis-workspace/export/export-cloud.md) qui comprend plusieurs dimensions, l’attribution conserve les modèles d’attribution appliqués à chaque dimension.

* L’**expiration** vous permet de déterminer la durée pendant laquelle un élément de dimension persiste au-delà de l’événement sur lequel il est défini.

La [!UICONTROL persistance] est disponible uniquement dans les dimensions et est rétroactive aux données auxquelles elle est appliquée. Il s’agit d’une transformation de données immédiate qui se produit avant l’application de la segmentation ou d’autres opérations d’analyse.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Définir la persistance] | Activez la persistance pour la dimension. Si la persistance n’est pas activée, la dimension se rapporte uniquement aux mesures qui existent dans le même événement. Ce paramètre est désactivé par défaut. |
| [!UICONTROL Attribution] | Spécifiez le modèle d’attribution utilisé sur une dimension pour la persistance. Les options sont les suivantes :<ul><li>**[!UICONTROL La plus récente]** : les valeurs de la dimension persistent jusqu’à ce qu’elles soient remplacées par les valeurs suivantes</li><li> **[!UICONTROL Original]** : la première valeur de cette dimension persiste et n’est pas remplacée par les valeurs suivantes</li><li>**[!UICONTROL Toutes]** : toutes les valeurs de cette dimension persistent simultanément.</li><li>**[!UICONTROL Première valeur connue]** : la première valeur de cette dimension est utilisée et sera appliquée à tous les événements avant et après.</li><li>**[!UICONTROL Dernière valeur connue]** : la dernière valeur de cette dimension est utilisée et sera appliquée à tous les événements avant et après.</li></ul> |
| [!UICONTROL Expiration] | Spécifiez la fenêtre de persistance pour une dimension. Les options sont les suivantes : <ul><li>**[!UICONTROL Session]** (par défaut)</li><li>**[!UICONTROL Personne]**</li><li>**[!UICONTROL Temps personnalisé]**</li><li>**[!UICONTROL Mesure]**</li></ul>. Il se peut que vous ayez besoin de pouvoir faire expirer la dimension lors dʼun achat (comme les termes de recherche interne ou dʼautres cas dʼutilisation du marchandisage). Le délai d’expiration maximal que vous pouvez définir est de 90 jours. Si vous sélectionnez une attribution de [!UICONTROL Toutes], seule l’expiration [!UICONTROL Session] ou [!UICONTROL Personne] est disponible. |

{style="table-layout:auto"}

## Paramètres [!UICONTROL Attribution]

Les paramètres d’attribution disponibles sont les suivants :

* **[!UICONTROL La plus récente]** : fait persister la valeur la plus récente (par horodatage) présente dans la dimension. Toutes les valeurs suivantes qui se produisent pendant la période d’expiration de la dimension remplacent la valeur persistante précédente. Si « Traiter &quot;Aucune valeur&quot; comme valeur » est activé sur cette dimension sous [Aucune option de valeur](no-value-options.md), les valeurs vides remplacent les valeurs précédemment conservées. Par exemple, considérez le tableau suivant avec l’attribution [!UICONTROL La plus récente] et l’expiration [!UICONTROL Session] :

  | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valeurs du jeu de données |  | C | B |  | A |
  | Affectation la plus récente |  | C | B | B | A |

* **[!UICONTROL Original]** : conserve par horodatage la valeur d’origine présente dans la dimension pour la durée de la période d’expiration. Si cette dimension comporte une valeur, elle n’est pas remplacée lorsqu’une autre valeur est vue dans un événement suivant. Par exemple, considérez le tableau suivant avec l’attribution [!UICONTROL Original] et l’expiration [!UICONTROL Session] :

  | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valeurs du jeu de données |  | C | B |  | A |
  | Affectation dʼorigine |  | C | C | C | C |

* **[!UICONTROL Toutes]** : agit de la même manière que le modèle dʼattribution de [!UICONTROL Participation] pour les mesures. Conserve toutes les valeurs de manière égale afin que chacune d’elles reçoive un crédit complet pour la mesure dans les rapports. Par exemple, considérez le tableau suivant avec l’attribution [!UICONTROL Toutes] et l’expiration [!UICONTROL Session] :

  | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valeurs du jeu de données | A | B | C |  | A |
  | Affectation Tous | A | A, B | A, B, C | A, B, C | A, B, C |

* **[!UICONTROL Première valeur connue]** et **[!UICONTROL Dernière valeur connue]** : (19 janvier 2022 ) ces deux modèles d’attribution répondent aux cas d’utilisation des dimensions « entrée » et « sortie ». Ils récupèrent la première ou la dernière valeur observée pour une dimension dans une étendue de persistance spécifiée (session, personne ou période personnalisée avec recherche en amont) et l’appliquent à tous les événements de lʼétendue spécifiée. Exemple :

  | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
  | --- | --- | --- | --- | --- | --- |
  | Date et heure (min) | 1 | 2 | 3 | 6 | 7 |
  | Valeurs d’origine |  | C | B |  | A |
  | Première valeur connue | C | C | C | C | C |
  | Dernière valeur connue | A | A | A | A | A |


## Paramètres [!UICONTROL Expiration]

Les paramètres d’expiration disponibles sont les suivants :

* **Session** : expire après une session donnée. Fenêtre d’expiration par défaut.
* **Créneau de rapport de la personne** : expire à la fin de votre créneau de rapport.
* **Créneau de rapport du compte global** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} : expire à la fin du créneau de rapport.
* **Créneau de rapport du compte** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} : expire à la fin de la période du créneau de rapport.
* **Créneau de rapport d’opportunité** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} : expire à la fin du créneau de rapport.
* **Créneau de rapport du groupe d’achat** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} : expire à la fin du créneau de rapport.
* **Heure personnalisée** : expire après une période spécifiée (jusqu’à 90 jours). Cette option dʼexpiration est disponible uniquement pour les modèles dʼattribution d’origine et La plus récente. Lors de lʼutilisation de lʼexpiration basée sur le temps, les valeurs antérieures au début de votre intervalle de compte rendu des performances (jusquʼà 90 jours) sont prises en compte.
* **Mesure** : lorsque cette mesure est vue dans un événement, la valeur conservée dans la dimension arrive immédiatement à expiration. Vous pouvez utiliser n’importe quelle mesure comme fin d’expiration pour cette dimension. Cette option dʼexpiration est disponible uniquement pour les paramètres dʼattribution Original et La plus récente.


## [!UICONTROL Dimension de liaison]

Un menu déroulant qui vous permet de lier la persistance d’une valeur de dimension aux valeurs de dimension dans une autre dimension. Les options de liste déroulante valides comprennent dʼautres dimensions incluses dans la vue de données.

Consultez [Utilisation de dimensions et de mesures de liaison dans Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) pour obtenir des exemples d’utilisation efficace des dimensions de liaison.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensions de liaison](https://video.tv.adobe.com/v/3409292/?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## [!UICONTROL Mesure de liaison]

Un menu déroulant qui vous permet de choisir une mesure qui agit comme un déclencheur de liaison. Les options valides comprennent les mesures incluses dans la vue de données.

Ce paramètre nʼapparaît que lorsque la Dimension de liaison est plus basse dans le tableau d’objets que le composant. Lorsque la mesure de liaison est présente dans un événement, les valeurs de la dimension sont copiées à partir de la dimension au niveau de lʼévénement vers le niveau inférieur du schéma de la dimension de liaison.

Consultez le deuxième exemple sous [Utiliser des dimensions et des mesures de liaison dans Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) pour plus d’informations sur l’utilisation efficace des mesures de liaison.
