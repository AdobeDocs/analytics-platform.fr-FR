---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
translation-type: ht
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# Questions fréquentes

| Question | Réponse |
|---|---|
| **Conditions préalables** |  |
| Avez-vous besoin d’une représentation graphique des appareils ou de Device Co-op pour [!UICONTROL Customer Journey Analytics] ? | Non, une représentation graphique des appareils privés ou Device Co-op ne sont pas nécessaires pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Avez-vous besoin d’un Experience Cloud ID (ECID) pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un ECID ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si vous avez besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur vos données avant de recourir à Customer Journey Analytics ? | Vous devez désormais travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les importer dans AEP. Si vous avez besoin d’utiliser un processus ETL une fois les données assimilées, AEP Query Services offre quelques options limitées. |
| **Assemblage** |  |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » des périphériques ou des jeux de données ? | Non. [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Des plans pour une bonne approche d’assemblage sont en cours d’élaboration. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |
| **Obtention de données dans [!UICONTROL Customer Journey Analytics]** |  |
| Quelle est la latence attendue de [!UICONTROL Customer Journey Analytics] sur [!UICONTROL Experience Platform] ? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Données de renvoi (jusqu’à 10 milliards d’événements) : &lt; 4 semaines</li></ul> |
| Comment connecter les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Tant que l’ID de personne correspond entre les jeux de données, [!UICONTROL Customer Journey Analytics] peut lier les segments, l’attribution, le flux, les abandons, etc. dans des jeux de données. |
| Comment puis-je importer mes données hors ligne dans Customer Journey Analytics ? | Les clients doivent d’abord importer toutes leurs données dans Experience Platform avant de pouvoir les utiliser avec Customer Journey Analytics. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à destination des clients. |
| Comment puis-je intégrer des données Analytics dans Customer Journey Analytics ? | Les données Analytics peuvent être connectées à Experience Platform par le biais du connecteur de données d’Analytics. La plupart des champs Analytics sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles (comme les dimensions de canal marketing). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |
| **Composants Analytics classiques** |  |
| Qu’est-ce que cela signifie pour notre produit Adobe Analytics classique ? | Customer Journey Analytics est notre produit d’analyse de nouvelle génération. L’évolution de nos produits actuels vers Customer Journey Analytics prendra des années et demandera une grande coordination. Cette version est un grand pas dans cette direction. |
| Puis-je partager des segments de Customer Journey Analytics vers AEP ou vers d’autres solutions ? | Pas encore. Nous envisageons de nouvelles façons innovantes de partager, à l’avenir, des segments qui n’ont pas un si long délai de Customer Journey Analytics vers l’AEP. Cela dit, vous pouvez partager les résultats de Query Services vers Unified Profile comme solution de contournement potentielle. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans Customer Journey Analytics. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | Customer Journey Analytics applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | Customer Journey Analytics n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec Customer Journey Analytics. |
| Comment Customer Journey Analytics gère-t-il les limitations `Uniques Exceeded` ? | Customer Journey Analytics n’a aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à Customer Journey Analytics dès maintenant ? | Tout dépend. Si vous comptez fortement sur Unified Customer Process (UCP), vous devriez mieux attendre la mise en œuvre de l’assemblage. Si vous disposez déjà de taux d’authentification de clients élevés, si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, Customer Journey Analytics peut vous convenir. |

