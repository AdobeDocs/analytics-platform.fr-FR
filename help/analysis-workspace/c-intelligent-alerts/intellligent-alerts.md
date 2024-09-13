---
description: Le nouveau système d’alertes intelligentes permet de contrôler plus précisément les alertes et intègre la détection des anomalies au système d’alerte.
title: Alertes intelligentes - Aperçu
feature: Workspace Basics
role: User, Admin
source-git-commit: 17a7e794533c1536e362ca1fd11f45b053954c0a
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 52%

---

# Alertes intelligentes - Aperçu

>[!NOTE]
>
>Les alertes intelligentes sont disponibles pour tous les clients. Toutefois, pour utiliser la détection des anomalies dans les alertes intelligentes, vous devez disposer de Customer Journey Analytics Select, Prime ou Ultimate.

Les alertes intelligentes (ou simplement les &quot;alertes&quot;) dans Customer Journey Analytics vous permettent d’être averti lorsque des événements anormaux se produisent dans vos données.

Vous pouvez définir le déclenchement d’alertes en fonction de seuils d’anomalie, de modification des pourcentages ou de points de données spécifiques. Les alertes fournissent des contrôles granulaires qui s’intègrent à la [détection des anomalies](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), ce qui se déclenche lorsque vous en avez le plus besoin.

Grâce aux alertes intelligentes, vous pouvez :

* créer des alertes d’après les anomalies (seuils de 90 %, 95 %, 99 %, 99,75 % et 99,90 % ; % de changement ; au-dessus/au-dessous) ;
* prévisualiser le nombre de fois où une alerte sera déclenchée ;
* envoyer des alertes par courrier électronique ou par SMS, avec des liens vers des projets Analysis Workspace générés automatiquement ;
* créer des alertes « empilées » qui présentent plusieurs mesures dans une seule alerte

Le tutoriel vidéo suivant présente un aperçu de base des alertes : [Alertes intelligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=fr) (5:34)

## Comprendre les différences entre les alertes dans Customer Journey Analytics et Adobe Analytics

Le processus d’utilisation des alertes intelligentes dans Customer Journey Analytics est presque identique à celui des alertes intelligentes dans Adobe Analytics. Cependant, il existe des différences importantes.

Pour plus d’informations, voir [Comparaison des fonctionnalités des alertes intelligentes : Customer Journey Analytics et Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md).

## Recherche en amont des alertes par anomalies

Si une alerte utilise la détection des anomalies, la période de formation varie en fonction de la granularité sélectionnée pour l’alerte.

* Granularité mensuelle : 15 mois + même période l’an dernier
* Granularité hebdomadaire : 15 semaines + même période l’an dernier
* Granularité quotidienne : 35 jours + même période l’an dernier
* Granularité horaire : 336 heures

Pour plus d’informations, voir [Techniques statistiques de la détection des anomalies](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Créer des alertes

Pour plus d’informations sur la création d’alertes dans Customer Journey Analytics, voir [Créer des alertes](/help/analysis-workspace/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilisation de données horodatées pour créer des alertes peut entraîner un déclenchement incorrect des alertes. Adobe recommande d’utiliser des données non horodatées pour les alertes intelligentes.

## Gérer les alertes

Vous pouvez gérer les alertes existantes dans le gestionnaire d’alertes. Vous pouvez effectuer diverses tâches de gestion sur les alertes, telles que le balisage, le changement de nom, la suppression, etc.

Pour plus d’informations sur la gestion des alertes existantes en Customer Journey Analytics, voir [Gestion des alertes](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md).

