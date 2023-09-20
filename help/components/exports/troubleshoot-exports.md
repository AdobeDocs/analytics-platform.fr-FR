---
description: Gestion des journaux des exportations existantes
keywords: Analysis Workspace
title: Résolution des problèmes d’exportation
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 24e9e4151360597b099a7985a4566b3ca7bfff00
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 3%

---

# Résolution des problèmes d’exportation

Lorsque vous [exporter des tables complètes d’Analysis Workspace vers des destinations cloud ;](/help/analysis-workspace/export/export-cloud.md), vous pouvez afficher l’état de ces exportations à partir de la [Onglet Exportations](/help/components/exports/manage-exports.md) et depuis le [Onglet Journaux](/help/components/exports/manage-export-logs.md). Les exportations ayant échoué affichent un état [!UICONTROL **En échec**].

Les exportations peuvent échouer pour diverses raisons. Le tableau suivant décrit quelques-unes des raisons les plus courantes, avec des actions que vous pouvez entreprendre pour remédier aux échecs :

| Motif de l’échec | Action suggérée | Informations supplémentaires |
|---------|----------|---------|
| Emplacement ou informations de compte non valides | Assurez-vous que vos informations d’identification et autres informations sont correctes pour le compte et l’emplacement cloud vers lequel vous exportez. | [Configuration des comptes d’exportation cloud](/help/components/exports/cloud-export-accounts.md) et [Configuration des emplacements d’exportation cloud](/help/components/exports/cloud-export-locations.md). |
| Une dimension ou une mesure du rapport a été supprimée de la vue de données. | Contactez votre administrateur système pour savoir quels composants ont été supprimés de la vue de données. Vous devrez peut-être utiliser une vue de données différente dans votre exportation ou supprimer des composants de votre table qui ne sont plus disponibles. | [Exportation des données de Customer Journey Analytics dans le cloud](/help/analysis-workspace/export/export-cloud.md) |
| Une stratégie de gouvernance des données appliquée par votre organisation empêche l’exportation des composants de votre table. | Contactez votre administrateur système pour savoir quels composants ne peuvent pas être exportés. Supprimez les composants restreints avant l’exportation. | *Filtrage des stratégies de gouvernance des données dans les vues de données* dans [Étiquettes et stratégies](/help/data-views/data-governance.md) |