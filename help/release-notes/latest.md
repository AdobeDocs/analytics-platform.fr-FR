---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 61209c4f86052059ab2f1ef3a3d68e9c16f8e621
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 37%

---

# Notes de mise à jour actuelles d’Adobe Customer Journey Analytics (juin 2024)

**Dernière mise à jour** : jeudi 12 juin 2024

Ces notes de mise à jour portent sur la période du 6 juin 2024 au 24 juillet 2024. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Assistant IA pour Customer Journey Analytics** | Permet de poser des questions en langage naturel dans l’interface utilisateur de Customer Journey Analytics et d’obtenir des réponses basées sur la documentation de Customer Journey Analytics. [En savoir plus](/help/ai-assistant.md) | | vendredi 6 juin 2024 |
| **Groupement basé sur les graphiques : assemblage à l’aide de l’exportation de graphiques UIS** | Grâce au groupement basé sur les graphiques, vous pouvez utiliser le graphique d’identités pour obtenir une meilleure vue du parcours client en :<ul><li>Association de jeux de données avec différents identifiants sans avoir à extraire, transformer et charger des données supplémentaires pour refléter un seul identifiant.</li><li>Amélioration de la couverture de l’identité préférée ou dorée pour un jeu de données unique en partageant des identités entre les jeux de données.</li><li>Alignement des profils créés dans Real-time Customer Data Platform et Journey Optimizer avec les personnes dans Customer Journey Analytics.</li></ul>(Lien vers la documentation à suivre) |  | samedi 28 juin 2024 |
| **Transformation des schémas B2B Personne/Compte** | Pour prendre en charge les recherches basées sur les personnes sur les données B2B (y compris les comptes, les opportunités, les listes marketing et les campagnes), vous pouvez transformer des jeux de données de recherche B2B. Cette transformation n’est disponible que pour les jeux de données avec des données pour les schémas de recherche B2B, en fonction des classes suivantes :<ul><li>Relation Personne/Compte d’entreprise XDM</li><li>Relation Personne/XDM Business Opportunity</li><li>Membres de la liste XDM Business Marketing</li><li>Membres de XDM Business Campaign</li></ul>[En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5 juin 2024 |
| **Champs dérivés - Fonction mathématique** | Permet d’effectuer des opérations mathématiques simples dans les vues de données pour répondre aux questions sur vos utilisateurs et utilisatrices. Vous pouvez, par exemple, combiner des revenus de produits, de garanties et d’expédition. <p>[En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 5 juin 2024 |
| **Champs dérivés - Champs dérivés - Fonction suivante ou précédente** | Permet d’examiner la valeur précédente ou suivante. Par exemple, avec quels canaux marketing l’utilisateur a-t-il interagi auparavant avant le canal marketing sélectionné ? Ou, avec quelle page les utilisateurs ont-ils interagi avant ou après la page sélectionnée ? Avec quel canal les utilisateurs les plus populaires interagissent-ils avant de partir en magasin ? <p>[En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 12 juin 2024 |
| **Champs dérivés - Fonction récapitulative** | Permet d’appliquer des fonctions de type agrégation à des mesures ou à des dimensions aux niveaux de l’événement, de la session et de l’utilisateur. (Lien vers la documentation à suivre) | | jeudi 26 juin 2024 |
| **Champs dérivés - Fonction de déduplication** | Permet d’empêcher le comptage répété d’une valeur. Peuvent être appliquées au niveau de l’utilisateur ou de la session ou selon la valeur unique d’une dimension. (Lien vers la documentation à suivre) |  | jeudi 26 juin 2024 |
| **Hiérarchisation de l’ingestion et latence** | Vous pouvez désormais ingérer vos données d’événement dans Customer Journey Analytics dans les 90 minutes (SLT), qu’elles aient été créées pendant 24 heures, 48 heures ou 7 jours. Notez que cette fonctionnalité diffère en fonction du module de SKU acheté par votre société :<ul><li>Ingestion prioritaire CJA : données âgées de 24 heures dans un traitement SLT de 90 minutes (disponible pour CJA Foundation et CJA Select).</li><li>Intermédiaire d’ingestion de priorité CJA : données de 72 heures dans un traitement SLT de 90 minutes (disponible pour CJA Prime)</li><li>Ingestion prioritaire CJA : données d’une semaine dans un traitement SLT de 90 minutes (disponible pour CJA Ultimate).</li></ul> |  | 12 juin 2024 |
| **Partager les comptes et les emplacements utilisés pour l’export et l’import** | Les personnes peuvent désormais mettre les comptes et les emplacements qu’elles créent à la disposition de toutes les personnes de leur organisation. Seuls les propriétaires de compte et d’emplacement et les administrateurs système peuvent modifier et supprimer des comptes et des emplacements. Auparavant, les comptes et emplacements ne pouvaient être utilisés que par l’utilisateur qui les avait créés. Ces paramètres sont disponibles lorsque les utilisateurs [configuration des comptes d’exportation cloud](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) et [configuration des emplacements d’exportation cloud](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 juin 2024 | mercredi 18 juin 2024 |
| **Sélectionnez plusieurs filtres lorsqu’ils sont disponibles dans le menu déroulant d’un tableau à structure libre.** | Lorsque plusieurs filtres ont été ajoutés à un tableau à structure libre sous forme de menu déroulant, les utilisateurs du tableau à structure libre peuvent désormais sélectionner plusieurs filtres à la fois. Le tableau à structure libre est filtré pour inclure l’un des filtres sélectionnés. <p>Auparavant, les utilisateurs ne pouvaient sélectionner qu’un seul filtre à la fois dans un menu déroulant de filtre.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see "Add filters to a project" in "Use components in Analysis Workspace."--> |  | jeudi 19 juin 2024 |
| **Table des matières pour les projets Workspace** | Une nouvelle table des matières est désormais disponible pour les projets. La table des matières contient des liens qui permettent aux utilisateurs d’accéder rapidement aux panneaux et aux visualisations dans le projet. <p>La table des matières peut être activée pour des projets individuels ou tous les projets pour un utilisateur donné.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | jeudi 19 juin 2024 |
| **Création d’hyperliens pour les éléments de dimension dans un tableau à structure libre** | Vous pouvez créer des hyperliens pour un ou plusieurs éléments de dimension afin de les rendre cliquables dans un tableau à structure libre d’Analysis Workspace. <p>Vous pouvez créer des liens hypertexte pour les éléments de dimension qui comportent des valeurs d’URL ou créer des URL personnalisées pour les éléments de dimension qui n’ont pas de valeurs d’URL.</p><p>Vous pouvez créer des URL personnalisées dynamiques pour plusieurs éléments de dimension à l’aide de variables. Les variables peuvent référencer la valeur d’un élément de dimension ou la dimension de ventilation.</p><p>(Lien vers la documentation à suivre.)<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | jeudi 19 juin 2024 |
| **Les audiences sont publiées dans une nouvelle section « Audiences » dans Experience Platform.** | Les audiences qui sont publiées à partir de Customer Journey Analytics sont désormais disponibles dans la nouvelle section « Audiences » d’Adobe Experience Platform.<p>Auparavant, les audiences qui étaient publiées à partir de Customer Journey Analytics étaient disponibles dans Experience Platform dans la section « Segments ».</p><p>Cette amélioration s’accompagne des avantages suivants :</p><ul><li>Les audiences n’ont plus un délai d’une heure avant d’apparaître dans Experience Platform ; elles sont disponibles quelques secondes après leur publication.</li><li>Les audiences peuvent être triées dans Experience Platform à l’aide de la colonne « Origine », qui affiche l’application à partir de laquelle l’audience a été publiée à l’origine.</li><li>Les options de filtrage et de tri d’Experience Platform vous permettent de trouver plus rapidement les audiences pertinentes.</li></ul> <p>(Lien vers la documentation à suivre)</p> |  | lundi 14 juillet 2024 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

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
