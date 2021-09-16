---
title: Création d’une vue de données
description: Tous les paramètres que vous pouvez ajuster pour créer ou modifier une vue de données.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 49b4998194274eec2ab8eca231029ccb5ccf648d
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 77%

---

# Création d’une vue de données

La création dʼune vue de données implique soit la création de mesures et de dimensions à partir dʼéléments de schéma, soit lʼutilisation de composants standard. La plupart des éléments de schéma peuvent être une dimension ou une mesure selon les besoins de votre entreprise. Une fois que vous avez fait glisser un élément de schéma dans une vue de données, des options s’affichent à droite, où vous pouvez ajuster le fonctionnement de la dimension ou de la mesure dans CJA.

## Configuration des paramètres et des conteneurs des vues de données

1. Dans Customer Journey Analytics, accédez à l’onglet **[!UICONTROL Vues de données]**.
2. Cliquez sur **[!UICONTROL Ajouter]** pour créer une nouvelle vue de données et configurer ses paramètres.

![Nouvelle vue de données](assets/new-data-view.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Connexion] | Ce champ relie la vue de données à la connexion que vous avez établie précédemment, qui contient un ou plusieurs jeux de données Adobe Experience Platform. |
| [!UICONTROL Nom] | Il est obligatoire d’attribuer un nom à la vue de données. |
| [!UICONTROL Description] | Une description détaillée nʼest pas obligatoire, mais recommandée. |
| [!UICONTROL Fuseau horaire] | Choisissez le fuseau horaire dans lequel vous souhaitez que vos données soient présentées. |
| [!UICONTROL Balises] | [!UICONTROL Les balises vous permettent d’organiser vos vues de données en catégories.] |
| [!UICONTROL Conteneurs] | Vous pouvez renommer vos conteneurs ici afin de déterminer la façon dont ils apparaîtront dans tout projet Workspace basé sur cette vue de données. Les [!UICONTROL conteneurs] sont utilisés dans les filtres, les abandons/flux, etc. Ils permettent de définir lʼétendue ou les limites de la portée ou du contexte. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=fr#filter-containers) |
| [!UICONTROL Le nom du conteneur Personne est...] | [!UICONTROL Personne] (par défaut). Le conteneur [!UICONTROL Personne] inclut chaque visite et page vue pour les visiteurs au cours dʼune période indiquée. Vous pouvez renommer ce conteneur en « Utilisateur » ou tout autre terme de votre choix. |
| [!UICONTROL Le nom du conteneur Session est...] | [!UICONTROL Session] (par défaut). Le conteneur [!UICONTROL Session] permet dʼidentifier les interactions de pages, les campagnes ou les conversions pour une session spécifique. Vous pouvez renommer ce conteneur en « Visite » ou tout autre terme de votre choix. |
| [!UICONTROL Le nom du conteneur Événement est...] | [!UICONTROL Événement] (par défaut). Le conteneur [!UICONTROL Événement] définit les événements de page que vous souhaitez inclure ou exclure dʼun filtre. |

Vous pouvez ensuite créer des mesures et des dimensions à partir dʼéléments de schéma. Vous pouvez également utiliser des composants standard.

## Création de mesures et de dimensions à partir dʼéléments de schéma

1. Dans [!UICONTROL Customer Journey Analytics] > [!UICONTROL Vues de données], cliquez sur lʼonglet [!UICONTROL Composants].

![Onglet Composants](assets/components-tab.png)

Vous pouvez voir la [!UICONTROL connexion] en haut à gauche qui contient les jeux de données et ses [!UICONTROL champs de schéma] en dessous. Gardez les éléments suivants à l’esprit :

* Les composants déjà inclus sont les composants standard requis (générés par le système).
* Par défaut, Adobe applique le filtre **[!UICONTROL Contient des données]**. Ainsi, seuls les champs de schéma contenant des données apparaissent. Si vous recherchez un champ qui ne contient pas de données, supprimez le filtre.

1. Faites maintenant glisser un champ de schéma, tel que [!UICONTROL pageTitle], du rail de gauche vers la section Mesures ou Dimensions.

   Vous pouvez faire glisser plusieurs fois le même champ de schéma vers les sections des dimensions ou des mesures et configurer la même dimension ou mesure de différentes manières.
Par exemple, à partir du champ **[!UICONTROL pageTitle]**, vous pouvez créer une dimension appelée « Pages de produits » et une autre « Pages dʼerreurs », etc., en renommant le **[!UICONTROL nom du composant]** à droite. À partir du champ **[!UICONTROL pageTitle]**, vous pouvez également créer des mesures à partir dʼune valeur de chaîne. Par exemple, vous pouvez créer une ou plusieurs mesures **[!UICONTROL Commandes]** avec des paramètres dʼattribution différents et des valeurs dʼinclusion/exclusion différentes.

   ![Onglet 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Vous pouvez faire glisser des dossiers de champs de schéma entiers depuis le rail de gauche et ils sont automatiquement triés dans les sections traditionnelles. Les champs de chaîne se retrouvent dans la section [!UICONTROL Dimensions] et les chiffres dans la section [!UICONTROL Mesures]. Vous pouvez également cliquer sur **[!UICONTROL Ajouter tout]** et tous les champs de schéma sont ajoutés.

1. Une fois le composant sélectionné, plusieurs paramètres sʼaffichent sur la droite. Configurez le composant à l’aide des paramètres décrits à la section

* [ Paramètres des composants - Aperçu](/help/data-views/component-settings/overview.md)
* [ Paramètres du composant Attribution](/help/data-views/component-settings/attribution.md)
* [ Paramètres du composant Comportement](/help/data-views/component-settings/behavior.md)
* [ Paramètres du composant de formatage](/help/data-views/component-settings/format.md)
* [[!UICONTROL Paramètres d’inclusion|] d’exclusion](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL Paramètres du composant ] Déduplication des mesures](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL Aucun paramètre ] de composant de valeur](/help/data-views/component-settings/no-value-options.md)
* [ Paramètres de composant persistant](/help/data-views/component-settings/persistence.md)
   [[!UICONTROL Paramètres du composant ] bucketingvalue](/help/data-views/component-settings/value-bucketing.md)

## Utilisation de la fonctionnalité [!UICONTROL Dupliquer]

La duplication de mesures ou de dimensions ainsi que la modification ultérieure de paramètres spécifiques est un moyen facile de créer plusieurs mesures ou dimensions à partir d’un seul champ de schéma. Sélectionnez tout simplement le paramètre [!UICONTROL Dupliquer] sous le nom de la mesure ou de la dimension en haut à droite. Ensuite, modifiez la nouvelle mesure ou dimension et enregistrez-la sous un nom plus explicite.

![Dupliquer](assets/duplicate.png)

## Filtrage des champs de schéma et des dimensions/mesures

Vous pouvez filtrer les champs de schéma dans le rail de gauche par les types de données suivants :

![Champs de filtrage](assets/filter-fields.png)

Vous pouvez également filtrer par jeux de données et selon quʼun champ de schéma contient des données ou quʼil sʼagit dʼune identité. Par défaut, nous appliquons le filtre **[!UICONTROL Contient des données]** à toutes les vues de données.

![Filtrer les autres](assets/filter-other.png)

## Ajouter un filtre global à la vue de données

Vous pouvez ajouter des filtres qui s’appliquent à une vue de données entière. Ce filtre est appliqué à tout rapport exécuté dans Workspace.

1. Cliquez sur lʼonglet [!UICONTROL Paramètres] dans [!UICONTROL Vues de données].
1. Faites glisser un filtre de la liste du rail de gauche vers le champ [!UICONTROL Ajouter des filtres].
