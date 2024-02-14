---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 29c124da55842bcb9085059a9008f7a7d6baf44e
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 47%

---

# Notes de mise à jour actuelles d’Adobe Customer Journey Analytics (février 2024)

**Dernière mise à jour** : le jeudi 14 février 2024

Ces notes de mise à jour portent sur la période du jeudi 14 février 2024 au mardi 11 mars 2024. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Prévision de séries temporelles** | [Prévisionnel](../analysis-workspace/c-forecast/forecasting.md) est une nouvelle fonctionnalité d’Analysis Workspace utilisée pour prévoir une mesure standard ou calculée avec toute granularité temporelle prise en charge (horaire, quotidien, hebdomadaire, mensuel et annuel) pour les tableaux à structure libre et les graphiques en courbes. | 31 janvier 2024 | 21 février 2024 |
| **Rapports Media Analytics - Audience moyenne par minute (AMA)** | Le panneau Audience moyenne par minute est désormais disponible dans CJA. Les clients Media Analytics peuvent utiliser le panneau Audience moyenne par minute pour mieux comprendre la consommation moyenne de leur contenu. Lʼaudience moyenne par minute permet de comparer des programmes de toute longueur ou de tout genre. En outre, les clients peuvent comparer ou ajouter cette audience numérique moyenne par minute aux mesures moyennes par minute de la télévision linéaire. Ce panneau offre davantage de flexibilité pour mesurer l’audience moyenne pour des périodes personnalisées, ainsi que le moment où la classification de durée a été mise à jour après coup. |  | samedi 16 février 2024 |
| **Mesures de nombre de lignes pour les données de recherche et de profil** | Les mesures de nombre de lignes des jeux de données, configurées dans le cadre d’une connexion, incluent désormais les enregistrements ajoutés, ignorés ou supprimés des jeux de données de profil et de recherche. |  | jeudi 14 février 2024 |
| **Détection des robots Experience Edge** | [Détection de robots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) vous permet d’identifier les événements générés par le SDK Web, le SDK Mobile et l’API serveur comme étant générés par des araignées et des robots connus. | | 21 février 2024 |
| **Mesures d’utilisation** | L’interface des mesures d’utilisation indique l’utilisation des lignes ingérées et reportables sur toutes les connexions. Cette interface vous permet de déterminer si votre utilisation de Customer Journey Analytics est conforme aux conditions contractuelles. | mercredi 20 février 2024 | Début mars 2024 |
| **Adobe Product Analytics : Partager avec n’importe qui** | Permet de partager un lien en lecture seule avec des personnes qui n’ont pas accès à Product Analytics pour les projets d’Adobe Product Analytics. |  | 21 février 2024 |
| **Adobe Product Analytics : appliquer des mesures calculées** | Vous pouvez désormais accéder aux mesures calculées créées dans Analysis Workspace ou dans le créateur de mesures calculées dans la vue Tendances : Utilisation , ce qui vous permet de suivre les tendances et de comparer les mesures au fil du temps. |  | samedi 16 février 2024 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| Ajout de membres aux objets d’API Adobe | 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets d’API existants sans préavis ni modification du contrôle de version. Ces ajouts doivent constituer des modifications sans ruptures pour votre mise en œuvre. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API, afin que ces ajouts soient ignorés dans le traitement s’ils ne sont pas compris. Adobe ne supprimera pas de paramètres ni n’ajoutera de paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
