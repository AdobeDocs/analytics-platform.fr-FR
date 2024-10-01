---
title: Panneau Audience moyenne par minute de média
description: Utilisation et interprétation du panneau Audience par minute moyenne des médias dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1796'
ht-degree: 17%

---

# Panneau d’audience moyenne par minute du média {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaminuteaverageaudience_button"
>title="Audience par minute moyenne du média"
>abstract="Créez un panneau pour analyser une audience moyenne par minute pour un contenu spécifique ou sur une période spécifique."


<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaaverageminuteaudience_panel"
>title="Audience par minute moyenne du média"
>abstract="Affiche les performances de contenu multimédia spécifique ou sur une période personnalisée.<br/><br/>**Paramètres généraux **<br/>**Calculer la mesure pour** : sélectionnez la mesure à utiliser pour le panneau. Sélectionnez **Contenu spécifique** pour analyser l’audience moyenne par minute pour un contenu ou un événement spécifique en fonction de la durée du contenu. **Sélectionnez Période personnalisée** pour analyser l’évolution de l’audience moyenne par minute sur une période sélectionnée personnalisée.<br/>**Dimension de création de rapports** : sélectionnez cette option pour créer un rapport en fonction du **Nom de la vidéo** de la dimension **ID de contenu**. Disponible uniquement lorsque vous avez sélectionné Contenu spécifique comme mesure.<br/>**Granularité** : sélectionnez la granularité pour les rapports. Disponible uniquement lorsque vous avez sélectionné Période personnalisée comme mesure.<br/>**Filtrer le contenu par (facultatif)** : sélectionnez un affichage, une saison, un épisode ou une dimension personnalisée pour filtrer le contenu.<br/><br/>**Paramètres avancés **<br/>**Paramètres du tableau** : choisissez d’afficher ou non les valeurs de calcul dans le tableau.<br/>**Mesure Durée de la visite** : sélectionnez la mesure Durée de la visite que vous souhaitez utiliser pour le calcul de contenu spécifique. Disponible uniquement lorsque vous avez sélectionné Contenu spécifique comme mesure."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#specific-content" text="Contenu spécifique"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#custom-time-period" text="Période personnalisée"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Le panneau **[!UICONTROL audience moyenne par minute de média]** est disponible uniquement pour les clients qui ont acheté le module complémentaire Collection de médias en flux continu pour Customer Journey Analytics.
>
>Pour plus d’informations, contactez votre représentant commercial d’Adobe ou votre équipe de compte d’Adobe.
>

Dans Analysis Workspace, l’audience moyenne par minute peut fournir des informations sur

* le temps passé à visionner un flux multimédia spécifique divisé par la durée du contenu, ou
* durée de consultation au cours d’une période personnalisée avec la granularité sélectionnée.

Le panneau Audience moyenne par minute multimédia vous permet de comprendre la consommation moyenne de votre contenu en comparant des programmes de n’importe quelle longueur ou genre. Vous pouvez, par exemple, comprendre la consommation moyenne lorsque vous comparez une sitcom de 30 minutes à un événement sportif de 3 heures.

En outre, vous pouvez utiliser le panneau Audience par minute moyenne du média pour comparer ou ajouter cette audience par minute numérique moyenne aux mesures par minute de la télévision linéaire.

Le panneau Audience moyenne par minute du média offre les avantages suivants par rapport à la mesure Audience moyenne par minute :

* Prend en charge les périodes personnalisées

* Permet de mettre à jour la classification de durée après le traitement des vues (si la classification de durée n’était pas présente ou doit être corrigée).

  Si vous effectuez cette mise à jour lors de l’utilisation de la mesure, la classification de durée n’existe pas (si la classification n’était pas présente). Ou la classification de durée est obsolète (si la classification était présente mais incorrecte).

## Sélectionnez l’option  

Pour utiliser un panneau **[!UICONTROL audience moyenne par minute du média]** :

