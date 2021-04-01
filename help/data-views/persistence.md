---
title: Qu’est-ce que la persistance des dimensions dans le Customer Journey Analytics ?
description: La persistance des Dimensions est une combinaison d’attribution et d’expiration. Ensemble, ils déterminent les valeurs de dimension qui persistent.
translation-type: tm+mt
source-git-commit: b99e108e9f6dd1c27c6ebb9b443f995beb71bdbd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Persistance

La persistance des Dimensions est une combinaison d’attribution et d’expiration. Ensemble, ils déterminent les valeurs de dimension qui persistent. L’Adobe vous recommande vivement de discuter au sein de votre organisation de la manière dont plusieurs valeurs pour chaque dimension sont gérées (attribution) et de la manière dont les valeurs de dimension cessent d’être conservées (expiration).

* Par défaut, une valeur de dimension utilise la dernière allocation. Les nouvelles valeurs remplacent les valeurs conservées.
* Par défaut, une valeur de dimension utilise une expiration de [!UICONTROL Session].

## Attribution

Détermine comment la CJA attribue le crédit d’un événement de réussite si une variable reçoit plusieurs valeurs avant le événement. Les valeurs acceptables sont :

* Le plus récent : la dernière valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar.
* Valeur d’origine : la première valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar.
* Instance: ??

Remarque : l’activation ou la désactivation d’une attribution de type Linéaire empêche l’affichage des données historiques. Mélanger divers types d’attribution dans l’interface de création de rapports peut se traduire par des données erronées dans les rapports. Il se peut, par exemple, qu’une attribution linéaire divise les recettes entre plusieurs valeurs eVar différentes. Après avoir rétabli le type d’attribution sur « Le plus récent », 100 % des recettes seront associées à la valeur unique la plus récente. Cette association peut mener à des conclusions incorrectes de la part des utilisateurs.

Pour éviter tout risque de confusion dans les rapports, les données historiques ne sont pas mises à la disposition des utilisateurs dans l’interface. Elles peuvent être visualisées si vous décidez de redéfinir l’eVar sur le paramètre d’attribution initial, même s’il est déconseillé de modifier les paramètres d’attribution de l’eVar aux seules fins d’accéder aux données historiques. Adobe recommande d’utiliser une nouvelle eVar lorsque de nouveaux paramètres d’attribution sont souhaités pour des données déjà en cours d’enregistrement, plutôt que de modifier les paramètres d’attribution sur une eVar qui a déjà accumulé une certaine quantité de données historiques.

## Expiration

Les valeurs de Dimension expirent après la période spécifiée. Une fois la valeur de dimension expirée, elle ne reçoit plus de crédit pour une mesure. Les Dimensions peuvent également être configurées pour expirer sur les mesures. Ainsi, dans le cas d’une promotion interne qui arrive à expiration à la fin de la visite, celle-ci ne reçoit du crédit que pour les achats ou inscriptions qui ont lieu au cours de la visite pendant laquelle ils ont été activés.

Il existe deux méthodes pour faire expirer une eVar :

Vous pouvez la configurer de manière à ce qu’elle arrive à expiration après une période ou un événement spécifique.
Vous pouvez forcer l’expiration d’une eVar en la réinitialisant, ce qui se révèle utile pour redéfinir son objectif.
Par exemple, si vous faites passer de 30 à 90 jours l’expiration d’une eVar, les valeurs d’eVar collectées continueront à persister pendant la durée du nouveau jeu d’expiration (dans ce cas, 90 jours). Le système examine simplement le paramètre d’expiration actuel et le dernier horodatage défini de la valeur eVar collectée pour déterminer l’expiration. Seule l’option Réinitialiser expire les valeurs et le fait immédiatement.

Autre exemple : Une eVar, d’une durée de validité de 21 jours, est utilisée en mai pour faire état de promotions internes, et en juin, est utilisée pour capturer des mots-clés de recherche interne. Dans ce cas, le 1er juin, vous devez forcer l’expiration de cette variable ou la réinitialiser. Ce faisant, les valeurs de promotion interne ne figureront pas dans les rapports de juin.