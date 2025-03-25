---
title: Utiliser des cartes thermiques de mesure quantique avec Customer Journey Analytics
description: Comprenez mieux l’engagement au niveau des pages et optimisez les pages en fonction du comportement des consommateurs à l’aide des données de carte thermique Quantum Metric.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: b82a345fbae1a0ab2debf2c4eb580422745db473
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---

# Utiliser des cartes thermiques de mesure quantique avec Customer Journey Analytics

La liaison de la correspondance de chaleur de Quantum Metric aux données CJA permet de mieux comprendre l’engagement au niveau des pages et d’optimiser les pages en fonction du comportement des consommateurs. Workspace peut être utilisé pour comprendre les flux d’utilisateurs consommateurs et consommatrices et pour voir quels chemins les consommateurs et consommatrices suivent d’une page à l’autre. Vous pouvez ensuite cliquer sur les URL de page liées pour afficher une carte thermique de la manière dont les utilisateurs et utilisatrices interagissent avec le contenu.  En associant Quantum Metric Heatmapping à CJA, vous pouvez désormais associer des interactions au niveau de la page à des résultats commerciaux, faisant passer votre analyse au niveau supérieur.

Le tableau renvoie toutes les sessions de ce segment. Vous pouvez cliquer sur l’une d’elles pour l’explorer davantage dans AEM.  Pour en savoir plus sur la relecture de session de Quantum Metric, consultez https://www.quantummetric.com/platform/session-replay

## Conditions préalables

Ce cas d’utilisation nécessite de collecter l’ID de session de Quantum Metric avec le reste de votre implémentation. Voir [Collecter des identifiants de session de mesure quantique dans Customer Journey Analytics](collect-session-id.md) pour savoir comment modifier votre implémentation.

Pour accéder aux fonctionnalités de carte thermique de Quantum Metric, vous devez disposer du package **UX Ops**.

## Créez un tableau à structure libre dans Workspace et configurez-le de sorte que les valeurs d’ID de session soient des liens directs vers Quantum Metric.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Workspace]** dans le menu supérieur.
1. Sélectionnez un projet existant ou créez-en un.
1. Créez un [tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Faites glisser la dimension URL de la page vers la zone de travail Workspace.
1. Cliquez avec le bouton droit sur l’en-tête de colonne de dimension, puis sélectionnez **[!UICONTROL Créer des liens hypertexte pour tous les éléments de dimension]**.
1. Sélectionnez **[!UICONTROL Créer une URL personnalisée]**.
1. Collez la structure d’URL suivante :

   ```
   $value?qm-visible=true
   ```

1. Cliquez sur **[!UICONTROL Créer]**.

1. Cliquez sur Créer , puis testez l’un des liens pour voir s’il s’ouvre dans l’URL avec l’extension AEM affichée. Remarque : elle s’ouvre dans un onglet distinct, afin que vous ne perdiez pas votre travail.


## Affichage des cartes thermiques en cliquant sur des liens dans Customer Journey Analytics

Une fois que vous avez trouvé une page pour laquelle vous souhaitez explorer la cartographie thermique, vous pouvez l’appliquer au panneau dans lequel se trouve votre URL. Le tableau renvoie une URL qui vous permet d’explorer les cartes thermiques de la page en question, la profondeur de défilement et les zones clés pour l’interaction.  Pour en savoir plus sur les cartes thermiques de mesure quantique, consultez [https://www.quantummetric.com/platform/interaction-heatmaps](https://www.quantummetric.com/platform/interaction-heatmaps).  Pour toute ressource supplémentaire, veuillez contacter votre représentant du service clientèle de Quantum Metric ou soumettre une demande par le biais de Quantum Metric [Portail de demandes client](https://community.quantummetric.com/s/public-support-page).


