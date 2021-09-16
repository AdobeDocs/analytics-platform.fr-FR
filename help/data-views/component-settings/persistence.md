---
title: Paramètres des composants de persistance
description: Déterminez comment ou si les valeurs de dimension persistent d’un événement à l’autre.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 23%

---


# Paramètres des composants de persistance

La persistance permet à une valeur de dimension donnée de se relier à une mesure au-delà de l’événement sur lequel elle est définie. Il utilise une combinaison d’attribution et d’expiration.

* **** L’affectation vous permet de déterminer la valeur conservée lorsque plusieurs éléments de dimension peuvent persister à la fois dans une seule colonne.
* **** L’expiration vous permet de déterminer la durée pendant laquelle un élément de dimension persiste au-delà de l’événement sur lequel il est défini.

La persistance n’est disponible que sur les dimensions et est rétroactive aux données auxquelles elle est appliquée. Il s’agit d’une transformation immédiate des données qui se produit avant l’application du filtrage ou d’autres opérations d’analyse.

![Persistance](../assets/persistence.png)

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Définir la persistance] | Activez la persistance pour la dimension. Si la persistance n’est pas activée, la dimension se rapporte uniquement aux mesures qui existent dans le même événement. Ce paramètre est désactivé par défaut. |
| [!UICONTROL Attribution] | Permet de définir le modèle dʼattribution utilisé sur une dimension pour la persistance. Les options sont les suivantes : [!UICONTROL Plus récent], [!UICONTROL Original], [!UICONTROL Instance], [!UICONTROL Tous]. |
| [!UICONTROL Expiration] | Permet de définir la période de persistance pour une dimension. Les options sont les suivantes : [!UICONTROL Session] (par défaut), [!UICONTROL Personne], [!UICONTROL Heure personnalisée], [!UICONTROL Mesure]. Il se peut que vous ayez besoin de pouvoir faire expirer la dimension lors dʼun achat (comme les termes de recherche interne ou dʼautres cas dʼutilisation du marchandisage). Le délai d’expiration maximal que vous pouvez définir est de 90 jours. Si vous sélectionnez une allocation de [!UICONTROL Toutes], seule l’expiration [!UICONTROL Session] ou [!UICONTROL Personne] est disponible. |

## Paramètres d’affectation

Détails sur les paramètres d’affectation disponibles.

* **Le plus récent** : conserve la valeur la plus récente (par horodatage) présente dans la dimension. Toutes les valeurs suivantes qui se produisent pendant la période d’expiration de la dimension remplacent la valeur précédemment persistante. Si &quot;Traiter &quot;Aucune valeur&quot; comme valeur&quot; est activé sur cette dimension sous [Aucune option de valeur](no-value-options.md), les valeurs vides remplacent les valeurs précédemment conservées. Par exemple, considérez le tableau suivant avec l’attribution [!UICONTROL la plus récente] et l’expiration [!UICONTROL Session] :

   | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valeurs du jeu de données |  | C | B |  | A |
   | Affectation la plus récente |  | C | B | B | A |

* **Original** : Conserve la valeur d’origine par horodatage présente dans la dimension pour la durée de la période d’expiration. Si cette dimension comporte une valeur, elle n’est pas remplacée lorsqu’une autre valeur est affichée sur un événement suivant. Par exemple, considérez le tableau suivant avec l’attribution [!UICONTROL Original] et l’expiration [!UICONTROL Session] :

   | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valeurs du jeu de données |  | C | B |  | A |
   | Affectation dʼorigine |  | C | C | C | C |

* **Tous** : Agit de la même manière que le modèle d’attribution   Participation pour les mesures. Conserve toutes les valeurs de manière égale afin que chacune d’elles reçoive un crédit complet pour la mesure dans les rapports. Par exemple, considérez le tableau suivant avec l’attribution [!UICONTROL All] et l’expiration [!UICONTROL Session] :

   | Dimension | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valeurs du jeu de données | A | B | C |  | A |
   | Affectation Tous | A | A,B | A, B, C | A, B, C | A, B, C |

## Expiration paramètres du profil

Détails sur les paramètres d’expiration disponibles.

* **Session** : Date d’expiration après une session donnée. Fenêtre d’expiration par défaut.
* **Personne** : Expire à la fin de la fenêtre de création de rapports.
* **Heure** : Vous pouvez définir la valeur de dimension pour qu’elle expire après une période spécifiée (jusqu’à 90 jours). Cette option dʼexpiration est disponible uniquement pour les modèles dʼattribution d’origine et La plus récente. Lors de l’utilisation de l’expiration temporelle, les valeurs antérieures au début de la période de création de rapports (jusqu’à 90 jours) sont prises en compte.
* **Mesure** : Lorsque cette mesure est vue dans un accès, la valeur conservée dans la dimension est immédiatement expirée. Vous pouvez utiliser n’importe quelle mesure comme fin d’expiration pour cette dimension. Cette option d’expiration est uniquement disponible pour les paramètres d’attribution Original et Le plus récent .
