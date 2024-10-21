---
title: Analyse de l'engagement
description: Comprendre l’étendue et la profondeur de l’engagement des fonctionnalités.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 5%

---

# Analyse [!UICONTROL Engagement]

L’analyse ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** permet de déterminer la fréquence d’utilisation d’une fonctionnalité par rapport au nombre de personnes qui l’utilisent. Cette analyse fonctionne mieux lorsque vous comparez plusieurs fonctions les unes aux autres. Cela contribue à alimenter les décisions d’investissement en comprenant vos caractéristiques fondamentales, votre puissance, ponctuelles et douteuses.

Les fonctionnalités qui se trouvent en haut de cette visualisation indiquent qu’elles sont fréquemment utilisées par les utilisateurs actifs. Les fonctionnalités qui se situent à droite de cette visualisation indiquent qu’elles sont largement adoptées par vos utilisateurs actifs. Le nombre médian de fois où une fonction est utilisée divise le graphique horizontalement. Le pourcentage médian des utilisateurs actifs divise le graphique verticalement. Les médias sont calculés en fonction des événements sélectionnés dans la requête, et non de toutes les données.

* Les fonctionnalités situées dans le coin supérieur gauche de la matrice sont vos fonctions **power** ; elles ne sont pas largement adoptées, mais sont fréquemment utilisées par les utilisateurs engagés.
* Les fonctionnalités situées dans le coin supérieur droit de la matrice sont vos fonctions **à fort impact** ; elles sont largement adoptées et fréquemment utilisées.
* Les fonctionnalités situées dans la partie inférieure gauche de la matrice sont vos fonctions **à faible impact** ; elles ne sont pas largement adoptées ou fréquemment utilisées.
* Les fonctionnalités situées dans le coin inférieur droit de la matrice sont vos fonctions **ponctuelles** ; elles sont largement adoptées, mais ne sont pas fréquemment utilisées.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)


## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Engagement par fonction** : vous pouvez établir une corrélation directe entre l’engagement et l’adoption d’une fonction spécifique. Comprendre les fonctionnalités les plus utilisées peut aider à déterminer celles dans lesquelles investir davantage.
* **Discover features under used** : les fonctionnalités avec des utilisateurs actifs faibles mais avec une utilisation élevée peuvent indiquer une fonctionnalité puissante, qui est précieuse mais qui n’est pas découverte ni utilisée par la population élargie. Envisagez d’améliorer la visibilité de ces fonctionnalités afin que plus d’utilisateurs les exploitent.
* **Améliorer les fonctionnalités populaires** : les fonctionnalités avec des utilisateurs actifs élevés mais avec une faible utilisation peuvent indiquer qu’une fonctionnalité est très demandée mais sous-utilisée. Ces situations offrent l’occasion d’en savoir plus à vos utilisateurs sur les améliorations qui rendraient la fonctionnalité plus précieuse pour eux.
* **Créer des segments basés sur des fonctionnalités** : visualisez l’utilisation des fonctionnalités de cette manière pour générer des opportunités d’analyse supplémentaires. Créez un segment pour n’importe quel point du graphique afin d’approfondir l’analyse de ce groupe d’utilisateurs et d’appliquer ces leçons à votre stratégie d’engagement des utilisateurs.
* **Test A/B de l’adoption des fonctionnalités** : comparez l’utilisation de plusieurs fonctionnalités dans différents groupes d’utilisateurs. Ajoutez des segments dans le rail de requêtes afin de déterminer la différence d’utilisation des fonctionnalités entre les groupes d’utilisateurs clés.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements]** : événements que vous souhaitez mesurer. Chaque événement représente l’utilisation d’une fonction donnée et s’affiche comme un point dans la matrice. Vous pouvez inclure jusqu’à dix événements. La médiane est calculée en fonction des événements sélectionnés.
* **[!UICONTROL Compté comme]** : le long de l’axe X, vous pouvez mesurer le pourcentage moyen d’utilisateurs actifs par jour, par semaine, par mois ou par trimestre. L’axe des ordonnées ajuste automatiquement la durée moyenne par utilisateur en fonction de la sélection de l’axe des abscisses.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de points tracés dans le graphique et de lignes dans le tableau. Vous pouvez inclure jusqu’à trois segments.

>[!TIP]
>
>Si plusieurs événements représentent l’utilisation d’une seule fonction, vous pouvez dériver un nouvel événement qui représente la fonction dans les vues de données.

### Paramètres du graphique

L’analyse [!UICONTROL Engagement] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu situé au-dessus du graphique :

* **[!UICONTROL Médians]** : déterminez où s’affichent les lignes médianes et comment les points tracés sont associés à ces supports.
   * **[!UICONTROL Standard]** : affichez la valeur absolue de l’utilisation et de l’engagement.
   * **[!UICONTROL Normalisé]** : affiche les changements relatifs de chaque médiane.
* **[!UICONTROL Superposition des principaux événements]** : comparez les performances de vos événements aux 20 premiers événements, en fonction de la récence et de la pertinence de l’entreprise et de l’utilisateur (le même algorithme appliqué au sélecteur d’événements dans le rail de requête).

### Comparaison de temps

{{apply-time-comparison}}

### Période

La période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Cette analyse traite [!UICONTROL Intervalle] de la même manière que [!UICONTROL Compté comme] dans le rail de requête. Les utilisateurs actifs par heure ne sont pas pris en charge.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les plages personnalisées précédemment enregistrées sont disponibles à des fins pratiques. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une plage de dates fixe.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
