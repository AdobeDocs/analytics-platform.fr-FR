---
description: Les administrateurs et administratrices sont chargés de surveiller l’intégrité du dictionnaire de données. Cela inclut le fait de savoir si les composants collectent des données, sont approuvés, contiennent des descriptions et sont exempts de doublons.
title: Surveiller l’intégrité du dictionnaire de données
feature: Components
role: Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 94%

---

# Surveiller l’intégrité du dictionnaire de données

Les administrateurs de Customer Journey Analytics sont chargés de la maintenance d’un dictionnaire de données sain.

## Caractéristiques d’un dictionnaire de données intègre

Dans un dictionnaire de données intègre, tous les composants :

* sont utilisés et collectent des données ;

* contiennent des descriptions utiles pour que les utilisateurs et utilisatrices sachent comment les utiliser au mieux ;

* sont exempts de doublons superflus ;

* sont approuvés par l’administrateur ou l’administratrice.

## Vérifier l’intégrité de votre dictionnaire de données

Pour identifier les problèmes d’intégrité dans votre dictionnaire de données :

1. Ouvrez un projet Analysis Workspace.

1. Sélectionnez l’icône du dictionnaire de données sur le côté gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![Vue d’administration du dictionnaire de données.](assets/data-dictionary-admin.png)

1. Assurez-vous que la bonne suite de rapports est sélectionnée dans le menu déroulant.

1. Sur l’onglet [!UICONTROL **Intégrité du dictionnaire**], sélectionnez [!UICONTROL **Affichage**] en regard de l’une des options suivantes :

   * [!UICONTROL **composants sans description**],

   * [!UICONTROL **composants avec doublons**],

   * [!UICONTROL **composants sans données connectées**].

   Selon ce que vous sélectionnez, le filtre approprié est appliqué au dictionnaire de données et seuls les composants appropriés sont affichés.

1. Modifiez l’un des composants pour améliorer l’intégrité du dictionnaire de données. Pour plus d’informations sur la modification d’un composant dans le dictionnaire de données, voir [Modifier les entrées de composant dans le dictionnaire de données](/help/components/data-dictionary/edit-entries-data-dictionary.md).