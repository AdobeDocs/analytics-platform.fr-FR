---
description: Découvrez comment utiliser les alertes pour un contrôle granulaire des notifications et leur intégration à la détection des anomalies.
title: Vue d’ensemble des alertes
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# Vue d’ensemble des alertes

Les alertes dans Customer Journey Analytics envoient un avertissement en fonction de pourcentages ou de points de données spécifiques modifiés.

Selon votre package Customer Journey Analytics, vous pouvez également déclencher les alertes en fonction des seuils d’anomalie. Ces alertes (également appelées *Alertes intelligentes*) fournissent des commandes granulaires qui s’intègrent à la [Détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) et se déclenchent lorsque vous en avez le plus besoin.

* Prévisualisez la fréquence de déclenchement d’une alerte.
* Envoyer des alertes par e-mail ou par SMS, avec des liens pour générer automatiquement les projets Analysis Workspace.
* Créez des alertes *empilées* qui capturent plusieurs mesures dans une seule alerte.
* Créer des alertes en fonction de :
   * Anomalies des mesures qui existent, sont supérieures ou inférieures aux valeurs de seuil attendues.

     [Détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) crée une valeur attendue ainsi qu’une limite supérieure et inférieure à l’aide des données historiques. Si la valeur de la mesure réelle dépasse la limite supérieure ou est inférieure à la limite inférieure définie comme valeur de seuil, cet événement est considéré comme une anomalie au niveau de confiance du seuil et déclenche l’alerte. Un seuil plus élevé (par exemple : 99 % ou 99,9 %) implique une bande plus large, ce qui entraîne moins d’alertes provoquées par des anomalies plus extrêmes. Un seuil inférieur (par exemple : 90 %) implique une bande plus étroite, ce qui entraîne plus d’alertes provoquées par des anomalies moins extrêmes.
   * Modification des mesures selon un pourcentage spécifique.
   * Mesures supérieures, inférieures ou égales à une valeur spécifique. (disponible uniquement pour les clients Adobe Analytics avec un package Select, Prime ou Ultimate)

Ce [tutoriel vidéo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fournit un aperçu de base des alertes.



## Comprendre en quoi les alertes diffèrent

Le processus d’utilisation des alertes dans Customer Journey Analytics est presque identique à celui des alertes dans Adobe Analytics. Cependant, il existe des différences importantes.

Pour plus d’informations, consultez [Comparaison des fonctionnalités d’alertes : Customer Journey Analytics et Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Recherche en amont des alertes par anomalies

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un forfait Customer Journey Analytics Select, Prime ou Ultimate.

Si une alerte utilise la détection des anomalies, la période de formation varie en fonction de la granularité sélectionnée pour l’alerte.

* Granularité mensuelle : 15 mois + même période l’an dernier
* Granularité hebdomadaire : 15 semaines + même période l’an dernier
* Granularité quotidienne : 35 jours + même période l’an dernier
* Granularité horaire : 336 heures

Pour en savoir plus, consultez [Techniques statistiques utilisées dans la détection des anomalies](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Créer des alertes

Pour plus d’informations sur la création d’alertes dans Customer Journey Analytics, consultez [Création d’alertes](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilisation de données horodatées pour créer des alertes peut entraîner un déclenchement incorrect des alertes. Adobe recommande d’utiliser des données non horodatées pour les alertes.

## Gérer les alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer différentes tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

Pour plus d’informations sur la gestion des alertes existantes dans Customer Journey Analytics, consultez [Gérer les alertes](/help/components/c-intelligent-alerts/alert-manager.md).
