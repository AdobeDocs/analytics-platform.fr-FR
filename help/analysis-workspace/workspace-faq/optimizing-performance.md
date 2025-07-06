---
description: Découvrez insight dans les facteurs qui affectent les performances d’Analysis Workspace et les optimisations que vous pouvez effectuer
title: Optimisation des performances d’Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 226afef7-00da-4ac2-be4e-e19995621c61
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '2469'
ht-degree: 42%

---

# Optimisation des performances d’Analysis Workspace

Divers facteurs influencent les performances d’un projet dans Analysis Workspace.  Pour comprendre ces facteurs, vous pouvez planifier et créer des projets de la manière la plus optimale.

Pour intégrer insight aux performances d’Analysis Workspace :

1. Sélectionnez **[!UICONTROL Aide] > [!UICONTROL Performances]**.

   Une boîte de dialogue modale s’affiche. Elle présente les facteurs qui affectent les performances de votre projet, notamment les facteurs relatifs au réseau, au navigateur et au projet. Pour des résultats plus précis, attendez que le projet se charge avant de le charger

   * La colonne **[!UICONTROL Projet en cours]** affiche les résultats pour votre projet en cours et votre environnement utilisateur.
   * La colonne **[!UICONTROL Règle]** affiche le seuil recommandé d’Adobe pour chaque facteur.

1. Sélectionnez **[!UICONTROL Télécharger au format CSV]** pour télécharger le rapport de performances afin de pouvoir le partager au sein de votre organisation interne ou avec le support technique d’Adobe.

>[!NOTE]
>
>Les informations de la page Performances varient chaque fois que la fenêtre modale est ouverte, car les facteurs peuvent changer. En outre, Adobe continue à affiner les directives fournies à mesure que de nouvelles données sont disponibles.

![](assets/cja-performance.png)

## Facteurs réseau

Les facteurs de réseau sont les suivants :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| Connexion à Adobe | Adobe envoie 10 appels test lorsque la page de performances est ouverte. Ces appels représentent le pourcentage d’appels vers Adobe qui réussissent. | Les problèmes de réseau local ou d’Adobe ont un impact sur ce facteur. | Consultez status.adobe.com pour vérifier s’il existe des problèmes de service connus. Ensuite, validez votre connexion réseau locale. |
| Bande passante Internet | Disponible pour Google Chrome uniquement. Estimation de la bande passante de votre navigateur à votre emplacement. La limite est de 2 Mo/s. | Votre connexion réseau locale a un impact sur ce facteur. | Validez votre connexion réseau locale. |
| Latence Internet | Adobe envoie 10 appels test lorsque la page de performances est ouverte. Ces appels représentent le temps moyen nécessaire à une requête pour atteindre Adobe et revenir. En d’autres termes, il s’agit d’une mesure de la vitesse Internet entre votre emplacement et Adobe. La ligne directrice est de &lt; 1 seconde. | Les problèmes de réseau local, de nombreux onglets de navigateur ouverts ou les problèmes Adobe ont un impact sur ce facteur. | Consultez status.adobe.com pour vérifier s’il existe des problèmes de service connus. Ensuite, validez votre connexion réseau locale et fermez les onglets inutilisés du navigateur. |

## Facteurs du navigateur