1. Créez un panneau **[!UICONTROL audience moyenne par minute du média]**. Pour plus d’informations sur la création d’un panneau, voir [Création d’un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner une vue de données pour le panneau dont les composants sont configurés à partir du module complémentaire Collection de médias en flux continu.


1. Spécifiez la [entrée](#panel-input) pour le panneau.

1. Observez la [sortie](#panel-output) pour le panneau.

### Entrée de panneau

Utilisez les paramètres d’entrée décrits dans cette section pour configurer le panneau Audience moyenne par minute du média.

1. Configurez les paramètres d’entrée suivants :

   | Paramètre | Description |
   |---------|------------|
   | **Période du panneau** | La valeur par défaut de la période du panneau est [!UICONTROL **Ce mois-ci**]. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br></br> La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
   | [!UICONTROL **Déposer un segment ici (ou tout autre composant)**] | Comme les autres panneaux, ce paramètre filtre vos sélections en fonction des segments que vous avez créés. Ce paramètre est un excellent moyen d’examiner des plateformes spécifiques, des diffusions en direct ou d’autres segments de médias courants. |
   | [!UICONTROL **Mesure de calcul pour**] | Choisissez si vous souhaitez afficher l’audience moyenne par minute pour le [**[!UICONTROL contenu spécifique]**](#specific-content). Ou si vous souhaitez afficher l’audience moyenne par minute pour une [**[!UICONTROL période personnalisée]**](#custom-time-period).<br/><br/>Sélectionnez [!UICONTROL **Période personnalisée**] : <ul><li>Si la durée n’est pas disponible, ou </li><li>si vous souhaitez afficher l’audience moyenne par minute pour une série temporelle comportant plusieurs éléments de contenu, ou</li><li>pour le contenu sans durée spécifique (par exemple, pendant un flux en direct ou un événement) ;</li></ul></li></li></ul> <p>Ce paramètre modifie le workflow et la sortie du rapport.</p> |

1. Passez à l’option [Contenu spécifique](#specific-content) ou [Période personnalisée](#custom-time-period), selon l’option choisie dans la liste déroulante [!UICONTROL **Calculer la mesure pour**] .

#### Contenu spécifique

1. Si vous avez sélectionné [!UICONTROL **Contenu spécifique**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs), spécifiez les options de configuration suivantes :

   | Paramètre | Description |
   |---------|------------|
   | [!UICONTROL **Dimension de création de rapports**] | Lorsque vous sélectionnez un contenu spécifique, vous pouvez sélectionner la sortie du rapport à l’aide des champs Nom de la vidéo ou Identifiant du contenu pour afficher le contenu et l’audience moyenne par minute associée. |
   | [!UICONTROL **Filtrer le contenu par (facultatif)**] | Choisissez comment filtrer le contenu spécifique, selon la vue que vous souhaitez ou la manière dont vos données sont structurées. <ul>[!UICONTROL **Afficher, saison, épisode**] : affiche les programmes disponibles dans la liste déroulante, que vous pouvez filtrer à l’aide d’une recherche (ou en faisant glisser et en déposant le nom d’affichage dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée.</li><li>[!UICONTROL **Dimension personnalisée**] : si votre nom d’affichage se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou en utilisant la recherche par colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode.</li><li>[!UICONTROL **None**] : affiche tous les noms de vidéo qui contiennent des données d’audience de minute moyenne pour la sélection que vous avez choisie. (Cette option est sélectionnée par défaut.)</li></ul> |

1. Passez à la [configuration avancée de contenu spécifique](#specific-content-advanced-settings) pour configurer les paramètres avancés.

#### Paramètres avancés du contenu spécifique

1. Avec [!UICONTROL **Contenu spécifique**] sélectionné dans le menu déroulant [!UICONTROL **Calculer la mesure pour**], sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez les options de configuration suivantes :

   | Options | Description |
   |---------|------------|
   | **[!UICONTROL Paramètres de table]** | L’option par défaut **[!UICONTROL Afficher les valeurs de calcul dans la table]** affiche le numérateur et le dénominateur de l’audience moyenne par minute comme les colonnes précédentes du tableau. La désélection de cette option supprime ces deux colonnes. La colonne d’audience par minute moyenne reste dans le tableau en regard du nom de la vidéo ou de l’identifiant du contenu. |
   | **[!UICONTROL Mesure Durée de la visite]** | Vous pouvez choisir l’option par défaut **[!UICONTROL Temps passé sur le contenu]**, qui inclut uniquement le temps passé sur le contenu. Vous pouvez également choisir d’utiliser **[!UICONTROL Temps passé sur le média]**, qui inclut le contenu et le temps publicitaire ensemble comme calcul du numérateur pour l’audience de minute moyenne. |

1. Sélectionnez [!UICONTROL **Build**] pour terminer la création du panneau d’audience de moyenne minute du média.

1. Passez à la [sortie du panneau](#panel-output) pour plus d’informations sur l’utilisation du panneau d’audience de minute moyenne pour les médias.

#### Période personnalisée

1. Si vous avez sélectionné [!UICONTROL **Période personnalisée**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs), spécifiez les options de configuration suivantes :

   | Options | Description |
   |---------|------------|
   | **[!UICONTROL Granularité]** | La granularité par défaut est de [!UICONTROL **5 minutes**], mais vous pouvez choisir n’importe quelle granularité utilisée comme dénominateur pour la série temporelle au cours de la période sélectionnée. Par exemple, si vous sélectionnez de 12h00 à 12h30 avec une granularité de 5 minutes, l’audience moyenne par minute est renvoyée sur une demi-heure complète, ainsi que six lignes avec l’audience moyenne par minute pour chaque période de 5 minutes. Ces lignes servent de points de données pour le graphique de série temporelle. |
   | [!UICONTROL **Filtrer le contenu par (facultatif)**] | Choisissez comment filtrer le contenu spécifique, selon la vue que vous souhaitez ou la manière dont vos données sont structurées. <ul>[!UICONTROL **Afficher, saison, épisode**] : affiche les programmes disponibles dans la liste déroulante, que vous pouvez filtrer à l’aide d’une recherche (ou en faisant glisser et en déposant le nom d’affichage dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée.</li><li>[!UICONTROL **Dimension personnalisée**] : si votre nom d’affichage se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou en utilisant la recherche par colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode.</li><li>[!UICONTROL **None**] : affiche tous les noms de vidéo qui contiennent des données d’audience de minute moyenne pour la sélection que vous avez choisie. (Cette option est sélectionnée par défaut.)</li></ul> |

1. Poursuivez avec les [Paramètres avancés de la période personnalisée](#custom-time-period-advanced-settings) pour configurer les paramètres avancés.

#### Paramètres avancés de la période personnalisée

1. Avec [!UICONTROL **Période personnalisée**] sélectionnée dans le menu déroulant [!UICONTROL **Calculer la mesure pour**], sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez l’option de configuration suivante :

   | Option | Description |
   |---------|------------|
   | **[!UICONTROL Paramètres de table]** | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, où apparaissent le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. Lorsque cette option est désélectionnée, ces deux colonnes laissent seulement apparaître l’audience moyenne par minute près de la période. |

1. Sélectionnez [!UICONTROL **Build**] pour terminer la création du panneau d’audience de moyenne minute du média.

1. Passez à la [sortie du panneau](#panel-output) pour plus d’informations sur l’utilisation du panneau d’audience de minute moyenne pour les médias.

### Sortie de panneau

La sortie du panneau varie selon que vous avez choisi [!UICONTROL **Contenu spécifique**] ou [!UICONTROL **Période personnalisée**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs).

#### Contenu spécifique

Le panneau Audience moyenne par minute du média renvoie les informations suivantes :

* Audience moyenne par minute totale pour l’ensemble de votre sélection
* Filtres et audience moyenne par minute pour les vidéos individuelles, affichés dans un tableau
* Temps passé sur le contenu et durée de la vidéo si ce paramètre avancé a été sélectionné

Pour modifier et recréer le panneau à tout moment, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) en haut à droite.

![Affichage par défaut](assets/specific-content-panel-output.png)

#### Source de données de contenu spécifique

Le panneau Audience par minute de média utilise uniquement la mesure d’audience par minute moyenne pour collecter des données. Les ventilations ou d’autres mesures ne peuvent pas être utilisées dans le panneau.

| Mesure | Description |
|--------|-------------|
| **[!UICONTROL Audience moyenne par minute]** | Il s’agit du temps passé à visionner votre flux multimédia divisé par la durée de la vidéo fournie au moyen des Classifications. |

#### Période personnalisée {#custom-time-period-output}

Le panneau Audience moyenne par minute du média renvoie les informations suivantes :

* audience totale par minute pour l’ensemble de votre sélection

* Audience par minute maximale et minimale

* Graphique de série linéaire montrant l’audience par minute moyenne sur toute la sélection.

* Un tableau présentant les filtres et l’audience par minute moyenne pour les granularités, ainsi que le temps passé sur le contenu et la granularité pour chaque période

  Ce tableau s’affiche uniquement si l’option sous les paramètres avancés appelée [!UICONTROL **Afficher les valeurs de calcul dans la table**] est sélectionnée.

Pour modifier et recréer le panneau à tout moment, sélectionnez ![Modifier le panneau d’audience de minute moyenne du média](/help/assets/icons/Edit.svg) dans le coin supérieur droit.


#### Source de données de période personnalisée

Le panneau Audience par minute de média utilise uniquement la mesure d’audience par minute moyenne pour collecter des données. Les ventilations ou d’autres mesures ne peuvent pas être utilisées dans le panneau.

| Mesure | Description |
|---|---|
| **[!UICONTROL Audience moyenne par minute]** | Il s’agit du temps passé à visionner votre flux multimédia divisé par la sélection totale ou la granularité sélectionnée en minutes. |


>[!MORELIKETHIS]
>
> [Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Panneau des visionneuses simultanées de médias](media-concurrent-viewers.md)
> [Panneau Durée de lecture du média](media-playback-time-spent.md)
>