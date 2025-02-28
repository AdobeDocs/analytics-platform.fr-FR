---
description: Découvrez comment spécifier les points de contact pour créer une séquence d’abandons multidimensionnelle.
title: Configuration d’une visualisation Abandons
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 38%

---

# Configuration d’une visualisation Abandons {#configure-fallout-visualization}


Vous pouvez spécifier les points de contact d’après lesquels créer une séquence d’abandons multidimensionnelle. En général, un point de contact est une page sur votre site. Ils ne se limitent toutefois pas à cela. Par exemple, vous pouvez ajouter des événements, tels que des unités, ainsi que des personnes uniques et des visites récurrentes. Vous pouvez aussi ajouter des dimensions, telles qu’une catégorie, un type de navigateur ou un terme de recherche interne.

Il est possible en outre d’ajouter des filtres dans un point de contact. Par exemple, vous pouvez comparer des filtres, tels que les utilisateurs d’iOS et d’Android™. Faites glisser les filtres souhaités en haut de l’abandon pour ajouter des informations sur ces filtres au rapport sur les abandons. Si vous souhaitez n’afficher que ces filtres, vous pouvez supprimer la ligne de base Toutes les visites.

Le nombre d’étapes que vous pouvez ajouter ou le nombre de dimensions utilisées ne sont pas limités.

Vous pouvez effectuer le cheminement sur des dimensions, des mesures et des filtres. Par exemple, supposons que quelqu&#39;un regarde des chaussures, une chemise sur une page, et que sur la page suivante, il regarde une chemise, des chaussettes. Le prochain rapport de flux de produits généré à partir des chaussures portera sur chemise et chaussettes, SAUF chemise.

## Utilisation

1. Ajoutez une visualisation ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Abandon]**. Voir [Ajouter une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Faites glisser une page, par exemple Accueil, de la dimension Page vers le menu déroulant *Ajouter un point de contact*.

   ![Page d’accueil de la dimension Page d’accueil déplacée vers le champ Ajouter un point de contact.](assets/fallout-drag.png)

   Pointez sur un point de contact pour afficher l’abandon et d’autres informations sur ce niveau, telles que le nom du point de contact et le nombre de personnes à ce stade. et afficher le taux de succès de ce point de contact (et comparer le taux de succès à d’autres points de contact).

   Les nombres encadrés dans la partie grise de la barre correspondent aux abandons entre les points de contact (et non à l’ensemble des abandons à ce point). Le **[!UICONTROL point de contact %]** indique la réussite de l’abandon de l’étape précédente à l’étape actuelle dans le rapport sur les abandons.

   Vous pouvez également ajouter une seule page au rapport des abandons, plutôt que la dimension entière. Cliquez sur la flèche droite ![ChevronRight](/help/assets/icons/ChevronRight.svg) sur la dimension de page pour sélectionner une page spécifique à ajouter au rapport sur les abandons.

1. Continuez à ajouter des points de contact jusqu’à ce que votre séquence soit complète.

   Vous pouvez **combiner plusieurs points de contact** en faisant glisser un ou plusieurs composants supplémentaires sur un point de contact.

   >[!NOTE]
   >
   >Plusieurs filtres sont reliés par l’opérateur AND, mais plusieurs éléments, tels que des éléments de dimension et des mesures, sont reliés par l’opérateur OR.

   ![Page:CamerRoll ou Page : points de contact de l’appareil photo mis en surbrillance.](assets/fallout-or.png)

1. Vous pouvez également **contraindre des points de contact individuels à l’événement suivant** (par opposition à *éventuellement*) dans le chemin. Sous chaque point de contact se trouve un sélecteur avec les options **[!UICONTROL Chemin éventuel]** et **[!UICONTROL Événement suivant]**, comme illustré ici :

   ![Vue Toutes les visites présentant l’option Chemin d’accès final mise en surbrillance. ](assets/fallout-nexthit.png)

   | Option | Description |
   |---|---|
   | **[!UICONTROL Chemin d’accès éventuel]** (par défaut) | On compte les personnes qui *éventuellement* arriveront à la page suivante du parcours, mais pas nécessairement à l’événement suivant. |
   | **[!UICONTROL Événement suivant]** | Sont comptés ceux qui arriveront à la page suivante du chemin lors du prochain événement. |


## Paramètres {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Conteneur d’abandons"
>abstract="Sélectionnez un conteneur pour analyser le cheminement. Cette sélection vous permet de comprendre l’engagement et de contraindre l’analyse au conteneur sélectionné."

Dans le cadre de la visualisation, des paramètres spécifiques sont disponibles.

| Conteneur d’abandons | Description |
|--- |--- |
| **[!UICONTROL Session]** ou **[!UICONTROL Personne]** | Basculez entre [!UICONTROL Session] et [!UICONTROL Personne] pour analyser le cheminement de la personne. La valeur par défaut est [!UICONTROL Personne]. Ces paramètres permettent de comprendre l’engagement des personnes au niveau des personnes (sur les sessions) ou de contraindre l’analyse à une seule session. |


## Menu contextuel

Dans le cadre de la visualisation, des options de menu contextuel spécifiques sont disponibles.

![Options d’abandon](assets/fallout-options.png)

| Option | Description |
|--- |--- |
| **[!UICONTROL Point de contact de tendance]** | Consultez dans un graphique linéaire les données sur les tendances d’un point de contact, avec quelques données de détection des anomalies prédéfinies. |
| **[!UICONTROL Point de contact de tendance (%)]** | Calcule la tendance du pourcentage total d’abandons. |
| **[!UICONTROL Tendance de tous les points de contact (%)]** | Ajoute une tendance à tous les pourcentages de point de contact dans l’abandon (à l’exception de **[!UICONTROL Toutes les personnes]**, si elle est incluse), sur le même graphique. |
| **[!UICONTROL Répartir les abandons à ce point de contact]** | Affichez ce que les personnes ont fait entre deux points de contact (ce point de contact et le point de contact suivant) si elles ont continué vers le point de contact suivant. Un tableau à structure libre présentant les dimensions est ainsi créé. Vous pouvez y remplacer les dimensions et d’autres éléments qui le composent. |
| **[!UICONTROL Répartir les abandons à ce point de contact]** | Vérifiez quelles personnes qui n’ont pas franchi l’entonnoir l’ont fait immédiatement après l’étape sélectionnée. |
| **[!UICONTROL Créer un filtre à partir du point de contact]** | Créez un nouveau filtre à partir du point de contact sélectionné. |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

