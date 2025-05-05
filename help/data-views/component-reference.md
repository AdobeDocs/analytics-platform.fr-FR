---
title: Référence de composant standard
description: Détails et informations sur tous les composants standard que vous pouvez ajouter à n’importe quelle vue de données.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 81%

---

# Référence de composant standard

La plupart des dimensions et des mesures dans Customer Journey Analytics sont basées sur des éléments de schéma de votre jeu de données Adobe Experience Platform. Cependant, plusieurs composants peuvent être ajoutés à une vue de données, quelle que soit la connexion que vous utilisez.

Les [!UICONTROL composants standard] sont des composants qui ne sont pas générés à partir des champs du schéma du jeux de données, mais qui sont générés par le système. Certains composants du système sont requis afin de faciliter les fonctionnalités de compte rendu des performances dans Analysis Workspace, tandis que dʼautres composants du système sont facultatifs.

![Composants standard](assets/dataview-standard-components.png)

## Composants standard requis {#required}

Ces composants standard requis sont ajoutés par défaut à chaque vue de données. Ils sont essentiels aux fonctionnalités de création de comptes rendus des performances proposées par Customer Journey Analytics.

| Nom du composant | Dimension ou mesure | Remarques |
| --- | --- | --- |
| [!UICONTROL Personnes] | Mesure | Basée sur lʼidentifiant de personne spécifié dans une [!UICONTROL Connexion]. |
| [!UICONTROL Comptes] | Mesure | En fonction de l’identifiant de compte spécifié dans une [!UICONTROL &#x200B; Connexion &#x200B;]. |
| [!UICONTROL Comptes globaux] | Mesure | En fonction de l’identifiant de comptes globaux spécifié dans le [!UICONTROL Connexion]. |
| [!UICONTROL &#x200B; Opportunité &#x200B;] | Mesure | Les opportunités, en fonction de l’identifiant d’opportunité spécifié dans la [!UICONTROL Connexion]. |
| [!UICONTROL Groupe d&#39;achat] | Mesure | Groupes d’achats, en fonction de l’identifiant de groupe d’achats spécifié dans la [!UICONTROL Connexion]. |
| [!UICONTROL Sessions] | Mesure | En fonction des paramètres de session de la vue de données. |
| [!UICONTROL Événements] | Mesure | Cette mesure représente le nombre de lignes de tous les jeux de données dʼévénements dans une [!UICONTROL Connexion]. |
| [!UICONTROL Secondes] | Dimension | Seconde à laquelle un événement donné s’est produit (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première seconde de la période, et le dernier élément de dimension correspond à la dernière seconde de la période. |
| [!UICONTROL Minute] | Dimension | La minute à laquelle un événement donné s’est produit (arrondi à l’unité inférieure). Le premier élément de dimension correspond à la première minute de la période, et le dernier élément de dimension correspond à la dernière minute de la période. |
| [!UICONTROL Heure] | Dimension | Heure à laquelle un événement donné s’est produit (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première heure de la période et le dernier élément de dimension correspond à la dernière heure de la période. |
| [!UICONTROL Jour] | Dimension | Le jour où un événement donné s’est produit. Le premier élément de dimension correspond au premier jour de la période et le dernier élément de dimension correspond au dernier jour de la période. |
| [!UICONTROL Semaine] | Dimension | La semaine où un événement donné s’est produit. Le premier élément de dimension correspond à la première semaine de la période et le dernier élément de dimension correspond à la dernière semaine de la période. |
| [!UICONTROL Mois] | Dimension | Le mois au cours duquel un événement donné s’est produit. Le premier élément de dimension correspond au premier mois de la période, et le dernier élément de dimension correspond au dernier mois de la période. |
| [!UICONTROL Trimestre] | Dimension | Le trimestre au cours duquel un événement donné s’est produit. Le premier élément de dimension correspond au premier trimestre de la période et le dernier élément de dimension correspond au dernier trimestre de la période. |
| [!UICONTROL Année] | Dimension | L’année au cours de laquelle un événement donné s’est produit. Le premier élément de dimension correspond à la première année de la période et le dernier élément de dimension correspond à la dernière année de la période. |
| [!UICONTROL La session commence] | Mesure | Le nombre dʼévénements qui étaient le premier événement dʼune session. Lorsqu’elle est utilisée dans une définition de segment (par exemple, « [!UICONTROL La session commence] existe »), elle segmente jusqu’au premier événement de chaque session.<p>Ce composant doit être inclus dans votre vue de données pour que la [mesure calculée](/help/components/calc-metrics/default-calcmetrics.md) suivante soit disponible dans Workspace : <ul><li>Taux de début de session</li></p> |
| [!UICONTROL La session se termine] | Mesure | Le nombre dʼévénements qui étaient le dernier événement dʼune session. Tout comme la méthode [!UICONTROL démarrages de session], elle peut également être utilisée dans une définition de segment pour segmenter les éléments jusqu’au dernier événement de chaque session.<p>Ce composant doit être inclus dans votre vue de données pour que la [mesure calculée](/help/components/calc-metrics/default-calcmetrics.md) suivante soit disponible dans Workspace : <ul><li>Taux de fin de session</li></p> |
| [!UICONTROL Durée (secondes)] | Mesure | Additionne le temps entre deux valeurs différentes pour une dimension.<p>Ce composant doit être inclus dans votre vue de données pour que la [mesure calculée](/help/components/calc-metrics/default-calcmetrics.md) suivante soit disponible dans Workspace : <ul><li>Durée par personne</li><li>Durée par session</li></p> |

{style="table-layout:auto"}

## Composants standard facultatifs {#optional}

Les composants standard facultatifs sont disponibles sous l’onglet **[!UICONTROL Vues de données]** > **[!UICONTROL Modifier la vue de données]** > **[!UICONTROL Composants]** > onglet **[!UICONTROL Composants standard]**.

| Nom du composant | Dimension ou mesure | Notes et valeurs |
| --- | --- | --- |
| [!UICONTROL Matin/après-midi] | Dimension de répartition temporelle | Matin ou après-midi |
| [!UICONTROL ID de lot] | Dimension | Représente le lot Experience Platform dont faisait partie un [!UICONTROL Événement]. |
| [!UICONTROL Identifiant du jeu de données] | Dimension | Représente le jeu de données Experience Platform dont faisait partie un [!UICONTROL Événement]. |
| [!UICONTROL Jour du mois] | Dimension de répartition temporelle | 1-31 |
| [!UICONTROL Jour de la semaine] | Dimension de répartition temporelle | Lundi, mardi, mercredi, jeudi, vendredi, samedi, dimanche |
| [!UICONTROL Jour de l’année] | Dimension de répartition temporelle | 1-366 |
| [!UICONTROL Heure de la journée] | Dimension de répartition temporelle | 0-23 |
| [!UICONTROL &#x200B; Mois de l’année] | Dimension de répartition temporelle | Janvier - Décembre |
| [!UICONTROL Premières sessions] | Mesure | Première session définie par une personne dans la fenêtre de création de rapports. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Sessions récurrentes] | Mesure | Nombre de sessions qui n’ont pas été la première session d’une personne. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL ID de personne] | Dimension | Chaque schéma du jeu de données défini dans Experience Platform peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un espace de noms d’identité. N’importe laquelle de ces identité peut être utilisée comme ID de personne. Par exemple, l’ID de cookie, l’ID groupé, l’ID d’utilisateur ou d’utilisatrice, le code de suivi, etc. La dimension de [!UICONTROL l’ID de personne] est la base de la combinaison de jeux de données et de l’identification des personnes uniques dans Customer Journey Analytics.<p>Les cas d’utilisation possibles sont les suivants :<ul><li>Création d’un segment sur une valeur d’ID de personne spécifique pour segmenter tout jusqu’au comportement de cet utilisateur.</li><li>Débogage : s’assurer que les données d’un ID de cookie spécifique (ou d’un ID de client spécifique) sont présentes.</li><li>Identification des utilisateurs qui ont contacté un centre d’appel.</li></ul> |
| [!UICONTROL Espace de nommage de l’ID de personne] | Dimension | Le type d’ID dont [!UICONTROL l’ID de personne] est constitué. Exemple : `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID de compte global] | Dimension | Le [!UICONTROL ID de compte global], lorsque vous utilisez le conteneur de compte global dans votre connexion. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID de compte] | Dimension | Le [!UICONTROL ID de compte], lorsque vous utilisez le conteneur Compte dans votre connexion. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL Opportunity ID] | Dimension | Le [!UICONTROL ID d’opportunité], lorsque vous utilisez le conteneur d’opportunité dans votre connexion. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID de groupe d&#39;achat] | Dimension | L&#39;[!UICONTROL identifiant du groupe d&#39;achat], lorsque vous utilisez le conteneur du groupe d&#39;achat dans votre connexion. |
| [!UICONTROL Trimestre de l’année] | Dimension de répartition temporelle | T1, T2, T3, T4 |
| [!UICONTROL Session répétée] | Mesure | Nombre de sessions qui n’ont pas été la toute première session d’une personne. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Type de session] | Dimension | Cette dimension possède deux valeurs : 1. [!UICONTROL Première fois] et 2. Récurrent. L’élément de ligne [!UICONTROL Première fois] comprend tous les comportements (mesures comparées à cette dimension) d’une session déterminée comme étant la première session définie par une personne. Tous les autres éléments sont inclus dans l’élément de ligne [!UICONTROL Récurrent] (en supposant que tous ceux-ci appartiennent à une session). Lorsque les mesures ne font partie d’aucune session, elles sont incluses dans le compartiment « Non applicable » de cette dimension. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat) |
| [!UICONTROL Durée par événement] | Dimension | Regroupe la mesure [!UICONTROL Temps passé] dans des regroupements [!UICONTROL Événement]. |
| [!UICONTROL Durée par session] | Dimension | Regroupe la mesure [!UICONTROL Temps passé] dans des regroupements [!UICONTROL Session]. |
| [!UICONTROL Durée par personne] | Dimension | Regroupe la mesure [!UICONTROL Temps passé] dans des regroupements [!UICONTROL Personne]. |
| [!UICONTROL Week-end]/[!UICONTROL Jour de semaine] | Dimension de répartition temporelle | Week-end ou jour de la semaine |

{style="table-layout:auto"}
