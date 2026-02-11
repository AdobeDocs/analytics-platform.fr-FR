---
title: Notes de mise à jour actuelles de Customer Journey Analytics
description: Afficher les dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e98a1abbab4b954df5f7759879203c1d355fd50
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 34%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (février 2026)

**Dernière mise à jour** : jeudi 11 février 2026

Ces notes de mise à jour couvrent la période de publication de février 2026. Les mises à jour d’Adobe Customer Journey Analytics suivent un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité et description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ------- | ---- |
| **Remplacements d’en-tête** <p>Vous pouvez spécifier un nom d’en-tête et une valeur d’en-tête secrète dans Content Analytics. Cette [configuration de remplacement de l’en-tête](/help/content-analytics/config/guided.md#header-overrides) garantit que Content Analytics envoie des en-têtes HTTP personnalisés pour contourner les technologies de détection des robots ou de contrôle du trafic que vous avez implémentées.</p> |  | mardi 2 février 2026 |
| **Inclure plusieurs colonnes de dimension dans un tableau à structure libre**<p>Vous pouvez désormais inclure jusqu’à 5 colonnes de dimension dans un tableau à structure libre, ce qui vous permet d’afficher plusieurs éléments de dimension côte à côte. Chaque ligne d’éléments de dimension se comporte comme un seul élément de dimension concaténé.</p><p>Vous pouvez appliquer des filtres, un tri, des répartitions, etc. aux tableaux à structure libre à plusieurs colonnes de dimensions afin de créer une analyse plus approfondie et plus personnalisée.</p><p>Auparavant, vous pouviez inclure une seule colonne de dimension dans un tableau à structure libre.</p><p>Pour plus d’informations, voir [Inclure plusieurs colonnes de dimensions dans un tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | jeudi 28 janvier 2026 | jeudi 18 février 2026 |
| **Trier les tableaux sur plusieurs colonnes**<p>Vous pouvez désormais trier les données d’un tableau à structure libre sur plusieurs colonnes dans Analysis Workspace, qu’il s’agisse de dimensions ou de mesures.</p><p>Lorsque vous triez des données sur plusieurs colonnes, les données sont triées en fonction de la priorité que vous attribuez à chaque colonne. Le score de priorité s’affiche en regard de l’icône de tri.</p><p>Pour plus d’informations, voir [Filtrer et trier les tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | jeudi 28 janvier 2026 | jeudi 18 février 2026 |
| **Améliorations de l’exportation de tables complètes**<p>L’exportation complète des tables comprend les améliorations suivantes :</p><p>Améliorations de la création et de la configuration des exportations</p><ul><li>Créez un export à partir de la page Exports . Auparavant, vous pouviez uniquement créer une exportation à partir d’Analysis Workspace en cliquant avec le bouton droit sur le tableau.</li><li>Ajoutez un nouveau compte ou emplacement lors de la création d’une exportation.</li><li>Automatisez la création de noms de fichiers et le placement de dossiers des fichiers exportés. Cela permet de prédire les noms de fichiers et de les organiser en dossiers de manière logique. Auparavant, les noms de fichier étaient imprévisibles et regroupés dans un seul dossier.</li><li>Prise en charge de l’exportation de données sous forme de fichiers Parquet pour une meilleure compatibilité avec Data Warehouse. Auparavant, seuls CSV et JSON étaient pris en charge.</li></ul><p>Améliorations de la gestion des exportations</p><ul><li>Renouveler ou annuler une ou plusieurs exportations à partir de la page Exports .</li><li>Renvoyez une ou plusieurs exportations à partir de la page Journaux .</li><li>Envoyer un e-mail à des utilisateurs individuels ou à des groupes lorsqu’une exportation échoue ou arrive à expiration.</li><li>Messages d’erreur plus précis pour les exportations ayant échoué.</li></ul><p>Améliorations des mesures calculées, des segments et des dimensions</p><ul><li>Prise en charge de fonctions de mesures plus calculées. Auparavant, seules les fonctions mathématiques simples étaient prises en charge.</li><li>Appliquez des segments lors de la création d’une exportation.</li><li>Prise en charge de dimensions de type double donnée pour une précision améliorée.</li></ul><p>Améliorations administratives</p><ul><li>Les administrateurs peuvent désormais afficher toutes les exportations et tous les journaux, quelle que soit la personne qui les a créés.</li></ul><p>(Lien vers la documentation à suivre.)</p> | jeudi 18 février 2026 | jeudi 4 mars 2026 |
| **Content Analytics : Miniatures et aperçus de visualisation Dispersion** <p>Lors de l’affichage d’une visualisation en nuage de points dans Content Analytics, une miniature de la ressource s’affiche désormais lorsque vous pointez sur un point du graphique. Cette miniature vous permet de voir rapidement et facilement quel contenu est représenté dans le graphique.</p><p>(Lien vers la documentation à suivre.)</p> | mercredi 17 février 2026 | mardi 2 mars 2026 |
| **Content Analytics : Miniatures et aperçus des visualisations en barres** <p>Lors de l’affichage d’une visualisation à barres horizontales dans Content Analytics, une miniature de la ressource s’affiche désormais lorsque vous pointez sur une barre du graphique. Cette miniature vous permet de voir rapidement et facilement quel contenu est représenté dans le graphique.</p><p>(Lien vers la documentation à suivre.)</p> | mardi 23 février 2026 | mardi 9 mars 2026 |
| **Mettre à jour vers la fonction Nombre approximatif d’éléments distincts**<p>L’algorithme probabiliste HLL utilisé dans la fonction Nombre approximatif d’éléments distincts sera bientôt mis à jour. La sortie résultante pour les nombres utilisant cette fonction peut changer légèrement par rapport aux nombres historiques, comme suit :<ul><li>Lorsque vous comptez de très petites quantités de valeurs uniques, les résultats seront améliorés pour utiliser des décomptes exacts plutôt que des estimations.</li><li>Lorsque vous comptabilisez des éléments de plus grande taille, les estimations de comptage conservent la même précision qu’avant cette mise à jour (les estimations sont exactes à moins de 5 % du nombre exact, 95 % du temps).</li></ul><p>Pour plus d&#39;informations sur la fonction Nombre approximatif d&#39;éléments distincts, voir [Nombre approximatif d&#39;éléments distincts](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) dans [Fonctions avancées](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | Mars 2026 |
| **Prise en charge de la mise en miroir des données**  <p>Grâce à la prise en charge des schémas basés sur des modèles et de la fonctionnalité de capture de données modifiées (CDC) pour des connecteurs sources spécifiques dans Experience Platform, Customer Journey Analytics sera en mesure de prendre en charge la fonctionnalité de [mise en miroir des données](/help/data-mirror/data-mirror.md) des solutions d’entrepôt de données telles que [!DNL Snowflake], [!DNL Azure Databricks] et [!DNL Google BigQuery].</p><p>Contactez votre équipe Adobe en charge des comptes pour accéder à la version bêta.</p> | Version bêta : 24 septembre 2025 | À confirmer |
| **Services de médias en streaming : prise en charge des données de planning** <p>Vous pouvez désormais charger les données de planning du contenu multimédia précédent en direct pour suivre plus facilement et plus précisément l’audience.</p><p>Les éléments suivants sont des exemples de contenu en direct qui sont pris en charge avec le chargement de données de planning :</p><ul><li>Plateformes FAST (Free Ad Supported TV)</li><li>Flux locaux</li><li>Sports en direct</li></ul><p>Le chargement des données de planning vous permet de suivre les audiences des programmes individuels qui ont été diffusés pendant la période que vous avez indiquée dans le fichier de chargement. Vous pouvez même recueillir des données d’audience pour des sujets ou des segments de programme spécifiques.</p><p>Ces fonctionnalités sont disponibles quelle que soit la manière dont vous avez mis en œuvre Streaming Media Collection.</p><p>Auparavant, il était difficile de relier avec précision une session donnée à des programmes spécifiques lors de l’analyse du contenu en direct, et il n’était pas possible de relier une session donnée à des sujets individuels ou à des segments de programmes.</p><p>Pour plus d’informations, voir [Charger des données de planning pour suivre le contenu en direct](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 octobre 2025 | Premier semestre 2026<p>(Version initialement prévue pour le 29 octobre 2025)</p> |

## Correctifs dans Customer Journey Analytics

**Analysis Workspace** : AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428834, AN-306540, AN-426014, AN-427801
**Composants** :
**Content Analytics**:
**Analyse guidée** :
**Exports** : AN-422041, AN-421599, AN-422112
**Vues de données** :
**Implémentation** :
**Report Builder**: AN-391415, AN-425125
**Reporting** : AN-425817, AN-424362, AN-425752, AN-425278, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Segmentation** : AN-428905, AN-428232
**Rapports planifiés** : AN-425484, AN-425137
**Mesures et dimensions partagées** :
**Autre** : AN-428833, AN-425074


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Suppression des suites de chiffrement TLS 1.2** | jeudi 11 février 2026 | Avis aux administrateurs : Adobe prévoit de supprimer la prise en charge des suites de chiffrement TLS 1.2 suivantes des serveurs de collecte de données Adobe le 27 mai 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Aucune action du client n’est requise pour la plupart des implémentations. Cette modification affecte principalement les données Analytics envoyées à partir d’applications natives héritées qui utilisent des bibliothèques TLS obsolètes, ainsi qu’un petit nombre de visiteurs web sur des navigateurs ou des systèmes d’exploitation obsolètes. La suppression de la prise en charge de ces suites de chiffrement améliore la sécurité et aligne Adobe sur les normes de chiffrement modernes. Moins de 0,1 % du trafic de collecte de données repose actuellement sur ces suites de chiffrement.</p> |

## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2025](/help/release-notes/2025.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour du module complémentaire Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
