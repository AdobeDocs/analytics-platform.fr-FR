---
description: Configuration d’une visualisation de canevas de Parcours
title: Zone de travail du parcours
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: 707bfbf6d34d999bc1b275b24cd6a78b8ef65e74
workflow-type: tm+mt
source-wordcount: '4276'
ht-degree: 1%

---

# Configuration d’une visualisation de canevas de Parcours

{{release-limited-testing}}

La visualisation du canevas de Parcours vous permet d’analyser et d’obtenir des informations détaillées sur les parcours que vous fournissez à vos utilisateurs et clients.

## Présentation du canevas de parcours

Pour en savoir plus sur le canevas de Parcours, voir [Aperçu du canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) , notamment :

* Principales fonctionnalités

* Informations potentielles

* Différences entre le canevas de Parcours et les abandons

* Détails sur l’analyse des parcours Journey Optimizer

* Et plus

## Commencer à créer une visualisation de zone de travail de Parcours

1. Ajoutez un panneau vierge à votre projet, sélectionnez l’icône [!UICONTROL **Visualisations**] dans le rail de gauche, puis faites glisser la visualisation [!UICONTROL **Canevas de Parcours**] dans le panneau.

   Ou

   Ajoutez une visualisation de canevas de Parcours de l’une des manières décrites dans la section [Ajouter des visualisations à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) de la [présentation des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Indiquez les informations de base suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Mesure de Principal**] | La mesure principale affecte les aspects suivants de la visualisation du canevas de Parcours :  <ul><li>Définit la façon dont les gens se déplacent dans le parcours.</li><li>Nombre total affiché sur chaque noeud.<p>Par exemple, si Personnes est la mesure principale, chaque noeud indique le nombre de personnes ayant atteint ce noeud dans le parcours.</p></li><li>Pourcentage affiché sur chaque noeud. (Une fois la visualisation créée, vous pouvez choisir d’afficher le pourcentage du total ou du noeud de départ.)</li><p>Par exemple, si Personnes est la mesure principale, chaque noeud affiche le pourcentage de personnes ayant atteint ce noeud dans le parcours (le pourcentage du total ou du noeud de départ).</p></li><li>Lorsqu’une dimension est ajoutée à la visualisation, les 3 premiers noeuds de la visualisation sont ajoutés, en fonction de la mesure principale.</li></ul> |
   | [!UICONTROL **Deuxième mesure**] | La mesure secondaire est facultative. Lorsqu’une mesure est sélectionnée, les informations suivantes s’affichent sur chaque noeud sous la mesure principale : <ul><li>Nombre total<p>Par exemple, si Sessions est la mesure secondaire, chaque noeud affiche le nombre de sessions qui ont atteint ce noeud dans le parcours.</p></li><li>Pourcentage (une fois la visualisation créée, vous pouvez choisir d’afficher le pourcentage du total ou du noeud de départ.)</li><p>Par exemple, si Sessions est la mesure secondaire, chaque noeud affiche le pourcentage de sessions ayant atteint ce noeud dans le parcours (le pourcentage du total ou du noeud de départ).</p></li></ul> |
   | [!UICONTROL **parcours Journey Optimizer**]<!-- name? --> | Sélectionnez le parcours Journey Optimizer que vous souhaitez utiliser comme base de votre analyse dans la zone de travail du Parcours. (Vous pouvez également laisser cette option vide si vous souhaitez créer un canevas vierge à partir duquel créer votre analyse dans Analysis Workspace.)</p> <p>Lorsque vous analysez un parcours Journey Optimizer dans un canevas de Parcours, le parcours s’affiche avec le même ordre, la même séquence et la même structure que dans Journey Optimizer. Pour plus d’informations, reportez-vous à la section [Analyse des parcours Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) dans la [présentation du canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Remarque** : Cette option s’affiche uniquement lorsque des données Journey Optimizer sont détectées dans la vue de données sélectionnée dans le panneau Analysis Workspace dans lequel vous ajoutez la visualisation. Pour plus d’informations sur la modification de la vue de données sur un panneau dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Facultatif) Sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Conteneur de canevas de Parcours**] | Sélectionnez le conteneur sur lequel vous souhaitez vous concentrer tout au long du parcours. Le conteneur que vous choisissez détermine les statistiques affichées dans la visualisation. (Si les noms de vos conteneurs diffèrent des noms par défaut affichés ci-dessous, ils ont été personnalisés dans votre vue de données.)<ul><li>**Sessions :** Contraint les statistiques de la visualisation à appartenir à une seule session définie pour une personne donnée. Cela signifie que les nombres et les pourcentages qui apparaissent sur chaque noeud (en fonction des mesures primaires et secondaires) doivent se produire au cours d’une seule session pour chaque personne.</li><li>**Personnes :** Permet aux statistiques de la visualisation d’étendre plusieurs sessions pour une personne donnée. Cela signifie que les nombres et les pourcentages qui apparaissent sur chaque noeud (en fonction des mesures primaires et secondaires) peuvent se produire sur n’importe quel nombre de sessions, à condition que les sessions appartiennent à la même personne. Il s’agit du paramètre par défaut.</li></ul> |

