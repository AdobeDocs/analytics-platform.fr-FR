---
title: Panneau Audience moyenne par minute de média
description: Utiliser et interpréter le panneau d’audience moyenne par minute de média dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: db48638cc1e22ca4e555a8981e0f5175d52970f2
workflow-type: ht
source-wordcount: '1313'
ht-degree: 100%

---


# Panneau Audience moyenne par minute de média

<!-- THIS FEATURE IS SCHEDULED FOR 2023 -->

Le panneau dʼaudience moyenne par minute permet aux clients Media Analytics de mieux comprendre la consommation de leur contenu en moyenne. Lʼaudience moyenne par minute permet de comparer des programmes de toute longueur ou de tout genre. En outre, les clients peuvent comparer ou ajouter cette audience numérique moyenne par minute aux mesures moyennes par minute de la télévision linéaire. Ce panneau offre plus de flexibilité pour mesurer l’audience moyenne pour des périodes personnalisées, ainsi que lorsque la classification de la durée a été mise à jour après coup. La mesure d’audience moyenne par minute actuelle ne fonctionne que si la durée est disponible au moment du traitement.

Dans Analysis Workspace, l’audience moyenne par minute correspond au temps passé à regarder votre flux multimédia divisé par la durée du contenu ou la sélection totale de la période et de la granularité sélectionnée.

Le panneau Audience moyenne par minute de média fournit une analyse de l’audience moyenne par minute pour le contenu spécifique sélectionné, si la durée est disponible à l’aide des classifications.
Le panneau Audience moyenne par minute fournit également une analyse sur une période sélectionnée qui peut être filtrée par un contenu spécifique, que la durée soit disponible ou non à l’aide des classifications. Pour afficher le panneau Audience moyenne par minute de média, accédez à une suite de rapports dont les composants Media Analytics sont activés. Cliquez ensuite sur l’icône du panneau située à l’extrémité gauche et faites glisser le panneau dans votre projet Analysis Workspace.

<!-- For more information, see the Media Average Minute Audience introduction video:
<< replace with AMA video when available >> -->

<!-- >[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12) -->

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau d’audience moyenne par minute de média à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---------|------------|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br></br> La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Faites glisser un segment ici (ou tout autre composant) | Comme les autres panneaux, ce paramètre filtre vos sélections en fonction des segments que vous avez créés. Il s’agit d’une excellente manière d’examiner des plateformes spécifiques, des diffusions en direct ou d’autres segments de médias courants. |
| Calculer la mesure pour | Ce paramètre vous permet de choisir si vous souhaitez afficher l’audience moyenne par minute pour un élément de contenu donné, en sélectionnant un *contenu spécifique*, ou si vous souhaitez afficher l’audience moyenne par minute pour une période donnée, en sélectionnant une *période personnalisée*. <br></br>Le contenu spécifique ne fonctionne que si la durée a été mise à jour à l’aide des classifications. Si la durée n’est pas disponible ou si vous souhaitez afficher l’audience moyenne par minute pour une série temporelle composée de plusieurs éléments de contenu ou de contenu sans durée spécifique attribuée (par exemple pendant une diffusion ou un événement en direct), vous devez sélectionner une période personnalisée. Ce paramètre modifie le workflow et la sortie du rapport. |

### Contenu spécifique

