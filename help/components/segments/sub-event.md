---
title: Analyse Des Sous-Événements
description: Découvrez comment l’analyse des sous-événements vous permet de filtrer des produits individuels ou d’autres conteneurs au sein d’un événement dans Customer Parcours Analytics, en éliminant le fond perdu d’attribution dans les rapports de produit.
feature: Segmentation
hold: true
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: c504a631398d14479c9a2b70d9ef43ac88e35704
workflow-type: tm+mt
source-wordcount: 565
ht-degree: 0%

---

# Analyse des sous-événements

{{release-limited-testing}}

L&#39;analyse des sous-événements permet d&#39;analyser les données d&#39;un événement à un niveau plus granulaire que le niveau de l&#39;événement. Au lieu de filtrer des événements entiers, vous pouvez segmenter des événements sur des conteneurs individuels. Par exemple :

- Segmenter sur une catégorie de produits spécifique sans inclure tous les autres produits achetés dans la même commande
- Voulez-vous segmenter une catégorie de ressources spécifique dans les données d’analyse de contenu ?
- Segmentation d’un canal multimédia spécifique dans les données Media Analytics.


Dans Customer Journey Analytics, définissez les conteneurs d’une vue de données pour lesquels vous souhaitez utiliser l’analyse des sous-événements. Sans analyse de sous-événement, la segmentation sur un attribut d’élément de conteneur renvoie tous les événements où n’importe quel élément d’un événement correspond à l’attribut d’élément de conteneur. Il en résulte une attribution incorrecte et des mesures de revenus exagérées. L’analyse des sous-événements étend le filtre à des lignes d’élément individuelles dans un événement et résout ces problèmes.

Dans l’analyse de sous-événement, la logique d’exclusion se comporte différemment de l’exclusion standard au niveau de l’événement par rapport au conteneur. Lorsque vous excluez des attributs d’élément dans le conteneur, le segment renvoie des événements qui **contiennent des éléments** mais ne correspondent pas à vos critères d’exclusion. Le segment ne renvoie pas d’événement sans élément du tout.


## Exemple

Vous ne voulez mesurer les revenus provenant que de la catégorie des combinaisons professionnelles. Sans analyse des sous-événements, l’application d’un segment pour les suites professionnelles inclut le chiffre d’affaires de chaque produit sur une commande (événement) qui contient au moins un produit appartenant à la catégorie des suites professionnelles. Avec l’analyse des sous-événements, vous définissez le filtre au niveau du produit et ne renvoyez que les recettes des produits de la catégorie des suites professionnelles.

Vous devez également mesurer les revenus en ligne de toutes les autres catégories, à l&#39;exception de la catégorie des costumes professionnels.

>[!BEGINTABS]

>[!TAB Analyse des événements]

Dans le créateur de segments ou dans le cadre d’un **[!UICONTROL segment rapide]**, vous spécifiez pour **[!UICONTROL Inclure]** le **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL est égal à]** **[!UICONTROL Vues professionnelles]** dans le conteneur **[!UICONTROL Events]**.

![Panneau présentant la segmentation au niveau de l’événement pour les suites professionnelles de catégorie de produit](./assets/product-category-segmentation-events.png)

Par conséquent, toutes les commandes contenant au moins une **[!UICONTROL suite professionnelle]** **[!UICONTROL product_category]** sont prises en compte et le chiffre d’affaires des autres produits de ces commandes est inclus dans la mesure **[!UICONTROL chiffre d’affaires]**.Lorsque vous générez des états sur les catégories, toutes les autres valeurs de **[!UICONTROL product_category]** sont générées dans le cadre d&#39;une commande incluant un produit avec le **[!UICONTROL Professional Suits]** **[!UICONTROL product_category]**.

>[!TAB Analyse des sous-événements]

Dans le créateur de segments ou dans le cadre d’un **[!UICONTROL segment rapide]**, vous spécifiez pour **[!UICONTROL Inclure]** le **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL est égal à]** **[!UICONTROL Vues professionnelles]** dans le conteneur **[!UICONTROL Products]**.

![Panneau présentant la segmentation au niveau des sous-événements pour les suites professionnelles de catégorie de produit](./assets/product-category-segmentation-subevents.png)

Par conséquent, toutes les commandes contenant au moins une **[!UICONTROL suite professionnelle]** **[!UICONTROL product_category]** sont prises en compte et seul le chiffre d’affaires des produits appartenant à la **[!UICONTROL suite professionnelle]** **[!UICONTROL product_category]** est inclus pour la mesure **[!UICONTROL chiffre d’affaires]**.Lorsque vous créez des rapports sur des catégories, seule la **[!UICONTROL suite professionnelle]** **[!UICONTROL catégorie_produit]** est signalée.

>[!TAB Analyse de sous-événements (exclure)]

Dans le créateur de segments ou dans le cadre d’un **[!UICONTROL segment rapide]**, vous spécifiez pour **[!UICONTROL Exclure]** le **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** sur le conteneur **[!UICONTROL Products]**.

![Panneau présentant la segmentation au niveau des sous-accès pour exclure la catégorie de produits Hommes](./assets/product-category-segmentation-subevents-exclude.png)

Pour exclure au niveau du produit, les événements contenant au moins un produit sont inclus, puis l’exclusion au niveau des sous-événements est appliquée dans cette portée. Cette exclusion est différente de l’exclusion au niveau de l’événement, qui exclut l’événement entier.

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
