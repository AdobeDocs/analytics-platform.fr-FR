---
title: Affichage des tendances de conversion
description: Effectuez le suivi des modifications du taux de conversion au fil du temps.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# [!UICONTROL Tendances de conversion] view

La variable **[!UICONTROL Tendances de conversion]** offre une visualisation de tendance des taux de conversion au fil du temps. L’axe horizontal correspond à un intervalle de temps, tandis que l’axe vertical représente le taux de conversion.

>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Suivi des efforts d’optimisation**: après avoir identifié les goulets d’étranglement clés que vous souhaitez améliorer à l’aide de [Friction](friction.md), vous pouvez utiliser cette vue pour suivre l’impact de ces optimisations sur le taux de conversion au fil du temps.
* **Évaluation des tests A/B**: évaluer l’efficacité des tests A/B ou des expériences menées dans le contexte d’un entonnoir. En comparant les taux de conversion entre différentes variations, vous pouvez facilement déterminer les tests qui génèrent des taux de conversion plus élevés, ce qui entraîne des décisions basées sur les données autour des variations à mettre en oeuvre de manière permanente.
* **Évaluation de campagnes dans le temps**: mesurez l’efficacité des campagnes marketing dans le temps. Vous pouvez créer un segment qui se concentre sur les utilisateurs qui ont touché une campagne donnée et comparer leurs taux de conversion à d’autres campagnes. Vous pouvez également comparer les taux de conversion actuels à des campagnes similaires qui ont été exécutées dans le passé.

## Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Affichage]**: basculez entre ce type de vue et [Friction](friction.md).
* **[!UICONTROL Étapes]**: points de contact de l’événement dont vous souhaitez effectuer le suivi. Chaque barre du graphique représente une étape. Vous pouvez inclure jusqu’à dix étapes.
* **[!UICONTROL Compté comme]**: méthode de comptage à appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Utilisateurs] et [!UICONTROL Sessions].
* **[!UICONTROL Segments]**: segments sur lesquels vous souhaitez comparer l’entonnoir. Chaque segment sélectionné divise chaque étape en plusieurs barres. Chaque couleur représente un segment différent. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

La variable [!UICONTROL Tendances de conversion] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Type de graphique]**: type de visualisation que vous souhaitez utiliser. Les options incluent [!UICONTROL Ligne].
* **[!UICONTROL Conversion depuis]**: détermine le calcul du pourcentage d’une étape à l’autre. Les options incluent le calcul de la conversion à partir de [!UICONTROL Première étape] ou [!UICONTROL Étape précédente].

>[!NOTE]
>
>La variable **Moyenne** La colonne du tableau de vue Tendances de conversion diffère de la colonne **Total** dans la colonne [Vue Friction](friction.md) table. Le premier est une moyenne des colonnes d’intervalle (par exemple, la moyenne des taux de conversion quotidiens), tandis que le second est un calcul agrégé sur toute la période.

## Comparaison de temps

{{apply-time-comparison}}

![Comparaison des tendances de conversion](../assets/conversion-trends-compare.png){style="border:1px solid gray"}

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendances. Les options valides sont : Par heure, Par jour, Par semaine, Par mois et Par trimestre. Les intervalles peuvent être différents pour une même période, ce qui affecte le nombre de points de données dans le graphique et le nombre de colonnes dans le tableau. Par exemple, l’affichage d’une analyse couvrant trois jours avec une granularité quotidienne afficherait uniquement trois points de données, tandis qu’une analyse couvrant trois jours avec une granularité horaire afficherait 72 points de données.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