| Paramètre | Description |
|---------|------------|
| Dimensions de la création de rapports | Lorsque vous choisissez un contenu spécifique, vous pouvez sélectionner la sortie du rapport à l’aide des champs Nom de la vidéo ou ID du contenu pour afficher le contenu et l’audience moyenne par minute associée pour la période sélectionnée. |
| Filtrer le contenu par (facultatif) | Vous pouvez filtrer le contenu spécifique en fonction de l’affichage souhaité ou de la structure de vos données. |
| Programme, saison, épisode | Sélectionnez « Programme, saison, épisode » pour afficher les programmes disponibles dans la liste déroulante. Vous pouvez ensuite les filtrer en effectuant une recherche (ou en glissant-déposant le nom du programme dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée. |
| Dimension personnalisée | Si le nom de votre programme se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou dans la colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode. |
| Aucun | Vous pouvez choisir *Aucun* pour afficher tous les noms de vidéo qui contiennent des données d’audience moyenne par minute pour votre sélection. |

### Paramètres avancés du contenu spécifique

| Paramètre | Description |
|---------|------------|
| Paramètres du tableau | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, où apparaissent le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. Lorsque cette option est désélectionnée, ces deux colonnes sont supprimées et seule l’audience moyenne par minute apparaît près du nom de la vidéo ou de l’ID du contenu. |
| Mesure Tranche de temps | Vous pouvez choisir le temps passé sur le contenu par défaut, qui inclut uniquement le temps passé sur le contenu, ou décider d’utiliser le temps passé sur le média, qui inclut la durée du contenu et des publicités comme calcul du numérateur de l’audience moyenne par minute. |

### Période personnalisée

| Paramètre | Description |
|---------|------------|
| Granularité | La granularité par défaut est de 5 minutes. Vous pouvez cependant choisir l’une des granularités utilisées en tant que dénominateur pour la série temporelle comprise dans la période globale sélectionnée dans le calendrier. Par exemple, si vous sélectionnez de 12 h 00 à 12 h 30 avec une granularité de 5 minutes, vous obtiendrez l’audience moyenne par minute sur la demi-heure complète ainsi que six lignes indiquant l’audience moyenne par minute pour chaque période de 5 minutes. Ces lignes servent de points de données pour le graphique de série temporelle. |
| Filtrer le contenu par (facultatif) | Vous pouvez filtrer le contenu spécifique en fonction de l’affichage souhaité ou de la structure de vos données. |
| Programme, saison, épisode | Sélectionnez *Programme, saison, épisode* pour afficher les programmes disponibles dans la liste déroulante. Vous pouvez ensuite les filtrer en effectuant une recherche (ou en glissant-déposant le nom du programme dans la colonne de gauche). Si vous arrêtez votre sélection ici, vous verrez toutes les saisons de votre programme. Vous pouvez aussi filtrer les résultats par saison, puis par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée. |
| Dimension personnalisée | Si le nom de votre programme se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou dans la colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode. |
| Aucun | Vous pouvez choisir *Aucun* pour afficher tous les noms des vidéos pendant la période choisie. |

### Paramètres avancés de la période personnalisée

| Paramètre | Description |
|---------|------------|
| Paramètres du tableau | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, où apparaissent le numérateur et le dénominateur de l’audience moyenne par minute sous forme des colonnes précédentes du tableau. Lorsque cette option est désélectionnée, ces deux colonnes laissent seulement apparaître l’audience moyenne par minute près de la période. |


## Sortie de panneau du contenu spécifique

Le panneau Audience moyenne par minute du média fournit les informations suivantes :

* Audience moyenne par minute totale pour l’ensemble de votre sélection
* Filtres et audience moyenne par minute pour les vidéos individuelles affichées dans un tableau
* Temps passé sur le contenu et durée de la vidéo si ce paramètre avancé a été sélectionné

Pour modifier et recréer le panneau, cliquez à tout moment sur l’icône de modification en forme de crayon dans le coin supérieur droit.

![Affichage par défaut](assets/specific-content-panel-output.png)


### Source de données du contenu spécifique

La seule mesure qui peut être utilisée dans ce panneau est l’Audience moyenne par minute.

| Mesure | Description |
|--------|-------------|
| Audience moyenne par minute | Il s’agit du temps passé à visionner votre flux multimédia divisé par la durée de la vidéo fournie au moyen des Classifications. |

## Sortie du panneau Période personnalisée {#custom-time-period-output}

Le panneau Audience moyenne par minute de média renvoie l’audience moyenne par minute totale pour l’ensemble de votre sélection, l’audience moyenne par minute maximale et minimale et le graphique linéaire des séries indiquant l’audience moyenne par minute sur l’ensemble de la sélection. Le tableau ci-dessous indique les filtres et l’audience moyenne par minute pour les granularités, ainsi que le temps passé sur le contenu et la granularité pour chaque période si ce paramètre avancé a été sélectionné.

Pour modifier et recréer le panneau, cliquez à tout moment sur l’icône de modification en forme de crayon dans le coin supérieur droit.

![sortie des observateurs simultanés](assets/custom-time-period-panel-output.png)

### Source de données de période personnalisée

La seule mesure qui peut être utilisée dans ce panneau est l’Audience moyenne par minute :

| Mesure | Description |
|---|---|
| Audience moyenne par minute | Il s’agit du temps passé à visionner votre flux multimédia divisé par la sélection totale ou la granularité sélectionnée en minutes. |



<!-- For more information about Media Average Minute Audience, visit [MA doc page]( https://url). -->
