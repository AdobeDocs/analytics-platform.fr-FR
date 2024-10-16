---
description: Adobe fournit diverses mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leurs utilisations prévues.
title: Modèles de mesures calculées
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 8%

---

# Modèles de mesures calculées

Customer Journey Analytics fournit les modèles de mesures calculées suivants pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées définies par l’Adobe sont identifiées par un petit logo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Pour filtrer rapidement ces mesures, sélectionnez ![Étiquette](/help/assets/icons/Label.svg) **[!UICONTROL Modèle d’Adobe]** dans le [filtre Composants](/help/components/overview.md#filter).

| Nom de la mesure calculée | Description<br/>Formule |
|---------|----------|
| **[!UICONTROL Taux de début de session]** | Pourcentage du nombre d’éléments de dimension qui se sont produits au premier événement d’une session.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le  [ ](/help/data-views/component-reference.md) composant standard [ dans la ](/help/data-views/create-dataview.md) vue de données.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Démarrages de session** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Sessions** **)** |
| **[!UICONTROL Durée de la visite par personne]** | Durée moyenne passée par une personne sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL composant standard Durée de la visite (secondes)] [ ](/help/data-views/component-reference.md) dans la [vue de données](/help/data-views/create-dataview.md). Le filtre Exclure le dernier événement de la session est appliqué à la mesure Personnes. Le filtre exclut le dernier événement de chaque session dans un jeu de données. Cette exclusion peut vous aider à analyser le comportement de l’utilisateur menant à un événement ou à une action, comme un achat ou un envoi de formulaire, tout en excluant l’action finale elle-même.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Durée (secondes)** ![Diviser](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclure le dernier événement de la session(** ![ ](/help/assets/icons/Event.svg) **Personnes )** |
| **[!UICONTROL Sessions par personne]** | Nombre moyen de sessions par personne.<p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Sessions** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Personnes** **)** |
| **[!UICONTROL Durée de la session]** | Durée moyenne passée par personne et par session sur un élément de dimension donné.<p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL composant standard Durée de la visite (secondes)] [ ](/help/data-views/component-reference.md) dans la [vue de données](/help/data-views/create-dataview.md). Le filtre Exclure le dernier événement de session est appliqué à la mesure Sessions . Le filtre exclut le dernier événement de chaque session dans un jeu de données. Cette exclusion peut vous aider à analyser le comportement de l’utilisateur menant à un événement ou à une action, comme un achat ou un envoi de formulaire, tout en excluant l’action finale elle-même.</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Durée (secondes)** ![Diviser](/help/assets/icons/Divide.svg) ![Segmentation](/help/assets/icons/Segmentation.svg) **Exclure le dernier événement de la session(** ![ ](/help/assets/icons/Event.svg) **Sessions )** |
| **[!UICONTROL Taux de fin de session]** | Pourcentage du dernier événement d’une session auquel un élément de dimension s’est produit. <p>Cette mesure calculée est automatiquement ajoutée à Workspace lorsque vous incluez le [!UICONTROL composant standard Session Ends] [ dans votre [ vue de données](/help/data-views/create-dataview.md).](/help/data-views/component-reference.md)</p>Résumé : **(** ![Événement](/help/assets/icons/Event.svg) **Fin de session** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **Sessions** **)** |

{style="table-layout:auto"}
