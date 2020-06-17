---
description: Créez une cohorte et générez un rapport d’analyse des cohortes dans Analysis Workspace.
keywords: Analysis Workspace
title: Exécution d’un rapport d’analyse des cohortes
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 73%

---


# Configure a [!UICONTROL Cohort Analysis] report

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Create a cohort and run a [!UICONTROL Cohort Analysis] report in Analysis Workspace.

1. Dans Analysis Workspace, cliquez sur l’icône **[!UICONTROL Visualisations]** du rail de gauche et faites glisser un **[!UICONTROL tableau de cohortes]** sur la zone de travail.

   ![](assets/cohort-table.png)

1. Définissez les **[!UICONTROL critères d’inclusion]**, **[!UICONTROL les critères de retour]**, **[!UICONTROL le type de cohorte]** et **[!UICONTROL les paramètres]** tel qu’illustré dans le tableau ci-dessous.

| Élément | Description |
|--- |--- |
| **[!UICONTROL Critères d’inclusion]** | Vous pouvez appliquer jusqu’à dix segments d’inclusion et trois mesures d’inclusion. La mesure spécifie ce qui place un utilisateur dans une cohorte. Par exemple, si la mesure d’inclusion est Commandes, seuls les utilisateurs qui ont passé une commande durant la période de l’analyse des cohortes seront inclus dans la cohorte initiale.<br>L’opérateur par défaut entre les mesures est AND, mais vous pouvez le changer en OR. En outre, vous pouvez ajouter un filtrage numérique à ces mesures. Par exemple : « Visites >= 1 ».</br> |
| **[!UICONTROL Critères de retour]** | Vous pouvez appliquer jusqu’à dix segments de retour et trois mesures de retour. La mesure indique si l’utilisateur a été fidélisé (rétention) ou non (perte de clientèle). Si, par exemple, la mesure de retour est Affichages de vidéos, seuls les utilisateurs qui ont affiché les vidéos durant des périodes consécutives (après la période pendant laquelle ils ont été ajoutés à une cohorte) seront représentés comme fidélisés. La mesure Visites quantifie également la fidélisation des utilisateurs. |
| **[!UICONTROL Granularité]** | Granularité temporelle : jour, semaine, mois, trimestre ou année. |
| **[!UICONTROL Type]** | **[!UICONTROL Rétention]** (par défaut) : une cohorte de rétention mesure si vos cohortes de visiteurs retournent sur votre propriété au cours du temps. Il s’agit de la cohorte standard que nous avons toujours proposé et qui indique le comportement des utilisateurs réguliers et récurrents. A [!UICONTROL Retention] Cohort is indicated by the color green in the table.<br>**[!UICONTROL Perte de clientèle ]** : une cohorte de perte de clientèle (également appelée « attrition » ou « abandon ») mesure la façon dont vos cohortes de visiteurs abandonnent votre propriété au cours du temps. Perte de clientèle = 1 - rétention.[!UICONTROL La perte de clientèle est une bonne mesure de l’attractivité et de l’opportunité, car elle vous indique la fréquence à laquelle les clients ne reviennent pas.]Vous pouvez utiliser la perte de clientèle pour analyser et identifier les zones d’intérêt, c’est-à-dire les segments de cohortes qui pourraient avoir besoin d’attention. A[!UICONTROL Churn]Cohort is indicated by the color red in the table (similar to fallout in our**[!UICONTROL  Flow ]**visualization).</br> |
| **[!UICONTROL Paramètres]** | **[!UICONTROL Calcul variable]** : calculez la rétention ou la perte de clientèle en fonction de la colonne précédente, plutôt que de la colonne Inclus (par défaut). [!UICONTROL Le calcul variable change la méthode de calcul pour vos périodes de « retour ». ] Le calcul normal trouve de manière indépendante les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période d’inclusion, qu’ils aient ou non fait partie de la cohorte pendant la période précédente. Instead, [!UICONTROL Rolling Calculation] finds users who meet &quot;return&quot; criteria and were part of the previous period. Therefore, [!UICONTROL Rolling Calculation] filters and funnels the users who continually meet the &quot;return&quot; criteria period over period. [!UICONTROL Les critères de retour sont appliqués à chacune des périodes menant à la période sélectionnée. ] </br><br>**[!UICONTROL Tableau ]**de latence : Un tableau de[!UICONTROL latence]mesure le temps qui s’est écoulé avant et après le événement d’inclusion.[!UICONTROL La latence est très intéressante à utiliser en pré-/post-analyse.]For example, if you have an upcoming product or campaign launch and you want to track behavior before as well as see how it performs after, the[!UICONTROL Latency]table will display the pre and post behavior side by side to see the direct impact. The pre-inclusion cells in the[!UICONTROL Latency]Table are calculated by users who meet the[!UICONTROL Inclusion]criteria on the inclusion period and then meet the[!UICONTROL Return]criteria in the periods before the inclusion period. Note that[!UICONTROL Latency]tables and[!UICONTROL Custom Dimension]Cohort cannot be used together.</br><br>**[!UICONTROL Cohorte de dimension personnalisée]** : créez des cohortes en fonction de la dimension sélectionnée, plutôt qu’en fonction du temps (par défaut). Nombre de clients veulent analyser leurs cohortes en fonction d’autres aspects que le temps. La nouvelle fonctionnalité Cohorte de dimension personnalisée vous fournit la flexibilité de créer des cohortes en fonction des dimensions de votre choix. Utilisez des dimensions telles que le canal marketing, la campagne, le produit, la page, la région ou toute autre dimension dans Adobe Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions. The [!UICONTROL Custom Dimension] Cohort segment definition applies the dimension item only as part of the inclusion period, not as part of the return definition.</br><br>[!UICONTROL Après avoir choisi l’option Cohorte de dimension personnalisée, vous pouvez faire glisser et déposer n’importe quelle dimension dans la zone de dépôt. ] Cela vous permet de comparer des éléments de dimension similaires sur la même période. Par exemple, vous pouvez comparer les performances des villes côte à côte, des produits, des campagnes, etc. Vous verrez vos 14 principaux éléments de dimension. Cependant, vous pouvez utiliser un filtre (accessible en survolant la partie droite de la dimension déposée) pour afficher uniquement les éléments de dimension désirés. A [!UICONTROL Custom Dimension] Cohort cannot be used with the [!UICONTROL Latency] Table feature.</br> |

