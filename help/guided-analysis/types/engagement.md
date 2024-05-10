---
title: Vue Engagement
description: Comprendre l’ampleur et la largeur de l’engagement des fonctionnalités.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# [!UICONTROL Engagement] view

La variable **[!UICONTROL Engagement]** La vue fournit des informations sur la fréquence d’utilisation d’une fonctionnalité par rapport au nombre de personnes qui l’utilisent. Cette analyse fonctionne mieux lorsque vous comparez plusieurs fonctions les unes aux autres.

Les fonctionnalités qui se trouvent en haut de cette visualisation indiquent qu’elle est fréquemment visitée par les personnes qui l’utilisent. Les fonctionnalités qui se trouvent à droite de cette visualisation indiquent que la plus grande proportion d’utilisateurs qui utilisent la fonctionnalité. Le nombre médian de fois où une fonction est utilisée divise le graphique horizontalement. Le pourcentage médian des utilisateurs actifs par jour divise le graphique verticalement.

* Les fonctionnalités situées dans le coin supérieur gauche de la matrice indiquent qu’une fonction n’est pas largement adoptée. Cependant, parmi les individus qui l’utilisent, ils l’utilisent fréquemment.
* Les fonctionnalités situées dans le coin supérieur droit de la matrice signifient qu’une fonction est à la fois largement adoptée et fréquemment utilisée.
* Les fonctions situées dans le coin inférieur droit de la matrice signifient qu’une fonction est largement adoptée, mais pas fréquemment utilisée.
* Les fonctions situées dans le coin inférieur gauche de la matrice indiquent qu’une fonction n’est pas largement adoptée et n’est pas fréquemment utilisée.

## Cas d’utilisation

Les cas d’utilisation de ce type de vue sont les suivants :

* **Engagement par fonction**: vous pouvez établir une corrélation directe entre l’engagement et l’adoption d’une fonction spécifique. Comprendre les fonctionnalités qui sont les plus utilisées peut aider à déterminer celles dont l’amélioration est prioritaire.
* **Découvrez les fonctionnalités sous-utilisées**: les fonctionnalités avec des utilisateurs actifs quotidiens faibles mais une utilisation élevée peuvent indiquer une fonctionnalité masquée mais précieuse. Envisagez d’exposer ces types de fonctionnalités à un plus grand nombre d’utilisateurs.
* **Améliorations des fonctionnalités populaires**: les fonctionnalités avec un nombre élevé d’utilisateurs actifs mais une utilisation faible peuvent indiquer qu’une fonctionnalité est très demandée, mais sous-utilisée. Envisagez d’investir dans l’amélioration de ces fonctionnalités afin qu’elles soient utilisées plus souvent.
* **Création de segments basés sur des fonctionnalités**: analyser la fréquence d’utilisation d’une fonction par rapport au nombre d’utilisateurs qui l’adoptent peut aider à déterminer les types d’utilisateurs qui adoptent une fonction donnée. Vous pouvez créer des segments en fonction des utilisateurs qui utilisent une fonction de manière occasionnelle ou en fonction des utilisateurs qui l’utilisent fréquemment.
* **Test A/B de l’adoption des fonctionnalités**: comparez l’utilisation de plusieurs fonctionnalités à l’aide de segments. Ajoutez les segments de chaque cohorte dans le rail de requête afin de déterminer facilement la différence d’utilisation des fonctionnalités.

## Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements]** : événements que vous souhaitez mesurer. Ces événements représentent généralement l’utilisation d’une fonction donnée. Chaque sélection est représentée sous la forme d’un point dans la matrice. Vous pouvez inclure jusqu’à dix événements.
* **[!UICONTROL Compté comme]**: déterminez les détails du nombre d’utilisateurs sur l’axe X. Vous pouvez mesurer le pourcentage moyen d’utilisateurs actifs quotidiens, hebdomadaires, mensuels ou trimestriels. L’axe des ordonnées ajuste automatiquement la durée moyenne par utilisateur en fonction de la sélection de l’axe des abscisses.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de points tracés dans le graphique et de lignes dans le tableau. Vous pouvez inclure jusqu’à trois segments.

## Paramètres du graphique

La variable [!UICONTROL Engagement] La vue propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Médias]**: déterminez l’emplacement d’affichage des lignes médianes et la manière dont les points tracés sont associés à ces supports.
   * **[!UICONTROL Standard]**: indique la valeur absolue de l’utilisation et de l’engagement.
   * **[!UICONTROL Normalisé]**: affiche les modifications relatives de chaque médiane.
* **[!UICONTROL Superposition des principaux événements]**: comparez les performances de vos événements aux événements les plus courants.

## Comparaison de temps

{{apply-time-comparison}}

## Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]**: granularité de date selon laquelle vous souhaitez afficher les données de tendance. Ce type de vue traite [!UICONTROL Intervalle] de même que [!UICONTROL Compté comme] dans le rail de requête. Les utilisateurs actifs par heure ne sont pas pris en charge.
* **[!UICONTROL Date]**: date de début et date de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.
