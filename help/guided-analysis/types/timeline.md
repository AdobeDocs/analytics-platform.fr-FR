---
title: Mode Chronologie
description: Explorez les modèles dans l’activité de session.
feature: Guided Analysis
keywords: analytics du produit
role: User
source-git-commit: ecdbe1b68aa0824bd9db4acefd3ef9059d9ac927
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# [!UICONTROL Chronologie] view

La variable **[!UICONTROL Chronologie]** vous permet d’analyser des sessions individuelles afin de déterminer les schémas de comportement. Le rail droit vous permet de sélectionner l’ID de personne à analyser. La zone centrale affiche l’heure, la valeur de propriété sélectionnée et la durée de chaque événement de cette personne.

Cette analyse requiert que vous ajoutiez la variable **[!UICONTROL ID de personne]** du composant standard [vue des données](/help/data-views/component-reference.md#optional). Si vous ne disposez pas de la variable [!UICONTROL ID de personne] ajouté à la vue de données, le message suivant s’affiche :

> La propriété PersonID est requise pour cette analyse. Ajoutez PersonID à la vue de données.

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Exploration des fragments**: si vous constatez une forte baisse dans la variable [Friction](friction.md) vous pouvez étudier les causes potentielles de cette perte à l’aide de cette vue.
* **Comportement d’erreur**: si les utilisateurs rencontrent une erreur dans votre produit, vous pouvez explorer ce que les utilisateurs font avant ou après avoir vu cette erreur.
* **Validation de la collecte de données**: les administrateurs de données peuvent filtrer cette vue pour s’isoler. Cette vue fournit un moyen fiable de s’assurer que la mise en oeuvre de votre entreprise fonctionne comme prévu.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Propriété]**: propriété pour laquelle vous souhaitez afficher des valeurs. L’analyse de session au centre affiche les valeurs de la propriété sélectionnée ici. Vous pouvez également filtrer les données selon la propriété sélectionnée. Les opérateurs valides pour le filtre incluent : [!UICONTROL Est égal à], [!UICONTROL N’est pas égal à], [!UICONTROL Commence par], [!UICONTROL Se termine par], [!UICONTROL Contient], [!UICONTROL Ne contient pas], [!UICONTROL Existe], et [!UICONTROL N’existe pas].
* **[!UICONTROL Segments]**: segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment. Un segment est pris en charge pour cette vue.

## Paramètres du graphique

La variable [!UICONTROL Chronologie] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Afficher sous]**: affiche les valeurs de propriété souhaitées.
   * [!UICONTROL Tout afficher]
   * [!UICONTROL Surligner]
   * [!UICONTROL Afficher uniquement]

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les vues qui n’ont pas de tendance, telles que la chronologie.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
