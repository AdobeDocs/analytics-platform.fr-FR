---
title: FAQ sur Cross-Channel Analytics
description: Questions fréquentes à propos de Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 5eede8eeb5d7e8632dc0d7d580f01ccc7ac8106c
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 59%

---

# Questions fréquentes

## Comment puis-je utiliser l’ACC pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) et créez un projet Espace de travail vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants à gauche, puis faites glisser la dimension &quot;Identifiant du jeu de données&quot; vers l’emplacement central &quot;Dimension ou élément&quot;.
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension Identifiant du jeu de données, vous pouvez utiliser un jeu de données de recherche.

## Jusqu’à combien de temps en arrière les visiteurs de l’ACC doivent-ils recomposer leurs données ?

La période de recherche arrière permettant de recomposer des données dépend de la fréquence souhaitée de [lecture](replay.md) des données. Par exemple, si vous configurez l’ACC pour qu’elle lise les données une fois par semaine, la période de recherche arrière pour la recomposition des données est de sept jours. Si vous configurez l’ACC pour qu’elle lise les données tous les jours, la période de recherche arrière pour la recomposition des données est d’un jour.

## Comment les appareils partagés sont-ils gérés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’identifiant transitoire a priorité sur l’identifiant persistant, de sorte que les appareils partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même appareil).

## Comment l’ACC gère-t-elle les situations où une seule personne a de nombreux identifiants persistants ?

Dans certains cas, un utilisateur individuel peut être associé à de nombreux identifiants persistants. Par exemple, une personne efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Le nombre d’identifiants persistants n’est pas pertinent pour l’identifiant transitoire. Un seul utilisateur peut appartenir à n’importe quel nombre d’appareils sans que cela n’ait d’incidence sur la capacité de l’ACC à faire le lien entre les appareils.

## Une fois que j’ai contacté mon gestionnaire de compte pour obtenir les informations souhaitées, combien de temps faut-il pour que le jeu de données recomposées soit disponible ?

L’assemblage en direct est disponible environ une semaine après l’activation de l’option Cross-Channel Analytics par Adobe. La disponibilité du renvoi dépend de la quantité de données existantes. Les petits jeux de données (moins d’un million d’événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard d’événements par jour) peuvent prendre une semaine ou plus.

## Quelle est la différence entre Analytics sur l’ensemble des appareils (une fonctionnalité d’Analytics traditionnel) et Analytics sur l’ensemble des canaux ?

[Analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) est une fonctionnalité spécifique à Adobe Analytics traditionnel qui vous permet de comprendre comment les personnes fonctionnent sur plusieurs périphériques. Il propose deux workflows pour lier les données de l’appareil : groupement basé sur les champs et représentation graphique des appareils.

[Analyse cross-canal](../overview.md) est une fonctionnalité spécifique à CJA qui vous permet de comprendre comment les personnes opèrent sur les appareils et les canaux. Il s’agit de l’ID de personne d’un jeu de données, ce qui permet de combiner facilement ce jeu de données avec d’autres jeux de données. Cette fonctionnalité fonctionne dans la conception de la même manière que le groupement basé sur les champs des analyses entre appareils, mais la mise en oeuvre diffère de l’architecture de données traditionnelle entre Analytics et CJA.

## Comment la fonctionnalité Cross-Channel Analytics gère-t-elle les demandes RGPD et CCPA ?

Adobe traite les demandes RGPD et CCPA conformément aux lois locales et internationales. Adobe propose [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour soumettre des demandes d’accès et de suppression de données. Ces demandes s’appliquent aussi bien aux jeux de données originales qu’aux jeu de données recomposées.

## Que se passe-t-il si le champ de lʼidentifiant persistant dʼun ou de plusieurs événements est vide ?

Si le champ `Persistent ID` dʼun événement dans un jeu de données assemblé à lʼaide du groupement basé sur les champs est vide, lʼACC renseigne le champ `Stitched ID` de cet événement de lʼune des deux façons suivantes :

* si le champ `Transient ID` nʼest pas vide, lʼACC utilise la valeur du champ `Transient ID` en tant que `Stitched ID`.
* si le champ `Transient ID` est vide, lʼACC laisse également le champ `Stitched ID` vide. Dans ce cas, `Persistent ID`, `Transient ID`, et `Stitched ID` sont toutes vides sur l’événement. Ces types d’événements sont ignorés de toute connexion CJA à l’aide du jeu de données assemblé là où `Stitched ID` a été choisi comme `Person ID`.

## En quoi diffèrent les mesures dans les jeux de données assemblés CJA par rapport aux mesures similaires dans les jeux de données désassemblés CJA et dʼAdobe Analytics traditionnel ?

Certaines mesures dans CJA sont similaires à celles dans Adobe Analytics traditionnel, mais dʼautres sont très différentes, en fonction des éléments que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données assemblées CJA** | **Données désassemblées CJA** | **Adobe Analytics traditionnel** | **Analytics Ultimate avec CDA** |
| ----- | ----- | ----- | ----- |
| **Personnes** = nombre de `Person ID` distincts où `Stitched ID` est sélectionné en tant que `Person ID`. Le nombre de **Personnes** peut être plus ou moins élevé que les **Visiteurs uniques** dans Adobe Analytics traditionnel, en fonction du résultat du processus dʼassemblage. | **Personnes** = nombre de `Person ID` distincts en fonction de la colonne sélectionnée en tant que `Person ID`. **Personnes** dans les jeux de données du connecteur source Adobe est similaire à **Visiteurs uniques** dans Adobe Analytics traditionnel si `endUserIDs._experience.aaid.id` est sélectionné comme `Person ID` dans CJA. | **Visiteurs uniques** = nombre dʼidentifiants de visiteur distincts. **Visiteurs uniques** peut ne pas être identique au nombre de **ECID** s. | Voir [Personnes](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=fr). |
| **Sessions**: Défini en fonction des paramètres de session dans la vue de données CJA. Le processus dʼassemblage peut combiner des sessions individuelles provenant de plusieurs appareils en une seule session. | **Sessions**: Défini en fonction des paramètres de session spécifiés dans la vue de données CJA. | **Visites** : voir [Visites](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=fr). | **Visites**: Défini en fonction des paramètres de session spécifiés dans la variable [Suite de rapports virtuelle CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=fr). |
| **Événements** = nombre de lignes dans les données CJA assemblées. Cette mesure est généralement proche de **Occurrences** dans Adobe Analytics traditionnel. Notez toutefois que la FAQ ci-dessus concernant les lignes avec un champ `Persistent ID` vide. | **Événements** = nombre de lignes dans les données CJA désassemblées. Cette mesure est généralement proche de **Occurrences** dans Adobe Analytics traditionnel. Notez toutefois que si des événements ont une valeur vide `Person ID` dans les données désassemblées du lac de données Experience Platform, ces événements ne sont pas inclus dans CJA. | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

D’autres mesures peuvent être similaires dans CJA et dans Adobe Analytics traditionnel. Par exemple, le nombre total pour Adobe Analytics [événements personnalisés](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=fr) 1 à 100 est généralement comparable entre Adobe Analytics traditionnel et CJA (assemblé ou désassemblé). [Différences de capacités](/help/getting-started/aa-vs-cja/cja-aa.md)), comme la déduplication des événements entre CJA et Adobe Analytics traditionnel, peut entraîner des incohérences entre les deux produits.

## L’ACC peut-elle utiliser les champs de carte des identités ?

Non, l’ACC ne peut actuellement pas utiliser les champs de carte des identités.