1. Sélectionnez la [!UICONTROL **Version**].

   Si vous disposez de Journey Optimizer et que vous avez sélectionné un parcours Journey Optimizer, le parcours s’affiche avec le même ordre, la même séquence et la même structure que dans Journey Optimizer.

   <!-- add screen shot -->

   Si vous ne disposez pas de Journey Optimizer ou si vous n’avez pas sélectionné de parcours Journey Optimizer, un canevas vierge s’affiche où vous pouvez commencer à remplir le parcours.

   <!-- add screen shot -->

1. Que vous créiez une nouvelle analyse à partir d’un canevas vierge ou que vous analysiez un parcours Journey Optimizer, vous pouvez configurer le parcours comme décrit dans [Configuration d’une visualisation de canevas de Parcours](#begin-building-a-journey-canvas-visualization).


## Configuration d’une visualisation de canevas de Parcours

Vous devez [commencer à créer une visualisation de canevas de Parcours](#begin-building-a-journey-canvas-visualization) avant de pouvoir la configurer comme décrit dans les sections suivantes.

### Configuration des paramètres

1. Dans Analysis Workspace, ouvrez une visualisation de canevas de Parcours existante ou [commencez à en créer une](#begin-building-a-journey-canvas-visualization).

1. Configurez l’un des paramètres suivants qui s’affichent dans la partie supérieure de la visualisation :

   | Paramètre | Fonction |
   |---------|----------|
   | [!UICONTROL **Type de noeud**] | Permet de configurer les types de noeud qui s’affichent dans la visualisation. Pour masquer un type de noeud de la visualisation, sélectionnez (x) en regard du type de noeud ou désélectionnez-le dans le menu déroulant. Pour afficher un type de noeud masqué, sélectionnez-le dans le menu déroulant. <p>Selon le contenu de votre visualisation, les types de noeuds possibles sont les suivants :</p><ul><li>[!UICONTROL **Lecture de segment**]</li><li>[!UICONTROL **End**]</li><li>[!UICONTROL **Dimension**]</li><li>[!UICONTROL **Mesure**]</li></ul><p>**Remarque** : Tenez compte des points suivants lors de l’utilisation de ce champ :</p><ul><li>Cette option s’affiche uniquement lorsque des données Journey Optimizer sont détectées dans la vue de données sélectionnée dans le panneau Analysis Workspace dans lequel vous ajoutez la visualisation. Pour plus d’informations sur la modification de la vue de données sur un panneau dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analysis-workspace/home.md).</li><li>Après avoir modifié un parcours Journey Optimizer dans la zone de travail du Parcours, cette option n’est plus disponible. Pour plus d’informations, voir [Différences visuelles après la modification d’un parcours dans la zone de travail du Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p> |
   | [!UICONTROL **Valeur en pourcentage**] | Choisissez l’une des options suivantes : <ul><li>[!UICONTROL **Pourcentage du total**] : pourcentage de toutes les personnes incluses dans la vue de données au cours de la période du panneau.</li><li>[!UICONTROL **Pourcentage du noeud de départ**] : pourcentage de toutes les personnes incluses dans la vue de données dans la période du panneau qui répondent également aux critères du noeud de départ du parcours. (Cette option est disponible uniquement dans les parcours avec un seul noeud de démarrage ; elle est désactivée dans les parcours avec plusieurs noeuds de démarrage. Un noeud de départ est défini comme tout noeud qui ne comporte pas de connexion.)</li></ul> |
   | [!UICONTROL **Paramètres de flèche**] | Choisissez l’une des options suivantes :<ul><li>[!UICONTROL **None**] : </li><li>[!UICONTROL **Condition :**] </li><li>[!UICONTROL **Toutes les étiquettes**] : </li></ul><p>**Remarque** : Cette option s’affiche uniquement lorsque des données Journey Optimizer sont détectées dans la vue de données sélectionnée dans le panneau Analysis Workspace dans lequel vous ajoutez la visualisation. Pour plus d’informations sur la modification de la vue de données sur un panneau dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analysis-workspace/home.md).</p> |
   | [!UICONTROL **Afficher l’abandon**] | Affiche les données d’abandon pour chaque noeud. Cela indique le nombre et le pourcentage de personnes qui ont quitté le parcours à un noeud donné. <p>Les personnes qui sont tombées du parcours peuvent avoir effectué d’autres actions sur le site, mais elles ne répondent jamais aux critères définis par le noeud suivant dans le parcours.</p> |

1. Poursuivez en [Ajoutez un noeud](#add-a-node).

### Ajouter un noeud

Les noeuds d’une visualisation de zone de travail de Parcours représentent les événements ou les actions d’un parcours utilisateur. Vous créez des noeuds en faisant glisser les composants Workspace du rail de gauche vers la zone de travail.

Pour ajouter un noeud à une visualisation de zone de travail de Parcours :

1. Dans Analysis Workspace, ouvrez une visualisation de canevas de Parcours existante ou [commencez à en créer une](#begin-building-a-journey-canvas-visualization).

1. Faites glisser des mesures, des dimensions, des éléments de dimension, des filtres ou des plages de dates depuis le rail de gauche vers la zone de travail. Les mesures basées sur un [champ dérivé](/help/data-views/derived-fields/derived-fields.md) sont prises en charge. Cependant, les mesures calculées, ainsi que les mesures ou dimensions basées sur un [jeu de données récapitulatif](/help/data-views/summary-data.md) ne sont pas prises en charge.

   Vous pouvez sélectionner plusieurs composants dans le rail de gauche en maintenant la touche Maj enfoncée ou en maintenant la touche Commande (sur Mac) ou Ctrl (sur Windows) enfoncée.

   La visualisation est mise à jour comme suit, selon le type de composant et la zone de la zone de travail dans laquelle vous la placez :

   | Type de composant | Emplacement du composant | Mises à jour de la visualisation après l’ajout du noeud |
   |---------|----------|----------|
   | Mesure | Zone vierge de la zone de travail | Le noeud s’affiche à l’endroit où le composant a été déposé, sans être connecté aux noeuds existants. |
   | Mesure | Un noeud existant | Le composant est automatiquement combiné avec le noeud existant. (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p> |
   | Mesure | Flèche entre 2 noeuds existants | Le noeud s’affiche entre les deux noeuds existants où le composant a été déposé et est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p> |
   | Dimension | Zone vierge de la zone de travail | 3 noeuds sont créés pour les 3 premiers éléments de dimension dans lesquels le composant a été déposé, sans être connecté aux noeuds existants. (**Remarque :** Si seulement 1 ou 2 noeuds s’affichent, cela signifie que les données ne sont disponibles que pour 1 ou 2 des éléments de dimension. Si aucun noeud ne s’affiche, cela signifie que les données ne sont disponibles pour aucun des éléments de dimension. Dans ce cas, essayez de l’ajouter à un autre point du parcours, ajustez la période de la visualisation ou choisissez une autre dimension.)<p>Maintenez la touche Maj enfoncée lorsque vous déposez la dimension sur la zone de travail pour l’ajouter en tant que noeud unique avec 3 éléments de dimension.</p><p></p> |
   | Dimension | Un noeud existant | Une ventilation est automatiquement appliquée au noeud avec les 5 premiers éléments de dimension affichés.<!--what happens if you hold Shift?--> |
   | Dimension | Une flèche qui connecte 2 noeuds existants | 3 noeuds sont créés pour les 3 premiers éléments de dimension qui suivent le premier événement après le premier noeud (de personnes/sessions qui atteignent finalement le deuxième noeud). Les noeuds s’affichent entre les deux noeuds existants où le composant a été déposé et chaque noeud est connecté aux deux noeuds existants. (**Remarque :** Si seulement 1 ou 2 noeuds s’affichent, cela signifie que les données ne sont disponibles que pour 1 ou 2 des éléments de dimension. Si aucun noeud ne s’affiche, cela signifie que les données ne sont disponibles pour aucun des éléments de dimension. Dans ce cas, essayez de l’ajouter à un autre point du parcours, ajustez la période de la visualisation ou choisissez une autre dimension.)<p>Maintenez la touche Maj enfoncée lorsque vous déposez la dimension sur la zone de travail pour l’ajouter en tant que noeud unique avec 3 éléments de dimension. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p> |
   | Élément de dimension | Zone vierge de la zone de travail | Le noeud s’affiche à l’endroit où le composant a été déposé, sans être connecté aux noeuds existants. |
   | Élément de dimension | Un noeud existant | Le composant est automatiquement combiné avec le noeud existant. |
   | Élément de dimension | Une flèche qui connecte 2 noeuds existants | Le noeud s’affiche entre les deux noeuds existants où le composant a été déposé et est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p> |
   | Filtre | Zone vierge de la zone de travail | Le noeud s’affiche là où le composant a été déposé sans être connecté aux autres noeuds.<p>Le nombre et le pourcentage qui apparaissent sur le noeud incluent le total de la mesure principale, filtré selon le filtre que vous avez sélectionné.</p> <p>Par exemple, si Personnes est sélectionné comme mesure principale pour le parcours, l’ajout d’un filtre Aujourd’hui à une zone vierge du canevas affiche toutes les personnes qui ont déclenché un événement aujourd’hui.</p> |
   | Filtre | Un noeud existant | Applique le filtre au noeud existant. |
   | Filtre | Une flèche qui connecte 2 noeuds | Le noeud s’affiche entre les deux noeuds existants où le composant a été déposé et est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p><p>Applique le filtre au point du chemin d’accès où le composant a été déposé.</p> |
   | Période | Zone vierge de la zone de travail | Le noeud s’affiche à l’endroit où le composant a été déposé, sans être connecté aux autres noeuds.<p>Le nombre et le pourcentage qui apparaissent sur le noeud incluent le total de la mesure principale, filtré selon la période que vous avez sélectionnée.</p> <p>Si, par exemple, Personnes est sélectionné comme mesure principale pour le parcours, l’ajout d’une période du mois en question à une zone vierge du canevas affiche toutes les personnes qui ont déclenché un événement au cours du mois en cours.</p> |
   | Période | Un noeud existant | Applique la période au noeud existant. |
   | Période | Une flèche qui connecte 2 noeuds | Le noeud s’affiche entre les deux noeuds existants où le composant a été déposé et est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p><p>Applique la période au point du chemin d’accès où le composant a été déposé.</p> |
   | Composants multiples | Zone vierge du canevas | **Si aucun des composants n’est une dimension :**<p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés, sans être connecté aux noeuds existants.</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. </p><p>**Si l’un des composants que vous ajoutez est des dimensions :**</p><p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés, sans être connecté aux noeuds existants.</p><p>Une seule dimension peut être ajoutée à la fois et 3 noeuds sont créés pour les 3 premiers éléments de dimension dans lesquels le composant a été déposé.</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. Les trois premiers éléments de dimension sont combinés avec chaque noeud. (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p> |
   | Composants multiples | Un noeud existant | Tous les composants sont combinés avec le noeud existant.<p>Si l’un des composants que vous ajoutez est des dimensions, les 3 premiers éléments de dimension sont combinés avec le noeud .</p> <p>Une seule dimension peut être ajoutée à la fois.</p> |
   | Composants multiples | Une flèche qui connecte 2 noeuds existants | **Si aucun des composants n’est une dimension :**<p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés et chaque noeud est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. (Les composants doivent être du même type pour être combinés en un seul noeud.) (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p><p>**Si l’un des composants que vous ajoutez est des dimensions :**</p><p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés et chaque noeud est connecté aux deux noeuds existants.</p><p>Une seule dimension peut être ajoutée à la fois et 3 noeuds sont créés pour les 3 premiers éléments de la dimension qui suivent le premier événement après le premier noeud (de personnes/sessions qui atteignent finalement le deuxième noeud). Chaque noeud est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. Les 3 premiers éléments de dimension sont combinés avec chaque noeud et chaque noeud est connecté aux deux noeuds existants. (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p> |

   Les noeuds s’affichent sous la forme d’une boîte rectangulaire avec les informations suivantes :

   * Nom du composant

   * Type de composant (comme une mesure ou une dimension)

   * Statistiques des mesures de Principal (total et pourcentage)

   * Statistiques des mesures Secondaire (total et pourcentage)

1. Répétez cette procédure pour continuer à ajouter des noeuds afin de créer votre parcours.

1. Continuez à personnaliser le parcours comme décrit dans les sections ci-dessous. Vous pouvez connecter des noeuds, renommer des noeuds, appliquer des ventilations, créer des audiences, ajouter des contraintes de temps, etc.

### Ajouter les principaux noeuds en fonction des noeuds existants

Vous pouvez ajouter automatiquement les noeuds supérieurs en fonction des noeuds déjà présents dans la zone de travail.

Cette option est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Flèche entre les noeuds

#### Ajouter les noeuds supérieurs après un noeud existant

Vous pouvez sélectionner un noeud et ajouter les 3 premiers noeuds qui lui succèdent dans le parcours.

1. Cliquez avec le bouton droit sur le noeud où vous souhaitez ajouter les 3 premiers noeuds qui viennent après dans le parcours.

   Ce noeud ne peut pas comporter de noeuds existants qui en sortent dans le parcours.

1. Sélectionnez [!UICONTROL **Ajouter les principaux noeuds après ce noeud**].

   Les 3 premiers noeuds qui suivent ce noeud dans le parcours sont ajoutés et chacun d’eux est connecté au noeud que vous avez sélectionné en tant que branche distincte.

#### Ajouter les noeuds supérieurs avant un noeud existant

Vous pouvez ajouter les 3 premiers noeuds situés avant un noeud existant dans le parcours.

1. Cliquez avec le bouton droit sur le noeud où vous souhaitez ajouter les 3 premiers noeuds qui précèdent dans le parcours.

   Ce noeud ne peut pas contenir de noeuds existants dans le parcours.

1. Sélectionnez [!UICONTROL **Ajouter les principaux noeuds avant ce noeud**].

   Les 3 premiers noeuds qui se trouvent avant ce noeud dans le parcours sont ajoutés et chacun d’eux est connecté au noeud que vous avez sélectionné en tant que branche distincte.

#### Ajout de noeuds supérieurs entre les noeuds existants

Vous pouvez ajouter les 3 premiers noeuds situés entre deux noeuds existants :

1. Cliquez avec le bouton droit de la souris sur la flèche entre les 2 noeuds où vous souhaitez ajouter les 3 premiers noeuds du parcours.

1. Sélectionnez [!UICONTROL **Ajouter les principaux noeuds**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   Les 3 premiers noeuds sont ajoutés entre les 2 noeuds existants et chacun d’eux est connecté en tant que branche distincte.

### Réorganiser les noeuds

Les parcours dans le canevas de Parcours se composent d’un graphique flexible de noeuds et de flèches représentant toute combinaison d’événements, d’éléments de dimension et de filtres.

Vous pouvez faire glisser des noeuds sur la zone de travail pour réorganiser les événements et les conditions du parcours. Comme vous le faites, les données sont mises à jour en conséquence.

### Combiner des noeuds

Un noeud combiné dans le canevas de Parcours est un point unique dans le parcours utilisateur (noeud) qui contient au moins 2 composants qui sont unis par le biais de la logique.

#### Créer des noeuds combinés

Vous pouvez effectuer l’une des opérations suivantes pour créer des noeuds combinés dans le canevas de Parcours :

* Dans le rail de gauche, faites glisser un seul composant sur un noeud de la zone de travail.

* Dans le rail de gauche, faites glisser plusieurs composants simultanément sur un noeud de la zone de travail.

* Dans le rail de gauche, faites glisser plusieurs composants simultanément sur une zone vierge de la zone de travail tout en maintenant la touche Maj enfoncée.

* Sur la zone de travail, sélectionnez les noeuds à combiner, cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés, puis sélectionnez **Combiner**.<!--Is there a limit on how many you can combine? -->

#### Logique lors de la combinaison de noeuds

La logique appliquée aux noeuds lorsqu’ils sont combinés diffère selon les types de composants que vous combinez, comme suit :

>[!TIP]
>
>Vous pouvez afficher la logique d’un noeud combiné en cliquant avec le bouton droit de la souris sur le noeud, puis en sélectionnant [!UICONTROL **Créer un filtre à partir du noeud**]. La logique est affichée dans la section [!UICONTROL **Définition**] .


| Types de composants à combiner | Logique (opérateur) utilisée |
|---------|----------|
| Mesure + mesure | Associé à l’opérateur OU |
| DIMENSION + DIMENSION | Associé à l’opérateur OU |
| Filtre + Filtre | Associé à AND |
| Dimension + Mesure, période ou filtre | Associé à AND |
| Période + Mesure, filtre ou Dimension | Associé à AND |
| Filtre + Mesure, période ou Dimension | Associé à AND |

### Connexion des noeuds

Vous pouvez connecter des noeuds qui se trouvent déjà sur la zone de travail ou connecter un noeud lors de son ajout à la zone de travail.

#### Flèches entre les noeuds

Les noeuds sont reliés par une flèche. La direction et la largeur de la flèche ont toutes deux une signification :

* **Direction** : indique la séquence d’événements du parcours

* **Largeur** : indique le volume en pourcentage d’un noeud à un autre

#### Logique lors de la connexion des noeuds

Lorsque vous connectez des noeuds dans le canevas de Parcours, ils sont connectés à l’aide de l’opérateur ALORS . On parle également de [filtrage séquentiel](/help/components/filters/seg-sequential-build.md).

Les noeuds sont connectés en tant que &quot;chemin d’accès final&quot;, ce qui signifie que les visiteurs sont comptabilisés tant qu’ils passent finalement d’un noeud à l’autre, indépendamment des événements se produisant entre les 2 noeuds.

Vous pouvez afficher la logique des noeuds connectés en cliquant avec le bouton droit de la souris sur le noeud, puis en sélectionnant [!UICONTROL **Créer un filtre à partir du noeud**]. La logique est affichée dans la section [!UICONTROL **Définition**] .

#### Connexion à des noeuds existants

Les parcours ne peuvent pas être circulaires, en boucle vers les noeuds précédemment connectés.

Pour connecter des noeuds dans la zone de travail de Parcours :

1. Sur la zone de travail, placez le pointeur de la souris sur le noeud qui apparaît en premier dans la séquence de parcours à laquelle vous souhaitez vous connecter à un autre noeud.

   4 points bleus apparaissent de chaque côté du noeud sélectionné.

1. Faites glisser l’un des 4 points bleus sur les 4 côtés du noeud auquel vous souhaitez vous connecter.

   Une flèche s’affiche, connectant les 2 noeuds. Pour plus d’informations, voir [Flèches entre les noeuds](#arrows-between-nodes) .

#### Connexion de noeuds lors de l’ajout d’un noeud

Lors de l’ajout d’un noeud à la zone de travail, vous pouvez le placer entre deux noeuds connectés. Le noeud est ajouté au flux du parcours entre les 2 noeuds existants.

Pour plus d’informations, voir [Ajout d’un noeud](#add-a-node).

### Modification de la couleur d’un noeud ou d’une flèche

Vous pouvez personnaliser visuellement un parcours en modifiant la couleur de n’importe quel noeud ou flèche sur la zone de travail. Vous pouvez, par exemple, ajuster les couleurs pour indiquer un événement désirable ou indésirable.

L’option permettant de modifier la couleur est disponible pour les objets suivants de la zone de travail :

* Noeuds individuels

* Flèche entre les noeuds

Pour modifier la couleur d’un noeud ou d’une flèche :

1. Cliquez avec le bouton droit sur le noeud ou la flèche dont vous souhaitez modifier la couleur.

1. Sélectionnez [!UICONTROL **Changer de couleur**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Sélectionnez la couleur de votre choix.

   Les couleurs suivantes sont disponibles : <!--look into this interaction and color list-->

### Renommer un noeud ou une flèche

Lorsque vous faites glisser un composant vers une visualisation de zone de travail de Parcours, il crée un noeud portant le même nom que le nom du composant. Vous pouvez renommer le noeud pour qu’il corresponde mieux à l’étape du parcours qu’il représente.

L’option permettant de renommer est disponible pour les objets suivants de la zone de travail :

* Noeuds individuels

* Flèche entre les noeuds

Pour renommer un noeud :

1. Cliquez avec le bouton droit sur le noeud que vous souhaitez renommer.

1. Sélectionnez [!UICONTROL **Renommer**].

1. Indiquez un nouveau nom, puis appuyez sur Entrée.<!--is that right?-->

### Appliquer une ventilation

L’option permettant d’appliquer une ventilation à vos données est disponible pour les objets suivants de la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

* Flèche entre les noeuds

* Flèches multiples entre les noeuds

### Application d’une ventilation à un ou plusieurs noeuds ou flèches

1. Sélectionnez un ou plusieurs noeuds auxquels appliquer une ventilation, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

   Ou

   Sélectionnez une ou plusieurs flèches entre deux noeuds auxquels appliquer la ventilation, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

1. Sélectionnez [!UICONTROL **Ventilation**].

### Application d’une ventilation à un noeud individuel

Vous pouvez faire glisser une dimension du rail de gauche vers le noeud de la zone de travail dans laquelle vous souhaitez appliquer la ventilation.

Pour plus d’informations, voir [Ajout d’un noeud](#add-a-node).

### Créer une audience

L’option de création d’une audience est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

* Flèche entre les noeuds

* Flèches multiples entre les noeuds

Pour créer une audience :

1. Sélectionnez un ou plusieurs noeuds dans lesquels vous souhaitez créer une audience, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

   Ou

   Sélectionnez une ou plusieurs flèches entre deux noeuds où vous souhaitez créer une audience, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

1. Sélectionnez [!UICONTROL **Créer une audience**].

1. Continuez à créer et publier l’audience comme décrit dans la section [Créer et publier des audiences](/help/components/audiences/publish.md).

### Affichage des données de tendance

Vous pouvez afficher les données de tendance dans un graphique linéaire pour les objets dans la zone de travail du Parcours. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

L’option de tendance est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

* Flèches entre les noeuds

* Flèches multiples entre les noeuds

Pour afficher les données de tendance :

1. Sélectionnez un ou plusieurs noeuds pour lesquels afficher les données de tendance, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

   Ou

   Sélectionnez une ou plusieurs flèches entre deux noeuds pour lesquels vous souhaitez afficher les données de tendance, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

1. Sélectionnez [!UICONTROL **Tendance**].

### Dupliquer les noeuds

L’option à dupliquer est disponible pour les objets suivants sur la zone de travail :

* Plusieurs noeuds

Pour dupliquer des noeuds :

1. Sélectionnez plusieurs noeuds à dupliquer.

1. Cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés, puis sélectionnez [!UICONTROL **Dupliquer**].


### Ajout d’une contrainte temporelle entre les noeuds

Vous pouvez définir une contrainte temporelle entre les noeuds. Lorsqu’une contrainte temporelle est en place, si une personne suit le parcours défini mais prend plus de temps que la période allouée pour se déplacer entre les noeuds, elle est considérée comme étant hors du parcours.

L’option permettant d’ajouter une contrainte temporelle est disponible pour les objets suivants sur la zone de travail :

* Flèche entre les noeuds

Pour ajouter une contrainte d’heure :

1. Cliquez avec le bouton droit de la souris sur la flèche entre 2 noeuds, puis sélectionnez [!UICONTROL **Ajouter une contrainte temporelle**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

### Création d’un filtre à partir d’un noeud ou d’une flèche

Vous pouvez créer un nouveau filtre à partir d’un noeud ou d’une flèche dans un parcours. Une fois le filtre créé, vous pouvez l’utiliser n’importe où dans Analysis Workspace.

Les filtres créés à partir du canevas de Parcours utilisent le [filtrage séquentiel](/help/components/filters/seg-sequential-build.md). Cela signifie que le filtre utilise l’opérateur ALORS pour associer la séquence d’événements (c’est-à-dire le parcours) traversée par les personnes, menant au noeud ou à la flèche sélectionné. Tous les événements correspondant au noeud ou à la flèche sélectionné sont inclus dans le filtre.

Si vous créez un filtre basé sur un noeud qui comporte plusieurs chemins d’accès, tous les chemins d’accès sont inclus dans le filtre. Des chemins distincts sont unis par l’opérateur OU.

Pour créer un filtre :

1. Sur la zone de travail, cliquez avec le bouton droit de la souris sur le noeud ou la flèche à utiliser pour créer le filtre.

1. Sélectionnez [!UICONTROL **Créer un filtre à partir du noeud**] ou [!UICONTROL **Créer un filtre à partir de la flèche**].

   Le créateur de filtres s’affiche. Dans la section [!UICONTROL **Définition**] , la définition de filtre est créée en fonction du noeud ou de la flèche que vous avez sélectionné et de son contexte dans le parcours.

1. Indiquez un titre pour le filtre et apportez toute autre modification. Pour plus d’informations sur la création d’un filtre, voir [Créateur de filtres](/help/components/filters/filter-builder.md).

1. Sélectionnez [!UICONTROL **Enregistrer**] pour enregistrer le filtre.

### Suppression de noeuds

Vous pouvez supprimer un ou plusieurs noeuds à la fois au sein d’un parcours. Lorsque vous supprimez un noeud qui est connecté entre 2 noeuds au sein du parcours, les 2 noeuds restants sont directement connectés.

Pour supprimer des noeuds dans la zone de travail de Parcours :

1. Sélectionnez un ou plusieurs noeuds à supprimer, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

1. Sélectionnez [!UICONTROL **Supprimer**].

### Suppression des flèches entre les noeuds

Vous pouvez supprimer une ou plusieurs flèches à la fois au sein d’un parcours. Lorsque vous supprimez une flèche entre deux noeuds, les noeuds ne sont plus connectés. Si la flèche faisait partie d’un chemin plus long, le chemin est déconnecté.

Pour supprimer des flèches entre les noeuds dans la zone de travail de Parcours :

1. Sélectionnez une ou plusieurs flèches entre deux noeuds à supprimer, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

1. Sélectionnez [!UICONTROL **Supprimer**].


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## Ouvrir un parcours à partir de Journey Optimizer


Dans Journey Optimizer, ouvrez le parcours que vous souhaitez analyser dans la zone de travail du Parcours.

1. Sélectionnez [!UICONTROL **Analyser dans CJA**]. <!-- ?? -->
