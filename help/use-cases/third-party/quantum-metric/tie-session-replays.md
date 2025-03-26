---
title: La session Lier Quantum Metric est relue aux données dans Customer Journey Analytics
description: La session Lier Quantum Metric est relue avec les données de CJA pour mieux comprendre le « pourquoi » derrière le « quoi ».
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 9563b13da52963eaf7b17050fb9a7cb3a47ef1ed
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---

# La session Lier Quantum Metric est relue aux données dans Customer Journey Analytics

En liant les relectures de session de Quantum Metric aux données de CJA, les clients peuvent mieux comprendre « le pourquoi » derrière « le quoi ».  Workspace peut être utilisé pour découvrir des sessions avec friction, puis vous pouvez cliquer sur des ID de session liés pour explorer la relecture de session dans Quantum Metric.  Ces données permettent de visualiser le comportement au sein d’une session et de mieux comprendre ce qui génère les frictions des consommateurs.  Grâce aux relectures de session liées à CJA, vous pouvez capturer un contexte critique autour du comportement des clients dans votre expérience.

## Conditions préalables :

Ce cas d’utilisation nécessite de collecter l’ID de session de Quantum Metric avec le reste de votre implémentation. Voir [Collecter des identifiants de session de mesure quantique dans Customer Journey Analytics](collect-session-id.md) pour savoir comment modifier votre implémentation.

## Étape 1 : configurer Workspace pour tenir compte de la dimension d’ID de session

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

## Étape 2 Affichage des sessions à partir de Customer Journey Analytics

Une fois que vous avez trouvé un segment intéressant pour lequel vous souhaitez explorer les relectures de session, vous pouvez l’appliquer au panneau qui inclut vos liens d’ID de session et le filtrer par segment. Le tableau renvoie toutes les sessions de ce segment. Vous pouvez cliquer sur l’une d’elles pour l’explorer davantage dans Quantum Metric.

En savoir plus sur la relecture de session de Quantum Metric sur [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay). Pour toute ressource supplémentaire, veuillez contacter votre représentant du service clientèle de Quantum Metric ou soumettre une demande par le biais de Quantum Metric [Portail de demandes client](https://community.quantummetric.com/s/public-support-page).

