---
title: Référence de composant standard
description: Détails et informations sur tous les composants standard que vous pouvez ajouter à n’importe quelle vue de données.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
source-git-commit: b4d2c564f9fc477212306dc022b4afc5ab92db97
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 92%

---

# Référence de composant standard

La plupart des dimensions et des mesures dans CJA sont basées sur des éléments de schéma de votre jeu de données Adobe Experience Platform. Cependant, plusieurs composants peuvent être ajoutés à une vue de données, quelle que soit la connexion que vous utilisez.

Les [!UICONTROL composants standard] sont des composants qui ne sont pas générés à partir des champs du schéma du jeux de données, mais qui sont générés par le système. Certains composants du système sont requis afin de faciliter les fonctionnalités de compte rendu des performances dans Analysis Workspace, tandis que dʼautres composants du système sont facultatifs.

![Composants standard](assets/standard-components.png)

## Composants standard requis

Ces composants standard requis sont ajoutés par défaut à chaque vue de données. Ils sont essentiels aux fonctionnalités de création de comptes rendus des performances proposées par Customer Journey Analytics.

| Nom du composant | Dimension ou mesure | Remarques |
| --- | --- | --- |
| [!UICONTROL Personnes] | Mesure | Basée sur lʼidentifiant de personne spécifié dans une [!UICONTROL Connexion]. |
| [!UICONTROL Sessions] | Mesure | En fonction des paramètres de session de la vue de données. |
| [!UICONTROL Événements] | Mesure | Cette mesure représente le nombre de lignes de tous les jeux de données dʼévénements dans une [!UICONTROL Connexion]. |
| [!UICONTROL Minute] | Dimension | La minute à laquelle un événement donné s’est produit (arrondi à l’unité inférieure). Le premier élément de dimension correspond à la première minute de la période, et le dernier élément de dimension correspond à la dernière minute de la période. |
| [!UICONTROL Heure] | Dimension | Heure à laquelle un événement donné s’est produit (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première heure de la période et le dernier élément de dimension correspond à la dernière heure de la période. |
| [!UICONTROL Jour] | Dimension | Le jour où un événement donné s’est produit. Le premier élément de dimension correspond au premier jour de la période et le dernier élément de dimension correspond au dernier jour de la période. |
| [!UICONTROL Semaine] | Dimension | La semaine où un événement donné s’est produit. Le premier élément de dimension correspond à la première semaine de la période et le dernier élément de dimension correspond à la dernière semaine de la période. |
| [!UICONTROL Mois] | Dimension | Le mois au cours duquel un événement donné s’est produit. Le premier élément de dimension correspond au premier mois de la période, et le dernier élément de dimension correspond au dernier mois de la période. |
| [!UICONTROL Trimestre] | Dimension | Le trimestre au cours duquel un événement donné s’est produit. Le premier élément de dimension correspond au premier trimestre de la période et le dernier élément de dimension correspond au dernier trimestre de la période. |
| [!UICONTROL Année] | Dimension | L’année au cours de laquelle un événement donné s’est produit. Le premier élément de dimension correspond à la première année de la période et le dernier élément de dimension correspond à la dernière année de la période. |

## Composants standard facultatifs

Les composants standard facultatifs sont disponibles sous l’onglet **[!UICONTROL Vues de données]** > **[!UICONTROL Modifier la vue de données]** > **[!UICONTROL Composants]** > onglet **[!UICONTROL Composants standard]**.

| Nom du composant | Dimension ou mesure | Remarques et les valeurs |
| --- | --- | --- |
| [!UICONTROL Matin/après-midi] | Dimension de répartition du temps | Matin ou après-midi |
| [!UICONTROL ID de lot] | Dimension | Représente le lot Experience Platform dont faisait partie un [!UICONTROL Événement]. |
| [!UICONTROL Identifiant du jeu de données] | Dimension | Représente le jeu de données Experience Platform dont faisait partie un [!UICONTROL Événement]. |
| [!UICONTROL Jour du mois] | Dimension de répartition du temps | 1-31 |
| [!UICONTROL Jour de la semaine] | Dimension de répartition du temps | Lundi, mardi, mercredi, jeudi, vendredi, samedi, dimanche |
| [!UICONTROL Jour de l’année] | Dimension de répartition du temps | 1-366 |
| [!UICONTROL Heure de la journée] | Dimension de répartition du temps | 0-23 |
| [!UICONTROL  Mois de l’année] | Dimension de répartition du temps | Janvier - Décembre |
| [!UICONTROL ID de personne] | Dimension | Chaque schéma de jeux de données défini dans Experience Platform peut disposer de son propre ensemble d’une ou de plusieurs identités définies et associées à un Espace de nommage d’identité. N’importe lequel de ces paramètres peut être utilisé comme ID de personne. Par exemple, l’ID de cookie, l’ID regroupé, l’ID utilisateur, le code de suivi, etc. Le [!UICONTROL ID de personne] La dimension est la base de la combinaison de jeux de données et de l’identification des visiteurs uniques dans CJA. |
| [!UICONTROL Espace de noms de l’ID de personne] | Dimension | Quel type d’identifiant la variable [!UICONTROL ID de personne] se compose de . Exemples : `email address`, `cookie ID`, `Analytics ID`, etc. |
| [!UICONTROL Trimestre de l’année] | Dimension de répartition du temps | T1, T2, T3, T4 |
| [!UICONTROL La session commence] | Mesure | Le nombre dʼévénements qui étaient le premier événement dʼune session. Lorsquʼelle est utilisée dans une définition de filtre (par exemple « [!UICONTROL Débuts de session] existe »), cette mesure ne filtre que le premier événement de chaque session. |
| [!UICONTROL La session se termine] | Mesure | Le nombre dʼévénements qui étaient le dernier événement dʼune session. Comme pour les [!UICONTROL Débuts de session], elle peut également être utilisée dans une définition de filtre pour filtrer les éléments jusquʼau dernier événement de chaque session. |
| [!UICONTROL Durée (secondes)] | Mesure | Additionne le temps entre deux valeurs différentes pour une dimension. |
| [!UICONTROL Durée par événement] | Dimension | Regroupe la mesure [!UICONTROL Temps passé] dans des regroupements [!UICONTROL Événement]. |
| [!UICONTROL Durée par session] | Dimension | Regroupe la mesure [!UICONTROL Temps passé] dans des regroupements [!UICONTROL Session]. |
| [!UICONTROL Durée par personne] | Dimension | Regroupe la mesure [!UICONTROL Temps passé] dans des regroupements [!UICONTROL Personne]. |
| [!UICONTROL Week-end]/[!UICONTROL Jour ouvrable] | Dimension de répartition du temps | Week-end ou Jour ouvrable |
