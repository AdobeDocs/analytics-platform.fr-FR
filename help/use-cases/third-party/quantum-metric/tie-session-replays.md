---
title: La session Lier Quantum Metric est relue aux données dans Customer Journey Analytics
description: La session Lier Quantum Metric est relue avec les données de CJA pour mieux comprendre le « pourquoi » derrière le « quoi ».
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 2%

---

# La session Lier Quantum Metric est relue aux données dans Customer Journey Analytics

En liant les relectures de session de Quantum Metric aux données de CJA, les clients peuvent mieux comprendre « le pourquoi » derrière « le quoi ».  Workspace peut être utilisé pour découvrir des sessions avec friction, puis vous pouvez cliquer sur des ID de session liés pour explorer la relecture de session dans Quantum Metric.  Ces données permettent de visualiser le comportement au sein d’une session et de mieux comprendre ce qui génère les frictions chez les consommateurs.  Grâce aux relectures de session liées à CJA, vous pouvez capturer un contexte critique autour du comportement des clients dans votre expérience.

## Conditions préalables

Ces étapes supposent que vous utilisiez les balises dans la collecte de données Adobe Experience Platform. Vous pouvez adapter ces méthodes de collecte de données vers une implémentation manuelle de Web SDK si votre entreprise n’utilise pas de balises.

Pour plus d’informations, consultez la documentation de l’[extension de balise Quantum Metric](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

## Étape 1 : créer un champ de schéma pour s’adapter à l’ID de session Quantum Metric

Ce cas d’utilisation nécessite un champ de schéma dédié vers lequel envoyer des données. Vous pouvez créer ce champ à l’emplacement de votre choix dans votre schéma et le nommer comme vous le souhaitez. Des exemples de valeurs sont fournis si votre organisation n’a pas de préférence en matière de nom ou d’emplacement.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Schémas]**.
1. Sélectionnez le schéma souhaité dans la liste.
1. Sélectionnez l’icône ![Ajouter un champ](/help/assets/icons/AddCircle.svg) en regard de l’objet souhaité. Par exemple, en regard de `Implementation Details`.
1. Sur la droite, saisissez le [!UICONTROL Nom] souhaité. Par exemple : `qmSessionId`.
1. Saisissez le [!UICONTROL Nom d’affichage] souhaité. Par exemple : `Quantum Metric session ID`.
1. Sélectionnez le [!UICONTROL Type] en tant que **[!UICONTROL Chaîne]**.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Étape 2 : capturer l’ID de session de mesure quantique à l’aide de l’extension de balise de mesure quantique

Pour ajouter l’identifiant de session Quantum Metric aux données envoyées à Adobe Experience Platform, procédez comme suit.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à **[!UICONTROL Collecte de données]** > **[!UICONTROL Balises]**.
1. Sélectionnez la propriété de balise de votre choix.
1. Sélectionnez **[!UICONTROL Éléments de données]**, puis sélectionnez **[!UICONTROL Ajouter un élément de données]**.
1. Définissez les paramètres suivants :
   * **[!UICONTROL Nom]** : `Quantum Metric session ID`
   * **[!UICONTROL Extension]** : [!UICONTROL Core]
   * **[!UICONTROL Type d’élément de données]** : [!UICONTROL Code personnalisé]
1. Sélectionnez le bouton **[!UICONTROL Ouvrir l’éditeur]** et collez le code suivant :

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Étape 3 : mapper l’élément de données au champ de schéma XDM souhaité

Maintenant que l’élément de données a une logique pour obtenir la valeur souhaitée, mappez l’élément de données à l’objet XDM.

1. Dans la propriété de balise, sélectionnez **[!UICONTROL Éléments de données]**, puis sélectionnez l’élément de données qui héberge votre objet XDM.
1. Dans la colonne de droite de cet élément de données, accédez au chemin d’accès établi lors de la création du champ de schéma.
1. Définissez la valeur sur le nom de l’élément de données entouré de signes de pourcentage. Par exemple : `%Quantum Metric session ID%`.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Ajoutez une bibliothèque, puis publiez vos modifications dans l’environnement de production.

Si votre objet XDM est déjà inclus dans une configuration d’action d’événement d’envoi, vous commencerez à voir les données lorsque les modifications seront publiées.

>[!NOTE]
>
>Parfois, le SDK Web fonctionne plus rapidement que le code de mesure quantique. Dans ce cas, l’ID de session est envoyé à l’accès suivant. Si un visiteur rebondit, l’ID de session n’est pas collecté dans ces instances.

## Étape 3 : ajouter un ID de session de mesure quantique en tant que dimension disponible

Une fois les modifications ci-dessus publiées dans votre implémentation, modifiez votre vue de données existante pour ajouter l’ID de session en tant que dimension disponible dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Vues de données]** dans le menu supérieur.
1. Sélectionnez la vue de données existante souhaitée.
1. Recherchez le champ ID de session de Quantum Metric sur la gauche, puis faites-le glisser vers la zone des dimensions au centre.
1. Dans le volet de droite, définissez le paramètre [persistance](/help/data-views/component-settings/persistence.md) sur `Session`.
1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Étape 4 : configuration d’Analysis Workspace pour s’adapter à la dimension d’ID de session

Créez un tableau à structure libre dans Workspace et configurez-le afin que les valeurs d’ID de session soient liées directement à Quantum Metric.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Workspace]** dans le menu supérieur.
1. Sélectionnez un projet existant ou créez-en un.
1. Créez un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Faites glisser la dimension ID de session vers la zone de travail Workspace.
1. Cliquez avec le bouton droit sur l’en-tête de colonne de dimension, puis sélectionnez **[!UICONTROL Créer des liens hypertexte pour tous les éléments de dimension]**.
1. Sélectionnez **[!UICONTROL Créer une URL personnalisée]**.
1. Collez la structure d’URL suivante :

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Cliquez sur **[!UICONTROL Créer]**.

Chaque ID de session est désormais un lien cliquable. Voir [Créer des liens hypertexte dans un tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) pour plus d’informations sur l’ajout de liens hypertexte aux éléments de dimension Analysis Workspace.

![Relecture de session](assets/session-replay.png)

## Étape 5 : affichage des sessions depuis Customer Journey Analytics

Une fois que vous avez trouvé un segment intéressant que vous souhaitez explorer, vous pouvez l’appliquer au panneau qui comprend vos liens d’ID de session. Le tableau renvoie toutes les sessions de ce segment et vous pouvez cliquer sur l’une d’entre elles pour l’explorer davantage dans la mesure quantique.

Pour plus d’informations[&#x200B; consultez le &#x200B;](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) Guide d’entreprise sur la relecture de session sur Quantum Metric . Vous pouvez également contacter votre représentant du service clientèle de Quantum Metric ou soumettre une demande par le biais du portail [Quantum Metric Customer Request](https://community.quantummetric.com/s/public-support-page).
