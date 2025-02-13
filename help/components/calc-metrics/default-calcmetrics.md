---
description: Adobe propose différentes mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leur utilisation prévue.
title: Modèles de mesures calculées
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d13f980d1fbae3f608bf64587f59dc22c3fac9ce
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 6%

---

# Modèles de mesures calculées

Customer Journey Analytics fournit les modèles de mesures calculées suivants pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées définies par Adobe sont identifiées par un petit logo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Pour filtrer rapidement ces mesures, sélectionnez ![Libellé](/help/assets/icons/Label.svg) **[!UICONTROL Modèle Adobe]** dans le [Filtre de composants](/help/components/overview.md#filter).

| Nom de la mesure calculée | Description<br/>Formule |
|---------|----------|
| **[!UICONTROL Taux de début de session]** | Pourcentage d’un élément de dimension survenu le premier événement d’une session.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL composant Démarrage de session] [standard](/help/data-views/component-reference.md) dans votre [vue de données](/help/data-views/create-dataview.md).</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Début de session** ![Division](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Sessions**)**** |
| **[!UICONTROL Temps passé par personne]** | Durée moyenne passée par une personne sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL Temps passé (secondes)] [composant standard](/help/data-views/component-reference.md) dans votre [vue de données](/help/data-views/create-dataview.md). Le filtre Exclure le dernier événement de la session est appliqué à la mesure Personnes . Le filtre exclut le dernier événement de chaque session d’un jeu de données. Cette exclusion peut vous aider à analyser le comportement des utilisateurs et utilisatrices menant à un événement ou à une action, comme un achat ou un envoi de formulaire, tout en excluant l’action finale elle-même.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Temps passé (secondes)** ![Diviser](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg)Exclure le dernier événement de la session(**Event**![People ) )](/help/assets/icons/Event.svg) **** |
| **[!UICONTROL Sessions par personne]** | Nombre moyen de sessions par personne.<p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Sessions** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) ****)**** |
| **[!UICONTROL Durée par session]** | Durée moyenne passée par personne et par session sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL Temps passé (secondes)] [composant standard](/help/data-views/component-reference.md) dans votre [vue de données](/help/data-views/create-dataview.md). Le filtre Exclure le dernier événement de la session est appliqué à la mesure Sessions . Le filtre exclut le dernier événement de chaque session d’un jeu de données. Cette exclusion peut vous aider à analyser le comportement des utilisateurs et utilisatrices menant à un événement ou à une action, comme un achat ou un envoi de formulaire, tout en excluant l’action finale elle-même.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Temps passé (secondes)** ![Diviser](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg)Exclure le dernier événement de la session(**Event** Sessions ) )![ ](/help/assets/icons/Event.svg) **** |
| **[!UICONTROL Taux de fin de session]** | Pourcentage d’un élément de dimension survenu le dernier événement d’une session. <p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL composant de fin de session] [standard](/help/data-views/component-reference.md) dans votre [vue de données](/help/data-views/create-dataview.md).</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Fin de session** ![Division](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Sessions**)**** |
| **[!UICONTROL Sessions web]** | Nombre de sessions qui se sont produites sur le site web. |
| **[!UICONTROL Taux d’achèvement de l’enquête]** | Taux auquel les personnes ont répondu à une enquête après l’avoir démarrée. |
| **[!UICONTROL Débit de session multicanal]** | Le ratio de sessions qui se sont produites et qui incluaient plusieurs canaux (comme le trafic web et le trafic mobile), par rapport à celles qui n’incluaient qu’un seul canal. |
| **[!UICONTROL Tarif personne multicanal]** | Taux de personnes ayant participé à plusieurs canaux par rapport à celles qui n’ont participé qu’à un seul canal. |
| **[!UICONTROL Sessions sur application mobile]** | Nombre de sessions qui se sont produites sur l’application mobile. |
| **[!UICONTROL Sessions cross-canal Web+app]** | Nombre de sessions qui se sont produites et qui incluaient à la fois le trafic web et le trafic mobile. |
| **[!UICONTROL Coût des appels]** | Coût total des appels au centre d’appels. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Durée moyenne d’appel]** | Durée moyenne des appels au centre d’appels. |
| **[!UICONTROL Coût moyen des appels]** | Coût moyen des appels passés au centre d’appels. |
| **[!UICONTROL Score moyen de l’enquête sur les appels]** | Score d’enquête moyen concernant les appels effectués au centre d’appels. |

{style="table-layout:auto"}
