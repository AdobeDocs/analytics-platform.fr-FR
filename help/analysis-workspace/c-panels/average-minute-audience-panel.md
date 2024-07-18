---
title: Panneau Audience moyenne par minute de média
description: Utiliser et interpréter le panneau d’audience moyenne par minute de média dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 31%

---

# Panneau d’audience moyenne par minute du média

>[!NOTE]
>
>Le panneau Audience moyenne par minute de média est disponible uniquement pour les clients qui ont acheté le module complémentaire Collection de médias en flux continu pour Customer Journey Analytics.
>
>Contactez votre représentant commercial Adobe ou votre équipe de compte d’Adobe pour acheter le module complémentaire de collecte de médias en flux continu.

Dans Analysis Workspace, l’audience moyenne par minute correspond au temps passé à regarder votre flux multimédia divisé par la durée du contenu ou la sélection totale de la période et de la granularité sélectionnée.

Le panneau Audience moyenne par minute multimédia vous permet de mieux comprendre la consommation moyenne de votre contenu en comparant des programmes de n’importe quelle longueur ou genre. Vous pouvez, par exemple, comprendre la consommation moyenne lorsque vous comparez une sitcom de 30 minutes à un événement sportif de 3 heures.

En outre, vous pouvez utiliser le panneau Audience par minute moyenne du média pour comparer ou ajouter cette audience par minute numérique moyenne aux mesures par minute de la télévision linéaire.

Le panneau Audience moyenne par minute du média offre les avantages suivants par rapport à la mesure Audience moyenne par minute :

* Prend en charge les périodes personnalisées

* Permet de mettre à jour la classification de durée après le traitement des vues (si elle n’était pas présente ou si elle doit être corrigée).

  Si vous l’avez fait lors de l’utilisation de la mesure, elle n’existera pas (si la classification n’était pas présente) ou elle sera obsolète (si la classification était présente mais incorrecte).

## Accès au panneau d’audience de moyenne minute du média

1. Dans Analysis Workspace, accédez à une suite de rapports dans laquelle les composants sont activés à partir du module complémentaire Collection de médias en flux continu.

1. Dans le volet de navigation de gauche, sélectionnez l’icône **Panneaux** .

   ![Icône Panneaux dans le volet de navigation de gauche](assets/panels-icon.png)

1. Faites glisser le panneau [!UICONTROL **Audience moyenne par minute du média**] sur la zone de travail dans Analysis Workspace.

