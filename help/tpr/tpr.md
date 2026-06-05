---
title: Rapports sur la population totale
description: Utilisez les rapports de population totale dans Customer Journey Analytics pour analyser les profils et les comptes dans vos jeux de données, indépendamment de l’activité des événements ou des périodes du panneau.
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 774ac76b0a49d8172b31dc97563c13debb0858a7
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---


# Rapports sur la population totale

Les rapports sur la population totale permettent d’analyser et de générer des rapports sur les entités définies dans les jeux de données de profil et de recherche et au-delà des séries temporelles d’événements des jeux de données d’événement. Cette fonctionnalité active de nouvelles classes de requêtes, de mesures et de définitions d’audience qui reflètent l’étendue complète de la base de clients d’une entreprise.

Customer Journey Analytics s’articule autour d’événements. Chaque mesure, chaque visualisation, chaque panneau et chaque rapport est ancré à une période et à des événements qui se produisent au cours de cette période. Vous posez les questions suivantes sur les solutions :

| Question | Événement | Période |
|---|---|---|
| Combien de personnes ont effectué un achat la semaine dernière ? | Achat | la semaine dernière |
| Combien de comptes ont visité la page de tarification au T1 ? | visite | T1 |

La période du panneau Espace de travail filtre les données. Vos dimensions et mesures décrivent ce qui s’est passé au cours de cette période.

Mais toutes les questions auxquelles votre entreprise doit répondre ne portent pas sur ce qui s&#39;est passé. Parfois, il faut connaître sa population.

| Question | Événement | Période |
|---|---|---|
| Combien de clients actifs avons-nous en ce moment ? | S.O. | S.O. |
| Combien y a-t-il de comptes dans notre base de données ? | S.O. | S.O. |
| Combien de nos membres n&#39;ont pas effectué d&#39;achat au cours des 30 derniers jours? | S.O. | 30 derniers jours |

Ces questions ne portent pas sur les événements, mais sur les personnes et les comptes qui existent, que ces personnes ou comptes aient fait ou non quelque chose récemment.

Les rapports sur la population totale introduisent une nouvelle classe de mesures qui génèrent des rapports sur les données de profil. Ces données de profil, qui peuvent contenir des personnes et des comptes, dans vos jeux de données de profil sont indépendantes de la période d’un panneau. Grâce aux rapports sur la population totale, vous pouvez combiner des mesures basées sur la population et des mesures basées sur des événements dans la même analyse, ce qui vous permet d’obtenir une vue plus complète de la clientèle et de ce qu’elle a fait.

Les rapports sur la population totale permettent à Customer Journey Analytics de créer des rapports sur toutes les entités définies dans les jeux de données de profil et de recherche, quelle que soit l’activité d’événement. Ces rapports incluent les éléments suivants :

* **Requêtes basées sur les profils** : analysez les attributs (quels que soient les événements) des profils (toutes les personnes, tous les comptes, toutes les opportunités et tous les groupes d’achats).
* **Profil moins requêtes d’événement** : identifiez les profils (toutes les personnes, tous les comptes, toutes les opportunités et tous les groupes d’achats) qui n’ont pas effectué d’action ou d’expérience spécifique pendant la période de création de rapports.
* **Recherches partagées** : prenez en charge la réutilisation des jeux de données de recherche sur plusieurs entités afin de réduire les coûts d’ingestion et d’améliorer les performances.

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## Mesures de reporting de la population totale

Les mesures de rapports sur la population totale se comportent différemment des mesures généralement utilisées dans Customer Journey Analytics :

* Les mesures de reporting de la population totale ne sont pas liées à la période du panneau. Une mesure de reporting de population totale telle que **[!UICONTROL Nombre total de personnes (profil)]** renvoie la population actuelle du jeu de données de votre profil, quelle que soit la période appliquée au panneau. Les filtres de date et les comparaisons de périodes n’affectent pas les mesures de rapports de population totale de la même manière que ces filtres et comparaisons affectent les mesures d’événement.
* Le compte rendu des performances de la population totale nécessite un jeu de données de profil sur la connexion. Les mesures de rapports sur la population totale n’apparaissent que lorsque votre connexion inclut au moins un jeu de données de profil ainsi qu’au moins un jeu de données d’événement. Les connexions avec uniquement des jeux de données d’événement continuent à fonctionner exactement comme auparavant et n’affichent pas les mesures de rapports sur la population totale.

Dans Workspace, les mesures de population totale sont signalées par une icône distincte (à déterminer) afin que vous puissiez rapidement identifier les mesures qui respectent la période du panneau et celles qui ne le respectent pas. Il est possible d’utiliser les mesures de population totale avec les mesures d’événement dans la plupart des cas, mais les types de visualisation qui dépendent de séquences d’événement (comme Abandon et Flux) ne sont pas pris en charge.

### Mesures de reporting de la population totale standard

Par défaut, le système inclut trois mesures de rapports sur la population totale standard, disponibles sur toute vue de données dont la connexion inclut un jeu de données de profil :

