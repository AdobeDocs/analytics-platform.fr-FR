---
description: Utilisez la visualisation en ligne pour représenter les jeux de données de tendances (temporels).
title: Ligne
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 20%

---


# Ligne

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

La visualisation Ligne représente les mesures qui utilisent une ligne pour montrer comment les valeurs changent sur une période donnée. Pour pouvoir utiliser un graphique en courbes, le temps doit être défini comme une dimension.

![Visualisation en ligne](assets/line-viz.png)

>[!IMPORTANT]
>
>Certains paramètres de visualisation de ligne, tels que [!UICONTROL Afficher la courbe de tendance], sont actuellement en test limité. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/landing/an-releases.html)

Cliquez sur l’icône en forme d’engrenage en haut à droite de la visualisation Ligne pour accéder à [**Paramètres de visualisation**](freeform-analysis-visualizations.md) disponible. Les paramètres sont classés par :

* **Général**: Paramètres communs à tous les types de visualisation
* **Axe**: Paramètres qui affectent l’axe x ou y de la visualisation en ligne
* **Incrustations**: Options permettant d’ajouter du contexte supplémentaire à la série affichée dans la visualisation en ligne.

![Paramètres de visualisation](assets/viz-settings-modal.png)

## Modifier la granularité

Une liste déroulante de granularité accessible dans les [paramètres de visualisation](freeform-analysis-visualizations.md) permet de modifier une visualisation avec suivi des tendances (ex. ligne, barre) de chaque jour à chaque mois, etc. La granularité est également mise à jour dans le tableau de la source de données.

## Afficher min ou max

Under **[!UICONTROL Paramètres de visualisation]** > **[!UICONTROL Incrustations]** > **[!UICONTROL Afficher min/max]**, vous pouvez superposer une étiquette de valeur minimale et maximale pour mettre rapidement en évidence les pics et les vallées dans une mesure. Remarque : Les valeurs min/max sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension.

![Afficher min/max](assets/min-max-labels.png)

## Afficher le recouvrement de tendance

Under **[!UICONTROL Paramètres de visualisation]** > **[!UICONTROL Incrustations]** > **[!UICONTROL Afficher la courbe de tendance]**, vous pouvez choisir d’ajouter une courbe de tendance de régression à votre série de lignes. Les lignes de tendances permettent de représenter un schéma plus clair dans les données.

![Ligne de tendance linéaire](assets/show-linear-trendline.png)

Tous les modèles sont ajustés en utilisant les moindres carrés ordinaires :

| Modèle | Description |
| --- | --- |
| Linéaire | Crée une ligne droite parfaitement adaptée aux jeux de données linéaires simples et est utile lorsque les données augmentent ou diminuent à un rythme régulier. Équation : `y = a + b * x` |
| Logarithmique | Crée une ligne incurvée qui convient le mieux et s’avère utile lorsque le taux de changement des données augmente ou diminue rapidement, puis diminue. Une courbe de tendance logarithmique peut utiliser des valeurs négatives et positives. Équation : `y = a + b * log(x)` |
| Exponentiel | Crée une ligne incurvée et est utile lorsque les données augmentent ou diminuent à un rythme constamment croissant. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : `y = a + e^(b * x)` |
| Puissance | Crée une ligne incurvée et est utile pour les jeux de données qui comparent les mesures qui augmentent à un rythme spécifique. Cette option ne doit pas être utilisée si vos données contiennent des valeurs nulles ou négatives. Équation : `y = a * x^b` |
| Quadratique | Trouve le meilleur ajustement pour un jeu de données en forme de parabole (concave vers le haut ou vers le bas). Équation : `y = a + b * x + c * x^2` |
