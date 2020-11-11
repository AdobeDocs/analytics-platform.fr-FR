---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 43%

---


# Questions fréquentes

## Conditions préalables

| Question | Réponse |
| --- | --- |
| Dois-je utiliser [!UICONTROL Graphique de périphérique privé] ou [!UICONTROL Device Coop] pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Graphique de périphérique privé] ou [!UICONTROL Device Coop] n&#39;est pas requis pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Ai-je besoin de [!UICONTROL ID Experience Cloud] (ECID) pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un ECID ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si j’ai besoin d’ETL (Extraire, Transformer, Charger) mes données avant [!UICONTROL Customer Journey Analytics] ? | Vous devez désormais travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les importer dans AEP. Si vous avez besoin d’ETL après l’assimilation des données, [!UICONTROL Adobe Experience Platform Requête Services] offre certaines options limitées. |

## Tracé des données

| Question | Réponse |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ? | Oui. [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Nous avons lancé une solution de couture en novembre 2020. En savoir plus. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |

## Transfert de données dans [!UICONTROL Customer Journey Analytics]

| Question | Réponse |
| --- | --- |
| Puis-je combiner des données provenant de différents sandbox [!UICONTROL Adobe Experience Platform] dans une seule connexion [!UICONTROL Customer Journey Analytics] ? | Non, vous ne pouvez pas accéder aux données d’un environnement de test à un autre. Vous pouvez combiner uniquement des jeux de données situés dans le même environnement de test. [En savoir plus...](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] sur [!UICONTROL Adobe Experience Platform] ? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Renvoi de données (jusqu’à 13 mois de données, quelle que soit leur taille) : &lt; 4 semaines</li></ul> |
| Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Tant que l’ID de personne correspond d’un jeu de données à un autre, [!UICONTROL Customer Journey Analytics] peut connecter les segments, l’attribution, le flux, les abandons, etc. d’un jeu de données à un autre. |
| Comment importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | Vous devez d’abord apporter des données à l’Experience Platform avant de pouvoir les utiliser avec [!UICONTROL Customer Journey Analytics]. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit. |
| Comment puis-je obtenir des données [!UICONTROL Adobe Analytics] dans [!UICONTROL Customer Journey Analytics] ? | [!UICONTROL Les données ] Analytics d’Adobe peuvent être connectées à l’Experience Platform par le biais du connecteur [ source de la ](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html)Adobe Analytics. La plupart des champs [!UICONTROL Adobe Analytics] sont transférés au format XDM, mais d’autres champs ne sont pas encore disponibles (comme les dimensions [!UICONTROL Canaux marketing]). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |

## Composants traditionnels [!UICONTROL Adobe Analytics]

| Question | Réponse |
| --- | --- |
| Qu’est-ce que cela signifie pour notre produit traditionnel [!UICONTROL Adobe Analytics] ? | [!UICONTROL Customer Journey Analytics est notre produit d’analyse de nouvelle génération. ] L&#39;évolution de nos produits actuels vers [!UICONTROL Customer Journey Analytics] prendra des années et beaucoup de coordination. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Puis-je partager des segments de [!UICONTROL Customer Journey Analytics] vers AEP ou d’autres solutions ? | Pas encore. Nous étudions de nouvelles façons innovantes de partager des segments de [!UICONTROL Customer Journey Analytics] à AEP dans le futur qui n&#39;ont pas un si long délai. Cela dit, vous pouvez partager les résultats de Query Services vers Unified Profile comme solution de contournement potentielle. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, props et événements au sens traditionnel Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | [!UICONTROL Customer Journey Analytics applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. ] Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | [!UICONTROL Customer Journey Analytics n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. ] Cela signifie qu’aucun des segments ou mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. |
| Comment [!UICONTROL Customer Journey Analytics] gère-t-il `Uniques Exceeded` les limitations ? | [!UICONTROL Customer Journey Analytics n’a aucune limite de valeur unique, donc pas besoin de vous en soucier !] |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à Customer Journey Analytics dès maintenant ? | Tout dépend. Si vous comptez fortement sur Unified Customer Process (UCP), vous devriez mieux attendre la mise en œuvre de l’assemblage. Si vous disposez déjà de taux d’authentification de clients élevés, si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, Customer Journey Analytics peut vous convenir. |

## Implications de la suppression de composants de données

En ce qui concerne la suppression, nous nous préoccupons de 6 éléments : sandbox, schéma, jeu de données, connexion, vue de données et projets Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Et si je... | Ça arrive... |
| --- | --- |
| Supprimer un sandbox dans [!UICONTROL Adobe Experience Platform] ? | La suppression d&#39;un sandbox interrompt le flux de données vers toute connexion [!UICONTROL Customer Journey Analytics] aux jeux de données de ce sandbox. Actuellement, les connexions dans CJA liées à ce sandbox ne seront pas automatiquement supprimées. |
| Supprimer un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma ? | [!UICONTROL Adobe Experience ] Plateforme n’autorise pas la suppression des schémas associés à un ou plusieurs jeux de données. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform] ? | La suppression d&#39;un jeu de données dans AEP interrompt le flux de données de ce jeu de données vers les connexions qui incluent ce jeu de données. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] ? | Actuellement, vous ne pouvez pas supprimer un jeu de données dans une connexion qui a été enregistrée. Vous devrez supprimer toute la connexion et tout le début. (Cependant, vous pouvez supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform].) |
| Supprimer un lot d&#39;un jeu de données (dans [!UICONTROL Adobe Experience Platform]) ? | Si un lot est supprimé d&#39;un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toutes les connexions CJA qui contiennent ce lot spécifique.  La CJA est informée des suppressions de lots dans [!UICONTROL Adobe Experience Platform]. |
| Supprimez un lot **lorsqu&#39;il est ingéré** dans [!UICONTROL Customer Journey Analytics] ? | S&#39;il n&#39;y a qu&#39;un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot n&#39;apparaîtra dans [!UICONTROL Customer Journey Analytics]. L&#39;ingestion sera annulée. Si, par exemple, le jeu de données contient 5 lots et que 3 d&#39;entre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprimer une connexion dans [!UICONTROL Customer Journey Analytics] ? | Un message d&#39;erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprimer une vue de données dans [!UICONTROL Customer Journey Analytics] ? | Un message d’erreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner. |
