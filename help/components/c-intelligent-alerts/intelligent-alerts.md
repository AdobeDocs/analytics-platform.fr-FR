---
description: Les alertes permettent un contrôle granulaire des notifications et une intégration à la détection des anomalies.
title: Présentation des alertes
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 28%

---

# Présentation des alertes

Les alertes dans Customer Journey Analytics vous permettent d’être averti en fonction de pourcentages ou de points de données modifiés.

Selon votre module de Customer Journey Analytics, vous pouvez également utiliser des alertes pour les déclencher en fonction des seuils d’anomalie. Ces alertes (également appelées &quot;alertes intelligentes&quot;) fournissent des contrôles granulaires qui s’intègrent à la [détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), ce qui se déclenche lorsque vous en avez le plus besoin.

Grâce aux alertes, vous pouvez :

* prévisualiser le nombre de fois où une alerte sera déclenchée ;
* envoyer des alertes par courrier électronique ou par SMS, avec des liens vers des projets Analysis Workspace générés automatiquement ;
* créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte
* Créer des alertes d’après les anomalies (seuils de 90 %, 95 %, 99 %, 99,75 % et 99,9 % ; % de changement ; au-dessus/au-dessous) (Disponible uniquement pour les clients Customer Journey Analytics disposant d’un package Select, Prime ou Ultimate)

Le tutoriel vidéo suivant présente un aperçu de base des alertes : [Alertes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=fr) (5:34)

## Comprendre les différences entre les alertes dans Customer Journey Analytics et Adobe Analytics

Le processus d’utilisation des alertes en Customer Journey Analytics est presque identique à celui d’Adobe Analytics. Cependant, il existe des différences importantes.

Pour plus d’informations, voir [Comparaison des fonctionnalités d’alertes : Customer Journey Analytics et Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Recherche en amont des alertes par anomalies

>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelée _Alertes intelligentes_) est disponible uniquement pour les organisations qui disposent d’un package Customer Journey Analytics Select, Prime ou Ultimate.

Si une alerte utilise la détection des anomalies, la période de formation varie en fonction de la granularité sélectionnée pour l’alerte.

* Granularité mensuelle : 15 mois + même période l’an dernier
* Granularité hebdomadaire : 15 semaines + même période l’an dernier
* Granularité quotidienne : 35 jours + même période l’an dernier
* Granularité horaire : 336 heures

Pour plus d’informations, voir [Techniques statistiques de la détection des anomalies](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Créer des alertes

Pour plus d’informations sur la création d’alertes dans Customer Journey Analytics, voir [Créer des alertes](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilisation de données horodatées pour créer des alertes peut entraîner un déclenchement incorrect des alertes. Adobe recommande d’utiliser des données non horodatées pour les alertes.

## Gérer les alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer diverses tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

Pour plus d’informations sur la gestion des alertes existantes en Customer Journey Analytics, voir [Gestion des alertes](/help/components/c-intelligent-alerts/alert-manager.md).

