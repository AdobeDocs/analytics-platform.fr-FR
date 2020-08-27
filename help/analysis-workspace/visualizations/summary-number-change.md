---
description: Utilisez les visualisations Synthèse des chiffres et Modifier pour afficher des points de données importants dans un projet.
title: Synthèse des chiffres et synthèse des changements
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 158c9da54f7d5dcdd0cca6223b5d4833df53abb7
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 52%

---


# Synthèse des chiffres et synthèse des changements

## Visualisation Synthèse des chiffres {#summary-number}

Utilisez la visualisation Synthèse des chiffres pour mettre en évidence un grand nombre d’éléments importants dans un projet. Cette visualisation se comporte comme suit :

* Sélectionne toutes les colonnes si aucune cellule n’est sélectionnée.
* Si une seule cellule est sélectionnée, son résumé s’affiche.
* Si plusieurs cellules sont sélectionnées, la première cellule sélectionnée s’affiche.
* Si la colonne est sélectionnée, la valeur de la première cellule de la colonne est affichée.

Cliquez sur le bouton **Paramètres de visualisation** accédez au coin supérieur droit pour configurer les paramètres Synthèse des chiffres :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichez des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Abréger la valeur | Choisissez d’abréger les valeurs et d’afficher jusqu’à 3 décimales. |
| Résumer la valeur par | Choisissez d’afficher le maximum, le minimum, la moyenne, la médiane ou la somme pour une sélection de données. |

## Visualisation Résumé des changements {#summary-change}

Utilisez la visualisation Synthèse des changements pour afficher le delta (changement) entre deux nombres. La couleur verte et rouge du résumé du changement peut être contrôlée par le biais de [polarité de événement personnalisée](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/success-events/success-event.html) ou une mesure calculée [Afficher la tendance à la hausse en tant que](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) .

Cette visualisation se comporte comme suit :

* Si aucune cellule n’est sélectionnée, les valeurs de deux premières cellules de la colonne sont comparées.
* Si une seule cellule est sélectionnée, 0 s’affiche, car la valeur de la cellule est comparée à elle-même.
* Si deux cellules sont sélectionnées, la première cellule sélectionnée sert de numérateur, la deuxième de dénominateur.
* Si plus de deux cellules sont sélectionnées, seules les deux premières sont prises en compte pour la comparaison.
* Si une rangée de cellules est sélectionnée, la première et la dernière cellules de la rangée sont comparées.
* Si la colonne est sélectionnée, la première valeur est comparée à elle-même ; 0 s’affiche.

Cliquez sur le bouton **Paramètres de visualisation** accédez au coin supérieur droit pour configurer les paramètres Résumé des modifications :

| Paramètre | Définition |
|--- |--- |
| Pourcentages | Affichez des pourcentages plutôt que des chiffres bruts. |
| Légende visible | Affiche des informations sur la mesure affichée. |
| Afficher la modification en pourcentage | Affiche la variation en pourcentage entre les 2 chiffres. |
| Afficher la différence brute | Affiche la différence brute entre 2 nombres. Vous pouvez également abréger des valeurs et afficher jusqu’à 3 décimales avec cette option. |
