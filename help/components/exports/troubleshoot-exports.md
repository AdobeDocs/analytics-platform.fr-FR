---
description: Gestion des journaux des exportations existantes
keywords: Analysis Workspace
title: Résolution des problèmes d’exportation
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# Résolution des problèmes d’exportation

Lorsque vous [exportez des tables complètes d’Analysis Workspace vers des destinations cloud](/help/analysis-workspace/export/export-cloud.md), vous pouvez afficher l’état de ces exportations à partir de l’onglet [Exportations](/help/components/exports/manage-exports.md) et de l’onglet [Journaux](/help/components/exports/manage-export-logs.md). Les exportations ayant échoué affichent l’état [!UICONTROL **Failed**].

## Échecs et actions courants

Les exportations peuvent échouer pour diverses raisons. Le tableau suivant décrit quelques-unes des raisons les plus courantes, avec des actions que vous pouvez entreprendre pour remédier aux échecs :

| Motif de l’échec | Action suggérée | Informations supplémentaires |
|---------|----------|---------|
| Informations non valides sur le lieu ou le compte | Assurez-vous que vos informations d’identification et autres informations sont correctes pour le compte et l’emplacement cloud vers lequel vous exportez. | [ Configurez les comptes d’exportation cloud ](/help/components/exports/cloud-export-accounts.md) et [ configurez les emplacements d’exportation cloud ](/help/components/exports/cloud-export-locations.md). |
| Une dimension ou une mesure du rapport a été supprimée de la vue de données. | Contactez votre administrateur système pour savoir quels composants ont été supprimés de la vue de données. Vous devrez peut-être utiliser une vue de données différente dans votre exportation ou supprimer des composants de votre table qui ne sont plus disponibles. | [Exporter des rapports de Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md) |
| Limite de ligne dépassée | Selon votre type de licence, vous pouvez exporter un maximum de 3 millions, 30 millions, 150 millions ou 300 millions de lignes. Mettez à jour le tableau que vous exportez pour réduire le nombre total de lignes. | [Exporter des rapports de Customer Journey Analytics vers le cloud](/help/analysis-workspace/export/export-cloud.md) |
| Expiration planifiée de l’exportation | L’exportation planifiée que vous avez configurée a expiré. Mettez à jour l’expiration de l’exportation. | [Gérer les exportations](/help/components/exports/manage-exports.md) |
| Dimension non prise en charge | <p>Les dimensions qui répondent à tous les critères suivants ne sont pas prises en charge dans l’exportation de table complète :</p> <ul><li>A été créé à partir d’un champ qui fait partie d’un tableau d’objets</li><li>La persistance est activée<li>N’utilise pas de dimension de liaison</li> | <ul><li>[Utilisation de tableaux d’objets](/help/use-cases/object-arrays.md)</li><li>[Paramètres du composant de persistance](/help/data-views/component-settings/persistence.md)<li>[Utiliser des dimensions et des mesures de liaison en Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Une stratégie de gouvernance des données appliquée par votre organisation empêche l’exportation des composants de votre table. | Contactez votre administrateur système pour savoir quels composants ne peuvent pas être exportés. Supprimez les composants restreints avant l’exportation. | *Filtrer sur les stratégies de gouvernance des données dans les vues de données* dans la section [Étiquettes et stratégies](/help/data-views/data-governance.md) |

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
