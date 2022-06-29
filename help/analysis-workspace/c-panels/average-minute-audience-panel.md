---
title: Panneau Audience moyenne par minute de média
description: Utilisation et interprétation du panneau Audience moyenne par minute du média dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: db48638cc1e22ca4e555a8981e0f5175d52970f2
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 23%

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

Vous pouvez configurer le panneau Audience moyenne par minute du média à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---------|------------|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br></br> La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Faire glisser un segment ici (ou tout autre composant) | Comme les autres panneaux, ce paramètre filtre vos sélections en fonction des segments que vous avez créés. Il s’agit d’une excellente manière d’examiner des plateformes spécifiques, des diffusions en direct ou d’autres segments de médias courants. |
| Calculer la mesure pour | Ce paramètre vous permet de choisir si vous souhaitez afficher l’audience moyenne par minute pour un élément de contenu spécifique, en sélectionnant *contenu spécifique* ou si vous souhaitez afficher l’audience moyenne par minute pendant une période spécifique, en sélectionnant *période personnalisée*. <br></br>Le contenu spécifique ne fonctionne que si la durée a été mise à jour à l’aide des classifications. Si la durée n’est pas disponible, ou si vous souhaitez afficher l’audience moyenne par minute pour une série temporelle avec plusieurs éléments de contenu ou de contenu sans une durée spécifique attribuée (comme pendant un flux en direct ou un événement), vous devez sélectionner une période personnalisée. Ce paramètre modifie le workflow et la sortie du rapport. |

### Contenu spécifique

| Paramètre | Description |
|---------|------------|
| Dimensions de création de rapports | Lorsque vous choisissez un contenu spécifique, vous pouvez sélectionner la sortie du rapport à l’aide des champs Nom de la vidéo ou Identifiant du contenu pour afficher le contenu et l’audience moyenne par minute associée pour la période sélectionnée. |
| Filtrage du contenu par (facultatif) | Vous pouvez filtrer le contenu spécifique selon la vue que vous souhaitez ou la manière dont vos données sont structurées. |
| Programme, saison, épisode | Sélectionnez &quot;Afficher, saison, épisode&quot; pour afficher les programmes disponibles dans la liste déroulante, que vous pouvez filtrer à l’aide d’une recherche (ou en faisant glisser et en déposant le nom de l’affichage dans la colonne de gauche). Vous pouvez y terminer votre sélection pour voir toutes les saisons de votre émission, ou vous pouvez filtrer par saison et par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée. |
| Dimension personnalisée | Si votre nom d’affichage se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou en effectuant une recherche dans la colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode. |
| Aucun | Vous pouvez choisir *Aucun* pour afficher tous les noms de vidéo qui contiennent des données d’audience de minute moyenne pour la sélection que vous avez choisie. |

### Paramètres avancés du contenu spécifique

| Paramètre | Description |
|---------|------------|
| Paramètres du tableau | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, qui affichent le numérateur et le dénominateur de l’audience moyenne par minute comme les colonnes précédentes du tableau. Si vous désélectionnez cette option, ces deux colonnes sont supprimées, l’audience moyenne par minute n’étant plus que le nom de la vidéo ou l’identifiant du contenu. |
| Mesure Durée de la visite | Vous pouvez choisir le temps passé par défaut sur le contenu, qui inclut uniquement le temps passé sur le contenu, ou choisir d’utiliser le temps passé sur le média, qui inclut le contenu et le temps de publicité ensemble comme calcul du numérateur de la minute moyenne d’audience. |

### Période personnalisée

| Paramètre | Description |
|---------|------------|
| Granularité | La granularité par défaut est de 5 minutes, mais vous pouvez choisir l’une des granularités utilisées comme dénominateur pour la série temporelle au cours de la sélection de période globale effectuée dans le calendrier. Par exemple, si vous sélectionnez de 12h00 à 12h30 avec une granularité de 5 minutes, l’audience moyenne par minute est renvoyée sur la demi-heure complète, ainsi que six lignes avec l’audience moyenne par minute pour chaque période de 5 minutes. Ces lignes sont utilisées comme points de données pour le graphique de série temporelle. |
| Filtrage du contenu par (facultatif) | Vous pouvez filtrer le contenu spécifique selon la vue que vous souhaitez ou la manière dont vos données sont structurées. |
| Programme, saison, épisode | Sélection *Programme, saison, épisode* affiche les affichages disponibles dans la liste déroulante, que vous pouvez filtrer par recherche (ou en faisant glisser le nom d’affichage depuis la colonne de gauche). Vous pouvez y terminer votre sélection pour voir toutes les saisons de votre émission, ou vous pouvez filtrer par saison et par épisodes individuels. Ce paramètre affiche les données relatives à ces programmes, saisons ou épisodes pour la période sélectionnée. |
| Dimension personnalisée | Si votre nom d’affichage se trouve sous une dimension personnalisée, vous pouvez le trouver en effectuant une recherche dans la liste déroulante Dimension (facultatif) ou en effectuant une recherche dans la colonne de gauche. L’élément de dimension est automatiquement renseigné en fonction de cette sélection et traité comme un épisode. |
| Aucun | Vous pouvez choisir *Aucun* pour afficher tous les noms des vidéos au cours de la période choisie. |

### Paramètres avancés de la période personnalisée

| Paramètre | Description |
|---------|------------|
| Paramètres du tableau | Le paramètre par défaut affiche les valeurs de calcul dans le tableau, qui affiche le numérateur et le dénominateur de l’audience moyenne par minute comme les colonnes précédentes du tableau. Si vous désélectionnez cette option, ces deux colonnes sont supprimées, ce qui laisse uniquement une audience moyenne par minute en regard de la période. |


## Sortie de panneau de contenu spécifique

Le panneau Audience moyenne par minute du média renvoie les informations suivantes :

* Audience moyenne par minute totale pour l’ensemble de votre sélection
* Filtres et audience moyenne par minute pour les vidéos individuelles affichées dans un tableau
* Durée de visionnage du contenu et durée de la vidéo (durée) si ce paramètre avancé a été sélectionné

Pour modifier et recréer le panneau à tout moment, cliquez sur le crayon de modification situé en haut à droite.

![Affichage par défaut](assets/specific-content-panel-output.png)


### Source de données de contenu spécifique

La seule mesure qui peut être utilisée dans ce panneau est Audience moyenne par minute.

| Mesure | Description |
|--------|-------------|
| Audience moyenne par minute | Durée de visionnage de votre flux multimédia divisée par la durée de la vidéo (durée) fournie via les classifications. |

## Sortie du panneau Période personnalisée {#custom-time-period-output}

Le panneau Audience moyenne par minute du média renvoie l’audience moyenne par minute totale pour l’ensemble de votre sélection, l’audience par minute maximale et minimale et le graphique de série chronologique présentant l’audience par minute moyenne sur l’ensemble de la sélection. Le tableau ci-dessous présente les filtres et l’audience par minute moyenne pour les granularités, ainsi que le temps passé sur le contenu et la granularité pour chaque période si ce paramètre avancé a été sélectionné.

Pour modifier et recréer le panneau à tout moment, cliquez sur le crayon de modification situé en haut à droite.

![sortie des observateurs simultanés](assets/custom-time-period-panel-output.png)

### Source de données de période personnalisée

La seule mesure qui peut être utilisée dans ce panneau est Audience moyenne par minute :

| Mesure | Description |
|---|---|
| Audience moyenne par minute | Temps passé à visionner votre flux multimédia divisé par la sélection totale ou la granularité sélectionnée en minutes. |



<!-- For more information about Media Average Minute Audience, visit [MA doc page]( https://url). -->
