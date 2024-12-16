---
title: Paramètres de session
description: Paramètres d’une vue de données à utiliser pour définir la durée d’une session ainsi que le déclencheur pour lancer une nouvelle session
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: edd49ea60901acc0bb4ba603bbb9377aeee423fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 91%

---

# Paramètres de session {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_settings_datapreview"
>title="Prévisualisation des données"
>abstract="Compare les données de ce filtre aux données de la connexion. Le pourcentage de prévisualisation est basé sur le nombre total dans la connexion des **90 derniers jours**.<br><br/>Si l’aperçu ne se charge pas, votre connexion peut encore être en cours de remplissage."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


Dans Customer Journey Analytics, vous pouvez définir une session de n’importe quelle façon pour faire correspondre la manière dont les personnes interagissent avec vos expériences numériques. Vous configurez les paramètres de session dans une vue de données.

Les paramètres de session sont non destructeurs et ne modifient pas les données sous-jacentes. Vous pouvez configurer plusieurs vues de données (chacune avec des paramètres de session spécifiques) comme base pour vos projets Workspace.

Pour définir le contexte d’une session dans une vue de données, procédez comme suit :

1. Sélectionnez **[!UICONTROL Vues des données]** dans l’interface utilisateur de Customer Journey Analytics.

2. Créez une nouvelle vue de données ou modifiez en une existante. Consultez [Créer ou modifier une vue de données](create-dataview.md) pour plus d’informations.

3. Sélectionnez l’onglet **[!UICONTROL Paramètres]**. Sous [!UICONTROL Paramètres de session] :

   1. Saisissez une valeur pour **[!UICONTROL Délai d’expiration de session]** en [!UICONTROL minutes], [!UICONTROL heures], [!UICONTROL jours] ou [!UICONTROL semaines]. Le délai d’expiration de la session détermine la durée pendant laquelle une session peut être inactive (aucun événement ne se produit) avant de démarrer une nouvelle session.

      Appliquez un délai d’expiration de session court (30 minutes, par exemple) si vous souhaitez analyser principalement les interactions en ligne. Vous pouvez, par exemple, analyser si les profils qui visitent les pages produits de votre boutique en ligne ajoutent des articles à leur panier ou s’ils effectuent des achats en ligne.

      Appliquez un long délai d’expiration de session (3 mois, par exemple) si vous combinez des données en ligne et hors ligne et souhaitez analyser si les clientes et les clients qui ont acheté un ou plusieurs produits ont appelé votre service clientèle dans les trois premiers mois suivant leur achat.


   2. Sélectionnez une mesure dans la liste **[!UICONTROL Déposer une mesure ici]** liste sous **[!UICONTROL Démarrer une nouvelle session avec une mesure]**. Vous pouvez également faire glisser et déposer une mesure à partir du volet de gauche sur le **[!UICONTROL champ Déposer une mesure]**. La mesure sélectionnée définit le début d’une nouvelle session. Vous pouvez définir plusieurs mesures.

      Vous pouvez utiliser n’importe quel type de mesure pour définir une nouvelle session. Par exemple, imaginez que vous souhaitiez définir une nouvelle session chaque fois qu’un profil lance votre application mobile. Dans **[!UICONTROL Vue des données]** > **[!UICONTROL Composants]**, vous définissez un composant de type mesure nommé **[!UICONTROL Lancements]**, basé sur un champ de schéma **[!UICONTROL Nom]** **[!UICONTROL appInteraction]**. Ensuite, vous spécifiez le composant de mesure **[!UICONTROL Lancements]** pour qu’il ne compte la valeur que lorsqu’elle correspond à `launch`.

      ![Composant de mesure d’interaction de l’application Lancements](assets/component-launches.png)

      Faites ensuite glisser-déposer, ou sélectionnez la mesure **[!UICONTROL Lancements]** en tant que mesure pour définir une nouvelle session.

      ![Paramètres de session Lancements](assets/session-settings-launches-metric.png)



4. Sélectionnez **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer et terminer]** pour enregistrer les paramètres de session.
