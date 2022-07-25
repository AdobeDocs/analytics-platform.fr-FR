---
description: Explique les facteurs qui influencent la cohérence des mesures et du nombre d’adhésions à l’audience entre Real-time Customer Data Platform (plateforme de données clients en temps réel) et CJA.
title: Cohérence des mesures et du nombre d’adhérents à l’audience entre la plateforme CDP en temps réel et CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: cf4e2136f5ab4e0ed702820e52e9a62ea8251860
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---


# Cohérence des mesures et du nombre d’adhérents à l’audience entre la plateforme CDP en temps réel et CJA

Dans des scénarios réels, la cohérence des mesures et du nombre d’adhésions à l’audience dans Real-time Customer Data Platform (plateforme de données clients en temps réel) et Customer Journey Analytics (CJA) ne peut pas être garantie. Ce document explique pourquoi.

## Différences dans les configurations d’identité

La plateforme CDP en temps réel et CJA ne partagent pas la même définition d’une personne aujourd’hui. La plateforme des données clients en temps réel repose entièrement sur les informations figurant dans la variable [Graphique d’identités](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) pour créer un profil fusionné.

CJA peut être configuré pour utiliser [Analyse cross-canal](/help/connections/cca/overview.md) qui extrait les identifiants des jeux de données du lac de données et applique une logique personnalisée pour les lier.
À l’avenir, CJA pourra utiliser le graphique d’identités.

## Différences dans la configuration des jeux de données

Vous pouvez choisir de placer certaines données dans la plateforme de données clients en temps réel et d’autres dans CJA. souvent, les clients choisissent de placer plus de données historiques dans CJA qu’il n’est pertinent pour la plateforme de données clients en temps réel. D’autres jeux de données peuvent être plus pertinents pour la plateforme de données clients en temps réel que pour CJA.

## Différences dans la configuration du traitement

CJA permet une modification complète des données au moment de la requête, par exemple la combinaison de champs, la division des champs entre eux et d’autres manipulations telles que les inclusions/exclusions, les sous-chaînes, la déduplication des valeurs, la sessionisation et le filtrage au niveau des lignes.

La plateforme CDP en temps réel offre un ensemble différent d’outils de manipulation de données. Elle s’applique [stratégies de fusion](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) pour déterminer quelles données seront hiérarchisées et quelles données seront combinées afin de créer une vue unifiée d’une personne.

## Différences entre la durée de vie et l’ingestion des données

Même si les jeux de données de la plateforme de données clients en temps réel et de CJA sont identiques, la plateforme de données clients en temps réel ne peut conserver qu’une fenêtre d’historique très limitée. En revanche, CJA a probablement des années de données. En outre:

* Les clients CJA et CDP en temps réel peuvent définir des fenêtres de conservation personnalisées pour les données, indépendamment les uns des autres.

* La plateforme CDP en temps réel et CJA ont une logique différente pour l’ingestion de données. CJA ignore les enregistrements sans ID de personne ou horodatage et a des limites strictes au nombre d’enregistrements qu’un seul profil/personne peut avoir.

* Les clients de la plateforme de données clients en temps réel disposent de 7 jours d’accès aux données du lac, principalement pour faciliter l’intégration des données dans leur profil et pour les requêtes ad hoc.

* Il n’existe pas de TTL pour les données du lac pour les clients de CJA. Toutefois, les utilisateurs de CJA peuvent eux-mêmes définir une fenêtre de rétention personnalisée dans CJA lors de la création d’une connexion.

* Le magasin de profils dans la plateforme de données clients en temps réel permet d’utiliser des TTL configurables par le client. Les clients peuvent modifier ce délai d’activation pour qu’il reste dans les limites de leurs droits de licence.

## Différences dans la latence d’ingestion des données

CJa ne dispose pas encore des fonctionnalités en temps réel de la plateforme de données clients en temps réel. Par conséquent, la création de rapports CJA inclut une certaine latence avant que les données ne soient disponibles pour la création de rapports ou d’audiences. La plateforme CDP en temps réel traite les données par le biais de différents systèmes présentant une latence différente.
