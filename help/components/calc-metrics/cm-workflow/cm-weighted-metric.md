---
description: Affiche des exemples de mesures calculées.
title: Exemples de mesures calculées
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Exemples de mesures calculées

Cet article présente des exemples de définition de mesures calculées plus avancées.

## Taux de rebond

Vous souhaitez calculer le taux de rebond.

+++ Détails

La définition d’un rebond fait l’objet d’une autre discussion, mais dans cet exemple, vous définissez un filtre Événements de rebond où Démarrage de session est égal à 1 et Fin de session est égal à 1. Vous utilisez ce filtre pour définir le taux de rebonds des sessions.


### Filtre

![Événements de rebond](assets/example-bounce-bouncedevents.png)

### Mesure calculée

![Taux de rebond](assets/example-bounce-rate.png)


### Champs dérivés

Vous pouvez également définir un taux de rebond [à l’aide de champs dérivés](/help/data-views/derived-fields/derived-fields.md#bounces).

Les champs dérivés font partie d’une vue de données qui présente l’avantage que tous les utilisateurs ne peuvent pas remplacer ou modifier la définition d’une mesure de taux de rebond. Cet avantage introduisit également une limitation. Les utilisateurs qui n’ont pas accès à une vue de données ne peuvent pas utiliser de champs dérivés et doivent recourir à des filtres et des mesures calculées pour définir un taux de rebond.

Pour plus d’informations sur le calcul des rebonds et du taux de rebond en Customer Journey Analytics, reportez-vous à cette [publication de blog](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Pages vues conditionnelles

Vous souhaitez définir une mesure calculée qui calcule uniquement les pages vues pour les pages qui ont été visitées au cours de plus de 100 sessions.

+++ Détails

![Pages vues conditionnelles](assets/conditional-page-views.png)

+++

## Pages vues pour les 30 % premières sessions

Vous souhaitez définir une mesure calculée qui calcule uniquement les pages vues pour les 30 % premières sessions.

+++ Détails

![30 % de pages vues les plus consultées](assets/top30-page-views.png)

+++
