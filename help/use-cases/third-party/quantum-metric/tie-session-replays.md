---
title: La session Lier Quantum Metric est relue aux données dans Customer Journey Analytics
description: La session Lier Quantum Metric est relue avec les données de CJA pour mieux comprendre le « pourquoi » derrière le « quoi ».
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---

# La session Lier Quantum Metric est relue aux données dans Customer Journey Analytics

En liant les relectures de session de Quantum Metric aux données de CJA, les clients peuvent mieux comprendre « le pourquoi » derrière « le quoi ».  Workspace peut être utilisé pour découvrir des sessions avec friction, puis vous pouvez cliquer sur des ID de session liés pour explorer la relecture de session dans Quantum Metric.  Ces données permettent de visualiser le comportement au sein d’une session et de mieux comprendre ce qui génère les frictions des consommateurs.  Grâce aux relectures de session liées à CJA, vous pouvez capturer un contexte critique autour du comportement des clients dans votre expérience.

## Conditions préalables

Ces étapes supposent que vous utilisiez les balises dans la collecte de données Adobe Experience Platform. Vous pouvez adapter ces méthodes de collecte de données vers une implémentation manuelle de Web SDK si votre entreprise n’utilise pas de balises.

Pour plus d’informations, consultez la documentation de l’[extension de balise Quantum Metric](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

## Étape 1 : capturer l’ID de session de mesure quantique à l’aide de l’extension de balises de mesure quantique

Pour ajouter l’identifiant de session Quantum Metric aux données envoyées à Adobe Experience Platform, procédez comme suit.

1. Utilisez l’extension Quantum Metric dans l’interface utilisateur des balises pour envoyer des données à Quantum Metric.
1. Créez quatre éléments de données :
   1. Un qui capture l’ID de session de Quantum Metric à partir du cookie de Quantum Metric nommé `QuantumMetricSessionID`
   1. Un qui extrait l’ID de session de Quantum Metric à partir de `localStorage`. Parfois, cet élément de données se charge plus rapidement que le cookie défini dans l’autre élément de données.
   1. Utilisez l’assistant d’élément de données ou un JavaScript personnalisé pour extraire le nœud de `s` de l’élément de données `localStorage`.
   1. Une qui utilise la logique pour rechercher d’abord l’élément de données de cookie et le renvoyer à un chemin d’objet XDM s’il est trouvé. Si non défini, essayez de rechercher l’élément de données de l’objet `localStorage` extrait.
1. Envoyez l’élément de données d’identifiant de session Quantum Metric final à l’objet XDM envoyé dans chaque événement.

>[!NOTE]
>Parfois, le SDK Web fonctionne plus rapidement que le code de mesure quantique. Dans ce cas, l’ID de session est envoyé à l’accès suivant. Si un visiteur rebondit, l’ID de session n’est pas collecté dans ces instances.

## Étape 2 : confirmer les champs du jeu de données inclus

Vérifiez que les jeux de données de votre connexion possèdent désormais l’ID de session de mesure quantique dans le jeu de données souhaité.

## Étape 3 : ajouter un ID de session de mesure quantique en tant que dimension disponible

Modifiez la vue de données existante pour ajouter l’ID de session en tant que dimension disponible dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Vues de données]** dans le menu supérieur.
1. Sélectionnez la vue de données existante souhaitée.
1. Recherchez la liste du champ d’ID de session de mesure quantique sur la gauche, puis faites-la glisser vers la zone des dimensions au centre.
1. Dans le volet de droite, définissez le paramètre [persistance](/help/data-views/component-settings/persistence.md) sur « Session ».
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Étape 4 : configurer Workspace pour prendre en compte la dimension d’ID de session

Créez un tableau à structure libre dans Workspace et configurez-le de sorte que les valeurs d’ID de session soient des liens directs vers Quantum Metric.

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

## Étape 5 : affichage des sessions depuis Customer Journey Analytics

Une fois que vous avez trouvé un segment intéressant que vous souhaitez explorer, vous pouvez l’appliquer au panneau qui comprend vos liens d’ID de session et le filtrer par segment. Le tableau renvoie toutes les sessions de ce segment et vous pouvez cliquer sur l’une d’entre elles pour l’explorer davantage dans la mesure quantique.

Pour plus d’informations](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) consultez le [ Guide d’entreprise sur la relecture de session sur Quantum Metric . Vous pouvez également contacter votre représentant du service clientèle de Quantum Metric ou soumettre une demande par le biais du portail [Quantum Metric Customer Request](https://community.quantummetric.com/s/public-support-page).
