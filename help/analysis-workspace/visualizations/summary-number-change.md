---
description: valeur nulle
title: Synthèse des chiffres et synthèse des changements
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 92%

---


# Synthèse des chiffres et synthèse des changements

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

## Visualisation Synthèse des chiffres

* Sélectionne toutes les colonnes si aucune cellule n’est sélectionnée.
* Si une seule cellule est sélectionnée, son résumé s’affiche.
* Si plusieurs cellules sont sélectionnées, la première cellule sélectionnée s’affiche.
* Si la colonne est sélectionnée, la valeur de la première cellule de la colonne est affichée.

![](assets/summary-number.png)

## Visualisation Résumé des changements

* Si aucune cellule n’est sélectionnée, les valeurs de deux premières cellules de la colonne sont comparées.
* Si une seule cellule est sélectionnée, 0 s’affiche, car la valeur de la cellule est comparée à elle-même.
* Si deux cellules sont sélectionnées, la première cellule sélectionnée sert de numérateur, la deuxième de dénominateur.
* Si plus de deux cellules sont sélectionnées, seules les deux premières sont prises en compte pour la comparaison.
* Si une rangée de cellules est sélectionnée, la première et la dernière cellules de la rangée sont comparées.
* Si la colonne est sélectionnée, la première valeur est comparée à elle-même ; 0 s’affiche.
* Les couleurs verte et rouge du résumé des changements peuvent être contrôlées par :
   * [la polarité des événements personnalisés](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/success-events/success-event.html) ;
   * l’option [Tendance à la hausse affichée](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) d’une mesure calculée.

## Paramètres du résumé des changements {#section_2581AC0107634FB4990AB8347E5897AA}

Cliquez sur l’icône d’engrenage en regard de la visualisation pour configurer les paramètres du résumé :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Utilisez des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche les mesures utilisées. |
| Options de la synthèse des chiffres : Abréger la valeur | Vous pouvez choisir de 0 à 3 nombres de décimales pour les valeurs abrégées. |
| Options du résumé des changements : Afficher la modification du pourcentage | Affiche la modification, en pourcentage, entre les 2 nombres. |
| Options du résumé des changements : Afficher la différence brute | Affiche la différence brute entre 2 nombres. |
