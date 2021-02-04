---
title: FAQ sur l’Analyse cross-canal
description: Questions fréquentes à propos de l’Analyse cross-canal
translation-type: ht
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: ht
source-wordcount: '460'
ht-degree: 100%

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