Les facteurs de navigateur sont les suivants :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| Vitesse de calcul | La vitesse à laquelle votre ordinateur effectue un test de traitement. La valeur recommandée est inférieure à 750 millisecondes. | Votre matériel ainsi que les programmes simultanés ont un impact sur ce facteur. | Ouvrez le Gestionnaire de tâches (PC) ou le Moniteur d’activité (Mac) de votre ordinateur pour déterminer si des programmes peuvent être fermés. Fermez ensuite les onglets inutilisés du navigateur ou d’autres programmes. <br><br>Si ces actions n’aident pas, discutez des détails matériels avec votre équipe informatique. |
| Mémoire utilisée | Disponible pour Google Chrome uniquement. Chaque onglet Workspace d’un navigateur Google Chrome partage 4 Go de mémoire au total. Cette mémoire utilisée représente le pourcentage de cette allocation de mémoire qui est consommé par le projet en cours. La consigne est de 3 500 Mo, c’est-à-dire le moment où Workspace commence à afficher les erreurs de mémoire. | Le fait de travailler sur plusieurs onglets ou de télécharger 50000 lignes de données contribue à augmenter l’utilisation de la mémoire. | Si vous recevez une erreur de mémoire, fermez les autres onglets Workspace et/ou exécutez 50 000 téléchargements de ligne, un à la fois. |
| Stockage local utilisé | Données stockées localement sur votre ordinateur en vue d’être utilisées dans le navigateur. Chaque origine (par exemple, experience.adobe.com) dispose d’une allocation de 10 Mo. | Analysis Workspace utilise l’enregistrement local pour plusieurs fonctions, notamment pour stocker des projets enregistrés automatiquement (existants), des paramètres utilisateur et des indicateurs de fonctionnalité. | Pour vous assurer que les fonctionnalités d’Analysis Workspace ne sont pas perturbées, effacez le stockage local pour le domaine experience.adobe.com. |
| Vitesse de rendu | Le nombre d’images par seconde désigne le nombre d’images par seconde pendant lequel le navigateur dessine la page sur votre écran. 24 i/s est généralement ce que l’œil humain peut observer. Si l’iOS est inférieur à 24 i/s, vous constatez des problèmes de rendu dans Workspace. | FPS est affecté par le multitâche sur de nombreux projets Workspace à la fois et par la taille du projet en cours de visualisation. D’autres programmes exécutés sur votre ordinateur peuvent avoir un impact, comme la diffusion en continu, les scanneurs en arrière-plan, etc. De plus, votre matériel a un impact sur ce facteur. | Ouvrez le Gestionnaire de tâches (PC) ou le Moniteur d’activité (Mac) de votre ordinateur pour déterminer si des programmes peuvent être fermés. Fermez ensuite les onglets inutilisés du navigateur ou d’autres programmes. <br><br>Si ces actions n’aident pas, discutez des détails matériels avec votre équipe informatique. |

## Facteurs du projet

Les facteurs du projet sont les suivants :

