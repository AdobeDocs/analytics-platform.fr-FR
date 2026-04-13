---
title: Analyse de l’engagement
description: Prenez conscience de l’étendue et de la profondeur de l’engagement des fonctionnalités.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 98%

---

# Analyse de l’[!UICONTROL engagement] {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Engagement"
>abstract="Prenez conscience de l’étendue et de la profondeur de l’engagement des fonctionnalités."

<!-- markdownlint-enable MD034 -->


L’analyse ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** fournit des informations sur la fréquence d’utilisation d’une fonctionnalité par rapport au nombre de personnes qui l’utilisent. Cette analyse fonctionne mieux lorsque vous comparez plusieurs fonctionnalités les unes aux autres. Prenez vos décisions d’investissement en comprenant quelles sont vos fonctionnalités principales, prédominantes, ponctuelles et discutables.

Les fonctionnalités qui s’affichent en haut de cette visualisation indiquent qu’elles sont fréquemment utilisées par les utilisateurs et utilisatrices engagés. Les fonctionnalités qui se trouvent à droite de cette visualisation indiquent qu’elles sont largement adoptées par vos utilisateurs et utilisatrices actifs. Le nombre médian de fois où une fonctionnalité est utilisée divise le graphique horizontalement. Le pourcentage médian d’utilisateurs et utilisatrices actifs divise le graphique verticalement. Les médianes sont calculées en fonction des événements sélectionnés dans la requête, et non de toutes les données.

* Les fonctionnalités du coin supérieur gauche de la matrice sont vos fonctionnalités **prédominantes** ; elles ne sont pas largement adoptées, mais sont fréquemment utilisées par les utilisateurs et utilisatrices engagés.
* Les fonctionnalités en haut à droite de la matrice sont vos fonctionnalités **à fort impact** ; elles sont largement adoptées et fréquemment utilisées.
* Les fonctionnalités situées dans le coin inférieur gauche de la matrice sont vos fonctionnalités **à faible impact** ; elles ne sont pas largement adoptées ni fréquemment utilisées.
* Les fonctions en bas à droite de la matrice sont vos fonctions **ponctuelles** ; elles sont largement adoptées, mais ne sont pas fréquemment utilisées.

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyse de l’engagement](https://video.tv.adobe.com/v/3447469?captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Engagement par fonctionnalité** : vous pouvez établir une corrélation directe entre l’engagement et l’adoption d’une fonctionnalité spécifique. Comprendre les fonctionnalités les plus utilisées peut aider à déterminer les fonctionnalités dans lesquelles investir davantage.
* **Découvrir les fonctionnalités sous-utilisées** : les fonctionnalités avec un faible nombre d’utilisateurs et utilisatrices actifs mais une utilisation élevée peuvent indiquer une fonctionnalité prédominante, qui a de la valeur, mais n’est pas découverte ou utilisée par la population plus large. Envisagez d’améliorer la capacité de découverte de ces fonctionnalités afin que plus d’utilisateurs et d’utilisatrices les exploitent.
* **Améliorer les fonctionnalités populaires** : les fonctionnalités avec un nombre élevé d’utilisateurs et utilisatrices actifs mais une faible utilisation peuvent indiquer qu’une fonctionnalité est très demandée, mais sous-utilisée. Ces situations présentent des opportunités pour en savoir plus de vos utilisateurs et utilisatrices sur les améliorations qui rendraient la fonctionnalité plus utile pour eux.
* **Créer des segments basés sur des fonctionnalités** : affichez l’utilisation des fonctionnalités de cette manière pour demander des opportunités d’analyse supplémentaires. Créez un segment pour tout point du graphique afin d’explorer plus en détail ce groupe d’utilisateurs et utilisatrices et d’appliquer ces enseignements à votre stratégie d’engagement client.
* **Tests A/B d’adoption des fonctionnalités** : comparez l’utilisation de plusieurs fonctionnalités sur différents groupes d’utilisateurs et utilisatrices. Ajoutez des segments dans le rail de requête pour déterminer la différence d’utilisation des fonctionnalités entre les groupes d’utilisateurs et utilisatrices clés.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Événements]** : événements que vous souhaitez mesurer. Chaque événement représente l’utilisation d’une fonctionnalité donnée et s’affiche sous la forme d’un point dans la matrice. Vous pouvez inclure jusqu’à dix événements. La médiane est calculée en fonction des événements sélectionnés.
* **[!UICONTROL Comptabilisé comme]** : le long de l’axe X, vous pouvez mesurer le pourcentage moyen d’utilisateurs et utiliatrices actifs par jour, par semaine, par mois ou par trimestre. L’axe Y ajuste automatiquement les temps moyens par personne en fonction de la sélection de l’axe X.
* **[!UICONTROL Segments]** : segments que vous souhaitez mesurer. Chaque segment sélectionné double le nombre de points du graphique et de lignes du tableau. Vous pouvez inclure jusqu’à trois segments.

>[!TIP]
>
>Si plusieurs événements représentent l’utilisation d’une seule fonctionnalité, vous pouvez dériver un nouvel événement qui représente la fonctionnalité dans les vues de données.

### Paramètres du graphique

L’analyse [!UICONTROL Engagement] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Médianes]** : Déterminez où les lignes médianes sont affichées et comment les points tracés se rapportent à ces médianes.
   * **[!UICONTROL Standard]** : montrez la valeur absolue de l’utilisation et de l’engagement.
   * **[!UICONTROL Normalisé]** : montrez les modifications relatives à partir de chaque médiane.
* **[!UICONTROL Principaux recouvrements d’événements]** : comparez vos événements à ceux des 20 principaux événements, en fonction de la récence et de la pertinence de l’entreprise et de la personne (le même algorithme appliqué au sélecteur d’événement dans le rail de requête).

### Comparaison de temps

{{apply-time-comparison}}

### Période

Période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Cette analyse traite [!UICONTROL Intervalle] de la même manière que [!UICONTROL Comptabilisé comme] dans le rail de requête. Les utilisateurs et utilisatrices actifs par heure ne sont pas pris en charge.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
