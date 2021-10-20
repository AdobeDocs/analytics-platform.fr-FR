---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: d88502218cd94fbb430a0fc5a3af994e7edaa73c
workflow-type: tm+mt
source-wordcount: '1649'
ht-degree: 93%

---

# Questions fréquentes

[!UICONTROL Customer Journey Analytics] est notre produit d’analyse de nouvelle génération. Vous trouverez ci-dessous les réponses aux questions les plus fréquentes sur CJA. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/cja-aa.md).

## 1. Prérequis

| Question | Réponse |
| --- | --- |
| Ai-je besoin d’un [!UICONTROL graphique d’appareil privé] ou d’un [!UICONTROL graphique d’appareil Coop] pour [!UICONTROL Customer Journey Analytics] ? | Non, un [!UICONTROL graphique d’appareil privé] ou d’[!UICONTROL appareil Coop] n’est pas nécessaire pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Ai-je besoin d’un [!UICONTROL Experience Cloud ID] (ECID) pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un [!UICONTROL ECID] ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si jʼai besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur mes données avant de recourir à [!UICONTROL Customer Journey Analytics] ? | Customer Journey Analytics comprend des fonctions de [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=fr) pour aider à transformer vos données avant de les placer dans le lac de données Adobe Experience Platform. Si vous avez besoin d’ETL après l’ingestion des données, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=fr#queries) offre certaines options limitées, bien que cela puisse engendrer des frais supplémentaires. |

{style=&quot;table-layout:auto&quot;}

## 2. Assemblage des données (Analyse cross-canal)

| Question | Réponse |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ? | Oui. [!UICONTROL Customer Journey Analytics] présente une solution d’assemblage appelée [Analye cross-canal](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=fr) (ACC). Elle vous permet de recréer l’identifiant personnel d’un jeu de données, ce qui permet de combiner plusieurs jeux de données de manière transparente. |
| Est-ce que l’assemblage d’un comportement anonyme avec un comportement authentifié est pris en charge ? | Oui. L’[analyse cross-canal](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un identifiant assemblé. |
| Comment fonctionne la « relecture » dans l’ACC ? | L’ACC « relit » les données en fonction des identifiants uniques qu’elle a appris. La relecture entraîne l’assemblage des nouveaux périphériques de la connexion. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=fr#%C3%A9tape-1-%3A-assemblage-en-direct) |
| Comment l’assemblage de données historiques (renvoi) fonctionne-t-il dans l’ACC ? | Lors de la première utilisation, Adobe fournit un renvoi de données assemblées qui remonte jusquʼau début du mois précédent (jusquʼà 60 jours). Pour effectuer ce renvoi, lʼidentifiant transitoire doit exister dans les données désassemblées à ce moment-là. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=fr#activer-l%E2%80%99analyse-cross-canal) |

{style=&quot;table-layout:auto&quot;}

## 3. Transfert de données dans [!UICONTROL Customer Journey Analytics]

| Question | Réponse |
| --- | --- |
| Puis-je combiner des données provenant de différents sandbox [!UICONTROL Adobe Experience Platform] dans une seule connexion [!UICONTROL Customer Journey Analytics] ? | Non, vous ne pouvez pas accéder aux données d’un environnement de test à un autre. Vous pouvez combiner uniquement des jeux de données situés dans le même environnement de test. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#select-sandbox-and-datasets) |
| Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | Tant que lʼID de personne correspond dʼun jeu de données à un autre, [!UICONTROL Customer Journey Analytics] peut connecter les filtres, lʼaffectation, le flux, les abandons, etc. d’un jeu de données à un autre. |
| Comment puis-je importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | Votre droit d’utilisation de Customer Journey Analytics vous permet d’ingérer des données dans Experience Platform. Vous pouvez ensuite créer des connexions à ces données et vues de données dans [!UICONTROL Customer Journey Analytics], pour les rapports dans Analysis Workspace. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit. |
| Comment puis-je intégrer des données [!UICONTROL Adobe Analytics] dans [!UICONTROL Customer Journey Analytics] ? | Les données [!UICONTROL Adobe Analytics] peuvent être connectées à Experience Platform par le biais du [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). La plupart des champs [!UICONTROL Adobe Analytics] sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles. |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |
| Quelles sont les limites d’ingestion de dates/horodatages passés ou futurs dans les jeux de données d’événement CJA ? | <ul><li>À propos des dates/horodatages passés : Données d’événement âgées jusqu’à 10 ans.</li><li>À propos des dates/horodatages futurs : Données d’événement (prédictives) jusqu’à 1 mois à l’avenir.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 4. Facteurs de latence

>[!NOTE]
>Il n’existe pas de taille de données fixe dans CJA et, par conséquent, Adobe ne peut pas respecter un temps d’ingestion standard. Nous nous efforçons de réduire ces latences grâce à de nouvelles mises à jour et à l’optimisation de l’ingestion.

| Question | Réponse |
| --- | --- |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] sur [!UICONTROL Adobe Experience Platform] ? | <ul><li>Données ou événements en direct : Traités et ingérés dans les 90 minutes, une fois les données disponibles dans AEP.</li><li>Taille du lot > 50 millions de lignes : plus de 90 minutes.</li><li>Petits renvoi : par exemple, un jeu de données de recherche de 10 millions de lignes : dans les 24 heures<li>Grands renvoi : 500 milliards de lignes, par exemple : 30 jours</li></ul> |


