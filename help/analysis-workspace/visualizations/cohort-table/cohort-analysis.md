---
title: Tableau de cohortes - Aperçu
description: Découvrez comment utiliser un tableau de cohortes pour l’analyse des cohortes dans Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 25%

---

# Tableau de cohortes - Aperçu {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_button"
>title="Tableau de cohortes"
>abstract="Créez une visualisation de cohortes pour regrouper les utilisateurs en fonction de la fin d’un événement et analysez l’engagement et la perte de clientèle au fil du temps."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_panel"
>title="Tableau de cohortes"
>abstract="Regroupez les utilisateurs en fonction de la fin d’un événement, puis analysez leur engagement et leur perte de clientèle au fil du temps.<br/><br/>**Paramètres **<br/>**Critères d’inclusion** : composants utilisés pour définir vos cohortes initiales de visiteurs.<br/>**Critères de retour** : composants utilisés pour déterminer si un visiteur est revenu."

<!-- markdownlint-enable MD034 -->


Une *cohorte* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifiée. Une visualisation ![ ](/help/assets/icons/TextNumbered.svg) **[!UICONTROL {tableau de cohortes]** est utile, par exemple, pour savoir comment une cohorte interagit avec une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Vous trouverez des explications sur l’[!UICONTROL analyse des cohortes] sur le Web, tel le cours [Cohort Analysis 101](https://fr.wikipedia.org/wiki/Cohort_analysis) (en anglais).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et filtres spécifiques), puis partager le rapport avec les personnes de votre choix. Consultez la section [Traitement et partage](/help/analysis-workspace/curate-share/curate.md).

Exemples de ce que vous pouvez faire avec une [!UICONTROL table de cohortes] :

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Reconnaissez quand terminer un essai ou une offre pour en optimiser la valeur.
* Trouvez des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.

[!UICONTROL La table des cohortes] est disponible pour tous les clients Customer Journey Analytics ayant des droits d’accès à [!UICONTROL Analysis Workspace].

+++ Affichez une démonstration vidéo du tableau de cohortes.

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>[!UICONTROL L’analyse des cohortes] ne prend pas en charge les mesures non filtrables (y compris les mesures calculées), les mesures non entières (telles que les recettes) ou les occurrences. Seules les mesures pouvant être utilisées dans les filtres peuvent être utilisées dans l’ [!UICONTROL analyse des cohortes], et elles ne peuvent être incrémentées que 1 à la fois.

## Fonctionnalités des tableaux de cohortes

Les capacités suivantes vous permettent d’exercer un contrôle précis sur les cohortes que vous créez :

### Table [!UICONTROL Rétention]

Une table de cohorte de [!UICONTROL rétention] renvoie des personnes : chaque cellule indique le nombre brut et le pourcentage de personnes dans la cohorte qui ont effectué l’action durant cette période. Vous pouvez inclure jusqu’à 3 mesures et 10 filtres.

![Rapport de cohorte sur la conversion montrant les unités et le pourcentage de personnes dans la cohorte.](assets/retention-report.png)

### Table [!UICONTROL Churn]

Une table de cohortes [!UICONTROL perte de clientèle] est l’inverse d’une table de rétention et affiche les personnes qui ont abandonné ou n’ont jamais rempli les critères de retour de votre cohorte au fil du temps. Vous pouvez inclure jusqu’à 3 mesures et 10 filtres.

![Tableau de perte de clientèle présentant les unités et le pourcentage de personnes qui ne répondent pas aux critères de retour d’une cohorte.](assets/churn-report.png)

### [!UICONTROL Calcul variable]

Vous pouvez calculer la rétention ou la perte de clientèle en fonction de la colonne précédente, et non de la colonne incluse, appelée calcul variable.

![ Rapport de rétention des cohortes montrant des calculs basés sur une colonne précédente de données.](assets/retention-report-rolling.png)

### Table [!UICONTROL Latence]

Un tableau de latence mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. La mesure de la latence est un excellent outil d’analyse avant et après. La colonne **[!UICONTROL Inclus]** se trouve au centre du tableau, tandis que les périodes avant et après l’événement d’inclusion sont affichées des deux côtés.

![Rapport de cohorte montrant le temps écoulé avant et après un événement.](assets/retention-report-latency.png)

### Cohorte [!UICONTROL Dimension personnalisée]

Vous pouvez créer des cohortes en fonction d’une dimension sélectionnée, et non des cohortes en fonction du temps (qui sont les cohortes par défaut). Utilisez des dimensions telles que [!UICONTROL Ville géo], [!UICONTROL Canal marketing], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL région] ou toute autre dimension pour afficher l’évolution de la rétention. En fonction des différentes valeurs de ces dimensions.

![Rapport de cohorte présentant un rapport personnalisé avec des dimensions sélectionnées et non la cohorte temporelle par défaut.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurer une table de cohortes](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

