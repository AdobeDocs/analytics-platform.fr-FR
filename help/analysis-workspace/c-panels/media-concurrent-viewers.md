---
title: Panneau Observateurs simultanés de médias
description: Comment utiliser et interpréter le panneau d’observateurs simultanés de médias dans Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 55b312552d32070875714a77e1177bf0da5f9d87
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 46%

---

# Panneau des visionneuses simultanées de médias {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Visionneuses simultanées de médias"
>abstract="Créez un panneau afin d’analyser l’audience moyenne par minute d’un contenu ou d’une période spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Visionneuses simultanées de médias"
>abstract="Analysez l’évolution des visionneuses simultanées, affichez la simultanéité la plus élevée ou ventilez et comparez-les.<br/><br>**Granularité** : sélectionnez une période pour laquelle afficher les visionneuses simultanées.<br/>**Nombre de résumés de panneau** :<br/>option permettant d’afficher les nombres de résumés avec des informations sur la date ou l’heure pour chaque ligne. La valeur maximale affiche les informations sur la simultanéité la plus élevée. La valeur minimale affiche les informations sur la plus basse.<br/>**Ventilation des séries (facultatif)** : ventilez la visualisation par segments, dimensions, éléments de dimension ou périodes. Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article documente le panneau d’observateurs simultanés de médias dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Voir [Panneau d’observateurs simultanés de médias](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) pour la version_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Le panneau d’audience moyenne par minute de média est disponible uniquement pour les clients qui ont acheté le module complémentaire Streaming Media Collection pour Customer Journey Analytics.
>
>Pour plus d’informations, contactez votre représentant commercial Adobe ou l’équipe du compte Adobe.
>

Le panneau **[!UICONTROL Observateurs simultanés de médias]** permet d’analyser les observateurs simultanés au fil du temps. Il fournit également des informations détaillées sur le pic d’accès simultanés et la possibilité de ventiler et de comparer.

Vous pouvez analyser les observateurs simultanés pour déterminer où s’est produit le pic d’accès simultanés ou où des abandons ont eu lieu, ce qui permet de mieux comprendre la qualité du contenu et l’engagement des observateurs. Et pour faciliter le dépannage ou la planification du volume ou de l’échelle.

Dans Analysis Workspace, la mesure Observateurs simultanés correspond au nombre de personnes uniques qui visualisent vos flux multimédias à un moment donné, quel que soit le nombre de sessions.


+++ Regardez une vidéo de démonstration de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

{{videoaa}}

+++

## Utilisation

Pour utiliser un panneau **[!UICONTROL Visionneuses simultanées de médias]** :

1. Créez un panneau **[!UICONTROL Visionneuses simultanées de médias]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner une vue de données pour le panneau dont les composants sont configurés à partir de la collection de médias en flux continu.

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.

### Entrée du panneau

Vous pouvez configurer le panneau d’observateurs simultanés de médias à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| **[!UICONTROL Période du panneau]** | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br> <br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| **[!UICONTROL Granularité]** | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| **[!UICONTROL Synthèse des chiffres des panneaux]** | Pour afficher les détails de date ou d’heure relatifs aux observateurs simultanés, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. **[!UICONTROL Minimum]** affiche les détails du creux.  Par défaut, le panneau affiche uniquement la valeur maximale, mais vous pouvez le modifier pour afficher la valeur minimale ou les deux valeurs.<br><br>Si vous utilisez des répartitions, une synthèse des chiffres s’affiche pour chacune d’elles. |
| **[!UICONTROL Répartition de la série]** | Vous pouvez éventuellement ventiler votre visualisation par filtres, dimensions, éléments de dimension ou périodes.<br>Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.<br>Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont sélectionnés automatiquement en fonction de la période du panneau sélectionnée.<br>Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de répartition de la série. |

Voici un exemple de panneau configuré pour une granularité **[!UICONTROL Minute]** avec des nombres de synthèse **[!UICONTROL Maximum uniquement]**. Et ventilé par **[!UICONTROL Autre]**, **[!UICONTROL Tableau]**, **[!UICONTROL Téléphone mobile]**, **[!UICONTROL Console de jeu]**, **[!UICONTROL Lecteur multimédia]**, **[!UICONTROL Décodeur]**, **[!UICONTROL Télévision]**.

