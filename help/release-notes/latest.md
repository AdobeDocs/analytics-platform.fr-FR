---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a54029648c9295e7a81243cb44e8fd1a85db294a
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 98%

---

# Notes de mise à jour de la version actuelle d’Adobe Customer Journey Analytics (août 2025)

**Dernière mise à jour** : 14 août 2025


Ces notes de mise à jour portent sur la période du 13 août au 16 septembre 2025. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualisation des cartes** | La visualisation des cartes est une visualisation d’Analysis Workspace qui permet de créer une carte visuelle de n’importe quelle mesure (y compris les mesures calculées). Elle s’avère utile pour identifier et comparer les données de mesure de différentes régions géographiques.<p>Auparavant, la visualisation des cartes n’était disponible que dans Adobe Analytics.</p><p>La visualisation des cartes dans Customer Journey Analytics contient les améliorations suivantes par rapport à la visualisation des cartes dans Adobe Analytics :</p><ul><li>Utilisation de n’importe quel segment de votre vue de données comme source de données.</li><li>Précision jusqu’à un mètre en configurant la dimension dans votre vue de données.</li><li>Nouvel outil de sélection permettant de créer un segment, une audience, une tendance ou une répartition à partir de n’importe quelle zone sélectionnée dans la visualisation.</li></ul><p>Pour plus d’informations, consultez la section [Carte](/help/analysis-workspace/visualizations/map.md).</p> | 13 août 2025 | 25 août 2025 |
| **Modèles B2B** | Si vous disposez d’une licence pour Customer Journey Analytics B2B Edition, les modèles B2B supplémentaires suivants sont désormais disponibles dans l’interface d’utilisation des modèles Adobe : <ul><li>Vue d’ensemble de l’engagement des comptes B2B</li><li>Vue d’ensemble de l’engagement des opportunités B2B</li><li>Activité du groupe d’achat B2B</li></ul><p>Pour plus d’informations, voir [Modèles B2B](/help/analysis-workspace/templates/use-templates.md#b2b-templates) dans [Utiliser des modèles](/help/analysis-workspace/templates/use-templates.md).</p> |  | 15 août 2025 |
| **Les projets téléchargés au format PDF sont enregistrés sur votre poste de travail.** | Lors du téléchargement d’un projet au format PDF, le fichier est enregistré dans le dossier des téléchargements de votre poste de travail. <p>Auparavant, le téléchargement d’un projet au format PDF ouvrait le fichier PDF dans un nouvel onglet du navigateur avec une URL unique.</p><p>Pour plus d’informations, consultez la section [Téléchargement de projets et de données](/help/analysis-workspace/export/download-send.md).</p> |  | 25 août 2025 |
| **Prise en charge des schémas ad hoc** | Les [schémas ad hoc](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/tutorials/ad-hoc) sont utilisés dans plusieurs workflows d’ingestion de données différents pour Experience Platform, notamment dans l’ingestion de fichiers CSV et dans la création de certains types de connexions sources. <p>Cette fonctionnalité permet la prise en charge de l’utilisation de schémas ad hoc dans Customer Journey Analytics. Dans le cadre de la définition d’une connexion, vous pouvez désormais sélectionner un jeu de données basé sur un schéma ad hoc et utiliser les données dans vos projets de vue de données et d’espace de travail.</p> <p>(Lien vers la documentation à suivre.)</p> |  | 18 septembre 2025 (version initialement prévue pour le 28 août 2025) |
| **Extension de la limite des clés de recherche** | En fonction de votre package Customer Journey Analytics, vous pouvez désormais disposer de jusqu’à 1 milliard de clés uniques dans un jeu de données de recherche. <p>Pour plus d’informations, consultez la section [Limites de transfert de données](/help/technotes/guardrails.md#data-transfer-limits) dans la documentation [Mécanismes de sécurisation](/help/technotes/guardrails.md) de Customer Journey Analytics.</p> |  | 29 août 2025 |
| **Créer des mesures et des dimensions en fonction de champs de mappage définis par l’utilisateur ou l’utilisatrice à partir du schéma Platform** | Les champs de mappage définis par l’utilisateur ou l’utilisatrice que vous définissez dans votre schéma Experience Platform peuvent désormais être utilisés dans Customer Journey Analytics.<p>Vous pouvez utiliser les champs de mappage suivants lors de la création de mesures et de dimensions dans Customer Journey Analytics :</p><ul><li>Chaîne vers chaîne</li><li>Chaîne vers entier</li></ul><p>Pour plus d’informations, voir la section [Paramètres des composants](/help/data-views/component-settings/overview.md).</p><p>Pour plus d’informations sur les champs de mappage dans Experience Platform, consultez la section [Définir des champs de mappage dans l’interface d’utilisation](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/ui/fields/map).</p> |  | Fin août 2025 |
| **Les projets supprimés sont immédiatement indisponibles par URL et sont supprimés des diffusions planifiées.** | Les projets supprimés sont immédiatement supprimés des diffusions planifiées et ne sont plus accessibles par leur URL.<p>Auparavant, les projets étaient inclus dans les diffusions planifiées et étaient accessibles avec leur URL pendant 60 jours après leur suppression.</p><p>Pour plus d’informations sur la suppression de projets, consultez [Vue d’ensemble des projets](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Fin août 2025 |
| **Rapports en temps réel** | Les rapports en temps réel dans Customer Journey Analytics affichent et mettent à jour en temps réel les données et les visualisations au sein d’un ou de plusieurs panneaux dans Analysis Workspace.<br/><br/>(Lien vers la documentation à venir.) | | 18 septembre 2025 (version initialement prévue pour le 15 août 2025) |
| **Médias en streaming : mise à jour des champs XDM pour la collecte des données des médias en streaming dans Adobe Experience Platform** | Lors de la collecte de données des médias en streaming dans Adobe Experience Platform, les chemins d’accès aux champs XDM affichés dans la section « Chemin d’accès au champ XDM » de la documentation des paramètres des médias de streaming ne doivent plus être utilisés. Au lieu de cela, les clientes et les clients qui ont implémenté le connecteur source Analytics pour collecter des données de médias en streaming dans Platform avant le 9 mai 2025 doivent migrer leurs configurations existantes vers les chemins d’accès aux champs mediaReporting, comme indiqué sous l’en-tête « Chemin d’accès au champ XDM de création de rapports » de la documentation des paramètres de médias en streaming.<p> Ces chemins d’accès aux champs se trouvent sur les pages suivantes et sont marqués comme « obsolètes » : [Paramètres audio et vidéo](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Paramètres d’annonce](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/ad-parameters), [Paramètres de chapitre](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/chapter-parameters), [Paramètres d’état du lecteur](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/player-state-parameters) et [Paramètres de qualité](https://experienceleague.adobe.com/fr/docs/media-analytics/using/implementation/variables/quality-parameters). (Aucune action n’est requise de la part des clientes et des clients qui implémentent le connecteur source Analytics après le 9 mai 2025 et qui utilisent déjà uniquement les chemins XDM mediaReporting.)</p><p>L’ingestion de données sur les chemins d’accès aux champs XDM obsolètes se poursuivra jusqu’à la fin octobre 2025. Après cette date, les chemins d’accès aux champs obsolètes seront intégralement abandonnés et ne seront plus visibles dans l’interface d’utilisation de schéma Adobe Experience Platform, et les données seront envoyées uniquement à l’aide des chemins d’accès aux champs mediaReporting.</p><p>Pour plus d’informations, consultez [Migrer une implémentation du connecteur Source Analytics vers des champs de médias en streaming XDM mis à jour](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Pour obtenir de l’aide concernant la migration, contactez les services Adobe Consulting ou l’équipe en charge des comptes. </p> |  | Octobre 2025 |
| **Groupement dans les connexions** | Simplifie le groupement Customer Journey Analytics. Au lieu de dupliquer un jeu de données et d’appliquer un groupement sur le jeu de données dupliqué, le groupement est désormais effectué sur l’ingestion de données dans Customer Journey Analytics, ce qui supprime l’exigence de jeux de données et de schémas dupliqués. <p>En outre, au lieu d’avoir à demander le groupement par le biais du service clientèle, vous pouvez désormais lancer le groupement vous-même à partir d’une interface d’utilisation de connexions mise à jour.</p><p> *Les dates de publication communiquées précédemment sont repoussées en raison d’efforts supplémentaires requis. Les nouvelles dates de publication coïncident avec la période des fêtes, ce qui introduit des contraintes de publication supplémentaires. Un déploiement progressif est maintenant prévu pour garantir la stabilité et réduire au minimum les perturbations pendant la période des fêtes.*</p> | Fin octobre 2025 | Fin janvier 2025 |

## Correctifs dans Customer Journey Analytics

**Analysis Workspace** : AN-389683 ; AN-389534 ; AN-389207 ; AN-389066 ; AN-388687 ; AN-388478 ; AN-387089 ; AN-384865 ; AN-384560 ; AN-383486 ; AN-365768 ; AN-351639
**Composants** :
**Analyse du contenu**:
**Analyse guidée** : AN-384426
**Platform** : AN-384410
**Report Builder** : AN-389336 ; AN-382775
**Rapports** :
**Segmentation** :
**Mesures et dimensions partagées** :
**Autre** : AN-388222 ; AN-384898 ; AN-387169


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
