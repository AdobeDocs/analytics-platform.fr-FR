---
description: Facteurs qui affectent les performances de Workspace et les optimisations recommandées
title: Facteurs de performances et optimisation d’Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 3928307fb51d1bde628773a91d5f4e2d4e5c2a5c
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 82%

---


# Optimisation des performances d’Analysis Workspace

Différents facteurs peuvent influencer les performances d’un projet dans Analysis Workspace. Il convient de savoir quels sont ces facteurs avant de démarrer un projet, afin de planifier et d’élaborer le projet d’une manière optimale. Cette page comprend une liste de facteurs qui aura un impact sur les performances et les optimisations recommandées que vous pouvez effectuer pour garantir des performances optimales dans Analysis Workspace.

>[!IMPORTANT]
>
>La page Performances d’Analysis Workspace est en version limitée. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/analytics/landing/an-releases.html)

## Aide > Performances dans Analysis Workspace

Sous **[!UICONTROL Analysis Workspace > Aide > Performances]**, vous pouvez voir les facteurs qui affectent les performances de votre projet, notamment les facteurs de réseau, de navigateur et de projet. Pour obtenir des résultats plus précis, laissez le projet à se charger complètement avant d’ouvrir la page Performances. En outre, vous pouvez **télécharger au format CSV** le contenu des performances à partager facilement avec l’Assistance clientèle d’Adobe ou vos équipes informatiques internes.

>[!NOTE]
>
>Les informations de la page Performances varient chaque fois que la fenêtre modale est ouverte, car les facteurs peuvent changer. En outre, l&#39;Adobe continuera à affiner les seuils recommandés à mesure que davantage de données seront disponibles.

![](assets/performance-modal.png)

## Facteurs réseau

**[!UICONTROL Aide > Les facteurs de performances u réseau incluent :]**

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- |--- | --- |
| Connexion à Adobe | Adobe envoie 10 appels test lorsque la page de performances est ouverte. Ceci représente le pourcentage de ces appels à Adobe qui réussissent. | Des problèmes de réseau local ou des problèmes Adobe auront une influence sur ce facteur. | Consultez status.adobe.com pour vérifier s’il existe des problèmes de service connus. Ensuite, validez votre connexion réseau locale. |
| Bande passante Internet | Estimation de la bande passante de votre navigateur à votre emplacement, testée uniquement pour Google Chrome. Le seuil recommandé est de 2,0 Mo/s. | Votre connexion réseau locale aura un impact sur ce facteur. | Validez votre connexion réseau locale. |
| Latence Internet | Adobe envoie 10 appels test lorsque la page de performances est ouverte. Cela représente le temps moyen nécessaire pour que chaque demande soit envoyée à Adobe et renvoyée. En d’autres termes, il s’agit d’une mesure de la vitesse Internet entre votre emplacement et Adobe. Le seuil recommandé est de &lt; 1 seconde. | Des problèmes de réseau local, un grand nombre d’onglets ouverts sur le navigateur ou des problèmes Adobe auront une influence sur ce facteur. | Consultez status.adobe.com pour vérifier s’il existe des problèmes de service connus. Ensuite, validez votre connexion réseau locale et fermez les onglets inutilisés du navigateur. |

## Facteurs du navigateur

**[!UICONTROL Aide > Les facteurs de performances des navigateurs incluent :]**

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| Vitesse de calcul | La vitesse à laquelle votre ordinateur effectue un test de traitement. Le seuil recommandé est de &lt; 750 ms. | Votre matériel ainsi que des programmes ouverts simultanément auront un impact sur ce facteur. | Ouvrez le Gestionnaire de tâches (PC) ou le Moniteur d’activité (Mac) de votre ordinateur pour déterminer si des programmes peuvent être fermés. Fermez ensuite les onglets inutilisés du navigateur ou d’autres programmes. <br><br>Si ces actions n’aident pas, discutez des détails matériels avec votre équipe informatique. |
| Mémoire utilisée | Chaque onglet Workspace d’un navigateur Google Chrome partage 4 Go de mémoire au total (Firefox a un seuil plus élevé). Ceci représente le pourcentage de cette mémoire allouée utilisée par le projet actuel. Le seuil recommandé est de 3 500 Mo, c’est-à-dire que Workspace commence à afficher les erreurs de mémoire. | L’utilisation de plusieurs onglets ou le téléchargement de 50 000 lignes de données contribuera à une utilisation accrue de la mémoire. | Si vous recevez une erreur de mémoire, il est recommandé de fermer les autres onglets de Workspace et/ou d’exécuter les téléchargements de ligne de 5 000 lignes une par une. |
| Stockage local utilisé | Données stockées localement sur votre ordinateur en vue de leur utilisation dans le navigateur. Chaque origine (ex. : experience.adobe.com) a une capacité de 10 Mo. | Analysis Workspace utilise l’enregistrement local pour plusieurs fonctions, notamment pour stocker des projets enregistrés automatiquement (existants), des paramètres utilisateur et des indicateurs de fonctionnalité. | Pour éviter toute perturbation des fonctions Analysis Workspace, effacez l’enregistrement local du domaine experience.adobe.com. |
| Vitesse de rendu | &quot;FPS&quot; signifie &quot;Images par seconde&quot;, c’est-à-dire le nombre de fois par seconde que le navigateur trace la page sur votre écran. 24 FPS est généralement ce que l’oeil humain peut observer ; si le FPS est inférieur à cela, vous constaterez des problèmes de rendu dans Workspace. | Le FPS est affecté par l’exécution de nombreuses tâches simultanées dans de nombreux projets Workspace et par la taille du projet affiché. D’autres programmes exécutés sur votre ordinateur peuvent avoir un impact, comme la diffusion en continu, les scanneurs en arrière-plan, etc. De plus, votre matériel aura un impact sur ce facteur. | Ouvrez le Gestionnaire de tâches (PC) ou le Moniteur d’activité (Mac) de votre ordinateur pour déterminer si des programmes peuvent être fermés. Fermez ensuite les onglets inutilisés du navigateur ou d’autres programmes. <br><br>Si ces actions n’aident pas, discutez des détails matériels avec votre équipe informatique. |

