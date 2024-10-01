---
description: Découvrez comment modifier les paramètres des colonnes pour configurer le formatage des colonnes, dont certains peuvent être conditionnels.
title: Paramètres des colonnes
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 19%

---

# [!UICONTROL Paramètres des colonnes]

Les [!UICONTROL paramètres de colonne] vous permettent de configurer le formatage des colonnes, dont certains peuvent être conditionnels.

+++ Affichez une démonstration vidéo de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

{{videoaa}}

+++

Pour accéder aux [!UICONTROL paramètres de colonne], sélectionnez ![Paramètres de colonne](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de colonne.

![Paramètres des colonnes](assets/column-settings.png)


Vous pouvez modifier les paramètres de plusieurs colonnes à la fois. Sélectionnez plusieurs colonnes et sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans l’une des colonnes sélectionnées. Toute modification que vous apportez s’applique à toutes les colonnes comportant des cellules sélectionnées.

| Option | Description |
| --- | --- |
| **[!UICONTROL Afficher le total]** | Afficher la somme de la colonne côté client. Ce total ne déduplique **pas** les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher le total général]** | Afficher la somme de la colonne côté serveur. Le total général déduplique les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher sparkline]** | Affichez un graphique en courbes au niveau de l’en-tête de colonne. |
| **[!UICONTROL Nombre]** | Déterminez si une cellule affiche/masque la valeur numérique de la mesure. Par exemple, si la mesure est Pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
| **[!UICONTROL Pour cent]** | Déterminez si une cellule affiche/masque la valeur de pourcentage pour la mesure. Si, par exemple, la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne.  Remarque : Les pourcentages supérieurs à 100 % sont possibles pour garantir la précision. La limite supérieure peut atteindre 1 000 % pour éviter que la largeur des colonnes ne devienne trop grande. |
| **[!UICONTROL Afficher les anomalies]** | Déterminez si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
| **[!UICONTROL Afficher la prévision]** | Déterminez si les valeurs des prévisions sont affichées dans cette colonne. |
| **[!UICONTROL Retour à la ligne du texte de l’en-tête]** | Entourez le texte de l’en-tête dans les tableaux à structure libre pour rendre les en-têtes plus lisibles et les tableaux plus faciles à partager. L’encapsulage est utile pour le rendu des PDF et pour les mesures dont le nom est long. Activé par défaut. |
| **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]** | Déterminez si, pour les cellules avec une valeur 0, une cellule 0 ou vide doit être affichée. Cette interprétation est utile lorsque vous examinez les données pour chaque jour d’un mois et que certains jours sont dans le futur.  Au lieu d’afficher des 0 pour les dates futures, des cellules vides s’affichent à la place. Les diagrammes respectent également ce paramètre (c’est-à-dire que les graphiques n’affichent pas de ligne ou de barre avec des valeurs 0). |
| **[!UICONTROL Contexte]** | Déterminez si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique en barres et la mise en forme conditionnelle. |
| **[!UICONTROL Graphique en barres]** | Afficher un graphique à barres horizontal représentant la valeur de la cellule par rapport au total de la colonne. |
| **[!UICONTROL Mise en forme conditionnelle]** | Utilisez une mise en forme conditionnelle. Voir la [section](#conditional-formatting) ci-dessous. |
| **[!UICONTROL Aperçu des cellules de tableau]** | Aperçu de l’affichage de chaque cellule avec les options de mise en forme actuellement sélectionnées appliquées. |
| **[!UICONTROL Utiliser le modèle d’attribution différent du modèle par défaut]** | Utilisez un modèle d’attribution autre que celui par défaut. Voir la [section](#use-non-default-attribution-model) ci-dessous. |

## Mise en forme conditionnelle {#conditional-formatting}

La mise en forme conditionnelle applique la mise en forme aux limites supérieure, moyenne et inférieure que vous pouvez définir. L’application d’une mise en forme conditionnelle dans les tableaux à structure libre est également activée automatiquement sur les ventilations, sauf si des limites [!UICONTROL personnalisées] sont sélectionnées.

<img src="./assets/conditional-formatting.png" alt="Options de mise en forme conditionnelle avec l’option Personnalisé sélectionnée" width="40%" />

| Options de mise en forme conditionnelle | Description |
| --- | --- |
| **[!UICONTROL Utiliser les limites de pourcentage]** | Modifier la plage de limites pour qu’elle soit basée sur des pourcentages plutôt que sur des valeurs absolues. La plage de limites de pourcentage fonctionne pour les mesures qui reposent uniquement sur des pourcentages (comme Taux de rebond) et pour les mesures qui comportent un nombre et un pourcentage (comme Pages vues). |
| **[!UICONTROL Génération automatique]** | Calculer automatiquement les limites hautes/moyennes/basses en fonction des données. La limite supérieure est la valeur la plus élevée de cette colonne. La limite inférieure est la valeur la plus faible et la valeur moyenne est la moyenne entre les limites supérieure et inférieure. |
| **[!UICONTROL Personnalisé]** | Affectez manuellement **[!UICONTROL Limite supérieure]**, **[!UICONTROL Milieu]** et **[!UICONTROL Limite inférieure]**. Les limites offrent la possibilité de déterminer quand une valeur de colonne devient bonne, moyenne ou mauvaise. |
| **[!UICONTROL Palette de mise en forme conditionnelle]** | Appliquez un jeu de couleurs préconfiguré aux cellules. Selon les modèles de couleurs disponibles que vous sélectionnez, différentes couleurs sont attribuées à des valeurs élevées, des valeurs moyennes et des valeurs faibles. <br> Le remplacement d’une dimension du tableau réinitialise les limites de la mise en forme conditionnelle. Le remplacement d’une mesure recalcule les limites de cette colonne (lorsqu’une mesure se trouve sur l’axe des abscisses et une dimension sur l’axe des ordonnées). |

## Utilisation d’un modèle d’attribution différent du modèle par défaut {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_column_usenondefaultattributionmodel"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Activation d’un modèle d’attribution autre que celui par défaut pour les colonnes sélectionnées"

<!-- markdownlint-enable MD034 -->


Vous pouvez remplacer le modèle d’attribution par défaut configuré dans [Vues de données](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Tenez compte des points suivants lors de la mise à jour de l’attribution d’un composant vers un modèle d’attribution autre que celui par défaut :
>
>* **Lors de l’utilisation du composant dans un rapport avec *une seule dimension* :** L’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>* **Lors de l’utilisation du composant dans un rapport avec *plusieurs dimensions* :** L’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>   Plusieurs dimensions sont disponibles uniquement lors de l’ [ export de données vers le cloud ](/help/analysis-workspace/export/export-cloud.md).
>
> Pour plus d’informations sur l’attribution, voir [Paramètres du composant de persistance](/help/data-views/component-settings/persistence.md).

Pour utiliser un modèle d’attribution autre que celui par défaut pour une mesure dans Analysis Workspace :

1. Sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**. Lorsqu’elle est déjà sélectionnée, utilisez **[!UICONTROL Modifier]** pour modifier le modèle d’attribution. Ou désélectionnez cette option pour revenir au modèle d’attribution par défaut.

   ![Les options de paramètre de colonne qui mettent en surbrillance l’option Paramètres des données : utilisez un mode d’attribution autre que celui par défaut.](assets/attribution-checkbox.png)

2. Dans **[!UICONTROL Modèle d’attribution de colonnes]**, sélectionnez un **[!UICONTROL modèle]** et une **[!UICONTROL fenêtre de recherche en amont]**. L’intervalle de recherche en amont détermine la fenêtre d’attribution des données appliquée pour chaque conversion.

   ![Les options du modèle d’attribution de colonnes affichant Linéaire sélectionné.](assets/attribution-select.png)


### Modèles d’attribution

{{attribution-models-details}}

### Intervalle de recherche en amont

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [Gestion des sources de données](/help/analysis-workspace/visualizations/t-sync-visualization.md)
