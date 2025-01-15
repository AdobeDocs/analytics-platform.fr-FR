---
title: Panneau Temps de lecture de média
description: Comment utiliser et interpréter le panneau Temps de lecture de média dans Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 55%

---

# Panneau Temps de lecture de média {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="Temps de lecture de média"
>abstract="Créez un panneau pour analyser l’évolution de la consommation vidéo, avec différents niveaux de granularité, et la possibilité de ventiler et de comparer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="Temps de lecture de média"
>abstract="Analysez l’évolution de la consommation vidéo, sélectionnez différentes granularités, ventilez et comparez-les.<br/><br/>**Granularité** : sélectionnez une période pour laquelle afficher les visionneuses simultanées.<br/>**Nombre de résumés de panneau (facultatif)** : option permettant d’afficher le nombres de résumés avec les informations sur la date ou l’heure pour chaque ligne. La valeur maximale affiche les informations sur le temps de lecture le plus élevé. La valeur minimale affiche les informations sur la plus basse. La somme affiche les informations sur le temps de lecture total.<br/>**Ventilation des séries (facultatif)** : ventilez la visualisation par segments, dimensions, éléments de dimension ou périodes. Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.<br/>**Format de l’heure** : option permettant d’afficher le format de l’heure des visualisations en heures ou en minutes."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Cet article documente le panneau Temps de lecture de média dans **Customer Journey Analytics**. Voir [Panneau Temps de lecture de média](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent) pour la version **Adobe Analytics**de cet article.*

>[!ENDSHADEBOX]


>[!NOTE]
>
>Le panneau d’audience moyenne par minute de média est disponible uniquement pour les clients qui ont acheté le module complémentaire Streaming Media Collection pour Customer Journey Analytics.
>Pour plus d’informations, contactez votre représentant commercial Adobe ou l’équipe du compte Adobe.
>

Le panneau **[!UICONTROL Temps de lecture de média]** permet d’analyser la lecture au fil du temps, avec des détails sur le pic d’accès simultanés et la possibilité de ventiler et de comparer.

Dans Analysis Workspace, le temps de lecture est la durée de visionnage de vos flux multimédias à un moment donné. Il comprend une pause, une mise en mémoire tampon et une heure de démarrage.

Les clients qui ont acheté le module complémentaire Streaming Media Collection peuvent analyser le temps de lecture pour obtenir des informations précieuses sur la qualité du contenu et l’engagement des observateurs. Et pour vous aider lors du dépannage ou de la planification du volume ou de l’échelle.

Le temps de lecture peut vous aider à comprendre :

* Où le pic d’accès simultanés s’est produit.

* L’endroit où les abandons ont eu lieu.

+++ Regardez une vidéo de démonstration de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/338699)

+++

## Utilisation

Pour utiliser un panneau **[!UICONTROL Temps de lecture de média]** :

1. Créez un panneau **[!UICONTROL Temps de lecture de média]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner une vue de données pour le panneau dont les composants sont configurés à partir de la collection de médias en flux continu.

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.


### Entrée du panneau

Vous pouvez configurer le panneau Durée de lecture des médias à lʼaide des paramètres dʼentrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou dʼheure relatifs à la durée de la lecture, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. La somme additionne la durée de lecture totale de la sélection. Le panneau nʼindique par défaut que la valeur maximale, mais vous pouvez modifier cette valeur par défaut et afficher la valeur minimale, la valeur totale ou une combinaison des trois valeurs.<br>Si vous utilisez des répartitions, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Répartition de la série | Vous pouvez éventuellement ventiler votre visualisation par filtres, dimensions, éléments de dimension ou périodes.<p>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.</p><p>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.</p>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de répartition de la série. |
| Format de l’heure | Vous pouvez afficher le temps de lecture passé dans `Hours:Minutes:Seconds` (par défaut) ou dans `Minutes` (affiché en nombres entiers, arrondi à 0,5). |
| Affichage de la séquence de dates | Si vous avez placé au moins deux filtres de période en tant que répartitions de série, vous voyez l’option permettant de sélectionner Recouvrement (par défaut) ou Séquentiel. L’option Recouvrement affiche les lignes avec un début d’axe x commun de sorte qu’elles s’exécutent en parallèle, tandis que l’option Séquentiel affiche les lignes avec leur début d’axe x spécifique. Si les données s’alignent (par exemple, le filtre 1 se termine à 20h44 et le filtre 2 commence à 20h45), les lignes s’affichent dans l’ordre. |


![Vue par défaut de la durée de consultation du playbook multimédia](assets/mpts_default_view.png).

### Sortie du panneau

Le panneau Durée de lecture des médias renvoie un graphique en courbes et des numéros de synthèse, qui incluent des détails sur la durée maximale, minimale et/ou totale de la lecture. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, sélectionnez ![Modifier le panneau Temps de lecture de média](/help/assets/icons/Edit.svg) pour modifier et recréer le panneau.

Si vous sélectionnez la répartition des séries, une ligne du graphique en courbes et une synthèse des chiffres s’affichent pour chacune d’elles :

![Sortie de durée de lecture des médias présentant un graphique en courbes et un résumé.](assets/mpts_outputs1.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est Durée de la lecture.

| Mesure | Description |
|---|---|
| Durée de la lecture | `hours:minutes:seconds` total (ou `minutes`) de contenu consulté au cours de la granularité sélectionnée, y compris la pause, la mémoire tampon et l’heure de début. |

## Questions fréquentes

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | <p></p><p>Le tableau à structure libre n’est pas disponible dans cet affichage. Pour télécharger la source de données, à partir du menu contextuel du graphique en courbes, sélectionnez l’option de téléchargement du fichier CSV.</p> |
| <p>Pourquoi ma granularité a-t-elle changé ?</p> | <p>La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète.</p><p></p><p>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation.</p> |
| <p></p><p>Comment puis-je comparer les noms de vidéo, les filtres, les types de contenu, etc. ?</p> | <p>Pour les comparer dans une visualisation unique, faites glisser des filtres, des dimensions ou des éléments de dimension spécifiques dans le filtre de répartition des séries.</p><p></p><p>L’affichage est limité à 10 répartitions. Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux.</p> |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les répartitions des séries en faisant glisser au moins 2 périodes. Ces périodes remplacent la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | <p></p><p>Ce panneau permet uniquement la visualisation des lignes pour la série temporelle.</p> |
| Puis-je exécuter la détection des anomalies ? | <p></p><p>Non. La détection des anomalies n’est pas disponible pour ce panneau.</p> |


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panneau d’audience moyenne par minute de média](average-minute-audience-panel.md)
>[Panneau Observateurs simultanés de médias ](media-concurrent-viewers.md)
>