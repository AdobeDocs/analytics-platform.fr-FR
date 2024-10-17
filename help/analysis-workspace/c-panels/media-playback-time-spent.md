---
title: Panneau Temps de lecture de média
description: Utilisation et interprétation du panneau Durée de lecture multimédia dans Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 54%

---

# Panneau Temps de lecture de média {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_button"
>title="Temps de lecture de média"
>abstract="Créez un panneau pour analyser l’évolution de la consommation vidéo, avec différents niveaux de granularité, et la possibilité de ventiler et de comparer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_panel"
>title="Temps de lecture de média"
>abstract="Analysez l’évolution de la consommation vidéo, sélectionnez différentes granularités, ventilez et comparez-les.<br/><br/>**Granularité** : sélectionnez une période pour laquelle afficher les visionneuses simultanées.<br/>**Nombre de résumés de panneau (facultatif)** : option permettant d’afficher le nombres de résumés avec les informations sur la date ou l’heure pour chaque ligne. La valeur maximale affiche les informations sur le temps de lecture le plus élevé. La valeur minimale affiche les informations sur la plus basse. La somme affiche les informations sur le temps de lecture total.<br/>**Ventilation des séries (facultatif)** : ventilez la visualisation par segments, dimensions, éléments de dimension ou périodes. Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.<br/>**Format de l’heure** : option permettant d’afficher le format de l’heure des visualisations en heures ou en minutes."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>Le panneau Audience moyenne par minute de média est disponible uniquement pour les clients qui ont acheté le module complémentaire Collection de médias en flux continu pour Customer Journey Analytics.
>Pour plus d’informations, contactez votre représentant commercial d’Adobe ou votre équipe chargée du compte d’Adobe.
>

Le panneau **[!UICONTROL Durée de lecture du média]** permet d’analyser la lecture au fil du temps, avec des détails sur la simultanéité la plus élevée et la possibilité de ventiler et de comparer.

Dans Analysis Workspace, la durée de lecture correspond à la durée passée à visionner vos diffusions multimédia à un moment donné. Il comprend la mise en pause, la mise en mémoire tampon et le temps de démarrage.

Les clients qui ont acheté le module complémentaire de collecte de médias en flux continu peuvent analyser le temps de lecture passé pour obtenir des informations précieuses sur la qualité du contenu et l’engagement des observateurs. et à vous aider lors de la résolution des problèmes ou de la planification du volume ou de l’échelle.

Le temps de lecture passé peut vous aider à comprendre :

* Là où le pic d’accès simultané s’est produit.

* Où des abandons ont eu lieu.

+++ Affichez une démonstration vidéo de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/338699)

+++

## Sélectionnez l’option  

Pour utiliser un panneau **[!UICONTROL Durée de lecture du média]** :

1. Créez un panneau **[!UICONTROL Durée de lecture du média]**. Pour plus d’informations sur la création d’un panneau, voir [Création d’un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner une vue de données pour le panneau dont les composants sont configurés à partir du module complémentaire Collection de médias en flux continu.

1. Spécifiez la [entrée](#panel-input) pour le panneau.

1. Observez la [sortie](#panel-output) pour le panneau.


### Entrée de panneau

Vous pouvez configurer le panneau Durée de lecture des médias à lʼaide des paramètres dʼentrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou dʼheure relatifs à la durée de la lecture, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. La somme additionne la durée de lecture totale de la sélection. Le panneau nʼindique par défaut que la valeur maximale, mais vous pouvez modifier cette valeur par défaut et afficher la valeur minimale, la valeur totale ou une combinaison des trois valeurs.<br>Si vous utilisez des répartitions, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Répartition de la série | Vous pouvez éventuellement ventiler votre visualisation par filtres, dimensions, éléments de dimension ou périodes.<p>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.</p><p>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionné.</p>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de répartition de la série. |
| Format de l’heure | Vous pouvez afficher le temps de lecture passé dans `Hours:Minutes:Seconds` (par défaut) ou dans `Minutes` (qui s’affiche en nombres entiers, arrondi à 0,5). |
| Affichage de la séquence de dates | Si vous avez placé au moins deux filtres de période sous forme de ventilations de série, vous avez la possibilité de sélectionner l’option de superposition (par défaut) ou séquentielle. La superposition affiche les lignes avec un début d’axe x commun afin qu’elles s’exécutent en parallèle, tandis que l’ordre affiche les lignes avec le début de leur axe x spécifique. Si les lignes de données s’affichent (par exemple, le filtre 1 se termine à 20 h 44 et le filtre 2 commence à 20 h 45), les lignes s’affichent dans l’ordre. |


![La durée de la lecture du média a passé la vue par défaut.](assets/mpts_default_view.png)

### Sortie de panneau

Le panneau Durée de lecture des médias renvoie un graphique en courbes et des numéros de synthèse, qui incluent des détails sur la durée maximale, minimale et/ou totale de la lecture. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, sélectionnez ![Modifier le temps de lecture du média](/help/assets/icons/Edit.svg) pour modifier et recréer le panneau.

Si vous sélectionnez la ventilation des séries, une ligne sur le graphique en courbes et un nombre récapitulatif s’affichent pour chacune d’elles :

![ La durée de lecture du média passée en sortie affiche un graphique en courbes et un résumé.](assets/mpts_outputs1.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est Durée de la lecture.

| Mesure | Description |
|---|---|
| Durée de la lecture | `hours:minutes:seconds` (ou `minutes`) total du contenu affiché lors de la granularité sélectionnée, y compris la mise en pause, la mémoire tampon et le temps de début. |

## Questions fréquentes

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | <p></p><p>Le tableau à structure libre n’est pas disponible dans cet affichage. Pour télécharger la source de données, dans le menu contextuel du graphique en courbes, sélectionnez l’option de téléchargement du fichier CSV.</p> |
| <p>Pourquoi ma granularité a-t-elle changé ?</p> | <p>La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète.</p><p></p><p>Lorsque vous passez d’une plage de dates plus grande à une plage de dates plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la plage de dates modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation.</p> |
| <p></p><p>Comment comparer les noms des vidéos, les filtres, les types de contenu, etc. ?</p> | <p>Pour les comparer dans une visualisation unique, faites glisser des filtres, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation de série.</p><p></p><p>L’affichage est limité à 10 répartitions. Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux.</p> |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les répartitions des séries en faisant glisser au moins 2 périodes. Ces plages de dates remplacent la plage de dates du panneau. |
| Comment puis-je modifier le type de visualisation ? | <p></p><p>Ce panneau permet uniquement la visualisation des lignes pour la série temporelle.</p> |
| Puis-je exécuter la détection des anomalies ? | <p></p><p>Non. La détection des anomalies n’est pas disponible pour ce panneau.</p> |


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panneau d’audience de minute moyenne du média](average-minute-audience-panel.md)
>[Panneau des visionneuses simultanées de médias](media-concurrent-viewers.md)
>