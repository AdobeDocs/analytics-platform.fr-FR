---
title: Créer une vue de données dans Customer Journey Analytics
description: En savoir plus sur le chemin recommandé lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
TQID: https://experienceleague.adobe.com/rQL8R2D1JeIabt-iQSyYGY74N5JkP3hTN-x2kj-swXU
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 95%

---

# Créer une vue de données dans Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Créer une vue de données dans Customer Journey Analytics"
>abstract="Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion.<br><br>Bien que la création initiale de la vue de données prenne quelques minutes, la configuration de chaque dimension et mesure avec les paramètres de composant souhaités peut prendre plusieurs jours. Ajuster ces paramètres s’applique rétroactivement afin que votre entreprise puisse les affiner au fil du temps."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

La création dʼune vue de données implique soit la création de mesures et de dimensions à partir dʼéléments de schéma, soit lʼutilisation de composants standard. La plupart des éléments de schéma peuvent être une dimension ou une mesure selon les besoins de votre entreprise. Une fois que vous avez fait glisser un élément de schéma dans une vue de données, des options s’affichent à droite, où vous pouvez ajuster le fonctionnement de la dimension ou de la mesure dans Customer Journey Analytics.

Pour créer une vue de données, procédez comme suit :

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et sélectionnez **[!UICONTROL Vues de données]**, éventuellement à partir de **[!UICONTROL Gestion des données]**, dans le menu supérieur.

1. Sélectionnez **[!UICONTROL Créer une vue de données]**. Vous pouvez également sélectionner une vue de données existante dans la liste des vues de données pour la modifier.

1. Dans l’onglet [!UICONTROL **Configurer**], spécifiez un nom pour la vue de données et configurez ses paramètres, composants et options de calendrier de base.

   Pour plus d’informations sur chaque champ, consultez [Configurer](/help/data-views/create-dataview.md#configure) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

   ![Configurer la vue de données](assets/dataview-configure.png)

1. Sélectionnez l’onglet [!UICONTROL **Composants**].

   L’onglet [!UICONTROL **Composants**] est l’endroit où vous définissez les composants d’une vue de données, ce qui signifie que vous pouvez créer des mesures et des dimensions à partir d’éléments de schéma. Vous pouvez également utiliser des composants standard.

   ![Onglet Composants](assets/dataview-components.png)

1. À partir de l’onglet [!UICONTROL **Composants**], faites glisser les éléments de schéma du rail de gauche vers la section [!UICONTROL **Mesures**] ou [!UICONTROL **Dimensions**]. Les éléments de schéma que vous ajoutez deviennent des mesures ou des dimensions dans la vue de données.

   Pour plus d’informations sur les options disponibles lors de l’ajout de composants à une vue de données, consultez [Composants](/help/data-views/create-dataview.md#components) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

1. Sélectionnez l’onglet [!UICONTROL **Paramètres**]. À partir de là, vous pouvez configurer des segments à appliquer à l’ensemble de votre vue de données et configurer les mesures et le délai d’expiration de la session.

   Pour plus d’informations sur les options disponibles lors de la configuration des paramètres d’une vue de données, consultez [Paramètres](/help/data-views/create-dataview.md#settings) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration de votre vue de données.

1. Une fois tous les paramètres spécifiés, sélectionnez **[!UICONTROL Enregistrer et terminer]**.

{{upgrade-final-step}}
