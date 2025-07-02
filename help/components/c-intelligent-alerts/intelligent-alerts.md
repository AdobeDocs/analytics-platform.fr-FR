---
description: Découvrez comment utiliser les alertes pour permettre un contrôle granulaire des notifications et l’intégration à la détection des anomalies.
title: Présentation des alertes
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 95%

---

# Vue d’ensemble des alertes

Les alertes dans Customer Journey Analytics envoient un avertissement en fonction de pourcentages ou de points de données spécifiques modifiés.

Selon votre package Customer Journey Analytics, vous pouvez également déclencher les alertes en fonction des seuils d’anomalie. Les alertes (ou « alertes intelligentes »), fournissent des contrôles granulaires qui s’intègrent à la [détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) et se déclenchent lorsque vous en avez le plus besoin.

Grâce aux alertes, vous pouvez effectuer ce qui suit :

* prévisualiser le nombre de fois où une alerte sera déclenchée ;
* envoyer des alertes par courrier électronique ou par SMS, avec des liens vers des projets Analysis Workspace générés automatiquement ;
* créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte
* Créer des alertes en fonction des anomalies (seuils de 90 %, 95 %, 99 %, 99,75 % et 99,9 % ; pourcentage de modification ; supérieur/inférieur) (disponible uniquement pour les clientes et clients Customer Journey Analytics avec un forfait Select, Prime ou Ultimate)

Le tutoriel vidéo suivant présente une vue d’ensemble de base des alertes : [Alertes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=fr) (5:34).

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