1. Pour configurer le panneau, continuez avec les [entrées de panneau](#panel-inputs).

## Entrées du panneau {#Input}

Utilisez les paramètres d’entrée décrits dans cette section pour configurer le panneau Audience moyenne par minute du média.

1. Commencez à créer un panneau d’audience de moyenne minute du média, comme décrit dans [Accès au panneau d’audience de moyenne minute du média](#access-the-media-average-minute-audience-panel).

1. Configurez les paramètres d’entrée suivants :

   | Paramètre | Description |
   |---------|------------|
   | **Période du panneau** | La valeur par défaut de la période du panneau est [!UICONTROL **Ce mois-ci**]. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br></br> La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
   | [!UICONTROL **Déposer un segment ici (ou tout autre composant)**] | Comme les autres panneaux, ce paramètre filtre vos sélections en fonction des segments que vous avez créés. Il s’agit d’une excellente manière d’examiner des plateformes spécifiques, des diffusions en direct ou d’autres segments de médias courants. |
   | [!UICONTROL **Mesure de calcul pour**] | Choisissez si vous souhaitez afficher l’audience par minute moyenne pour un élément de contenu spécifique ou si vous souhaitez afficher l’audience par minute moyenne pour une période personnalisée :<ul><li>**Contenu spécifique :** Ce contenu n’est disponible que si la durée a été mise à jour à l’aide des classifications. Si la durée n’est pas disponible, ou si vous souhaitez afficher l’audience moyenne par minute pour une série temporelle avec plusieurs éléments de contenu ou de contenu sans une durée spécifique attribuée (comme lors d’un flux ou d’un événement en direct), sélectionnez [!UICONTROL **Période personnalisée**]. (Les durées peuvent être définies à l’aide de classifications avant ou après le temps de traitement.)</li><li>**Période personnalisée :** Cette option est disponible que les durées soient rendues disponibles à l’aide des classifications.</li></ul> <p>Ce paramètre modifie le workflow et la sortie du rapport.</p> |

1. Poursuivez en cliquant sur [Contenu spécifique](#specific-content) ou [Période personnalisée](#custom-time-period), selon l’option que vous avez choisie dans le menu déroulant [!UICONTROL **Calculer la mesure pour**].

### Contenu spécifique

1. Si vous avez sélectionné [!UICONTROL **Contenu spécifique**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs), spécifiez les options de configuration suivantes :

   | Paramètre | Description |
   |---------|------------|
   | [!UICONTROL **Dimension de création de rapports**] | Lorsque vous choisissez un contenu spécifique, vous pouvez sélectionner la sortie du rapport à l’aide des champs Nom de la vidéo ou ID du contenu pour afficher le contenu et l’audience moyenne par minute associée pour la période sélectionnée. |
   | [!UICONTROL **Filtrer le contenu par (facultatif)**] | Choisissez comment filtrer le contenu spécifique, selon la vue que vous souhaitez ou la manière dont vos données sont structurées. <ul>[!UICONTROL **Afficher, saison, épisode**] : affiche les programmes disponibles dans la liste déroulante, que vous pouvez filtrer à l’aide d’une recherche (ou en faisant glisser et en déposant le nom d’affichage dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée.</li><li>[!UICONTROL **Dimension personnalisée**] : si votre nom d’affichage se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou en utilisant la recherche par colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode.</li><li>[!UICONTROL **None**] : affiche tous les noms de vidéo qui contiennent des données d’audience de minute moyenne pour la sélection que vous avez choisie. (Cette option est sélectionnée par défaut.)</li></ul> |

1. Passez à la [configuration avancée de contenu spécifique](#specific-content-advanced-settings) pour configurer les paramètres avancés.

### Paramètres avancés du contenu spécifique

1. Avec [!UICONTROL **Contenu spécifique**] sélectionné dans le menu déroulant [!UICONTROL **Calculer la mesure pour**], sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez les options de configuration suivantes :

   | Paramètre | Description |
   |---------|------------|
   | Paramètres du tableau | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, où apparaissent le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. Lorsque cette option est désélectionnée, ces deux colonnes sont supprimées et seule l’audience moyenne par minute apparaît près du nom de la vidéo ou de l’ID du contenu. |
   | Mesure Tranche de temps | Vous pouvez choisir le temps passé sur le contenu par défaut, qui inclut uniquement le temps passé sur le contenu, ou décider d’utiliser le temps passé sur le média, qui inclut la durée du contenu et des publicités comme calcul du numérateur de l’audience moyenne par minute. |

1. Sélectionnez [!UICONTROL **Build**] pour terminer la création du panneau d’audience de moyenne minute du média.

1. Passez à la [sortie du panneau](#panel-output) pour plus d’informations sur l’utilisation du panneau d’audience de minute moyenne pour les médias.

### Période personnalisée

1. Si vous avez sélectionné [!UICONTROL **Période personnalisée**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs), spécifiez les options de configuration suivantes :

   | Paramètre | Description |
   |---------|------------|
   | Granularité | La granularité par défaut est de [!UICONTROL **5 minutes**], mais vous pouvez choisir l’une des granularités utilisées comme dénominateur pour la série temporelle lors de la sélection globale de la période effectuée dans la sélection de calendrier. Par exemple, si vous sélectionnez de 12h00 à 12h30 avec une granularité de 5 minutes, l’audience moyenne par minute est renvoyée sur une demi-heure complète, ainsi que six lignes avec l’audience moyenne par minute pour chaque période de 5 minutes. Ces lignes servent de points de données pour le graphique de série temporelle. |
   | [!UICONTROL **Filtrer le contenu par (facultatif)**] | Choisissez comment filtrer le contenu spécifique, selon la vue que vous souhaitez ou la manière dont vos données sont structurées. <ul>[!UICONTROL **Afficher, saison, épisode**] : affiche les programmes disponibles dans la liste déroulante, que vous pouvez filtrer à l’aide d’une recherche (ou en faisant glisser et en déposant le nom d’affichage dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée.</li><li>[!UICONTROL **Dimension personnalisée**] : si votre nom d’affichage se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou en utilisant la recherche par colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode.</li><li>[!UICONTROL **None**] : affiche tous les noms de vidéo qui contiennent des données d’audience de minute moyenne pour la sélection que vous avez choisie. (Cette option est sélectionnée par défaut.)</li></ul> |

1. Poursuivez avec les [Paramètres avancés de la période personnalisée](#custom-time-period-advanced-settings) pour configurer les paramètres avancés.

### Paramètres avancés de la période personnalisée

1. Avec [!UICONTROL **Période personnalisée**] sélectionnée dans le menu déroulant [!UICONTROL **Calculer la mesure pour**], sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez l’option de configuration suivante :

   | Paramètre | Description |
   |---------|------------|
   | Paramètres du tableau | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, où apparaissent le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. Lorsque cette option est désélectionnée, ces deux colonnes laissent seulement apparaître l’audience moyenne par minute près de la période. |

1. Sélectionnez [!UICONTROL **Build**] pour terminer la création du panneau d’audience de moyenne minute du média.

1. Passez à la [sortie du panneau](#panel-output) pour plus d’informations sur l’utilisation du panneau d’audience de minute moyenne pour les médias.

## Sortie de panneau

La sortie du panneau varie selon que vous avez choisi [!UICONTROL **Contenu spécifique**] ou [!UICONTROL **Période personnalisée**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs).

### Contenu spécifique

Le panneau Audience moyenne par minute du média renvoie les informations suivantes :

* Audience moyenne par minute totale pour l’ensemble de votre sélection
* Filtres et audience moyenne par minute pour les vidéos individuelles affichées dans un tableau
* Temps passé sur le contenu et durée de la vidéo si ce paramètre avancé a été sélectionné

Pour modifier et recréer le panneau à tout moment, sélectionnez l’icône Modifier (crayon) en haut à droite.

![Affichage par défaut](assets/specific-content-panel-output.png)

### Source de données de contenu spécifique

Le panneau Audience moyenne par minute du média utilise uniquement la mesure Audience moyenne par minute pour collecter des données. Les ventilations ou d’autres mesures ne peuvent pas être utilisées dans le panneau.

| Mesure | Description |
|--------|-------------|
| Audience moyenne par minute | Il s’agit du temps passé à visionner votre flux multimédia divisé par la durée de la vidéo fournie au moyen des Classifications. |

### Période personnalisée {#custom-time-period-output}

Le panneau Audience moyenne par minute du média renvoie les informations suivantes :

* audience totale par minute pour l’ensemble de votre sélection

* Audience par minute maximale et minimale

* Graphique de série linéaire montrant l’audience par minute moyenne sur toute la sélection.

* Un tableau présentant les filtres et l’audience par minute moyenne pour les granularités, ainsi que le temps passé sur le contenu et la granularité pour chaque période

  Ce tableau s’affiche uniquement si l’option sous les paramètres avancés appelée [!UICONTROL **Afficher les valeurs de calcul dans la table**] est sélectionnée.

Pour modifier et recréer le panneau à tout moment, sélectionnez l’icône Modifier (crayon) en haut à droite.

![sortie des observateurs simultanés](assets/custom-time-period-panel-output.png)

### Source de données de période personnalisée

Le panneau Audience moyenne par minute du média utilise uniquement la mesure Audience moyenne par minute pour collecter des données. Les ventilations ou d’autres mesures ne peuvent pas être utilisées dans le panneau.

| Mesure | Description |
|---|---|
| Audience moyenne par minute | Il s’agit du temps passé à visionner votre flux multimédia divisé par la sélection totale ou la granularité sélectionnée en minutes. |
