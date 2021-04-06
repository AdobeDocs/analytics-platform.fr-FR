---
description: Créez une cohorte et générez un rapport d’analyse des cohortes dans Analysis Workspace.
keywords: Analysis Workspace
title: Configuration d’un rapport d’analyse des cohortes
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 88%

---

# Configuration d’un rapport d’[!UICONTROL analyse des cohortes]

Créez une cohorte et générez un rapport d’[!UICONTROL analyse des cohortes] dans Analysis Workspace.

1. Dans Analysis Workspace, cliquez sur l’icône **[!UICONTROL Visualisations]** du rail de gauche et faites glisser un **[!UICONTROL tableau de cohortes]** sur la zone de travail.

   ![](assets/cohort-table.png)

1. Définissez les **[!UICONTROL critères d’inclusion]**, **[!UICONTROL les critères de retour]**, **[!UICONTROL le type de cohorte]** et **[!UICONTROL les paramètres]** tel qu’illustré dans le tableau ci-dessous.

| Élément | Description |
|--- |--- |
| **[!UICONTROL Critères d’inclusion]** | Vous pouvez appliquer jusqu’à 10 filtres d’inclusion et jusqu’à 3 mesures d’inclusion. La mesure spécifie ce qui place un utilisateur dans une cohorte. Par exemple, si la mesure d’inclusion est Commandes, seuls les utilisateurs qui ont passé une commande durant la période de l’analyse des cohortes seront inclus dans la cohorte initiale.<br>L’opérateur par défaut entre les mesures est AND, mais vous pouvez le changer en OR. En outre, vous pouvez ajouter un filtrage numérique à ces mesures. Par exemple : « Visites >= 1 ».</br> |
| **[!UICONTROL Critères de retour]** | Vous pouvez appliquer jusqu’à 10 filtres de retour et jusqu’à 3 mesures de retour. La mesure indique si l’utilisateur a été fidélisé (rétention) ou non (perte de clientèle). Si, par exemple, la mesure de retour est Affichages de vidéos, seuls les utilisateurs qui ont affiché les vidéos durant des périodes consécutives (après la période pendant laquelle ils ont été ajoutés à une cohorte) seront représentés comme fidélisés. La mesure Visites quantifie également la fidélisation des utilisateurs. |
| **[!UICONTROL Granularité]** | Granularité temporelle : jour, semaine, mois, trimestre ou année. |
| **[!UICONTROL Type]** | **[!UICONTROL Rétention]** (par défaut) : une cohorte de rétention mesure si vos cohortes de visiteurs retournent sur votre propriété au cours du temps. Il s’agit de la cohorte standard que nous avons toujours proposée et qui indique le comportement des utilisateurs réguliers et récurrents. Une cohorte de [!UICONTROL rétention] est indiquée par la couleur verte dans le tableau.<br>**[!UICONTROL Perte de clientèle ]** : une cohorte de perte de clientèle (également appelée « attrition » ou « abandon ») mesure la façon dont vos cohortes de visiteurs abandonnent votre propriété au cours du temps. Perte de clientèle = 1 - rétention. La [!UICONTROL perte de clientèle] est une bonne mesure de l’attractivité et de l’opportunité, car elle vous indique la fréquence à laquelle les clients ne reviennent pas. Vous pouvez utiliser churn pour analyser et identifier les zones d’intérêt : quels filtres de cohortes pourraient faire l&#39;objet d&#39;une certaine attention. Une cohorte de [!UICONTROL perte de clientèle] est indiquée par la couleur rouge dans le tableau (semblable à l’abandon dans notre visualisation **[!UICONTROL  Flux ]**).</br> |
| **[!UICONTROL Paramètres]** | **[!UICONTROL Calcul variable]** : calculez la rétention ou la perte de clientèle en fonction de la colonne précédente, plutôt que de la colonne Inclus (par défaut). Le [!UICONTROL calcul variable] change la méthode de calcul pour vos périodes de « retour ». Le calcul normal trouve de manière indépendante les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période d’inclusion, qu’ils aient ou non fait partie de la cohorte pendant la période précédente. Au lieu de cela, le [!UICONTROL calcul variable] trouve les utilisateurs qui répondent aux critères de « retour » et faisaient partie de la période précédente. Par conséquent, le [!UICONTROL calcul variable] filtre et fait passer par des entonnoirs les utilisateurs qui répondent continuellement aux critères de « retour », période après période. Les critères de [!UICONTROL retour] sont appliqués à chacune des périodes menant à la période sélectionnée. </br><br>**[!UICONTROL Tableau de latence ]** : un tableau de [!UICONTROL latence] mesure le temps qui s’est écoulé avant et après l’événement d’inclusion. La [!UICONTROL latence] est très intéressante à utiliser en pré-/post-analyse. Par exemple, si vous allez lancer une campagne ou un produit et que vous voulez suivre le comportement avant et après le lancement, le tableau de [!UICONTROL latence] affiche le comportement avant et après côte à côte afin de voir l’impact direct. Les cellules de préinclusion dans le tableau de [!UICONTROL latence] sont calculées par les utilisateurs qui répondent aux critères d’[!UICONTROL inclusion] au cours de la période d’inclusion et répondent ensuite aux critères de [!UICONTROL retour] dans les périodes ultérieures à la période d’inclusion. Notez que les tables de [!UICONTROL latence] et la cohorte de [!UICONTROL dimension personnalisée] ne peuvent pas être utilisées conjointement.</br><br>**[!UICONTROL Cohorte de dimension personnalisée]** : créez des cohortes en fonction de la dimension sélectionnée, plutôt qu’en fonction du temps (par défaut). Nombre de clients veulent analyser leurs cohortes en fonction d’autres aspects que le temps. La nouvelle fonctionnalité Cohorte de dimension personnalisée vous fournit la flexibilité de créer des cohortes en fonction des dimensions de votre choix. Utilisez des dimensions telles que le canal marketing, la campagne, le produit, la page, la région ou toute autre dimension dans Adobe Analytics de façon à afficher l’évolution de la rétention en fonction des différentes valeurs de ces dimensions. La définition de filtre de cohorte [!UICONTROL Dimension personnalisée] applique l&#39;élément de dimension uniquement dans le cadre de la période d&#39;inclusion, et non dans la définition de retour.</br><br>Après avoir choisi l’option Cohorte de [!UICONTROL dimension personnalisée], vous pouvez faire glisser et déposer n’importe quelle dimension dans la zone de dépôt. Cela vous permet de comparer des éléments de dimension similaires sur la même période. Par exemple, vous pouvez comparer les performances des villes côte à côte, des produits, des campagnes, etc. Vous verrez vos 14 principaux éléments de dimension. Cependant, vous pouvez utiliser un filtre (accessible en survolant la partie droite de la dimension déposée) pour afficher uniquement les éléments de dimension désirés. Une cohorte de [!UICONTROL dimension personnalisée] ne peut pas être utilisée avec la fonctionnalité de tableau de [!UICONTROL latence].</br> |