## 5. Composants traditionnels [!UICONTROL Adobe Analytics]

| Question | Réponse |
| --- | --- |
| Puis-je partager/publier des filtres (segments) de Customer Journey Analytics vers le profil unifié Experience Platform ou vers d’autres applications Experience Cloud ? | Pas encore, mais nous travaillons activement à fournir cette fonctionnalité. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | [!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | [!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. |
| Comment [!UICONTROL Customer Journey Analytics] gère-t-il les limitations `Uniques Exceeded` ? | [!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à [!UICONTROL Customer Journey Analytics] dès maintenant ? | Cela dépend de votre cas d’utilisation. Veuillez collaborer avec votre équipe de compte Adobe. Vos cas d’utilisation actuels sont peut-être déjà adaptés à Customer Journey Analytics ! |

{style=&quot;table-layout:auto&quot;}

## 6. Implications de la suppression de composants de données

En ce qui concerne la suppression de données, nous nous préoccupons de 6 éléments : sandbox, schéma, jeu de données, connexion, vue de données et projets Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Si vous... | Ceci se produit : |
| --- | --- |
| Supprime un sandbox dans [!UICONTROL Adobe Experience Platform] | La suppression dʼun sandbox interrompt le flux de données vers toute connexion [!UICONTROL Customer Journey Analytics] aux jeux de données de ce sandbox. Actuellement, les connexions dans CJA liées à ce sandbox supprimé ne seront pas automatiquement supprimées. |
| Supprime un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma | [!UICONTROL Adobe Experience Platform] n’autorise pas la suppression des schémas associés à un ou plusieurs jeux de données. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Supprime un jeu de données dans le lac de données [!UICONTROL Adobe Experience Platform] | La suppression d’un jeu de données dans le lac de données AEP interrompt le flux de données entre ce jeu et les connexions qui l’incluent. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprime un jeu de données dans [!UICONTROL Customer Journey Analytics] | À l’heure actuelle, vous ne pouvez pas supprimer de jeu de données au sein d’une connexion qui a été enregistrée. Il vous faudrait supprimer la connexion entière et recommencer. (Toutefois, les clients qui ont acheté le SKU CJA peuvent supprimer un jeu de données dans l’interface utilisateur [!UICONTROL Adobe Experience Platform].) |
| Supprime un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé dʼun jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toutes les connexions CJA qui contiennent ce lot spécifique.  CJA est informé des suppressions de lots dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] | Sʼil n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot nʼapparaîtra dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprime une vue de données dans [!UICONTROL Customer Journey Analytics] | Un message dʼerreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner. |

## 7. Remarques concernant la fusion de suites de rapports dans CJA

Si vous prévoyez d’ingérer des données Adobe Analytics par l’intermédiaire du [connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr), tenez compte de ces ramifications lors de la fusion de 2 suites de rapports Adobe Analytics ou plus.

| Problème | Considération |
| --- | --- |
| Variables | Les variables telles que [!UICONTROL eVars] peuvent ne pas s’afficher dans toutes les suites de rapports. Par exemple, l’eVar 1 de la suite de rapports 1 peut pointer vers **[!UICONTROL Page]**. Dans la suite de rapports 2, l’eVar1 peut pointer vers **[!UICONTROL Campagne interne]**, ce qui entraîne des rapports variés et inexacts. |
| Comptes de [!UICONTROL Sessions] et de [!UICONTROL Personnes] | Elles sont dédupliquées dans les suites de rapports. Par conséquent, les comptes peuvent ne pas correspondre. |
| Déduplication des mesures | Déduplique les instances d’une mesure (par exemple, [!UICONTROL Commandes]) si plusieurs lignes possèdent le même ID de transaction (par exemple, [!UICONTROL ID d’achat]). Cela permet d’éviter le surcomptage des mesures clés. Par conséquent, les mesures telles que [!UICONTROL Commandes] peuvent ne pas s’additionner dans les suites de rapports. |
| Devise | La conversion de devise n’est pas encore prise en charge dans CJA. Si les suites de rapports que vous tentez de fusionner utilisent des devises de base différentes, des problèmes peuvent survenir. |
| [!UICONTROL Persistance] | [La persistance](../data-views/component-settings/persistence.md) s’étend sur toutes les suites de rapport, ce qui se répercute sur les [!UICONTROL filtres], l’[!UICONTROL attribution], etc. Les nombres peuvent ne pas s’additionner correctement. |
| [!UICONTROL Classifications] | [!UICONTROL Les classifications] ne sont pas automatiquement dédupliquées lors de la fusion de suites de rapports. Lorsque vous combinez plusieurs fichiers de classification en un seul jeu de données de [!UICONTROL recherche], vous pouvez rencontrer des problèmes. |