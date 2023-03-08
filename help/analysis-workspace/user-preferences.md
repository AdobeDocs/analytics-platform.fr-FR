---
title: Comment définir les préférences utilisateur dans Analysis Workspace
description: Vous pouvez définir des préférences générales et des préférences du projet pour les utilisateurs.
feature: CJA Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
source-git-commit: 0c41c5a4c79105520f6f98e9e9ea60f19befd608
workflow-type: tm+mt
source-wordcount: '2928'
ht-degree: 84%

---

# Préférences de l’utilisateur

Vous pouvez gérer les paramètres d’Analysis Workspace et ses composants connexes pour tous les nouveaux projets ou panneaux que vous créez. Les projets et panneaux existants ne sont pas affectés.

## Préférences de mise à jour

1. Dans Customer Journey Analytics, accédez à la page de destination [!UICONTROL **Projet**], puis sélectionnez [!UICONTROL **Préférences**].

   ![Préférences utilisateur](assets/user-preferences.png)

1. Pour plus d’informations sur les préférences disponibles sur chaque onglet, reportez-vous aux sections suivantes de cet article :

   * [Préférences générales](#general-preferences)

   * [Préférences du projet](#project-preferences)

   * [Préférences du tableau à structure libre](#freeform-table-preferences)

   * [Préférences de visualisation](#visualizations-preferences)

## Préférences générales

Les préférences générales sʼappliquent à votre expérience Customer Journey Analytics dans le navigateur.

| Préférence | Options |
| --- | --- |
| Page de destination | Choisissez la page qui s’affiche par défaut lorsque vous accédez à Adobe Analytics : <ul><li>Liste des projets (par défaut)</li><li>Projet vierge</li><li>Projet spécifique     sélectionné dans une liste</li></ul> |
| Afficher les conseils | Affiche les conseils dans un cadre bleu de la zone inférieure droite d’Analysis Workspace. <p>Cette option est activée par défaut.</p> |
| Composants affichés dans les groupes du rail de gauche | Choisissez le nombre de chaque composant à afficher dans le menu Composants du rail de gauche. <p>Si vous choisissez 0, le composant n’est plus accessible à partir du rail de gauche de vos espaces de travail.</p><p>Par défaut, 5 composants sont affichés pour chacun des éléments suivants :</p> <ul><li>Dimensions</li><li>Mesures</li><li>Filtres</li><li>Périodes</li></ul> <p>Pour plus d’informations sur les composants dans Analysis Workspace, consultez [Présentation des composants](/help/components/overview.md).</p> |

## Préférences du projet

Vous pouvez personnaliser les préférences du projet de tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des projets individuels, comme décrit dans la section [Présentation des projets](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

Cliquez sur les titres des préférences liées pour plus d’informations et de contexte sur chaque préférence.

| Section | Préférence | Options |
| --- | --- | --- |
| **Afficher** |  |  |
|  | [Afficher la densité](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=fr) | Sélectionnez le contenu à afficher à l’écran en réduisant l’espacement vertical du rail de gauche, des tableaux à structure libre et des tableaux de cohortes. <ul><li>Compact</li><li>Confortable</li><li>Développé (par défaut)</li></ul> |
|  | [Palette de couleurs](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=fr) | Sélectionnez la palette de couleurs de visualisation utilisée dans Analysis Workspace. <ul><li>Palettes fournies par Adobe (par défaut)</li><li>Palette de mise en forme conditionnelle </li><li>Palette haut/bas (diverge)<li>Palettes personnalisées</li></ul> |
| **Data** (Données) |  |  |
|  | [Suite de rapports](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr#report-suite) | Choisissez l’emplacement où les tableaux et les visualisations obtiennent leurs données. <ul><li>La plus récente (par défaut)</li><li>Suite de rapports spécifique sélectionnée dans une liste</li></ul> |
|  | [Calendrier](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr#calendar) | Effectuez une sélection dans une liste de : <ul><li>Plages fournies par Adobe (par défaut, ce mois-ci)</li><li>Plages personnalisées</li></ul> |
|  | [Type de panneau](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=fr) | <ul><li>À structure libre (par défaut)</li><li>Vide</li><li>Aperçu rapide</li></ul> |
|  | Compter les instances répétées | Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports. Par exemple, lorsqu’il est activé, ce paramètre traite plusieurs pages vues consécutives sur la même page comme plusieurs pages vues. Lorsque ce paramètre est désactivé, elles sont comptabilisées comme une seule page vue. <p>**Remarque :** ce paramètre affecte uniquement certaines mesures (telles que Visites de page unique) et ne s’applique pas aux visualisations Flux ou Abandons.</p> |
|  | Format du nombre | <ul><li>1 000,00 (par défaut)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Séparateur CSV     caractère | <ul><li>Virgule (par défaut)</li><li>Point-virgule</li><li>Deux-points</li><li>Tube</li><li>Point</li><li>un espace</li><li>Tabulation</li></ul> |
|  | Afficher les annotations | Indiquez si les annotations sont visibles dans les projets. Pour plus d’informations sur les annotations, consultez [Présentation des annotations](/help/components/annotations/overview.md). |


## Préférences du tableau à structure libre

Vous pouvez personnaliser les préférences du tableau à structure libre pour tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des tableaux individuels.

Cliquez sur les titres des sections liées pour plus d’informations et de contexte sur les préférences disponibles.

| Section | Préférence | Options |
| --- | --- | --- |
| **Tableau** |  |  |
|  | Type de tableau | <ul><li>Structure libre</li><li>Créateur de tableaux</li></ul> |
|  | Mesure par défaut du tableau | <ul><li>Occurrences</li><li>Visiteurs uniques</li><li>Visites</li></ul> |
|  | Dimension du tableau par défaut | Sélectionnez l’option Minute, Heure, Jour, Semaine, Mois, Trimestre ou Année. |
|  | Aligner les dates | Sélectionnez cette option pour harmoniser les dates de chaque colonne afin qu’elles commencent toutes à partir de la même ligne. |
| **[Colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** |  |  |
|  | Renvoyer à la ligne le texte d’en-tête | Permet de renvoyer à la ligne le texte de l’en-tête dans les tableaux à structure libre afin de rendre les en-têtes plus lisibles et les tableaux plus faciles à partager. Cette option est utile pour le rendu .pdf et pour les mesures dont le nom est long. Activé par défaut. |
|  | Afficher les totaux | Ce total est généralement égal au [!UICONTROL Total général] ou est un sous-ensemble de ce dernier. Il reflète les filtres de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Inclure aucun]. |
|  | Afficher les totaux généraux | Ce total représente tous les accès qui ont été collectés. Il est parfois appelé « total de la suite de rapports ». Lorsqu’un segment est appliqué au niveau du panneau ou dans le tableau à structure libre, ce total s’ajuste pour refléter tous les accès qui correspondent aux critères de segment. Le total général n’est pas pris en charge pour les tableaux ou les ventilations avec des [lignes statiques](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
|  | Afficher les graphiques sparkline | Afficher ou masquer les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
|  | Nombre | Détermine si une cellule affiche/masque la valeur numérique pour la mesure. Par exemple, si la mesure est Pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
|  | Pourcentage | Détermine si une cellule affiche/masque la valeur de pourcentage pour la mesure. Par exemple, si la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne.  Remarque : Nous pouvons désormais afficher les pourcentages supérieurs à 100 %, pour plus de précision. Nous avons également rehaussé le plafond supérieur à 1 000 % afin de garantir que les colonnes puissent s’adapter à une largeur trop importante. |
|  | Afficher les anomalies <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Détermine si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
|  | Interpréter zéro comme n’étant pas une valeur | Pour les cellules dont la valeur est 0, détermine s’il convient d’afficher un 0 ou une cellule vierge. Ce paramètre est utile lorsque vous examinez les données pour chaque jour d’un mois et que certains jours n’ont pas encore eu lieu.  Des cellules vierges peuvent être affichées au lieu de 0 pour les dates futures. Les diagrammes respectent également ce paramètre (c.-à-d. qu’ils n’affichent pas une ligne ou une barre avec des valeurs 0 lorsque ce paramètre est activé). |
|  | Contexte | Détermine si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique en barres et la mise en forme conditionnelle. <ul><li>Graphique en barres</li> Affiche un graphique en barres horizontal représentant la valeur de la cellule par rapport au total de la colonne. <li>Mise en forme conditionnelle</li>Pour plus d’informations sur la mise en forme conditionnelle, consultez « Mise en forme conditionnelle » dans [Paramètres de colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).</ul> |
|  | Aperçu de la cellule | Affiche un aperçu de l’aspect de chaque cellule après application des options de mise en forme actuellement sélectionnées. |
| **[Ligne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** |  |  |
|  | Ventilation par position | Sélectionnez cette option si vous souhaitez que la ventilation conserve la position de l’élément plutôt que l’élément lui-même. Pour plus d’informations sur les ventilations, consultez [Ventilation des dimensions](/help/components/dimensions/t-breakdown-fa.md). |
|  | Calcul du pourcentage | <ul><li>Colonne</li><li>Ligne</li></ul> |

## Préférences de visualisation

Vous pouvez mettre à jour les préférences de visualisation pour tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des visualisations individuelles.

Cliquez sur les titres des sections liées pour plus d’informations et de contexte sur les préférences disponibles.

| Section | Préférence | Options |
| --- | --- | --- |
| **Valeurs par défaut générales** |  |  |
|  | Pourcentages | Affiche les valeurs en pourcentages pour toutes les visualisations. |
|  | Légende visible | Permet de masquer le texte de légende détaillé pour toutes les visualisations. |
|  | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X pour toutes les visualisations. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
|  | Afficher l’axe double (le cas échéant) | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
|  | Normalisation (le cas échéant) | Force les mesures en proportions égales. Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
|  | Ancrer l’axe Y sur zéro | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |
|  | Autoriser les anomalies à mettre à l’échelle l’axe Y | Si un graphique comporte plusieurs mesures, vous devez pointer sur chaque anomalie pour afficher la marge de confiance correspondante. Pour rendre la visualisation plus lisible, l’intervalle de confiance Détection des anomalies ne met pas automatiquement à l’échelle l’axe Y. Cette option permet à l’intervalle de confiance de mettre la visualisation à l’échelle. <p>Pour plus d’informations, consultez [Affichage des anomalies dans Analysis Workspace](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md).</p> |
| **[Ligne](/help/analysis-workspace/visualizations/line.md)** |  |  |
|  | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Ligne. |
|  | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Ligne. |
|  | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Ligne. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
|  | Afficher l’axe double (le cas échéant) | S’applique seulement s’il existe deux mesures : vous pouvez afficher un axe des ordonnées sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
|  | Normalisation (le cas échéant) | Force les mesures en proportions égales. Cela sʼavère utile lorsque les mesures tracées présentent des dimensions très différentes. |
|  | Afficher l’axe X | Affiche l’axe X sur le graphique en courbes. |
|  | Afficher l’axe Y | Affiche l’axe Y sur le graphique en courbes. |
|  | Ancrer l’axe Y | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |
|  | Afficher la valeur minimale | Superposez un libellé de valeur minimale pour mettre rapidement en surbrillance les creux d’une mesure. Remarque : les valeurs minimales sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension. |
|  | Afficher la valeur maximale | Superposez un libellé de valeur maximale pour mettre rapidement en surbrillance les pics d’une mesure. Remarque : les valeurs maximales sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension. |
|  | Afficher la courbe de tendance | Affichez une courbe de tendance de régression ou de moyenne glissante sur votre série de lignes. Les courbes de tendance permettent d’illustrer plus clairement un schéma dans les données. |
| **[Cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** |  |  |
|  | Granularité | Pour les visualisations de tendances, vous pouvez modifier la granularité temporelle (Jour, Semaine, Mois, Trimestre ou Année). Cette modification sʼapplique également au tableau de source de données. |
|  | Afficher uniquement le pourcentage | Supprime la valeur numérique et affiche uniquement le pourcentage. |
|  | Arrondir le pourcentage à l’entier le plus proche | Arrondit la valeur de pourcentage à l’entier le plus proche au lieu d’afficher la valeur décimale. |
|  | Afficher la ligne en pourcentage moyen | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |
|  | Aperçu des cohortes | Un aperçu de la façon dont la palette de couleurs apparaît dans la visualisation de cohorte. |
|  | Palette de cohortes | Palette de couleurs utilisée dans la visualisation de cohorte. |
| **[Graphiques combinés](/help/analysis-workspace/visualizations/combo-charts.md)** |  |  |
|  | Afficher l’axe X | Affiche l’axe X sur le graphique combiné. |
|  | Afficher l’axe Y | Affiche l’axe Y sur le graphique combiné. |
|  | Afficher les barres à disques sur les lignes | Affiche les barres à disques sur les lignes des graphiques combinés. |
| **[Résumé des mesures clés](/help/analysis-workspace/visualizations/key-metric.md)** |  |  |
|  | Type d’affichage du résumé | <ul><li>Mettre en gras le pourcentage de modification</li><li>Mettre en gras la valeur numérique</li></ul> |
|  | Afficher les graphiques sparkline | Affichez ou masquez les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
|  | Afficher les valeurs minimales et maximales sur les graphiques sparkline | Affichez les valeurs minimales et maximales sur les graphiques en courbes principaux et de comparaison. |
|  | Afficher la comparaison | Affichez les données de comparaison. Lorsqu’ils sont masqués, les objets de modification de graphique en courbes de comparaison et de modification de synthèse sont hors de vue. |
|  | Options de valeur numérique | Dans la section [!UICONTROL **Résumé des mesures clés**] <ul><li>Afficher le pourcentage de modification</li><li>Afficher la différence brute</li>Différence brute entre la valeur totale de la mesure dans la période principale et la période secondaire</ul> |
| **[Abandon](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** |  |  |
|  | Conteneur | Permet de basculer entre Visite et Visiteur afin d’analyser le cheminement du visiteur. La valeur par défaut est Visiteur. Ces paramètres permettent de comprendre l’engagement des visiteurs au niveau des visiteurs (à l’échelle de toutes visites) ou de contraindre l’analyse à une seule visite. <p>Les options disponibles sont les suivantes :</p> <ul><li>Visite</li><li>Visiteur</li></ul> |
| **[Flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** |  |  |
|  | Conteneur | Dans la section [!UICONTROL **Flux**] <ul><li>Visite</li><li>Visiteur</li></ul> |
|  | Développer les étiquettes | Habituellement, les étiquettes sur les éléments de flux sont tronquées pour gagner de l’espace à l’écran, mais vous pouvez afficher l’étiquette complète en cochant cette case. Valeur par défaut = non coché. |
|  | Inclure des instances de répétition | Les visualisations de flux sont basées sur des instances d’une dimension. Ce paramètre vous donne la possibilité d’inclure ou d’exclure des instances de répétition, telles que des rechargements de page. Toutefois, les répétitions ne peuvent pas être supprimées des visualisations de flux qui incluent des dimensions à valeurs multiples, comme des listVars, listProps, s.product, eVars de marchandisage, etc. Valeur par défaut = non coché. |
|  | Afficher les infobulles | Détermine si les infobulles contenant les données de nœud s’affichent lorsque vous survolez les nœuds individuels dans une visualisation de flux. |
|  | Nombre de colonnes | Détermine le nombre de colonnes souhaité dans le diagramme Flux. |
|  | Éléments développés par colonne | Nombre d’éléments à inclure dans chaque colonne. |
| **Graphiques empilés** |  |  |
|  | 100 % empilé | Ce paramètre appliqué aux graphiques à zones empilées, à barres empilées ou à barres horizontales empilées offre un aperçu « 100 % empilé » du diagramme. <p>Pour plus d’informations, consultez [Barres et barres empilées](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogramme](/help/analysis-workspace/visualizations/histogram.md)** |  |  |
|  | Nombre d’intervalles | Sélectionnez le nombre de plages de données (intervalles) dans la visualisation. Il ne peut pas y avoir plus de 50 intervalles. <p>Pour plus d’informations, consultez [Histogramme](/help/analysis-workspace/visualizations/histogram.md).</p> |
|  | Méthode de comptage | Choisissez l’une des options suivantes : <ul><li>Accès</li><li>Visite</li><li>Visiteur</li></ul> <p>Par exemple, lorsque vous l’utilisez conjointement avec les pages vues, vous pouvez choisir les pages vues par visiteur, les pages vues par visite ou les pages vues par accès. Pour l’accès, la mesure « Occurrences » est utilisée comme mesure de l’axe Y dans un tableau à structure libre.</p> |
| **[Synthèse des modifications](/help/analysis-workspace/visualizations/summary-number-change.md)** |  |  |
|  | Valeur | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Changement en pourcentage</li><li>Différence brute</li></ul> |
|  | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Synthèse des modifications. |
|  | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des modifications. |
| **[Synthèse des chiffres](/help/analysis-workspace/visualizations/summary-number-change.md)** |  |  |
|  | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Synthèse des chiffres. |
|  | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des chiffres. |
|  | Synthèse des valeurs par | Choisissez parmi Max, Min, Moyenne, Médiane et Somme. |
|  | Abréger la valeur | Dans la section [!UICONTROL **Synthèse des chiffres**] |
| **[Treemap](/help/analysis-workspace/visualizations/treemap.md)** |  |  |
|  | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Treemap. |
|  | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Treemap. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** |  |  |
|  | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Venn. |
| **[Dispersion](/help/analysis-workspace/visualizations/scatterplot.md)** |  |  |
|  | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Dispersion. |
|  | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Dispersion. |
|  | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Dispersion. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
|  | Ancrer l’axe Y sur zéro | Si toutes les valeurs mappées dans le graphique sont considérablement supérieures à zéro, le seuil de l’axe des ordonnées est par défaut NON NUL. Si cette option est activée, l’axe des ordonnées est obligatoirement ancré à zéro (et le graphique est retracé). |

## Préférences de l’entreprise

>[!AVAILABILITY]
>
>La fonctionnalité Liens d’accès public décrite dans cette section est dans la phase Tests limités de la version et peut ne pas être encore disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).

Vous pouvez mettre à jour les préférences de l’entreprise qui s’appliquent à tous les utilisateurs et projets de votre entreprise. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

| Section | Préférence | Options |
| --- | --- | --- |
| **Liens d’accès public** <!-- Double check the names of all these settings for what they are actually called --> |  |  |
|  | Désactiver tous les liens d’accès public | <p>Désactive tous les liens d’accès public existants et empêche les utilisateurs de votre entreprise de créer de nouveaux liens. Cela signifie que les utilisateurs ne peuvent pas partager des projets Analysis Workspace avec des personnes qui n’ont pas de compte Adobe Customer Journey Analytics. Les utilisateurs peuvent partager des projets uniquement avec d’autres utilisateurs Customer Journey Analytics de votre entreprise.</p> <p>Lorsque les liens publics sont désactivés :</p> <ul><li><p>Les utilisateurs ne peuvent pas créer de liens d’accès publics</p><p>L’option &quot;Partager le lien public&quot; est supprimée du menu Partager . Cela signifie que les utilisateurs ne peuvent plus partager de projets avec des personnes qui n’ont pas de compte Analysis Workspace dans votre organisation, comme décrit dans la section [Partager un lien public avec quiconque (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Partage de projets](/help/analysis-workspace/curate-share/share-projects.md).</p></li> <li><p>Tous les liens publics existants sont désactivés.</p></li><p>Si les liens publics sont désactivés puis réactivés, tous les liens désactivés précédemment ne sont pas automatiquement réactivés. Dans ce cas, les utilisateurs doivent les réactiver manuellement pour chaque projet à partir de la boîte de dialogue Partager le projet .</p> |
|  | Identification de l’Experience Cloud requise | <p>Lorsque cette option est activée, seuls les destinataires disposant d’un identifiant fédéré et pouvant se connecter à Adobe Experience Cloud peuvent accéder aux liens publics partagés.</p> <p>Une fois cette option activée, chaque fois qu’un utilisateur crée un lien vers un projet Analysis Workspace, l’option &quot;Exiger une authentification Experience Cloud&quot; est activée dans la boîte de dialogue de partage et elle ne peut pas être désactivée par l’utilisateur qui partage le lien. (Pour plus d’informations sur la manière dont les utilisateurs peuvent partager des projets avec des utilisateurs en dehors de l’entreprise, voir [Partager un lien public avec quiconque (aucune connexion requise)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Partage de projets](/help/analysis-workspace/curate-share/share-projects.md).)</p> <p>Tenez compte des points suivants lors de l’activation de cette option :</p><ul><li><p>Lorsque vous activez cette option, tous les liens publics actuellement principaux pour lesquels Experience Cloud n’est pas activé sont désactivés.</p></li> <li><p>Si cette option est activée puis désactivée ultérieurement, tous les liens désactivés précédemment ne sont pas automatiquement réactivés. Dans ce cas, les utilisateurs doivent les réactiver manuellement à partir de la boîte de dialogue Partager le projet .</p></li> <li><p>Cette option est disponible uniquement si SSO est implémenté dans votre entreprise. Pour plus d’informations sur la manière dont les administrateurs système peuvent activer l’authentification unique pour votre entreprise, voir [Configuration de l’identité et de l’authentification unique](https://helpx.adobe.com/fr/enterprise/using/set-up-identity.html){target=_blank}.</p><p>Si l’authentification unique est configurée pour votre organisation, vérifiez si un type de création de compte automatique est implémenté dans la console. En règle générale, un administrateur système configure cette configuration, comme décrit dans la section [Activation de la création automatique de compte](https://helpx.adobe.com/enterprise/using/automatic-account-creation.html){target=_blank}.</p></li><li><p>Si votre entreprise fait partie d’un secteur qui nécessite la conformité HIPAA, cette option est automatiquement activée et ne peut pas être désactivée.</p></li></ul> |

{style="table-layout:auto"}

## Restaurer les préférences par défaut

Vous pouvez restaurer toutes vos préférences utilisateur aux valeurs par défaut du système. Cela n’a aucune incidence sur les préférences de l’administrateur sous l’onglet Société.

Cette action ne peut pas être annulée.

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] **>** [!UICONTROL **Préférences**].

   ![Préférences utilisateur](assets/user-preferences.png)

1. Dans le coin supérieur droit, sélectionnez **[!UICONTROL Restaurer les valeurs par défaut]**.

1. Lorsque vous y êtes invité, sélectionnez **[!UICONTROL Restaurer les valeurs par défaut]**.

## [!UICONTROL Thème sombre]

Si vous préférez afficher un arrière-plan sombre pour votre interface utilisateur dʼAdobe Analytics, vous pouvez activer le [!UICONTROL Thème sombre].

1. Cliquez sur lʼicône dʼutilisateur dʼExperience Cloud en haut à droite.

   ![thème-sombre](assets/dark-theme.png)

1. Déplacez le bouton bascule du **[!UICONTROL Thème sombre]** vers la droite.

