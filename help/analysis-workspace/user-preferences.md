---
title: Comment définir les préférences utilisateur dans Analysis Workspace
description: Vous pouvez définir des préférences générales et des préférences du projet pour les utilisateurs.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '3466'
ht-degree: 73%

---

# Préférences de l’utilisateur

Vous pouvez gérer les paramètres utilisateur ou les préférences d’Analysis Workspace et des composants associés pour tous les nouveaux projets ou panneaux que vous créez. Les projets et panneaux existants ne sont pas affectés.

## Préférences de mise à jour

Vous pouvez mettre à jour vos préférences comme suit :

- Sélectionnez ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Modifier les préférences]** dans l’interface principale de Workspace.
- Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Préférences utilisateur]** dans le menu lorsque vous travaillez dans un projet Workspace.
- Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Préférences]** dans la barre supérieure du Customer Journey Analytics principal (disponible uniquement pour les administrateurs de produit).

## Configuration des préférences

Vous pouvez configurer les préférences suivantes :

### Préférences générales

Les préférences générales s’appliquent à votre expérience Customer Journey Analytics dans le navigateur. Pour plus d’informations sur l’accès à ces préférences, consultez [Mettre à jour les préférences](#update-preferences).

| Préférence | Options |
| --- | --- |
| **[!UICONTROL Page de destination]** | Choisissez la page qui s’affiche par défaut lorsque vous accédez à Customer Journey Analytics : <ul><li>Liste des projets (par défaut)</li><li>Projet vierge</li><li>Analyse guidée Blank Trends</li><li>Projet spécifique, sélectionné dans une liste</li></ul> |
| **[!UICONTROL Astuces]** | Affiche les conseils dans un cadre bleu de la zone inférieure droite d’Analysis Workspace. <p>Cette option est activée par défaut.</p> |
| **[!UICONTROL Composants affichés dans les groupes de panneaux de gauche]** | Sélectionnez le nombre de composants de chaque groupe à afficher dans le menu Composants du panneau de gauche. <p>Si vous choisissez 0 pour un groupe de composants, celui-ci n’est plus accessible à partir du panneau de gauche.</p><p>Par défaut, 5 composants sont affichés pour chacun des groupes de composants suivants :</p> <ul><li>Dimensions</li><li>Mesures</li><li>Filtres</li><li>Périodes</li></ul> <p>Pour plus d’informations sur les composants dans Analysis Workspace, consultez [Présentation des composants](/help/components/overview.md).</p> |

### Préférences de l’organisation IMS {#ims-organization-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_shareonlyworkspace"
>title="Autoriser le partage uniquement avec les utilisateurs et utilisatrices de Workspace"
>abstract="Lorsqu’elle est activée, l’option **[!UICONTROL Partager avec n’importe qui]** n’est plus disponible pour les utilisateurs qui partagent un projet Analysis Workspace. Les personnes qui ont auparavant reçu l’accès à un projet via cette option de partage ne peuvent plus accéder au projet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_requireexperiencecloudauth"
>title="Exiger une authentification Experience Cloud"
>abstract="Lorsqu’elle est activée, les personnes qui ont accès à un projet à partir de l’option Partager avec n’importe qui dans Analysis Workspace doivent s’authentifier à l’aide de leurs informations d’identification d’Experience Cloud."

<!-- markdownlint-enable MD034 -->


Vous pouvez mettre à jour les préférences de la société qui s’appliquent aux utilisateurs et utilisatrices et aux projets de votre organisation. Pour plus d’informations sur l’accès à ces préférences, consultez [Mettre à jour les préférences](#update-preferences).

| Section | Préférence | Options |
| --- | --- | --- |
| **Partage des projets** | | |
| | Autoriser le partage uniquement avec les utilisateurs et utilisatrices de Workspace | Lorsque cette option est activée, les utilisateurs de votre entreprise ne peuvent pas voir l’option **[!UICONTROL Partager avec n’importe qui]** dans le menu **[!UICONTROL Partager]** . Cela signifie que les utilisateurs et utilisatrices ne peuvent pas partager des projets avec des personnes qui n’ont pas de compte Analysis Workspace dans votre organisation, comme décrit dans [Partager un projet avec tout le monde (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) dans [Partager des projets](/help/analysis-workspace/curate-share/share-projects.md).<br/>Cette option est désactivée par défaut pour toutes les organisations (ce qui signifie que les utilisateurs peuvent partager des projets avec des personnes en dehors de l’organisation), à l’exception des clients qui disposent d’une licence Healthcare Shield. <p>Tenez compte des points suivants lorsque vous activez ou désactivez cette option :<ul><li>Lorsque vous activez cette option, les personnes qui avaient auparavant reçu l’accès à un projet via l’option de partage [!UICONTROL Partager avec n’importe qui] ne peuvent plus accéder au projet.</li><li>Si cette option est activée (pour permettre le partage uniquement avec les utilisateurs de Workspace) puis désactivée ultérieurement (pour permettre le partage avec n’importe qui), les personnes qui ont précédemment reçu l’accès à un projet via l’option de partage [!UICONTROL Partager avec n’importe qui] ne retrouvent pas automatiquement leur accès au projet. Dans ce cas, l’utilisateur qui a partagé le projet doit activer l’option [!UICONTROL **Le lien est actif**] disponible lors du partage d’un projet avec n’importe qui **([!UICONTROL Partager]** > **[!UICONTROL Partager avec n’importe qui]**), comme décrit dans la section [Partager un projet avec n’importe qui (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) dans [Partager des projets](/help/analysis-workspace/curate-share/share-projects.md).</li><li>**Pour les clientes et clients qui détiennent une licence Healthcare Shield :** cette option est activée par défaut et ne peut pas être désactivée. Avant de pouvoir désactiver cette option pour que les utilisateurs puissent utiliser l’option de partage [!UICONTROL Partager avec n’importe qui], vous devez d’abord ajouter l’autorisation [!UICONTROL Partager les liens de projet avec n’importe qui] (située sous [!UICONTROL Outils de création de rapports]) dans Adobe Admin Console. Une fois l’autorisation ajoutée, vous pouvez désactiver cette option, puis accepter la mention légale qui en résulte. Pour plus d’informations sur l’ajout d’une autorisation dans Admin Console, voir [Gestion des autorisations de produit dans Admin Console](https://helpx.adobe.com/fr/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Exiger une authentification Experience Cloud | Lorsqu’elle est activée, les personnes qui ont accès à un projet à partir de l’option Partager avec n’importe qui dans Analysis Workspace doivent s’authentifier à l’aide de leurs informations d’identification d’Experience Cloud.<p>Une fois cette option activée, chaque fois qu’un utilisateur partage un projet à l’aide de l’option de partage [!UICONTROL Partager avec n’importe qui], l’option [!UICONTROL Exiger une authentification Experience Cloud] est activée dans la boîte de dialogue de partage et elle ne peut pas être désactivée par l’utilisateur qui partage le projet. Pour plus d’informations sur la façon dont les utilisateurs peuvent partager des projets avec n’importe qui, voir [Partager un projet avec n’importe qui (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) dans [Partager des projets](/help/analysis-workspace/curate-share/share-projects.md). <p> <p>Tenez compte des points suivants lorsque vous activez cette option : <ul><li>Lorsque vous activez cette option, tous les projets qui étaient précédemment partagés avec l’option de partage [!UICONTROL Partager avec n’importe qui] et pour lesquels l’option [!UICONTROL Exiger une authentification Experience Cloud] n’est pas activée sont désactivés.<p>Si cette option est activée (pour exiger une authentification de l’Experience Cloud) puis désactivée ultérieurement (pour permettre à toute personne disposant du lien d’accéder au projet), les personnes qui ont auparavant reçu l’accès à un projet via l’option de partage [!UICONTROL Partager avec n’importe qui] ne retrouvent pas automatiquement leur accès au projet. Dans ce cas, l’utilisateur qui a partagé le projet doit activer l’option [!UICONTROL Le lien est actif]*disponible lors du partage d’un projet avec n’importe qui **([!UICONTROL Partager]** > **[!UICONTROL Partager avec n’importe qui]** > **[!UICONTROL Le lien est actif]**), comme décrit dans la section [Partager un projet avec quiconque (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) dans [Partager des projets de partage](/help/analysis-workspace/curate-share/share-projects.md)} .</li><li>Cette option est disponible uniquement si l’authentification unique est implémentée dans votre organisation. Pour plus d’informations sur la façon dont les administrateurs système peuvent activer l’authentification unique pour votre organisation, voir [Configuration de l’identité et de l’authentification unique](https://helpx.adobe.com/fr/enterprise/using/set-up-identity.html).</p><p>Si l’authentification unique est configurée pour votre organisation, vérifiez si un type de création de compte automatique est implémenté dans la console. En règle générale, un administrateur système configure cette configuration, comme décrit dans la section [Activer la création automatique de compte](https://helpx.adobe.com/fr/enterprise/using/automatic-account-creation.html).</li><li>Si votre entreprise détient une licence Healthcare Shield, cette option est activée par défaut et ne peut pas être désactivée.</li></ul> |

{style="table-layout:auto"}

### Préférences des projets et analyses {#project-and-analysis-preferences}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_categoricalpalette"
>title="Palette catégorielle"
>abstract="Appliquée à de nombreuses visualisations dans Analysis Workspace et l’analyse guidée. Chaque couleur représente une valeur catégorielle distincte."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_divergingpalette"
>title="Palette divergente"
>abstract="Appliquée au tableau de cohorte dans Analysis Workspace et l’analyse guidée par la croissance des utilisateurs. Cette palette a une signification numérique avec deux extrêmes et une ligne de base au milieu."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_sequentialpalette"
>title="Palette séquentielle"
>abstract="Appliquée à l’analyse guidée des tendances de fréquence (barres empilées). Cette palette a une signification numérique allant du plus clair au plus foncé."

<!-- markdownlint-enable MD034 -->


Vous pouvez personnaliser ces préférences pour tous les nouveaux projets Analysis Workspace, les nouveaux panneaux Analysis Workspace et les nouvelles analyses guidées. Pour plus d’informations sur l’accès à ces préférences, consultez [Mettre à jour les préférences](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des projets individuels dans Analysis Workspace, comme décrit dans la section [Vue d’ensemble des projets](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

| Section | Préférence | Options |
| --- | --- | --- |
| **Afficher** | | |
|  | [Afficher la densité](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=fr) | Sélectionnez le contenu à afficher à l’écran en réduisant l’espacement vertical du panneau de gauche, des tableaux à structure libre et des tableaux de cohortes. <ul><li>Compact</li><li>Confortable</li><li>Développé (par défaut)</li></ul> |
| | [Palette de couleurs](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=fr) | Sélectionnez les palettes de couleurs de visualisation utilisées dans Analysis Workspace et les analyses guidées. <ul><li> Palette catégorielle : appliquée à de nombreuses visualisations dans Analysis Workspace et l’analyse guidée. Chaque couleur représente une valeur catégorielle distincte. Choisissez parmi les options fournies par Adobe ou saisissez une palette personnalisée définie par des valeurs hexadécimales délimitées par des virgules.</li><li> Palette divergente : appliquée à la table de cohorte dans Analysis Workspace et à l’analyse guidée Croissance des utilisateurs et des utilisatrices. Cette palette a une signification numérique, avec deux extrêmes et une ligne de base au milieu.<li> Palette séquentielle : appliquée à l’analyse guidée Tendances de fréquence (barre empilée). Cette palette a une signification numérique allant du clair au foncé.</li></ul> |
| **Données** | | |
|  | [Vue de données](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr#report-suite) | Sélectionnez les données dans lesquelles les tableaux et les visualisations obtiennent leurs données. <ul><li>La plus récente (par défaut)</li><li>Vue de données spécifique sélectionnée dans une liste</li></ul> |
|  | [Calendrier](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr#calendar) | Effectuez une sélection dans une liste de : <ul><li>Plages fournies par Adobe (par défaut, ce mois-ci)</li><li>Vous pouvez activer par défaut [!UICONTROL Effectuer des composants de période par rapport au calendrier du panneau].</li></ul> |
|  | [Type de panneau](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr) | <ul><li>À structure libre (par défaut)</li><li>Vide</li><li>Quick Insights</li></ul> |
|  | Comptage des instances | Activez l’option [!UICONTROL Compter les instances de répétition] pour indiquer si les instances de répétition sont comptabilisées dans les rapports. Par exemple, lorsqu’elle est activée, plusieurs pages vues consécutives sur la même page sont traitées comme plusieurs pages vues. Lorsque cette option est désactivée, plusieurs pages vues consécutives sur la même page sont comptabilisées comme une seule page vue. <p>**Remarque :** Ce paramètre affecte uniquement certaines mesures (telles que les sessions) et ne s’applique pas aux visualisations Flux ou Abandons.</p> |
|  | Format du nombre | <ul><li>1 000,00 (par défaut)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Caractère de séparation CSV | <ul><li>Virgule (par défaut)</li><li>Point-virgule</li><li>Deux-points</li><li>Tube</li><li>Point</li><li>un espace</li><li>Tabulation</li></ul> |
|  | Afficher les annotations | Indiquez si les annotations sont visibles dans les projets. Pour plus d’informations sur les annotations, consultez [Présentation des annotations](/help/components/annotations/overview.md). |


### Préférences du tableau à structure libre {#freeform-table-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_showanomalies"
>title="Afficher les anomalies"
>abstract="Sélectionnez **[!UICONTROL Afficher les anomalies]** pour exécuter automatiquement la détection des anomalies sur la première colonne de mesure ajoutée à une visualisation de tableau à structure libre de série temporelle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_showforecast"
>title="Afficher les prévisions"
>abstract="Sélectionnez **[!UICONTROL Afficher la prévision]** pour prévoir automatiquement la première colonne de mesures ajoutée à une visualisation de tableau à structure libre de série temporelle."

<!-- markdownlint-enable MD034 -->


Vous pouvez personnaliser les préférences du tableau à structure libre pour tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des tableaux individuels.

Sélectionnez les titres des sections liées pour plus d’informations et de contexte sur les préférences disponibles.

| Section | Préférence | Options |
| --- | --- | --- |
| **Tableau** | | |
| | Type de tableau | <ul><li>Structure libre</li><li>Créateur de tableaux</li></ul> |
| | Mesure par défaut du tableau | <ul><li>Occurrences</li><li>Visiteurs uniques</li><li>Visites</li></ul> |
| | Dimension du tableau par défaut | Sélectionnez l’option Minute, Heure, Jour, Semaine, Mois, Trimestre ou Année. |
| | Aligner les dates | Sélectionnez cette option pour harmoniser les dates de chaque colonne afin qu’elles commencent toutes à partir de la même ligne. |
| **[Colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Renvoyer à la ligne le texte d’en-tête | Permet de renvoyer à la ligne le texte de l’en-tête dans les tableaux à structure libre afin de rendre les en-têtes plus lisibles et les tableaux plus faciles à partager. Cette option est utile pour le rendu .pdf et pour les mesures dont le nom est long. Activé par défaut. |
| | Afficher les totaux | Ce total est généralement égal au [!UICONTROL Total général] ou est un sous-ensemble de ce dernier. Il reflète les filtres de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Inclure aucun]. |
| | Afficher les totaux généraux | Ce total représente tous les événements qui ont été collectés. Il est parfois appelé « total de la vue de données ». Lorsquʼun filtre est appliqué au niveau du panneau ou dans le tableau à structure libre, ce total sʼajuste pour refléter tous les événements qui correspondent aux critères de filtre. Le total général n’est pas pris en charge pour les tableaux ou les répartitions avec des [lignes statiques](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Afficher les graphiques sparkline | Afficher ou masquer les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
| | Nombre | Détermine si une cellule affiche/masque la valeur numérique pour la mesure. Par exemple, si la mesure est Pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
| | Pourcentage | Détermine si une cellule affiche/masque la valeur de pourcentage pour la mesure. Par exemple, si la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne.  Remarque : Nous pouvons désormais afficher les pourcentages supérieurs à 100 %, pour plus de précision. Nous avons également rehaussé le plafond supérieur à 1 000 % afin de garantir que les colonnes puissent s’adapter à une largeur trop importante. |
| | Afficher les anomalies <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Détermine si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
| | Afficher les prévisions | Détermine si les valeurs de prévision sont affichées automatiquement pour la première colonne de mesures dans un tableau à structure libre de série temporelle que vous créez. |
| | Interpréter zéro comme n’étant pas une valeur | Pour les cellules dont la valeur est 0, détermine s’il convient d’afficher un 0 ou une cellule vierge. Ce paramètre est utile lorsque vous examinez les données pour chaque jour d’un mois et que certains jours n’ont pas encore eu lieu.  Des cellules vierges peuvent être affichées au lieu de 0 pour les dates futures. Les diagrammes respectent également ce paramètre (c.-à-d. qu’ils n’affichent pas une ligne ou une barre avec des valeurs 0 lorsque ce paramètre est activé). |
| | Contexte | Détermine si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique en barres et la mise en forme conditionnelle. <ul><li>Graphique en barres</li> Affiche un graphique en barres horizontal représentant la valeur de la cellule par rapport au total de la colonne. <li>Mise en forme conditionnelle</li>Pour plus d’informations sur la mise en forme conditionnelle, consultez « Mise en forme conditionnelle » dans [Paramètres de colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).</ul> |
| | Aperçu de la cellule | Affiche un aperçu de l’aspect de chaque cellule après application des options de mise en forme actuellement sélectionnées. |
| **[Ligne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Répartition par position | Sélectionnez cette option si vous souhaitez que la répartition conserve la position de l’élément plutôt que l’élément lui-même. Pour plus d’informations sur les répartitions, consultez [Répartition des dimensions](/help/components/dimensions/t-breakdown-fa.md). |
| | Calcul du pourcentage | <ul><li>Colonne</li><li>Ligne</li></ul> |
| | Totaux des colonnes (lignes statiques uniquement) | <ul><li>Afficher la somme des lignes : affiche la somme des éléments de ligne individuels. </li><li>Afficher le total général : affiche la somme dédupliquée des lignes.</li></ul> |

### Préférences de visualisation

Vous pouvez mettre à jour les préférences de visualisation pour tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des visualisations individuelles.

Sélectionnez les titres des sections liées pour plus d’informations et de contexte sur les préférences disponibles.

| Section | Préférence | Options |
| --- | --- | --- |
| **Valeurs par défaut générales** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour toutes les visualisations. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour toutes les visualisations. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X pour toutes les visualisations. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| | Afficher l’axe double (le cas échéant) | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| | Normalisation (le cas échéant) | Force les mesures en proportions égales. Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| | Ancrer l’axe Y sur zéro | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |
| | Ancre des anomalies à l’échelle de l’axe Y | L’axe des ordonnées est mis à l’échelle à l’aide de valeurs d’anomalie. |
| **[Ligne](/help/analysis-workspace/visualizations/line.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Ligne. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Ligne. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Ligne. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| | Afficher l’axe double (le cas échéant) | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| | Normalisation (le cas échéant) | Force les mesures en proportions égales. Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
| | Afficher l’axe X | Affiche l’axe X sur le graphique en courbes. |
| | Afficher l’axe Y | Affiche l’axe Y sur le graphique en courbes. |
| | Ancrer l’axe Y | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |
| | Autoriser les anomalies à mettre à l’échelle l’axe Y | Si un graphique comporte plusieurs mesures, vous devez pointer sur chaque anomalie pour afficher la marge de confiance correspondante. Pour rendre la visualisation plus lisible, l’intervalle de confiance Détection des anomalies ne met pas automatiquement à l’échelle l’axe Y. Cette option permet à l’intervalle de confiance de mettre la visualisation à l’échelle. <p>Pour plus d’informations, consultez [Affichage des anomalies dans Analysis Workspace](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| | Autoriser les prévisions à l’échelle de l’axe Y | Si les valeurs des prévision se situent en dehors des limites supérieure et inférieure des valeurs historiques, l’axe Y n’est pas automatiquement mis à l’échelle pour ces valeurs prévisionnelles. Lorsqu’elle est activée, cette option met correctement à l’échelle l’axe Y pour les valeurs prévues. |
| | Afficher la valeur minimale | Superposez un libellé de valeur minimale pour mettre rapidement en surbrillance les creux d’une mesure. Remarque : les valeurs minimales sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension. |
| | Afficher la valeur maximale | Superposez un libellé de valeur maximale pour mettre rapidement en surbrillance les pics d’une mesure. Remarque : les valeurs maximales sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension. |
| | Afficher la courbe de tendance | Affichez une courbe de tendance de régression ou de moyenne glissante sur votre série de lignes. Les courbes de tendance permettent d’illustrer plus clairement un schéma dans les données. |
| **[Cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularité | Pour les visualisations de tendances, vous pouvez modifier la granularité temporelle (Jour, Semaine, Mois, Trimestre ou Année). Cette modification sʼapplique également au tableau de source de données. |
| | Afficher uniquement le pourcentage | Supprime la valeur numérique et affiche uniquement le pourcentage. |
| | Arrondir le pourcentage à l’entier le plus proche | Arrondit la valeur de pourcentage à l’entier le plus proche au lieu d’afficher la valeur décimale. |
| | Afficher la ligne en pourcentage moyen | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |
| **[Graphiques combinés](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Afficher l’axe X | Affiche l’axe X sur le graphique combiné. |
| | Afficher l’axe Y | Affiche l’axe Y sur le graphique combiné. |
| | Afficher les barres à disques sur les lignes | Affiche les barres à disques sur les lignes des graphiques combinés. |
| **[Résumé des mesures clés](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | Type d’affichage du résumé | <ul><li>Mettre en gras le pourcentage de modification</li><li>Mettre en gras la valeur numérique</li></ul> |
| | Afficher les graphiques sparkline | Affichez ou masquez les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
| | Afficher les valeurs minimales et maximales sur les graphiques sparkline | Affichez les valeurs minimales et maximales sur les graphiques en courbes principaux et de comparaison. |
| | Afficher la comparaison | Affichez les données de comparaison. Lorsqu’ils sont masqués, les objets de modification de graphique en courbes de comparaison et de modification de synthèse sont hors de vue. |
| | Options de valeur numérique | Dans la section [!UICONTROL **Résumé des mesures clés**] <ul><li>Afficher le pourcentage de modification</li><li>Afficher la différence brute</li>Différence brute entre la valeur totale de la mesure dans la période principale et la période secondaire</ul> |
| **[Abandon](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Conteneur | Permet de basculer entre **[!UICONTROL Session]** et **[!UICONTROL Personne]** pour analyser le cheminement de la personne. La valeur par défaut est **[!UICONTROL Person]**. Ces paramètres permettent de comprendre l’engagement des personnes au niveau des personnes (sur les sessions) ou de contraindre l’analyse à une seule session. <p>Les options disponibles sont les suivantes :</p> <ul><li>Session</li><li>Personne</li></ul> |
| **[Flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Conteneur | Dans la section [!UICONTROL **Flux**] <ul><li>Session</li><li>Personne</li></ul> |
| | Développer les étiquettes | Habituellement, les étiquettes sur les éléments de flux sont tronquées pour gagner de l’espace à l’écran, mais vous pouvez afficher l’étiquette complète en cochant cette case. Valeur par défaut = non coché. |
| | Inclure des instances de répétition | Les visualisations de flux sont basées sur des instances d’une dimension. Ce paramètre vous donne la possibilité d’inclure ou d’exclure des instances de répétition, telles que des rechargements de page. Toutefois, les répétitions ne peuvent pas être supprimées des visualisations de flux qui incluent des dimensions à valeurs multiples, comme des listVars, listProps, s.product, eVars de marchandisage, etc. Valeur par défaut = non coché. |
| | Afficher les infobulles | Détermine si les infobulles contenant les données de nœud s’affichent lorsque vous survolez les nœuds individuels dans une visualisation de flux. |
| | Nombre de colonnes | Détermine le nombre de colonnes souhaité dans le diagramme Flux. |
| | Éléments développés par colonne | Nombre d’éléments à inclure dans chaque colonne. |
| **Graphiques empilés** | | |
| | 100 % empilé | Ce paramètre appliqué aux graphiques à zones empilées, à barres empilées ou à barres horizontales empilées offre un aperçu « 100 % empilé » du diagramme. <p>Pour plus d’informations, consultez [Barres et barres empilées](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogramme](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Nombre d’intervalles | Sélectionnez le nombre de plages de données (intervalles) dans la visualisation. Il ne peut pas y avoir plus de 50 intervalles. <p>Pour plus d’informations, consultez [Histogramme](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Méthode de comptage | Choisissez l’une des options suivantes : <ul><li>Accès</li><li>Session</li><li>Personne</li></ul> <p>Par exemple, lorsque vous l’utilisez conjointement avec les pages vues, vous pouvez choisir les pages vues par personne, les pages vues par visite ou les pages vues par événement. Pour l’accès, la mesure « Occurrences » est utilisée comme mesure de l’axe Y dans un tableau à structure libre.</p> |
| **[Synthèse des modifications](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valeur | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Changement en pourcentage</li><li>Différence brute</li></ul> |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Synthèse des modifications. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des modifications. |
| **[Synthèse des chiffres](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Synthèse des chiffres. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des chiffres. |
| | Synthèse des valeurs par | Choisissez parmi Max, Min, Moyenne, Médiane et Somme. |
| | Abréger la valeur | Dans la section [!UICONTROL **Synthèse des chiffres**] |
| **[Treemap](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Treemap. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Treemap. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Venn. |
| **[Dispersion](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Dispersion. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Dispersion. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Dispersion. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| | Ancrer l’axe Y sur zéro | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |

## Restaurer les préférences par défaut

Vous pouvez restaurer toutes vos préférences utilisateur aux valeurs par défaut du système. Cela n’a aucune incidence sur les préférences de l’administrateur sous l’onglet Société.

Cette action ne peut pas être annulée.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Components**] **>** [!UICONTROL **Preferences**] dans le menu supérieur. Ou sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Paramètres utilisateur]** dans le menu Workspace.

1. Dans le coin supérieur droit, sélectionnez **[!UICONTROL Restaurer les valeurs par défaut]**.

1. Sélectionnez **[!UICONTROL Restaurer les paramètres par défaut]** dans **[!UICONTROL Restaurer les paramètres par défaut du système]**, .

## [!UICONTROL Thème sombre]

Si vous préférez afficher un arrière-plan sombre pour votre interface utilisateur de Customer Journey Analytics, vous pouvez activer le [!UICONTROL Thème sombre].

1. Sélectionnez l’icône utilisateur Experience Cloud en haut à droite.

   ![thème-sombre](assets/dark-theme.png)

1. Activez **[!UICONTROL Thème sombre]**.