1. Réglez les **[!UICONTROL paramètres du tableau de cohortes]** en cliquant sur l’icône d’engrenage.

| Paramètre| Description|
| Afficher uniquement le pourcentage | Supprime la valeur numérique et affiche uniquement le pourcentage. |
| Pourcentage arrondi au plus proche entier | Arrondit le pourcentage à la valeur entière la plus proche au lieu d’afficher la valeur décimale. |
| Afficher la rangée en pourcentage moyen | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |

## Création du rapport [!UICONTROL Analyse des cohortes]

1. Cliquez sur **[!UICONTROL Créer]**.

   ![Résultat de l’étape](assets/cohort-report.png)

   Le rapport présente les visiteurs qui ont passé une commande (colonne *`Included`*) et qui sont revenus sur votre site au cours de visites consécutives. Une réduction des visites au fil du temps permet d’identifier les problèmes et d’agir.
1. (Facultatif) Créez un filtre à partir d’une sélection.

   Sélectionnez des cellules (contiguës ou non), puis cliquez avec le bouton droit de la souris > **[!UICONTROL Créer un filtre à partir de la sélection]**.

1. Dans le [Créateur de filtres](/help/components/filters/manage-filters.md), modifiez davantage le filtre, puis cliquez sur **[!UICONTROL Enregistrer]**.

   Le filtre enregistré peut être utilisé dans le panneau [!UICONTROL Filtre] de [!UICONTROL Analysis Workspace].
1. Nommez et enregistrez votre projet de cohorte.
1. (Facultatif) [Traitez et partagez](/help/analysis-workspace/curate-share/curate.md) les composants de projet.

   >[!NOTE]
   >
   >Vous devez enregistrer votre projet pour que la fonction de traitement soit disponible.
