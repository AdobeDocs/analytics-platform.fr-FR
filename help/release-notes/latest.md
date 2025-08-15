---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f959ac6c12280f745a986237c39d7fb1e7af5aa7
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 19%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (août 2025)

**Dernière mise à jour** : vendredi 14 août 2025


Ces notes de mise à jour couvrent la période du 13 août au 16 septembre 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualisation des cartes** | La visualisation des cartes est une visualisation d’Analysis Workspace qui vous permet de créer une carte visuelle de n’importe quelle mesure (y compris les mesures calculées). Il est utile pour identifier et comparer des données de mesure dans différentes régions géographiques.<p>Auparavant, la visualisation des cartes n’était disponible que dans Adobe Analytics.</p><p>La visualisation des cartes dans Customer Journey Analytics contient les améliorations suivantes par rapport à la visualisation des cartes dans Adobe Analytics :</p><ul><li>Utilisez n’importe quel segment de votre vue de données comme source de données.</li><li>Précision jusqu’à un seul mètre en configurant la dimension dans votre vue de données.</li><li>Un nouvel outil de sélection vous permet de créer un segment, une audience, une tendance ou une répartition à partir de n’importe quelle zone sélectionnée dans la visualisation.</li></ul><p>Pour plus d’informations, voir [Carte](/help/analysis-workspace/visualizations/map.md).</p> | jeudi 13 août 2025 | mardi 25 août 2025 |
| **Création de rapports en temps réel** | Les rapports en temps réel dans Customer Journey Analytics affichent et mettent à jour en temps réel les données et les visualisations au sein d’un ou de plusieurs panneaux dans Analysis Workspace. | | samedi 15 août 2025 |
| **Modèles B2B** | Si vous disposez d’une licence pour Customer Journey Analytics B2B edition, les modèles B2B supplémentaires suivants sont désormais disponibles dans l’interface utilisateur des modèles Adobe : <ul><li>Vue d’ensemble de l’engagement des comptes B2B</li><li>Vue d’ensemble de l’engagement des opportunités B2B</li><li>Activité du groupe d’achat B2B</li></ul><p>(Lien vers la documentation à suivre.)</p> |  | samedi 15 août 2025 |
| **Les projets téléchargés au format PDF sont enregistrés sur votre poste de travail.** | Lors du téléchargement d’un projet as a PDF, le PDF est téléchargé dans le dossier des téléchargements de votre station de travail. <p>Auparavant, le téléchargement d’un projet en tant que PDF lançait le PDF dans un nouvel onglet du navigateur avec une URL unique.</p><p>Pour plus d’informations, voir [Télécharger des projets et des données](/help/analysis-workspace/export/download-send.md).</p> |  | mardi 25 août 2025 |
| **Prise en charge des schémas ad hoc** | Les [schémas ad hoc](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/ad-hoc) sont utilisés dans divers workflows d’ingestion de données pour Experience Platform, notamment dans l’ingestion de fichiers CSV et dans la création de certains types de connexions sources. <p>Cette fonctionnalité permet la prise en charge de l’utilisation de schémas ad hoc dans Customer Journey Analytics. Dans le cadre de la définition d’une connexion, vous pouvez désormais sélectionner un jeu de données basé sur un schéma ad hoc et utiliser les données dans vos projets de vue de données et d’espace de travail.</p> <p>(Lien vers la documentation à suivre.)</p> |  | vendredi 28 août 2025 |
| **Groupement dans les connexions** | Simplifie l’assemblage Customer Journey Analytics. Au lieu de dupliquer un jeu de données et d’appliquer un groupement sur le jeu de données dupliqué, le groupement est désormais effectué sur l’ingestion de données dans Customer Journey Analytics, ce qui supprime l’exigence de jeux de données et de schémas dupliqués. <p>En outre, au lieu d’avoir à demander le groupement par le biais du service clientèle, vous pouvez désormais lancer le groupement vous-même à partir d’une interface utilisateur de connexions mise à jour.</p><p> *Les dates de publication communiquées précédemment sont repoussées en raison d’efforts supplémentaires requis. Les nouvelles dates de publication se chevauchent avec la saison des fêtes, ce qui introduit des contraintes de publication supplémentaires. Un déploiement échelonné est maintenant prévu pour garantir la stabilité et réduire au minimum les perturbations pendant la période de vacances.*</p> | Fin octobre 2025 | Fin janvier 2026 |
| **Extension de la limite des clés de recherche** | En fonction de votre package Customer Journey Analytics, vous pouvez désormais avoir jusqu’à 1 milliard de clés uniques au maximum dans un jeu de données de recherche. <p>Pour plus d’informations, voir [Limites de transfert de données](/help/technotes/guardrails.md#data-transfer-limits) dans la documentation de Customer Journey Analytics [Mécanismes de sécurisation](/help/technotes/guardrails.md).</p> |  | samedi 29 août 2025 |
| **Création de mesures et de dimensions en fonction de champs de mappage définis par l’utilisateur à partir du schéma Platform** | Les champs de mappage définis par l’utilisateur que vous définissez dans votre schéma Experience Platform peuvent désormais être utilisés dans Customer Journey Analytics.<p>Vous pouvez utiliser les champs de mappage suivants lors de la création de mesures et de dimensions dans Customer Journey Analytics :</p><ul><li>Chaîne en chaîne</li><li>Chaîne en entier</li></ul><p>(Lien vers la documentation à suivre.)</p><p>Pour plus d’informations sur les champs de mappage dans Experience Platform, voir [ Définir des champs de mappage dans l’interface utilisateur ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/map).</p> |  | Fin août 2025 |
| **Les projets supprimés sont immédiatement indisponibles par URL et sont supprimés des diffusions planifiées** | Les projets supprimés sont immédiatement supprimés des diffusions planifiées et ne sont plus accessibles par leur URL.<p>Auparavant, les projets étaient inclus dans les diffusions planifiées et étaient accessibles avec leur URL pendant 60 jours après leur suppression.</p><p>Pour plus d’informations sur la suppression de projets, voir [Présentation des projets](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Fin août 2025 |
| **Streaming Media : mise à jour des champs XDM pour la collecte de données Streaming Media dans Adobe Experience Platform** | Lors de la collecte de données des médias en streaming dans Adobe Experience Platform, les chemins d’accès aux champs XDM affichés dans la section « Chemin d’accès au champ XDM » de la documentation des paramètres des médias de streaming ne doivent plus être utilisés. Au lieu de cela, les clients qui ont implémenté le connecteur source Analytics pour collecter des données de médias en flux continu dans Platform avant le 9 mai 2025 doivent migrer leurs configurations existantes vers les chemins d’accès aux champs mediaReporting, comme indiqué sous l’en-tête « Chemin d’accès au champ XDM de création de rapports » de la documentation des paramètres de médias en flux continu.<p> Ces chemins d’accès aux champs se trouvent sur les pages suivantes et sont marqués comme « Obsolètes » : [Paramètres audio et vidéo](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Paramètres d’annonce](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/ad-parameters), [Paramètres de chapitre](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/chapter-parameters), [Paramètres d’état du lecteur](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/player-state-parameters) et [Paramètres de qualité](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/quality-parameters). (Aucune action n’est requise de la part des clients qui implémentent le connecteur source Analytics après le 9 mai 2025 et qui utilisent déjà uniquement les chemins XDM mediaReporting.)</p><p>L’ingestion des données sur les chemins d’accès aux champs XDM obsolètes se poursuivra jusqu’à la fin octobre 2025. Passé ce délai, les chemins d’accès aux champs obsolètes seront entièrement supprimés et ne seront plus visibles dans l’interface utilisateur du schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des chemins d’accès aux champs mediaReporting.</p><p>Pour plus d’informations, consultez [Migration d’une implémentation du connecteur Source Analytics vers des champs de streaming multimédia XDM mis à jour](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Contactez les services Adobe Consulting ou l’équipe du compte pour obtenir une assistance sur la migration. </p> |  | Octobre 2025 |

## Correctifs dans Customer Journey Analytics

**Analysis Workspace** : AN-389683 ; AN-389534 ; AN-389207 ; AN-389066 ; AN-388687 ; AN-388478 ; AN-387089 ; AN-384865 ; AN-384560 ; AN-383486 ; AN-365768 ; AN-351639 ; AN-
**Composants** :
**Content Analytics**:
**Analyse guidée** : AN-384426
**Platform** : AN-384410
**Report Builder**: AN-389336; AN-382775
**Rapports** :
**Segmentation** :
**Mesures et dimensions partagées** :
**Autre** : AN-388222 ; AN-384898 ; AN-387169


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