![Vue de répartition de la série d’observateurs simultanés de médias présentant 7 dimensions, segments ou périodes sur 10.](assets/concurrent-viewers-series-breakdown.png)

### Sortie du panneau

Le panneau Observateurs simultanés de médias renvoie un graphique en courbe et des synthèses de chiffres pour inclure des détails sur les valeurs maximales et/ou minimales d’observateurs simultanés. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, sélectionnez ![Modifier le panneau des visionneuses simultanées de médias](/help/assets/icons/Edit.svg) pour modifier et recréer le panneau.

Si vous sélectionnez une répartition de série, une ligne du graphique en courbes et une synthèse des chiffres s’affichent pour chacune d’elles :

![Sortie des observateurs simultanés de médias.](assets/concurrent-viewers-output.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est **[!UICONTROL Observateurs simultanés]** :

| Mesure | Description |
|---|---|
| **[!UICONTROL Observateurs simultanés]** | Nombre de personnes uniques qui regardent vos flux multimédias à un moment spécifique dans le temps, quel que soit le nombre de sessions. |

Un tableau à structure libre n’est pas disponible dans cet affichage. Pour afficher la source de données, vous pouvez la télécharger à partir du menu contextuel de visualisation sous forme de graphique en courbes et sélectionner **[!UICONTROL Télécharger les données au format CSV]**.  Les répartitions de séries sont incluses.

![Les options de sortie des observateurs simultanés avec l’option « Télécharger les données au format CSV » mise en surbrillance.](assets/concurrent-viewers-download-csv.png)

## Questions fréquentes

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | Le tableau à structure libre n’est pas disponible dans cet affichage. Vous pouvez télécharger la source de données à partir du menu contextuel du graphique en courbes et sélectionner **[!UICONTROL Télécharger les données au format CSV]**. |
| Pourquoi ma granularité a-t-elle changé ? | La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète.<br><br>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation. |
| Comment puis-je comparer les noms de vidéo, les filtres, les types de contenu, etc. ? | Pour comparer ces éléments dans une visualisation unique, faites glisser des filtres, des dimensions ou des éléments de dimension spécifiques dans le filtre de répartition des séries.<br><br>L’affichage est limité à 10 répartitions.  Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux. |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les répartitions des séries en faisant glisser au moins 2 périodes.  Les périodes remplacent la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | Ce panneau permet uniquement la visualisation des lignes pour la série temporelle. |
| Puis-je exécuter la détection des anomalies ? | Non.  La détection des anomalies n’est pas disponible pour ce panneau. |
| Pourquoi utiliser des personnes uniques plutôt que des sessions actives ? | L’utilisation de personnes uniques permet de supprimer les pics indésirables aux limites de l’affichage (où les sessions se terminent et commencent simultanément). |
| Que signifie le fait d’avoir des observateurs simultanés avec une granularité supérieure à la minute ? | Avec une granularité supérieure à une minute, les observateurs simultanés représentent la somme des observateurs simultanés uniques pour toutes les minutes de cette période. Par exemple, les observateurs simultanés avec une granularité au niveau de l’heure représentent la somme des observateurs simultanés uniques pour toutes les minutes de l’heure. |
| Le panneau Espace de travail affiche-t-il les mêmes informations que le rapport sur les observateurs simultanés ? | Non.  Dans Analysis Workspace, la mesure Observateurs simultanés est définie comme le nombre de personnes uniques qui visualisent votre flux de médias à un moment donné. Quel que soit le nombre de sessions.<br><br>Cette mesure est différente de celle des observateurs simultanés dans la section Rapports, qui utilise les sessions simultanées actives. L’utilisation de personnes uniques entraîne la suppression des pics indésirables aux limites de l’affichage (où les sessions se terminent et commencent en même temps). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panneau Temps de lecture de média ](media-playback-time-spent.md)
>[Panneau d’audience moyenne par minute de média](average-minute-audience-panel.md)
>