| Facteur | Définition | Optimisation |
| --- | --- | --- |
| Nombre de demandes | Nombre total de requêtes adressées à Adobe pour récupérer les données affichées dans le projet. Les requêtes comprennent les demandes avec classement de tableaux, de détection des anomalies, de graphiques sparkline, de composants affichés dans le rail de gauche, etc. Ce nombre exclut les panneaux réduits et les visualisations. La ligne directrice est de 100. | Simplifiez votre projet lorsque cela est possible en divisant les données en plusieurs projets qui répondent à un objectif spécifique ou à un groupe de parties prenantes. Utilisez les balises pour organiser les projets par thèmes et utilisez les [liens directs](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links) pour créer une table des matières interne afin que les parties prenantes puissent trouver plus facilement ce dont elles ont besoin. |
| Panneaux développés (sur le total des panneaux) | Nombre de panneaux développés, sur le nombre total de panneaux dans le projet. La ligne directrice est de 5. | Après avoir pris des mesures pour simplifier votre projet, réduisez les panneaux qui n’ont pas besoin d’être affichés au chargement. Lorsque le projet est ouvert, seuls les panneaux développés sont traités. Les panneaux réduits ne sont pas traités tant que l’utilisateur ne les développe pas. |
| Visualisations développées (sur le total des visualisations) | Nombre de tableaux et de visualisations développés par rapport au total du projet, y compris les sources de données masquées. La ligne directrice est de 15. | Après avoir pris des mesures pour simplifier votre projet, réduisez les visualisations de votre projet qui n’ont pas besoin d’être affichées au chargement. Classez par ordre de priorité les éléments visuels qui sont les plus importants pour le consommateur du rapport et décomposez les éléments visuels associés dans un panneau ou projet distinct et plus détaillé, au besoin. |
| Nombre de cellules à structure libre | Le nombre total de cellules de tableau à structure libre dans le projet, calculé par lignes * colonnes dans tous les tableaux. Ce nombre exclut les sources de données masquées. La ligne directrice est de 4000. | Réduisez le nombre de colonnes dans votre tableau en conservant uniquement les points de données les plus pertinents. Réduisez le nombre de lignes du tableau en ajustant le nombre de lignes affichées, en appliquant un filtre de tableau ou en appliquant un segment. |
| Composants disponibles | Le nombre total de composants récupérés dans le rail gauche du projet, dans toutes les suites de rapports du projet. Ce nombre a une incidence sur la vitesse de chargement du rail de gauche et sur la vitesse à laquelle les résultats de recherche sont renvoyés. La ligne directrice est de 2000. | Contactez l’administrateur de votre produit au sujet de la création d’une suite de rapports virtuelle organisée dotée d’un ensemble de composants plus personnalisé. |
| Composants utilisés | Le nombre total de composants utilisés dans le projet. La ligne directrice est de 100. | Le nombre de composants utilisés n’influe pas directement sur les performances. Cependant, la complexité de ces composants contribue aux performances du projet. Consultez les optimisations dans la section [ facteurs supplémentaires ](#additional-factors) ci-dessous. |
| Période la plus longue | Ce facteur affiche la période la plus longue utilisée dans le projet. La ligne directrice est d’un an. | Si possible, n’extrayez que les données dont vous avez besoin. Limitez le calendrier du panneau aux dates pertinentes pour votre analyse. Vous pouvez également utiliser des composants de période (composants violets) dans vos tableaux à structure libre. Les périodes utilisées dans un tableau remplacent les périodes du panneau. Par exemple, vous pouvez ajouter le mois dernier, la semaine dernière et hier aux colonnes du tableau pour demander ces périodes spécifiques. Pour en savoir plus sur l’utilisation des périodes dans Analysis Workspace, [regardez cette vidéo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-date-ranges-and-comparisons-in-analysis-workspace). <br><br>En outre, réduisez le nombre de comparaisons d’une année à l’autre utilisées dans le projet. Lorsqu’une comparaison d’une année sur l’autre est calculée, elle examine l’ensemble des 13 mois de données entre les mois ciblés. Cette comparaison a le même impact que la modification de la période du panneau sur 13 mois. |

## Facteurs de requête

Facteurs de requête

Utilisez le diagramme et les termes suivants pour découvrir comment les demandes sont traitées et les différents facteurs qui influencent les temps de traitement :

>[!NOTE]
>
>Les instructions recommandées pour ces facteurs sont basées sur un score de complexité de moyen pour les demandes de création de rapports.


### Diagramme de traitement des demandes

![Traitement des demandes](assets/request-processing.png)

### Conditions de traitement des demandes

| Facteur | Définition | Optimisation |
| --- | --- | --- |
| [!UICONTROL **Durée moyenne de la requête**] | Temps nécessaire entre le lancement de la requête et sa fin. La règle est de 15 secondes. <p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de requête représente le processus complet, de **requête Analysis Workspace lancée** à **requête Analysis Workspace terminée**.</p> |  |
| [!UICONTROL **Durée de requête la plus longue**] | Temps nécessaire entre le lancement de la requête et sa fin. <p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de requête représente le processus complet, de **requête Analysis Workspace lancée** à **requête Analysis Workspace terminée**.</p> |  |
| [!UICONTROL **Temps de recherche moyen**] | Comme Analysis Workspace stocke uniquement le hachage des chaînes utilisées dans les segments, chaque fois que vous traitez un projet, des **recherches** sont effectuées pour faire correspondre les hachages aux valeurs appropriées. La règle est de moins de 2 secondes.<p>Ces recherches peuvent être un processus gourmand en ressources, selon le nombre de valeurs pouvant potentiellement correspondre au hachage. </p><p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de recherche est représenté dans la phase **Recherches** (au moment de la phase **Traitement du moteur de requêtes**).</p> | Si les requêtes ralentissent ici, c’est probablement dû à un trop grand nombre de segments de chaîne dans votre projet, ou à des chaînes avec des valeurs trop génériques qui ont trop de correspondances potentielles. |
| [!UICONTROL **Temps moyen dans la file**] | Durée totale d’attente dans la file d’attente avant le traitement des demandes. La règle est de 5 secondes.<p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, la durée de la file d’attente est représentée dans les phases **File d’attente du moteur de requêtes** et **File d’attente du serveur**.</p> | Si les requêtes ralentissent ici, cela peut être dû à un trop grand nombre de requêtes s’exécutant simultanément dans votre organisation. Essayez d’exécuter la requête en dehors des heures de pointe. |
| [!UICONTROL **Temps moyen de traitement du serveur**] | Temps moyen nécessaire au traitement de la requête.<p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de traitement moyen du serveur est représenté dans les phases **File d’attente du serveur** et **Traitement du serveur**. La règle est de 10 secondes | Si les requêtes ralentissent ici, il est probable que le projet comporte des périodes trop longues ou des visualisations complexes. Essayez de raccourcir la période de votre projet pour réduire les temps de traitement. |
| [!UICONTROL **Complexité**] | Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande. La consigne est Medium ou une valeur inférieure. <p>Valeurs possibles :</p> <ul><li>[!UICONTROL **Faible**]</li><li>[!UICONTROL **Moyen**]</li><li>[!UICONTROL **Élevé**]</li></ul>Cette valeur est influencée par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles**]</li><li>[!UICONTROL **Colonnes**]</li><li>[!UICONTROL **Segments**]</li></ul> |  |
| [!UICONTROL **Limites mensuelles**] | Nombre de mois inclus dans une demande. L’ajout de limites de mois ajoute à la complexité de la requête. La règle est de 6 ou moins. | Si les requêtes ralentissent ici, c’est peut-être parce que les limites de mois dans votre projet sont trop grandes. Essayez de réduire le nombre de mois. |
| [!UICONTROL **Colonnes**] | Nombre de mesures et de répartitions dans la demande. D’autres colonnes ajoutent à la complexité de la requête. La règle est de 10 ou moins. | Si les requêtes ralentissent ici, c’est peut-être parce que votre projet comporte trop de colonnes. Essayez de réduire le nombre de colonnes. |
| [!UICONTROL **Segments**] | Nombre de segments appliqués à la demande. D’autres segments ajoutent à la complexité de la requête. La règle est de 5 ou moins. | Si les requêtes ralentissent ici, c’est peut-être parce que votre projet comporte trop de segments. Essayez de réduire le nombre de segments. |

