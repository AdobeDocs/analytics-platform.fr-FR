---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
translation-type: tm+mt
source-git-commit: b0069e0f3528942620a6a69aaae1447f7452956f
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 40%

---


# Questions fréquentes

## Conditions préalables

| Question | Réponse |
| --- | --- |
| Est-ce que je dois [!UICONTROL Graphique de périphérique privé] ou [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | Non, [!UICONTROL Graphique de périphérique privé] ou [!UICONTROL Device Coop] ne sont pas nécessaires pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Est-ce que je dois [!UICONTROL ID Experience Cloud] (ECID) pour [!UICONTROL Customer Journey Analytics]? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un ECID ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si j’ai besoin d’ETL (Extraire, Transformer, Charger) mes données avant [!UICONTROL Customer Journey Analytics]? | Vous devez désormais travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les importer dans AEP. Si vous avez besoin d’ETL après l’assimilation des données, [!UICONTROL Adobe Experience Platform Requête Services] propose quelques options limitées. |

## Tracé des données

| Question | Réponse |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ? | Oui. [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Nous avons lancé une solution de couture en novembre 2020. En savoir plus. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |

## Transfert de données dans [!UICONTROL Customer Journey Analytics]

| Question | Réponse |
| --- | --- |
| Puis-je combiner des données différentes [!UICONTROL Adobe Experience Platform] sandbox dans un [!UICONTROL Customer Journey Analytics] connexion ? | Non, vous ne pouvez pas accéder aux données d’un environnement de test à un autre. Vous pouvez combiner uniquement des jeux de données situés dans le même environnement de test. [En savoir plus...](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Renvoi de données (jusqu’à 13 mois de données, quelle que soit leur taille) : &lt; 4 semaines</li></ul> |
| Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Tant que l’ID de personne correspond d’un jeu de données à un autre, [!UICONTROL Customer Journey Analytics] peut connecter les segments, l’attribution, le flux, les abandons, etc. d’un jeu de données à un autre. |
| Comment importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics]? | Vous devez d’abord apporter des données à l’Experience Platform avant de pouvoir les utiliser avec [!UICONTROL Customer Journey Analytics]. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit. |
| Comment obtenir [!UICONTROL Adobe Analytics] données dans [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] les données peuvent être connectées à l’Experience Platform via la variable [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html). Le plus [!UICONTROL Adobe Analytics] les champs sont transférés au format XDM, mais d’autres champs ne sont pas encore disponibles (comme [!UICONTROL Canaux marketing] dimensions). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |

## Traditionnel [!UICONTROL Adobe Analytics] composants

| Question | Réponse |
| --- | --- |
| Qu&#39;est-ce que cela signifie pour notre tradition [!UICONTROL Adobe Analytics] produit ? | [!UICONTROL Customer Journey Analytics est notre produit d’analyse de nouvelle génération. ] Évoluer de nos produits actuels à [!UICONTROL Customer Journey Analytics] il faudra des années et beaucoup de coordination. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Puis-je partager des segments à partir de [!UICONTROL Customer Journey Analytics] à AEP ou à d&#39;autres solutions ? | Pas encore. Nous étudions de nouveaux moyens innovants de partager des segments à partir de [!UICONTROL Customer Journey Analytics] à AEP dans le futur qui n&#39;a pas un si long délai. Cela dit, vous pouvez partager les résultats de Query Services vers Unified Profile comme solution de contournement potentielle. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements au sens traditionnel Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | [!UICONTROL Customer Journey Analytics applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. ] Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | [!UICONTROL Customer Journey Analytics n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. ] Cela signifie qu’aucun des segments ou mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. |
| Comment [!UICONTROL Customer Journey Analytics] manipuler `Uniques Exceeded` limitations ? | [!UICONTROL Customer Journey Analytics n’a aucune limite de valeur unique, donc pas besoin de vous en soucier !] |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à Customer Journey Analytics dès maintenant ? | Tout dépend. Si vous comptez fortement sur Unified Customer Process (UCP), vous devriez mieux attendre la mise en œuvre de l’assemblage. Si vous disposez déjà de taux d’authentification de clients élevés, si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, Customer Journey Analytics peut vous convenir. |

## Implications de la suppression de composants de données

En ce qui concerne la suppression, nous nous préoccupons de 6 éléments : sandbox, schéma, jeu de données, connexion, vue de données et projets Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Et si quelqu&#39;un... | Ça arrive... |
| --- | --- |
| Supprime un sandbox dans [!UICONTROL Adobe Experience Platform]? | La suppression d’un sandbox rompt les événements [!UICONTROL Customer Journey Analytics] se connecte à des jeux de données dans ce sandbox. Toutefois, les jeux de données de la CJA ne seront pas supprimés pour l&#39;instant. |
| Supprime un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma ? | [!UICONTROL Adobe Experience Platform] ne permet pas la suppression des schémas auxquels un ou plusieurs jeux de données sont associés. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Supprime un jeu de données dans [!UICONTROL Adobe Experience Platform]? | Aucune notification n’est envoyée dans [!UICONTROL Customer Journey Analytics]; toutefois, si les données en flux continu sont activées, plus aucune nouvelle donnée n’arrivera après la suppression des jeux de données.<br>En d’autres termes, si le paramètre **[!UICONTROL Importer automatiquement tous les nouveaux jeux de données dans cette connexion, à partir d&#39;aujourd&#39;hui]** dans le cas de la connexion activée, aucune nouvelle donnée n&#39;entrerait après la suppression des jeux de données. |
| Supprime un jeu de données dans [!UICONTROL Customer Journey Analytics]? | Actuellement, vous ne pouvez pas supprimer un jeu de données dans une connexion qui a été enregistrée. Vous devrez supprimer toute la connexion et tout le début. (Cependant, vous pouvez supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform]0) |
| Supprime un lot d’un jeu de données (dans [!UICONTROL Adobe Experience Platform]) ? | Si le lot a déjà été assimilé à [!UICONTROL Customer Journey Analytics], [!UICONTROL Customer Journey Analytics] ne sait pas actuellement que le lot a été supprimé. Si le lot n&#39;a pas été ingéré, il ne peut évidemment pas être ingéré une fois qu&#39;il a été supprimé dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **pendant qu&#39;il est ingéré** into [!UICONTROL Customer Journey Analytics]? | S&#39;il n&#39;y a qu&#39;un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot n&#39;apparaîtra dans [!UICONTROL Customer Journey Analytics]. L&#39;ingestion sera annulée. Si, par exemple, le jeu de données contient 5 lots et que 3 d&#39;entre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaîtront dans [!UICONTROL Customer Journey Analytics]. |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics]? | Un message d&#39;erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprime une vue de données dans [!UICONTROL Customer Journey Analytics]? | Un message d’erreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner. |
| Supprime un projet Workspace dans [!UICONTROL Customer Journey Analytics]? | Vous pouvez recréer le projet ou vous pouvez utiliser une solution pour récupérer le projet. Aller à [!UICONTROL > Admin > Journaux > Journal d’utilisation et des accès], recherchez le projet supprimé et copiez son ID. Ouvrez ensuite tout projet Workspace et mettez à jour l’identifiant dans l’URL avec le projet copié. Enregistrez ensuite le projet. |

