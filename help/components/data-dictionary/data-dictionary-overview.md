---
description: Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices de cataloguer et de suivre les différents composants dans Analysis Workspace, y compris leur utilisation prévue, ceux qui sont approuvés, ceux qui sont des doublons, etc.
title: Présentation du dictionnaire de données
feature: Components
role: User, Admin
exl-id: 8e4b8169-7c7f-4a58-a6c6-70efb0c86ce8
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 67%

---

# Présentation du dictionnaire de données

Le dictionnaire de données dans Analysis Workspace permet aux utilisateurs et utilisatrices, et aux administrateurs et administratrices, de suivre et de mieux comprendre les composants dans leur environnement Analytics.

Les administrateurs d’Analytics sont chargés de traiter les informations sur chaque composant du dictionnaire de données afin de les mettre à la disposition des utilisateurs.

## Avantages pour les utilisateurs et utilisatrices

Le dictionnaire de données permet aux utilisateurs et utilisatrices de mieux comprendre chaque composant disponible.

Les informations disponibles dans le dictionnaire de données incluent :

* La fonction et l’utilisation prévue d’un composant

* Les composants généralement utilisés avec celui que vous consultez

* Les composants similaires à celui que vous consultez

* Si un composant est approuvé par l’administrateur ou l’administratrice système

Pour plus d’informations sur l’accès au dictionnaire de données et pour plus d’informations sur les informations qu’il contient, voir [Affichage des informations sur les composants dans le dictionnaire de données](/help/components/data-dictionary/view-data-dictionary.md).

## Avantages pour les administrateurs et administratrices

Le dictionnaire de données permet aux administrateurs et administratrices système de suivre et de traiter les composants dans leur environnement Analytics.

Voici quelques-unes des façons dont les administrateurs et administratrices d’Analytics peuvent utiliser le dictionnaire de données :

* Identifier les composants en double qui doivent être consolidés.

* Identifier les composants qui ne collectent aucune donnée afin qu’ils puissent être mis à jour ou supprimés.

* Identifier les composants qui ne sont pas encore approuvés.

* Mettre à jour les descriptions des composants directement dans Analysis Workspace. Toutes les mises à jour apportées aux descriptions de composant dans le dictionnaire de données sont répercutées dans la vue de données.

   De même, toutes les mises à jour apportées aux descriptions de composant dans la vue de données sont répercutées dans Analysis Workspace.

   Pour plus d’informations sur l’ajout de descriptions de composant dans Analysis Workspace ou dans une vue de données, voir [Ajout de descriptions de composant](/help/components/add-component-descriptions.md).

## Accéder au dictionnaire de données

Vous pouvez accéder au dictionnaire de données de l’une des manières suivantes dans Analysis Workspace :

* Depuis l’icône **Dictionnaire de données** dans le rail de gauche.

   ![Icône du dictionnaire de données dans le rail de gauche.](assets/data-dictionary-access-icon.png)

* Depuis l’icône **Dictionnaire de données** dans la fenêtre contextuelle d’informations d’un composant.

   ![Icône du dictionnaire de données dans la fenêtre contextuelle d’informations.](assets/data-dictionary-access-infopopover.png)
   <!--update screenshot; this was taken from a mock-->

* Depuis le menu : [!UICONTROL **Aide**] > [!UICONTROL **Dictionnaire de données**].

Pour plus d’informations sur les différentes options disponibles dans le dictionnaire de données, voir [Affichage des informations sur les composants dans le dictionnaire de données](/help/components/data-dictionary/view-data-dictionary.md).

## Mise à jour et traitement du dictionnaire de données

Les administrateurs de Customer Journey Analytics sont chargés de gérer un dictionnaire de données sain pour leur organisation, comme décrit dans la section [Surveillance de l’intégrité du dictionnaire de données](/help/components/data-dictionary/monitor-data-dictionary-health.md).

Dans le cadre de ce processus, les administrateurs CJA peuvent modifier des informations sur chaque composant du dictionnaire de données, comme décrit dans la section [Modifier les entrées de composant dans le dictionnaire de données](/help/components/data-dictionary/edit-entries-data-dictionary.md).

## Déplacer, réduire ou fermer le dictionnaire de données

Lorsque vous ouvrez le dictionnaire de données (comme décrit dans [Accéder au dictionnaire de données](#access-the-data-dictionary)), il s’affiche sous la forme d’une fenêtre par-dessus Analysis Workspace.

Vous pouvez manipuler la fenêtre du dictionnaire de données de l’une des manières suivantes :

* Faites-la glisser dans n’importe quelle zone d’Analysis Workspace.

   Si vous fermez et rouvrez Analysis Workspace, la fenêtre du dictionnaire de données reste à l’emplacement où vous l’avez déplacée pour la dernière fois. <!--True?-->

* Réduire le dictionnaire de données

   Une fois réduit, le dictionnaire de données s’affiche sous la forme d’un onglet bleu dans le coin inférieur droit d’Analysis Workspace.

   Lorsque vous sélectionnez l’onglet bleu, le dictionnaire de données s’ouvre sur le composant que vous avez consulté le plus récemment.

* Fermer le dictionnaire de données
