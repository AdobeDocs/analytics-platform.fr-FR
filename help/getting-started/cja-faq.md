---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 95%

---

# Questions fréquentes

## Conditions préalables

| Question | Réponse |
| --- | --- |
| Ai-je besoin d’un [!UICONTROL graphique d’appareil privé] ou d’un [!UICONTROL graphique d’appareil Coop] pour [!UICONTROL Customer Journey Analytics] ? | Non, un [!UICONTROL graphique d’appareil privé] ou d’[!UICONTROL appareil Coop] n’est pas nécessaire pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge. |
| Ai-je besoin d’un [!UICONTROL Experience Cloud ID] (ECID) pour [!UICONTROL Customer Journey Analytics] ? | Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un [!UICONTROL ECID] ou de tout autre identifiant de votre choix. |
| Que se passe-t-il si jʼai besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur mes données avant de recourir à [!UICONTROL Customer Journey Analytics] ? | Vous devez désormais travailler avec un partenaire ETL (Unifi ou Informatica) si vous devez transformer vos données avant de les importer dans AEP. Si vous avez besoin d’utiliser un processus ETL alors que les données ont déjà été ingérées, [!UICONTROL Adobe Experience Platform Query Services] offre quelques options limitées. |

## Assemblage des données

| Question | Réponse |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ? | Oui. [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Nous avons lancé une solution dʼassemblage en novembre 2020. En savoir plus. |
| Est-ce que l’assemblage d’un comportement anonyme à un comportement authentifié est pris en charge ? | Non, pas encore. |

## Transfert de données dans [!UICONTROL Customer Journey Analytics]

| Question | Réponse |
| --- | --- |
| Puis-je combiner des données provenant de différents sandbox [!UICONTROL Adobe Experience Platform] dans une seule connexion [!UICONTROL Customer Journey Analytics] ? | Non, vous ne pouvez pas accéder aux données d’un environnement de test à un autre. Vous pouvez combiner uniquement des jeux de données situés dans le même environnement de test. [En savoir plus...](https://docs.adobe.com/content/help/fr-FR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Quelle est la latence attendue pour [!UICONTROL Customer Journey Analytics] sur [!UICONTROL Adobe Experience Platform] ? | <ul><li>En charge normale : &lt; 60 minutes <br>**Remarque :** dans le cas d’un volume de données exceptionnellement élevé via un pipeline, cela pourrait prendre jusqu’à 24 heures.</li><li>Renvoi de données (jusqu’à 13 mois de données, quelle que soit leur taille) : &lt; 4 semaines</li></ul> |
| Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | [!UICONTROL Customer Journey Analytics] est un système d’analyse « bring your own ID ». Tant que l&#39;ID de personne correspond entre les jeux de données, [!UICONTROL Customer Journey Analytics] peut connecter des filtres, l&#39;attribution, le flux, les abandons, etc. d’un jeu de données à un autre. |
| Comment puis-je importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics] ? | Vous devez d’abord importer toutes les données dans Experience Platform avant de pouvoir les utiliser avec [!UICONTROL Customer Journey Analytics]. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit. |
| Comment puis-je intégrer des données [!UICONTROL Adobe Analytics] dans [!UICONTROL Customer Journey Analytics] ? | Les données [!UICONTROL Adobe Analytics] peuvent être connectées à Experience Platform par le biais du [Connecteur source Adobe Analytics](https://docs.adobe.com/content/help/fr-FR/experience-platform/sources/connectors/adobe-applications/analytics.html). La plupart des champs [!UICONTROL Adobe Analytics] sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles (comme les dimensions de [!UICONTROL canal marketing]). |
| Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ? | Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données. |
| Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ? | Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable. |

## Composants traditionnels [!UICONTROL Adobe Analytics]

| Question | Réponse |
| --- | --- |
| Qu’est-ce que cela signifie pour notre produit [!UICONTROL Adobe Analytics] classique ? | [!UICONTROL Customer Journey Analytics] est notre produit d’analyse de nouvelle génération. L’évolution de nos produits actuels vers [!UICONTROL Customer Journey Analytics] prendra des années et demandera une grande coordination. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Puis-je partager des filtres de [!UICONTROL Customer Journey Analytics] vers AEP ou d&#39;autres solutions ? | Pas encore. Nous étudions de nouvelles façons innovantes de partager des filtres de [!UICONTROL Customer Journey Analytics] à AEP dans le futur qui n&#39;ont pas un si long délai. Cela dit, vous pouvez partager les résultats de Query Services vers Unified Profile comme solution de contournement potentielle. |
| Qu’est-il advenu de mon ancien paramètre eVar ? | Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête. |
| Où sont désormais tous mes paramètres de persistance des sessions et des variables ? | [!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données ! |
| Qu’advient-il de nos segments/mesures calculées existants ? | [!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements et utilise à la place n’importe quel schéma AEP. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics]. |
| Comment [!UICONTROL Customer Journey Analytics] gère-t-il les limitations `Uniques Exceeded` ? | [!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier ! |
| Si je suis un client existant [!DNL Data Workbench], puis-je passer à [!UICONTROL Customer Journey Analytics] dès maintenant ? | Tout dépend. Si vous comptez fortement sur Unified Customer Process (UCP), vous devriez mieux attendre la mise en œuvre de l’assemblage. Si vous disposez déjà de taux d’authentification de clients élevés, si vous souhaitez que toutes vos données se trouvent au même endroit, ou si vous souhaitez vous débarrasser des eVars, Customer Journey Analytics peut vous convenir. |

## Implications de la suppression de composants de données

En ce qui concerne la suppression, nous nous préoccupons de 6 éléments : sandbox, schéma, jeu de données, connexion, vue de données et projets Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Et si je… | Ceci se produit : |
| --- | --- |
| Supprime un sandbox dans [!UICONTROL Adobe Experience Platform] ? | La suppression dʼun sandbox interrompt le flux de données vers toute connexion [!UICONTROL Customer Journey Analytics] aux jeux de données de ce sandbox. Actuellement, les connexions dans CJA liées à ce sandbox ne seront pas automatiquement supprimées. |
| Supprime un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma ? | [!UICONTROL Adobe Experience Platform] n’autorise pas la suppression des schémas associés à un ou plusieurs jeux de données. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Supprime un jeu de données dans [!UICONTROL Adobe Experience Platform] ? | La suppression d’un jeu de données dans AEP interrompt le flux de données entre ce jeu et les connexions qui l’incluent. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprime un jeu de données dans [!UICONTROL Customer Journey Analytics] ? | À l’heure actuelle, vous ne pouvez pas supprimer de jeu de données au sein d’une connexion qui a été enregistrée. Il vous faudrait supprimer la connexion entière et recommencer. (Cependant, vous pouvez supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform].) |
| Supprime un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) ? | Si un lot est supprimé dʼun jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toutes les connexions CJA qui contiennent ce lot spécifique.  CJA est informé des suppressions de lots dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] ? | Sʼil n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot nʼapparaîtra dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] ? | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprime une vue de données dans [!UICONTROL Customer Journey Analytics] ? | Un message dʼerreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner. |
