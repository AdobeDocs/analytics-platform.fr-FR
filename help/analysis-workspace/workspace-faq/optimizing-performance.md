---
description: valeur nulle
title: Optimisation des performances d’Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: d49e07d14d1b202d9cc12f42d60083c052a1c364
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 85%

---


# Optimisation des performances d’Analysis Workspace

Certains facteurs peuvent influencer les performances d’un projet dans Analysis Workspace. Il convient de savoir quels sont ces facteurs avant de démarrer un projet, afin de planifier et d’élaborer le projet d’une manière optimale. Vous trouverez ci-dessous une liste des facteurs influençant les performances, ainsi que de bonnes pratiques pour optimiser vos projets. Adobe accorde une importance particulière aux performances d’Analysis Workspace et s’efforce continuellement de les améliorer.

## Complexité de la logique de segment

Des segments complexes peuvent avoir un impact significatif sur la performance des projets. Les facteurs qui ajoutent de la complexité à un segment (dans l’ordre décroissant d’impact) incluent les éléments suivants :

* Les opérateurs de type « contains », « contains any of », « matches », « starts with » ou « ends with »
* La segmentation séquentielle, en particulier lorsque des restrictions dimensionnelles (Within/After) sont utilisées
* Le nombre d’éléments de dimensions uniques dans les dimensions utilisées dans le segment (par exemple, Page = ’A’ lorsque Page comporte 10 éléments uniques sera plus rapide que Page = ’A’ lorsque la page a 100 000 éléments uniques)
* Le nombre de dimensions différentes utilisées (par exemple, Page = ’Home’ et Page = ’Search results’ seront plus rapides que eVar 1 = ’red’ et eVar 2 = ’blue’)
* Beaucoup d’opérateurs OR (au lieu de AND)
* Des contenants imbriqués dont la portée varie (par ex., « Hit inside of Visit inside of Visitor »)

**Bonnes pratiques pour la complexité logique**

Bien qu’il soit impossible d’éviter certains facteurs de complexité, pensez aux possibilités de réduire la complexité de vos segments. En général, plus vous pouvez être précis dans vos critères de segment, mieux c’est. Par exemple :

* Avec les conteneurs, l’utilisation d’un seul conteneur en haut du segment sera plus rapide qu’une série de conteneurs imbriqués
* Avec les opérateurs, « equals » sera plus rapide que « contains » et « equals any of » sera plus rapide que « contains any of »
* Avec de nombreux critères, les opérateurs AND seront plus rapides qu’une série d’opérateurs OR. Recherchez également des occasions de réduire plusieurs instructions OR en une seule instruction « equals any of »

