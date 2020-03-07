---
title: FAQ sur les analyses de parcours du client
description: Analyse du parcours du client - Questions fréquentes.
translation-type: tm+mt
source-git-commit: cca701c2a18d094ee4b172b032c125e710b51ff0

---


# Questions fréquentes

| Question | Réponse |
|---|---|
| **Conditions préalables** |  |
| Avez-vous besoin d&#39;un graphique de périphérique ou d&#39;une copie de périphérique pour les analyses de parcours des clients ? | Non, le graphique de périphérique privé ou le code de périphérique ne sont pas nécessaires pour les analyses de parcours du client. En fait, ils ne sont pas encore soutenus. |
| Avez-vous besoin de l’ID Experience Cloud (ECID) pour les analyses de parcours des clients ? | Non, les analyses de parcours du client prennent en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse de l’ECID ou de tout autre identifiant que vous choisissez. |
| Que se passe-t-il si vous avez besoin d’ETL de vos données avant l’analyse du parcours du client ? | Aujourd&#39;hui, vous devez travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les placer dans AEP. Si vous avez besoin d’ETL après l’assimilation des données, AEP Services propose quelques options limitées. |
| **Rognage** |  |
| Les analyses de parcours du client peuvent-elles &quot;assembler&quot; des périphériques ou des jeux de données ? | Non. Les analyses de parcours du client sont un système d’analyse &quot;d’acquisition de votre propre ID&quot;. Des plans pour une bonne approche de couture sont en cours d&#39;élaboration. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |
| **Obtention de données dans les analyses de parcours du client** |  |
| Quelle est la latence attendue pour la plate-forme Analyse du parcours du client ? | <ul><li>Sous charge normale: &lt; 60<br>**minutesRemarque :**Dans le cas d’un volume de données exceptionnellement élevé qui traverserait le pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Données de renvoi (jusqu’à 10 milliards de ) : &lt; 4 semaines</li></ul> |
| Comment connectez-vous les données en ligne aux données hors ligne dans les analyses de parcours du client ? | Les analyses de parcours du client sont un système d’analyse &quot;Apportez vos propres identifiants&quot;. Tant que l’ID de personne correspond entre les jeux de données, les analyses de parcours du client peuvent lier des segments, l’attribution, le flux, les abandons, etc. entre des jeux de données. |
| Comment puis-je importer mes données hors ligne dans les analyses de parcours du client ? | Les clients doivent d’abord apporter des données à AEP avant de pouvoir les utiliser avec les analyses de parcours des clients. L’équipe d’intégration des données de la plate-forme d’expérience peut vous aider à formuler des recommandations ou à consulter les clients, le cas échéant. |
| Comment puis-je intégrer des données Analytics dans les analyses de parcours des clients ? | Les données Analytics peuvent être connectées à AEP par le biais du connecteur de données Analytics. La plupart des champs Analytics sont transférés au format XDM, mais d’autres champs ne sont pas encore disponibles (comme les dimensions de l’marketing). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans un  de données ? | Quelques heures pour commencer, et quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données d’identification personnelle pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID de client, qui n’est pas une identification personnelle. |
| **Composants Analytics traditionnels** |  |
| Qu’est-ce que cela signifie pour notre produit Adobe Analytics traditionnel ? | Les analyses de parcours client sont notre produit d’analyse de nouvelle génération. L’évolution de nos produits actuels vers les analyses de parcours des clients prendra des années et une grande coordination. Cette version est un grand pas dans cette direction. |
| Puis-je partager des segments de l’analyse du parcours du client vers AEP ou d’autres solutions ? | Pas encore. Nous étudions de nouvelles façons innovantes de partager, à l’avenir, des segments de l’analyse du parcours du client vers l’AEP qui n’ont pas un si long délai. Cela dit, vous pouvez partager la sortie des  de services avec les unifiés comme solution potentielle. |
| Qu’est-il advenu de mon ancien paramètre d’eVar ? | Les eVars, les props et les  de dans le sens traditionnel d’Adobe Analytics n’existent plus dans les analyses de parcours du client. Vous disposez d’un nombre illimité d’éléments  (dimensions, mesures, champs de). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au  du moment. |
| Où sont maintenant tous les paramètres de persistance de la session et de la variable ? | Les analyses de parcours du client appliquent tous ces paramètres au moment du rapport. Ces paramètres résident désormais dans les  de données. Les modifications apportées à ces paramètres sont désormais rétroactives et vous pouvez avoir plusieurs versions en utilisant plusieurs  de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | Les analyses de parcours du client n’utilisent plus d’eVars, de props ou de  et utilisent à la place un AEP. Cela signifie qu’aucun des segments ou mesures calculées existants n’est compatible avec les analyses de parcours du client. |
| Comment les analyses de parcours du client gèrent-elles `Uniques Exceeded` les limitations ? | Les analyses de parcours du client n’ont aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un [!DNL Data Workbench] client existant, puis-je passer à Customer Journey Analytics dès maintenant ? | Ça dépend. Si vous comptez fortement sur le processus de client unifié (UCP), vous devrez attendre la mise en oeuvre de l’assemblage. Si vous avez déjà des taux d’authentification client élevés, ou si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, les analyses de parcours du client peuvent être tout à fait appropriées. |

