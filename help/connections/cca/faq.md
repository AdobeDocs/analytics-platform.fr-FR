---
title: FAQ sur l’Analyse cross-canal
description: Questions fréquentes à propos de l’Analyse cross-canal
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 100%

---

# Questions fréquentes

## Comment puis-je utiliser l’ACC pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) et créez un projet Espace de travail vide.
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

## Que se passe-t-il si le champ de lʼidentifiant persistant dʼun ou de plusieurs événements est vide ?

Si le champ `Persistent ID` dʼun événement dans un jeu de données assemblé à lʼaide du groupement basé sur les champs est vide, lʼACC renseigne le champ `Stitched ID` de cet événement de lʼune des deux façons suivantes :
* si le champ `Transient ID` nʼest pas vide, lʼACC utilise la valeur du champ `Transient ID` en tant que `Stitched ID`.
* si le champ `Transient ID` est vide, lʼACC laisse également le champ `Stitched ID` vide. Dans ce cas, les champs `Persistent ID`, `Transient ID` et `Stitched ID` seront tous vides lors de lʼévénement. Les événements de ce type sont ignorés de CJA lors de chaque connexion CJA utilisant le jeu de données en cours dʼassemblage où `Stitched ID` a été sélectionné en tant que `Person ID`.

## En quoi diffèrent les mesures dans les jeux de données assemblés CJA par rapport aux mesures similaires dans les jeux de données désassemblés CJA et dʼAdobe Analytics traditionnel ?

Certaines mesures dans CJA sont similaires à celles dans Adobe Analytics traditionnel, mais dʼautres sont très différentes, en fonction des éléments que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données assemblées CJA** | **Données désassemblées CJA** | **Adobe Analytics traditionnel** | **Analytics Ultimate avec CDA** |
| ----- | ----- | ----- | ----- |
| **Personnes** = nombre de `Person ID` distincts où `Stitched ID` est sélectionné en tant que `Person ID`. Le nombre de **Personnes** peut être plus ou moins élevé que les **Visiteurs uniques** dans Adobe Analytics traditionnel, en fonction du résultat du processus dʼassemblage. | **Personnes** = nombre de `Person ID` distincts en fonction de la colonne sélectionnée en tant que `Person ID`. Les **Personnes** dans les jeux de données du connecteur Adobe Analytics (ADC) est similaire aux **Visiteurs uniques** dans Adobe Analytics traditionnel si `endUserIDs. _experience. aaid.id` est sélectionné en tant que `Person ID` dans CJA. | **Visiteurs uniques** = nombre dʼidentifiants de visiteur distincts. Notez que le nombre de **Visiteurs uniques** peut être différent du nombre de **ECID**. | Voir [Personnes](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=fr). |
| **Sessions** : est défini en fonction des paramètres de sessionisation définis dans la vue de données CJA. Le processus dʼassemblage peut combiner des sessions individuelles provenant de plusieurs appareils en une seule session. | **Sessions** : est défini en fonction des paramètres de sessionisation définis dans la vue de données CJA. | **Visites** : voir [Visites](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=fr). | **Visites** : est défini en fonction des paramètres de sessionisation définis dans la [suite de rapports virtuelle CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=fr). |
| **Événements** = nombre de lignes dans les données CJA assemblées. En règle générale, cette valeur devrait être proche de la valeur **Occurrences** dʼAdobe Analytics traditionnel. Notez toutefois que la FAQ ci-dessus concernant les lignes avec un champ `Persistent ID` vide. | **Événements** = nombre de lignes dans les données CJA désassemblées. En règle générale, cette valeur doit être proche de la valeur **Occurrences** dʼAdobe Analytics traditionnel. Remarquez toutefois que si des événements dont le champ `Person ID` est vide dans les données désassemblées du lac de données AEP, ces événements seront ignorés (non inclus) dans CJA. | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). |

Dʼautres mesures peuvent être similaires dans CJA et Adobe Analytics traditionnel. Par exemple, le nombre total dʼ[événements personnalisés](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=fr) Adobe Analytics (événements 1-100) doit en principe être très similaire dans Adobe Analytics tradictionnel et CJA (assemblés ou désassemblés). Notez toutefois que cela peut ne pas toujours être vrai en raison des [différences en matière de fonctionnalités](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=fr), telles que la déduplication des événements, entre CJA et Adobe Analytics traditionnel.
