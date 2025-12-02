---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 99%

---

# Questions fréquentes

Adobe Customer Journey Analytics est le produit d’analyse de nouvelle génération. L’article ci-dessous fournit les réponses aux questions fréquentes sur Customer Journey Analytics. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## &#x200B;1. Prérequis {#prerequisites}

+++**Ai-je besoin d’un [!UICONTROL graphique d’appareil privé] ou d’un [!UICONTROL graphique d’appareil Coop] pour [!UICONTROL Customer Journey Analytics] ?**

Non, un [!UICONTROL graphique d’appareil privé] ou d’[!UICONTROL appareil Coop] n’est pas nécessaire pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge.

+++


+++**Ai-je besoin d’un [!UICONTROL Experience Cloud ID] (ECID) pour [!UICONTROL Customer Journey Analytics] ?**

Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un [!UICONTROL ECID] ou de tout autre identifiant de votre choix.

+++


+++**Que se passe-t-il si jʼai besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur mes données avant de recourir à [!UICONTROL Customer Journey Analytics] ?**

Customer Journey Analytics comprend des fonctions de [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=fr) pour aider à transformer vos données avant de les placer dans le lac de données Adobe Experience Platform. Si vous avez besoin d’ETL après l’ingestion des données, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=fr#queries) offre certaines options limitées, bien que cela puisse engendrer des frais supplémentaires.

+++


## &#x200B;2. Groupement des données {#stitching}

+++**[!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ?**

Oui. [!UICONTROL Customer Journey Analytics] dispose d’une fonctionnalité de [groupement](../stitching/overview.md) pour les événements authentifiés et non authentifiés d’un jeu de données. L’assemblage permet de résoudre des enregistrements disparates sur un seul ID groupé, pour une analyse sur l’ensemble des appareils au niveau de la personne.
En outre, lorsqu’un ID d’espace de noms commun (ID de personne) est utilisé dans les jeux de données au sein d’une [connexion](/help/connections/overview.md), vous pouvez exécuter des analyses sur une combinaison transparente de plusieurs jeux de données « groupés » au niveau de la personne.

+++


+++**Est-ce que l’assemblage d’un comportement anonyme avec un comportement authentifié est pris en charge ?**

Oui. Le [groupement](../stitching/overview.md) examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un ID groupé.

+++


+++**Comment fonctionne la « relecture » dans le groupement ?**

Le groupement « relit » les données en fonction des identifiants uniques qu’il a appris. La relecture vise à regrouper les événements initialement non authentifiés des appareils identifiés entre-temps. [En savoir plus](../stitching/overview.md)

+++


+++**Comment le groupement de données historiques (renvoi) fonctionne-t-il ?**

Lorsque l’option est activée pour la première fois, Adobe fournit un renvoi des données groupées qui remontent jusqu’à la date de votre sélection (jusqu’à 25 mois, en fonction du module de Customer Journey Analytics auquel vous avez droit). Pour effectuer ce renvoi, lʼidentifiant transitoire doit exister dans les données désassemblées à ce moment-là. [En savoir plus](../stitching/overview.md)

+++


+++**Quel est le comportement attendu des enregistrements de jeu de données de profil non assemblés ?**

**Exemple de scénario** : vous joignez deux jeux de données dans une connexion Customer Journey Analytics en utilisant `CRMid` comme ID de personne. L’un de ces jeux de données est un jeu de données d’événement Web incluant `CRMid` dans tous les enregistrements. L’autre jeu de données est un jeu de données de profil CRM. 40 % du jeu de données CRM inclut `CRMid` dans le jeu de données d’événement Web. Les 60 % restants sont absents du jeu de données d’événement Web. Ces enregistrements apparaissent-ils dans les rapports d’Analysis Workspace ?<p> **Réponse** : les lignes de profil sans événement associé sont stockées dans Customer Journey Analytics. Cependant, vous ne pouvez pas les consulter dans Analysis Workspace tant qu’un événement lié à cet ID n’apparaît pas.

+++

## &#x200B;3. Transfert de données dans [!UICONTROL Customer Journey Analytics] {#ingest}

+++**Puis-je combiner des données provenant de différentes sandbox [!UICONTROL Adobe Experience Platform] dans une seule connexion [!UICONTROL Customer Journey Analytics] ?**

Non, vous ne pouvez pas accéder aux données d’une sandbox à un autre. Vous pouvez combiner uniquement des jeux de données situés dans la même sandbox. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#select-sandbox-and-datasets)

+++


+++**Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ?**

Tant que lʼID de personne correspond dʼun jeu de données à un autre, [!UICONTROL Customer Journey Analytics] peut connecter dans les jeux de données les segments, lʼattribution, le flux, les abandons, etc.

+++


+++**Comment puis-je importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics] ?**

