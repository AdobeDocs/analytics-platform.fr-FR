---
description: Découvrez comment modifier les paramètres des colonnes pour configurer le formatage des colonnes, dont certains peuvent être conditionnels.
title: Paramètres des colonnes
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 78%

---

# [!UICONTROL Paramètres des colonnes]

Grâce aux [!UICONTROL paramètres de colonne], vous pouvez configurer la mise en forme des colonnes, dont certains éléments peuvent être conditionnels.

Regardez une vidéo sur les paramètres des lignes et des colonnes ici :

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

## Modifier les [!UICONTROL paramètres de colonne] {#edit-column-settings}

Pour accéder aux [!UICONTROL Paramètres de colonne], faites glisser un tableau à structure libre vers le projet, puis cliquez sur l’icône en forme d’engrenage dans l’en-tête de la colonne.

![Les paramètres Colonne affichent les cellules de totaux, les cellules de tableau et l’aperçu des cellules de tableau.](assets/column_settings.png)

Vous pouvez modifier les paramètres **pour plusieurs colonnes à la fois**. Sélectionnez plusieurs colonnes et cliquez sur l’icône des paramètres de n’importe laquelle de ces colonnes. Toute modification que vous apportez s’applique à toutes les colonnes comportant des cellules sélectionnées.

| Élément | Description |
| --- | --- |
| Nombre | Détermine si une cellule affiche/masque la valeur numérique pour la mesure. Par exemple, si la mesure est Pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
| Pourcentage | Détermine si une cellule affiche/masque la valeur de pourcentage pour la mesure. Par exemple, si la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne.  Remarque : Nous pouvons désormais afficher les pourcentages supérieurs à 100 %, pour plus de précision. Nous avons également rehaussé le plafond supérieur à 1 000 % afin de garantir que les colonnes puissent s’adapter à une largeur trop importante. |
| Anomalies | Détermine si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
| Renvoyer à la ligne le texte d’en-tête | Permet de renvoyer à la ligne le texte de l’en-tête dans les tableaux à structure libre afin de rendre les en-têtes plus lisibles et les tableaux plus faciles à partager. Cette option est utile pour le rendu .pdf et pour les mesures dont le nom est long. Activé par défaut. |
| Interpréter zéro comme n’étant pas une valeur | Pour les cellules dont la valeur est 0, détermine s’il convient d’afficher un 0 ou une cellule vierge. Ce paramètre est utile lorsque vous examinez les données pour chaque jour d’un mois et que certains jours n’ont pas encore eu lieu.  Des cellules vierges peuvent être affichées au lieu de 0 pour les dates futures. Les diagrammes respectent également ce paramètre (c.-à-d. qu’ils n’affichent pas une ligne ou une barre avec des valeurs 0 lorsque ce paramètre est activé). |
| Contexte | Détermine si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique en barres et la mise en forme conditionnelle. |
| Graphique en barres | Affiche un graphique en barres horizontal représentant la valeur de la cellule par rapport au total de la colonne. |
| Mise en forme conditionnelle | Voir la section suivante. |
| Aperçu des cellules de tableau | Affiche un aperçu de l’aspect de chaque cellule après application des options de mise en forme actuellement sélectionnées. |

## Mise en forme conditionnelle {#conditional-formatting}

La mise en forme conditionnelle applique la mise en forme aux limites supérieure, moyenne et inférieure que vous pouvez définir. L’application d’une mise en forme conditionnelle (couleurs, etc.) dans les tableaux à structure libre est également activée automatiquement sur les répartitions, sauf si des limites « personnalisées » sont sélectionnées.

![Options de mise en forme conditionnelle avec l’option Personnalisé sélectionnée.](assets/conditional-formatting.png)

| Élément | Description |
| --- | --- |
| Mise en forme conditionnelle | Applique aux cellules un jeu de couleurs préconfiguré de votre choix. En fonction des 4 modèles de couleurs disponibles que vous sélectionnez, différentes couleurs sont attribuées aux valeurs élevées, aux valeurs intermédiaires et aux valeurs faibles. <br> Le remplacement d’une dimension du tableau réinitialise les limites de la mise en forme conditionnelle. Le remplacement d’une mesure recalcule les limites de cette colonne (lorsqu’une mesure se trouve sur l’axe des abscisses et une dimension sur l’axe des ordonnées). |
| Utiliser des limites en pourcentage | Modifier la plage de limites pour qu’elle soit basée sur des pourcentages plutôt que sur des valeurs absolues. Cette option fonctionne avec les mesures qui reposent uniquement sur des pourcentages (comme Taux de rebond) et celles qui reposent sur un nombre et un pourcentage (comme Pages vues). |
| Génération automatique | Calculer automatiquement les limites hautes/moyennes/basses en fonction des données. La limite supérieure est la valeur la plus élevée de cette colonne. La limite inférieure est la valeur la plus faible et la valeur moyenne est la moyenne entre les limites supérieure et inférieure. |
| Personnalisé | Attribuer manuellement les limites hautes/inférieures/basses. Vous disposez ainsi de la flexibilité nécessaire pour déterminer si la valeur d’une colonne devient bonne, moyenne ou mauvaise. |
| Palette de mise en forme conditionnelle | Sélectionnez l’un des 4 modèles de couleurs disponibles à utiliser pour votre mise en forme conditionnelle. |

## Utilisation d’un modèle d’attribution différent du modèle par défaut {#attribution}

Permet de remplacer le modèle d’attribution par défaut défini dans [Vues des données](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Tenez compte des points suivants lors de la mise à jour de l’attribution d’un composant vers un modèle d’attribution autre que celui par défaut :
>
>* **Lors de l’utilisation du composant dans un rapport avec *une seule dimension*:** L’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>* **Lors de l’utilisation du composant dans un rapport avec *dimensions multiples*:** L’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>   Plusieurs dimensions sont disponibles uniquement lorsque [exportation de données vers le cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Pour plus d’informations sur l’affectation, voir [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).

Pour utiliser un modèle d’attribution autre que celui par défaut pour une mesure dans Analysis Workspace :

1. Cliquez sur l’icône Paramètres (engrenage) sur une mesure dans une colonne d’un tableau à structure libre.

   ![Les options Paramètres de colonne mettent en surbrillance l’option Paramètres des données : utilisez un mode d’attribution autre que celui par défaut.](assets/attribution-checkbox.png)

2. Sous **[!UICONTROL Paramètres des données]**, cochez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**. Pour plus d’informations sur les différents modèles d’attribution, reportez-vous à la section [Modèles d’attribution](/help/data-views/component-settings/attribution.md).

   ![Les options du modèle d’attribution de colonnes affichant Linéaire sélectionné.](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Gestion des sources de données](/help/analysis-workspace/visualizations/t-sync-visualization.md)
