---
title: Qu’est-ce que l’analyse des cohortes ?
description: En savoir plus sur l’analyse des cohortes dans Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 64%

---

# Qu’est-ce que l’[!UICONTROL analyse des cohortes] ?

Une *`cohort`* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. L’[!UICONTROL analyse des cohortes] s’avère utile, par exemple, pour savoir de quelle façon une cohorte réagit par rapport à une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Vous trouverez des explications sur l’[!UICONTROL analyse des cohortes] sur le Web, tel le cours [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis) (en anglais).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et filtres spécifiques), puis partager le rapport avec les personnes de votre choix. Consultez la section [Traitement et partage](/help/analysis-workspace/curate-share/curate.md).

Exemples d’utilisation de l’[!UICONTROL analyse des cohortes] :

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Reconnaissez quand terminer un essai ou une offre pour en optimiser la valeur.
* Trouvez des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.

L’[!UICONTROL analyse des cohortes] est disponible pour tous les clients Customer Journey Analytics avec des droits d’accès à [!UICONTROL Analysis Workspace].

[Tutoriel vidéo sur les analyses des cohortes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=fr) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Analyse des cohortes] ne prend pas en charge les mesures non filtrables (y compris les mesures calculées), les mesures non entières (telles que Recettes) ou les occurrences. Seules les mesures pouvant être utilisées dans les filtres peuvent être utilisées dans [!UICONTROL Analyse des cohortes], et elles ne peuvent être incrémentées que 1 à la fois.

## Capacités de l’analyse des cohortes

Les capacités suivantes vous permettent d’exercer un contrôle précis sur les cohortes que vous créez :

### Tableau de [!UICONTROL rétention]

A [!UICONTROL Rétention] rapport de cohorte sur les personnes qui reviennent sur votre site : chaque cellule indique le nombre brut et le pourcentage de personnes dans la cohorte qui ont effectué l’action durant cette période. Vous pouvez inclure jusqu’à 3 mesures et 10 filtres.

![Rapport de cohorte sur les conversions indiquant les unités et le pourcentage de personnes dans la cohorte.](assets/retention-report.png)

### Tableau de [!UICONTROL perte de clientèle]

A [!UICONTROL Churn] cohorte est l’inverse d’un tableau de rétention. Elle indique les personnes qui ont abandonné ou n’ont jamais rempli les critères de retour de votre cohorte au fil du temps. Vous pouvez inclure jusqu’à 3 mesures et 10 filtres.

![Tableau de perte de clientèle présentant les unités et le pourcentage de personnes qui ne remplissaient pas les critères de retour d’une cohorte.](assets/churn-report.png)

### [!UICONTROL Calcul variable]

Permet de calculer la rétention ou la perte de clientèle en fonction de la colonne précédente, et non de la colonne Inclus.

![Rapport de rétention des cohortes présentant les calculs basés sur une colonne de données précédente.](assets/cohort-rolling-calculation.png)

### Tableau de [!UICONTROL latence]

Mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. Il s’agit d’un excellent outil pré-/post-analyse. La colonne **[!UICONTROL Inclus]** se trouve au centre du tableau, tandis que les périodes avant et après l’événement d’inclusion sont affichées des deux côtés.

![Rapport de cohortes montrant le temps écoulé avant et après un événement.](assets/cohort-latency.png)

### Cohorte de [!UICONTROL dimension personnalisée]

Créez des cohortes sur la base d’une dimension sélectionnée, et non des cohortes en fonction du temps, qui sont les cohortes par défaut. Utilisez des dimensions telles que le [!UICONTROL canal marketing], la [!UICONTROL campagne], le [!UICONTROL produit], la [!UICONTROL page], la [!UICONTROL région] ou toute autre dimension dans Customer Journey Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions.

![Rapport de cohortes présentant un rapport personnalisé avec des dimensions sélectionnées et non la cohorte temporelle par défaut.](assets/cohort-customizable-cohort-row.png)

Pour obtenir des instructions sur la configuration et l’exécution d’un rapport de cohorte, accédez à [Configuration d’un rapport d’analyse des cohortes](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
