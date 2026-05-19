---
title: Paramètres de session
description: Découvrez les paramètres d’une vue de données que vous pouvez utiliser pour définir la durée d’une session et le déclencheur pour lancer une nouvelle session
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
autotag-review: '2026-05-19T08:57:43.886Z'
TQID: 'https://experienceleague.adobe.com/79GGBxPwVb2uQytFBwgAP2QTd57VbjXuwQqq4oKGGUY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 65%

---

# Paramètres de session {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="Prévisualisation des données"
>abstract="Compare les données de cette vue de données aux données de la connexion. Le pourcentage de prévisualisation est basé sur le nombre total dans la connexion des **90 derniers jours**.<br><br/>Si la prévisualisation ne se charge pas, il se peut que votre connexion soit encore en train de remplir les données."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


Dans Customer Journey Analytics, vous pouvez définir une session de n’importe quelle façon pour faire correspondre la manière dont les personnes interagissent avec vos expériences numériques. Vous configurez les paramètres de session dans une vue de données.

Les paramètres de session sont non destructeurs et ne modifient pas les données sous-jacentes. Vous pouvez configurer plusieurs vues de données (chacune avec des paramètres de session spécifiques) comme base pour vos projets Workspace.

Pour définir le contexte d’une session dans une vue de données, procédez comme suit :

1. Sélectionnez **[!UICONTROL Vues de données]**, éventuellement dans **[!UICONTROL Gestion des données]**, dans la navigation principale de l’interface d’utilisation de Customer Journey Analytics.

1. Créez une nouvelle vue de données ou modifiez en une existante. Consultez [Créer ou modifier une vue de données](create-dataview.md) pour plus d’informations.

1. Sélectionnez l’onglet **[!UICONTROL Paramètres]**. Sous [!UICONTROL Paramètres de session] :

   1. Saisissez une valeur pour **[!UICONTROL Délai d’expiration de session]** en [!UICONTROL minutes], [!UICONTROL heures], [!UICONTROL jours] ou [!UICONTROL semaines]. Le délai d’expiration de la session détermine la durée pendant laquelle une session peut être inactive (aucun événement ne se produit) avant de démarrer une nouvelle session.

      Appliquez un délai d’expiration de session court (30 minutes, par exemple) si vous souhaitez analyser principalement les interactions en ligne. Vous pouvez, par exemple, analyser si les profils qui visitent les pages produits de votre boutique en ligne ajoutent des articles à leur panier ou s’ils effectuent des achats en ligne.

      Appliquez un long délai d’expiration de session (3 mois, par exemple) si vous combinez des données en ligne et hors ligne et souhaitez analyser si les clientes et les clients qui ont acheté un ou plusieurs produits ont appelé votre service clientèle dans les trois premiers mois suivant leur achat.

   1. Sélectionnez un segment dans le menu déroulant **[!UICONTROL Ajouter des segments]** si vous souhaitez segmenter une vue de données. Vous pouvez également faire glisser un segment depuis ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** dans le volet de gauche de l’**[!UICONTROL _Déposez un segment ici_]**.

      Seuls les segments partagés répertoriés et auxquels vous avez accès peuvent être évalués en fonction des composants que vous avez définis pour la vue de données.

   1. Sélectionnez une mesure dans le menu déroulant **[!UICONTROL Démarrer une nouvelle session avec une mesure]** . Vous pouvez également faire glisser une mesure depuis ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Mesures]** dans le volet gauche du **[!UICONTROL _Déposer une mesure ici_]**. La mesure sélectionnée définit le début d’une nouvelle session. Vous pouvez définir plusieurs mesures.

      Vous pouvez utiliser n’importe quel type de mesure pour définir une nouvelle session. Par exemple, imaginez que vous souhaitiez définir une nouvelle session chaque fois qu’un profil lance votre application mobile. Dans **[!UICONTROL Vue de données]** > **[!UICONTROL Composants]**, définissez un composant de type mesure, nommé **[!UICONTROL Launch]**, en fonction d’un champ de schéma **[!UICONTROL appInteraction]** **[!UICONTROL Name]**. Vous spécifiez en outre le composant de mesure **[!UICONTROL Launch]** pour ne comptabiliser la valeur que lorsque la valeur correspond à `launch`.

      ![Composant de mesure d’interaction de l’application Lancements](assets/component-launches.png)

      Ensuite, effectuez un glisser-déposer ou sélectionnez la mesure **[!UICONTROL Lancement]** pour définir une nouvelle session.

      ![Paramètres de session Lancements](assets/session-settings-launches-metric.png)



1. Sélectionnez **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer et terminer]** pour enregistrer les paramètres de session.
