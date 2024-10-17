---
title: Panneau Observateurs simultanés de médias
description: Utilisation et interprétation du panneau des visionneuses simultanées de médias dans Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 44%

---

# Panneau des visionneuses simultanées de médias {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaconcurrentviewers_button"
>title="Visionneuses simultanées de médias"
>abstract="Créez un panneau afin d’analyser l’audience moyenne par minute d’un contenu ou d’une période spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaconcurrentviewers_panel"
>title="Visionneuses simultanées de médias"
>abstract="Analysez l’évolution des visionneuses simultanées, affichez la simultanéité la plus élevée ou ventilez et comparez-les.<br/><br>**Granularité** : sélectionnez une période pour laquelle afficher les visionneuses simultanées.<br/>**Nombre de résumés de panneau** :<br/>option permettant d’afficher les nombres de résumés avec des informations sur la date ou l’heure pour chaque ligne. La valeur maximale affiche les informations sur la simultanéité la plus élevée. La valeur minimale affiche les informations sur la plus basse.<br/>**Ventilation des séries (facultatif)** : ventilez la visualisation par segments, dimensions, éléments de dimension ou périodes. Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>Le panneau Audience moyenne par minute de média est disponible uniquement pour les clients qui ont acheté le module complémentaire Collection de médias en flux continu pour Customer Journey Analytics.
>
>Pour plus d’informations, contactez votre représentant commercial d’Adobe ou votre équipe de compte d’Adobe.
>

Le panneau **[!UICONTROL Visionneuses simultanées de médias]** permet d’analyser les visionneuses simultanées au fil du temps, avec des détails sur la simultanéité la plus élevée et la possibilité de ventiler et de comparer.

Vous pouvez analyser les visionneuses simultanées pour déterminer où s’est produit le pic d’accès simultané ou où des abandons ont eu lieu afin de fournir des informations précieuses sur la qualité du contenu et l’engagement des visionneuses. et pour vous aider à résoudre les problèmes ou à planifier le volume ou l’échelle.

Dans Analysis Workspace, la mesure Visionneuses simultanées est le nombre de personnes uniques qui visualisent vos diffusions multimédia à un moment donné, quel que soit le nombre de sessions.


+++ Affichez une démonstration vidéo de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

{{videoaa}}

+++

## Sélectionnez l’option  

Pour utiliser un panneau **[!UICONTROL Visionneuses simultanées de médias]** :

