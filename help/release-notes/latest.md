---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 524aed20a62b8d8648230be81c63f9c58c84ae87
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 80%

---

# Notes de mise à jour actuelles de Customer Journey Analytics (CJA) (février 2023)

**Dernière mise à jour** : le 6 février 2023

Les mises à jour de Customer Journey Analytics fonctionnent sur une [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités clés et mises à jour

| Fonctionnalité | Description | [Début du déploiement](/help/release-notes/releases.md) | [Disponibilité générale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Mettre à jour les audiences CJA** | Une fois que vous avez créé une audience, Adobe crée un segment de diffusion en continu Experience Platform pour chaque nouvelle audience CJA. Un segment en continu ne sera créé que si votre organisation est configurée pour la segmentation en continu. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=fr#after-audience-created) | S.O. | 3 février 2023 |
| **Masquer les périodes de comparaison dans les cartes de performance mobiles** | Avec les cartes de performance mobiles, vous pouvez désormais masquer la comparaison des périodes. | S.O. | 8 février 2023 |
| **Mises à jour du calendrier dans Workspace** | <ul><li>Ancrer les dates du panneau : vous pouvez créer des composants de la période par rapport au calendrier du panneau. [En savoir plus](/help/components/date-ranges/calendar.md)</li><li>Mises à jour des styles de calendrier : les styles de calendrier de l’ensemble de l’interface utilisateur ont été mis à niveau afin de présenter un workflow plus cohérent et plus facile à utiliser.</li><li>Mises à jour de la formule de calendrier : si vous utilisez des dates relatives, toutes les formules de calendrier refléteront le début de la période du panneau. [En savoir plus](/help/components/date-ranges/calendar.md)</li></ul> | S.O. | 8 février 2023 |
| **Mises à jour des plages de dates des panneaux** | Dans Workspace, nous avons ajouté les améliorations suivantes :<ul><li>À compter de la version de février, les aperçus de composants et de données seront basés sur la période du panneau et non sur les 90 derniers jours. </li><li>Tous les composants répertoriés dans le rail de gauche seront disponibles en fonction de la période du panneau.</li><li>Tous les aperçus de date dans les créateurs de segments et de mesures calculées sont basés sur la période du panneau (sauf si vous y accédez à partir des gestionnaires de composants, qui n’ont pas de panneau associé, ils seront toujours basés sur les 90 derniers jours).</li><li>Tous les aperçus de données affichent des données ou des composants en fonction de la période du panneau.</li></ul> | S.O. | 8 février 2023 |
| **Filtrage des lignes/colonnes pour la diffusion en continu du connecteur source Adobe Analytics** | Le connecteur source Analytics dans Adobe Experience Platform permet désormais de filtrer les données Analytics utilisées pour renseigner les profils dans [Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr).<p>Le filtrage au niveau des lignes permet de réduire le nombre d’événements associés aux profils. Le filtrage au niveau des colonnes contribue à réduire la richesse des événements eux-mêmes, ce qui vous permet d’optimiser l’utilisation des droits sur les profils. Ce filtrage s’applique uniquement aux données envoyées à Real-Time Customer Profile et au [Service d’identités](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr).<p>**Le filtrage n’a aucune incidence sur les données envoyées au lac de données en vue de leur utilisation dans des applications telles que Customer Journey Analytics.**. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr#filtering-for-profile) | S.O. | 22 février 2023 |

{style=&quot;table-layout:auto&quot;}

## Correctifs dans Customer Journey Analytics

AN-309106

## Avis importants destinés aux administrateurs de CJA

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| Aucun avis actuel | S.O. | S.O. |

{style=&quot;table-layout:auto&quot;}

## Ressources connexes

* [Notes de mise à jour de CJA précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
