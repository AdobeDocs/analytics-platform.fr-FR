---
description: Découvrez comment partager des projets dans Analysis Workspace.
keywords: Partage Analysis Workspace
title: Partager des projets
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '2089'
ht-degree: 76%

---

# Partager des projets {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="Partager des projets"
>abstract="Vous pouvez partager l’un de ces rôles de projet avec d’autres utilisateurs et utilisatrices de votre entreprise."



Vous pouvez partager un projet Analysis Workspace avec les types de personnes suivants :

* Utilisateurs et groupes de votre organisation ayant accès à Customer Journey Analytics

  Vous pouvez partager l’accès Modifier, Dupliquer ou Afficher

* Personnes et groupes de votre organisation n’ayant pas accès à Adobe Customer Journey Analytics

  Les personnes destinataires ont un accès en lecture seule

* Personnes en dehors de votre organisation

  Les personnes destinataires ont un accès en lecture seule

Les [traitements](curate.md) appliqués avant le partage sont répercutés lorsque les personnes destinataires ouvrent le projet.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Partage de projet dans Analysis Workspace](https://video.tv.adobe.com/v/40030/?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


## Partager avec des utilisateurs, des utilisatrices et des groupes de votre organisation {#Add}

Vous pouvez partager un projet avec des utilisateurs, des utilisatrices ou des groupes Analysis Workspace existants de votre organisation. Lorsque vous partagez un projet comme décrit dans cette section, les utilisateurs avec lesquels vous partagez le projet doivent déjà disposer d’un compte Customer Journey Analytics.

Vous pouvez partager un rôle spécifique avec des utilisateurs et utilisatrices ou des groupes, ainsi que partager un lien.

* [Partager un rôle de projet spécifique](#share-a-specific-project-role)

* [Partager un lien vers un projet](#share-a-link-to-a-project)

## Partager un rôle de projet spécifique

Lorsque vous partagez un rôle de projet spécifique avec des utilisateurs et utilisatrices et des groupes de votre organisation, tenez compte des points suivants :

* Les rôles de projet (**[!UICONTROL Modifier l’original]**, **[!UICONTROL Modifier la copie]** et **[!UICONTROL Lecture seule]**) s’appliquent à l’utilisateur ou à l’utilisatrice et à un ID de projet spécifique. Les rôles de projet ne dépendent pas des autorisations d&#39;utilisateur gérées dans [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/fr/docs/core-services/interface/administration/admin-getting-started).

* Dans Customer Journey Analytics, les groupes sont définis par profils de produit dans l’[Admin Console Adobe Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/administration/admin-getting-started). Les administrateurs peuvent partager des ressources avec n’importe quel groupe, y compris *Tous*. Les personnes ne disposant pas de droit d’administration peuvent partager des projets avec des groupes dont elles sont membres, à l’exception de *Tous*.

* Si un utilisateur ou une utilisatrice reçoit plusieurs rôles, le rôle le plus élevé s’applique. Ce scénario peut se produire si un utilisateur est ajouté à la fois en tant que personne individuelle et en tant que membre d’un groupe. Par exemple, si un utilisateur ou une utilisatrice reçoit le rôle **[!UICONTROL Modifier l’original]** en tant que personne individuelle et le rôle **[!UICONTROL Lecture seule]** en tant que membre d’un groupe, la personne bénéficie d’une expérience de projet **[!UICONTROL Modifier l’original]**.

* Les administrateurs et administratrices se voyant attribuer un rôle **[!UICONTROL Modifier la copie]** ou **[!UICONTROL Lecture seule]** bénéficient de ces expériences limitées lorsqu’ils ouvrent un projet. Une personne chargée de l’administration peut remplacer son rôle par **[!UICONTROL Modifier l’original]** en partageant le projet avec elle-même, puis en accordant le rôle Modifier, comme décrit dans la procédure suivante.

* Si vous sélectionnez plusieurs projets à partager, les destinataires sont ajoutés à la liste existante des destinataires pour chaque projet.

  Par exemple, le projet A est déjà partagé avec les personnes destinataires 1, 2 et 3, tandis que le projet B est déjà partagé avec les personnes destinataires 4, 5 et 6.

  Les projets A et B sont ensuite partagés avec les personnes destinataires 4 et 7. La nouvelle liste de partage pour le projet A est désormais 1, 2, 3, 4 et 7, tandis que la nouvelle liste de partage pour le projet B est 4, 5, 6 et 7.

Pour partager un rôle de projet spécifique avec des utilisateurs et utilisatrices ou des groupes de votre organisation, procédez comme suit :

1. Dans Customer Journey Analytics, sélectionnez l’onglet [!UICONTROL **Workspace**], puis [!UICONTROL **Projets**] dans le panneau de gauche.

1. Cochez la case en regard d’un ou plusieurs projets que vous souhaitez partager, puis sélectionnez [!UICONTROL **Partager**].

   Ou

   Pour partager un projet individuel uniquement, vous pouvez ouvrir le projet que vous souhaitez partager, puis sélectionner **[!UICONTROL Partager]** > **[!UICONTROL Partager avec les utilisateurs et utilisatrices Workspace]**.
Si des modifications n’ont pas enregistrées, on vous invite d’abord à enregistrer votre projet.

   La boîte de dialogue Partage de projets s’affiche. Les sections [!UICONTROL **Partager par lien**] et [!UICONTROL **Paramètres**] de la boîte de dialogue ne sont visibles que lors du partage d’un seul projet.

   ![Fenêtre Partager le projet.](assets/share-proj-modal.png)

1. Ajoutez des personnes destinataires ou des groupes de personnes destinataires dans l’un des champs de rôle disponibles :

   **Modifier l’original :** les personnes destinataires peuvent **[!UICONTROL enregistrer]** les modifications dans un projet et agir en tant que personnes copropriétaires. Ce rôle est utile si vous souhaitez gérer un projet conjointement avec d’autres collègues. Ce rôle inclut la modification, la suppression et la modification des listes de destinataires pour un projet partagé. <br>Remarque : Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. Il est donc recommandé qu’un seul utilisateur modifie un projet à la fois. Si des projets sont enregistrés au même moment, la dernière version est conservée.

   **Modifier la copie :** les destinataires peuvent **[!UICONTROL enregistrer sous]** et ont accès au panneau de gauche. Les interactions avec le projet ne se limitent pas à ce rôle. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs et utilisatrices qui comprennent les données de votre organisation et comment utiliser Analysis Workspace. Mais vous ne souhaitez pas que ces utilisateurs modifient votre projet.

   **Lecture seule :** les destinataires ne peuvent pas **[!UICONTROL enregistrer]** ou **[!UICONTROL enregistrer sous]** et n’ont pas accès au panneau de gauche. Les interactions avec le projet sont également limitées. Ce rôle est utile si vous souhaitez partager un projet avec des personnes qui connaissent moins bien la structure de données de votre organisation, Analysis Workspace ou Customer Journey Analytics en général. Cependant, vous souhaitez tout de même que les utilisateurs et utilisatrices consomment des données et des insights dans un environnement sûr. En savoir plus sur l’[expérience de projet Lecture seule](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Conditionnel) Si vous partagez un seul projet, choisissez d’activer les options suivantes lors du partage du projet :

   * **Partager les composants intégrés au projet :** partagez avec l’ensemble des destinataires les segments, mesures calculées et périodes. Une fois partagés, ces composants apparaîtront dans le menu déroulant des composants de l’espace de travail de destination. Ce paramètre n’est pas persistant, il s’applique une seule fois, au moment du partage du projet.

   * **Définir comme page de destination pour les destinataires :** définit cette page comme page de destination pour les destinataires. Ce paramètre n’est pas persistant, il s’applique une seule fois, au moment du partage du projet.

1. Sélectionnez **[!UICONTROL Partager]**. (Si le projet a déjà été partagé, sélectionnez [!UICONTROL **Mettre à jour**].)

   Ou

   Sélectionnez **[!UICONTROL Traiter et partager]** pour appliquer automatiquement le traitement du projet. (Si le projet a déjà été partagé, sélectionnez **[!UICONTROL Traitement et mise à jour]**.) En savoir plus sur le [traitement du projet](curate.md).


## Partager un lien vers un projet

Lorsque vous partagez un lien comme décrit dans cette section, tenez compte des points suivants :

* Les destinataires qui utilisent le lien doivent se connecter à Customer Journey Analytics avant d’accéder au projet.

* Si la personne destinataire ne se voit pas attribuer de rôle et reçoit un [lien partageable](/help/analysis-workspace/curate-share/shareable-links.md) vers le projet (**[!UICONTROL Partager] > [!UICONTROL Obtenir le lien du projet]**), elle se verra attribuer un rôle par défaut. Les personnes chargées de l’administration reçoivent **[!UICONTROL Modifier l’original]** et les autres reçoivent **[!UICONTROL Modifier la copie]**.

Pour partager le lien du projet avec les utilisateurs et utilisatrices de votre organisation, procédez comme suit :

1. Enregistrez le projet. Si des modifications n’ont pas enregistrées, on vous invite à enregistrer votre projet avant de partager un lien.

1. Sélectionnez **[!UICONTROL Partager]** > **[!UICONTROL Partager avec les utilisateurs et utilisatrices Workspace]**, puis sélectionnez **[!UICONTROL Copier]** en regard du champ **[!UICONTROL Partager par lien]**.

   ![Projet de partage mettant en surbrillance le champ Partager par lien.](assets/share-proj-modal.png)

1. Partagez le lien avec les utilisateurs et utilisatrices de votre organisation. Vous pouvez par exemple le coller dans un e-mail, sur un site web interne, etc.

## Partager un projet avec n’importe quelle personne (pas de connexion nécessaire) {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="Exiger une authentification Experience Cloud"
>abstract="Votre organisation exige que les utilisateurs et utilisatrices se connectent à Experience Cloud pour pouvoir utiliser ce lien."


Vous pouvez accorder un [accès en lecture seule](/help/analysis-workspace/curate-share/view-only-projects.md) vers les projets Analysis Workspace à des personnes qui n’ont pas accès à Customer Journey Analytics. Cet accès accordé peut inclure :

* Personnes en dehors de votre organisation

* Personnes de votre organisation n’ayant pas accès à Customer Journey Analytics

>[!NOTE]
>
>Tenez compte des points suivants lors du partage d’un projet Analysis Workspace avec des personnes qui n’ont pas accès à Customer Journey Analytics :
>
>* La possibilité de partager un projet de cette manière peut être désactivée par l’administrateur ou l’administratrice de Customer Journey Analytics, comme décrit dans la section [Préférences](/help/analysis-workspace/user-preferences.md). Si vous ne pouvez pas partager un projet comme décrit dans cette section, cela signifie que votre administrateur ou votre administratrice Customer Journey Analytics a désactivé cette fonctionnalité.
>
>* Les projets avec plus de 50 visualisations étendues ne peuvent être partagés qu’avec des personnes qui ont accès à Customer Journey Analytics.
>
>* Les personnes avec lesquelles vous partagez le projet peuvent afficher les segments qui ont été appliqués au projet pendant le [traitement](curate.md).
> 
>* Les personnes avec lesquelles vous effectuez le partage peuvent modifier la période du projet. La période que vous avez définie pour le projet s’affiche par défaut.
>
>* Un projet peut devenir inaccessible si de nombreuses personnes tentent d’accéder simultanément à un lien donné. Par défaut, plus de 190 personnes peuvent accéder à un seul lien toutes les 5 minutes. Si votre organisation atteint cette limite, patientez 5 minutes, puis tentez à nouveau d’accéder au lien.
>
>* Pour les licences [!DNL Healthcare Shield] et [!DNL Privacy & Security Shield], la fonctionnalité [!UICONTROL Partager avec tout le monde] nécessite une authentification Experience Cloud. Pour les clientes et clients [!DNL Healthcare Shield], un avertissement de « conformité HIPAA » s’affiche, mais vous pouvez toujours utiliser cette fonctionnalité après l’authentification auprès d’Experience Cloud.

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Partager avec tout le monde](https://video.tv.adobe.com/v/3452452/?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


Pour partager un projet Analysis Workspace avec tout le monde, procédez comme suit :

1. Ouvrez le projet Analysis Workspace que vous souhaitez partager.

1. Sélectionnez **[!UICONTROL Partager]** > **[!UICONTROL Partager avec tout le monde]**.

   Si des modifications n’ont pas enregistrées, on vous invite à enregistrer votre projet.

   <!-- Add screen shot of new modal -->

1. Activez l’option **[!UICONTROL Le lien est actif]**, le cas échéant.

   Cette option crée un lien vers le projet qui peut être partagé avec tout le monde. Vous pouvez désactiver l’accès au projet à tout moment en désactivant cette option.

   La personne propriétaire du projet est également propriétaire de ce lien. La propriété du lien ne peut être transférée à une autre personne que lorsque la propriété du projet est transférée, comme décrit dans la section [Transférer les ressources de l’utilisateur ou de l’utilisatrice](/help/tools/asset-transfer/transfer-assets.md) dans le guide d’administration d’Analytics.

1. Indiquez si l’option de sécurité suivante doit être activée (cette option peut être contrôlée par votre administrateur ou administratrice Customer Journey Analytics) :

   * **[!UICONTROL Exiger une authentification Experience Cloud] :**

     Lorsque cette option est activée, les seules personnes qui peuvent accéder au projet sont celles qui peuvent se connecter à l’organisation Adobe Experience Cloud dans laquelle le projet que vous partagez a été créé. Toutefois, les personnes avec lesquelles vous partagez vos données n’ont pas nécessairement besoin d’avoir accès à Customer Journey Analytics.

     Les administrateurs et administratrices de Customer Journey Analytics peuvent configurer cette préférence pour l’entreprise, comme décrit dans [Préférences](/help/analysis-workspace/user-preferences.md). Selon la manière dont les administrateurs et administratrices ont configuré cette option, vous pouvez rencontrer les scénarios suivants :

      * Si cette option n’est pas visible, c’est que l’administrateur ou l’administratrice Customer Journey Analytics n’a pas activé cette fonctionnalité.

      * Si cette option est activée et que vous ne pouvez pas la désactiver, l’option verrouillée signifie que votre administrateur Customer Journey Analytics requiert une authentification Experience Cloud pour toute personne accédant aux projets Analysis Workspace. C’est toujours le cas pour les organisations disposant d’une licence Healthcare Shield.

1. En regard du champ **[!UICONTROL Partager avec tout le monde (pas de connexion nécessaire)]**, sélectionnez l’icône ![Lien](/help/assets/icons/Link.svg) pour copier le lien dans le presse-papiers de votre système.

1. Partagez le lien avec les personnes que vous souhaitez voir accéder au projet. Par exemple, vous pouvez coller le lien dans un e-mail.

   Toute personne avec laquelle vous partagez le lien peut visualiser le projet Analysis Workspace.

1. (Facultatif) Vous pouvez sélectionnez l’![icône Générer un lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) pour supprimer l’accès des personnes qui ont précédemment reçu un lien vers le projet. Un nouveau lien est généré, que vous pouvez partager avec les personnes que vous souhaitez voir accéder au projet.

1. Sélectionnez **[!UICONTROL Fermer]** pour fermer la boîte de dialogue de partage. Vos modifications sont automatiquement enregistrées.

## Afficher les projets partagés avec vous

Lorsqu’une personne partage un projet avec vous en [partageant un rôle de projet spécifique](#share-a-specific-project-role), vous pouvez accéder aux projets partagés à partir de l’[onglet Projets sur la page de destination d’Analytics](/help/getting-started/landing.md#navigate-the-projects-tab).

Lorsqu’une personne partage un projet avec vous en partageant un lien (soit à partir de l’onglet [Partager le projet](#share-a-link-to-a-project) soit à l’aide d’un [partager avec tout le monde](#share-a-project-with-anyone-no-login-required)), vous devez utiliser le lien qui a été partagé avec vous pour accéder au projet. Par exemple, le lien peut avoir été partagé dans un e-mail, sur un site web interne, etc.

## Partager des composants intégrés

Vous pouvez partager les composants incorporés qui font partie de votre projet.

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Partager des composants incorporés dans Analysis Workspace](https://video.tv.adobe.com/v/327496/?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

{{videoaa}}

>[!ENDSHADEBOX]


## Questions fréquentes {#FAQs}

| Question | Réponse |
|---|---|
| Que se passe-t-il si deux éditeurs enregistrent un projet en même temps ? | Les modifications ne sont pas fusionnées et la dernière version de projet enregistrée est conservée. Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. |
| En tant qu’administrateur, quelle expérience de projet puis-je voir ? | Les administrateurs et administratrices se voyant attribuer un rôle **[!UICONTROL Modifier la copie]** ou **[!UICONTROL Lecture seule]** bénéficient de ces rôles limités lorsqu’ils ouvrent un projet. En cas de besoin, une personne chargée de l’administration peut augmenter son rôle pour obtenir le rôle **[!UICONTROL Modifier l’original]** à tout moment via **[!UICONTROL Composants] > [!UICONTROL Projets]**. |
| Que se passe-t-il si un destinataire reçoit un rôle en tant qu’individu et un autre rôle en tant que membre d’un groupe ? | Si un destinataire est placé dans plusieurs rôles, il bénéficie toujours de la meilleure expérience. Par exemple, si un destinataire se voit attribuer le rôle **[!UICONTROL Modifier l’original]** en tant que personne individuelle et le rôle **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, l’utilisateur bénéficie d’une expérience de projet **[!UICONTROL Modifier l’original]**. |
| Quelle expérience obtient un destinataire s’il ouvre un lien de projet ? | Les destinataires reçoivent le rôle que vous leur avez attribué dans la boîte de dialogue modale de partage. Si la personne destinataire ne se voit pas attribuer un rôle et reçoit un lien vers le projet (**[!UICONTROL Partager]** > **[!UICONTROL Partager avec les utilisateurs Workspace]**, puis sélectionne **[!UICONTROL Copier]** en regard du champ **[!UICONTROL Partager par lien]**), est placée dans un rôle par défaut. Les administrateurs reçoivent les rôles **[!UICONTROL Modifier l’original]** et les non-administrateurs reçoivent les rôles **[!UICONTROL Modifier la copie]**. |