## Facteurs supplémentaires

Autres facteurs non inclus dans Aide > Performances :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| Complexité des segments | Des segments complexes peuvent avoir un impact significatif sur la performance des projets. | Les facteurs qui ajoutent de la complexité à un segment (dans l’ordre décroissant d’impact) incluent les éléments suivants : <ul><li>Les opérateurs de **[!UICONTROL contient]**, **[!UICONTROL contient l’un des]**, **[!UICONTROL correspond]**, **[!UICONTROL commence par]** ou **[!UICONTROL se termine par]**/ </li><li>La segmentation séquentielle, en particulier lorsque des restrictions dimensionnelles (Within/After) sont utilisées </li><li>Nombre d’éléments de dimension uniques dans les dimensions utilisés dans le segment (par exemple, Page = « A » lorsque la page comporte 10 éléments uniques est plus rapide que Page = « A » lorsque la page comporte 100000 éléments uniques). </li><li>Le nombre de dimensions différentes utilisées (par exemple, Page = « Accueil » et Page = « Résultats de la recherche » est plus rapide qu’eVar 1 = « rouge » et eVar 2 = « bleu »).</li><li>Beaucoup d’opérateurs OR (au lieu de AND)</li><li>Conteneurs imbriqués dont la portée varie (par exemple, Accès dans Visite dans Visiteur)</li></ul> | Bien qu’il soit impossible d’éviter certains facteurs de complexité, recherchez les possibilités de réduire la complexité de vos segments. En général, plus vous pouvez être précis dans vos critères de segment, mieux c’est. Par exemple :<ul><li>Avec les conteneurs, l’utilisation d’un seul conteneur en haut du segment est plus rapide qu’une série de conteneurs imbriqués.</li><li>Avec les opérateurs , **[!UICONTROL égal à]** est plus rapide que **[!UICONTROL contient]**, et **[!UICONTROL égal à n’importe lequel]** est plus rapide que **[!UICONTROL contient n’importe lequel]**.</li><li>Avec de nombreux critères, les opérateurs ET sont plus rapides qu’une série d’opérateurs OU.</li></ul> Recherchez les possibilités de réduire de nombreuses instructions OR en une seule instruction **[!UICONTROL égal à n’importe laquelle]**. |
| Complexité de la visualisation (segments, mesures, filtres) | Le type de visualisation (par exemple, Abandons par rapport à un tableau à structure libre) n’influence pas beaucoup les performances du projet. La complexité de la visualisation augmente le temps de traitement. | Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :<ul><li>Plage de données demandée</li><li>Nombre de segments appliqués ; par exemple, les segments utilisés comme des lignes d’un tableau à structure libre</li><li>Utilisation de segments complexes</li><li>Lignes ou colonnes de [postes statiques](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows) dans les tableaux de forme libre</li><li>Filtres appliqués aux lignes des tableaux à structure libre</li><li>Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des segments</li></ul> | Si vos projets ne se chargent pas aussi rapidement que prévu, remplacez si possible certains segments par des eVars et des filtres.<br><br>Si vous utilisez continuellement des segments et des mesures calculées pour les points de données importants dans le cadre de vos activités, envisagez d’améliorer votre mise en œuvre afin de capturer plus directement ces points de données. L’utilisation de balises dans Adobe Experience Platform et des règles de traitement d’Adobe peut faciliter et accélérer les modifications de l’implémentation. |
| Taille de la suite de rapports | La quantité de données collectées dans votre suite de rapports. | - | Contactez votre équipe d’implémentation ou un expert Adobe pour déterminer si des améliorations peuvent être apportées à l’implémentation afin d’améliorer l’expérience globale dans Adobe Analytics. |
| Requêtes simultanées | Le nombre de requêtes simultanément demandées par votre organisation à Adobe. Chaque entreprise a droit à un minimum de 5 requêtes simultanées. | Si la création d’un rapport prend beaucoup de temps, ce rapport est placé dans la file d’attente avec d’autres rapports, ce qui signifie que votre entreprise tente d’exécuter de nombreuses requêtes simultanées sur une suite de rapports spécifique. Les requêtes peuvent provenir de requêtes d’API, d’interfaces utilisateur de création de rapports (Analysis Workspace, Report Builder), de projets planifiés, de rapports planifiés, d’alertes planifiées et d’utilisateurs et utilisatrices simultanés effectuant des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée. De même, déplacez vos requêtes vers les heures creuses lorsque cela est possible. Le lundi matin, le mardi matin et le premier jour de chaque mois sont les périodes de pointe pour les comptes rendus des performances. |

## Conseils pour accroître votre productivité dans Analysis Workspace


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Conseils pour augmenter la productivité](https://video.tv.adobe.com/v/31157?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]
