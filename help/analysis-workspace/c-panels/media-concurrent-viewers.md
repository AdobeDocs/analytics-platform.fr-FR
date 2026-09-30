---
title: Panneau Observateurs simultanés de médias
description: Découvrez comment utiliser et interpréter le panneau d’observateurs simultanés de médias dans Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
TQID: 'https://experienceleague.adobe.com/IkzScFK8pyrB-ejW-Kjtgwm-A5XfdLSR-5JqrU30EGw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: e634a07b-b7ca-4af3-a124-3024ce559e17
    internal-label: Workspace panels
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '1215'
ht-degree: 90%
---
# Panneau des visionneuses simultanées de médias {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Visites simultanées de médias"
>abstract="Créez un panneau pour analyser les visionneuses simultanées sur une période spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Visites simultanées de médias"
>abstract="Analysez l’évolution du nombre de spectateurs simultanés, affichez le pic de simultanéité et, éventuellement, ventilez et comparez les données à l’aide de segments, de dimensions, d’éléments de dimension ou de périodes."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente le panneau d’observateurs simultanés de médias dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Voir [Panneau d’observateurs simultanés de médias](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) pour la version_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de cet article._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Le panneau Audience moyenne par minute de média est disponible uniquement pour les clientes et clients qui ont acheté le module complémentaire Streaming Media Collection pour Customer Journey Analytics.
>
>Pour plus d’informations, contactez votre représentant ou représentante du service commercial Adobe ou l’équipe Adobe en charge des comptes.
>

Le panneau **[!UICONTROL Visiteurs et visiteuses simultanés de médias]** permet d’analyser les visiteurs et visiteuses simultanés au fil du temps. Il fournit également des informations détaillées sur le pic d’accès simultanés et la possibilité de ventiler et de comparer.

Vous pouvez analyser les visiteurs et visiteuses simultanés pour déterminer où s’est produit le pic d’accès simultanés ou l’endroit où des abandons ont eu lieu, ce qui permet de mieux comprendre la qualité du contenu et l’engagement des personnes. Et pour faciliter le dépannage ou la planification du volume ou de l’échelle.

Dans Analysis Workspace, la mesure « Nombre d’observateurs simultanés » correspond au nombre de personnes uniques qui visualisent vos flux de médias à un moment donné, quel que soit le nombre de sessions.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panneau Visiteurs et visiteuses simultanés de médias](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/media-concurrent-viewers-panel-in-analysis-workspace){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]

## Utilisation

Pour utiliser un panneau **[!UICONTROL Visiteurs et visiteuses simultanés de médias]**, procédez comme suit :

1. Créez un panneau **[!UICONTROL Visiteurs et visiteuses simultanés de médias]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner pour le panneau une vue de données dont les composants sont configurés à partir de Streaming Media Collection.

1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.

### Entrée du panneau

Vous pouvez configurer le panneau Visiteurs et visiteuses simultanés de médias à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| **[!UICONTROL Période du panneau]** | La période par défaut du panneau est définie sur Aujourd’hui.  Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br> <br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| **[!UICONTROL Granularité]** | La granularité par défaut est définie sur Minute.<br>Cette visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| **[!UICONTROL Synthèse des chiffres des panneaux]** | Pour afficher les détails de date ou d’heure relatifs aux observateurs simultanés, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur **[!UICONTROL minimale]** affiche les détails du creux.  Par défaut, le panneau affiche uniquement la valeur maximale, mais vous pouvez le modifier pour afficher la valeur minimale ou les deux valeurs. <br><br>Si vous utilisez des répartitions, une synthèse des chiffres s’affiche pour chacune d’elles. |
| **[!UICONTROL Répartition de la série]** | Vous pouvez ventiler votre visualisation par segments, dimensions, éléments de dimension ou périodes.<br>Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.<br>Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.<br>Pour comparer des périodes, faites glisser deux périodes ou plus dans le segment de répartition de la série. |

Voici un exemple de panneau configuré pour une granularité **[!UICONTROL Minute]** avec une synthèse des chiffres **[!UICONTROL Maximum uniquement]**. Et ventilé par **[!UICONTROL Autre]**, **[!UICONTROL Tableau]**, **[!UICONTROL Téléphone mobile]**, **[!UICONTROL Console de jeu]**, **[!UICONTROL Lecteur multimédia]**, **[!UICONTROL Décodeur]**, **[!UICONTROL Télévision]**.