Votre droit d’utilisation de Customer Journey Analytics vous permet d’ingérer des données dans Experience Platform. Vous pouvez ensuite créer des connexions à ces données et vues de données dans [!UICONTROL Customer Journey Analytics], pour les rapports dans Analysis Workspace. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit.

+++


+++**Comment puis-je intégrer des données [!UICONTROL Adobe Analytics] dans [!UICONTROL Customer Journey Analytics] ?**

Les données [!UICONTROL Adobe Analytics] peuvent être connectées à Experience Platform par le biais du [connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). La plupart des champs [!UICONTROL Adobe Analytics] sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles.

+++


+++**Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ?**

Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données.

+++


+++**Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ?**

Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable.

+++


+++**Quelles sont les limites en matière dʼingestion de dates/horodatages passés ou futurs dans les jeux de données dʼévénement Customer Journey Analytics ?**

* Concernant les dates/horodatages passés : les données dʼévénement datant de dix ans maximum.
* Concernant les dates/horodatages futurs : les données dʼévénement (prédictives) jusquʼà un mois dans le futur.

+++


## &#x200B;4. Considérations relatives à la latence {#latency}

>[!NOTE]
>
>Il nʼexiste pas de taille de données fixe dans Customer Journey Analytics, par conséquent Adobe ne peut pas proposer de temps dʼingestion standard. Adobe s’efforce de réduire ces latences grâce à de nouvelles mises à jour et à lʼoptimisation de lʼingestion.

* Données ou événements dynamiques : traitement et ingestion en 90 minutes, une fois les données disponibles dans Adobe Experience Platform. (Taille du lot > 50 millions de lignes : plus de 90 minutes). Si le groupement est activé, l’ingestion peut prendre jusqu’à 4 heures. Pour plus de détails, consultez la section [Mécanismes de sécurisation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/technotes/guardrails).
* Petits renvois : dans les sept jours
* Grands renvois : dans les 30 jours

Adobe a récemment modifié la manière dont il traite les données dans Customer Journey Analytics :

* Les données d’événement pour la journée actuelle sont diffusées en continu sous forme de données dynamiques. Toutes les données dont l’heure de l’événement est antérieure à 11:59:59 pm (23:59:59) le jour précédent sont traitées comme des renvois.
* Toutes les données d’événement de plus de 24 heures (même si elles se trouvent dans le même lot que les données plus récentes) sont considérées comme un renvoi et sont ingérées avec une priorité inférieure.

## &#x200B;5. Définition dʼune fenêtre dynamique pour la conservation des données de [!UICONTROL connexion] {#data-retention}

Le paramètre [**[!UICONTROL Activer la fenêtre dynamique de données &#x200B;]**](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection) vous permet de définir la conservation des données Customer Journey Analytics sous la forme d’une fenêtre dynamique en mois (trois mois, six mois, etc.). Il est défini au niveau de la [!UICONTROL connexion] et non au niveau du [!UICONTROL jeu de données]. La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de rétention des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable.

Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.

## &#x200B;6. Implications de la suppression de composants de données {#deletion}

La suppression des données implique six types de composants : sandbox, schéma, jeu de données, connexion, vue de données et projet Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Si vous... | Ceci se produit : |
| --- | --- |
| Supprime un sandbox dans [!UICONTROL Adobe Experience Platform] | La suppression dʼun sandbox arrête le flux de données vers toute connexion [!UICONTROL Customer Journey Analytics] aux jeux de données de ce sandbox. Les connexions, vues de données, mesures et dimensions liées à ce sandbox seront également supprimées. |
| Supprimer un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma | [!UICONTROL Adobe Experience Platform] n’autorise pas la suppression des [!UICONTROL schémas] associés à un ou plusieurs [!UICONTROL jeux de données]. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Supprime un jeu de données dans le lac de données [!UICONTROL Adobe Experience Platform] | La suppression d’un jeu de données dans le lac de données Adobe Experience Platform arrête le flux de ce jeu de données vers les connexions de Customer Journey Analytics qui incluent ce jeu de données. Toutes les données de ce jeu de données sont automatiquement supprimées des connexions Customer Journey Analytics associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] | Contactez votre équipe Adobe en charge des comptes afin de lancer le processus de suppression d’un jeu de données pour une connexion déjà enregistrée. |
| Supprimer un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé d’un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toute connexion Customer Journey Analytics contenant ce lot spécifique. Customer Journey Analytics est informé des suppressions de lots dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] | Si le jeu de données ne contient qu’un seul lot, aucune des données ou données partielles de ce lot n’apparaît dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient cinq lots et que trois dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cessent de fonctionner.</li></ul> |
| Supprime une vue de données dans [!UICONTROL Customer Journey Analytics] | Un message dʼerreur indique que tous les projets Workspace qui dépendent de cette vue de données supprimée cesseront de fonctionner. |

