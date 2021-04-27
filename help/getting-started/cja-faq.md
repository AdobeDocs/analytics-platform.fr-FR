---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 5667e2f43873061c5350c75fdb830a95b1c9b73f
workflow-type: tm+mt
source-wordcount: '1368'
ht-degree: 60%

---

# Questions fréquentes

[!UICONTROL Customer Journey Analytics]  (CJA) est notre produit d’analyse de nouvelle génération. Vous trouverez ci-dessous les réponses aux questions les plus fréquentes sur la MCJ. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/cja-aa.md).

## 1. Conditions préalables

| Question | Réponse |
| --- | --- |
| Ai-je besoin d’un [!UICONTROL graphique d’appareil privé] ou d’un [!UICONTROL graphique d’appareil Coop] pour [!UICONTROL Customer Journey Analytics] ? | Non, un [!UICONTROL graphique d’appareil privé] ou d’[!UICONTROL appareil Coop] n’est pas nécessaire pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Ai-je besoin d’un [!UICONTROL Experience Cloud ID] (ECID) pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un [!UICONTROL ECID] ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si jʼai besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur mes données avant de recourir à [!UICONTROL Customer Journey Analytics] ? | Le Customer Journey Analytics comprend des fonctions [Prép de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html) pour aider à transformer vos données avant de les placer dans le lac de données Adobe Experience Platform. Si vous avez besoin d&#39;ETL après l&#39;assimilation des données, [Adobe Experience Platform Requête Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries) offre certaines options limitées, bien qu&#39;il puisse y avoir des frais supplémentaires. |

{style=&quot;table-layout:auto&quot;}

## 2. Collage des données (analyses entre Canaux)

| Question | Réponse |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ? | Oui. [!UICONTROL L’] analyse du Parcours client constitue une solution de raccordement appelée analyse [](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)  des Canaux croisés (CCA). Il vous permet de recréer l’identifiant personnel d’un jeu de données, ce qui permet une combinaison transparente de plusieurs jeux de données. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Oui. [Analyses entre Canaux ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un identifiant assemblé. |
| Comment fonctionne le &quot;replay&quot; dans la DPA ? | La DPA &quot;relaie&quot; les données en fonction des identifiants uniques qu&#39;elle a appris. La réexécution entraîne l&#39;assemblage de nouveaux périphériques à la connexion. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| Comment l&#39;assemblage de données historiques (renvoi) fonctionne-t-il dans la DPA ? | Lorsqu’il est activé pour la première fois, l’Adobe fournit un renvoi de données assemblées qui remonte au début du mois précédent (jusqu’à 60 jours). Pour ce renvoi, l’ID transitoire doit exister dans les données désassemblées qui remontent loin dans le temps. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. Obtention de données dans [!UICONTROL Customer Journey Analytics]

| # | Question | Réponse |
| --- | --- | --- |
| Puis-je combiner des données provenant de différents sandbox [!UICONTROL Adobe Experience Platform] dans une seule connexion [!UICONTROL Customer Journey Analytics] ? | Non, vous ne pouvez pas accéder aux données d’un environnement de test à un autre. Vous pouvez combiner uniquement des jeux de données situés dans le même environnement de test. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] sur [!UICONTROL Adobe Experience Platform] ? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Renvoi de données (jusqu’à 13 mois de données, quelle que soit leur taille) : &lt; 4 semaines</li></ul> |
| Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | Tant que l&#39;ID de personne correspond entre les jeux de données, [!UICONTROL Customer Journey Analytics] peut connecter des filtres, l&#39;attribution, le flux, les abandons, etc. d’un jeu de données à un autre. |
| Comment puis-je importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | Votre droit à l’Customer Journey Analytics vous permet d’assimiler des données à l’Experience Platform. Vous pouvez ensuite créer des connexions à ces données et vues de données dans [!UICONTROL Customer Journey Analytics], pour le rapports dans Analysis Workspace. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit. |
| Comment puis-je intégrer des données [!UICONTROL Adobe Analytics] dans [!UICONTROL Customer Journey Analytics] ? | Les données [!UICONTROL Adobe Analytics] peuvent être connectées à Experience Platform par le biais du [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html). La plupart des champs [!UICONTROL Adobe Analytics] sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles (comme les dimensions de [!UICONTROL canal marketing]). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |

{style=&quot;table-layout:auto&quot;}

## 4. Composants traditionnels [!UICONTROL Adobe Analytics]

| Question | Réponse |
| --- | --- |
| Puis-je partager/publier des filtres (segments) du Profil unifié Customer Journey Analytics à Experience Platform ou d’autres applications Experience Cloud ? | Pas encore, mais nous travaillons activement à fournir cette capacité. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | [!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | [!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. |
| Comment [!UICONTROL Customer Journey Analytics] gère-t-il les limitations `Uniques Exceeded` ? | [!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à [!UICONTROL Customer Journey Analytics] dès maintenant ? | Cela dépend de votre cas d&#39;utilisation. Veuillez travailler avec votre équipe de compte d&#39;Adobe. Vos cas d&#39;utilisation actuels sont peut-être déjà un bon choix pour les Customer Journey Analytics ! |

{style=&quot;table-layout:auto&quot;}

## 5. Conséquences de la suppression des composants de données

En ce qui concerne la suppression des données, nous nous préoccupons de 6 types de composants : sandbox, schéma, jeu de données, connexion, vue de données et projet Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Si vous... | Ceci se produit : |
| --- | --- |
| Supprimer un sandbox dans [!UICONTROL Adobe Experience Platform] | La suppression dʼun sandbox interrompt le flux de données vers toute connexion [!UICONTROL Customer Journey Analytics] aux jeux de données de ce sandbox. Actuellement, les connexions dans CJA liées au sandbox supprimé ne seront pas automatiquement supprimées. |
| Supprimez un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma. | [!UICONTROL Adobe Experience Platform] n’autorise pas la suppression des schémas associés à un ou plusieurs jeux de données. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Supprimer un jeu de données dans le lac de données [!UICONTROL Adobe Experience Platform] | La suppression d&#39;un jeu de données dans le lac de données AEP interrompra le flux de données de ce jeu de données vers les connexions CJA qui incluent ce jeu de données. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] | À l’heure actuelle, vous ne pouvez pas supprimer de jeu de données au sein d’une connexion qui a été enregistrée. Il vous faudrait supprimer la connexion entière et recommencer. (Toutefois, les clients qui ont acheté le SKU CJA peuvent supprimer un jeu de données dans l’interface utilisateur [!UICONTROL Adobe Experience Platform].) |
| Supprimer un lot d&#39;un jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé dʼun jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toutes les connexions CJA qui contiennent ce lot spécifique.  CJA est informé des suppressions de lots dans [!UICONTROL Adobe Experience Platform]. |
| Supprimez un lot **lors de son assimilation** dans [!UICONTROL Customer Journey Analytics]. | Sʼil n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot nʼapparaîtra dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprimer une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprimer une vue de données dans [!UICONTROL Customer Journey Analytics] | Un message dʼerreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner. |
