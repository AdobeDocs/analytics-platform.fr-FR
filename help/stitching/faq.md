---
title: FAQ sur l’assemblage
description: Questions fréquentes sur le groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
source-git-commit: 53d394feb7d1132ad6339bae0e980f32bfe2ee6f
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 34%

---

# Questions fréquentes

Voici quelques questions fréquentes sur l’assemblage :

+++**Comment puis-je utiliser l’assemblage pour voir comment les gens passent d’un canal à un autre ?**

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connexion à [Customer Journey Analytics](https://analytics.adobe.com) et créez un projet Workspace vide.
2. Sélectionnez la variable **[!UICONTROL ** Visualisations **]** à gauche, puis faites glisser un **[!UICONTROL ** Flux **]** dans la zone de travail à droite.
3. Sélectionnez la variable **[!UICONTROL ** Composants **]** à gauche, puis faites glisser la dimension **[!UICONTROL ** Identifiant du jeu de données **]** à l’emplacement central intitulé **[!UICONTROL ** Dimension ou élément **]**.
4. Ce rapport de flux est interactif. Pour étendre les flux aux pages suivantes ou précédentes, sélectionnez l’une des valeurs. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension Identifiant du jeu de données, vous pouvez utiliser un jeu de données de recherche.

+++

+++**Jusqu’où remonte l’assemblage de visiteurs de relecture ?**

L’intervalle de recherche en amont permettant de recomposer des données dépend de la fréquence souhaitée de [lecture](explained.md) des données. Par exemple, si vous configurez le groupement pour qu’il lise les données une fois par semaine, l’intervalle de recherche en amont pour la recomposition des données est de sept jours. Si vous configurez le groupement pour qu’il lise les données tous les jours, la période de recherche arrière pour le regroupement est d’un jour.

+++

+++**Comment les appareils partagés sont-ils gérés ?**

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’identifiant transitoire a priorité sur l’identifiant persistant, de sorte que les appareils partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même appareil).

+++

+++**Comment l’assemblage gère-t-il les situations où une seule personne a de nombreux identifiants persistants ?**

Dans certains cas, un utilisateur individuel peut être associé à un grand nombre d’identifiants persistants. Par exemple, une personne efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Le nombre d’identifiants persistants n’est pas pertinent pour l’identifiant transitoire. Un utilisateur unique peut appartenir à n’importe quel nombre d’appareils sans affecter la capacité d’un Customer Journey Analytics à se regrouper entre les appareils.

+++

+++**Une fois que j’ai contacté mon équipe de compte d’Adobe avec les informations souhaitées, combien de temps faut-il pour que le jeu de données recomposées soit disponible ?**

L’assemblage en direct est disponible environ une semaine après que l’Adobe a activé l’assemblage. La disponibilité du renvoi dépend de la quantité de données existantes. Les petits jeux de données (moins d’un million d’événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard d’événements par jour) peuvent prendre une semaine ou plus.

+++

+++**Quelle est la différence entre les analyses entre appareils (une fonctionnalité d’Analytics traditionnel) et les analyses cross-canal ?**

[Analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) est une fonctionnalité spécifique à Adobe Analytics traditionnel qui vous permet de comprendre comment les personnes fonctionnent sur plusieurs périphériques. Elle offre deux workflows pour lier les données de l’appareil : l’assemblage basé sur les champs et le graphique d’appareil.

L’analyse cross-canal est un cas d’utilisation spécifique à Customer Journey Analytics qui vous permet de comprendre comment les personnes fonctionnent sur les appareils et les canaux. Elle assemble l’ID de personne d’un jeu de données, ce qui permet de combiner facilement ce jeu de données avec d’autres jeux de données. Cette fonctionnalité fonctionne dans la conception de la même manière que le groupement basé sur les champs d’analyse entre appareils, mais l’implémentation est différente en raison de l’architecture des données différente entre Analytics traditionnel et Customer Journey Analytics. Voir [Assemblage](overview.md) et la variable [analyse cross-canal](../use-cases/cross-channel/cross-channel.md) cas d’utilisation pour plus d’informations.

+++

+++**Comment le regroupement gère-t-il les demandes d’accès à des informations personnelles ?**

