---
title: Aperçu du tableau de cohortes
description: Découvrez comment approfondir les données relatives à votre audience et les diviser en groupes associés à l’aide de l’analyse des cohortes. Utilisez l’analyse des cohortes dans Analysis Workspace.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
TQID: https://experienceleague.adobe.com/3WB5sKKSaLe9VvAe6rlCTUqDYsG3kiqLCN-KaEtIlDw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: addf009e-030a-4310-8534-776a3e62ed48
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 754
ht-degree: 92%

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

_Cet article présente le tableau de cohortes dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Voir [Tableau de cohortes](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


Une *cohorte* est un groupe de personnes partageant des caractéristiques communes au cours d’une période spécifique. Une visualisation ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Table de cohorte]** s’avère utile, par exemple, pour savoir de quelle façon une cohorte réagit par rapport à une marque. Vous pouvez facilement déceler des changements de tendances, pour y réagir en conséquence. (Vous trouverez des explications sur l’[!UICONTROL analyse des cohortes] sur le Web, tel le cours [Cohort Analysis 101](https://fr.wikipedia.org/wiki/Cohort_analysis) (en anglais).)

Après avoir créé un rapport de cohorte, vous pouvez en traiter les composants (dimensions, mesures et segments spécifiques), puis partager le rapport avec les personnes de votre choix. Consultez la section [Traitement et partage](/help/analysis-workspace/curate-share/curate.md).

Exemples d’utilisation de la [!UICONTROL Table de cohorte] :

* Lancez des campagnes conçues pour déclencher une action spécifique.
* Ajustez le budget marketing exactement au bon moment au cours du cycle de vie des clients.
* Sachez reconnaître quand terminer un essai ou une offre pour en optimiser la valeur.
* Trouvez des idées de test A/B dans des domaines tels que le prix, le cheminement de mise à niveau, etc.

La [!UICONTROL Table de cohorte] est disponible pour tous les clientes et clients Customer Journey Analytics avec des droits d’accès à [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyse des cohortes dans Analysis Workspace](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>Lʼ[!UICONTROL analyse de cohortes] ne prend pas en charge les mesures qui ne peuvent pas être segmentées (y compris les mesures calculées), les mesures non entières (telles que le chiffre d’affaires) ou les occurrences. Seules les mesures pouvant être utilisées dans les segments sont compatibles avec une [!UICONTROL analyse de cohortes], mais elles ne peuvent être augmentées que de 1 à la fois.

Les tables de cohorte de Customer Journey Analytics prennent en charge les mesures à base double (ou à base numérique en général). Par exemple, la valeur Purchase.Value (double) peut être utilisée comme mesure d’inclusion/retour. En outre, toutes les mesures transmises à Adobe Experience Platform par le biais du connecteur source Analytics sont également doubles.

## Fonctionnalités de la table de cohorte

Les sections suivantes décrivent les fonctionnalités d’analyse des cohortes qui permettent un contrôle précis des cohortes que vous créez.

Pour plus d’informations sur la création d’une cohorte et l’exécution d’un rapport [!UICONTROL Analyse des cohortes], consultez [Configurer une table de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Table de rétention

Une table de cohorte de [!UICONTROL rétention] renvoie des personnes : chaque cellule de données indique le nombre brut et le pourcentage de personnes dans la cohorte qui ont effectué l’action durant cette période. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![Rapport de cohorte de rétention indiquant les unités et le pourcentage de personnes dans la cohorte.](assets/retention-report.png)

### Tableau de résiliation

Une table de cohorte d’[!UICONTROL attrition] est l’opposé d’un tableau de rétention. Elle indique les personnes qui ont abandonné ou n’ont jamais rempli les critères de retour de votre cohorte au fil du temps. Vous pouvez inclure jusqu’à 3 mesures et 10 segments.

![Tableau d’attrition montrant les unités et le pourcentage de personnes qui ne répondaient pas aux critères de retour pour une cohorte.](assets/churn-report.png)

### Calcul évolutif

Vous pouvez calculer la rétention ou l’attrition en fonction de la colonne précédente, et non de la colonne incluse, que l’on appelle calcul glissant.

![Rapport de cohorte de rétention présentant des calculs basés sur une colonne de données précédente.](assets/retention-report-rolling.png)

### Tableau de latence

Un tableau de latence mesure la durée écoulée avant et après l’événement d’inclusion. La mesure de la latence est un excellent outil pré-/post-analyse. La colonne **[!UICONTROL Inclus]** se trouve au centre du tableau, tandis que les périodes avant et après l’événement d’inclusion sont affichées des deux côtés.

![Rapport de cohorte indiquant le temps écoulé avant et après un événement.](assets/retention-report-latency.png)

### Cohorte de dimension personnalisée

Vous pouvez créer des cohortes sur la base d’une dimension sélectionnée, et non des cohortes en fonction du temps, qui sont les cohortes par défaut. Utilisez des dimensions telles que [!UICONTROL Ville géographique], [!UICONTROL Canal marketing], [!UICONTROL campagne], [!UICONTROL produit], [!UICONTROL page], [!UICONTROL région] ou toute autre dimension pour afficher l’évolution de la rétention. En fonction des différentes valeurs de ces dimensions.

![Rapport de cohorte présentant un rapport personnalisé avec des dimensions sélectionnées et non la cohorte en fonction du temps par défaut.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurez une table de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

