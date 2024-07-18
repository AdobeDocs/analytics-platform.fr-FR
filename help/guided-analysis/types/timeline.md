---
title: Mode Chronologie
description: Observez les événements de session au niveau de l’utilisateur au fil du temps pour trouver des modèles d’expérience.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: e9721eaf993175dd46e9d8edf9176d7c00308e8c
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# Vue [!UICONTROL Chronologie]

La vue **[!UICONTROL Chronologie]** vous permet d’observer au fil du temps les événements de session au niveau de l’utilisateur afin de trouver des schémas d’expérience et de raconter de meilleures histoires d’utilisateur. Le rail de gauche vous permet de filtrer le flux par valeurs de propriété et par segments. Le rail de droite vous permet de sélectionner parmi une liste aléatoire d’utilisateurs qui correspondent aux critères de filtrage. La zone centrale affiche la diffusion pour l’utilisateur sélectionné par session, composée de l’horodatage, des valeurs de propriété et de la durée. La durée n’est pas disponible pour le dernier événement d’une session donnée.

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)

>[!NOTE]
>
>La vue de la chronologie requiert que le composant standard **[!UICONTROL ID de personne]** soit disponible dans la [ vue de données](/help/data-views/component-reference.md#optional). L’inclusion de l’ID de personne dans une vue de données est gérée par l’administrateur de votre Customer Journey Analytics, ce qui permet à votre organisation de contrôler pleinement la confidentialité de qui peut accéder à ces données.

Si le composant [!UICONTROL ID de personne] n’est pas ajouté à une vue de données, le message suivant s’affiche :

* **Admins** : *La propriété PersonID est requise pour cette analyse. Ajoutez l&#39;ID de personne à la vue de données.*
* **Non-administrateurs** : *La propriété PersonID est requise pour cette analyse. Veuillez travailler avec votre administrateur de Customer Journey Analytics pour ajouter un ID de personne à la vue de données.*

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Exploration des fragments** : si vous trouvez une forte baisse dans la vue [Friction](friction.md), vous pouvez créer un segment de ces utilisateurs et appliquer le segment dans cette vue pour étudier les causes potentielles.
* **Comportement d’erreur** : si les utilisateurs rencontrent une erreur de produit, vous pouvez explorer ce que les utilisateurs faisaient avant ou après avoir vu cette erreur.
* **Validation de la collecte de données** : les administrateurs de données peuvent filtrer cette vue sur leur propre ID de personne pour vérifier que l’implémentation de leur organisation fonctionne comme prévu.

## Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Propriété]** : propriété pour laquelle vous souhaitez afficher les valeurs en flux continu. Le flux au centre affiche les valeurs de la propriété sélectionnée. Vous pouvez également appliquer des filtres pour limiter le flux à des données plus pertinentes. Les opérateurs valides pour le filtre sont [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists] et [!UICONTROL Does not exists].
* **[!UICONTROL Segments]** : segment que vous souhaitez analyser. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment. Si vous souhaitez réduire la vue à un ID de personne spécifique, vous pouvez filtrer cet ID de personne ici. Un segment est pris en charge pour cette vue.

## Paramètres du graphique

La vue [!UICONTROL Chronologie] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Afficher comme]** : affiche les valeurs de propriété souhaitées.
   * [!UICONTROL Afficher tout] : affiche toutes les valeurs de propriété dans une session.
   * [!UICONTROL Highlight] : surligne visuellement les valeurs de propriété d’une session qui correspondent aux filtres de requête.
   * [!UICONTROL Afficher uniquement] : afficher uniquement les valeurs de propriété dans une session qui correspondent aux filtres de requête.

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les vues qui n’ont pas de tendance, telles que la chronologie.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
