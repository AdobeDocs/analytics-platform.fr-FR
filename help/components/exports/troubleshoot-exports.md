---
description: Gestion des journaux des exportations existantes
keywords: Analysis Workspace
title: Résolution des problèmes d’exportation
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 3252a41f5ee1f439a3f233b06a8be1fdf6150234
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 7%

---

# Résolution des problèmes d’exportation

{{release-limited-testing}}

Lorsque vous [exporter des tables complètes d’Analysis Workspace vers des destinations cloud ;](/help/analysis-workspace/export/export-cloud.md), vous pouvez afficher l’état de ces exportations à partir de la [Onglet Exportations](/help/components/exports/manage-exports.md) et depuis le [Onglet Journaux](/help/components/exports/manage-export-logs.md). Les exportations ayant échoué affichent un état [!UICONTROL **En échec**].

## Échecs et actions courants

Les exportations peuvent échouer pour diverses raisons. Le tableau suivant décrit quelques-unes des raisons les plus courantes, avec des actions que vous pouvez entreprendre pour remédier aux échecs :

| Motif de l’échec | Action suggérée | Informations supplémentaires |
|---------|----------|---------|
| Emplacement ou informations de compte non valides | Assurez-vous que vos informations d’identification et autres informations sont correctes pour le compte et l’emplacement cloud vers lequel vous exportez. | [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md) et [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md). |
| Une dimension ou une mesure du rapport a été supprimée de la vue de données. | Contactez votre administrateur système pour savoir quels composants ont été supprimés de la vue de données. Vous devrez peut-être utiliser une vue de données différente dans votre exportation ou supprimer des composants de votre table qui ne sont plus disponibles. | [Exportation des rapports des Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md) |
| Limite de ligne dépassée | Selon votre type de licence, vous pouvez exporter un maximum de 3 millions, 30 millions, 150 millions ou 300 millions de lignes. Mettez à jour le tableau que vous exportez pour réduire le nombre total de lignes. | [Exportation des rapports des Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md) |
| Expiration planifiée de l’exportation | L’exportation planifiée que vous avez configurée a expiré. Mettez à jour l’expiration de l’exportation. | [Gestion des exportations](/help/components/exports/manage-exports.md) |
| Dimension non prise en charge | <p>Les dimensions qui répondent à tous les critères suivants ne sont pas prises en charge dans l’exportation de table complète :</p> <ul><li>A été créé à partir d’un champ qui fait partie d’un tableau d’objets</li><li>La persistance est activée<li>N’utilise pas de dimension de liaison</li> | <ul><li>[Utilisation de tableaux d’objets](/help/use-cases/object-arrays.md)</li><li>Paramètres des composants : [persistance](/help/data-views/component-settings/persistence.md)<li>[Utilisation des dimensions et des mesures de liaison dans Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Une stratégie de gouvernance des données appliquée par votre organisation empêche l’exportation des composants de votre table. | Contactez votre administrateur système pour savoir quels composants ne peuvent pas être exportés. Supprimez les composants restreints avant l’exportation. | *Filtrage des stratégies de gouvernance des données dans les vues de données* dans [Étiquettes et stratégies](/help/data-views/data-governance.md) |

## Pour ce faire, contactez l’assistance clientèle d’Adobe

Si vous continuez à rencontrer des problèmes, contactez l’assistance clientèle d’Adobe. Lorsque vous contactez l’assistance clientèle au sujet d’un échec d’exportation, assurez-vous que les informations suivantes sont disponibles :

* Nom de l’export

* ID d’exportation

* ID d’instance

* Nom de la vue de données

* Emplacement

* Compte

* Connexion

* Nom de la société
