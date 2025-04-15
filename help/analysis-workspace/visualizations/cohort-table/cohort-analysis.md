---
title: Vue d’ensemble de la table de cohorte
description: Découvrez comment utiliser un tableau de cohortes pour l’analyse des cohortes dans Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 88%

---

# Vue d’ensemble de la table de cohorte {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Table de cohorte"
>abstract="Créez une visualisation de cohorte pour regrouper les utilisateurs et utilisatrices en fonction de la fin d’un événement et analyser l’évolution de l’engagement et de l’attrition client."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Table de cohorte"
>abstract="Regroupez les utilisateurs et utilisatrices en fonction de la fin d’un événement, puis analysez l’évolution de l’engagement et de l’attrition client. Spécifiez des paramètres supplémentaires tels que la granularité, le type d’analyse des cohortes et l’utilisation ou non du calcul variable. Vous pouvez définir des options avancées pour créer un tableau de latence ou une cohorte de dimension personnalisée en fonction d’une dimension sélectionnée."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente le tableau de cohortes dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Voir [Tableau de cohorte](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


Une *cohorte* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. La visualisation ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Table de cohorte]** s’avère utile, par exemple, pour savoir de quelle façon une cohorte interagit avec une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Vous trouverez des explications sur l’[!UICONTROL analyse des cohortes] sur le Web, tel le cours [Cohort Analysis 101](https://fr.wikipedia.org/wiki/Cohort_analysis) (en anglais).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et segments spécifiques), puis partager le rapport avec les personnes de votre choix. Consultez la section [Traitement et partage](/help/analysis-workspace/curate-share/curate.md).

Exemples d’utilisation de la [!UICONTROL Table de cohorte] :

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Déterminer quand terminer un essai ou une offre pour en optimiser la valeur.
* Trouver des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.

La [!UICONTROL Table de cohorte] est disponible pour tous les clientes et clients Customer Journey Analytics avec des droits d’accès à [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyse de cohorte dans Analysis Workspace](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>L’[!UICONTROL Analyse des cohortes] ne prend pas en charge les mesures non segmentables (y compris les mesures calculées), les mesures non entières (telles que le chiffre d’affaires) ou les occurrences. Seules les mesures pouvant être utilisées dans les segments peuvent être utilisées dans [!UICONTROL Analyse des cohortes] et elles ne peuvent être incrémentées que de 1 à la fois.

Les tables de cohorte de Customer Journey Analytics prennent en charge les mesures à base double (ou toute mesure numérique). Par exemple, la valeur Purchase.Value (valeur double) peut être utilisée comme mesure d’inclusion/retour. En outre, toutes les mesures transmises à Adobe Experience Platform par le biais du connecteur source Analytics sont également doublées.

## Fonctionnalités de la table de cohorte

Les sections suivantes décrivent les fonctionnalités d’analyse de cohorte qui permettent un contrôle précis des cohortes que vous créez.

Pour plus d’informations sur la création d’une cohorte et l’exécution d’un rapport [!UICONTROL Analyse de cohorte], voir [Configurer une table de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Table de [!UICONTROL rétention]

Table de cohorte de [!UICONTROL Rétention] sur les visiteurs et visiteuses récurrents : chaque cellule indique le nombre brut et le pourcentage de visiteurs et visiteuses dans la cohorte qui ont effectué l’action durant cette période. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![Rapport de cohorte de rétention indiquant les unités et le pourcentage de personnes dans la cohorte.](assets/retention-report.png)

### Table [!UICONTROL Attrition]

Une table de cohorte [!UICONTROL Attrition] est l’inverse d’un tableau de rétention. Elle indique les personnes qui ont abandonné ou n’ont jamais rempli les critères de retour de votre cohorte au fil du temps. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![Table Attrition montrant les unités et le pourcentage de personnes qui ne répondaient pas aux critères de retour pour une cohorte.](assets/churn-report.png)

### [!UICONTROL Calcul variable]

Vous pouvez calculer la rétention ou l’attrition en fonction de la colonne précédente, et non de la colonne incluse, ce qu’on appelle calcul variable.

![Rapport de cohorte sur la rétention présentant des calculs basés sur une colonne de données précédente.](assets/retention-report-rolling.png)

### Tableau [!UICONTROL Latence]

Un tableau de latence mesure la durée écoulée avant et après un événement d’inclusion. Mesurer la latence est un excellent outil avant et après analyse. La colonne **[!UICONTROL Inclus]** se trouve au centre de la table, tandis que les périodes avant et après l’événement d’inclusion sont affichées des deux côtés.

![Rapport de cohorte indiquant le temps écoulé avant et après un événement.](assets/retention-report-latency.png)

### Cohorte [!UICONTROL Dimension personnalisée]

Vous pouvez créer des cohortes en fonction d’une dimension sélectionnée, et non des cohortes en fonction du temps, qui sont les cohortes par défaut. Utilisez des dimensions telles que [!UICONTROL Ville géographique], [!UICONTROL Canal marketing], [!UICONTROL campagne], [!UICONTROL produit], [!UICONTROL page], [!UICONTROL région] ou toute autre dimension pour afficher l’évolution de la rétention. En fonction des différentes valeurs de ces dimensions.

![Rapport de cohorte présentant un rapport personnalisé avec des dimensions sélectionnées et non la cohorte temporelle par défaut.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurez une table de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

