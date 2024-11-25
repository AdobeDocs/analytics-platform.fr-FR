---
title: Création d’un schéma personnalisé pour Customer Journey Analytics
description: Découvrez comment créer un schéma personnalisé pour Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 45f2097d2f0657f623b825acb8d06ec6972f757f
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 48%

---

# Création d’un schéma personnalisé à utiliser avec l’implémentation de votre SDK Web Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

>[!IMPORTANT]
>
>Avant de commencer à créer votre schéma personnalisé, collaborez avec votre équipe de données et d’autres parties prenantes de votre entreprise pour identifier la conception de schéma idéale de votre entreprise pour Customer Journey Analytics et les autres applications Adobe Experience Platform que vous utilisez. Pour plus d’informations, voir [Architecte de votre schéma à utiliser avec Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

Adobe recommande de créer un schéma XDM (Experience Data Model) personnalisé à utiliser avec le SDK Web lors de la mise à niveau vers Customer Journey Analytics. Un schéma personnalisé permet de disposer d’un schéma rationalisé adapté aux besoins de votre entreprise et aux applications Platform spécifiques que vous utilisez. Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.

## Créer le schéma

Le schéma personnalisé que vous définissez pour votre implémentation du SDK Web représente le modèle des données que vous collectez dans Adobe Experience Platform.

Pour créer un schéma personnalisé :

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. Dans Adobe Experience Platform, dans le rail de gauche, sélectionnez **[!UICONTROL Schémas]** dans [!UICONTROL  DATA MANAGEMENT].

1. Sélectionnez **[!UICONTROL Créer un schéma]**.

1. À l’étape **[!UICONTROL Sélectionner une classe]** de l’assistant Créer un schéma :

   1. Sélectionnez **[!UICONTROL Experience Event]**.

      ![ Créez un schéma mettant en surbrillance l’événement d’expérience ](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Un schéma d’événement d’expérience est utilisé pour modéliser le _comportement_ d’un profil (comme le nom de la scène, le bouton Push à ajouter au panier). Un schéma de profil individuel est utilisé pour modéliser les _attributs_ de profil (nom, e-mail, sexe, etc.).

   1. Sélectionnez **[!UICONTROL Suivant]**.


1. Dans l’ [!UICONTROL étape de nom et de révision] de l’assistant [!UICONTROL Créer un schéma] :

   1. Saisissez un **[!UICONTROL nom d’affichage de schéma]** pour votre schéma et (facultatif) une **[!UICONTROL description]**.

      ![Créer une fenêtre de schéma présentant le nom de vos champs de schéma](assets/create-ee-schema-wizard-step-2.png)

   1. Sélectionnez **[!UICONTROL Terminer]**.

1. Ajoutez tous les groupes de champs qui contiennent les champs que vous souhaitez inclure dans votre schéma.

   Les groupes de champs sont des collections d’objets et d’attributs réutilisables permettant d’étendre facilement le schéma.

   1. Dans la section **[!UICONTROL Groupes de champs]**, sélectionnez **[!UICONTROL + Ajouter]**.

      ![Ajouter un groupe de champs](assets/add-field-group-button.png)

   1. Dans la boîte de dialogue [!UICONTROL Ajouter des groupes de champs], sélectionnez le groupe de champs **[!UICONTROL ExperienceEvent du SDK Web AEP]** dans la liste.

      ![Groupe de champs ExperienceEvent du SDK Web AEP](assets/select-aepwebsdk-experienceevent.png)

      Vous pouvez sélectionner le bouton Aperçu pour afficher un aperçu des champs qui font partie de ce groupe de champs, comme `web > webPageDetails > name`.

      ![Aperçu du groupe de champs ExperienceEvent du SDK Web AEP](assets/aepwebsdk-experiencevent-preview.png)

      Sélectionnez **[!UICONTROL Précédent]** pour fermer l’aperçu.

   1. (Facultatif) Sélectionnez d’autres groupes de champs à inclure.

   1. Sélectionnez **[!UICONTROL Ajouter des groupes de champs]**.

1. (Facultatif) Si vous souhaitez inclure des champs personnalisés dans votre schéma, créez un groupe de champs personnalisé et ajoutez-le au groupe de champs.

   1. Dans la section **[!UICONTROL Groupes de champs]**, sélectionnez **[!UICONTROL + Ajouter]**.

      ![Ajouter un groupe de champs](assets/add-field-group-button.png)

   1. Dans la boîte de dialogue [!UICONTROL Ajouter des groupes de champs], sélectionnez **[!UICONTROL Créer un groupe de champs]**.

   1. Spécifiez un nom d’affichage et une description facultative, puis sélectionnez **[!UICONTROL Ajouter des groupes de champs]**.

1. Sélectionnez **[!UICONTROL +]** en regard du nom du schéma dans le panneau [!UICONTROL Structure].

   ![Exemple du bouton Ajouter un champ de schéma](assets/example-schema-plus.png)

1. Dans le panneau [!UICONTROL Propriétés du champ], saisissez `Identification` en tant que nom et **[!UICONTROL Identification]** en tant que [!UICONTROL Nom d’affichage]. Sélectionnez **[!UICONTROL Objet]** en tant que [!UICONTROL Type] et **[!UICONTROL ExperienceEvent Core v2.1]** en tant que [!UICONTROL Groupe de champs].

   >[!NOTE]
   >
   >Si ce groupe de champs n’est pas disponible, recherchez un autre groupe contenant des champs d’identité. Ou [ créez un groupe de champs ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) et [ajoutez de nouveaux champs d’identité](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (comme `ecid`, `crmId` et d’autres dont vous avez besoin) au groupe de champs et sélectionnez ce nouveau groupe de champs.

   ![Objet d’identification](assets/identification-field.png)

   L’objet d’identification ajoute des fonctionnalités d’identification à votre schéma. Dans votre cas, vous souhaitez identifier les profils qui visitent votre site à l’aide de l’identifiant Experience Cloud et de l’adresse électronique. De nombreux autres attributs sont disponibles pour effectuer le suivi de l’identification de votre personne (par exemple, l’ID de client, l’ID de fidélité).

   Sélectionnez **[!UICONTROL Appliquer]** pour ajouter cet objet au schéma.

1. Sélectionnez le champ **[!UICONTROL ecid]** dans l’objet d’identification que vous venez d’ajouter, puis sélectionnez **[!UICONTROL Identité]**, **[!UICONTROL Identité principale]** et **[!UICONTROL ECID]** dans la liste [!UICONTROL Espace de noms d’identité] du panneau de droite.

   ![Spécifier l’ECID comme identité](./assets/specify-identity.png)

   Vous spécifiez Experience Cloud Identity comme identité principale qu’Adobe Experience Platform Identity Service peut utiliser pour combiner (regrouper) le comportement des profils avec le même ECID.

   Sélectionnez **[!UICONTROL Appliquer]**. Une icône d’empreinte digitale apparaît dans l’attribut ecid.

1. Sélectionnez le champ **[!UICONTROL e-mail]** dans l’objet d’identification que vous venez d’ajouter, puis sélectionnez **[!UICONTROL Identité]** et **[!UICONTROL E-mail]** dans la liste [!UICONTROL Espace de noms d’identité] du panneau [!UICONTROL Propriétés du champ].

   ![Spécifier l’e-mail comme identité](./assets/specify-email-identity.png)

   Vous spécifiez l’adresse e-mail en tant qu’autre identité qu’Adobe Experience Platform Identity Service peut utiliser pour combiner (regrouper) le comportement des profils.

   Sélectionnez **[!UICONTROL Appliquer]**. Une icône d’empreinte digitale apparaît dans l’attribut d’e-mail.

   Sélectionnez **[!UICONTROL Enregistrer]**.

1. (Facultatif) Si vous souhaitez intégrer Customer Journey Analytics à RTCDP, sélectionnez l’élément racine de votre schéma qui affiche le nom du schéma, puis sélectionnez le commutateur **[!UICONTROL Profile]**.

   Vous êtes invité à activer le schéma pour le profil. Une fois activé, lorsque les données sont ingérées dans des jeux de données basés sur ce schéma, ces données sont fusionnées dans le profil client en temps réel.

   Consultez [Activer le schéma à utiliser dans le profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile) pour plus d’informations.

   >[!IMPORTANT]
   >
   >Une fois que vous avez activé un schéma pour le profil, il ne peut pas être désactivé pour le profil.

   ![Activer un schéma pour le profil](./assets/enable-for-profile.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le schéma.

   Vous avez créé un schéma minimal qui modélise les données que vous pouvez capturer à partir du site Web. Le schéma permet d’identifier les profils à l’aide d’Experience Cloud Identity et de l’adresse e-mail. En activant le schéma pour le profil, vous vous assurez que les données capturées sur le site Web sont ajoutées au profil client en temps réel.

   En regard des données de comportement, vous pouvez également capturer les données d’attribut de profil du site (par exemple, les détails des profils s’abonnant à une newsletter).

   Pour capturer ces données de profil, vous devez :

   * Créer un schéma basé sur la classe Profil XDM individuel ;

   * Ajouter le groupe de champs Profil principal v2 au schéma ;

   * Ajouter un objet d’identification basé sur le groupe de champs Profil principal v2 ;

   * Définissez l’ID d’Experience Cloud comme identifiant principal et l’e-mail comme identifiant.

   * Activer le schéma pour le profil.

   Consultez [Créer et modifier des schémas dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=fr) pour plus d’informations sur l’ajout et la suppression de groupes de champs et de champs individuels dans un schéma.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
