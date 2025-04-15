---
title: Panneau Audience moyenne par minute de média
description: Comment utiliser et interpréter le panneau d’audience moyenne par minute de média dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 94%

---

# Panneau Audience moyenne par minute de média {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Audience moyenne par minute de média"
>abstract="Créez un panneau afin d’analyser l’audience moyenne par minute d’un contenu ou d’une période spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Audience moyenne par minute de média"
>abstract="Affiche les performances du contenu multimédia ou de la période personnalisée. Spécifiez la dimension de reporting et éventuellement le contenu du segment."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Cet article présente le panneau d’audience moyenne par minute de média dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Voir [Panneau d’audience moyenne par minute de média](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel) pour la version_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]

>[!NOTE]
>
>Le panneau **[!UICONTROL Audience moyenne par minute de média]** est disponible uniquement pour les clients qui ont acheté Streaming Media Collection for Customer Journey Analytics.
>
>Pour plus d’informations, contactez votre représentant ou représentante du service commercial Adobe ou l’équipe Adobe en charge des comptes.
>

Dans Analysis Workspace, l’audience moyenne par minute peut fournir des informations sur les éléments suivants :

* le temps passé à visionner un flux multimédia spécifique divisé par la durée du contenu, ou
* le temps passé à visionner au cours d’une période personnalisée avec une granularité sélectionnée.

Le panneau Audience moyenne par minute de média vous permet de comprendre la consommation moyenne de votre contenu en comparant des programmes, peu importe leur longueur ou leur genre. Par exemple, vous pouvez comprendre la consommation moyenne en comparant une sitcom de 30 minutes à un événement sportif de 3 heures.

En outre, vous pouvez utiliser le panneau Audience moyenne par minute de média pour comparer ou ajouter cette audience numérique moyenne par minute aux mesures linéaires moyennes par minute de la télévision.

Le panneau Audience moyenne par minute de média offre les avantages suivants par rapport à la mesure Audience moyenne par minute :

* Prend en charge les périodes personnalisées.

* Permet de mettre à jour la classification de durée après le traitement des vues (si la classification de durée n’était pas présente ou doit être corrigée).

  Si vous effectuez cette mise à jour lors de l’utilisation de la mesure, la classification de durée n’existe pas (si la classification n’était pas présente). Ou la classification de durée est obsolète (si la classification était présente mais incorrecte).

## Utilisation

Pour utiliser un panneau **[!UICONTROL Audience moyenne par minute de média]**, procédez comme suit :

1. Créez un panneau **[!UICONTROL Audience moyenne par minute de média]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner une vue de données pour le panneau dont les composants sont configurés à partir du module complémentaire Streaming Media Collection.

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.

### Entrée du panneau

Utilisez les paramètres d’entrée décrits dans cette section pour configurer le panneau Audience moyenne par minute de média.

