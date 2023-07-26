---
title: Sessions contextuelles
description: Paramètres d’une vue de données que vous pouvez utiliser pour définir des sessions contextuelles.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 6235fbb128098e2a624d5fd4fd72c2c583cfd277
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---


# Sessions contextuelles

Les sessions contextuelles dans les vues de données modifient la manière dont Customer Journey Analytics calcule les sessions à partir des données de votre connexion.

Dans le [!UICONTROL Paramètres] de vues de données, vous pouvez définir une session de n’importe quelle manière pour faire correspondre la manière dont les personnes interagissent avec vos expériences numériques. Les définitions de session contextuelles sont non destructives et ne modifient pas les données sous-jacentes. Vous pouvez configurer plusieurs vues de données, chacune avec sa définition de session contextuelle spécifique comme base de vos projets Workspace.

Pour définir le contexte d’une session pour une vue de données :

1. Sélectionner **[!UICONTROL Vues des données]** dans l’interface utilisateur de Customer Journey Analytics.

1. Créez ou modifiez une vue de données existante. Voir [Création ou modification d’une vue de données](create-dataview.md) pour plus d’informations.

1. Sélectionnez la variable **[!UICONTROL Paramètres]** . Sous-plan [!UICONTROL Paramètres de session]:

   1. Saisissez une valeur pour **[!UICONTROL Timeout de session]** in [!UICONTROL minutes], [!UICONTROL hour(s)], [!UICONTROL day(s)], ou [!UICONTROL week(s)]. Le délai d’expiration de la session détermine la durée pendant laquelle une session peut être inactive (aucun événement ne se produit) avant de démarrer une nouvelle session.

   2. Sélectionnez une mesure dans le **[!UICONTROL Déposer une mesure ici]** liste sous [!UICONTROL Démarrer une nouvelle session avec une mesure]. Vous pouvez également faire glisser et déposer une mesure à partir du volet de gauche sur le **[!UICONTROL Déposer un champ de mesure]**. La mesure sélectionnée définit le début d’une nouvelle session. Vous pouvez définir plusieurs mesures.

1. Sélectionner **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer et terminer]** pour enregistrer la définition de session contextuelle.