* **Nombre total de personnes (profil)** : nombre total de personnes dans le jeu de données de profil.
* **Nombre total de comptes (profil)** : nombre total de comptes dans le jeu de données de profil. [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **Nombre total de personnes (Profil + Événement)** : nombre d’unions combinant des personnes de portée profil avec des personnes de portée événement.

Vous pouvez également créer des mesures personnalisées avec l’une des trois portées à l’aide des champs de vos jeux de données de profil.

## Exigences, conditions préalables et considérations

Pour que les rapports sur l’ensemble de la population fonctionnent correctement, les conditions préalables, les exigences et les considérations doivent être prises en compte.

### Exigences de connexion

Pour une connexion afin de prendre en charge les rapports sur la population totale :

* Au moins un jeu de données d’événement est requis pour la connexion. Les connexions de profil uniquement ne sont pas prises en charge.
* Au moins un jeu de données de profil doit être ajouté à la connexion. Les mesures de rapports sur la population totale n’apparaissent pas dans les vues de données créées sur des connexions qui contiennent uniquement des données d’événement.
* Les recherches partagées doivent être configurées pour chaque jeu de données de profil. Les recherches partagées définissent la manière dont chaque jeu de données de profil est joint aux événements dans votre connexion en spécifiant la clé correspondante, l’espace de noms (pour les champs de mappage d’identité) et le chemin de jointure.

#### Configuration du jeu de données de profil

Lorsqu’un jeu de données de profil est ajouté à une connexion, Customer Journey Analytics renseigne une configuration de recherche partagée par défaut en fonction du type de jeu de données :

* Pour les jeux de données de profil de personne : la valeur par défaut est match-by-container, définie sur [!UICONTROL Personne], avec le mappage d’identité comme champ clé. Vous pouvez modifier cette valeur par défaut. Par exemple, pour choisir un espace de noms spécifique dans le mappage d’identités plutôt que dans la clé primaire. Ou pour spécifier un espace de noms secondaire dans les cas où le premier espace de noms n’est pas renseigné (ce qui est commun aux jeux de données groupés).
* Pour les jeux de données de profil de compte {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} : la valeur par défaut est match-by-container définie sur [!UICONTROL Account] (ou [!UICONTROL Global Account], si les comptes globaux sont activés sur la connexion). Le champ Compte peut être un identifiant unique ou un mappage d’identités. Lorsque le champ de compte est un mappage d’identités, vous sélectionnez l’espace de noms à utiliser.

Vous pouvez configurer plusieurs recherches partagées sur un seul jeu de données de profil afin de prendre en charge plusieurs chemins de jointure vers vos événements. Lorsque la même carte des identités est utilisée comme champ de clé dans plusieurs recherches partagées, les sélections d’espaces de noms doivent être cohérentes.

### Exigences relatives aux vues de données

Pour que les mesures de rapports sur la population totale fonctionnent correctement sur une vue de données :

* La connexion doit inclure un jeu de données de profil (voir [Exigences de connexion](#connection-requirements)). Si vous supprimez le dernier jeu de données de profil restant d’une connexion, les mesures de rapports sur la population totale ne sont pas disponibles sur les vues de données créées à partir de celle-ci.
* [Les segments au niveau de la vue de données](/help/data-views/create-dataview.md#settings-segments) ne doivent pas être explicites quant à l’événement. Si un segment appliqué directement à la vue de données est défini entièrement en termes de conditions de portée d’événement (par exemple, `hit where page = X`), la création de rapports sur la population totale n’est pas possible sur cette vue de données. Avant de se fier aux mesures de rapports sur la population totale, vérifiez que tous les segments de niveau de vue de données sont compatibles avec les rapports de portée de profil.
* La portée de la mesure doit être correctement définie. Lors de la création d’un composant de mesure personnalisé dans le créateur de vues de données, sélectionnez la portée appropriée (événement, profil ou profil + événement) en fonction du jeu de données du champ et du comportement de la mesure. L’étendue ne peut pas être modifiée une fois que la mesure est utilisée dans des audiences ou des rapports récurrents sans rompre ces dépendances.

### Compatibilité Workspace

Les mesures de rapports sur la population totale peuvent être utilisées avec les mesures basées sur un événement dans la plupart des contextes Workspace : [tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), [ligne](/help/analysis-workspace/visualizations/line.md), [barre](/help/analysis-workspace/visualizations/bar.md) et [barre horizontale](/help/analysis-workspace/visualizations/horizontal-bar.md) visualisations, [tableaux de cohortes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) lorsqu’elles sont configurées correctement, etc. Certains types de visualisation ne sont pas pris en charge, car ils dépendent intrinsèquement des séquences d’événement :

* [Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [Flux](/help/analysis-workspace/visualizations/c-flow/flow.md)
* types de visualisation supplémentaires non pris en charge à confirmer avant la publication.

Lorsque vous ajoutez une mesure de rapports sur la population totale à une visualisation non prise en charge, Workspace indique que la mesure ne peut pas être utilisée dans ce contexte.

### Considérations relatives à l’audience

Les audiences créées à partir des mesures de rapports sur la population totale dépendent des mesures qui restent présentes dans la vue de données :

* Une audience récurrente qui utilise une mesure de reporting de population totale échoue et passe à un état ERREUR si la mesure de reporting de population totale est supprimée de la vue de données.
* L’interface de Customer Journey Analytics empêche la suppression d’une mesure tandis qu’une audience récurrente active dépend de la mesure et affiche des conseils sur la dépendance avant que vous ne confirmiez la suppression.

### Autorisations

À confirmer : toutes les exigences d’accès aux rôles ou aux fonctionnalités de l’organisation IMS ou du profil de produit du client avant que les mesures de rapports sur la population totale ne soient visibles. Ceci vaut la peine d&#39;être signalé au PM avant la publication.
