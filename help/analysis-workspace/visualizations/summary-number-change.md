---
description: Utilisez les visualisations Synthèse des chiffres et Synthèse des changements pour afficher des points de données importants dans un projet.
title: Synthèse des chiffres et synthèse des changements
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 9733d6471e6f1c886fd27b702654349d6760870c
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 100%

---


# Synthèse des chiffres et synthèse des changements

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

## Visualisation Synthèse des chiffres {#summary-number}

Utilisez la visualisation Synthèse des chiffres pour mettre en évidence un grand nombre d’éléments importants dans un projet. Cette visualisation fonctionne comme suit :

* Sélectionne toutes les colonnes si aucune cellule n’est sélectionnée.
* Si une seule cellule est sélectionnée, son résumé s’affiche.
* Si plusieurs cellules sont sélectionnées, la première cellule sélectionnée s’affiche.
* Si la colonne est sélectionnée, la valeur de la première cellule de la colonne est affichée.

![Numéro de résumé](assets/summary-number.png)

Cliquez sur l’engrenage **Paramètres de visualisation** dans le coin supérieur droit pour configurer les paramètres de Synthèse des chiffres :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichent des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Abréger la valeur | Abrège les valeurs et affiche jusqu’à 3 chiffres après la virgule. |
| Résumer la valeur par | Affiche le maximum, le minimum, la moyenne, la médiane ou la somme pour une sélection de données. |

## Visualisation Résumé des changements {#summary-change}

Utilisez la visualisation Synthèse des changements pour afficher le delta (changement) entre deux chiffres. La couleur verte et la couleur rouge de la Synthèse des changements peuvent être contrôlées par [polarité d’événement personnalisé](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/success-events/success-event.html) ou par l’option [Tendance à la hausse affichée](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) d’une mesure calculée.

Cette visualisation fonctionne comme suit :

* Si aucune cellule n’est sélectionnée, les valeurs de deux premières cellules de la colonne sont comparées.
* Si une seule cellule est sélectionnée, 0 s’affiche, car la valeur de la cellule est comparée à elle-même.
* Si deux cellules sont sélectionnées, la première cellule sélectionnée sert de numérateur, la deuxième de dénominateur.
* Si plus de deux cellules sont sélectionnées, seules les deux premières sont prises en compte pour la comparaison.
* Si une rangée de cellules est sélectionnée, la première et la dernière cellules de la rangée sont comparées.
* Si la colonne est sélectionnée, la première valeur est comparée à elle-même ; 0 s’affiche.

![Résumé des changements](assets/summary-change.png)

Cliquez sur l’engrenage **Paramètres de visualisation** dans le coin supérieur droit pour configurer les paramètres de Synthèse des changements :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichent des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Afficher le pourcentage de changement | Affiche le pourcentage de changement entre les 2 chiffres. |
| Afficher la différence brute | Affiche la différence brute entre 2 nombres. Vous pouvez également abréger des valeurs et afficher jusqu’à 3 chiffres après la virgule avec cette option. |