1. Réglez les **[!UICONTROL paramètres du tableau de cohortes]** en cliquant sur l’icône d’engrenage.

| Paramètre| Description|
| Afficher uniquement le pourcentage | Supprime la valeur numérique et affiche uniquement le pourcentage. |
| Pourcentage arrondi au plus proche entier | Arrondit le pourcentage à la valeur entière la plus proche au lieu d’afficher la valeur décimale. |
| Afficher la rangée en pourcentage moyen | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |

## Build the [!UICONTROL Cohort Analysis] report

1. Cliquez sur **[!UICONTROL Créer]**.

   ![Résultat de l’étape](assets/cohort-report.png)

   Le rapport présente les visiteurs qui ont passé une commande (colonne *`Included`*) et qui sont revenus sur votre site au cours de visites consécutives. Une réduction des visites au fil du temps permet d’identifier les problèmes et d’agir.
1. (Facultatif) Créez un segment à partir d’une sélection.

   Sélectionnez des cellules (contiguës ou non), puis cliquez avec le bouton droit de la souris > **[!UICONTROL Créer un segment d’après la sélection]**.

1. In the [Filter Builder](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html), further edit the segment, then click **[!UICONTROL Save]**.

   Le segment enregistré est disponible pour utilisation dans le panneau [!UICONTROL Segment][!UICONTROL  d’Analysis Workspace].
1. Nommez et enregistrez votre projet de cohorte.
1. (Facultatif) [Traitez et partagez](/help/analysis-workspace/curate-share/curate.md) les composants de projet.

   >[!NOTE]
   >
   >Vous devez enregistrer votre projet pour que la fonction de traitement soit disponible.

