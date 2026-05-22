---
title: Créer des champs de mappage et du connecteur source Analytics
description: Découvrir comment créer des champs de mappage et du connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
autotag-review: '2026-05-19T08:18:13.585Z'
TQID: 'https://experienceleague.adobe.com/IQVDwcpMVnEa-dFXbNkpmHQRofC6d8z2ocf-PIaK--Q'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 758
ht-degree: 100%

---

# Créer des champs de mappage et du connecteur source Analytics {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Créer le connecteur source Analytics"
>abstract="Utilisez le connecteur source Analytics pour ingérer les données de suite de rapports à utiliser dans Customer Journey Analytics.<br><br>La création du connecteur source Analytics ne prend que quelques minutes avec les paramètres par défaut."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Créer des champs de mappage de schéma et du connecteur source Analytics"
>abstract="Le connecteur source doit savoir comment mapper les champs Adobe Analytics au schéma de votre organisation. Utilisez cette interface pour fournir ce mappage au connecteur source. Cette étape fait partie de l’ajout de données historiques à Customer Journey Analytics.<br><br>Le temps nécessaire à cette étape dépend fortement du nombre de dimensions et de mesures que vous devez mapper. Cette étape n’est pas vraiment difficile, elle est plutôt fastidieuse et répétitive. Le mappage du train de données devrait prendre environ une semaine."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Comprendre comment le connecteur source Analytics peut importer des données historiques dans Customer Journey Analytics.

Vous pouvez utiliser le connecteur source Analytics pour importer les données des suites de rapports Adobe Analytics dans Adobe Experience Platform. Ces données peuvent ensuite être utilisées comme données historiques dans Customer Journey Analytics.

Ce processus suppose que vous souhaitez [créer un schéma personnalisé à utiliser avec votre implémentation du SDK web Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), car vous souhaitez un schéma rationalisé et adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.

Pour utiliser le connecteur source Analytics afin d’importer des données historiques dans Customer Journey Analytics, vous devez effectuer ce qui suit :

1. [Créer un schéma personnalisé pour le connecteur source Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Si vous ne disposez pas déjà d’un connecteur source Analytics, créez le connecteur source Analytics et mappez les champs à votre schéma personnalisé de SDK web, comme décrit ci-dessous.

   Ou

   Si vous disposez déjà d’un connecteur source Analytics, [mappez les champs du connecteur source à votre schéma personnalisé de SDK web](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Ajouter le jeu de données du connecteur source Analytics à la connexion](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Créer des champs de mappage et du connecteur source Analytics

Une fois votre schéma personnalisé créé, vous devez créer le connecteur source Adobe Analytics à utiliser pour les données historiques. (Pour obtenir des instructions générales plus complètes sur la création d’un connecteur source, consultez [Création d’une connexion source Adobe Analytics dans l’interface d’utilisation](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr).)

Pour créer un connecteur source Adobe Analytics à utiliser pour les données historiques, procédez comme suit :

1. Dans l’interface d’utilisation de Platform, dans la section **[!UICONTROL Connexions]** du rail de gauche, sélectionnez **[!UICONTROL Sources]**.

1. Sélectionnez **[!UICONTROL Applications Adobe]** dans la liste des [!UICONTROL CATÉGORIES].

1. Sélectionnez **[!UICONTROL Ajouter des données]** dans la tuile Adobe Analytics.

   ![Fenêtre Adobe Experience Platform avec les sources sélectionnées et les applications Adobe et Ajouter des données en surbrillance.](./assets/sources-overview.png)

1. Sélectionnez **[!UICONTROL Suite de rapports]** puis, dans la liste des suites de rapports, sélectionnez la suite de rapports contenant les données historiques à utiliser dans Customer Journey Analytics.

   ![Fenêtre Adobe Experience Platform affichant la liste Suites de rapports](./assets/report-suites.png)

1. Sélectionnez **[!UICONTROL Suivant]** dans le coin supérieur droit de l’écran.

1. Sélectionnez **[!UICONTROL Schéma personnalisé]**, puis sélectionnez le schéma que vous avez créé dans [Création d’un schéma personnalisé qui inclut le groupe de champs Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md). <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. Mappez chaque dimension Adobe Analytics à une dimension de schéma personnalisée.

   1. Dans la section **[!UICONTROL Mapper les champs standard]**, sélectionnez l’onglet **[!UICONTROL Personnalisé]**.

   1. Sélectionnez **[!UICONTROL Ajouter un nouveau mappage]**.

   ![Champs de schéma de recherche](assets/schema-mapping.png)

   1. Dans le **[!UICONTROL champ Source]** sélectionnez un champ Adobe Analytics dans le groupe de champs Modèle ExperienceEvent Adobe Analytics. Ensuite, dans le **[!UICONTROL Champ cible]**, sélectionnez le champ personnalisé du schéma XDM vers lequel vous souhaitez le mapper.

      Tous les champs Adobe Analytics n’ont pas de champ correspondant dans XDM en raison des différences d’architecture inhérentes entre AppMeasurement et XDM.

   1. Répétez cette procédure pour chaque champ du groupe de champs Modèle ExperienceEvent Adobe Analytics que vous utilisez pour collecter des données dans Adobe Analytics.

1. Sélectionnez **[!UICONTROL Suivant]** dans le coin supérieur droit de l’écran.

1. Nommez le flux de données et (facultatif) fournissez une description.

   ![Fenêtre Adobe Experience Platform mettant en surbrillance la section Détails du flux de données](./assets/dataflow-detail.png)

1. Sélectionnez **[!UICONTROL Suivant]** dans le coin supérieur droit de l’écran.

1. Vérifiez la connexion et sélectionnez **[!UICONTROL Terminer]**.

   ![Fenêtre Adobe Experience Platform mettant en surbrillance les sections Connexion et Type de données pour révision](./assets/review.png)

   Une fois la connexion créée, le flux de données est automatiquement créé pour renseigner un jeu de données avec les données Adobe Analytics de votre suite de rapports. Le flux de données ingère jusqu’à 13 mois de données historiques pour les sandbox de production. Le renvoi dans les sanbox hors production est limité à 3 mois.

   Si vous utilisez le connecteur source Analytics pour importer des données historiques dans votre implémentation du SDK web Customer Journey Analytics, vous devez ajouter ce jeu de données créé automatiquement à la connexion que vous avez créée pour votre implémentation du SDK web.

{{upgrade-final-step}}