Adobe traite les demandes d’accès à des informations personnelles conformément aux lois locales et internationales. Adobe propose [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour soumettre des demandes d’accès et de suppression de données. Ces demandes s’appliquent aussi bien aux jeux de données originaux qu’aux jeux de données recomposés.

+++

+++**Que se passe-t-il si le champ Identifiant persistant d’un ou de plusieurs événements est vide ?**

Si le champ Identifiant persistant est vide sur un événement d’un jeu de données assemblé , l’identifiant assemblé pour cet événement est déterminé de l’une des deux façons suivantes :

* Si le champ ID transitoire n’est pas vide, Customer Journey Analytics utilise la valeur de l’ID transitoire comme identifiant assemblé.
* Si le champ Identifiant transitoire est vide, Customer Journey Analytics laisse également l’identifiant assemblé vide. Dans ce cas, les identifiants persistants, transitoires et regroupés sont tous vides sur l’événement. Ces types d’événements sont ignorés de toute connexion de Customer Journey Analytics à l’aide du jeu de données assemblé où l’identifiant assemblé a été choisi comme identifiant de personne.

+++


+++**Que se passe-t-il si le champ Identifiant transitoire dans un ou plusieurs événements comporte des valeurs d’espace réservé, comme &quot;Non défini&quot; ?**

Soyez prudent lorsque l’assemblage de données est appliqué à des données qui utilisent des valeurs d’espace réservé pour les identifiants transitoires. Dans l’exemple de tableau ci-dessous, les identifiants de personne non définis provenant d’un jeu de données provenant d’un système CRM sont renseignés avec la valeur &quot;Non défini&quot;, ce qui entraîne une représentation incorrecte des personnes.

| Événement | Horodatage | ID persistant (ID de cookie) | Identifiant transitoire (identifiant de connexion) | Identifiant assemblé (après relecture) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Non défini | **Non définie** |
| 4 | 2023-05-12 12:04 | 456 | - | **Non définie** |
| 5 | 2023-05-12 12:05 | 789 | Non défini | **Non définie** |
| 6 | 2023-05-12 12:06 | 012 | Non défini | **Non définie** |
| 7 | 2023-05-12 12:07 | 012 | - | **Non définie** |
| 8 | 2023-05-12 12:03 | 789 | Non défini | **Non définie** |
| 9 | 2023-05-12 12:09 | 456 | - | **Non définie** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 appareils** | **2 personnes**:<br/>Perte des événements 1, 4, 7, 9 et 10 | **2 personnes**:<br/>Cory, non authentifié (réduit à une seule personne) |

+++

+++**Comment les mesures des jeux de données assemblés en Customer Journey Analytics se comparent-elles aux mesures similaires dans les jeux de données désassemblés en Customer Journey Analytics et avec Adobe Analytics ?**

Certaines mesures en Customer Journey Analytics sont similaires aux mesures dans Analytics traditionnel, mais d’autres sont différentes, selon ce que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données groupées de Customer Journey Analytics** | **Données non groupées de Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate avec CDA** |
| ----- | ----- | ----- | ----- |
| **Personnes** = Nombre d’ID de personne distincts où l’ID regroupé est sélectionné comme ID de personne. Le nombre de **Personnes** peut être plus ou moins élevé que les **Visiteurs uniques** dans Adobe Analytics traditionnel, en fonction du résultat du processus dʼassemblage. | **Personnes** = Nombre d’ID de personne distincts selon la colonne sélectionnée comme ID de personne. **Personnes** dans les jeux de données du connecteur source Analytics est similaire à **Visiteurs uniques** dans Adobe Analytics traditionnel si `endUserIDs._experience.aaid.id` est utilisé comme ID de personne dans Customer Journey Analytics. | **Visiteurs uniques** = nombre dʼidentifiants de visiteur distincts. Le nombre de **Visiteurs uniques** peut être différent du nombre d’**ECID** distincts. | Voir [Personnes](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=fr). |
| **Sessions** : définies en fonction des paramètres de session dans la vue de données Customer Journey Analytics. Le processus dʼassemblage peut combiner des sessions individuelles provenant de plusieurs appareils en une seule session. | **Sessions** : défini en fonction des paramètres de session spécifiés dans la vue de données Customer Journey Analytics. | **Visites** : voir [Visites](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=fr). | **Visites** : défini en fonction des paramètres de session réglés dans la [suite de rapports virtuelle CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=fr). |
| **Événements** = nombre de lignes dans les données groupées dans Customer Journey Analytics. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Notez toutefois que la FAQ ci-dessus concernant les lignes avec un identifiant persistant vide. | **Événements** = nombre de lignes dans les données non groupées dans Customer Journey Analytics. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Notez toutefois que si des événements comportent un ID de personne vide dans les données désassemblées du lac de données Experience Platform, ces événements ne sont pas inclus dans Customer Journey Analytics. | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). |

D’autres mesures peuvent être similaires dans Customer Journey Analytics et Adobe Analytics. Par exemple, le nombre total pour Adobe Analytics [événements personnalisés](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=fr) 1 à 100 est comparable entre Adobe Analytics traditionnel et Customer Journey Analytics (assemblé ou désassemblé). [Différences de capacités](/help/getting-started/aa-vs-cja/cja-aa.md)), comme la déduplication des événements entre Customer Journey Analytics et Adobe Analytics, peut entraîner des incohérences entre les deux produits.

+++

+++**Customer Journey Analytics peut-il utiliser les champs de carte des identités ?**

Non, Customer Journey Analytics ne peut pas actuellement utiliser les champs de carte des identités pour le groupement.

+++
