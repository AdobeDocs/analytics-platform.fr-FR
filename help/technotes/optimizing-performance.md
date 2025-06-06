---
description: Facteurs qui affectent les performances et les optimisations de Customer Journey Analytics et Workspace que vous pouvez créer
title: Optimisation des performances de Customer Journey Analytics et d’Analysis Workspace
feature: FAQ
exl-id: ad00e476-6f19-462b-ba53-d72ddd949802
role: Admin
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '2578'
ht-degree: 58%

---

# Optimisation des performances de Customer Journey Analytics et d’[!UICONTROL Analysis Workspace]

Divers facteurs peuvent influencer les performances globales de Customer Journey Analytics ainsi que les performances d’un projet dans Analysis Workspace. Dans Workspace, il se peut que vous receviez un message d’erreur indiquant :

`This query is too complex. Please review best practices for building Analysis Workspace queries.`

Ces bonnes pratiques expliquent quels facteurs peuvent entraîner cette erreur et comment simplifier le rapport/projet.

## Facteurs de requête {#query}

Voici les facteurs de requête les plus courants qui influencent les performances globales de Customer Journey Analytics :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| **Nombre de lignes et colonnes à structure libre** | Le nombre total de cellules de tableau à structure libre dans le projet, calculé par lignes * colonnes dans tous les tableaux. Exclut les sources de données masquées. La ligne directrice est de 4000. | | Réduisez le nombre de colonnes dans votre tableau en conservant uniquement les points de données les plus pertinents. Réduisez le nombre de lignes de votre tableau en ajustant le nombre de lignes affichées, en appliquant un segment de tableau ou un segment. |
| **Composants utilisés** | Le nombre total de composants utilisés dans le projet. La ligne directrice est de 100. | Le nombre de composants utilisés n’influe pas directement sur les performances. Toutefois, la complexité de ces composantes contribuera à la performance du projet. Voir les optimisations dans la section « Facteurs supplémentaires » ci-dessous. |
| **Période la plus longue** | Ce facteur affiche la période la plus longue utilisée pour le projet. La ligne directrice est d’un an. |  | Si possible, n’extrayez que les données dont vous avez besoin. Limitez le calendrier du panneau aux dates appropriées à votre analyse ou utilisez des composants de période (composants violets) dans vos tableaux à structure libre. Les périodes utilisées dans un tableau remplacent les périodes du panneau. Par exemple, vous pouvez ajouter le mois dernier, la semaine dernière et hier aux colonnes du tableau pour demander ces périodes spécifiques. Pour en savoir plus sur l’utilisation des périodes dans Analysis Workspace, [regardez cette vidéo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html?lang=fr). <br><br>En outre, réduisez le nombre de comparaisons d’une année à l’autre utilisées dans le projet. Lorsqu’une comparaison d’une année à l’autre est calculée, elle examine l’ensemble des données des 13 mois concernés. Cette action a le même impact que de définir la période du panneau sur les 13 derniers mois. |
| **Complexité des segments** | Des segments complexes peuvent avoir un impact significatif sur la performance des projets. | Les facteurs qui ajoutent de la complexité à un segment (dans l’ordre décroissant d’impact) incluent les éléments suivants : <ul><li>Les opérateurs de type « contient », « contient l’un des », « correspond à », « commence par » ou « se termine par » </li><li>Segmentation séquentielle, en particulier lorsque des restrictions dimensionnelles (Within/After) sont utilisées </li><li>Le nombre d’éléments de dimensions uniques dans les dimensions utilisées dans le segment (par exemple, Page = ’A’ lorsque Page comporte 10 éléments uniques sera plus rapide que Page = ’A’ lorsque la page a 100 000 éléments uniques) </li><li>Le nombre de dimensions différentes utilisées (par exemple, Page = &#39;Home&#39; et Page = &#39;Search results&#39; seront plus rapides que eVar 1 = &#39;red&#39; et eVar 2 = &#39;blue&#39;)</li><li>Beaucoup d’opérateurs OR (au lieu de AND)</li><li>Conteneurs imbriqués dont la portée varie (par exemple, « Événement » dans « Session » dans « Personne »)</li></ul> | Bien qu’il soit impossible d’éviter certains facteurs de complexité, recherchez les possibilités de réduire la complexité de vos segments. En général, plus vous pouvez être précis dans vos critères de segment, mieux c’est. Par exemple :<ul><li>Avec les conteneurs, l’utilisation d’un seul conteneur en haut du segment est plus rapide qu’une série de conteneurs imbriqués.</li><li>Avec les opérateurs , « égal à » est plus rapide que « contient » et « égal à n’importe lequel » est plus rapide que « contient n’importe lequel ».</li><li>Avec de nombreux critères, les opérateurs ET sont plus rapides qu’une série d’opérateurs OU.</li></ul> Recherchez les possibilités de réduire de nombreuses instructions OR en une seule instruction « égal à n’importe lequel ».<br> |
| **Complexité de la visualisation** (segments, mesures, filtres) | Le type de visualisation (par exemple, Abandons par rapport à un tableau à structure libre) ajouté à un projet en lui-même n’influence pas beaucoup les performances du projet. C’est la complexité de la visualisation qui ajoute au temps de traitement. | Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :<ul><li>Plage de données demandée</li><li>Nombre de segments appliqués ; par exemple, les segments utilisés comme des lignes d’un tableau à structure libre</li><li>Utilisation de segments complexes</li><li>Lignes ou colonnes de [postes statiques](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) dans les tableaux de forme libre</li><li>Segments appliqués aux lignes des tableaux à structure libre</li><li>Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des segments</li></ul> |
| **Capacité du centre de données** | Capacité de création de comptes rendus des performances que vous et dʼautres clients partagez au sein dʼun centre de données Adobe. | Cela dépend du nombre de requêtes simultanées effectuées par votre entreprise et dʼautres entreprises au sein de votre centre de données. | Votre entreprise a droit à une capacité déterminée, et, si le système est peu sollicité, Adobe vous transférera une capacité supérieure à celle à laquelle vous avez droit. |
| **Nombre de requêtes simultanées** | Le nombre de requêtes qui sont demandées par votre organisation en même temps. Chaque organisation a droit à un minimum de 5 requêtes simultanées. Si un rapport prend beaucoup de temps, cʼest généralement parce quʼil est dans une file dʼattente avec dʼautres rapports. Cela signifie que votre organisation tente d’exécuter de nombreuses requêtes simultanées sur une vue de données spécifique. | Les requêtes peuvent provenir de requêtes d’API, d’interfaces utilisateur de création de rapports (Analysis Workspace, Report Builder, etc.), de projets planifiés, d’alertes planifiées et d’utilisateurs et utilisatrices simultanés effectuant des requêtes de création de rapports. | Répartissez vos requêtes et plannings pour la vue de données de manière plus uniforme tout au long de la journée. De même, déplacez vos requêtes vers les heures creuses lorsque cela est possible. Le lundi matin, le mardi matin et le premier jour de chaque mois sont les périodes de pointe pour les comptes rendus des performances. |
| **Taille de la connexion** | La quantité de données collectées dans votre connexion. |  | Contactez votre équipe d’implémentation ou un expert Customer Journey Analytics pour déterminer si des améliorations peuvent être apportées à l’implémentation afin d’améliorer l’expérience globale dans Customer Journey Analytics. |
| **Complexité des paramètres de dimension** | Des dimensions très complexes peuvent avoir un impact significatif sur les performances du projet, en particulier les dimensions ou les mesures basées sur des champs personnalisés complexes. | | Réduire le nombre de champs personnalisés ou créer des dimensions distinctes |
| **Dimensions comportant de nombreuses valeurs uniques** | Également appelées dimensions à cardinalité élevée, ces dimensions peuvent avoir un impact sur les performances des rapports. | Voir [dimensions à cardinalité élevée](/help/components/dimensions/high-cardinality.md) | Voir [dimensions à cardinalité élevée](/help/components/dimensions/high-cardinality.md) |

## [!UICONTROL Aide] > [!UICONTROL Performances] dans Analysis Workspace

Différents facteurs peuvent influencer les performances d’un projet dans Analysis Workspace. Il convient de savoir quels sont ces facteurs avant de démarrer un projet, afin de planifier et d’élaborer le projet d’une manière optimale. Cette section comprend une liste des facteurs qui affectent les performances et les optimisations que vous pouvez effectuer pour garantir des performances optimales dans Analysis Workspace.

Sous **Analysis Workspace > [!UICONTROL Aide] > [!UICONTROL Performances]**, vous pouvez voir les facteurs qui affectent les performances de votre projet, notamment les facteurs de réseau, de navigateur et de projet. Pour obtenir des résultats plus précis, laissez le projet à se charger complètement avant d’ouvrir la page Performances.

* La colonne Projet actuel affiche les résultats de votre projet actuel et de votre environnement utilisateur.
* La colonne Ligne directrice affiche le seuil recommandé par Adobe pour chaque facteur.

En outre, vous pouvez **Télécharger au format CSV** le contenu des performances à partager facilement avec l’Assistance clientèle d’Adobe ou vos équipes informatiques internes.

>[!NOTE]
>
>Les informations de la page Performances varient chaque fois que la fenêtre modale est ouverte, car les facteurs peuvent changer. En outre, Adobe continuera d’affiner les lignes directrices fournies au fur et à mesure que davantage de données seront disponibles.

![Performances d’Analysis Workspace indiquant le facteur réseau, le projet actuel et les directives.](assets/performance-modal.png)

### Facteurs réseau

[!UICONTROL Aide] > [!UICONTROL Performances]. Les facteurs de performances du réseau incluent :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| **Connexion à Adobe** | Adobe envoie 10 appels test lorsque la page de performances est ouverte. Ceci représente le pourcentage de ces appels à Adobe qui réussissent. | Des problèmes de réseau local ou des problèmes Adobe auront une influence sur ce facteur. | Consultez status.adobe.com pour vérifier s’il existe des problèmes de service connus. Ensuite, validez votre connexion réseau locale. |
| **Bande passante Internet** | Disponible pour Google Chrome uniquement. Estimation de la bande passante de votre navigateur à votre emplacement. La limite est de 2 Mo/s. | Votre connexion réseau locale aura un impact sur ce facteur. | Validez votre connexion réseau locale. |
| **Latence Internet** | Adobe envoie 10 appels test lorsque la page de performances est ouverte. Cela représente le temps moyen nécessaire pour que chaque demande soit envoyée à Adobe et renvoyée. En d’autres termes, il s’agit d’une mesure de la vitesse Internet entre votre emplacement et Adobe. La ligne directrice est de &lt; 1 seconde. | Des problèmes de réseau local, un grand nombre d’onglets ouverts sur le navigateur ou des problèmes Adobe auront une influence sur ce facteur. | Consultez status.adobe.com pour vérifier s’il existe des problèmes de service connus. Ensuite, validez votre connexion réseau locale et fermez les onglets inutilisés du navigateur. |

### Facteurs du navigateur

[!UICONTROL Aide] > [!UICONTROL Performances]. Les facteurs de performances du navigateurs incluent :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| **Vitesse de calcul** | La vitesse à laquelle votre ordinateur effectue un test de traitement. La ligne directrice est de &lt; 750 ms. | Votre matériel ainsi que des programmes ouverts simultanément auront un impact sur ce facteur. | Ouvrez le Gestionnaire de tâches (PC) ou le Moniteur d’activité (Mac) de votre ordinateur pour déterminer si des programmes peuvent être fermés. Fermez ensuite les onglets inutilisés du navigateur ou d’autres programmes. <br><br>Si ces actions n’aident pas, discutez des détails matériels avec votre équipe informatique. |
| **Mémoire utilisée** | Disponible pour Google Chrome uniquement. Chaque onglet Workspace d’un navigateur Google Chrome partage 4 Go de mémoire au total. Ceci représente le pourcentage de cette mémoire allouée utilisée par le projet actuel. La ligne directrice est de 3 500 Mo, ce qui est le seuil auquel Workspace commence à afficher les erreurs de mémoire. | L’utilisation de plusieurs onglets ou le téléchargement de 50 000 lignes de données contribuera à une utilisation accrue de la mémoire. | Si vous recevez une erreur de mémoire, fermez les autres onglets Workspace et/ou exécutez 50 000 téléchargements de ligne, un à la fois. |
| **Stockage local utilisé** | Données stockées localement sur votre ordinateur en vue de leur utilisation dans le navigateur. Chaque origine (ex. : experience.adobe.com) a une capacité de 10 Mo. | Analysis Workspace utilise l’enregistrement local pour plusieurs fonctions, notamment pour stocker des projets enregistrés automatiquement (existants), des paramètres utilisateur et des indicateurs de fonctionnalité. | Pour éviter toute perturbation des fonctions Analysis Workspace, effacez l’enregistrement local du domaine experience.adobe.com. |
| **Vitesse de rendu** | FPS signifie Frames per second (Images par seconde), c’est-à-dire le nombre de fois par seconde que le navigateur trace la page sur votre écran. 24 FPS est généralement ce que l’oeil humain peut observer ; si le FPS est inférieur à cela, vous constaterez des problèmes de rendu dans Workspace. | Le FPS est affecté par l’exécution de nombreuses tâches simultanées dans de nombreux projets Workspace et par la taille du projet affiché. D’autres programmes exécutés sur votre ordinateur peuvent avoir un impact, comme la diffusion en continu, les scanneurs en arrière-plan, etc. De plus, votre matériel aura un impact sur ce facteur. | Ouvrez le Gestionnaire de tâches (PC) ou le Moniteur d’activité (Mac) de votre ordinateur pour déterminer si des programmes peuvent être fermés. Fermez ensuite les onglets inutilisés du navigateur ou d’autres programmes. <br><br>Si ces actions n’aident pas, discutez des détails matériels avec votre équipe informatique. |

### Facteurs du projet

[!UICONTROL Aide] > [!UICONTROL Performances]. Les facteurs de performances du projet incluent :

| Facteur | Définition | Optimisation |
| --- | --- | --- |
| **Nombre de requêtes** | Nombre total de requêtes (demandes) effectuées à Adobe pour extraire les données affichées dans le projet. Les requêtes comprennent les demandes avec classement de tableaux, de détection des anomalies, de graphiques sparkline, de composants affichés dans le rail de gauche, etc. Exclut les panneaux et les visualisations réduits. La ligne directrice est de 100. | Simplifiez votre projet lorsque cela est possible en divisant les données en plusieurs projets qui répondent à un objectif spécifique ou à un groupe de parties prenantes. Utilisez les balises pour organiser les projets par thèmes et utilisez les [liens directs](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=fr) pour créer une table des matières interne afin que les parties prenantes puissent trouver plus facilement ce dont elles ont besoin. |
| **Panneaux développés (sur le total des panneaux)** | Nombre de panneaux développés sur le nombre total de panneaux du projet. La ligne directrice est de 5. | Après avoir pris des mesures pour simplifier votre projet, réduisez les panneaux de votre projet qui n’ont pas besoin d’être affichés au chargement. Lorsque le projet est ouvert, seuls les panneaux développés sont traités. Les panneaux réduits ne sont pas traités tant que l’utilisateur ne les développe pas. |
| **Visualisations étendues (sur le total des visualisations)** | Nombre de tableaux et de visualisations développés par rapport au total du projet, y compris les sources de données masquées. La ligne directrice est de 15. | Après avoir pris des mesures pour simplifier votre projet, réduisez les visualisations de votre projet qui n’ont pas besoin d’être affichées au chargement. Classez par ordre de priorité les éléments visuels qui sont les plus importants pour le consommateur du rapport et décomposez les éléments visuels associés dans un panneau ou projet distinct et plus détaillé, au besoin. |
| **Nombre de cellules libres** | Consultez le tableau « Facteurs de requête » ci-dessus. | |
| **Composants utilisés** | Consultez le tableau « Facteurs de requête » ci-dessus. | |
| **Période la plus longue** | Consultez le tableau « Facteurs de requête » ci-dessus. | |

## Facteurs de requête

Facteurs de requête [!UICONTROL Aide] > [!UICONTROL Performances]

Utilisez le diagramme et les termes suivants pour découvrir comment les demandes sont traitées et les différents facteurs qui influencent les temps de traitement :

>[!NOTE]
>
>Les instructions recommandées pour ces facteurs sont basées sur un score de complexité de Medium pour les requêtes de création de rapports.


### Diagramme de traitement des demandes

![Traitement des demandes](assets/request-processing.png)

### Conditions de traitement des demandes

| Facteur | Définition | Optimisation |
| --- | --- | --- |
| [!UICONTROL **Durée moyenne de la requête**] | Temps nécessaire entre le lancement de la requête et sa fin. La règle est de 15 secondes. <p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de requête représente le processus complet, de **requête Analysis Workspace lancée** à **requête Analysis Workspace terminée**.</p> |  |
| [!UICONTROL **Durée de requête la plus longue**] | Temps nécessaire entre le lancement de la requête et sa fin. <p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de requête représente le processus complet, de **requête Analysis Workspace lancée** à **requête Analysis Workspace terminée**.</p> |  |
| [!UICONTROL **Temps de recherche moyen**] | Comme Analysis Workspace stocke uniquement le hachage des chaînes utilisées dans les segments, chaque fois que vous traitez un projet, des **recherches** sont effectuées pour faire correspondre les hachages aux valeurs appropriées. La règle est de moins de 2 secondes.<p>Il peut s’agir d’un processus gourmand en ressources, selon le nombre de valeurs susceptibles de correspondre au hachage. </p><p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de recherche est représenté dans la phase **Recherches** (au moment du **Traitement du moteur de requêtes**).</p> | Si les requêtes ralentissent ici, c’est probablement dû à un trop grand nombre de segments de chaîne dans votre projet, ou à des chaînes avec des valeurs trop génériques qui ont trop de correspondances potentielles. |
| [!UICONTROL **Temps moyen dans la file**] | Durée totale d’attente en file d’attente avant le traitement des demandes. La règle est de 5 secondes.<p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, la durée de la file d’attente est représentée dans les phases **File d’attente du moteur de requêtes** et **File d’attente du serveur**.</p> | Si les requêtes ralentissent ici, cela peut être dû à un trop grand nombre de requêtes s’exécutant simultanément dans votre organisation. Essayez d’exécuter la requête en dehors des heures de pointe. |
| [!UICONTROL **Temps moyen de traitement du serveur**] | Temps moyen nécessaire au traitement de la requête.<p>Dans le diagramme [Traitement des requêtes](#request-processing-diagram) ci-dessus, le temps de traitement moyen du serveur est représenté dans les phases **File d’attente du serveur** et **Traitement du serveur**. La règle est de 10 secondes | Si les requêtes ralentissent ici, il est probable que le projet comporte des périodes trop longues ou des visualisations complexes. Essayez de raccourcir la période de votre projet afin de réduire les temps de traitement. |
| [!UICONTROL **Complexité**] | Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande. La consigne est Medium ou une valeur inférieure. <p>Valeurs possibles :</p> <ul><li>[!UICONTROL **Faible**]</li><li>[!UICONTROL **Moyen**]</li><li>[!UICONTROL **Élevé**]</li></ul>Cette valeur est influencée par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles**]</li><li>[!UICONTROL **Colonnes**]</li><li>[!UICONTROL **Segments**]</li></ul> |  |
| [!UICONTROL **Limites mensuelles**] | Nombre de mois inclus dans une demande. L’ajout de limites de mois ajoute à la complexité de la requête. La règle est de 6 ou moins. | Si les requêtes ralentissent ici, c’est peut-être parce que les limites de mois dans votre projet sont trop grandes. Essayez de réduire le nombre de mois. |
| [!UICONTROL **Colonnes**] | Nombre de mesures et de répartitions dans la demande. L’ajout de colonnes ajoute à la complexité de la requête. La règle est de 10 ou moins. | Si les requêtes ralentissent ici, c’est peut-être parce que votre projet comporte trop de colonnes. Essayez de réduire le nombre de colonnes. |
| [!UICONTROL **Segments**] | Nombre de segments appliqués à la demande. Plus de segments ajoute à la complexité de la requête. La règle est de 5 ou moins. | Si les requêtes ralentissent ici, c’est peut-être parce que votre projet comporte trop de segments. Essayez de réduire le nombre de segments. |
