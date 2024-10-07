---
description: Configurer une visualisation de la zone de travail du parcours
title: Zone de travail du parcours
feature: Visualizations
role: User
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: cbe713c08269fd3cc4e1076181020ff3fdc947b3
workflow-type: tm+mt
source-wordcount: '6391'
ht-degree: 1%

---

# Configurer une visualisation de la zone de travail du parcours

{{release-limited-testing}}

La visualisation du canevas de Parcours vous permet d’analyser et d’obtenir des informations détaillées sur les parcours que vous fournissez à vos utilisateurs et clients.

![Canevas de Parcours](assets/journey-canvas.png)

## Vue d’ensemble de la zone de travail du parcours

Pour en savoir plus sur le canevas de Parcours, voir [Aperçu du canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) , notamment :

* Principales fonctionnalités

* Informations potentielles

* Différences entre le canevas de Parcours et les abandons

* Détails sur l’analyse des parcours Journey Optimizer

* Et plus

## Commencer à créer une visualisation de zone de travail de Parcours

1. Ajoutez un panneau vierge à votre projet, sélectionnez l’icône [!UICONTROL **Visualisations**] dans le rail de gauche, puis faites glisser la visualisation ![GraphPathing](/help/assets/icons/Branch3.svg) [!UICONTROL **Canevas de Parcours**] dans le panneau.

   Ou

   Ajoutez une visualisation de canevas de Parcours de l’une des manières décrites dans la section [Ajouter des visualisations à un panneau](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) de la [présentation des visualisations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   ![Configuration du canevas de Parcours](assets/journey-canvas-configure.png)

1. Indiquez les informations de base suivantes pour configurer le canevas de Parcours :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Mesure de Principal**] | Détermine la mesure utilisée lors du calcul des valeurs de pourcentage et de nombre sur chaque noeud du parcours. <p>**Remarque** : La portée des données incluses dans chaque valeur de pourcentage et de nombre est déterminée par la mesure que vous choisissez dans le champ **[!UICONTROL Conteneur de canevas de Parcours]**. Par exemple, si **[!UICONTROL Person]** est défini comme conteneur, les statistiques affichées dans le parcours s’étendent sur plusieurs sessions pour une personne donnée. Si **[!UICONTROL Session]** est défini comme conteneur, les statistiques affichées dans le parcours sont contraintes à une seule session définie pour une personne donnée.</p><p>Prenons les exemples suivants :</p><ul><li>Si _Personnes_ est la mesure principale et que _Personne_ est le conteneur, seules les personnes qui ont un événement qui correspond aux critères de chaque noeud successif du parcours se déplacent tout au long du parcours. Les abandons surviennent sur un noeud lorsqu’une personne n’est jamais arrivée à l’un des noeuds suivants immédiats du parcours. Ils ont peut-être effectué d’autres actions sur le site, mais ils ne remplissaient pas les critères définis par l’un des noeuds qui suivent immédiatement.</li><li>Si _Personnes_ est la mesure principale et que _Session_ est le conteneur, seules les personnes qui ont un événement qui correspond aux critères de chaque noeud dans le parcours au cours d’une seule session se déplacent tout au long du parcours. Les abandons surviennent sur un noeud lorsqu’une personne n’est jamais arrivée à l’un des noeuds suivants immédiats du parcours au cours d’une seule session. Ils ont peut-être effectué d’autres actions sur le site au cours de la session, mais ils ne remplissaient pas les critères définis par l’un des noeuds qui suivent immédiatement.</li></ul> <p>La mesure principale affecte les aspects suivants de la visualisation du canevas de Parcours :</p><ul><li>Nombre total affiché sur chaque noeud.  <p>Par exemple, si Événements est la mesure principale, chaque noeud affiche le nombre de personnes qui ont eu un événement correspondant aux critères de ce noeud (et chaque noeud précédent qui y a mené dans le parcours).</p></li><li>Pourcentage affiché sur chaque noeud. (Une fois la visualisation créée, vous pouvez utiliser le menu déroulant **[!UICONTROL Valeur en pourcentage]** pour choisir d’afficher le pourcentage du total, le pourcentage du noeud précédent ou le pourcentage du noeud de départ.)</li><p>Par exemple, si Événements est la mesure principale, chaque noeud affiche le pourcentage de personnes ayant un événement qui correspond aux critères de ce noeud (et chaque noeud précédent qui le dirige dans le parcours).</p></li><li>Lorsqu’une dimension est ajoutée à la visualisation, les 3 premiers noeuds de la visualisation sont ajoutés, en fonction de la mesure principale.</li></ul> |
   | [!UICONTROL **Deuxième mesure**] | Détermine la mesure secondaire utilisée lors du calcul des valeurs de pourcentage et de nombre sur chaque noeud du parcours. La mesure secondaire est facultative. <p>**Remarque** : La portée des données incluses dans chaque valeur de pourcentage et de nombre est déterminée par la mesure que vous choisissez dans le champ **[!UICONTROL Conteneur de canevas de Parcours]**. Par exemple, si **[!UICONTROL Person]** est défini comme conteneur, les statistiques affichées dans le parcours s’étendent sur plusieurs sessions pour une personne donnée. Si **[!UICONTROL Session]** est défini comme conteneur, les statistiques affichées dans le parcours sont contraintes à une seule session définie pour une personne donnée.</p><p>Lorsqu’une mesure secondaire est sélectionnée, elle affecte les aspects suivants de la visualisation du canevas de Parcours :</p><ul><li>Nombre total affiché sur chaque noeud sous la mesure principale. <p>Par exemple, si Comptes est la mesure secondaire, le nombre de comptes s’affiche sur le noeud pour toutes les personnes ayant atteint ce noeud si seules ces personnes, chaque noeud affiche le nombre de sessions ayant atteint ce noeud dans le parcours.</p></li><li>Pourcentage affiché sur chaque noeud sous la mesure principale. (Une fois la visualisation créée, vous pouvez choisir d’afficher le pourcentage du total ou du noeud de départ.)</li><p>Par exemple, si Sessions est la mesure secondaire, chaque noeud affiche le pourcentage de sessions ayant atteint ce noeud dans le parcours (le pourcentage du total ou du noeud de départ).</p></li></ul> |
   | [!UICONTROL **parcours Journey Optimizer**]<!-- name? --> | Sélectionnez le parcours Journey Optimizer que vous souhaitez utiliser comme base de votre analyse dans la zone de travail du Parcours. Les parcours avec l’un des états suivants sont disponibles : En ligne, Arrêté ou Terminé. <p>Vous pouvez également laisser cette option vide si vous souhaitez créer un canevas vierge à partir duquel créer votre analyse dans Analysis Workspace.</p> <p>Lorsque vous analysez un parcours Journey Optimizer dans un canevas de Parcours, le parcours s’affiche avec le même ordre, la même séquence et la même structure que dans Journey Optimizer. Pour plus d’informations, reportez-vous à la section [Analyse des parcours Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) dans la [présentation du canevas de Parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Remarque** : Cette option s’affiche uniquement lorsque des données Journey Optimizer sont détectées dans la même vue de données que celle sélectionnée dans le panneau Analysis Workspace dans lequel vous ajoutez la visualisation. Pour plus d’informations sur la modification de la vue de données sur un panneau dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Facultatif) Sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez les informations suivantes :

   | Champ | Fonction |
   |---------|----------|
   | [!UICONTROL **Conteneur de canevas de Parcours**] | Sélectionnez le conteneur sur lequel vous souhaitez vous concentrer tout au long du parcours. Le conteneur que vous choisissez détermine la portée des données capturées dans le parcours. Cela affecte les statistiques affichées dans la visualisation. (Si les noms de vos conteneurs diffèrent des noms par défaut affichés ci-dessous, ils ont été personnalisés dans votre vue de données.)<ul><li>**Session :** Contraint les statistiques de la visualisation à appartenir à une seule session définie pour une personne donnée. Cela signifie que les nombres et les pourcentages qui apparaissent sur chaque noeud (en fonction des mesures primaires et secondaires) doivent se produire au cours d’une seule session pour chaque personne. En d’autres termes, une personne peut être représentée plusieurs fois en un seul parcours.<p>Ce conteneur utilise la mesure Sessions .</p></li><li>**Personne :** (Par défaut) Permet aux statistiques de la visualisation d’étendre plusieurs sessions pour une personne donnée. Cela signifie que les nombres et les pourcentages qui apparaissent sur chaque noeud (en fonction des mesures primaires et secondaires) peuvent se produire sur n’importe quel nombre de sessions, à condition que les sessions appartiennent à la même personne. En d’autres termes, une personne ne peut être représentée qu’une seule fois dans un seul parcours.<p>Ce conteneur utilise la mesure Personnes .</p></li></ul> |

