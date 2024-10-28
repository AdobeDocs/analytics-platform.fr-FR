---
title: Création d’une vue de données dans Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 22%

---

# Création d’une vue de données dans Customer Journey Analytics

>[!NOTE]
>
>Cette documentation doit être utilisée après avoir rempli le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes précédentes qui ont été générées dynamiquement pour votre organisation.
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau générées dynamiquement pour votre organisation à partir du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

La création dʼune vue de données implique soit la création de mesures et de dimensions à partir dʼéléments de schéma, soit lʼutilisation de composants standard. La plupart des éléments de schéma peuvent être une dimension ou une mesure, selon les besoins de votre entreprise. Une fois que vous avez fait glisser un élément de schéma dans une vue de données, des options s’affichent à droite, où vous pouvez ajuster le fonctionnement de la dimension ou de la mesure dans Customer Journey Analytics.

Pour créer une vue de données :

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]**.

1. Sélectionnez **[!UICONTROL Créer une vue de données]**. Vous pouvez également sélectionner une vue de données existante dans la liste des vues de données pour la modifier.

1. Dans l’onglet [!UICONTROL **Configurer**] , spécifiez un nom pour la vue de données et configurez ses paramètres de base, ses composants et ses options de calendrier.

   Pour plus d&#39;informations sur chaque champ, voir [Configurer](/help/data-views/create-dataview.md#configure) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

   ![Configurer la vue de données](assets/dataview-configure.png)

1. Sélectionnez l’onglet [!UICONTROL **Composants**].

   L’onglet [!UICONTROL **Composants**] vous permet de définir les composants d’une vue de données, ce qui signifie que vous pouvez créer des mesures et des dimensions à partir d’éléments de schéma. Vous pouvez également utiliser des composants standard.

   ![Onglet Composants](assets/dataview-components.png)

1. À partir de l’onglet [!UICONTROL **Composants**], faites glisser les éléments de schéma du rail de gauche vers la section [!UICONTROL **Mesures**] ou la section [!UICONTROL **Dimensions**]. Les éléments de schéma que vous ajoutez deviennent des mesures ou des dimensions dans la vue de données.

   Pour plus d’informations sur les options disponibles lors de l’ajout de composants à une vue de données, voir [Composants](/help/data-views/create-dataview.md#components) dans [Création ou modification d’une vue de données](/help/data-views/create-dataview.md).

1. Sélectionnez l’onglet [!UICONTROL **Paramètres**]. À partir de là, vous pouvez configurer des filtres à appliquer à l’ensemble de votre vue de données et configurer le délai d’expiration de session et les mesures.

   Pour plus d’informations sur les options disponibles lors de la configuration des paramètres pour une vue de données, voir [Paramètres](/help/data-views/create-dataview.md#settings) dans [Création ou modification d’une vue de données](/help/data-views/create-dataview.md).

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration de votre vue de données.

1. Une fois tous les paramètres spécifiés, sélectionnez **[!UICONTROL Enregistrer et terminer]**.

1. Continuez à suivre les étapes de mise à niveau générées dynamiquement pour votre organisation à partir du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

