---
description: Adobe propose différentes mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leurs utilisations prévues.
title: Modèles de mesures calculées
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
TQID: https://experienceleague.adobe.com/-jngIXgXeFZZkfL5jSHLuX8ZmcWU5rIfLqb26ovn6QY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 83%

---

# Modèles de mesures calculées

Customer Journey Analytics fournit les modèles de mesures calculées suivants pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées définies par Adobe sont identifiées par un petit logo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Pour filtrer rapidement ces mesures, sélectionnez ![Libellé](/help/assets/icons/Label.svg) **[!UICONTROL Modèle Adobe]** dans le [Filtre de composants](/help/components/overview.md#filter).

| Nom de la mesure calculée | Description<br/>Formule |
|---------|----------|
| **[!UICONTROL Taux de début de session]** | Pourcentage de fois où un élément de dimension sʼest produit lors du premier événement dʼune session.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [composant standard](/help/data-views/component-reference.md) [!UICONTROL Début de session] dans votre [vue de données](/help/data-views/create-dataview.md).</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Début de session** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Sessions** **)** |
| **[!UICONTROL Temps passé par personne]** | Durée moyenne passée par une personne sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [composant standard](/help/data-views/component-reference.md) [!UICONTROL Temps passé (secondes)] dans votre [vue de données](/help/data-views/create-dataview.md). Le segment Exclure le dernier événement de la session est appliqué à la mesure Personnes . Le segment exclut le dernier événement de chaque session d’un jeu de données. Cette exclusion peut vous aider à analyser le comportement des utilisateurs et utilisatrices menant à un événement ou à une action, comme un achat ou un envoi de formulaire, tout en excluant l’action finale elle-même.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Temps passé (secondes)** ![Diviser](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclure le dernier événement de la session(** ![Événement](/help/assets/icons/Event.svg) **Personnes)** |
| **[!UICONTROL Sessions par personne]** | Nombre moyen de sessions par personne.<p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Sessions** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Personnes** **)** |
| **[!UICONTROL Temps passé par session]** | Durée moyenne passée par personne et par session sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [composant standard](/help/data-views/component-reference.md) [!UICONTROL Temps passé (secondes)] dans votre [vue de données](/help/data-views/create-dataview.md). Le segment Exclure le dernier événement de la session est appliqué à la mesure Sessions . Le segment exclut le dernier événement de chaque session d’un jeu de données. Cette exclusion peut vous aider à analyser le comportement des utilisateurs et utilisatrices menant à un événement ou à une action, comme un achat ou un envoi de formulaire, tout en excluant l’action finale elle-même.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Temps passé (secondes)** ![Diviser](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclure le dernier événement de la session(** ![Événement](/help/assets/icons/Event.svg) **Sessions)** |
| **[!UICONTROL Taux de fin de session]** | Pourcentage de fois où un élément de dimension sʼest produit lors du dernier événement dʼune session. <p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [composant standard](/help/data-views/component-reference.md) [!UICONTROL Fin de session] dans votre [vue de données](/help/data-views/create-dataview.md).</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Fin de session** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Sessions** **)** |
| **[!UICONTROL Sessions web]** | Nombre de sessions qui se sont produites sur le site web. |
| **[!UICONTROL Taux d’achèvement de l’enquête]** | Taux auquel les personnes ont répondu à une enquête après l’avoir démarrée. |
| **[!UICONTROL Taux de session multicanaux]** | Ratio de sessions qui se sont produites et qui incluaient plusieurs canaux (comme le trafic web et le trafic mobile), par rapport à celles qui n’incluaient qu’un seul canal. |
| **[!UICONTROL Taux de personnes multicanaux]** | Taux de personnes ayant participé à plusieurs canaux par rapport à celles qui n’ont participé qu’à un seul canal. |
| **[!UICONTROL Sessions de l’application mobile]** | Nombre de sessions qui se sont produites sur l’application mobile. |
| **[!UICONTROL Sessions cross-canal web et application]** | Nombre de sessions qui se sont produites et qui incluaient à la fois le trafic web et le trafic mobile. |
| **[!UICONTROL Coût des appels]** | Coût total des appels au centre d’appel. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Durée moyenne d’appel]** | Durée moyenne des appels au centre d’appel. |
| **[!UICONTROL Coût moyen par appel]** | Coût moyen des appels passés au centre d’appel. |
| **[!UICONTROL Score moyen de l’enquête sur les appels]** | Score moyen d’enquête concernant les appels effectués au centre d’appel. |

{style="table-layout:auto"}
