---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b633e3e70c24d9b00b1ab2f80954ad698b12ce29
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 37%

---

# Notes de mise à jour du Customer Journey Analytics actuel (CJA) (janvier 2023)

**Dernière mise à jour** : le 6 février 2023

Les mises à jour de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Début du déploiement](/help/release-notes/releases.md) | [Disponibilité générale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Mise à jour vers les audiences CJA** | Après avoir créé une audience, [Adobe crée un segment de diffusion en continu Experience Platform pour chaque nouvelle audience CJA.](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). Un segment de diffusion en continu AEP n’est créé que si l’organisation est configurée pour la segmentation en continu. | S.O. | 3 février 2023 |
| **Prise en charge des tableaux d’objets pour les jeux de données de profil et de recherche** | Les jeux de données de profil et les jeux de données de recherche prennent désormais en charge les tableaux d’objets à utiliser dans CJA. | 11 janvier 2023 | 19 janvier 2023 |
| **Dossiers dans Workspace** | Les dossiers vous aident à organiser et à catégoriser vos projets pour une meilleure récupération et un meilleur accès. En outre, un **[!UICONTROL Société]** permet aux administrateurs de créer et de partager facilement du contenu avec tous les utilisateurs de Workspace. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=fr) | S.O. | 11 janvier 2023 |
| **Page de destination par défaut** | Le [nouvelle landing page](/help/getting-started/landing.md) qui a été introduit en 2022 deviendra l’expérience par défaut pour tous les utilisateurs de **11 janvier 2023**. La page d’entrée héritée sera obsolète et tous les utilisateurs devront utiliser la nouvelle expérience. | S.O. | 11 janvier 2023 |
| **Page Gestionnaire de projets obsolète** | Avec la publication de la nouvelle landing page, nous avons abandonné la variable **[!UICONTROL Chef de projet]** comme répertorié sous **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Composants]**. La nouvelle page d’entrée contient toutes les fonctionnalités de l’ancienne page Gestionnaire de projets, etc. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | S.O. | 11 janvier 2023 |
| **Planification de classeurs dans Report Builder** | Dans Customer Journey Analytics, vous pouvez créer des plannings pour envoyer des classeurs à intervalles réguliers. Désormais, les destinataires peuvent recevoir régulièrement les dernières mises à jour de vos classeurs. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | S.O. | 11 janvier 2023 |
| **Enregistrement automatique des nouveaux projets** | Analysis Workspace enregistre désormais automatiquement les nouveaux projets créés. Si, pour une raison quelconque, vous perdez inopinément l’accès à un nouveau projet avant de l’enregistrer manuellement, une version de récupération de votre projet est désormais disponible. Auparavant, les projets n’étaient enregistrés automatiquement qu’après avoir été initialement enregistrés manuellement. [En savoir plus](/help/analysis-workspace/build-workspace-project/save-projects.md) | S.O. | 11 janvier 2023 |
| **Amélioration des préférences utilisateur** | Vous pouvez maintenant configurer des préférences supplémentaires au niveau de l’utilisateur (dans [!UICONTROL Composants] > [!UICONTROL Préférences]). Lorsque vous définissez des préférences utilisateur, vos sélections s’étendent sur l’ensemble de vos projets, tableaux et visualisations. La page Préférences contient désormais les nouveaux onglets suivants, chacun contenant de nombreuses nouvelles options de configuration :<ul><li>Tableau à structure libre</li><li>Visualisations>/li></ul>. En outre, d’autres préférences sont désormais disponibles sur la page **[!UICONTROL Général]** et **[!UICONTROL Projet]** onglets.<p>Auparavant, la plupart de ces préférences n’étaient configurables que pour des projets, des tableaux et des visualisations individuels. [En savoir plus](/help/analysis-workspace/user-preferences.md) | S.O. | 11 janvier 2023 |

{style=&quot;table-layout:auto&quot;}

## Correctifs

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| **Amélioration du mappage IP/géolocalisation** | 29 septembre 2022 | Digital Element, le fournisseur d’Adobe pour les recherches IP, effectue une mise à niveau vers un nouveau jeu de données amélioré (NetAcuity Pulse) pour le mappage IP/géolocalisation. Adobe Analytics a reporté l’adoption de ce nouveau jeu de données sur **11 janvier 2023**. La nouvelle base de données sera plus précise que les versions précédentes. Certains mappages IP/géolocalisation seront modifiés/améliorés lors de l’adoption de la nouvelle base de données.<p> Les données CJA fournies par le biais du [!UICONTROL connecteur source Analytics] tireront également automatiquement parti des nouveaux mappages. |

{style=&quot;table-layout:auto&quot;}


## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2022](/help/release-notes/2022.md)

* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)

* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)

* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)

* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
