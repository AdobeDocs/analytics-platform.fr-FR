---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 98bba7c7bc56cfc2a2436f13d833dbf6504d7d6e
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 59%

---

# Notes de mise à jour actuelles d’Adobe Customer Journey Analytics (septembre 2023)

**Dernière mise à jour** : 7 septembre 2023

Ces notes de mise à jour portent sur la période du 13 septembre 2023 au 3 octobre 2023. Les mises à jour d’Adobe Customer Journey Analytics fonctionnent sur un [modèle de diffusion continue](releases.md) qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Fonctionnalités nouvelles ou mises à jour

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Prise en charge des classifications A4T dans le connecteur source Analytics** | Prise en charge de la nouvelle `correlationID` champ pour Adobe Analytics | La variable `_experience.decisioning.propositions.scopeDetails.correlationID` est maintenant disponible dans le schéma du connecteur source Adobe Analytics. Ce champ est utilisé pour prendre en charge les classifications A4T et sera renseigné à compter de septembre 2023. | | S.O. | 12 septembre 2023 |
| **Mises à jour des champs dérivés** | Les mises à jour suivantes ont été apportées à la fonctionnalité des champs dérivés :<ul><li>La variable [!UICONTROL Recherche] a été renommée en [!UICONTROL Classifier], avec des options supplémentaires pour charger les données CSV. **(Versions le 27 septembre 2023)**</li><li>D’autres fonctions peuvent être utilisées lors de la définition d’un champ dérivé : [!UICONTROL Rogner], [!UICONTROL Minuscules] et [!UICONTROL Recherche].</li><li>Les définitions de champ dérivées prennent désormais en charge les champs provenant de [!UICONTROL Recherche] et [!UICONTROL Profil] jeux de données.</li></ul>[En savoir plus](/help/data-views/derived-fields/derived-fields.md) | S.O. | 13 septembre 2023 |
| **Nouvelles fonctionnalités d’Adobe Product Analytics** | <ul><li>**Détection des anomalies**: comparez les événements aux valeurs attendues dérivées des tendances historiques. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=fr)</li><li>**Tendances Fréquence d’utilisation du mode**: mesurez l’adoption de vos fonctionnalités par fréquence d’utilisation. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**Préférences utilisateur**: configurez un certain nombre de préférences utilisateur, telles que les palettes de couleurs, les vues de données, les calendriers, le comptage d’instances, le format de nombre et le délimiteur de virgule. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=fr)</li></ul> | S.O. | 18 septembre 2023 |
| **Recherches de périphériques Experience Edge** | Activez la collecte automatique de données de type périphérique via le réseau Edge Experience Platform. Ce service Experience Edge bénéficie au Customer Journey Analytics ainsi qu’à d’autres applications Experience Platform. (Lien vers la documentation à suivre) | S.O. | 27 septembre 2023 |

{style="table-layout:auto"}

## Correctifs dans Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


## Avis importants à l’intention des administrateurs et administratrices de Customer Journey Analytics

| Avis | Ajout ou mise à jour des avis | Description |
| --- | --- | --- |
| S.O. | S.O. | S.O. |

{style="table-layout:auto"}

## Avis de fin de vie

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les API Adobe Analytics et Customer Journey Analytics et les clients et clientes Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Ressources connexes

* [Notes de mise à jour précédentes de Customer Journey Analytics pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr)
* [Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
