---
title: Mode Chronologie
description: Observez les événements de session au niveau de l’utilisateur au fil du temps pour trouver des modèles d’expérience.
feature: Guided Analysis
keywords: analytics du produit
role: User
source-git-commit: 6f3725653453e31244bfed34670782fe9d9c0c2f
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 1%

---

# [!UICONTROL Chronologie] view

La variable **[!UICONTROL Chronologie]** vous permet d’observer les événements de session au niveau de l’utilisateur au fil du temps afin de trouver des schémas d’expérience et de raconter de meilleures histoires d’utilisateurs. Le rail de gauche vous permet de filtrer le flux par valeurs de propriété et par segments. Le rail de droite vous permet de sélectionner parmi une liste aléatoire d’utilisateurs qui correspondent aux critères de filtrage. La zone centrale affiche la diffusion pour l’utilisateur sélectionné par session, composée de l’horodatage, des valeurs de propriété et de la durée. La durée n’est pas disponible pour le dernier événement d’une session donnée.

>[!NOTE]
>
>La vue Chronologie requiert que la variable **[!UICONTROL ID de personne]** le composant standard doit être disponible dans la fonction [vue des données](/help/data-views/component-reference.md#optional). L’inclusion de l’ID de personne dans une vue de données est gérée par l’administrateur de votre Customer Journey Analytics, ce qui permet à votre organisation de contrôler pleinement la confidentialité de qui peut accéder à ces données.

Si une vue de données ne comporte pas la variable [!UICONTROL ID de personne] ajouté, le message suivant s’affiche :

* **Administrateurs**: *La propriété PersonID est requise pour cette analyse. Ajoutez l’ID de personne à la vue de données.*
* **Non-administrateurs**: *La propriété PersonID est requise pour cette analyse. Contactez votre administrateur de Customer Journey Analytics pour ajouter un ID de personne à la vue de données.*

![Capture d’écran de la chronologie](../assets/timeline.png)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Exploration des fragments**: si vous constatez une forte baisse dans la variable [Friction](friction.md) vous pouvez créer un segment de ces utilisateurs et l’appliquer dans cette vue pour étudier les causes potentielles.
* **Comportement d’erreur**: si les utilisateurs rencontrent une erreur de produit, vous pouvez explorer ce que les utilisateurs faisaient avant ou après avoir vu cette erreur.
* **Validation de la collecte de données**: les administrateurs de données peuvent filtrer cette vue sur leur propre ID de personne pour vérifier que l’implémentation de leur entreprise fonctionne comme prévu.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Propriété]**: propriété pour laquelle vous souhaitez afficher les valeurs en flux continu. Le flux au centre affiche les valeurs de la propriété sélectionnée. Vous pouvez également appliquer des filtres pour limiter le flux à des données plus pertinentes. Les opérateurs valides pour le filtre incluent : [!UICONTROL Est égal à], [!UICONTROL N’est pas égal à], [!UICONTROL Commence par], [!UICONTROL Se termine par], [!UICONTROL Contient], [!UICONTROL Ne contient pas], [!UICONTROL Existe], et [!UICONTROL N’existe pas].
* **[!UICONTROL Segments]**: segment que vous souhaitez analyser. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment. Si vous souhaitez réduire la vue à un ID de personne spécifique, vous pouvez filtrer cet ID de personne ici. Un segment est pris en charge pour cette vue.

## Paramètres du graphique

La variable [!UICONTROL Chronologie] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Afficher sous]**: affiche les valeurs de propriété souhaitées.
   * [!UICONTROL Tout afficher]: affiche toutes les valeurs de propriété d’une session.
   * [!UICONTROL Surligner]: met visuellement en surbrillance les valeurs de propriété d’une session qui correspondent aux filtres de requête.
   * [!UICONTROL Afficher uniquement]: affiche uniquement les valeurs de propriété dans une session qui correspondent aux filtres de requête.

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les vues qui n’ont pas de tendance, telles que la chronologie.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