En outre, l’utilisation de [classifications](https://docs.adobe.com/content/help/fr-FR/analytics/components/classifications/c-classifications.html) peut contribuer à consolider de nombreuses valeurs en groupes concis à partir desquels vous pouvez créer des segments. La segmentation appliquée aux groupes de classifications optimise les performances par rapport aux segments qui contiennent de nombreuses instructions OR ou de critères « contains ».

## Plage de données demandée

La plage de données demandée lors d’un projet influence les performances d’Analysis Workspace.

**Recommandations relatives aux plages de dates**

Si possible, n’extrayez que les données dont vous avez besoin. Limitez le calendrier du panneau aux dates appropriées pour votre analyse ou utilisez des composants de plage de dates (composants violets) dans vos tableaux à structure libre. Les plages de dates utilisées dans un tableau remplacent la plage de dates du panneau. Par exemple, vous pouvez ajouter le mois dernier, la semaine dernière et hier aux colonnes du tableau pour demander ces plages de données spécifiques. Pour en savoir plus sur l’utilisation des plages de dates dans Analysis Workspace, [regardez cette vidéo](https://www.youtube.com/watch?v=MIkT6FZ5gKk).

Réduire au minimum le nombre de comparaisons d&#39;une année à l&#39;autre utilisées dans le projet. Lorsqu’une comparaison d’une année à l’autre est calculée, elle examine l’ensemble des données de 13 mois entre les mois d’intérêt. Cela a le même impact que de modifier la plage de dates du panneau pour qu’elle dure 13 mois.

## Nombre de visualisations

Le nombre de visualisations contenues dans un projet aura une incidence sur la réactivité globale de l’Analysis Workspace. En effet, chaque visualisation, qu’il s’agisse d’un tableau ou d’un graphique, dispose d’une source de données qui doit être demandée.

**Bonne pratique pour le nombre de visualisations**

Réduisez le nombre de visualisations dans votre projet. Pour chaque visuel que vous ajoutez, Analysis Workspace exécute un traitement conséquent en arrière-plan. Par conséquent, donnez la priorité aux visuels les plus importants pour l’utilisateur du rapport et, si nécessaire, répartissez les visuels connexes dans un projet distinct plus détaillé.

## Complexité des visualisations (segments, mesures, filtres)

Le type de visualisation (abandons ou tableau à structure libre) ajouté à un projet n’a pas de réelle incidence sur les performances du projet. Le temps de traitement dépend de la complexité de la visualisation. Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :

* Plage de données demandée, comme mentionné ci-dessus
* Nombre de segments appliqués ; par exemple, les segments utilisés comme des lignes d’un tableau à structure libre
* Utilisation de segments complexes
* [Lignes ou colonnes de postes statiques dans les tableaux de forme libre](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html)
* Filtres appliqués aux lignes des tableaux à structure libre
* Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des segments

**Bonne pratique pour la complexité de la visualisation**

Si vos projets ne se chargent pas aussi rapidement que prévu, remplacez si possible certains segments par des eVars et des filtres.

Si vous utilisez constamment des segments et des mesures calculées pour les points de données importants dans le cadre de vos activités, envisagez d’améliorer votre mise en œuvre afin de capturer plus directement ces points de données. Envisagez d’utiliser un gestionnaire de balises tel qu’Adobe Experience Platform Launch et les règles de traitement d’Adobe pour faciliter et accélérer les modifications de la mise en œuvre. Pour mieux comprendre comment simplifier des segments complexes, reportez-vous à « Complexité de la logique de segment » ci-dessus.

## Nombre de panneaux

Un panneau peut contenir plusieurs visualisations et, par conséquent, le nombre de panneaux peut également influencer la réactivité globale d’Analysis Workspace.

**Bonne pratique pour le nombre de panneaux**

N’ajoutez rien à un projet. Créez plutôt des projets distincts ayant un objectif ou un groupe de participants spécifique. À l’aide des balises, classez les projets par thèmes clés et partagez avec les groupes de participants les projets connexes.

Si vous devez classer davantage les projets, vous pouvez [lier directement](https://www.youtube.com/watch?v=6IOEewflG2U) votre projet. Créez un index interne des projets, de sorte que les participants puissent facilement trouver ce qu’ils recherchent.

Si plusieurs panneaux sont nécessaires dans un projet, réduisez les panneaux avant d’enregistrer et de partager. Quand un projet est chargé, Analysis Workspace charge seulement le contenu correspondant aux panneaux développés. Les panneaux réduits ne sont pas chargés tant que l’utilisateur ne les développe pas. Cette approche présente deux avantages :

* le temps de chargement général d’un projet est optimisé ;
* grâce aux panneaux réduits, organisez vos projets de manière logique pour l’utilisateur du rapport.

## Taille de la suite de rapports

Même si la taille de la suite de rapports peut sembler être un facteur capital, son rôle en matière de performances du projet est en réalité mineur, en raison de la façon dont Adobe traite les données.  Il peut y avoir des exceptions à cette règle ; consultez votre équipe de mise en oeuvre ou un expert en Adobe pour déterminer si des améliorations peuvent être apportées à l’implémentation afin d’améliorer l’expérience globale dans Adobe Analytics.

## Nombre d’utilisateurs qui accèdent en même temps à Analysis Workspace

Le nombre d’utilisateurs accédant simultanément à Analysis Workspace ou à des projets spécifiques n’a aucune incidence importante sur les performances d’Analysis Workspace si les utilisateurs accèdent à différentes suites de rapports. Si des utilisateurs accèdent simultanément à la même suite de rapports, les performances sont affectées.

## Messages d’erreur courants dans Analysis Workspace

Vous pouvez rencontrer des erreurs au moment d’interagir avec Analysis Workspace. Les erreurs peuvent se produire pour plusieurs raisons. Les erreurs répertoriées ci-dessous sont les plus courantes.

| Message d’erreur | Quelle en est la raison ? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. Nous vous recommandons de répartir plus uniformément vos demandes et vos plannings pour la suite de rapports tout au long de la journée. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe rencontre un problème qui doit être résolu. Nous vous recommandons d’envoyer le code d’erreur en adressant une demande à l’assistance clientèle. |
| `The request is too complex.` | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les dépassements de délai en raison de la taille de la requête, du nombre trop élevé d’éléments correspondants dans un segment ou un filtre de recherche, du nombre trop élevé de mesures incluses, des combinaisons de dimensions et de mesures incompatibles, etc. Nous vous recommandons de simplifier votre requête. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Nous vous recommandons de limiter vos critères de texte de recherche et d’effectuer une nouvelle requête. |
| `This dimension does not currently support non-default attribution models.` | Nous vous recommandons de remplacer la dimension de votre tableau par une dimension compatible avec [Attribution IQ](../attribution/overview.md). |
| `Your request failed as a result of too many columns or pre-configured rows.` | Nous vous recommandons de supprimer certaines colonnes ou lignes ou de les diviser en visualisations distinctes. |
