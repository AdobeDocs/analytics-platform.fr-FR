---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: dcd7484a98363a6a818b59e9e183f699eecc1ed4
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 79%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (mai 2024)

**Dernière mise à jour** : mercredi 21 mai 2024

Ces notes de mise à jour portent sur la période du 15 mai 2024 à juin 2024. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Extension BI** | L’extension BI permet à SQL d’accéder aux vues de données que vous avez définies dans Customer Journey Analytics. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 15 mai 2024 |
| **Les audiences sont publiées dans une nouvelle section « Audiences » dans Experience Platform.** | Les audiences qui sont publiées à partir de Customer Journey Analytics sont désormais disponibles dans la nouvelle section « Audiences » d’Adobe Experience Platform.<p>Auparavant, les audiences qui étaient publiées à partir de Customer Journey Analytics étaient disponibles dans Experience Platform dans la section « Segments ».</p><p>Cette amélioration s’accompagne des avantages suivants :</p><ul><li>Les audiences n’ont plus un délai d’une heure avant d’apparaître dans Experience Platform ; elles sont disponibles quelques secondes après leur publication.</li><li>Les audiences peuvent être triées dans Experience Platform à l’aide de la colonne « Origine », qui affiche l’application à partir de laquelle l’audience a été publiée à l’origine.</li><li>Les options de filtrage et de tri d’Experience Platform vous permettent de trouver plus rapidement les audiences pertinentes.</li></ul> <p>(Mise à jour du lien vers la documentation à suivre)</p> |  | Fin mai à début juin 2024 |
| **Assistant IA pour Customer Journey Analytics** | Permet de poser des questions en langage naturel dans l’interface utilisateur de Customer Journey Analytics et d’obtenir des réponses en fonction de la documentation du Customer Journey Analytics. <p>(Mise à jour du lien vers la documentation à suivre)</p> | | 30 mai 2024 |
| **Médias en streaming : envoyer des données web à l’Edge Network d’Adobe Experience Platform avec le SDK web** | Vous pouvez désormais utiliser le SDK web d’Adobe Experience Platform pour envoyer des données web de médias en streaming à l’Edge Network d’Adobe Experience Platform, ce qui vous permet de créer des campagnes plus personnalisées et de fournir un contenu plus personnalisé, entraînant un plus grand nombre de données de suivi sur lesquelles générer des rapports.<p>Avec cette amélioration, vous disposez d’une méthode de collecte unifiée pour les implémentations web couvrant toutes les solutions de la plateforme, notamment Customer Journey Analytics, RT-CDP, AJO et le transfert d’événements. Auparavant, la seule manière d’envoyer des données web de médias en flux continu à l’Edge Network était d’utiliser l’API Media Edge. <p>[En savoir plus](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | jeudi 29 mai 2024 |
| **Champs dérivés - Fonction mathématique** | Permet d’effectuer des opérations mathématiques simples dans les vues de données pour répondre aux questions sur vos utilisateurs et utilisatrices. Vous pouvez, par exemple, combiner des produits, des garanties et des recettes d’expédition. <p>(Mise à jour du lien vers la documentation à suivre)</p> | | 5 juin 2024 |
| **Partage des comptes et des emplacements utilisés pour l’exportation et l’importation** | Les utilisateurs peuvent désormais mettre les comptes et emplacements qu’ils créent à la disposition de tous les utilisateurs de leur entreprise. Seuls les propriétaires de compte et d’emplacement et les administrateurs système peuvent modifier et supprimer des comptes et des emplacements.<p>Auparavant, les comptes et emplacements ne pouvaient être utilisés que par l’utilisateur qui les avait créés.</p><p>Ces paramètres sont disponibles lorsque les utilisateurs configurent des comptes d’exportation dans le cloud et configurent des emplacements d’exportation dans le cloud.</p> <p>(Mise à jour du lien vers la documentation à suivre)</p> | jeudi 12 juin 2024 | lundi 30 juin 2024 |
| **Nouvelle documentation pour la mise à niveau d’Adobe Analytics vers Customer Journey Analytics** | Pour les entreprises qui passent d’Adobe Analytics à Customer Journey Analytics, il existe plusieurs options de mise à niveau et de nombreux points à prendre en compte en fonction de la mise en œuvre actuelle d’Adobe Analytics et des objectifs à long terme de l’entreprise. De nouvelles ressources documentaires sont désormais disponibles pour vous aider à mieux comprendre ce qui suit :<ul><li>Les différentes voies de mise à niveau existantes</li><li>Les voies de mise à niveau disponibles en fonction de l’implémentation actuelle d’Adobe Analytics par l’entreprise</li><li>Les avantages et les inconvénients de chaque voie de mise à niveau</li><li>Guide étape par étape pour chaque voie de mise à niveau</li><li>Considérations relatives au traitement des données historiques</li></ul>[Commencer avec la mise à niveau vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponible maintenant |
| **Nouvelle documentation sur [Cas d’utilisation d’export de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-usecases/data-export/overview)** | Cette nouvelle section décrit les cas d’utilisation d’export de données, tels que<ul><li>Sauvegarde de données</li><li>Validation des données</li><li>Lac de données, entrepôt de données ou outils BI</li><li>Préparation à l’IA/ML</li></ul> et comment les mettre en œuvre à l’aide des fonctionnalités d’Experience Platform et de Customer Journey Analytics. | | Disponible maintenant |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-342309 ; AN-342312 ; AN-345267 ; AN-345909 ; AN-346016 ; AN-346049 ; AN-346052 ; AN-346287 ; AN-346624 ; AN-347919

## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

{style="table-layout:auto"}

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2024](/help/release-notes/2024.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
