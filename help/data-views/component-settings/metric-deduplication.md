---
title: 'Paramètres des composants : déduplication des mesures'
description: Ne comptabilise que la première occurrence dʼune mesure dans les rapports.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 100%

---

# Paramètres des composants : déduplication des mesures

La déduplication de la mesure vous permet de configurer une mesure pour ne compter que les valeurs de manière non répétitive.

| Paramètre | Description |
| --- | --- |
| Déduplication des mesures | Case à cocher vous permettant dʼactiver la déduplication de la mesure. Option désactivée par défaut. |
| Portée de la déduplication | Permet de déterminer la période sur laquelle porte le contrôle unique.<br>**Session** : seule la première occurrence de la mesure de la session est comptabilisée.<br>**Personne** : seule la première occurrence de la mesure dans la fenêtre du compte rendu des performances est comptabilisée. |
| ID de la déduplication | Permet dʼappliquer la déduplication de la mesure en fonction dʼune dimension, et non de la mesure elle-même. Utile pour appliquer la déduplication à des dimensions telles que lʼID dʼachat. |
