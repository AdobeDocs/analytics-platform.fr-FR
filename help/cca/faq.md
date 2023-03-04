---
title: FAQ sur Cross-Channel Analytics
description: Questions fréquentes à propos de Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: dac10a1e4848514661bf06fe71d233da6f9aa878
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 97%

---

# Questions fréquentes

## Comment puis-je utiliser l’CCA pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) et créez un projet Espace de travail vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Identifiant du jeu de données » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension Identifiant du jeu de données, vous pouvez utiliser un jeu de données de recherche.

## Jusqu’à combien de temps en arrière les visiteurs de l’CCA doivent-ils recomposer leurs données ?

La période de recherche arrière permettant de recomposer des données dépend de la fréquence souhaitée de [lecture](replay.md) des données. Par exemple, si vous configurez l’CCA pour qu’elle lise les données une fois par semaine, la période de recherche arrière pour la recomposition des données est de sept jours. Si vous configurez l’CCA pour qu’elle lise les données tous les jours, la période de recherche arrière de recomposition des données est d’un jour.

## Comment les appareils partagés sont-ils gérés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’identifiant transitoire a priorité sur l’identifiant persistant, de sorte que les appareils partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même appareil).

## Comment l’CCA gère-t-elle les situations où une seule personne a un grand nombre d’identifiants persistants ?

Dans certains cas, un utilisateur individuel peut être associé à un grand nombre d’identifiants persistants. Par exemple, une personne efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Le nombre d’identifiants persistants n’est pas pertinent pour l’identifiant transitoire. Un seul utilisateur peut appartenir à n’importe quel nombre d’appareils sans que cela n’ait d’incidence sur la capacité de l’CCA à faire le lien entre les appareils.

## Une fois que j’ai contacté mon équipe de compte d’Adobe avec les informations souhaitées, combien de temps faut-il pour que le jeu de données recomposées soit disponible ?

L’assemblage en direct est disponible environ une semaine après l’activation de Cross-Channel Analytics par Adobe. La disponibilité du renvoi dépend de la quantité de données existantes. Les petits jeux de données (moins d’un million d’événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard d’événements par jour) peuvent prendre une semaine ou plus.

## Quelle est la différence entre l’analyse entre appareils (une fonctionnalité d’Analytics classique) et l’analyse cross-canal ?

L’[analyse entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) est une fonctionnalité spécifique à Adobe Analytics classique qui vous permet de comprendre le comportement des personnes sur plusieurs périphériques. Elle offre deux workflows pour lier les données de l’appareil : l’assemblage basé sur les champs et le graphique d’appareil.

L’[analyse cross-canal](/help/cca/overview.md) est une fonctionnalité spécifique à CJA qui vous permet de comprendre le comportement des personnes à la fois sur plusieurs périphériques et plusieurs canaux. Elle recrée l’ID de personne d’un jeu de données, ce qui permet de combiner facilement ce jeu de données avec d’autres. Cette fonctionnalité s’exécute de la même manière que l’assemblage basé sur les champs de l’analyse entre appareils, avec cependant une implémentation distincte en raison de l’architecture des données qui diffère entre Analytics classique et CJA.

## Comment la fonctionnalité Cross-Channel Analytics gère-t-elle les demandes RGPD et CCPA ?

Adobe traite les demandes RGPD et CCPA conformément aux lois locales et internationales. Adobe propose [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour soumettre des demandes d’accès et de suppression de données. Ces demandes s’appliquent aussi bien aux jeux de données originaux qu’aux jeux de données recomposés.

## Que se passe-t-il si le champ de lʼidentifiant persistant dʼun ou de plusieurs événements est vide ?

Si le champ `Persistent ID` dʼun événement dans un jeu de données assemblé à lʼaide du groupement basé sur les champs est vide, lʼCCA renseigne le champ `Stitched ID` de cet événement de lʼune des deux façons suivantes :

* si le champ `Transient ID` nʼest pas vide, lʼCCA utilise la valeur du champ `Transient ID` en tant que `Stitched ID`.
* si le champ `Transient ID` est vide, lʼCCA laisse également le champ `Stitched ID` vide. Dans ce cas, les champs `Persistent ID`, `Transient ID` et `Stitched ID` sont tous vides pour lʼévénement. Ces types d’événements sont ignorés de toute connexion CJA utilisant le jeu de données assemblé là où `Stitched ID` a été choisi comme `Person ID`.

## En quoi diffèrent les mesures dans les jeux de données assemblés CJA par rapport aux mesures similaires dans les jeux de données désassemblés CJA et dʼAdobe Analytics traditionnel ?

Certaines mesures dans CJA sont similaires à celles dans Adobe Analytics traditionnel, mais dʼautres sont très différentes, en fonction des éléments que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données assemblées CJA** | **Données désassemblées CJA** | **Adobe Analytics traditionnel** | **Analytics Ultimate avec CDA** |
| ----- | ----- | ----- | ----- |
| **Personnes** = nombre de `Person ID` distincts où `Stitched ID` est sélectionné en tant que `Person ID`. Le nombre de **Personnes** peut être plus ou moins élevé que les **Visiteurs uniques** dans Adobe Analytics traditionnel, en fonction du résultat du processus dʼassemblage. | **Personnes** = nombre de `Person ID` distincts en fonction de la colonne sélectionnée en tant que `Person ID`. Les **Personnes** dans les jeux de données du connecteur Adobe Analytics sont similaires aux **Visiteurs uniques** dans Adobe Analytics traditionnel si `endUserIDs._experience.aaid.id` est sélectionné en tant que `Person ID` dans CJA. | **Visiteurs uniques** = nombre dʼidentifiants de visiteur distincts. Le nombre de **Visiteurs uniques** peut être différent du nombre d’**ECID** distincts. | Voir [Personnes](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=fr). |
| **Sessions** : défini en fonction des paramètres de session dans la vue de données CJA. Le processus dʼassemblage peut combiner des sessions individuelles provenant de plusieurs appareils en une seule session. | **Sessions** : défini en fonction des paramètres de session spécifiés dans la vue de données CJA. | **Visites** : voir [Visites](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=fr). | **Visites** : défini en fonction des paramètres de session réglés dans la [suite de rapports virtuelle CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=fr). |
| **Événements** = nombre de lignes dans les données CJA assemblées. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Notez toutefois que la FAQ ci-dessus concernant les lignes avec un champ `Persistent ID` vide. | **Événements** = nombre de lignes dans les données CJA désassemblées. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Remarquez toutefois que si des événements dont le champ `Person ID` est vide dans les données désassemblées du lac de données Experience Platform, ces événements ne sont pas inclus dans CJA. | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). |

Dʼautres mesures peuvent être similaires dans CJA et Adobe Analytics classique. Par exemple, le nombre total dʼ[événements personnalisés](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=fr) Adobe Analytics 1-100 est en principe très similaire dans Adobe Analytics classique et CJA (vaut pour les événements assemblés comme désassemblés). Les [différences de capacités](/help/getting-started/aa-vs-cja/cja-aa.md), comme la déduplication des événements entre CJA et Adobe Analytics classique, peuvent entraîner des incohérences entre les deux produits.

## L’CCA peut-elle utiliser les champs de carte des identités ?

Non, pour le moment, l’CCA ne peut pas utiliser les champs de carte des identités.
