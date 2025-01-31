---
description: Découvrez comment modifier les paramètres des colonnes pour configurer la mise en forme des colonnes, dont certaines peuvent être conditionnelles.
title: Paramètres des colonnes
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 21%

---

# [!UICONTROL Paramètres des colonnes]

[!UICONTROL Paramètres des colonnes] vous permet de configurer le formatage des colonnes, qui peut parfois être conditionnel.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Paramètres de ligne et de colonne dans un tableau à structure libre](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


Pour accéder à [!UICONTROL Paramètres des colonnes], sélectionnez ![Paramètres des colonnes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) dans l’en-tête de colonne.

![Paramètres des colonnes](assets/column-settings.png)


Vous pouvez modifier les paramètres de plusieurs colonnes à la fois. Sélectionnez plusieurs colonnes et sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans l’une des colonnes sélectionnées. Toute modification que vous apportez s’applique à toutes les colonnes contenant des cellules sélectionnées.

| Option | Description |
| --- | --- |
| **[!UICONTROL Afficher le total]** | Afficher une somme côté client de la colonne. Ce total ne déduplique **pas** les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher le total général]** | Afficher une somme côté serveur de la colonne. Le total général déduplique les mesures telles que les sessions ou les personnes. |
| **[!UICONTROL Afficher la sparkline]** | Afficher un graphique en courbes dans l’en-tête des colonnes. |
| **[!UICONTROL Nombre]** | Déterminer si une cellule affiche/masque la valeur numérique de la mesure. Par exemple, si la mesure est Pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
| **[!UICONTROL Pour cent]** | Déterminer si une cellule affiche/masque la valeur de pourcentage pour la mesure. Par exemple, si la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne.  Remarque : des pourcentages supérieurs à 100 % sont possibles pour garantir l’exactitude. La limite supérieure peut passer à 1 000 % pour éviter que la largeur des colonnes ne devienne trop grande. |
| **[!UICONTROL Afficher les anomalies]** | Déterminez si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
| **[!UICONTROL Afficher les prévisions]** | Déterminez si les valeurs de prévision sont affichées dans cette colonne. |
| **[!UICONTROL Renvoyer à la ligne le texte de l’en-tête]** | Placez le texte de l’en-tête dans des tableaux à structure libre pour rendre les en-têtes plus lisibles et les tableaux plus partageables. L’encapsulation est utile pour le rendu du PDF et pour les mesures dont les noms sont longs. Activé par défaut. |
| **[!UICONTROL Interpréter zéro comme n’étant pas une valeur]** | Déterminez, pour les cellules contenant une valeur 0, s’il faut afficher une cellule 0 ou une cellule vide. Cette interprétation est utile lorsque vous examinez les données de chaque jour d’un mois et que certains jours se situent dans le futur.  Au lieu d’afficher des zéros pour les dates futures, des cellules vides s’affichent à la place. Les graphiques respectent également ce paramètre (en d’autres termes, ils n’affichent pas de ligne ou de barre avec des valeurs 0). |
| **[!UICONTROL Contexte]** | Déterminez si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique à barres et la mise en forme conditionnelle. |
| **[!UICONTROL Graphique en barres]** | Afficher un graphique à barres horizontal représentant la valeur de la cellule par rapport au total de la colonne. |
| **[!UICONTROL Mise en forme conditionnelle]** | Utilisez la mise en forme conditionnelle. Voir la [section](#conditional-formatting) ci-dessous. |
| **[!UICONTROL Aperçu des cellules de tableau]** | Un aperçu de l’aspect de chaque cellule avec les options de mise en forme actuellement sélectionnées appliquées. |
| **[!UICONTROL Utiliser le modèle d’attribution différent du modèle par défaut]** | Utilisez un modèle d’attribution autre que celui par défaut. Voir la [section](#use-non-default-attribution-model) ci-dessous. |

## Mise en forme conditionnelle {#conditional-formatting}

La mise en forme conditionnelle applique la mise en forme aux limites supérieure, moyenne et inférieure que vous pouvez définir. L’application d’une mise en forme conditionnelle dans les tableaux à structure libre est également activée automatiquement sur les répartitions, sauf si des limites [!UICONTROL personnalisées] sont sélectionnées.

![Mise en forme conditionnelle](./assets/conditional-formatting.png)

| Options de mise en forme conditionnelle | Description |
| --- | --- |
| **[!UICONTROL Utiliser les limites en pourcentage]** | Modifier la plage de limites pour qu’elle soit basée sur des pourcentages plutôt que sur des valeurs absolues. La plage de limites en pourcentage fonctionne pour les mesures basées uniquement sur un pourcentage (comme le Taux de rebond) ainsi que pour les mesures comportant un nombre et un pourcentage (comme les Pages vues). |
| **[!UICONTROL Généré automatiquement]** | Calculer automatiquement les limites hautes/moyennes/basses en fonction des données. La limite supérieure est la valeur la plus élevée de cette colonne. La limite inférieure est la valeur la plus faible et la valeur moyenne est la moyenne entre les limites supérieure et inférieure. |
| **[!UICONTROL Personnalisé]** | Attribuez manuellement les valeurs **[!UICONTROL Limite supérieure]**, **[!UICONTROL Milieu]** et **[!UICONTROL Limite inférieure]**. Les limites permettent de déterminer quand une valeur de colonne devient bonne, moyenne ou mauvaise. |
| **[!UICONTROL Palette de mise en forme conditionnelle]** | Appliquez un jeu de couleurs préconfiguré aux cellules. En fonction des quatre modèles de couleurs disponibles que vous sélectionnez, différentes couleurs sont attribuées aux valeurs élevées, aux valeurs intermédiaires et aux valeurs faibles. <br> Le remplacement d’une dimension du tableau réinitialise les limites de la mise en forme conditionnelle. Le remplacement d’une mesure recalcule les limites de cette colonne (lorsqu’une mesure se trouve sur l’axe des abscisses et une dimension sur l’axe des ordonnées). |

## Utilisation d’un modèle d’attribution différent du modèle par défaut {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Activez un modèle d’attribution autre que celui par défaut pour les colonnes sélectionnées."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Le mode d’attribution autre que celui par défaut n’est pas disponible pour cette mesure."

<!-- markdownlint-enable MD034 -->



Vous pouvez remplacer le modèle d’attribution par défaut configuré dans [Vues de données](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Tenez compte des points suivants lors de la mise à jour de l’attribution d’un composant à un modèle d’attribution autre que celui par défaut :
>
>* **Lors de l’utilisation du composant dans un rapport avec *une seule dimension* :** l’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>* **Lors de l’utilisation du composant dans un rapport avec *plusieurs dimensions* :** l’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution autre que celui par défaut est utilisé.
>
>   Plusieurs dimensions sont disponibles uniquement lors de l’[exportation de données vers le cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Pour plus d’informations sur l’affectation, voir [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).

Pour utiliser un modèle d’attribution autre que celui par défaut pour une mesure dans une Analysis Workspace :

1. Sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**. Lorsque cette option est déjà sélectionnée, utilisez **[!UICONTROL Modifier]** pour modifier le modèle d’attribution. Vous pouvez également désélectionner cette option pour revenir au modèle d’attribution par défaut.

   ![Options des paramètres de colonne mettant en surbrillance l’option Paramètres de données : utilisez un mode d’attribution autre que celui par défaut.](assets/attribution-checkbox.png)

2. Dans **[!UICONTROL Modèle d’attribution de colonne]**, sélectionnez un **[!UICONTROL Modèle]** et un **[!UICONTROL Intervalle de recherche en amont]**. L’intervalle de recherche en amont détermine la fenêtre d’attribution des données appliquée à chaque conversion.

   ![Options du modèle d’attribution de colonne affichant Linéaire sélectionné.](assets/attribution-select.png)


### Modèles d’attribution

{{attribution-models-details}}

### Intervalle de recherche en amont

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [Gestion des sources de données](/help/analysis-workspace/visualizations/t-sync-visualization.md)
