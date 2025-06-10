---
description: Créez un tableau de cohortes et exécutez une analyse des cohortes dans Analysis Workspace.
keywords: Analysis Workspace
title: Configuration d’une table de cohorte
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 86%

---

# Configuration d’une table de cohorte

Pour créer et configurer une [!UICONTROL table de cohorte], procédez comme suit :

1. Ajoutez une visualisation ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Table de cohorte]**. Voir [Ajouter une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Définissez les **[!UICONTROL critères d’inclusion]**, les **[!UICONTROL critères de retour]**, le **[!UICONTROL type de cohorte]** et les **[!UICONTROL paramètres]** comme indiqué dans le tableau ci-dessous.

   ![Configurer une table de cohorte](assets/cohort-configure.png)

   | Élément | Description |
   |--- |--- |
   | **[!UICONTROL Critères d’inclusion]** | Vous pouvez appliquer jusqu’à dix segments d’inclusion et trois mesures d’inclusion. La mesure indique à quelle cohorte appartient un utilisateur ou une utilisatrice. Par exemple, si la mesure d’inclusion est Commandes, seuls les utilisateurs et utilisatrices qui ont passé une commande durant la période de l’analyse des cohortes seront inclus dans la cohorte initiale.<br>L’opérateur par défaut entre les mesures est AND, mais vous pouvez le changer en OR. En outre, vous pouvez ajouter une segmentation numérique à ces mesures. Par exemple : `Sessions >= 1`.</br> |
   | **[!UICONTROL Critères de retour]** | Vous pouvez appliquer jusqu’à dix segments de retour et trois mesures de retour. La mesure indique si la personne utilisatrice a été fidélisée (rétention) ou non (perte de clientèle). Par exemple, si la mesure de retour est Vues vidéos, seuls les utilisateurs et utilisatrices qui ont affiché les vidéos durant des périodes consécutives (après la période pendant laquelle ils ont été ajoutés à une cohorte) seront représentés comme fidélisés. La mesure Sessions quantifie également la rétention des utilisateurs et utilisatrices. |
   | [!BADGE Conteneur ]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL  B2B edition ]** | Par défaut, l’analyse des cohortes est liée au conteneur Personne . Si d’autres conteneurs autres que Personne sont disponibles à partir de la connexion basée sur le compte qui prend en charge le projet Workspace, vous pouvez sélectionner un autre conteneur pour l’analyse des cohortes dans le menu déroulant **[!UICONTROL Conteneur]**. |
   | **[!UICONTROL Granularité]** | Granularité temporelle : jour, semaine, mois, trimestre ou année. |
   | **[!UICONTROL Type]** | **[!UICONTROL Rétention]** (par défaut) : une cohorte **[!UICONTROL Rétention]** mesure si vos cohortes de personnes retournent sur votre propriété au fil du temps. Une cohorte de rétention est la cohorte standard et indique le comportement de retour et de répétition des utilisateurs et utilisatrices. Une couleur verte indique une cohorte [!UICONTROL Rétention] dans la table.<br>**[!UICONTROL Attrition ]** : une cohorte**[!UICONTROL  Attrition ]**(également appelée « perte de la clientèle » ou « abandon ») mesure la façon dont vos cohortes de personnes abandonnent votre propriété au fil du temps. L’attrition est le contraire de la rétention : `Churn = 1 - Retention`. L’[!UICONTROL attrition] est une bonne mesure de l’attractivité et de l’opportunité, car elle vous indique la fréquence à laquelle les clients et clientes ne reviennent pas. Vous pouvez utiliser l’attrition pour analyser et identifier les domaines ciblés : quels segments de cohortes pourraient nécessiter une certaine attention ? Une couleur rouge indique une cohorte [!UICONTROL Attrition] dans la table (similaire à l’abandon dans la visualisation**[!UICONTROL  Flux ]**).</br> |
   | **[!UICONTROL Paramètres]** | **[!UICONTROL Calcul variable]** : calculez la rétention ou l’attrition en fonction de la colonne précédente, plutôt que de la colonne Inclus (par défaut). Le [!UICONTROL calcul variable] change la méthode de calcul pour vos périodes de « retour ». Le calcul normal trouve les utilisateurs et les utilisatrices qui répondent aux critères de retour et qui faisaient partie de la période d’inclusion. Qu’ils fassent partie ou non de la cohorte de la période précédente. Au lieu de cela, le [!UICONTROL calcul variable] trouve les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période précédente. Par conséquent, la [!UICONTROL Calcul variable] segmente et entonnoir les utilisateurs qui répondent continuellement aux critères de « retour » sur une période donnée. Les critères de [!UICONTROL retour] sont appliqués à chacune des périodes menant à la période sélectionnée. </br><br>**[!UICONTROL Table de latence ]** : une [!UICONTROL table de latence] mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. La [!UICONTROL table de latence] est intéressante à utiliser avant/après analyse. Par exemple, vous avez un lancement de produit ou de campagne à venir et vous souhaitez effectuer le suivi du comportement avant et après le lancement. La [!UICONTROL table de latence] affiche côte à côte le comportement avant et après pour voir l’impact direct. Les cellules de préinclusion dans la [!UICONTROL table de latence] sont calculées par les utilisateurs et utilisatrices qui répondent aux critères d’[!UICONTROL inclusion] au cours de la période d’inclusion et répondent ensuite aux critères de [!UICONTROL retour] dans les périodes antérieures à la période d’inclusion. Notez que la [!UICONTROL table de latence] et la [!UICONTROL cohorte de dimension personnalisée] ne peuvent pas être utilisées conjointement.</br><br>**[!UICONTROL Cohorte de dimension personnalisée]** : créez des cohortes en fonction de la dimension sélectionnée, plutôt qu’en fonction du temps (par défaut). Nombre de clients veulent analyser leurs cohortes en fonction d’autres aspects que le temps. La nouvelle fonctionnalité Cohorte de dimension personnalisée vous fournit la flexibilité de créer des cohortes en fonction des dimensions de votre choix. Utilisez des dimensions telles que le canal marketing, la campagne, le produit, la page, la zone géographique ou toute autre dimension dans Adobe Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions. La définition de segment de cohorte de [!UICONTROL dimension personnalisée] applique la dimension uniquement dans le cadre de la période d’inclusion, et non dans le cadre de la définition du renvoi.</br><br>Après avoir choisi l’option [!UICONTROL Cohorte de dimension personnalisée], vous pouvez faire glisser et déposer n’importe quelle dimension dans la zone de dépôt. Ajouter des dimensions vous permet de comparer des éléments de dimension similaires sur la même période. Par exemple, vous pouvez comparer les performances des villes côte à côte, des produits, des campagnes, etc. La table de cohorte renvoie vos 14 principaux éléments de dimension. Cependant, vous pouvez utiliser un segment ![segment](/help/assets/icons/Filter.svg) pour afficher uniquement les éléments de dimension souhaités. Une [!UICONTROL cohorte de dimension personnalisée] ne peut pas être utilisée avec la fonctionnalité de [!UICONTROL table de latence].</br> |

