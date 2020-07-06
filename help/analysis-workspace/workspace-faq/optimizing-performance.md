---
description: valeur nulle
title: Optimisation des performances d’Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 98%

---


# Optimisation des performances d’Analysis Workspace

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

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

En outre, l’utilisation de [classifications](https://docs.adobe.com/content/help/fr-FR/analytics/components/classifications/c-classifications.translate.html) peut contribuer à consolider de nombreuses valeurs en groupes concis à partir desquels vous pouvez créer des segments. La segmentation appliquée aux groupes de classifications optimise les performances par rapport aux segments qui contiennent de nombreuses instructions OR ou de critères « contains ».

## Plage de données demandée

La plage de données demandée lors d’un projet influence les performances d’Analysis Workspace.

**Bonnes pratiques pour la période**

Si possible, n’extrayez que les données dont vous avez besoin.

N’oubliez pas que les plages de dates (composants violets) sont prioritaires sur la plage de dates du panneau. Si, par conséquent, vous utilisez d’autres plages de dates comme colonnes (par exemple, le mois dernier, la semaine dernière et hier), la plage de dates du panneau n’a pas à couvrir toutes les plages de dates des colonnes. Il suffit qu’elle soit définie sur « hier », puisque les plages de données utilisées dans le tableau à structure libre ont priorité sur celles du panneau. Pour en savoir plus sur l’utilisation des plages de dates dans Analysis Workspace, [regardez cette vidéo](https://www.youtube.com/watch?v=ybmv6EBmhn0).

Utilisez les [options de comparaison des dates](/help/components/date-ranges/time-comparison.md) pour extraire et comparer les données de périodes spécifiques. Si, par exemple, vous devez comparer les données du mois dernier à celles du même mois l’année précédente, utilisez simplement l’option de comparaison des périodes pour afficher les performances d’une année sur l’autre, plutôt que de définir les 13 derniers mois de données dans le panneau.

## Nombre de visualisations

Le nombre de visualisations graphiques contenues dans un projet affecte la réactivité globale d’Analysis Workspace.

**Bonne pratique pour le nombre de visualisations**

Réduisez le nombre de visualisations dans votre projet. Pour chaque visuel que vous ajoutez, Analysis Workspace exécute un traitement conséquent en arrière-plan. Par conséquent, donnez la priorité aux visuels les plus importants pour l’utilisateur du rapport et, si nécessaire, répartissez les visuels connexes dans un projet distinct plus détaillé.

## Complexité des visualisations (segments, mesures, filtres)

Le type de visualisation (abandons ou tableau à structure libre) ajouté à un projet n’a pas de réelle incidence sur les performances du projet. Le temps de traitement dépend de la complexité de la visualisation. Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :

* Plage de données demandée, comme mentionné ci-dessus
* Nombre de segments appliqués ; par exemple, les segments utilisés comme des lignes d’un tableau à structure libre
* Utilisation de segments complexes
* Lignes ou colonnes de postes statiques dans les tableaux de forme libre
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

Si vous devez ajouter de nombreux panneaux dans un Workspace, réduisez-les avant d’enregistrer et de partager le projet. Quand un projet est chargé, Analysis Workspace charge seulement le contenu correspondant aux panneaux développés. Les panneaux réduits ne sont pas chargés tant que l’utilisateur ne les développe pas. Cette approche présente deux avantages :

* le temps de chargement général d’un projet est optimisé ;
* grâce aux panneaux réduits, organisez vos projets de manière logique pour l’utilisateur du rapport.

## Taille de la suite de rapports

Même si la taille de la suite de rapports peut sembler être un facteur capital, son rôle en matière de performances du projet est en réalité mineur, en raison de la façon dont Adobe traite les données.

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
