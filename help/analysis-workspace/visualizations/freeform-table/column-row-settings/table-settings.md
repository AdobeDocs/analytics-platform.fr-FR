---
description: Les configurations des lignes varient selon le composant déposé dans le tableau.
title: Paramètres des lignes
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 92%

---

# Paramètres des lignes


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Paramètres de ligne et de colonne dans un tableau à structure libre](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

Les paramètres des lignes varient selon le composant déposé dans le tableau. Pour accéder aux paramètres des lignes du tableau, sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) **[!UICONTROL Paramètres]** en regard d’une dimension, d’un segment, d’une mesure, d’une période ou d’une répartition dans chacun de ces objets.

![Tableau à structure libre mettant en surbrillance l’icône Paramètres pour les mesures](assets/row-settings.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Répartition par position]** | Par défaut, ce paramètre est désactivé et les répartitions sont fixées aux éléments de la ligne statique. Par exemple, imaginons que vous répartissiez les éléments de la dimension 3 premières pages (page d’accueil, résultats de recherche et passage en caisse) par canal marketing. Ensuite, vous quittez le projet et revenez deux semaines plus tard. Lors de la réouverture du projet, les 3 premières pages ont changé. Désormais, la page d’accueil, les résultats de recherche et le passage en caisse figurent sur les 4 à 6 premières pages. Par défaut, les répartitions des canaux marketing apparaîtront toujours sous Page d’accueil, Résultats de recherche et le Passage en caisse, même si elles se trouvent maintenant dans les lignes 4 à 6. <br>En revanche, la **répartition par position** répartit toujours les 3 premiers éléments, quelle que soit leur nature. Pour revenir à l’exemple, lorsque vous rouvrez votre projet, les répartitions des canaux marketing sont liées aux 3 premières pages du tableau. Elles ne sont pas liées à Page d’accueil, Résultats de recherche et Passage en caisse, qui se trouvent désormais dans les lignes 4 à 6. |
| **[!UICONTROL Pourcentages]** | **Calculer les pourcentages par colonne** (par défaut) : les pourcentages visibles dans une colonne sont calculés en fonction du total de la colonne. <br>**Calcul des pourcentages par ligne** : les pourcentages des cellules sont calculés par ligne, et non pas par colonne, avec le total général comme dénominateur. Ce calcul s’avère utile pour les pourcentages de tendance. |
| **[!UICONTROL Totaux des colonnes]** | Ces paramètres sont uniquement disponibles pour les [lignes statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> L’option **Afficher comme somme des lignes actuelles** affiche la somme des lignes du tableau côté client, ce qui signifie que le total *ne dédupliquera pas* de mesures telles que les visites ou les personnes. <br> L’option **Afficher le total général** indique une somme côté serveur, ce qui signifie que le total dédupliquera les mesures. |

## Modification du nombre de lignes

Pour modifier le nombre de lignes affichées, procédez comme suit :

1. Cliquez sur le nombre en regard de **[!UICONTROL Lignes]** en haut de la première colonne du tableau.

   ![Tableau à structure libre présentant la liste déroulante pour le nombre de lignes affichées. L’option 400 lignes est sélectionnée.](assets/change-row-count.gif)

1. Dans la liste déroulante, sélectionnez le nombre de lignes à afficher dans le tableau.


## Menu contextuel

Les options de menu contextuel suivantes sont disponibles lors de la sélection de l’en-tête de dimension.

| Option | Description |
| --- | --- |
| **[!UICONTROL Copier la sélection dans le presse-papiers]** | Copiez la sélection de la visualisation dans le presse-papiers. |
| **[!UICONTROL Télécharger les éléments au format CSV (*nom de dimension*)]** | Téléchargez immédiatement les éléments de dimension (jusqu’à 50 000 au maximum) de la visualisation sur votre appareil local. Un maximum de 50 000 éléments de dimension pour la dimension sélectionnée. |
| **[!UICONTROL Télécharger la sélection au format CSV]** | Téléchargez immédiatement les éléments de dimension de la visualisation sur votre appareil local. |
| **[!UICONTROL Créer des liens hypertexte pour tous les éléments de dimension]** | Créez des liens hypertexte pour tous les éléments de dimension. Voir [Liens hypertexte pour les dimensions dans un tableau à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Modifier le lien hypertexte pour tous les éléments de dimension]** | Modifiez les liens hypertexte pour tous les éléments de dimension. Voir [Créer des liens hypertexte pour les dimensions dans un tableau à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Supprimer les liens hypertexte pour tous les éléments de dimension]** | Supprimez les liens hypertexte pour tous les éléments de dimension. Voir [Liens hypertexte pour les dimensions dans un tableau à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Supprimer]** | Supprime la dimension du tableau. |
| **[!UICONTROL Visualisation]** | Visualisez la dimension à l’aide de l’une des visualisations disponibles. |
| **[!UICONTROL Afficher uniquement les lignes sélectionnées]** | Affichez uniquement les éléments sélectionnés dans la visualisation. |
| **[!UICONTROL Créer une annotation à partir d’une sélection]** | Ouvrez les **[!UICONTROL Détails de l’annotation]** pour ajouter une annotation. |


Les options de menu contextuel supplémentaires suivantes sont disponibles lors de la sélection d’un ou de plusieurs éléments de dimension (première colonne) ou d’une ou de plusieurs cellules individuelles dans le tableau à structure libre.

| Option | Description |
| --- | --- |
| **[!UICONTROL Créer un lien hypertexte]** | Créez un lien hypertexte pour l’élément. Voir [Liens hypertexte pour les dimensions dans un tableau à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Modifier le lien hypertexte]** | Modifiez un lien hypertexte pour l’élément. Voir [Liens hypertexte pour les dimensions dans un tableau à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Supprimer le lien hypertexte]** | Supprimez un lien hypertexte pour l’élément. Voir [Liens hypertexte pour les dimensions dans un tableau à structure libre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Répartition]** | Ventilez l’élément de dimension. Faites votre choix dans la liste **[!UICONTROL Dimensions]**, **[!UICONTROL Mesures]**, **[!UICONTROL Segments]** ou **[!UICONTROL Périodes]**. Autre recherche d’un composant à l’aide de *Recherche*. |
| **[!UICONTROL Supprimer la sélection]** | Supprimez les lignes (éléments) sélectionnées. |
| **[!UICONTROL Sélection de tendances]** | Créez une visualisation sous forme de graphique linéaire de tendance pour la sélection. |
| **[!UICONTROL Afficher uniquement les lignes sélectionnées]** | Affichez uniquement les lignes sélectionnées dans la visualisation. |
| **[!UICONTROL Afficher toutes les lignes]** | Affichez toutes les lignes de la visualisation. |
| **[!UICONTROL Création d’un segment d’après une sélection]** | Ouvrez le **[!UICONTROL Créateur de segments]** pour créer un segment à partir de la sélection. |
| **[!UICONTROL Créer une audience à partir de la sélection]** | Ouvrez la boîte de dialogue **[!UICONTROL Créer une audience]** pour créer une audience à partir de la sélection. |

Les options de menu contextuel supplémentaires suivantes sont disponibles lors de la sélection d’un en-tête de colonne de mesure.

| Option | Description |
|---|---|
| **[!UICONTROL Créer une mesure à partir d’une sélection]** | Créez une mesure à partir de la mesure sélectionnée. La mesure peut être Moyenne, Média, Colonne max, Colonne min, Somme de la colonne. Vous pouvez également sélectionner Ouvrir dans le créateur de mesures calculées pour créer une mesure calculée. |
| **[!UICONTROL Ajouter une colonne de période]** | Ajoutez une colonne de période. Plusieurs options vous sont proposées, la période de calendrier du panneau déterminant la *période* : <li>**[!UICONTROL *Période* précédant cette période]**</li><li>**[!UICONTROL *Période* à cette période]**.</li><li>**[!UICONTROL Période personnalisée à cette période]**. Ouvre le **[!UICONTROL Créateur de périodes]** pour spécifier la période.</li>Voir [Comparaison de dates](/help/components/date-ranges/time-comparison.md) pour plus d’informations. |
| **[!UICONTROL Comparaison de périodes]** | Ajoute des colonnes de comparaison de périodes. Disponible uniquement lorsque la dimension n’est pas temporelle. Plusieurs options permettent de déterminer la *période* : <li>**[!UICONTROL *Période* précédant cette période]**</li><li>**[!UICONTROL Période personnalisée à cette période]**. Ouvre le **[!UICONTROL Créateur de périodes]** pour spécifier la période.</li>Voir [Comparaison de dates](/help/components/date-ranges/time-comparison.md) pour plus d’informations. |
| **[!UICONTROL Modifier les modèles d’attribution]** | Modifiez le modèle d’attribution de la colonne. |
| **[!UICONTROL Comparer le modèle d’attribution]** | Spécifiez un nouveau modèle d’attribution et comparez-le au modèle d’attribution de la colonne sélectionnée. Une nouvelle colonne est ajoutée avec les nouvelles mesures de modèle d’attribution. Une colonne Changement en pourcentage est également ajoutée à des fins de comparaison. |
| **[!UICONTROL Réinitialiser les largeurs de colonne]** | Rétablissez la largeur par défaut des colonnes. |
| **[!UICONTROL Créer une annotation à partir d’une sélection]** | Ouvrez les **[!UICONTROL Détails de l’annotation]** pour ajouter une annotation. |
| **[!UICONTROL Création d’un segment d’après une sélection]** | Ouvrez le **[!UICONTROL Créateur de segments]** pour créer un segment à partir de la sélection. |
| **[!UICONTROL Créer une audience à partir de la sélection]** | Ouvrez la boîte de dialogue **[!UICONTROL Créer une audience]** pour créer une audience à partir de la sélection. |

## Modifier la hauteur de ligne

Vous pouvez définir la densité d’affichage d’un projet sur **[!UICONTROL Compact]**, **[!UICONTROL Confortable]** et **[!UICONTROL Développé]**. [En savoir plus](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/view-density).