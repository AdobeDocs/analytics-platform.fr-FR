---
title: FAQ sur l’Analyse cross-canal
description: Questions fréquentes à propos de l’Analyse cross-canal
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
source-git-commit: 2be442915587780ce41f33b13e27b8cf44e239a6
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 46%

---

# Questions fréquentes

## Comment puis-je utiliser l’ACC pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Identifiant du jeu de données » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension Identifiant du jeu de données, vous pouvez utiliser un jeu de données de recherche.

## Jusqu’à combien de temps en arrière les visiteurs de l’ACC doivent-ils recomposer leurs données ?

La période de recherche arrière permettant de recomposer des données dépend de la fréquence souhaitée de [lecture](replay.md) des données. Par exemple, si vous configurez l’ACC pour qu’elle lise les données une fois par semaine, la période de recherche arrière pour la recomposition des données est de 7 jours. Si vous définissez l’ACC pour qu’elle lise les données tous les jours, la période de recherche arrière de recomposition des données est d’un jour.

## Comment les appareils partagés sont-ils gérés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’identifiant transitoire a priorité sur l’identifiant persistant, de sorte que les appareils partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même appareil).

## Comment l’ACC gère-t-elle les situations où une seule personne a un grand nombre d’identifiants persistants ?

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’identifiants persistants. Par exemple, une personne efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Le nombre d’identifiants persistants n’est pas pertinent pour l’identifiant transitoire. Un seul utilisateur peut appartenir à n’importe quel nombre d’appareils sans que cela n’ait d’incidence sur la capacité de l’ACC à faire le lien entre les appareils.

## Une fois que j’ai contacté mon gestionnaire de compte pour obtenir les informations souhaitées, combien de temps faut-il pour que le jeu de données recomposées soit disponible ?

L’assemblage en direct est disponible environ une semaine après l’activation de l’Analyse cross-canal par Adobe. La disponibilité du renvoi dépend de la quantité de données existantes. Les petits jeux de données (moins d’un million d’événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard d’événements par jour) peuvent prendre une semaine ou plus.

## Comment la fonctionnalité Analyse cross-canal gère-t-elle les demandes RGPD et CCPA ?

Adobe traite les demandes RGPD et CCPA conformément aux lois locales et internationales. Adobe propose [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour soumettre des demandes d’accès et de suppression de données. Ces demandes s’appliquent aussi bien aux jeux de données originales qu’aux jeu de données recomposées.

## Que se passe-t-il si le champ Identifiant persistant d’un ou de plusieurs événements est vide ?

Si le champ `Persistent ID` est vide sur un événement d’un jeu de données assemblé à l’aide de l’assemblage de la base de champ, l’ACC renseigne la balise `Stitched ID` de cet événement de l’une des deux façons suivantes :
* Si le champ `Transient ID` n’est pas vide, l’ACC utilise la valeur `Transient ID` comme `Stitched ID`.
* Si le champ `Transient ID` est vide, l’ACC laisse également `Stitched ID` vide. Dans ce cas, `Persistent ID`, `Transient ID` et `Stitched ID` seront tous vides sur l’événement. Les événements de ce type sont ignorés de CJA dans toute connexion CJA à l’aide du jeu de données assemblé où `Stitched ID` a été sélectionné comme `Person ID`.

## Comment les mesures dans les jeux de données assemblés CJA se comparent-elles aux mesures similaires dans les jeux de données désassemblés CJA et avec Adobe Analytics traditionnel ?

Certaines mesures dans CJA sont similaires aux mesures dans Analytics traditionnel, mais d’autres sont très différentes, selon ce que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données groupées CJA** | **données désassemblées CJA** | **Adobe Analytics traditionnelle** | **Analytics Ultimate avec les analyses entre appareils** |
| ----- | ----- | ----- | ----- |
| **Personnes**  = Nombre de  `Person ID`s distinctes où  `Stitched ID` est sélectionné comme  `Person ID`. **** Les personnes peuvent être supérieures ou inférieures à  **Visiteurs** uniques dans Adobe Analytics traditionnel, selon le résultat du processus de regroupement. | **Personnes**  = Nombre de  `Person ID`s distincts selon la colonne sélectionnée comme  `Person ID`. **** Les jeux de données People Adobe Analytics Connector (ADC) sont similaires aux  **Visiteurs** uniques dans Adobe Analytics traditionnels si  `endUserIDs. _experience. aaid.id` est sélectionné comme  `Person ID` dans CJA. | **Visiteurs uniques**  = Nombre d’identifiants visiteur distincts. Notez que **Visiteurs uniques** peut ne pas être identique au nombre de **ECID** distincts. | Voir [Personnes](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en). |
| **Sessions** : est défini en fonction des paramètres de sessionisation spécifiés dans la vue de données CJA ; Le processus de regroupement peut combiner des sessions individuelles de plusieurs appareils en une seule session. | **Sessions** : est défini en fonction des paramètres de sessionisation spécifiés dans la vue de données CJA ; | **Visites** : Voir  [Visites](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en). | **Visites** : est défini en fonction des paramètres de sessionisation définis dans la suite de rapports virtuelle des  [Analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en). |
| **Événements**  = nombre de lignes dans les données regroupées dans CJA. En règle générale, cette valeur doit être proche de **Occurrences** dans Adobe Analytics traditionnel. Notez toutefois que la FAQ ci-dessus concernant les lignes avec un `Persistent ID` vide. | **Events**  = nombre de lignes dans les données désassemblées dans CJA. En règle générale, cette valeur doit être proche de **Occurrences** dans Adobe Analytics traditionnel. Notez toutefois que si des événements comportent une balise `Person ID` vide dans les données désassemblées du lac de données AEP, ces événements seront ignorés (non inclus) dans CJA. | **Occurrences** : Voir  [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). | **Occurrences** : Voir  [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). |

D’autres mesures peuvent être similaires dans CJA et dans Adobe Analytics traditionnel. Par exemple, le nombre total pour les [événements personnalisés ](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en) Adobe Analytics (événements 1-100) doit généralement être très proche dans les Adobe Analytics et CJA traditionnels (assemblés ou désassemblés). Notez toutefois que cela peut ne pas toujours être vrai en raison des [différences de fonctionnalités](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en) telles que la déduplication des événements entre CJA et Adobe Analytics traditionnel.