1. Sélectionnez la [!UICONTROL **Version**].

   Si vous disposez de Journey Optimizer et que vous avez sélectionné un parcours Journey Optimizer, le parcours s’affiche avec le même ordre, la même séquence et la même structure que dans Journey Optimizer.

   <!-- add screen shot -->

   Si vous ne disposez pas de Journey Optimizer ou si vous n’avez pas sélectionné de parcours Journey Optimizer, un canevas vierge s’affiche où vous pouvez commencer à ajouter des noeuds au parcours.

   <!-- add screen shot -->

1. Que vous créiez une nouvelle analyse à partir d’un canevas vierge ou que vous analysiez un parcours Journey Optimizer, vous pouvez configurer le parcours comme décrit dans [Configuration des paramètres de visualisation](#configure-visualization-settings).


## Configuration des paramètres de visualisation

Diverses options de configuration sont disponibles dans l’en-tête du canevas de Parcours.

Pour configurer les paramètres de la visualisation du canevas de Parcours :

1. Dans Analysis Workspace, ouvrez une visualisation de canevas de Parcours existante ou [commencez à en créer une](#begin-building-a-journey-canvas-visualization).

   Les options permettant de configurer la visualisation du canevas de Parcours sont disponibles dans l’en-tête :

   ![Options d’en-tête de canevas de Parcours](assets/journey-canvas-header.png)

1. Configurez l’un des paramètres suivants qui s’affichent dans la partie supérieure de la visualisation :

   | Paramètre | Fonction |
   |---------|----------|
   | [!UICONTROL **Type de noeud**] | Permet de configurer les types de noeud qui s’affichent dans la visualisation.<p>Pour masquer un type de noeud de la visualisation, sélectionnez (x) en regard du type de noeud ou désélectionnez-le dans le menu déroulant. Pour afficher un type de noeud masqué, sélectionnez-le dans le menu déroulant. (Les noeuds ne sont pas supprimés du parcours lorsque vous les masquez. Pour plus d’informations sur la suppression d’un noeud, voir [Suppression de noeuds](#delete-nodes).)</p><p>Ce champ peut contenir les types de noeuds Journey Optimizer ([!UICONTROL **Lecture de segment**], [!UICONTROL **Fin**], etc.) et les types de noeuds de composant ([!UICONTROL **Dimension**], [!UICONTROL **Mesure**], [!UICONTROL **Filtre**] et [!UICONTROL **Plage de dates**]), comme suit : </p><ul><li>**Seuls les types de noeuds Journey Optimizer sont affichés** si le parcours est un parcours Journey Optimizer qui n’a pas été modifié dans le canevas de Parcours avec l’une des modifications suivantes :<ul><li>Ajout ou suppression de noeuds</li><li>Ajout ou suppression de flèches</li><li>Modification des composants sur un noeud</li></ul></li><li>**Les types de noeuds Journey Optimizer et les types de noeuds de composant sont affichés** si le parcours est un parcours Journey Optimizer qui a été modifié dans le canevas de Parcours avec l’une des modifications suivantes :<ul><li>Ajout ou suppression de noeuds</li><li>Ajout ou suppression de flèches</li><li>Modification des composants sur un noeud</li></ul></li><li>**Seuls les types de noeuds de composant sont affichés** si le parcours n’est pas un parcours Journey Optimizer.</li></ul></p> |
   | [!UICONTROL **Valeur en pourcentage**] | Pourcentage affiché sur chaque noeud du parcours.<p>![valeur en pourcentage](assets/journey-canvas-percentage.png)</p> <p>Tenez compte de ce qui suit lors de la configuration des valeurs en pourcentage affichées sur les noeuds du parcours :</p><ul><li>Un pourcentage est affiché sur chaque noeud pour la mesure principale. Un pourcentage s’affiche également pour la mesure secondaire si elle est configurée. (Pour plus d’informations sur les paramètres de mesure primaire et secondaire, voir [Commencer la création d’une visualisation de canevas de Parcours](#begin-building-a-journey-canvas-visualization).)</li><li>Les pourcentages comprennent toutes les personnes ou sessions incluses dans la vue de données au cours de la période du panneau. L’utilisation de _people_ ou de _sessions_ dépend du paramètre de conteneur. (Pour plus d’informations sur le paramètre de conteneur, voir [Commencer la création d’une visualisation de canevas de Parcours](#begin-building-a-journey-canvas-visualization).)</li></ul> <p>Choisissez l’une des options suivantes :</p> <ul><li>[!UICONTROL **Pourcentage du noeud de départ**] : calcule les pourcentages affichés sur chaque noeud par rapport au noeud de départ. Les pourcentages sont basés sur la mesure principale et secondaire que vous avez sélectionnée. <p>Un _noeud de départ_ est un noeud qui ne comporte aucun noeud connecté avant lui.</p><p>Un parcours peut contenir plusieurs noeuds de départ. Cependant, [!UICONTROL **Pourcentage du total**] est utilisé si le parcours contient 2 noeuds de départ ou plus qui mènent à un noeud commun. Si vous souhaitez utiliser [!UICONTROL **Pourcentage du noeud de départ**], mettez à jour le parcours afin que chaque noeud du parcours puisse être redirigé vers un seul noeud de départ.</p></li><li>[!UICONTROL **Pourcentage du noeud précédent**] : calcule les pourcentages affichés sur chaque noeud par rapport au noeud précédent. Les pourcentages sont basés sur la mesure principale et secondaire que vous avez sélectionnée.</li><li>[!UICONTROL **Pourcentage du total**] : calcule les pourcentages affichés sur chaque noeud par rapport à toutes les données de la vue de données. Les pourcentages sont basés sur la mesure principale et secondaire que vous avez sélectionnée.</li></ul> |
   | [!UICONTROL **Paramètres de flèche**] | Les flèches qui apparaissent entre les noeuds de la zone de travail de Parcours peuvent être configurées pour afficher des libellés et des valeurs personnalisés. <p>![paramètres de flèche](assets/journey-canvas-arrow-settings.png)</p><p>_Les libellés_ sont des noms personnalisés qui apparaissent sur les flèches. Une seule étiquette s’affiche sur une flèche donnée. Les libellés peuvent être l’un des suivants. Ils s’affichent dans cet ordre de préférence :</p><ol><li>Un nom personnalisé ajouté à partir du canevas de Parcours (comme décrit dans [Ajouter ou mettre à jour une étiquette sur une flèche ](#add-or-update-a-label-on-an-arrow))</li><li>Libellé Journey Optimizer</li><li>Une condition Journey Optimizer</li></ol><p>Les _valeurs_ sont les nombres et les pourcentages qui apparaissent sur les flèches, et indiquent les personnes ou les sessions qui sont passées d’un noeud à un autre dans le parcours. (En d&#39;autres termes, ceux qui n&#39;ont pas quitté le parcours à une étape donnée.) </p><p>Les options suivantes sont disponibles pour les parcours qui ne proviennent pas de Journey Optimizer et pour les parcours Journey Optimizer qui n’ont pas été modifiés de manière significative dans le canevas de Parcours : (Les modifications importantes incluent l’ajout ou la suppression de noeuds, l’ajout ou la suppression de flèches ou la modification des composants d’un noeud.)</p><ul><li>[!UICONTROL **Aucune étiquette**] : aucune étiquette n’est affichée sur les flèches du parcours. </br> Cette option est disponible uniquement si le parcours a été modifié dans </li><li>[!UICONTROL **Étiquettes uniquement**] : les étiquettes s’affichent sur les flèches du parcours.</li></ul><p>Les options suivantes sont disponibles pour les parcours Journey Optimizer qui ont été modifiés de manière significative dans le canevas de Parcours : (Les modifications significatives incluent l’ajout ou la suppression de noeuds, l’ajout ou la suppression de flèches, ou la modification des composants d’un noeud.)(**Remarque** : ces options s’affichent uniquement lorsque des données Journey Optimizer sont détectées dans la même vue de données que celle sélectionnée dans le panneau Analysis Workspace dans lequel vous ajoutez la visualisation. Pour plus d’informations sur la modification de la vue de données sur un panneau dans Analysis Workspace, voir [Présentation d’Analysis Workspace](/help/analysis-workspace/home.md).)</p><ul><li>[!UICONTROL **Aucune étiquette ou valeur**] : aucune étiquette ou valeur ne s’affiche sur les flèches du parcours.</li><li>[!UICONTROL **Libellés uniquement**] : seuls les libellés s’affichent sur les flèches du parcours. Les valeurs ne sont pas affichées.</li><li>[!UICONTROL **Valeurs uniquement**] : seules les valeurs s’affichent sur les flèches du parcours. Les libellés ne s’affichent pas.</li><li>[!UICONTROL **Valeurs et libellés**] : les libellés et les valeurs sont affichés sur les flèches du parcours.</li></ul> |
   | [!UICONTROL **Afficher l’abandon**] | Les données sur les abandons affichent un pourcentage et un nombre sortant de chaque noeud du parcours. Les données d’abandon sont basées sur la mesure associée aux paramètres de conteneur du parcours ; elles ne sont pas basées sur la mesure principale ou secondaire. <p>![abandon](assets/journey-canvas-fallout.png)</p><p>Par défaut, le conteneur est _Personne_, de sorte que la mesure utilisée pour les données d’abandon est _Personnes_. Si le conteneur est remplacé par _Session_, la mesure utilisée pour les données d’abandon est _Sessions_, etc.</p><p>Par exemple, avec _Personne_ comme paramètre de conteneur, l’abandon indique le pourcentage et le nombre de personnes sur chaque noeud du parcours qui n’ont jamais atteint l’un des noeuds suivants immédiats. Ils ont peut-être effectué d’autres actions sur le site, mais ils ne remplissaient pas les critères définis par l’un des noeuds qui suivent immédiatement.</p> <p>Pour plus d’informations sur le paramètre de conteneur de canevas de Parcours, voir [Commencer la création d’une visualisation de canevas de Parcours](#begin-building-a-journey-canvas-visualization). |
   | **Commandes de zoom** | Les commandes de zoom suivantes sont disponibles dans le coin supérieur droit de la zone de travail :<ul><li>**Zoom avant** ![icône de zoom avant](assets/zoom-in-icon.png) : agrandit des zones spécifiques de la visualisation.<p>Vous pouvez également utiliser les commandes de la souris, telles que le pincement sur un pavé tactile.</p></li><li>**Zoom arrière** ![icône de zoom arrière](assets/zoom-out-icon.png) : réduit la visualisation pour permettre plus d’espace sur la zone de travail.<p>Vous pouvez également utiliser les commandes de la souris, telles que le pincement sur un pavé tactile.</p></li><li>**Plein écran** ![Icône d’ajustement d’écran](assets/fill-screen-icon.png) : permet de régler les paramètres actuels de zoom et de panoramique pour remplir l’écran avec la visualisation complète.</li></ul><p>Pour effectuer un panoramique sur la zone de travail après avoir effectué un zoom avant ou arrière, cliquez sur la souris et faites glisser le curseur vers l’emplacement de votre choix.</p> |

1. Passez à [Ajouter des noeuds](#add-nodes).

## Ajout de noeuds

Les noeuds d’une visualisation de zone de travail de Parcours représentent les événements ou les actions d’un parcours utilisateur.

Vous pouvez créer des noeuds de la manière suivante : en faisant glisser des composants Workspace du rail de gauche vers la zone de travail ; en autorisant la zone de travail de Parcours à choisir les noeuds suivants ou précédents en fonction des noeuds existants ; ou en dupliquant des noeuds existants.

### Faire glisser des composants depuis le rail de gauche

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
   | Dimension | Un noeud existant | Une ventilation est automatiquement appliquée au noeud avec les 5 premiers éléments de dimension affichés.<!--what happens if you hold Shift?--><p>Pour afficher la ventilation dans une nouvelle visualisation de tableau à structure libre, sélectionnez le lien [!UICONTROL **Ouvrir dans un tableau à structure libre**] sur le noeud.</p> |
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
   | Composants multiples | Zone vierge du canevas | **Si aucun des composants n’est une dimension :**<p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés, sans être connecté aux noeuds existants.</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. </p><p>**Si l’un des composants que vous ajoutez est des dimensions :**</p><p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés, sans être connecté aux noeuds existants.</p><p>Une seule dimension peut être ajoutée à la fois. Lorsque la dimension est ajoutée, 3 noeuds sont créés pour les 3 premiers éléments de dimension dans lesquels le composant a été déposé.</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. Les trois premiers éléments de dimension sont combinés avec chaque noeud. (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p> |
   | Composants multiples | Un noeud existant | Tous les composants sont combinés avec le noeud existant.<p>Si l’un des composants que vous ajoutez est des dimensions, les 3 premiers éléments de dimension sont combinés avec le noeud .</p> <p>Une seule dimension peut être ajoutée à la fois.</p> |
   | Composants multiples | Une flèche qui connecte 2 noeuds existants | **Si aucun des composants n’est une dimension :**<p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés et chaque noeud est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. (Les composants doivent être du même type pour être combinés en un seul noeud.) (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p><p>**Si l’un des composants que vous ajoutez est des dimensions :**</p><p>Chaque composant s’affiche sous la forme d’un noeud distinct où les composants ont été déposés et chaque noeud est connecté aux deux noeuds existants.</p><p>Une seule dimension peut être ajoutée à la fois. Lorsque la dimension est ajoutée, 3 noeuds sont créés pour les 3 premiers éléments de la dimension qui suivent le premier événement après le premier noeud (de personnes/sessions qui atteignent finalement le deuxième noeud). Chaque noeud est connecté aux deux noeuds existants. (Voir [Connexion aux noeuds](#connect-nodes) pour plus d’informations.)</p><p>Maintenez la touche Maj enfoncée lorsque vous déposez les composants sur la zone de travail pour les ajouter sous la forme d’un noeud combiné. Les 3 premiers éléments de dimension sont combinés avec chaque noeud et chaque noeud est connecté aux deux noeuds existants. (Voir [Combiner des noeuds](#combine-nodes) pour plus d’informations.)</p> |

   Les noeuds s’affichent sous la forme d’une boîte rectangulaire avec les informations suivantes :

   * Nom du composant

   * Type de composant (comme une mesure ou une dimension)

   * Statistiques des mesures de Principal (total et pourcentage)

   * Statistiques des mesures Secondaire (total et pourcentage)

   Un noeud pulsant ou brillant indique que les données sont chargées pour ce noeud.

1. Répétez cette procédure pour continuer à ajouter des noeuds afin de créer votre parcours.

1. Continuez à personnaliser le parcours comme décrit dans les sections ci-dessous. Vous pouvez connecter des noeuds, renommer des noeuds, appliquer des ventilations, créer des audiences, ajouter des contraintes de temps, etc.

### Afficher les principaux noeuds en fonction des noeuds existants

Vous pouvez afficher automatiquement les principaux noeuds en fonction des noeuds déjà présents dans la zone de travail. Vous pouvez ajouter les noeuds supérieurs au canevas de Parcours ou les afficher dans un tableau à structure libre.

Cette option est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Flèche entre les noeuds

#### Afficher les noeuds supérieurs après un noeud existant

Vous pouvez sélectionner un noeud et afficher les principaux éléments de dimension qui lui succèdent dans le parcours. Vous pouvez ajouter les 3 premiers éléments de dimension au canevas de Parcours sous la forme de noeuds distincts, ou afficher tous les principaux éléments de dimension dans un tableau à structure libre.

1. Cliquez avec le bouton droit de la souris sur le noeud dans lequel vous souhaitez afficher les principaux éléments de dimension qui le suivent dans le parcours.

   Le noeud ne peut pas comporter de noeuds existants qui en sortent dans le parcours.

1. Sélectionnez [!UICONTROL **Afficher les principaux noeuds après ce noeud**].

1. Sélectionnez l’emplacement d’affichage des éléments de dimension :

   * [!UICONTROL **Dans la zone de travail de Parcours**] : ajoute les 3 premiers noeuds à la zone de travail qui suivent ce noeud dans le parcours. Chaque noeud est connecté au noeud que vous avez sélectionné comme branche distincte sur la zone de travail.

   * [!UICONTROL **Dans un tableau à structure libre**] : crée une visualisation de tableau à structure libre présentant tous les éléments de dimension principaux qui se trouvent après ce noeud dans le parcours.

1. Sélectionnez la dimension souhaitée dans la liste des dimensions.

   Selon ce que vous avez choisi à l’étape précédente, les 3 premiers éléments de dimension sont ajoutés au canevas sous la forme de 3 noeuds distincts, ou tous les principaux éléments de dimension sont affichés dans un tableau à structure libre.

#### Afficher les noeuds supérieurs avant un noeud existant

Vous pouvez sélectionner un noeud et afficher les principaux éléments de dimension qui le précèdent dans le parcours. Vous pouvez ajouter les 3 premiers éléments de dimension au canevas de Parcours sous la forme de noeuds distincts, ou afficher tous les principaux éléments de dimension dans un tableau à structure libre.

1. Cliquez avec le bouton droit sur le noeud où vous souhaitez afficher les principaux éléments de dimension qui le précèdent dans le parcours.

   Ce noeud ne peut pas contenir de noeuds existants dans le parcours.

1. Sélectionnez [!UICONTROL **Afficher les principaux noeuds avant ce noeud**].

1. Sélectionnez l’emplacement d’affichage des éléments de dimension :

   * [!UICONTROL **Dans la zone de travail de Parcours**] : ajoute les 3 premiers noeuds à la zone de travail qui se trouvent avant ce noeud dans le parcours. Chaque noeud est connecté au noeud que vous avez sélectionné comme branche distincte sur la zone de travail.

   * [!UICONTROL **Dans un tableau à structure libre**] : crée une visualisation de tableau à structure libre présentant tous les éléments de dimension principaux qui se trouvent avant ce noeud dans le parcours.

1. Sélectionnez la dimension souhaitée dans la liste des dimensions.

   Selon ce que vous avez choisi à l’étape précédente, les 3 premiers éléments de dimension sont ajoutés au canevas sous la forme de 3 noeuds distincts, ou tous les principaux éléments de dimension sont affichés dans un tableau à structure libre.

#### Afficher les noeuds supérieurs entre les noeuds existants

Vous pouvez sélectionner une flèche et afficher les principaux éléments de dimension qui se trouvent entre deux noeuds existants dans le parcours. Vous pouvez ajouter les 3 premiers éléments de dimension au canevas de Parcours sous la forme de noeuds distincts, ou afficher tous les principaux éléments de dimension dans un tableau à structure libre.

1. Cliquez avec le bouton droit de la souris sur la flèche entre les deux noeuds où vous souhaitez afficher les principaux éléments de dimension.

1. Sélectionnez [!UICONTROL **Afficher les principaux noeuds entre ces noeuds**].

1. Sélectionnez l’emplacement d’affichage des éléments de dimension :

   * [!UICONTROL **Dans la zone de travail de Parcours**] : ajoute les 3 premiers noeuds à la zone de travail qui se trouvent entre les 2 noeuds existants. Chaque noeud est connecté aux noeuds environnants en tant que branche distincte sur la zone de travail.

   * [!UICONTROL **Dans un tableau à structure libre**] : crée une visualisation de tableau à structure libre présentant tous les éléments de dimension principaux compris entre les 2 noeuds existants.

1. Sélectionnez la dimension souhaitée dans la liste des dimensions.

   Selon ce que vous avez choisi à l’étape précédente, les 3 premiers éléments de dimension sont ajoutés au canevas sous la forme de 3 noeuds distincts, ou tous les principaux éléments de dimension sont affichés dans un tableau à structure libre.

### Dupliquer les noeuds

L’option à dupliquer est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

Pour dupliquer des noeuds :

1. Sélectionnez un ou plusieurs noeuds à dupliquer.

   Pour sélectionner plusieurs noeuds, maintenez la touche Commande (sur Mac) ou Ctrl (sur Windows) enfoncée.

1. Cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés, puis sélectionnez [!UICONTROL **Dupliquer**].

## Concevoir le parcours

L’ordre des noeuds et les connexions entre eux affectent les données du canevas de Parcours. Les parcours doivent refléter visuellement et précisément la séquence d’événements sur lesquels vous souhaitez générer des rapports.

Une fois les noeuds ajoutés à la zone de travail, vous pouvez les réorganiser, les combiner, les connecter et ajouter des contraintes de temps entre eux.

### Réorganiser les noeuds

Les parcours dans le canevas de Parcours se composent d’un graphique flexible de noeuds et de flèches représentant toute combinaison d’événements, d’éléments de dimension et de filtres.

Vous pouvez faire glisser des noeuds sur la zone de travail pour réorganiser les événements et les conditions du parcours.

Lorsque vous réorganisez l’ordre des noeuds dans le parcours, les données sont mises à jour en conséquence.

### Combiner des noeuds

Un noeud combiné dans le canevas de Parcours est un point unique dans le parcours utilisateur (noeud) qui contient au moins 2 composants qui sont unis par le biais de la logique.

#### Créer des noeuds combinés

Vous pouvez effectuer l’une des opérations suivantes pour combiner des noeuds dans la zone de travail de Parcours :

* Dans le rail de gauche, faites glisser un seul composant sur un noeud de la zone de travail.

* Dans le rail de gauche, faites glisser plusieurs composants simultanément sur un noeud de la zone de travail.

* Dans le rail de gauche, faites glisser plusieurs composants simultanément sur une zone vierge de la zone de travail tout en maintenant la touche Maj enfoncée.

<!-- * On the canvas, select the nodes that you want to combine, right-click one of the selected nodes, then select **Combine**. Is there a limit on how many you can combine? -->

#### Logique lors de la combinaison de noeuds

La logique appliquée aux noeuds lorsqu’ils sont combinés diffère selon les types de composants que vous combinez, comme suit :

>[!TIP]
>
>Vous pouvez afficher la logique d’un noeud combiné en cliquant avec le bouton droit de la souris sur le noeud, puis en sélectionnant [!UICONTROL **Créer un filtre à partir du noeud**]. La logique est affichée dans la section [!UICONTROL **Définition**] .


| Types de composants à combiner | Logique (opérateur) utilisée |
|---------|----------|
| Mesure + mesure | Associé à l’opérateur OU |
| élément de Dimension + élément de Dimension (de la même dimension parent) | Associé à l’opérateur OU |
| élément de Dimension + élément de Dimension (de différentes dimensions parentes) | Associé à AND |
| Filtre + Filtre | Associé à AND |
| Dimension + Mesure, période ou filtre | Associé à AND |
| Période + Mesure, filtre ou Dimension | Associé à AND |
| Filtre + Mesure, période ou Dimension | Associé à AND |

### Connexion des noeuds

Vous pouvez connecter des noeuds qui se trouvent déjà sur la zone de travail ou connecter un noeud lors de son ajout à la zone de travail.

Vous connectez des noeuds pour définir la séquence d’événements du parcours.

#### Flèches entre les noeuds

Les noeuds sont reliés par une flèche. La direction et la largeur de la flèche ont toutes deux une signification :

* **Direction** : indique la séquence d’événements du parcours

* **Largeur** : indique le volume en pourcentage d’un noeud à un autre

  ![Orientation et largeur de la flèche](assets/journey-canvas-arrow-width.png)

#### Logique lors de la connexion des noeuds

Lorsque vous connectez des noeuds dans le canevas de Parcours, ils sont connectés à l’aide de l’opérateur ALORS . On parle également de [filtrage séquentiel](/help/components/filters/seg-sequential-build.md).

Les noeuds sont connectés en tant que &quot;chemin d’accès final&quot;, ce qui signifie que les visiteurs sont comptabilisés tant qu’ils passent finalement d’un noeud à l’autre, indépendamment des événements se produisant entre les 2 noeuds. Le temps alloué aux utilisateurs pour se déplacer le long du chemin est déterminé par le paramètre du conteneur. <!-- It can also be controlled by [adding a time constraint](#add-a-time-constraint-between-nodes). -->

Vous pouvez afficher la logique des noeuds connectés en cliquant avec le bouton droit de la souris sur le noeud, puis en sélectionnant [!UICONTROL **Créer un filtre à partir du noeud**]. La logique est affichée dans la section [!UICONTROL **Définition**] .

#### Connexion à des noeuds existants

Les parcours ne peuvent pas être circulaires, en boucle vers les noeuds précédemment connectés.

Pour connecter des noeuds dans la zone de travail de Parcours :

1. Dans une visualisation de canevas de Parcours, passez la souris sur le noeud qui vient en premier dans la séquence de parcours à laquelle vous souhaitez vous connecter à un autre noeud.

   4 points bleus apparaissent de chaque côté du noeud sélectionné.

1. Faites glisser l’un des 4 points bleus sur les 4 côtés du noeud auquel vous souhaitez vous connecter.

   Une flèche s’affiche, connectant les 2 noeuds. Pour plus d’informations, voir [Flèches entre les noeuds](#arrows-between-nodes) .

#### Connexion de noeuds lors de l’ajout d’un noeud

Lors de l’ajout d’un noeud à la zone de travail, vous pouvez le placer entre deux noeuds connectés. Le noeud est ajouté au flux du parcours entre les 2 noeuds existants.

Pour plus d’informations, voir [Ajout de noeuds](#add-nodes).

<!--

### Add a time constraint between nodes

>[!AVAILABILITY]
>
>This feature is not yet available.

You can set a time constraint between nodes. When a time constraint is in place, people are considered to have fallen out of the journey if they follow the defined journey but take longer than the allotted time period to move between the nodes.

The option to add a time constraint is available for the following objects on the canvas:

* The arrow between nodes

To add a time constraint:

1. In a Journey canvas visualization, right-click the arrow between 2 nodes, then select [!UICONTROL **Add time constraint**].

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Gestion des noeuds ou des flèches

<!--

### Change the color of a node or arrow

>[!AVAILABILITY]
>
>This feature is not yet available.

You can visually customize a journey by changing the color of any node or arrow on the canvas. For example, you could adjust colors to indicate a desirable or undesirable event.

The option to change the color is available for the following objects on the canvas:

* Individual nodes

* The arrow between nodes

To change the color of a node or arrow:

1. In a Journey canvas visualization, right-click the node or arrow whose color you want to change.

1. Select [!UICONTROL **Change color**]. 

1. Select the desired color. 

   The following colors are available: 

-->

### Renommer un noeud

Lorsque vous faites glisser un composant vers une visualisation de zone de travail de Parcours, il crée un noeud portant le même nom que le nom du composant. Vous pouvez renommer le noeud pour qu’il corresponde mieux à l’étape du parcours qu’il représente.

L’option permettant de renommer est disponible pour les objets suivants de la zone de travail :

* Noeuds individuels

Pour renommer un noeud :

1. Dans une visualisation de canevas de Parcours, cliquez avec le bouton droit sur le noeud que vous souhaitez renommer.

1. Sélectionnez [!UICONTROL **Renommer**].

1. Indiquez un nouveau nom, puis appuyez sur Entrée.<!--is that right?-->

### Ajouter ou mettre à jour un libellé sur une flèche

Les flèches qui apparaissent entre les noeuds de la zone de travail de Parcours peuvent être configurées pour afficher des libellés et des valeurs personnalisés.

Les libellés sont des noms personnalisés qui apparaissent sur les flèches. Une seule étiquette s’affiche sur une flèche donnée.

Pour plus d’informations sur les libellés et les valeurs qui apparaissent sur les flèches, voir &quot;Paramètres des flèches&quot; dans [ Configuration des paramètres de visualisation](#configure-visualization-settings).

L’option permettant d’ajouter ou de mettre à jour un libellé est disponible pour les objets suivants de la zone de travail :

* Flèche entre les noeuds

Pour ajouter un libellé à une flèche :

1. Dans une visualisation de canevas de Parcours, cliquez avec le bouton droit de la souris sur la flèche à l’endroit où vous souhaitez ajouter un libellé.

1. Sélectionnez **[!UICONTROL Ajouter une étiquette]**.

1. Saisissez un nom pour le libellé, puis appuyez sur Entrée.

   Si les paramètres de flèche sont actuellement configurés pour masquer les libellés, un message s’affiche vous invitant à afficher les libellés.

Pour mettre à jour un libellé existant sur une flèche :

1. Dans une visualisation de canevas de Parcours, cliquez avec le bouton droit de la souris sur la flèche à l’endroit où vous souhaitez ajouter un libellé.

1. Sélectionnez **[!UICONTROL Mettre à jour le libellé]**.

1. Saisissez un nom pour le libellé, puis appuyez sur Entrée.

   Si les paramètres de flèche sont actuellement configurés pour masquer les libellés, un message s’affiche vous invitant à afficher les libellés.

### Appliquer une ventilation

L’option permettant d’appliquer une ventilation à vos données est disponible pour les objets suivants de la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

* Flèche entre les noeuds

* Flèches multiples entre les noeuds

Tenez compte des points suivants lors de l’application d’une ventilation :

* Les ventilations sont appliquées à la mesure principale. La mesure secondaire n’est pas affectée.

* L’application d’une ventilation ne modifie pas le parcours. Il affiche simplement une ventilation des données pour le noeud sur lequel il est appliqué.

* Si un noeud comporte déjà une ventilation, l’application d’une nouvelle ventilation remplace celle existante.

* Les données de ventilation sont mises à jour si des modifications sont effectuées à un point antérieur du parcours.

#### Application d’une ventilation à un ou plusieurs noeuds ou flèches

1. Dans une visualisation de canevas de Parcours, sélectionnez un ou plusieurs noeuds auxquels vous souhaitez appliquer une ventilation, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

   Ou

   Dans une visualisation de canevas de Parcours, sélectionnez une ou plusieurs flèches entre deux noeuds auxquels vous souhaitez appliquer la ventilation, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

   Pour sélectionner plusieurs noeuds ou flèches, maintenez la touche Commande (sous Mac) ou Ctrl (sous Windows) enfoncée.

1. Sélectionnez [!UICONTROL **Ventilation**].

1. Sélectionnez l&#39;emplacement de la répartition :

   * [!UICONTROL **Dans la zone de travail de Parcours**]

   * [!UICONTROL **Dans une table à structure libre**]

1. Sélectionnez la dimension à utiliser pour la ventilation.

   Si vous choisissez d’afficher la ventilation dans la zone de travail du Parcours, les 5 premiers éléments de dimension s’affichent sur le noeud . Une option est disponible sur le noeud pour ouvrir la ventilation dans un tableau à structure libre.

   Si vous choisissez d’afficher la ventilation dans un tableau à structure libre, les principaux éléments de dimension s’affichent dans un nouveau tableau à structure libre immédiatement au-dessus de la visualisation du canevas de Parcours.

#### Application d’une ventilation à un noeud individuel

Vous pouvez faire glisser une dimension du rail de gauche vers le noeud de la zone de travail dans laquelle vous souhaitez appliquer la ventilation.

Pour plus d’informations, voir [Ajout de noeuds](#add-nodes).

#### Suppression d’une ventilation

Pour supprimer une ventilation qui a été appliquée :

1. Cliquez avec le bouton droit sur le noeud auquel est appliquée la ventilation.

1. Sélectionnez **[!UICONTROL Supprimer la ventilation]**.

### Créer une audience

L’option de création d’une audience est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

* Flèche entre les noeuds

* Flèches multiples entre les noeuds

Lorsque vous créez une audience à partir de plusieurs noeuds ou flèches, elle est associée à l’opérateur OU.

Pour créer une audience :

1. Dans une visualisation de canevas de Parcours, sélectionnez un ou plusieurs noeuds dans lesquels vous souhaitez créer une audience, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

   Ou

   Dans une visualisation de canevas de Parcours, sélectionnez une ou plusieurs flèches entre deux noeuds où vous souhaitez créer une audience, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

   Pour sélectionner plusieurs noeuds ou flèches, maintenez la touche Commande (sous Mac) ou Ctrl (sous Windows) enfoncée.

   >[!NOTE]
   >
   >Les audiences ne peuvent pas inclure de mesures calculées ou de mesures basées sur un [jeu de données de résumé](/help/data-views/summary-data.md). Si vous essayez de créer une audience à partir d’une zone de canevas de Parcours contenant une mesure calculée ou une mesure basée sur un jeu de données de résumé, la mesure calculée ne sera pas incluse dans la définition de l’audience.

1. Sélectionnez [!UICONTROL **Créer une audience à partir du noeud**] ou [!UICONTROL **Créer une audience à partir de la flèche**].

1. Continuez à créer et publier l’audience comme décrit dans la section [Créer et publier des audiences](/help/components/audiences/publish.md).

### Affichage des données de tendance

Vous pouvez afficher les données de tendance dans un graphique linéaire pour les objets dans la zone de travail du Parcours. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

L’option de tendance est disponible pour les objets suivants sur la zone de travail :

* Noeuds individuels

* Plusieurs noeuds

* Flèches entre les noeuds

* Flèches multiples entre les noeuds

Pour afficher les données de tendance :

1. Dans une visualisation de canevas de Parcours, sélectionnez un ou plusieurs noeuds pour lesquels vous souhaitez afficher les données de tendance, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

   Ou

   Dans une visualisation de canevas de Parcours, sélectionnez une ou plusieurs flèches entre deux noeuds pour lesquelles vous souhaitez afficher les données de tendance, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

   Pour sélectionner plusieurs noeuds ou flèches, maintenez la touche Commande (sous Mac) ou Ctrl (sous Windows) enfoncée.

1. Sélectionnez [!UICONTROL **Tendance**].

### Création d’un filtre à partir d’un noeud ou d’une flèche

Vous pouvez créer un nouveau filtre à partir d’un noeud ou d’une flèche dans un parcours. Une fois le filtre créé, vous pouvez l’utiliser n’importe où dans Analysis Workspace.

Les filtres créés à partir du canevas de Parcours utilisent le [filtrage séquentiel](/help/components/filters/seg-sequential-build.md). Cela signifie que le filtre utilise l’opérateur ALORS pour associer la séquence d’événements (le parcours) traversée par les personnes, en direction du noeud ou de la flèche sélectionné. Tous les événements correspondant au noeud ou à la flèche sélectionné sont inclus dans le filtre.

Si vous créez un filtre basé sur un noeud qui comporte plusieurs chemins d’accès, tous les chemins d’accès sont inclus dans le filtre. Des chemins distincts sont unis par l’opérateur OU.

Pour créer un filtre :

1. Dans une visualisation de canevas de Parcours, cliquez avec le bouton droit de la souris sur le noeud ou la flèche à utiliser pour créer le filtre.

1. Sélectionnez [!UICONTROL **Créer un filtre à partir du noeud**] ou [!UICONTROL **Créer un filtre à partir de la flèche**].

   Le créateur de filtres s’affiche. Dans la section [!UICONTROL **Définition**] , la définition de filtre est créée en fonction du noeud ou de la flèche que vous avez sélectionné et de son contexte dans le parcours.

1. Indiquez un titre pour le filtre et apportez toute autre modification. Pour plus d’informations sur la création d’un filtre, voir [Créateur de filtres](/help/components/filters/filter-builder.md).

1. Sélectionnez [!UICONTROL **Enregistrer**] pour enregistrer le filtre.

### Supprimer des nœuds

Vous pouvez supprimer un ou plusieurs noeuds à la fois au sein d’un parcours. Lorsque vous supprimez un noeud qui est connecté entre 2 noeuds au sein du parcours, les 2 noeuds restants sont directement connectés.

Pour supprimer des noeuds dans la zone de travail de Parcours :

1. Dans une visualisation de canevas de Parcours, sélectionnez un ou plusieurs noeuds à supprimer, puis cliquez avec le bouton droit de la souris sur l’un des noeuds sélectionnés.

1. Sélectionnez [!UICONTROL **Supprimer**].

### Suppression des flèches entre les noeuds

Vous pouvez supprimer une ou plusieurs flèches à la fois au sein d’un parcours. Lorsque vous supprimez une flèche entre deux noeuds, les noeuds ne sont plus connectés. Si la flèche faisait partie d’un chemin plus long, le chemin est déconnecté.

Pour supprimer des flèches entre les noeuds dans la zone de travail de Parcours :

1. Dans une visualisation de canevas de Parcours, sélectionnez une ou plusieurs flèches entre deux noeuds à supprimer, puis cliquez avec le bouton droit de la souris sur l’une des flèches sélectionnées.

1. Sélectionnez [!UICONTROL **Supprimer**].

## Ouvrir un parcours à partir de Journey Optimizer

Lors de l’affichage d’un parcours dans Journey Optimizer, vous pouvez choisir de l’afficher dans la zone de travail du Parcours.

1. Dans Journey Optimizer, ouvrez le parcours que vous souhaitez analyser dans la zone de travail du Parcours.

1. Sélectionnez [!UICONTROL **Analyser dans CJA**]. <!-- ?? -->
