---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
translation-type: tm+mt
source-git-commit: eb7d7d80ee07298f7d0fe308bdc93a3435f2c381
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 96%

---


# Questions fréquentes

| Question | Réponse |
| --- | --- |
| **Conditions préalables** |  |
| Ai-je besoin d’une représentation graphique des appareils ou de Device Co-op pour [!UICONTROL Customer Journey Analytics] ? | Non, une représentation graphique des appareils privés ou Device Co-op ne sont pas nécessaires pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Ai-je besoin d’un Experience Cloud ID (ECID) pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un ECID ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si j’ai besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur mes données avant de recourir à Customer Journey Analytics ? | Vous devez désormais travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les importer dans AEP. Si vous avez besoin d’utiliser un processus ETL alors que les données ont déjà été assimilées, AEP Query Services offre quelques options limitées. |
| **Assemblage** |  |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ? | Non. [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Des plans pour une bonne approche d’assemblage sont en cours d’élaboration. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |
| **Transfert de données dans [!UICONTROL Customer Journey Analytics]** |  |
| Puis-je combiner des données provenant de différents environnements de test Experience Platform dans une même connexion de CJA ? | Non, vous ne pouvez pas accéder aux données d’un environnement de test à un autre. Vous pouvez combiner uniquement des jeux de données situés dans le même environnement de test. [En savoir plus...](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] sur [!UICONTROL Experience Platform] ? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Renvoi de données (jusqu’à 13 mois de données, quelle que soit leur taille) : &lt; 4 semaines</li></ul> |
| Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Tant que l’ID de personne correspond d’un jeu de données à un autre, [!UICONTROL Customer Journey Analytics] peut connecter les segments, l’attribution, le flux, les abandons, etc. d’un jeu de données à un autre. |
| Comment puis-je importer mes données hors ligne dans Customer Journey Analytics ? | Vous devez d’abord importer toutes leurs données dans Experience Platform avant de pouvoir les utiliser avec Customer Journey Analytics. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit. |
| Comment puis-je intégrer des données Analytics dans Customer Journey Analytics ? | Les données Analytics peuvent être connectées à Experience Platform par le biais du [connecteur de données d’Analytics](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html). La plupart des champs Analytics sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles (comme les dimensions de canal marketing). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |
| **Composants Analytics classiques** |  |
| Qu’est-ce que cela signifie pour notre produit Adobe Analytics classique ? | Customer Journey Analytics est notre produit d’analyse de nouvelle génération. L’évolution de nos produits actuels vers Customer Journey Analytics prendra des années et demandera une grande coordination. Pour plus d’informations, consultez [Prise en charge des fonctionnalités Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Puis-je partager des segments de Customer Journey Analytics vers AEP ou vers d’autres solutions ? | Pas encore. Nous envisageons de nouvelles façons innovantes de partager, à l’avenir, des segments qui n’ont pas un si long délai de Customer Journey Analytics vers l’AEP. Cela dit, vous pouvez partager les résultats de Query Services vers Unified Profile comme solution de contournement potentielle. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans Customer Journey Analytics. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | Customer Journey Analytics applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | Customer Journey Analytics n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec Customer Journey Analytics. |
| Comment Customer Journey Analytics gère-t-il les limitations `Uniques Exceeded` ? | Customer Journey Analytics n’a aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à Customer Journey Analytics dès maintenant ? | Tout dépend. Si vous comptez fortement sur Unified Customer Process (UCP), vous devriez mieux attendre la mise en œuvre de l’assemblage. Si vous disposez déjà de taux d’authentification de clients élevés, si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, Customer Journey Analytics peut vous convenir. |

