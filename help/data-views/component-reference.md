---
title: Référence des composants standard
description: Détails et informations sur tous les composants standard que vous pouvez ajouter à n’importe quelle vue de données.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 58%

---


# Référence des composants standard

La plupart des dimensions et des mesures dans CJA sont basées sur des éléments de schéma de votre jeu de données Adobe Experience Platform. Cependant, plusieurs composants peuvent être ajoutés à une vue de données, quelle que soit la connexion que vous utilisez.

Les [!UICONTROL composants standard] sont des composants qui ne sont pas générés à partir des champs du schéma du jeux de données, mais qui sont générés par le système. Certains composants système sont nécessaires pour faciliter les fonctionnalités de création de rapports dans Analysis Workspace, tandis que d’autres composants système sont facultatifs.

![Composants standard](assets/standard-components.png)

## Composants standard requis

Ces composants standard requis sont ajoutés par défaut à chaque vue de données. Elles sont essentielles aux fonctionnalités de création de rapports offertes par Customer Journey Analytics.

| Nom du composant | Dimension ou mesure | Remarques |
| --- | --- | --- |
| [!UICONTROL Personnes] | Mesure | En fonction de l’ID de personne spécifié dans une [!UICONTROL connexion]. |
| [!UICONTROL Sessions] | Mesure | En fonction des paramètres de session de la vue de données. |
| [!UICONTROL Événements] | Mesure | Le nombre de lignes de tous les jeux de données d’événement dans une [!UICONTROL connexion]. |
| [!UICONTROL Minute] | Dimension | minute à laquelle un événement donné s’est produit (arrondi au bas). Le premier élément de dimension correspond à la première minute de la période, et le dernier élément de dimension correspond à la dernière minute de la période. |
| [!UICONTROL Heure] | Dimension | Heure à laquelle un événement donné s’est produit (arrondie à l’unité inférieure). Le premier élément de dimension correspond à la première heure de la période et le dernier élément de dimension correspond à la dernière heure de la période. |
| [!UICONTROL Jour] | Dimension | Le jour où un événement donné s’est produit. Le premier élément de dimension correspond au premier jour de la période et le dernier élément de dimension correspond au dernier jour de la période. |
| [!UICONTROL Semaine] | Dimension | La semaine où un événement donné s’est produit. Le premier élément de dimension correspond à la première semaine de la période et le dernier élément de dimension correspond à la dernière semaine de la période. |
| [!UICONTROL Mois] | Dimension | Le mois au cours duquel un événement donné s’est produit. Le premier élément de dimension correspond au premier mois de la période, et le dernier élément de dimension correspond au dernier mois de la période. |
| [!UICONTROL Trimestre] | Dimension | Le trimestre au cours duquel un événement donné s’est produit. Le premier élément de dimension correspond au premier trimestre de la période et le dernier élément de dimension correspond au dernier trimestre de la période. |
| [!UICONTROL Année] | Dimension | L’année au cours de laquelle un événement donné s’est produit. Le premier élément de dimension correspond à la première année de la période et le dernier élément de dimension correspond à la dernière année de la période. |

## Composants standard facultatifs

Facultatif Les composants standard sont disponibles sous **[!UICONTROL Vues de données]** > **[!UICONTROL Modifier la vue de données]** > **[!UICONTROL Onglet Composants]** > **[!UICONTROL Composants standard]**.

| Nom du composant | Dimension ou mesure | Remarques |
| --- | --- | --- |
| [!UICONTROL La session commence] | Mesure | Nombre d’événements qui ont été le premier événement d’une session. Lorsquʼelle est utilisée dans une définition de filtre (par exemple « [!UICONTROL Débuts de session] existe »), cette mesure ne filtre que le premier événement de chaque session. |
| [!UICONTROL La session se termine] | Mesure | Le nombre d’événements qui ont été le dernier événement d’une session. Comme pour les [!UICONTROL Débuts de session], elle peut également être utilisée dans une définition de filtre pour filtrer les éléments jusquʼau dernier événement de chaque session. |
| [!UICONTROL Durée (secondes)] | Mesure | Totalise le temps entre deux valeurs différentes pour une dimension. |
| [!UICONTROL Durée par événement] | Dimension | Regroupe la mesure [!UICONTROL Durée de la visite] dans les compartiments [!UICONTROL Événement]. |
| [!UICONTROL Durée par session] | Dimension | Regroupe la mesure [!UICONTROL Durée de la visite] dans les compartiments [!UICONTROL Session]. |
| [!UICONTROL Durée par personne] | Dimension | Regroupe la mesure [!UICONTROL Durée de la visite] dans les compartiments [!UICONTROL Personne]. |
| [!UICONTROL ID de lot] | Dimension | Représente le lot Experience Platform dont faisait partie un [!UICONTROL Événement]. |
| [!UICONTROL Identifiant du jeu de données] | Dimension | Représente le jeu de données Experience Platform dont faisait partie un [!UICONTROL Événement]. |
