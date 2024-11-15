---
title: Création des champs de mappage et du connecteur source Analytics
description: Découvrez comment créer les champs de mappage et de connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: aedf7a2ad41b09521938b789dbaf1c193cdb661f
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 2%

---

# Création des champs de mappage et du connecteur source Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

## Comprendre comment le connecteur source Analytics peut importer des données historiques dans Customer Journey Analytics

Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques en Customer Journey Analytics.

Ce processus suppose que vous souhaitiez [créer un schéma XDM lors de la mise à niveau vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), car vous souhaitez un schéma rationalisé adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.

Pour utiliser le connecteur source Analytics afin d’importer des données historiques dans Customer Journey Analytics, vous devez :

1. [Création d’un schéma XDM pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Créez les champs Connecteur source et Mappage Analytics, comme décrit ci-dessous.

1. [Ajout du jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Création des champs de mappage et du connecteur source Analytics

Une fois votre schéma XDM créé, vous devez créer le connecteur source Adobe Analytics à utiliser pour les données historiques. (Pour obtenir des instructions générales plus complètes sur la création d’un connecteur source, voir [Création d’une connexion source Adobe Analytics dans l’interface utilisateur](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).)

Pour créer un connecteur source Adobe Analytics à utiliser pour les données historiques :

1. Dans l’interface utilisateur de Platform, dans la section **[!UICONTROL Connexions]** du rail de gauche, sélectionnez **[!UICONTROL Sources]**.

1. Sélectionnez **[!UICONTROL Applications Adobe]** dans la liste des [!UICONTROL CATÉGORIES].

1. Sélectionnez **[!UICONTROL Ajouter des données]** dans la mosaïque Adobe Analytics.

   ![Fenêtre Adobe Experience Platform avec les sources sélectionnées avec les applications d&#39;Adobe et Ajouter des données surlignées.](./assets/sources-overview.png)

1. Sélectionnez **[!UICONTROL Suite de rapports]**, puis, dans la liste des suites de rapports, sélectionnez la suite de rapports contenant les données historiques que vous souhaitez utiliser dans Customer Journey Analytics.

   ![Fenêtre Adobe Experience Platform affichant la liste des suites de rapports](./assets/report-suites.png)

1. Sélectionnez **[!UICONTROL Suivant]** dans le coin supérieur droit de l’écran.

1. Sélectionnez **[!UICONTROL Schéma personnalisé]**, puis sélectionnez le schéma que vous avez créé dans [Créer un schéma XDM qui inclut le groupe de champs Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Mappez chaque dimension Adobe Analytics à une dimension de schéma XDM personnalisé.

   1. Dans la section **[!UICONTROL Mapper les champs standard]** , sélectionnez l’onglet **[!UICONTROL Personnalisé]** .

   1. Sélectionnez **[!UICONTROL Ajouter un nouveau mapping]**.

   ![Champs de schéma de carte](assets/schema-mapping.png)

   1. Dans le **[!UICONTROL champ Source]**, sélectionnez un champ Adobe Analytics dans le groupe de champs Modèle Adobe Analytics ExperienceEvent. Ensuite, dans le **[!UICONTROL champ cible]**, sélectionnez le champ XDM vers lequel vous souhaitez le mapper.

   1. Répétez cette procédure pour chaque champ du groupe de champs Modèle ExperienceEvent Adobe Analytics que vous utilisez pour collecter des données dans Adobe Analytics.

1. Sélectionnez **[!UICONTROL Suivant]** dans le coin supérieur droit de l’écran.

1. Nommez le flux de données et (facultatif) fournissez une description.

   ![Fenêtre Adobe Experience Platform mettant en surbrillance la section Détails du flux de données](./assets/dataflow-detail.png)

1. Sélectionnez **[!UICONTROL Suivant]** dans le coin supérieur droit de l’écran.

1. Vérifiez la connexion, puis sélectionnez **[!UICONTROL Terminer]**.

   ![Fenêtre Adobe Experience Platform mettant en surbrillance les sections Connexion et Type de données à réviser](./assets/review.png)

   Une fois la connexion créée, le flux de données est automatiquement créé pour renseigner un jeu de données avec les données Adobe Analytics de votre suite de rapports. Le flux de données ingère jusqu’à 13 mois de données historiques pour les environnements de test de production. Le renvoi des environnements de test hors production est limité à trois mois.

   Si vous utilisez le connecteur source Analytics pour importer des données historiques dans l’implémentation de votre SDK Web Customer Journey Analytics, vous devez ajouter ce jeu de données créé automatiquement à la connexion que vous avez créée pour l’implémentation de votre SDK Web.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
