---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5a4d9ad92de69c91d4cf8f4f400ede37470c3baa
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 47%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (avril 2025)

**Dernière mise à jour** : jeudi 16 avril 2025

Ces notes de mise à jour portent sur la période du 27 mars au vendredi 15 mai 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mises à jour de l’élément de ligne « Aucune valeur » sur les dimensions numériques** | Pour les dimensions numériques, cette mise à jour permet les actions suivantes :<ul><li>Utilisez l’élément de dimension « Aucune valeur » dans un segment.</li><li>Effectuer une répartition dans un rapport sur l’élément de ligne « Aucune valeur ».</li></ul> [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 27 mars 2025 |
| **Adobe Content Analytics** | Adobe Content Analytics permet d’examiner rapidement et facilement de grands volumes de données de contenu pour découvrir des tendances, repérer des anomalies, identifier la lassitude du contenu et obtenir des informations grâce à l’exposition du contenu.<p>Dès le départ, vous pouvez gagner du temps grâce aux modèles de création de rapports préconfigurés et aux nouvelles fonctionnalités telles que l’Inspecteur de ressources. Cette fonctionnalité vous permet non seulement de visualiser la ressource en ligne avec vos données, mais également d’ouvrir chaque ressource pour obtenir un résumé des détails, notamment les performances, les emplacements, les attributs, etc.<p>Vous pouvez examiner ce nouvel ensemble de données de contenu dans le cadre du parcours clientèle complet pour répondre à des questions commerciales importantes, évaluer les performances du contenu, améliorer la segmentation, identifier les opportunités d’optimisation et définir de nouvelles audiences pour l’activation.<p>Content Analytics est un module complémentaire de Customer Journey Analytics. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/content-analytics/content-analytics) |  | 27 mars 2025 |
| **Media Collection : mises à jour du connecteur Source d’Adobe pour le nouveau XDM de création de rapports multimédia** | Le connecteur source Analytics mappe automatiquement les données de médias en streaming dans Adobe Analytics aux mêmes champs utilisés par le SDK web. Auparavant, les données étaient mappées à la fois à l’ancien et au nouvel emplacement, mais seul le nouvel emplacement sera utilisé à l’avenir. [En savoir plus](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 31 mars 2025 |
| **Mise à jour des champs XDM pour la collecte de données Streaming Media dans Adobe Experience Platform** | Lors de la collecte de données Streaming Media dans Adobe Experience Platform, le groupe de champs `media.mediaTimed` ne doit plus être utilisé. Au lieu de cela, les clients doivent migrer vers le groupe de champs `mediaReporting`.<p>Pendant une période de transition de trois mois, l’ingestion des données sur les champs `media.mediaTimed` se poursuivra. Cependant, à la fin du mois de juillet 2025, les champs `the media.mediaTimed` seront entièrement obsolètes et ne seront plus visibles dans l’interface utilisateur du schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des champs `mediaReporting`.<p>Les clients qui ont implémenté le connecteur source Analytics pour collecter les données Streaming Media dans Platform avant le 22 avril 2025 doivent migrer leurs configurations existantes pour utiliser le nouveau groupe de champs. Cette migration doit être terminée d’ici la fin juillet 2025. Contactez les services Adobe Consulting ou l’équipe du compte pour obtenir une assistance sur la migration. Aucune action n’est requise de la part des clients qui implémentent le connecteur source Analytics après le 22 avril 2025. |  | mercredi 22 avril 2025 |
| **Modification de la terminologie : « Filtres » en « Segments »** | Auparavant, Adobe Customer Journey Analytics appelait les segments « filtres ». Cette terminologie a été mise en conformité avec Adobe Analytics. Les « filtres » sont désormais appelés « segments ». (Bien entendu, les filtres de recherche sont toujours appelés « filtres ».) L’interface utilisateur a été mise à jour et la documentation est en cours de mise à jour. |  | jeudi 16 avril 2025 |
| **Assemblage : récupération des identifiants persistants et temporaires de XDM IdentityMap** | Cette fonctionnalité prend en charge l’utilisation d’identités stockées dans le mappage d’identité XDM dans le processus de groupement. IdentityMap peut être utilisé pour l’ID persistant ou temporaire du groupement basé sur les champs et peut être utilisé pour l’ID persistant du groupement basé sur les graphiques.  Vous pouvez utiliser un espace de noms spécifique ou une identité principale à partir du mappage d’identité. (Lien vers la documentation à suivre) |  | samedi 25 avril 2025 |
| **Mesures et dimensions partagées entre les vues de données** | Permet d’appliquer des paramètres de dimension et de mesure à plusieurs vues de données. Les modifications apportées à une dimension ou à une mesure partagée s’appliquent à toutes les instances de cette dimension ou mesure dans toutes les vues de données applicables. Cette interface permet aux administrateurs Customer Journey Analytics de gérer plus facilement les composants lorsque de nombreuses vues de données sont utilisées. (Lien vers la documentation à suivre) |  | jeudi 30 avril 2025 |


## Correctifs dans Customer Journey Analytics

**Admin Console** : AN-370228
**Analysis Workspace**: AN-371933; AN-371933; AN-371979
**Audiences** : AN-373032
**Paramètres des composants** : AN-367400
**Champs dérivés** : AN-370614 ; AN-370959
**Emplacements d’exportation** : AN-371670
**Exportation de table complète** : AN-360492 ; AN-369204 ; AN-370755 ; AN-372294 ; AN-372363 ; AN-372754 ; AN-373040 ; AN-373081 ; AN-373168
**Zone de travail de Parcours** : AN-373294
**Application mobile** : AN-363169 ; AN-368496 ; AN-371766
**Utilisation du produit** : AN-369501
**Rapports** : AN-369085 ; AN-371094 ; AN-372580


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | | |

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
