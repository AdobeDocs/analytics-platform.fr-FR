---
title: Optimisation des performances CJA
description: Bonnes pratiques relatives à l’optimisation des performances de CJA
solution: Customer Journey Analytics
role: Admin
hide: true
hide-from-toc: true
source-git-commit: a546c52d2a686c38f7a9a23e0c541568c2918495
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 93%

---


# Optimisation des performances de CJA

>[!NOTE]
>
>Pour optimiser les facteurs de performances de Workspace, voir [Optimiser [!UICONTROL Analysis Workspace] performance](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

Ces facteurs influent sur les performances globales de CJA :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| Complexité du filtre | Des filtres complexes peuvent avoir un impact significatif sur la performance des projets. | Les facteurs qui ajoutent de la complexité à un filtre (dans l’ordre décroissant d’impact) incluent les éléments suivants : <ul><li>Les opérateurs de type « contient », « contient n’importe lequel », « correspond à », « commence par » ou « se termine par ». </li><li>Le filtrage séquentiel, en particulier lorsque des restrictions dimensionnelles (Within/After) sont utilisées. </li><li>Le nombre d’éléments de dimensions uniques dans les dimensions utilisées dans le filtre (par exemple, Page = « A » lorsque la page comporte 10 éléments uniques est plus rapide que Page = « A » lorsque la page comporte 100 000 éléments uniques). </li><li>Le nombre de dimensions différentes utilisées (par exemple, Page = ’Home’ et Page = ’Search results’ seront plus rapides que eVar 1 = ’red’ et eVar 2 = ’blue’)</li><li>Beaucoup d’opérateurs OR (au lieu de AND)</li><li>Des contenants imbriqués dont la portée varie (par ex., « Hit inside of Visit inside of Visitor »)</li></ul> | Bien qu’il soit impossible d’éviter certains facteurs de complexité, recherchez les possibilités de réduire la complexité de vos filtres. En général, plus vous pouvez être précis dans vos critères de filtre, mieux c’est. Par exemple :<ul><li>Avec les conteneurs, l’utilisation d’un seul conteneur en haut du filtre est plus rapide qu’une série de conteneurs imbriqués.</li><li>Avec les opérateurs, « est égal à » sera plus rapide que « contient » et « est égal à l’un(e) de » sera plus rapide que « contient l’un des ».</li><li>Avec de nombreux critères, les opérateurs AND seront plus rapides qu’une série d’opérateurs OR.</li></ul> Recherchez également des occasions de réduire plusieurs instructions OR en une seule instruction « est égal à l’un(e) de ». <br> |
| Complexité de la visualisation (filtres, mesures) | Le type de visualisation (abandons ou tableau à structure libre) ajouté à un projet n’a pas de réelle incidence sur les performances du projet. Le temps de traitement dépend de la complexité de la visualisation. | Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :<ul><li>Plage de données demandée</li><li>Nombre de filtres appliqués ; par exemple, les filtres utilisés comme des lignes d’un tableau à structure libre</li><li>Utilisation de filtres complexes</li><li>Lignes ou colonnes de [postes statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) dans les tableaux de forme libre</li><li>Filtres appliqués aux lignes des tableaux à structure libre</li><li>Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des filtres</li></ul> | Si vos projets ne se chargent pas aussi rapidement que prévu, remplacez si possible certains filtres par des eVars.<br><br>Si vous utilisez continuellement des filtres et des mesures calculées pour les points de données importants dans le cadre de vos activités, envisagez d’améliorer votre implémentation afin de capturer plus directement ces points de données. Envisagez d’utiliser un gestionnaire de balises tel qu’Adobe Experience Platform Launch et les règles de traitement d’Adobe pour faciliter et accélérer les modifications de lʼimplémentation. |
| Capacité du centre de données | Capacité de création de comptes rendus des performances que vous et dʼautres clients partagez au sein dʼun centre de données Adobe. | Cela dépend du nombre de requêtes simultanées effectuées par votre entreprise et dʼautres entreprises au sein de votre centre de données. | Votre entreprise a droit à une capacité déterminée, et, si le système est peu sollicité, Adobe vous transférera une capacité supérieure à celle à laquelle vous avez droit. |