## &#x200B;7. Remarques concernant la fusion de suites de rapports dans Customer Journey Analytics {#merge-reportsuite}

Si vous prévoyez d’ingérer des données Adobe Analytics par l’intermédiaire du [connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html), tenez compte de ces ramifications lors de la fusion de suites de rapports Adobe Analytics ou plus.

| Problème | Considération |
| --- | --- |
| Variables | Les variables telles que [!UICONTROL eVars] peuvent ne pas s’afficher dans toutes les suites de rapports. Par exemple, l’eVar1 de la suite de rapports 1 peut pointer vers **[!UICONTROL Page]**. Dans la suite de rapports 2, l’eVar1 peut pointer vers **[!UICONTROL Campagne interne]**, ce qui entraîne des rapports variés et inexacts. |
| Comptes de [!UICONTROL Sessions] et de [!UICONTROL Personnes] | Elles sont dédupliquées dans les suites de rapports. Par conséquent, les comptes peuvent ne pas correspondre. |
| Déduplication des mesures | Déduplique les instances d’une mesure (par exemple, [!UICONTROL Commandes]) si plusieurs lignes possèdent le même ID de transaction (par exemple, [!UICONTROL ID d’achat]). Cela permet d’éviter le surcomptage des mesures clés. Par conséquent, les mesures telles que [!UICONTROL Commandes] peuvent ne pas s’additionner dans les suites de rapports. |
| Devise | La conversion de devises n’est pas encore prise en charge dans Customer Journey Analytics. Si les suites de rapports que vous tentez de fusionner utilisent des devises de base différentes, des problèmes peuvent survenir. |
| [!UICONTROL Persistance] | La [persistance](../data-views/component-settings/persistence.md) s’étend à l’ensemble des suites de rapport, ce qui se répercute sur les [!UICONTROL segments], l’[!UICONTROL attribution], etc. Les nombres peuvent ne pas s’additionner correctement. |
| [!UICONTROL Classifications] | [!UICONTROL Les classifications] ne sont pas automatiquement dédupliquées lors de la fusion de suites de rapports. Lorsque vous combinez plusieurs fichiers de classification en un seul jeu de données de [!UICONTROL recherche], vous pouvez rencontrer des problèmes. |

## &#x200B;8. Composants [!UICONTROL Adobe Analytics]

+++**Puis-je partager/publier des [!UICONTROL audiences] de [!DNL Customer Journey Analytics] vers Experience Platform Real-Time CDP ou vers d’autres applications Experience Cloud ?**

Vous pouvez [créer et publier des audiences](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-components/audiences/publish) découvertes dans Customer Journey Analytics dans le profil client en temps réel d’Adobe Experience Platform pour le ciblage et la personnalisation des clientes et clients.

+++

+++**Qu’est-il advenu de mon ancien paramètre [!UICONTROL eVar] ?**

Les [!UICONTROL eVars], les [!UICONTROL props] et les [!UICONTROL événements] comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez au cours du processus de collecte de données sont maintenant appliqués au moment de la requête.

+++

+++**Où sont désormais tous mes paramètres de persistance des sessions et des variables ?**

[!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données !

+++

+++**Qu’advient-il de nos segments/mesures calculées existants ?**

Cependant, [!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements, mais des éléments de schéma Adobe Experience Platform. Cela signifie qu’aucun des segments ou des mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics].

+++

+++**Comment [!UICONTROL Customer Journey Analytics] gère-t-il les limitations `Uniques Exceeded` ?**

[!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier !

+++

+++**Si je suis un client ou une cliente existant(e) [!DNL Data Workbench], puis-je passer à [!UICONTROL Customer Journey Analytics] dès maintenant ?**

Cela dépend de votre cas d’utilisation. Veuillez collaborer avec votre équipe Adobe en charge des comptes. Vos cas d’utilisation actuels sont peut-être déjà adaptés à Customer Journey Analytics !

+++

## &#x200B;9. Estimer la taille de connexion {#estimate-size}

Consultez [&#x200B; Utilisation des connexions](/help/connections/manage-connections.md#usage).

## &#x200B;10. À propos des limites d’utilisation {#overage}

Les limites d’utilisation sont surveillées et Adobe en assure l’application stricte. « Lignes de données » désigne les lignes de données moyennes quotidiennes disponibles pour analyse dans Customer Journey Analytics.

Supposons par exemple que votre contrat vous donne droit à 1 million de lignes de données. Lors de votre premier jour d’utilisation de Customer Journey Analytics, vous chargez 2 millions de lignes de données. Le jour suivant, vous supprimez 1 million de lignes et ne dépassez pas cette limite (soit 1 million) pour le reste de la durée de votre licence. Selon les conditions de votre contrat, des frais de surutilisation peuvent vous être imputés au prorata pour le premier jour, car vous avez dépassé votre droit de licence « Lignes de données ».

## &#x200B;11. Repérer les écarts de données {#discrepancies}

Parfois, vous remarquerez peut-être que le nombre total dʼévénements ingérés par votre connexion est différent du nombre de lignes du jeu de données dans [!UICONTROL Adobe Experience Platform]. Dans cet exemple, le jeu de données « Impression B2B » contient 7 650 lignes, mais le jeu de données contient 3 830 lignes dans [!UICONTROL Adobe Experience Platform]. Il existe plusieurs raisons pour lesquelles des écarts peuvent survenir et les mesures suivantes peuvent être prises pour effectuer un diagnostic :

1. Ventilez cette dimension par **[!UICONTROL ID de jeu de données Platform]** et vous remarquerez deux jeux de données de même taille, avec différents **[!UICONTROL ID de jeu de données Platform]**. Chaque jeu de données contient 3 825 enregistrements. Cela signifie que [!UICONTROL Customer Journey Analytics] a ignoré cinq enregistrements en raison d’identifiants de personne manquants ou d’horodatages manquants :

   ![répartition](assets/data-size2.png)

1. En outre, si vous archivez [!UICONTROL Adobe Experience Platform], il nʼexiste aucun jeu de données avec lʼID 5f21c12b732044194bffc1d0, dʼoù la suppression de ce jeu de données particulier dʼ[!UICONTROL Adobe Experience Platform] lors de la création de la connexion initiale. Par la suite, il a été de nouveau ajouté à Customer Journey Analytics, mais un autre [!UICONTROL ID de jeu de données Platform] a été généré par [!UICONTROL Adobe Experience Platform].

Découvrez-en plus sur les [implications de la suppression du jeu de données et de la connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#implications-of-deleting-data-components) dans [!UICONTROL Customer Journey Analytics] et [!UICONTROL Adobe Experience Platform].


## &#x200B;12. Collecte de données régionales

Adobe Experience Cloud utilise la collecte de données régionale (RDC) afin que les interactions entre vos visiteurs/visiteuses et vos solutions Adobe et non Adobe se produisent le plus près possible de vos visiteurs/visiteuses. Une fois que les données sont collectées à l’échelle régionale dans un centre de collecte de données (DCC, également appelé site Edge, qui fait partie de Platform Edge Network), elles sont transférées au moyen d’une connexion sécurisée aux solutions appropriées, en fonction de la configuration de votre train de données et/ou du transfert d’événement.

![Flux de données utilisant les réseaux Edge](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

Le processus de collecte de données régionale suit les étapes ci-après :

1. Le DNS résout automatiquement le nom d’hôte de la collecte à l’adresse IP du centre de collecte de données le plus proche du visiteur ou de la visiteuse.
1. Le visiteur ou la visiteuse envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée aux solutions définies par la configuration du transfert de données ou d’événement.

L’utilisation de la collecte de données régionale présente plusieurs avantages :

* **Performance** : avec la collecte de données régionale, vos visiteurs et visiteuses se connectent au centre de collecte de données le plus proche. Cette optimisation permet de disposer du temps de réponse le plus rapide, ce qui autorise un suivi plus précis et des temps de chargement plus rapides.
* **Redondance** : dans le cas d’une interruption de communication entre le centre de collecte de données et votre centre de traitement de données, l’infrastructure de collecte de données régionale d’Adobe enregistre les données localement, puis les transmet au centre de traitement de données lorsque les communications sont restaurées.

La collecte de données régionale inclut actuellement les emplacements suivants (sujets à modification) :


| Type de collecte de données régionale | Centres de collecte de données |
| --- | --- |
| Mondiale (par défaut) | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Amériques uniquement | Oregon, Virginie |
| Europe uniquement | Irlande, Paris |
| Asie-Pacifique uniquement | Mumbai, Singapour, Tokyo, Sydney |

{style="table-layout:auto"}

Lorsque les données atteignent le centre de données régional, la configuration du train de données détermine la manière dont les données sont acheminées plus loin.

Customer Journey Analytics nécessite des jeux de données d’Adobe Experience Platform. Par conséquent, votre configuration de transfert de flux de données/d’événement nécessite que le service Adobe Experience Platform achemine les données du centre de données régional vers le centre de données où se trouve votre instance Adobe Experience Platform. Customer Journey Analytics et ses services et son infrastructure de prise en charge sont déployés sur cette même instance Adobe Experience Platform.


Voir [Vue d’ensemble de la collecte de données](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html) pour plus d’informations sur le processus de collecte de données au-delà du réseau Adobe Experience Platform Edge et de ses centres de données régionaux.