1. Configurez les paramètres d’entrée suivants :

   | Paramètre | Description |
   |---------|------------|
   | **Période du panneau** | La période par défaut du panneau est définie sur [!UICONTROL **Ce mois**]. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br></br> La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
   | [!UICONTROL **Déposez un segment ici (ou tout autre composant)**] | Comme les autres panneaux, ce paramètre segmente vos sélections en fonction des segments que vous avez créés. Il s’agit d’une excellente manière d’examiner des plateformes spécifiques, des diffusions en direct ou d’autres segments de médias courants. |
   | [!UICONTROL **Calculer la mesure pour**] | Choisissez si vous souhaitez afficher l’audience moyenne par minute pour un [**[!UICONTROL Contenu spécifique]**](#specific-content). Ou si vous souhaitez afficher l’audience moyenne par minute pour une [**[!UICONTROL Période personnalisée]**](#custom-time-period).<br/><br/>Sélectionnez une [!UICONTROL **Période personnalisée**] : <ul><li>si la durée n’est pas disponible, ou </li><li>si vous souhaitez afficher l’audience moyenne par minute pour une série temporelle composée de plusieurs éléments de contenu, ou</li><li>pour le contenu sans durée attribuée spécifique (par exemple pendant un flux ou un événement en direct)</li></ul></li></li></ul> <p>Ce paramètre modifie le workflow et la sortie du rapport.</p> |

1. Continuez avec [Contenu spécifique](#specific-content) ou [Période personnalisée](#custom-time-period), selon l’option choisie dans la liste déroulante [!UICONTROL **Calculer la mesure pour**].

#### Contenu spécifique

1. Si vous avez sélectionné [!UICONTROL **Contenu spécifique**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées de panneau](#panel-inputs), spécifiez les options de configuration suivantes :

   | Paramètre | Description |
   |---------|------------|
   | [!UICONTROL **Dimension de création de rapports**] | Lorsque vous choisissez un contenu spécifique, vous pouvez sélectionner la sortie du rapport à l’aide des champs Nom de la vidéo ou ID du contenu pour afficher le contenu et l’audience moyenne par minute associée pour la période sélectionnée. |
   | [!UICONTROL **Filtrer le contenu par (facultatif)**] | Vous pouvez filtrer le contenu spécifique en fonction de l’affichage souhaité ou de la structure de vos données. <ul>[!UICONTROL **Programme, saison, épisode**] : affiche les programmes disponibles dans la liste déroulante. Vous pouvez ensuite les filtrer en effectuant une recherche (ou en glissant-déposant le nom du programme dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée.</li><li>[!UICONTROL **Dimension personnalisée**] : si le nom de votre programme se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou dans la colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode.</li><li>[!UICONTROL **Aucun**] : affiche tous les noms de vidéo qui contiennent des données d’audience moyenne par minute pour votre sélection. (Cette option est sélectionnée par défaut.)</li></ul> |

1. Continuez avec [Paramètres avancés du contenu spécifique](#specific-content-advanced-settings) pour configurer les paramètres avancés.

#### Paramètres avancés du contenu spécifique

1. Lorsque [!UICONTROL **Contenu spécifique**] est sélectionné dans le menu déroulant [!UICONTROL **Calculer la mesure pour**], sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez les options de configuration suivantes :

   | Options | Description |
   |---------|------------|
   | **[!UICONTROL Paramètres du tableau]** | Le paramètre par défaut **[!UICONTROL Afficher les valeurs de calcul dans le tableau]** affiche le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. La désélection de cette option supprime ces deux colonnes. La colonne d’audience moyenne par minute reste dans le tableau en regard du nom de la vidéo ou de l’identifiant du contenu. |
   | **[!UICONTROL Mesure Tranche de temps]** | Vous pouvez choisir l’option par défaut **[!UICONTROL Temps passé sur le contenu]**, qui inclut uniquement la durée du contenu. Vous pouvez également choisir d’utiliser **[!UICONTROL Temps passé sur les médias]**, qui inclut la durée du contenu et de l’annonce publicitaire comme calcul du numérateur pour l’audience moyenne par minute. |

1. Sélectionnez [!UICONTROL **Créer**] pour terminer la création du panneau Audience moyenne par minute de média.

1. Continuez avec [Sortie de panneau](#panel-output) pour plus d’informations sur l’utilisation du panneau Audience moyenne par minute de média.

#### Période personnalisée

1. Si vous avez sélectionné [!UICONTROL **Période personnalisée**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées de panneau](#panel-inputs), spécifiez les options de configuration suivantes :

   | Options | Description |
   |---------|------------|
   | **[!UICONTROL Granularité]** | La granularité par défaut est de [!UICONTROL **5 minutes**]. Vous pouvez cependant choisir l’une des granularités utilisées en tant que dénominateur pour la série temporelle comprise dans la période sélectionnée. Par exemple, si vous sélectionnez de 12 h 00 à 12 h 30 avec une granularité de 5 minutes, vous obtiendrez l’audience moyenne par minute sur la demi-heure complète ainsi que six lignes indiquant l’audience moyenne par minute pour chaque période de 5 minutes. Ces lignes servent de points de données pour le graphique de série temporelle. |
   | [!UICONTROL **Filtrer le contenu par (facultatif)**] | Vous pouvez filtrer le contenu spécifique en fonction de l’affichage souhaité ou de la structure de vos données. <ul>[!UICONTROL **Programme, saison, épisode**] : affiche les programmes disponibles dans la liste déroulante. Vous pouvez ensuite les filtrer en effectuant une recherche (ou en glissant-déposant le nom du programme dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée.</li><li>[!UICONTROL **Dimension personnalisée**] : si le nom de votre programme se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou dans la colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode.</li><li>[!UICONTROL **Aucun**] : affiche tous les noms de vidéo qui contiennent des données d’audience moyenne par minute pour votre sélection. (Cette option est sélectionnée par défaut.)</li></ul> |

1. Continuez avec [Paramètres avancés de la période personnalisée](#custom-time-period-advanced-settings) pour configurer les paramètres avancés.

#### Paramètres avancés de la période personnalisée

1. Avec l’option [!UICONTROL **Période personnalisée**] sélectionnée dans le menu déroulant [!UICONTROL **Calculer la mesure pour**], sélectionnez [!UICONTROL **Afficher les paramètres avancés**], puis spécifiez l’option de configuration suivante :

   | Option | Description |
   |---------|------------|
   | **[!UICONTROL Paramètres du tableau]** | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, où apparaissent le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. Lorsque cette option est désélectionnée, ces deux colonnes laissent seulement apparaître l’audience moyenne par minute près de la période. |

1. Sélectionnez [!UICONTROL **Créer**] pour terminer la création du panneau Audience moyenne par minute de média.

1. Continuez avec [Sortie de panneau](#panel-output) pour plus d’informations sur l’utilisation du panneau Audience moyenne par minute de média.

### Sortie du panneau

La sortie du panneau varie selon que vous avez choisi [!UICONTROL **Contenu spécifique**] ou [!UICONTROL **Période personnalisée**] dans le menu déroulant [!UICONTROL **Calculer la mesure pour**] lors de la [configuration des entrées du panneau](#panel-inputs).

#### Contenu spécifique

Le panneau Audience moyenne par minute de média fournit les informations suivantes :

* Audience moyenne par minute totale pour l’ensemble de votre sélection
* Filtres et audience moyenne par minute pour les vidéos individuelles, affichés dans un tableau.
* Temps passé sur le contenu et durée de la vidéo si ce paramètre avancé a été sélectionné.

Pour modifier et recréer le panneau à tout moment, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) dans le coin supérieur droit.

![Affichage par défaut](assets/specific-content-panel-output.png)

#### Source de données du contenu spécifique

Le panneau Audience moyenne par minute de média utilise uniquement la mesure d’audience moyenne par minute pour collecter des données. Les répartitions ou autres mesures ne peuvent pas être utilisées dans le panneau.

| Mesure | Description |
|--------|-------------|
| **[!UICONTROL Audience moyenne par minute]** | Il s’agit du temps passé à visionner votre flux multimédia divisé par la durée de la vidéo fournie au moyen des Classifications. |

#### Période personnalisée {#custom-time-period-output}

Le panneau Audience moyenne par minute de média fournit les informations suivantes :

* Audience moyenne par minute totale pour l’ensemble de votre sélection

* Audience moyenne par minute maximale et minimale

* Graphique linéaire des séries indiquant l’audience moyenne par minute sur l’ensemble de la sélection.

* Tableau indiquant les filtres et l’audience moyenne par minute pour les granularités, ainsi que le temps passé sur le contenu et la granularité pour chaque période

  Ce tableau s’affiche uniquement si l’option sous les paramètres avancés appelée [!UICONTROL **Afficher les valeurs de calcul dans le tableau**] est sélectionnée.

Pour modifier et recréer le panneau à tout moment, sélectionnez ![Modifier le panneau Audience moyenne par minute de média](/help/assets/icons/Edit.svg) en haut à droite.


#### Source de données de période personnalisée

Le panneau Audience moyenne par minute de média utilise uniquement la mesure d’audience moyenne par minute pour collecter des données. Les répartitions ou autres mesures ne peuvent pas être utilisées dans le panneau.

| Mesure | Description |
|---|---|
| **[!UICONTROL Audience moyenne par minute]** | Il s’agit du temps passé à visionner votre flux multimédia divisé par la sélection totale ou la granularité sélectionnée en minutes. |


>[!MORELIKETHIS]
>
> [Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Panneau Observateurs et observatrices simultanés de médias](media-concurrent-viewers.md)
> [Panneau Temps de lecture de média](media-playback-time-spent.md)
>