1. Cliquez sur **[!UICONTROL Créer]**.
1. Pour reconfigurer la [!UICONTROL table de cohorte], sélectionnez ![Modifier](/help/assets/icons/Edit.svg).

1. (Facultatif) Créez un segment ou une audience à partir d’une sélection.

   Sélectionnez des cellules (contiguës ou non), puis cliquez avec le bouton droit de la souris > **[!UICONTROL Créer un segment d’après la sélection]**.

   ![Créer un segment ou une audience](assets/retention-createfilter.png)

1. Dans le [Créateur de segments](/help/components/segments/seg-builder.md), modifiez davantage le segment, puis cliquez sur **[!UICONTROL Enregistrer]**.

   Le segment enregistré est disponible pour utilisation dans le panneau [!UICONTROL Segment] d’[!UICONTROL Analysis Workspace].

## Paramètres

Vous pouvez définir des paramètres spécifiques pour une [!UICONTROL table de cohorte].

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) pour ajuster les paramètres de la [!UICONTROL Table de cohorte].

   | Paramètre | Description |
   |---|---|
   | **Afficher uniquement le pourcentage** | Supprime la valeur numérique et affiche uniquement le pourcentage. |
   | **Arrondir le pourcentage à l’entier le plus proche** | Arrondit la valeur de pourcentage à l’entier le plus proche au lieu d’afficher la valeur décimale. |
   | **Afficher la ligne en pourcentage moyen** | Insère une nouvelle ligne en haut de la table, puis ajoute la moyenne des valeurs dans chaque colonne. |


>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Paramètres de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu contextuel de visualisation](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

