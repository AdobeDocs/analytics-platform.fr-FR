---
title: Sessions contextuelles
description: Paramètres d’une vue de données que vous pouvez utiliser pour définir des sessions contextuelles.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: ht
source-wordcount: '236'
ht-degree: 100%

---


# Sessions contextuelles

Les sessions contextuelles dans les vues de données modifient la manière dont Customer Journey Analytics calcule les sessions à partir des données de votre connexion.

Dans l’onglet [!UICONTROL Paramètres] des vues de données, vous pouvez définir une session de n’importe quelle façon pour faire correspondre la manière dont les personnes interagissent avec vos expériences numériques. Les définitions de sessions contextuelles sont non destructives et ne modifient pas les données sous-jacentes. Vous pouvez configurer plusieurs vues de données (chacune avec sa définition de session contextuelle spécifique) comme base pour vos projets Workspace.

Pour définir le contexte d’une session pour une vue de données :

1. Sélectionnez **[!UICONTROL Vues des données]** dans l’interface utilisateur de Customer Journey Analytics.

1. Créez une nouvelle vue de données ou modifiez en une existante. Consultez [Créer ou modifier une vue de données](create-dataview.md) pour plus d’informations.

1. Sélectionnez l’onglet **[!UICONTROL Paramètres]**. Sous [!UICONTROL Paramètres de session] :

   1. Saisissez une valeur pour **[!UICONTROL Délai d’expiration de session]** en [!UICONTROL minutes], [!UICONTROL heures], [!UICONTROL jours] ou [!UICONTROL semaines]. Le délai d’expiration de la session détermine la durée pendant laquelle une session peut être inactive (aucun événement ne se produit) avant de démarrer une nouvelle session.

   2. Sélectionnez une mesure dans la liste **[!UICONTROL Déposer une mesure ici]** liste sous [!UICONTROL Démarrer une nouvelle session avec une mesure]. Vous pouvez également faire glisser et déposer une mesure à partir du volet de gauche sur le **[!UICONTROL champ Déposer une mesure]**. La mesure sélectionnée définit le début d’une nouvelle session. Vous pouvez définir plusieurs mesures.

1. Sélectionnez **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer et terminer]** pour enregistrer la définition de session contextuelle.
