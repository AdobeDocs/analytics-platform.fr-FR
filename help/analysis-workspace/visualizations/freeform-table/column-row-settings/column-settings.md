---
description: Découvrez comment modifier les paramètres des colonnes pour configurer la mise en forme des colonnes, dont certaines peuvent être conditionnelles.
title: Paramètres des colonnes
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 94%

---

# [!UICONTROL Paramètres des colonnes]

Grâce aux [!UICONTROL paramètres des colonnes], vous pouvez configurer la mise en forme des colonnes, dont certains éléments peuvent être conditionnels.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Paramètres des lignes et des colonnes dans un tableau à structure libre](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


Pour accéder aux [!UICONTROL Paramètres des colonnes], sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de colonne.

![Paramètres des colonnes](assets/column-settings.png)


Vous pouvez modifier les paramètres pour plusieurs colonnes à la fois. Sélectionnez plusieurs colonnes, puis ![Paramètre](/help/assets/icons/Setting.svg) dans l’une des colonnes sélectionnées. Toute modification s’applique à l’ensemble des colonnes dont certaines cellules sont sélectionnées.

| Option | Description |
| --- | --- |
| **[!UICONTROL Afficher le total]** | Affichez une somme côté client de la colonne. Ce total **ne déduplique pas** les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher le total général]** | Affichez une somme côté serveur de la colonne. Le total général déduplique les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher les graphiques sparkline]** | Affichez un graphique en courbes dans l’en-tête des colonnes. |
| **[!UICONTROL Nombre]** | Déterminez si une cellule affiche/masque la valeur numérique pour la mesure. Par exemple, si la mesure est Pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
| **[!UICONTROL Pour cent]** | Déterminez si une cellule affiche/masque la valeur de pourcentage pour la mesure. Par exemple, si la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne. Remarque : des pourcentages supérieurs à 100 % sont possibles pour garantir l’exactitude. La limite supérieure peut passer à 1 000 % pour éviter que la largeur des colonnes ne devienne trop grande. |
| **[!UICONTROL Afficher les anomalies]** | Déterminez si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
| **[!UICONTROL Afficher la prévision]** | Déterminez si les valeurs de prévision sont affichées dans cette colonne. |
| **[!UICONTROL Renvoyer à la ligne le texte d’en-tête]** | Renvoyez à la ligne le texte de l’en-tête dans les tableaux à structure libre afin de rendre les en-têtes plus lisibles et les tableaux plus faciles à partager. Le renvoi à la ligne est utile pour le rendu PDF et pour les mesures dont le nom est long. Activé par défaut. |
| **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]** | Pour les cellules dont la valeur est 0, déterminez s’il convient d’afficher un 0 ou une cellule vierge. Ce paramètre est utile lorsque vous examinez les données pour chaque jour d’un mois et que certains jours n’ont pas encore eu lieu. Des cellules vierges peuvent être affichées au lieu de 0 pour les dates futures. Les graphiques respectent également ce paramètre (en d’autres termes, ils n’affichent pas de ligne ou de barre avec des valeurs 0). |
| **[!UICONTROL Arrière-plan]** | Déterminez si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique à barres et la mise en forme conditionnelle. |
| **[!UICONTROL Graphique à barres]** | Affichez un graphique à barres horizontales représentant la valeur de la cellule par rapport au total de la colonne. |
| **[!UICONTROL Mise en forme conditionnelle]** | Utilisez la mise en forme conditionnelle. Voir la [section](#conditional-formatting) ci-dessous. |
| **[!UICONTROL Aperçu des cellules de tableau]** | Aperçu de l’aspect de chaque cellule après application des options de mise en forme actuellement sélectionnées. |
| **[!UICONTROL Utiliser le modèle d’attribution différent du modèle par défaut]** | Utilisez un modèle d’attribution différent du modèle par défaut. Voir la [section](#use-non-default-attribution-model) ci-dessous. |

## Mise en forme conditionnelle {#conditional-formatting}

La mise en forme conditionnelle applique la mise en forme aux limites supérieure, moyenne et inférieure que vous pouvez définir. L’application d’une mise en forme conditionnelle dans les tableaux à structure libre est également activée automatiquement sur les répartitions, sauf si des limites [!UICONTROL personnalisées] sont sélectionnées.

![Mise en forme conditionnelle](./assets/conditional-formatting.png)

| Options de mise en forme conditionnelle | Description |
| --- | --- |
| **[!UICONTROL Utiliser des limites en pourcentage]** | Modifiez la plage de limites pour qu’elle soit basée sur des pourcentages plutôt que sur des valeurs absolues. La plage de limites en pourcentage fonctionne avec les mesures qui reposent uniquement sur des pourcentages (comme Taux de rebond) et celles qui reposent sur un nombre et un pourcentage (comme Pages vues). |
| **[!UICONTROL Génération automatique]** | Calculer automatiquement les limites hautes/moyennes/basses en fonction des données. La limite supérieure est la valeur la plus élevée de cette colonne. La limite inférieure est la valeur la plus faible et la valeur moyenne est la moyenne entre les limites supérieure et inférieure. |
| **[!UICONTROL Personnalisé]** | Attribuez manuellement les valeurs **[!UICONTROL Limite supérieure]**, **[!UICONTROL Milieu]** et **[!UICONTROL Limite inférieure]**. Vous disposez grâce aux limites de la flexibilité nécessaire pour déterminer si la valeur d’une colonne devient bonne, moyenne ou mauvaise. |
| **[!UICONTROL Palette de mise en forme conditionnelle]** | Appliquez un jeu de couleurs préconfiguré aux cellules. En fonction du modèle de couleurs sélectionné parmi les quatre disponibles, différentes couleurs sont attribuées aux valeurs élevées, aux valeurs intermédiaires et aux valeurs faibles. <br> Le remplacement d’une dimension du tableau réinitialise les limites de la mise en forme conditionnelle. Le remplacement d’une mesure recalcule les limites de cette colonne (lorsqu’une mesure se trouve sur l’axe des abscisses et une dimension sur l’axe des ordonnées). |

## Utiliser un modèle d’attribution différent du modèle par défaut {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="Utiliser un modèle d’attribution différent du modèle par défaut"
>abstract="Activez un modèle d’attribution autre que celui par défaut pour les colonnes sélectionnées."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="Utiliser un modèle d’attribution différent du modèle par défaut"
>abstract="Le mode d’attribution autre que celui par défaut n’est pas disponible pour cette mesure."

<!-- markdownlint-enable MD034 -->



Vous pouvez remplacer le modèle d’attribution par défaut configuré dans [Vues de données](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Tenez compte des points suivants lors de la mise à jour de l’attribution d’un composant à un modèle d’attribution autre que celui par défaut :
>
>* **Lors de l’utilisation du composant dans un rapport avec *une seule dimension* :** l’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>* **Lors de l’utilisation du composant dans un rapport avec *plusieurs dimensions* :** l’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution différent du modèle par défaut est utilisé.
>
>   Plusieurs dimensions sont disponibles uniquement lors de l’[export de données vers le cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Pour plus d’informations sur l’attribution, consultez [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).

Pour utiliser un modèle d’attribution autre que celui par défaut pour une mesure dans une Analysis Workspace :

1. Sélectionnez **[!UICONTROL Utiliser le modèle d’attribution différent du modèle par défaut]**. Lorsque cette option est déjà sélectionnée, utilisez **[!UICONTROL Modifier]** pour modifier le modèle d’attribution. Vous pouvez également désélectionner cette option pour revenir au modèle d’attribution par défaut.

   ![Options des paramètres des colonnes mettant en surbrillance l’option Paramètres des données : Utiliser un mode d’attribution autre que celui par défaut.](assets/attribution-checkbox.png)

2. Dans **[!UICONTROL Modèle d’attribution de colonne]**, sélectionnez un **[!UICONTROL Modèle]** et un **[!UICONTROL Intervalle de recherche en amont]**. L’intervalle de recherche en amont détermine la fenêtre d’attribution des données qui sera appliquée à chaque conversion.

   ![Options du modèle d’attribution de colonne affichant l’option Linéaire sélectionnée.](assets/attribution-select.png)


### Modèles d’attribution

{{attribution-models-details}}

### Conteneur

{{attribution-container}}

### Intervalle de recherche en amont

{{attribution-lookback-window}}

### Exemple

{{attribution-example}}

>[!MORELIKETHIS]
>
>* [Gérer les sources de données](/help/analysis-workspace/visualizations/t-sync-visualization.md)