![Vue de répartition de la série Visiteurs et visiteuses simultanés de médias présentant 7 dimensions, segments ou périodes sur 10.](assets/concurrent-viewers-series-breakdown.png)

### Sortie du panneau

Le panneau « Observateurs simultanés de médias » affiche un graphique linéaire et des valeurs récapitulatives qui fournissent des informations sur le nombre maximal et/ou minimal de spectateurs simultanés.  En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, sélectionnez ![Modifier le panneau Visiteurs et visiteuses simultanés de médias](/help/assets/icons/Edit.svg) pour modifier et recréer le panneau.

Si vous sélectionnez une répartition de série, une ligne du graphique linéaire et une valeur récapitulative s’affichent pour chaque élément :

![Sortie des Visiteurs et visiteuses simultanés de médias.](assets/concurrent-viewers-output.png)

### Source de données

La seule mesure qui peut être utilisée dans ce panneau est **[!UICONTROL Visiteurs et visiteuses simultanés]** :

| Mesure | Description |
|---|---|
| **[!UICONTROL Visiteurs et visiteuses simultanés]** | Nombre de personnes uniques qui visualisent vos flux de médias à un moment donné, quel que soit le nombre de sessions. |

Un tableau à structure libre n’est pas disponible dans cet affichage.  Pour afficher la source de données, vous pouvez la télécharger à partir du menu contextuel de visualisation sous forme de graphique en courbes et sélectionner **[!UICONTROL Télécharger les données au format CSV]**.  Les répartitions de séries sont incluses.

![Options de sortie Visiteurs et visiteuses simultanés avec l’option « Télécharger les données au format CSV » mise en surbrillance.](assets/concurrent-viewers-download-csv.png)

## Questions fréquentes

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | Le tableau à structure libre n’est pas disponible dans cette vue.  Vous pouvez télécharger la source de données à partir du menu contextuel du graphique en courbes et sélectionner **[!UICONTROL Télécharger les données au format CSV]**. |
| Pourquoi la granularité a-t-elle changé ? | La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète.<br><br>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher un niveau de granularité supérieur, modifiez le panneau et recréez la vue. |
| Comment puis-je comparer les noms de vidéo, les segments, les types de contenu, etc. ? | Pour les comparer dans une visualisation unique, faites glisser des segments, des dimensions ou des éléments de dimension spécifiques dans le segment de répartition de la série.<br><br>L’affichage est limité à 10 répartitions.  Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux. |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les répartitions des séries en faisant glisser au moins 2 périodes.  Ces périodes remplacent alors la période du panneau. |
| Comment modifier le type de visualisation ? | Ce panneau permet uniquement la visualisation des lignes pour la série temporelle. |
| Puis-je exécuter la détection des anomalies ? | Non.  La détection des anomalies n’est pas disponible pour ce panneau. |
| Pourquoi utiliser des personnes uniques plutôt que des sessions actives ? | L’utilisation de personnes uniques permet de supprimer les pics indésirables aux limites de l’affichage (où les sessions se terminent et commencent simultanément). |
| Que signifie la mesure Nombre d’observateurs simultanés avec une granularité supérieure à la minute ? | Avec une granularité supérieure à une minute, les observateurs simultanés représentent la somme des observateurs simultanés uniques pour toutes les minutes de cette période.  Par exemple, les visiteurs et visiteuses simultanés avec une granularité au niveau de l’heure représentent la somme des visiteurs et visiteuses simultanés uniques pour toutes les minutes de cette heure. |
| Le panneau Espace de travail affiche-t-il les mêmes informations que le rapport sur les observateurs simultanés ? | Non.  Dans Analysis Workspace, la mesure Visiteurs et visiteuses simultanés est définie comme le nombre personnes uniques qui visualisent votre flux de médias à un moment précis. Quel que soit le nombre de sessions.<br><br>Cette mesure est différente de le rapport Visiteurs et visiteuses simultanés dans la section Rapports, qui utilise les sessions simultanées actives. L’utilisation de personnes uniques entraîne la suppression des pics indésirables aux limites du programme (où les sessions se terminent et commencent au même moment). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panneau Temps de lecture de média](media-playback-time-spent.md)
>[Panneau Audience moyenne par minute de média](average-minute-audience-panel.md)
>