---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
translation-type: tm+mt
source-git-commit: 297ed03ff59cc8d719a6bf0984e82597e8d33392
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 69%

---


# Questions fréquentes

| Question | Réponse |
| --- | --- |
| **Conditions préalables** |  |
| Ai-je besoin d&#39;un graphique de périphérique ou d&#39;une coop de périphérique pour [!UICONTROL Customer Journey Analytics]? | Non, le graphique de périphérique privé ou la coop de périphérique ne sont pas requis pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Ai-je besoin d’un ID d’Experience Cloud (ECID) pour [!UICONTROL Customer Journey Analytics]? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel ID d’un jeu de données, qu’il s’agisse de l’ECID ou de tout autre ID que vous choisissez. |
| Que se passe-t-il si j&#39;ai besoin d&#39;ETL (Extraction, Transformer, Charger) mes données avant le Customer Journey Analytics ? | Vous devez désormais travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les importer dans AEP. Si vous avez besoin d’ETL après l’assimilation des données, AEP Requête Services propose quelques options limitées. |
| **Assemblage** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; sur les périphériques ou les jeux de données ? | Non. [!UICONTROL Customer Journey Analytics est un système d’analyse « bring your own ID ». ] Des plans pour une bonne approche d’assemblage sont en cours d’élaboration. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |
| **[!UICONTROL Obtention de données dans Customer Journey Analytics]** |  |
| Puis-je combiner des données provenant de différents sandbox Experience Platform dans une même connexion CJA ? | Non, vous ne pouvez pas accéder aux données dans les sandbox. Vous pouvez combiner uniquement des jeux de données situés dans le même sandbox. [En savoir plus...](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] on [!UICONTROL experience platform]? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Données de renvoi (jusqu’à 10 milliards d’événements) : &lt; 4 semaines.</li></ul> |
| Comment connecter des données en ligne à des données hors ligne dans [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics est un système d’analyse « bring your own ID ».] Tant que l&#39;ID de personne correspond entre les jeux de données, [!UICONTROL Customer Journey Analytics] peuvent connecter des segments, l’attribution, le flux, les abandons, etc. dans des jeux de données. |
| Comment puis-je importer mes données hors ligne dans Customer Journey Analytics ? | Vous devez d’abord apporter des données à l’Experience Platform avant de pouvoir les utiliser avec le Customer Journey Analytics. L’équipe de données à l’intégration de l’Experience Platform peut vous aider à formuler des recommandations ou à vous consulter, si nécessaire. |
| Comment puis-je intégrer des données Analytics dans Customer Journey Analytics ? | Les données Analytics peuvent être connectées à l’Experience Platform par le biais de la variable [Connecteur de données Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). La plupart des champs Analytics sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles (comme les dimensions de canal marketing). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |
| **Composants Analytics classiques** |  |
| Qu’est-ce que cela signifie pour notre produit Adobe Analytics classique ? | Customer Journey Analytics est notre produit d’analyse de nouvelle génération. L’évolution de nos produits actuels vers Customer Journey Analytics prendra des années et demandera une grande coordination. |
| Puis-je partager des segments de Customer Journey Analytics vers AEP ou vers d’autres solutions ? | Pas encore. Nous envisageons de nouvelles façons innovantes de partager, à l’avenir, des segments qui n’ont pas un si long délai de Customer Journey Analytics vers l’AEP. Cela dit, vous pouvez partager les résultats de Query Services vers Unified Profile comme solution de contournement potentielle. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans Customer Journey Analytics. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | Customer Journey Analytics applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | Customer Journey Analytics n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec Customer Journey Analytics. |
| Comment Customer Journey Analytics gère-t-il les limitations `Uniques Exceeded` ? | Customer Journey Analytics n’a aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à Customer Journey Analytics dès maintenant ? | Tout dépend. Si vous comptez fortement sur Unified Customer Process (UCP), vous devriez mieux attendre la mise en œuvre de l’assemblage. Si vous disposez déjà de taux d’authentification de clients élevés, si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, Customer Journey Analytics peut vous convenir. |

