---
title: Mode Chronologie
description: Explorez les schémas d’expérience et racontez de meilleures histoires d’utilisateurs.
feature: Guided Analysis
keywords: analytics du produit
role: User
source-git-commit: d7e1092e1b2b4e9decd8d601c4b6415b13f1e02a
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# [!UICONTROL Chronologie] view

La variable **[!UICONTROL Chronologie]** vous permet d’observer les événements de session au niveau de l’utilisateur au fil du temps afin de trouver des schémas d’expérience et de raconter de meilleures histoires d’utilisateurs. Le rail de gauche vous permet de filtrer les valeurs de propriété que vous souhaitez diffuser et le rail de droite vous permet de sélectionner l’ID de personne à analyser. La zone centrale affiche le flux par session, composée de l’horodatage, des valeurs de propriété et de la durée. Notez que la durée n’est pas disponible pour le dernier événement d’une session donnée.

>[!NOTE]
>
>La vue Chronologie requiert que la variable **[!UICONTROL ID de personne]** le composant standard doit être disponible dans la fonction [vue des données](/help/data-views/component-reference.md#optional). L’inclusion de l’ID de personne dans une vue de données est gérée par votre administrateur de données Adobe Analytics, ce qui permet aux entreprises de contrôler pleinement la confidentialité de qui peut accéder à ces données.

Si une vue de données ne comporte pas la variable [!UICONTROL ID de personne] ajouté, le message suivant s’affiche :
* **Administrateurs**: la propriété PersonID est requise pour cette analyse. Ajoutez l’ID de personne à la vue de données.
* **Non-administrateurs**: la propriété PersonID est requise pour cette analyse. Contactez votre administrateur de Customer Journey Analytics pour ajouter un ID de personne à la vue de données.

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Exploration des fragments**: si vous constatez une forte baisse dans la variable [Friction](friction.md) vous pouvez créer un segment de ces utilisateurs et l’appliquer dans cette vue pour étudier les causes potentielles.
* **Comportement d’erreur**: si les utilisateurs rencontrent une erreur de produit, vous pouvez explorer ce que les utilisateurs faisaient avant ou après avoir vu cette erreur.
* **Validation de la collecte de données**: les administrateurs de données peuvent filtrer cette vue sur leur propre ID de personne et l’utiliser pour vérifier que l’implémentation de votre entreprise fonctionne comme prévu.

## Rail de requêtes

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Propriété]**: propriété pour laquelle vous souhaitez afficher les valeurs en flux continu. Le flux au centre affiche les valeurs de la propriété sélectionnée. Vous pouvez également appliquer des filtres pour réduire le flux afin d’obtenir des données plus pertinentes. Les opérateurs valides pour le filtre incluent : [!UICONTROL Est égal à], [!UICONTROL N’est pas égal à], [!UICONTROL Commence par], [!UICONTROL Se termine par], [!UICONTROL Contient], [!UICONTROL Ne contient pas], [!UICONTROL Existe], et [!UICONTROL N’existe pas].
* **[!UICONTROL Segments]**: segment que vous souhaitez analyser. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment. Si vous souhaitez réduire la vue à un ID de personne spécifique, vous pouvez filtrer cet ID de personne ici. Un segment est pris en charge pour cette vue.

## Paramètres du graphique

La variable [!UICONTROL Chronologie] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Afficher sous]**: affiche les valeurs de propriété souhaitées.
   * [!UICONTROL Tout afficher]: affiche toutes les valeurs de propriété d’une session.
   * [!UICONTROL Surligner]: permet de mettre visuellement en surbrillance les valeurs de propriété d’une session qui correspondent aux filtres de requête.
   * [!UICONTROL Afficher uniquement]: affiche uniquement les valeurs de propriété dans une session qui correspondent aux filtres de requête.

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les vues qui n’ont pas de tendance, telles que la chronologie.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