1. Créez un panneau **[!UICONTROL Visionneuses simultanées de médias]**. Pour plus d’informations sur la création d’un panneau, voir [Création d’un panneau](panels.md#create-a-panel).

1. Veillez à sélectionner une vue de données pour le panneau dont les composants sont configurés à partir du module complémentaire Collection de médias en flux continu.

1. Spécifiez la [entrée](#panel-input) pour le panneau.

1. Observez la [sortie](#panel-output) pour le panneau.

### Entrée de panneau

Vous pouvez configurer le panneau Visionneuses simultanées de médias à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| **[!UICONTROL Période du panneau]** | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br> <br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| **[!UICONTROL Granularité]** | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| **[!UICONTROL Nombre de résumés de panneau]** | Pour afficher les détails de date ou d’heure relatifs aux observateurs simultanés, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. **[!UICONTROL Minimum]** affiche des détails sur le creux.  Par défaut, le panneau affiche uniquement la valeur maximale, mais vous pouvez le modifier pour afficher la valeur minimale ou les deux valeurs.<br><br>Si vous utilisez des répartitions, une synthèse des chiffres s’affiche pour chacune d’elles. |
| **[!UICONTROL Ventilation des séries]** | Vous pouvez éventuellement ventiler votre visualisation par filtres, dimensions, éléments de dimension ou périodes.<br>Vous pouvez afficher jusqu’à 10 lignes à la fois. Les répartition sont limitées à un seul niveau.<br>Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période sélectionnée dans le panneau.<br>Pour comparer des plages de dates, faites glisser 2 plages de dates ou plus dans le filtre de ventilation des séries. |

Voici un exemple du panneau configuré pour la granularité **[!UICONTROL Minute]**, avec des nombres de synthèse **[!UICONTROL Maximum uniquement]**. Et ventilé par **[!UICONTROL Autre]**, **[!UICONTROL Table]**, **[!UICONTROL Téléphone mobile]**, **[!UICONTROL Console de jeux]**, **[!UICONTROL Lecteur multimédia]**, **[!UICONTROL Cadre fixe]**, **[!UICONTROL Télévision]**.

![La vue de ventilation Série de visionneuses simultanées de médias présente 7 dimensions, segments ou plages de dates sur 10.](assets/concurrent-viewers-series-breakdown.png)

### Sortie de panneau

Le panneau Observateurs simultanés de médias renvoie un graphique en courbe et des synthèses de chiffres pour inclure des détails sur les valeurs maximales et/ou minimales d’observateurs simultanés. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, sélectionnez ![Modifier le panneau des visionneuses simultanées de médias](/help/assets/icons/Edit.svg) pour modifier et recréer le panneau.

Si vous sélectionnez une ventilation de série, une ligne sur le graphique en courbes et un nombre récapitulatif s’affichent pour chacune d’elles :

![Sortie De Visionneuses Simultanées De Médias.](assets/concurrent-viewers-output.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est **[!UICONTROL Visionneuses simultanées]** :

| Mesure | Description |
|---|---|
| **[!UICONTROL Visionneuses simultanées]** | Le nombre de personnes uniques qui visualisent vos diffusions multimédia à un moment donné, quel que soit le nombre de sessions. |

Un tableau à structure libre n’est pas disponible dans cet affichage. Pour afficher la source de données, vous pouvez télécharger la source de données à partir du menu contextuel de visualisation en graphique en courbes et sélectionner **[!UICONTROL Télécharger les données au format CSV]**.  Les ventilations de séries sont incluses.

![ Les options de sortie des visionneuses simultanées avec &quot;Télécharger les données au format CSV&quot; en surbrillance.](assets/concurrent-viewers-download-csv.png)

## Questions fréquentes

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | Le tableau à structure libre n’est pas disponible dans cet affichage. Vous pouvez télécharger la source de données à partir du menu contextuel du graphique en courbes et sélectionner **[!UICONTROL Télécharger les données au format CSV]**. |
| Pourquoi ma granularité a-t-elle changé ? | La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète.<br><br>Lorsque vous changez une plage de dates plus grande en une plage de dates plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la plage de dates modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation. |
| Comment comparer les noms des vidéos, les filtres, les types de contenu, etc. ? | Pour comparer ces éléments dans une visualisation unique, faites glisser des filtres, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation de série.<br><br>L’affichage est limité à 10 répartitions.  Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux. |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les répartitions des séries en faisant glisser au moins 2 périodes.  Les périodes remplacent la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | Ce panneau permet uniquement la visualisation des lignes pour la série temporelle. |
| Puis-je exécuter la détection des anomalies ? | Non.  La détection des anomalies n’est pas disponible pour ce panneau. |
| Pourquoi utiliser des personnes uniques plutôt que des sessions actives ? | L’utilisation de personnes uniques permet la suppression des pics indésirables aux limites des affichages (où les sessions se terminent et commencent en même temps). |
| Que signifie le fait d’avoir des observateurs simultanés avec une granularité supérieure à la minute ? | Avec une granularité supérieure à une minute, les observateurs simultanés représentent la somme des observateurs simultanés uniques pour toutes les minutes de cette période. Par exemple, les visionneuses simultanées de granularité au niveau de l’heure sont la somme des visionneuses simultanées uniques pour toutes les minutes de l’heure. |
| Le panneau Espace de travail affiche-t-il les mêmes informations que le rapport sur les observateurs simultanés ? | Non.  Dans Analysis Workspace, la mesure Visionneuses simultanées est définie comme le nombre de personnes uniques qui visualisent votre diffusion multimédia à un moment donné. Quel que soit le nombre de sessions.<br><br>Cette mesure est différente de la création de rapports de visionneuse simultanée dans la section Rapports, qui utilise des sessions actives simultanées. L’utilisation de personnes uniques permet de supprimer les pics indésirables aux limites des affichages (les sessions se terminent et démarrent en même temps). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Créer un panneau](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panneau Durée de lecture du média](media-playback-time-spent.md)
>[Panneau d’audience de minute moyenne du média](average-minute-audience-panel.md)
>