## Facteurs du projet

**[!UICONTROL Aide > Facteurs de performances du projet :]**

| Facteur | Définition | Optimisation |
| --- | --- | --- |
| Nombre de requêtes | Nombre total de requêtes (demandes) effectuées à Adobe pour extraire les données affichées dans le projet. Les requêtes comprennent les demandes avec classement de tableaux, de détection des anomalies, de graphiques sparkline, de composants affichés dans le rail de gauche, etc. Exclut les panneaux et les visualisations réduits. Le seuil recommandé est de 100. | Simplifiez votre projet lorsque cela est possible en divisant les données en plusieurs projets qui répondent à un objectif spécifique ou à un groupe de parties prenantes. Utilisez les balises pour organiser les projets par thèmes et utilisez les [liens directs](/help/analysis-workspace/curate-share/shareable-links.md) pour créer une table des matières interne afin que les parties prenantes puissent trouver plus facilement ce dont elles ont besoin. |
| Panneaux développés (sur le total des panneaux) | Nombre de panneaux développés sur le nombre total de panneaux du projet. Le seuil recommandé est de 5. | Après avoir pris des mesures pour simplifier votre projet, réduisez les panneaux de votre projet qui n’ont pas besoin d’être affichés au chargement. Lorsque le projet est ouvert, seuls les panneaux développés sont traités. Les panneaux réduits ne sont pas traités tant que l’utilisateur ne les développe pas. |
| Visualisations développées (sur le total des visualisations) | Nombre de tableaux et de visualisations développés par rapport au total du projet. Exclut les sources de données masquées. Le seuil recommandé est de 15. | Après avoir pris des mesures pour simplifier votre projet, réduisez les visualisations de votre projet qui n’ont pas besoin d’être affichées au chargement. Classez par ordre de priorité les éléments visuels qui sont les plus importants pour le consommateur du rapport et décomposez les éléments visuels associés dans un panneau ou projet distinct et plus détaillé, au besoin. |
| Nombre de cellules à structure libre | Le nombre total de cellules de tableau à structure libre dans le projet, calculé par lignes * colonnes dans tous les tableaux. Exclut les sources de données masquées. Le seuil recommandé est de 4 000. | Réduisez le nombre de colonnes dans votre tableau en conservant uniquement les points de données les plus pertinents. Réduisez le nombre de lignes du tableau en ajustant le nombre de lignes affichées, en appliquant un filtre de tableau ou en appliquant un segment. |
| Composants disponibles | Le nombre total de composants récupérés dans le rail gauche du projet, dans toutes les suites de rapports du projet. Le seuil recommandé est 2000. | Contactez l’administrateur de votre produit au sujet de la création d’une suite de rapports virtuelle organisée dotée d’un ensemble de composants plus personnalisé. |
| Composants utilisés | Le nombre total de composants utilisés dans le projet. Le seuil recommandé est de 100. | Le nombre de composants utilisés n’influe pas directement sur les performances. Toutefois, la complexité de ces composantes contribuera à la performance du projet. Voir les optimisations recommandées dans la section &quot;Facteurs supplémentaires&quot; ci-dessous. |
| Période la plus longue | Ce facteur affiche la période la plus longue utilisée pour le projet. Le seuil recommandé est de 1 an. | Si possible, n’extrayez que les données dont vous avez besoin. Limitez le calendrier du panneau aux dates appropriées à votre analyse ou utilisez des composants de période (composants violets) dans vos tableaux à structure libre. Les périodes utilisées dans un tableau remplacent les périodes du panneau. Par exemple, vous pouvez ajouter le mois dernier, la semaine dernière et hier aux colonnes du tableau pour demander ces périodes spécifiques. Pour en savoir plus sur l’utilisation des plages de dates dans Analysis Workspace, [regardez cette vidéo](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>En outre, réduisez le nombre de comparaisons d’une année à l’autre utilisées dans le projet. Lorsqu’une comparaison d’une année à l’autre est calculée, elle examine l’ensemble des données des 13 mois concernés. Cette action a le même impact que de définir la période du panneau sur les 13 derniers mois. |

## Facteurs supplémentaires

Les facteurs supplémentaires qui ne sont pas inclus dans Aide > Performances sont les suivants :

| Facteur | Définition | Influencé par | Optimisation |
| --- | --- | --- | --- |
| Complexité du filtre | Des filtres complexes peuvent avoir un impact important sur le rendement du projet. | Les facteurs qui rendent un filtre plus complexe (dans l’ordre décroissant d’impact) sont les suivants : <ul><li>Les opérateurs de type « contains », « contains any of », « matches », « starts with » ou « ends with » </li><li>Filtres séquentiels, en particulier lorsque des restrictions de dimension (Dans/Après) sont utilisées </li><li>Le nombre d’éléments de dimensions uniques dans les dimensions utilisées dans le segment (par exemple, Page = ’A’ lorsque Page comporte 10 éléments uniques sera plus rapide que Page = ’A’ lorsque la page a 100 000 éléments uniques) </li><li>Le nombre de dimensions différentes utilisées (par exemple, Page = ’Home’ et Page = ’Search results’ seront plus rapides que eVar 1 = ’red’ et eVar 2 = ’blue’)</li><li>Beaucoup d’opérateurs OR (au lieu de AND)</li><li>Des contenants imbriqués dont la portée varie (par ex., « Hit inside of Visit inside of Visitor »)</li></ul> | Bien que certains facteurs de complexité ne puissent pas être évités, recherchez des occasions de réduire la complexité de vos filtres. En général, plus vous pouvez être précis avec vos critères de filtrage, mieux c&#39;est. Par exemple :<ul><li>Avec les conteneurs, l’utilisation d’un seul conteneur en haut du segment sera plus rapide qu’une série de conteneurs imbriqués</li><li>Avec les opérateurs, « equals » sera plus rapide que « contains » et « equals any of » sera plus rapide que « contains any of »</li><li>Avec de nombreux critères, les opérateurs AND seront plus rapides qu’une série d’opérateurs OR.</li><li>Recherchez également des occasions de réduire plusieurs instructions OR en une seule instruction « equals any of ». </li></ul> |
| Complexité de la visualisation (filtres, mesures) | Le type de visualisation (par exemple, abandon par rapport à un tableau à structure libre) ajouté à un projet en lui-même n’influence pas beaucoup les performances du projet. C’est la complexité de la visualisation qui augmente le temps de traitement. | Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :<ul><li>Plage de données demandée</li><li>Nombre de filtres appliqués ; par exemple, filtres utilisés comme lignes d’un tableau à structure libre</li><li>Utilisation de filtres complexes</li><li>[Lignes ou colonnes de postes statiques dans les tableaux de forme libre](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md)</li><li>Filtres appliqués aux lignes des tableaux à structure libre</li><li>Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des filtres</li></ul> | Si vous constatez que vos projets ne se chargent pas aussi rapidement que vous le souhaitez, essayez de remplacer certains filtres par des eVars et des filtres, si possible.<br><br>Si vous utilisez continuellement des segments et des mesures calculées pour les points de données importants dans le cadre de vos activités, envisagez d’améliorer votre mise en œuvre afin de capturer plus directement ces points de données. Envisagez d’utiliser un gestionnaire de balises tel qu’Adobe Experience Platform Launch et les règles de traitement d’Adobe pour faciliter et accélérer les modifications de la mise en œuvre. |

## Messages d’erreur courants

Vous pouvez rencontrer des erreurs lors de l’interaction avec Analysis Workspace qui influenceront également les performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

| Message d’erreur | Quelle en est la raison ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL Établissement de rapports inhabituellement lourd pour la suite de rapports. Réessayez ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée. |
| [!UICONTROL Une erreur système s’est produite. Veuillez soumettre un ticket à l’Assistance clientèle sous Aide > Envoyer le ticket d’assistance en incluant votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL La requête est trop complexe.] | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les dépassements de délai en raison de la taille de la requête, du nombre trop élevé d’éléments correspondants dans un segment ou un filtre de recherche, du nombre trop élevé de mesures incluses, des combinaisons de dimensions et de mesures incompatibles, etc. | Simplifiez votre requête en supprimant certaines colonnes ou lignes du tableau ou en divisant le tableau en plusieurs requêtes distinctes. |
| [!UICONTROL L’un des segments ou la recherche dans cette visualisation contient une recherche de texte qui a renvoyé trop de résultats.] | Les critères de segment ou le filtre de rapport sont trop étendus. | Limitez vos critères de texte de recherche et effectuez une nouvelle requête. |
| [!UICONTROL Actuellement, cette dimension ne prend pas en charge les modèles d’attribution autres que ceux par défaut.] | L’attribution autre que l’attribution par défaut n’est pas prise en charge pour la dimension que vous utilisez. | Remplacez la dimension de votre tableau par une dimension compatible avec [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |
