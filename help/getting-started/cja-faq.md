---
title: Customer Journey Analytics - FAQ
description: Customer Journey Analytics - Questions fréquentes.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: 355b7a84274f56e392a718ef11002eb44a57c14e
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 61%

---

# Questions fréquentes

Adobe Customer Journey Analytics est le produit d’analyse de nouvelle génération. Cet article répond aux questions les plus fréquemment posées sur Customer Journey Analytics. Pour plus d’informations, consultez [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Prérequis {#prerequisites}

+++**Ai-je besoin d’un [!UICONTROL graphique d’appareil privé] ou d’un [!UICONTROL graphique d’appareil Coop] pour [!UICONTROL Customer Journey Analytics] ?**

Non, un [!UICONTROL graphique d’appareil privé] ou d’[!UICONTROL appareil Coop] n’est pas nécessaire pour [!UICONTROL Customer Journey Analytics]. D’ailleurs, ils ne sont pas encore pris en charge.

+++


+++**Ai-je besoin d’un [!UICONTROL Experience Cloud ID] (ECID) pour [!UICONTROL Customer Journey Analytics] ?**

Non, [!UICONTROL Customer Journey Analytics] prend en charge n’importe quel identifiant dans un jeu de données, qu’il s’agisse d’un [!UICONTROL ECID] ou de tout autre identifiant de votre choix.

+++


+++**Que se passe-t-il si jʼai besoin d’utiliser un processus ETL (extraction, transformation, chargement) sur mes données avant de recourir à [!UICONTROL Customer Journey Analytics] ?**

Customer Journey Analytics inclut [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=fr) fonctionnalités permettant de transformer vos données avant de les placer dans le lac de données Adobe Experience Platform. Si vous avez besoin d’ETL après l’ingestion des données, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=fr#queries) offre certaines options limitées, bien que cela puisse engendrer des frais supplémentaires.

+++


## 2. Groupement des données {#stitching}

+++**[!UICONTROL Customer Journey Analytics] peut-il « assembler » d’un périphérique ou d’un jeu de données à l’autre ?**

Oui. [!UICONTROL Customer Journey Analytics] dispose d’une fonctionnalité de [groupement](../stitching/overview.md) pour les événements authentifiés et non authentifiés d’un jeu de données. Ce regroupement permet de résoudre des enregistrements disparates sur un seul identifiant assemblé, pour une analyse entre appareils au niveau de la personne.
En outre, lorsqu’un ID d’espace de noms commun (ID de personne) est utilisé dans les jeux de données au sein d’un [Connexion](/help/connections/overview.md), vous pouvez exécuter des analyses sur une combinaison transparente de plusieurs jeux de données &quot;assemblés&quot; au niveau de la personne.

+++


+++**Est-ce que l’assemblage d’un comportement anonyme avec un comportement authentifié est pris en charge ?**

Oui. Le [groupement](../stitching/overview.md) examine les données utilisateur des sessions authentifiées et non authentifiées afin de générer un ID groupé.

+++


+++**Comment fonctionne la « relecture » dans le groupement ?**

Le groupement « relit » les données en fonction des identifiants uniques qu’il a appris. La relecture vise à regrouper les événements initialement non authentifiés des appareils identifiés entre-temps. [En savoir plus](../stitching/explained.md)

+++


+++**Comment le groupement de données historiques (renvoi) fonctionne-t-il ?**

Lors de la première utilisation, Adobe fournit un renvoi de données assemblées qui remonte jusquʼau début du mois précédent (jusquʼà 60 jours). Pour effectuer ce renvoi, lʼidentifiant transitoire doit exister dans les données désassemblées à ce moment-là. [En savoir plus](../stitching/explained.md)

+++


+++**Quel est le comportement attendu des enregistrements de jeu de données de profil non assemblés ?**

**Exemple de scénario**: vous rejoignez deux jeux de données dans une connexion de Customer Journey Analytics en utilisant `CRMid` comme ID de personne. L’un de ces jeux de données est un jeu de données d’événement Web incluant `CRMid` dans tous les enregistrements. L’autre jeu de données est un jeu de données de profil CRM. 40 % du jeu de données CRM inclut `CRMid` dans le jeu de données d’événement Web. Les 60 % restants ne sont pas présents dans le jeu de données d’événement web. Ces enregistrements apparaissent-ils dans les rapports dans Analysis Workspace ?<p> **Réponse** : les lignes de profil sans événement associé sont stockées dans Customer Journey Analytics. Cependant, vous ne pouvez pas les consulter dans Analysis Workspace tant qu’un événement lié à cet ID n’apparaît pas.

+++

## 3. Transfert de données dans [!UICONTROL Customer Journey Analytics] {#ingest}

+++**Puis-je combiner des données provenant de différentes sandbox [!UICONTROL Adobe Experience Platform] dans une seule connexion [!UICONTROL Customer Journey Analytics] ?**

Non, vous ne pouvez pas accéder aux données d’une sandbox à un autre. Vous pouvez combiner uniquement des jeux de données situés dans la même sandbox. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#select-sandbox-and-datasets)

+++


+++**Comment est-ce que je connecte les données en ligne aux données hors ligne dans [!UICONTROL Customer Journey Analytics] ?**

Tant que l’ID de personne correspond entre les jeux de données, [!UICONTROL Customer Journey Analytics] peuvent connecter des filtres, des attributions, des flux, des abandons, etc., sur plusieurs jeux de données.

+++


+++**Comment puis-je importer mes données hors ligne dans [!UICONTROL Customer Journey Analytics] ?**

Votre droit d’utilisation de Customer Journey Analytics vous permet d’ingérer des données dans Experience Platform. Vous pouvez ensuite créer des connexions à ces données et vues de données dans [!UICONTROL Customer Journey Analytics], pour les rapports dans Analysis Workspace. Si besoin, l’équipe d’intégration des données Experience Platform peut formuler des recommandations ou des conseils à votre endroit.

+++


+++**Comment puis-je intégrer des données [!UICONTROL Adobe Analytics] dans [!UICONTROL Customer Journey Analytics] ?**

Les données [!UICONTROL Adobe Analytics] peuvent être connectées à Experience Platform par le biais du [connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr). La plupart des champs [!UICONTROL Adobe Analytics] sont transférés au format XDM. Cependant, d’autres champs ne sont pas encore disponibles.

+++


+++**Combien de temps faut-il pour assembler des éléments de jeu de données dans une vue de données ?**

Quelques heures pour commencer, puis quelques jours pour renvoyer les 13 derniers mois de données.

+++


+++**Est-il nécessaire d’apporter des données personnelles identifiables pour établir des connexions entre les données ?**

Non, vous pouvez utiliser n’importe quel ID, y compris le hachage d’un ID client, qui n’est pas une donnée personnelle identifiable.

+++


+++**Quelles sont les limites en matière dʼingestion de dates/horodatages passés ou futurs dans les jeux de données dʼévénement Customer Journey Analytics ?**

<ul><li>Concernant les dates/horodatages passés : données d’événement âgées de plus de dix ans.</li><li>À propos des dates/horodatages futurs : données d’événement (prédictives) jusqu’à un mois dans le futur.</li></ul>

+++


## 4. Considérations relatives à la latence {#latency}

>[!NOTE]
>Il nʼexiste pas de taille de données fixe dans Customer Journey Analytics, par conséquent Adobe ne peut pas proposer de temps dʼingestion standard. Adobe travaille activement à réduire ces latences par de nouvelles mises à jour et une optimisation de l’ingestion.

<ul><li>Données ou événements dynamiques : traitement et ingestion en 90 minutes, une fois les données disponibles dans Adobe Experience Platform. (taille du lot &gt; 50 millions de lignes : plus de 90 minutes).</li><li>Petits renvois : dans les sept jours<li>Grands renvois : dans les 30 jours</li></ul>

Adobe a récemment modifié la manière dont il traite les données dans Customer Journey Analytics :

<ul><li>Toutes les données d’événement datant de moins de 24 heures sont diffusées en continu.</li><li>Toute donnée d’événement ayant un horodatage de plus de 24 heures (même si elle se trouve dans le même lot que les données plus récentes) est considérée comme un renvoi et est ingérée avec une priorité inférieure.</li></ul>

## 5. Définition dʼune fenêtre dynamique pour la rétention des données de [!UICONTROL connexion] {#data-retention}

La variable [**[!UICONTROL Activer la fenêtre de données flottante ]**paramètre](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#create-connection) permet de définir la conservation des données des Customer Journey Analytics sous la forme d’un créneau variable en mois (trois mois, six mois, etc.). Il est défini au niveau de la [!UICONTROL connexion] et non au niveau du [!UICONTROL jeu de données]. La conservation des données est basée sur les horodatages des jeux de données dʼévénement et sʼapplique uniquement aux jeux de données dʼévénement. Aucun paramètre de rétention des données nʼexiste pour les jeux de données de profil ou de recherche, car il nʼexiste aucun horodatage applicable.

Lʼavantage principal est que vous ne stockez ou ne créez des rapports que sur les données applicables et utiles, et supprimez les données plus anciennes qui ne sont plus utiles. Elle vous aide à rester dans les limites de votre contrat et réduit le risque de surcoût.

## 6. Implications de la suppression de composants de données {#deletion}

Pour la suppression des données, vous devez vous préoccuper de six types de composants : sandbox, schéma, jeu de données, connexion, vue de données et projet Workspace. Voici quelques scénarios possibles de suppression de l’un de ces composants :

| Si vous... | Ceci se produit : |
| --- | --- |
| Supprime un sandbox dans [!UICONTROL Adobe Experience Platform] | La suppression d’un environnement de test interrompt le flux de données vers n’importe quel environnement de test. [!UICONTROL Customer Journey Analytics] se connectent à des jeux de données dans cet environnement de test. Actuellement, les [!UICONTROL connexions] dans Customer Journey Analytics liées à ce sandbox supprimé ne seront pas automatiquement supprimées. |
| Supprimer un schéma dans [!UICONTROL Adobe Experience Platform], mais pas le ou les jeux de données associés à ce schéma | [!UICONTROL Adobe Experience Platform] n’autorise pas la suppression des [!UICONTROL schémas] associés à un ou plusieurs [!UICONTROL jeux de données]. Cependant, un administrateur disposant des droits appropriés peut d’abord supprimer les jeux de données, puis supprimer le schéma. |
| Suppression d’un jeu de données dans le [!UICONTROL Adobe Experience Platform] lac de données | La suppression d’un jeu de données dans le lac de données Adobe Experience Platform interrompt le flux de ce jeu de données vers les connexions de Customer Journey Analytics qui incluent ce jeu de données. Toutes les données de ce jeu de données sont automatiquement supprimées des connexions de Customer Journey Analytics associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] | Contactez votre équipe Adobe en charge des comptes afin de lancer le processus de suppression d’un jeu de données pour une connexion déjà enregistrée. |
| Supprimer un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé d’un [!UICONTROL Adobe Experience Platform] jeu de données, le même lot est supprimé de toutes les connexions de Customer Journey Analytics qui contiennent ce lot spécifique. Customer Journey Analytics est informé des suppressions de lots dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] | S’il n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot n’apparaît dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Par exemple, s’il existe cinq lots dans le jeu de données et que trois d’entre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces trois lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, tout projet Workspace qui dépend des vues de données dans la connexion supprimée cesse de fonctionner.</li></ul> |
| Supprime une vue de données dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que tout projet Workspace qui dépend de cette vue de données supprimée cessera de fonctionner. |

## 7. Remarques concernant la fusion de suites de rapports dans Customer Journey Analytics {#merge-reportsuite}

Si vous prévoyez d’ingérer des données Adobe Analytics via la variable [Connecteur source Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr), tenez compte de ces ramifications lors de la fusion de plusieurs suites de rapports Adobe Analytics.

| Problème | Considération |
| --- | --- |
| Variables | Les variables telles que [!UICONTROL eVars] peuvent ne pas s’afficher dans toutes les suites de rapports. Par exemple, l’eVar1 de la suite de rapports 1 peut pointer vers **[!UICONTROL Page]**. Dans la suite de rapports 2, l’eVar1 peut pointer vers **[!UICONTROL Campagne interne]**, ce qui entraîne des rapports variés et inexacts. |
| Comptes de [!UICONTROL Sessions] et de [!UICONTROL Personnes] | Elles sont dédupliquées dans les suites de rapports. Par conséquent, les comptes peuvent ne pas correspondre. |
| Déduplication des mesures | Déduplique les instances d’une mesure (par exemple, [!UICONTROL Commandes]) si plusieurs lignes possèdent le même ID de transaction (par exemple, [!UICONTROL ID d’achat]). Cela permet d’éviter le surcomptage des mesures clés. Par conséquent, les mesures telles que [!UICONTROL Commandes] peuvent ne pas s’additionner dans les suites de rapports. |
| Devise | La conversion de devises n’est pas encore prise en charge dans Customer Journey Analytics. Si les suites de rapports que vous tentez de fusionner utilisent des devises de base différentes, des problèmes peuvent survenir. |
| [!UICONTROL Persistance] | [La persistance](../data-views/component-settings/persistence.md) s’étend sur toutes les suites de rapport, ce qui se répercute sur les [!UICONTROL filtres], l’[!UICONTROL attribution], etc. Les nombres peuvent ne pas s’additionner correctement. |
| [!UICONTROL Classifications] | [!UICONTROL Les classifications] ne sont pas automatiquement dédupliquées lors de la fusion de suites de rapports. Lorsque vous combinez plusieurs fichiers de classification en un seul jeu de données de [!UICONTROL recherche], vous pouvez rencontrer des problèmes. |

## 8. Composants [!UICONTROL Adobe Analytics]

+++**Puis-je partager/publier des [!UICONTROL filtres] de [!DNL Customer Journey Analytics] vers Experience Platform Real-Time CDP ou vers d’autres applications Experience Cloud ?**

Pas encore, mais l&#39;Adobe travaille activement à fournir cette capacité.

+++

+++**Qu’est-il advenu de mon ancien paramètre [!UICONTROL eVar] ?**

Les [!UICONTROL eVars], les [!UICONTROL props] et les [!UICONTROL événements] comme l’entend habituellement Adobe Analytics n’existent plus dans [!UICONTROL Customer Journey Analytics]. Vous disposez d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Ainsi, tous les paramètres d’attribution que vous appliquiez pendant le processus de collecte de données sont désormais appliqués au moment de la requête.

+++

+++**Où sont désormais tous mes paramètres de persistance des sessions et des variables ?**

[!UICONTROL Customer Journey Analytics] applique tous ces paramètres au moment du rapport. Ils se trouvent désormais dans les vues de données. Les modifications apportées à ces paramètres sont désormais rétroactives. Vous pouvez disposer de plusieurs versions en utilisant plusieurs vues de données !

+++

+++**Qu’advient-il de vos segments/mesures calculées existants ?**

Cependant, [!UICONTROL Customer Journey Analytics] n’utilise plus d’eVars, de props ou d’événements, mais des éléments de schéma Adobe Experience Platform. Cela signifie qu’aucun des segments ou mesures calculées existants n’est compatible avec [!UICONTROL Customer Journey Analytics].

+++

+++**Comment [!UICONTROL Customer Journey Analytics] gère-t-il les limitations `Uniques Exceeded` ?**

[!UICONTROL Customer Journey Analytics] n’a aucune limite de valeur unique, donc pas besoin de vous en soucier !

+++

+++**Si je suis un client ou une cliente existant(e) [!DNL Data Workbench], puis-je passer à [!UICONTROL Customer Journey Analytics] dès maintenant ?**

Cela dépend de votre cas d’utilisation. Vous devez donc collaborer avec votre équipe de compte d’Adobe. Votre cas d’utilisation actuel est peut-être déjà adapté au Customer Journey Analytics.

+++

## 9. Estimer la taille de connexion {#estimate-size}

Consultez [Estimer et gérer l’utilisation](/help/admin/estimate-usage.md).

## 10. À propos des limites d’utilisation {#overage}

Les limites d’utilisation sont surveillées et Adobe en assure l’application stricte. « Lignes de données » désigne les lignes de données moyennes quotidiennes disponibles pour analyse dans Customer Journey Analytics.

Supposons, par exemple, que votre contrat vous donne droit à 1 million de lignes de données. À votre premier jour d’utilisation de Customer Journey Analytics, vous téléchargez 2 millions de lignes de données. Le jour 2, vous supprimez 1 million de lignes et maintenez votre utilisation à ce maximum (c’est-à-dire un million de lignes de données) pour le reste de votre terme de licence. Selon les conditions de votre contrat, des frais de surutilisation peuvent vous être imputés au prorata pour le premier jour, car vous avez dépassé votre droit de licence « Lignes de données ».

## 11. Repérer les écarts de données {#discrepancies}

Parfois, vous pouvez remarquer que le nombre total d’événements ingérés par votre connexion est différent du nombre de lignes du jeu de données dans [!UICONTROL Adobe Experience Platform]. Dans cet exemple, le jeu de données « Impression B2B » contient 7 650 lignes, mais le jeu de données contient 3 830 lignes dans [!UICONTROL Adobe Experience Platform]. Il existe plusieurs raisons pour lesquelles des écarts peuvent survenir et les mesures suivantes peuvent être prises pour effectuer un diagnostic :

1. Ventilez cette dimension par **[!UICONTROL Identifiant du jeu de données Platform]** et vous remarquez deux jeux de données de la même taille mais différents. **[!UICONTROL Identifiants des jeux de données Platform]**. Chaque jeu de données contient 3 825 enregistrements. Cela signifie [!UICONTROL Customer Journey Analytics] a ignoré cinq enregistrements en raison d’identifiants de personne manquants ou d’horodatages manquants :

   ![répartition](assets/data-size2.png)

1. En outre, si vous archivez [!UICONTROL Adobe Experience Platform], il n’existe aucun jeu de données avec l’identifiant &quot;5f21c12b732044194bffc1d0&quot;. Par conséquent, quelqu’un a supprimé ce jeu de données particulier de [!UICONTROL Adobe Experience Platform] lors de la création de la connexion initiale. Par la suite, il a été de nouveau ajouté à Customer Journey Analytics, mais un autre [!UICONTROL ID de jeu de données Platform] a été généré par [!UICONTROL Adobe Experience Platform].

Découvrez-en plus sur les [implications de la suppression du jeu de données et de la connexion](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#implications-of-deleting-data-components) dans [!UICONTROL Customer Journey Analytics] et [!UICONTROL Adobe Experience Platform].


## 12. Collecte de données régionale

Adobe Experience Cloud utilise la collecte de données régionale (RDC) afin que les interactions entre vos visiteurs et vos solutions d’Adobe et non Adobe se produisent le plus près possible de vos visiteurs. Une fois que les données sont collectées à l’échelle régionale dans un centre de collecte de données (DCC, également appelé site Edge, qui fait partie de Platform Edge Network), elles sont transférées au moyen d’une connexion sécurisée aux solutions appropriées en fonction de la configuration de votre flux de données et/ou du transfert d’événement.

![Flux de données à l’aide des réseaux Edge](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png?lang=en)

Le processus de collecte de données régionale suit les étapes suivantes :

1. Le DNS résout automatiquement le nom d’hôte de la collecte sur l’adresse IP du centre de collecte de données le plus proche du visiteur.
1. Le visiteur envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée aux solutions définies par la configuration du transfert de données ou d’événement.

L’utilisation de la collecte de données régionale présente plusieurs avantages :

* **Performances**: avec la collecte de données régionale, vos visiteurs se connectent au centre de collecte de données le plus proche. Cette optimisation fournit le temps de réponse le plus rapide, ce qui se traduit par un suivi plus précis et des temps de chargement plus rapides.
* **Redondance**: en cas d’interruption de communication entre le centre de collecte de données et votre centre de traitement des données, l’infrastructure de collecte de données régionale de l’Adobe enregistre les données localement, puis les transfère au centre de traitement des données lorsque les communications sont restaurées.

La collecte de données régionale inclut actuellement les emplacements suivants (sujets à modification) :


| Type de collecte de données régionale | Centres de collecte de données |
| --- | --- |
| Mondiale (par défaut) | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Amériques uniquement | Oregon, Virginie |
| Europe uniquement | Irlande, Paris |
| Asie-Pacifique uniquement | Mumbai, Singapour, Tokyo, Sydney |

{style="table-layout:auto"}

Lorsque les données atteignent le centre de données régional, la configuration du flux de données détermine la manière dont les données sont acheminées plus loin.

Customer Journey Analytics nécessite des jeux de données de Adobe Experience Platform. Par conséquent, votre configuration de transfert de flux de données/d’événement nécessite que le service Adobe Experience Platform achemine les données du centre de données régional vers le centre de données où se trouve votre instance Adobe Experience Platform. Customer Journey Analytics et ses services et son infrastructure de prise en charge sont déployés sur cette même instance Adobe Experience Platform.


Voir [Présentation de la collecte de données](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html?lang=en) pour plus d’informations sur le processus de collecte de données au-delà du réseau Experience Edge et de ses centres de données régionaux.

