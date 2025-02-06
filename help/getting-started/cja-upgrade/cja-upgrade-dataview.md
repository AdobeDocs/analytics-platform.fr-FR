---
title: Création d’une vue de données dans Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 20%

---

# Création d’une vue de données dans Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Création d’une vue de données dans Customer Journey Analytics"
>abstract="Une vue de données est un conteneur spécifique à Customer Journey Analytics qui vous permet de déterminer comment interpréter les données d’une connexion.<br><br>Bien que la création initiale de la vue de données prenne quelques minutes, la configuration de chaque dimension et mesure avec les paramètres de composant souhaités peut prendre plusieurs jours. Ajuster ces paramètres s’applique rétroactivement afin que votre entreprise puisse les affiner au fil du temps."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du questionnaire de mise à niveau d’[Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

La création dʼune vue de données implique soit la création de mesures et de dimensions à partir dʼéléments de schéma, soit lʼutilisation de composants standard. La plupart des éléments de schéma peuvent être une dimension ou une mesure, selon les besoins de votre entreprise. Une fois que vous avez fait glisser un élément de schéma dans une vue de données, des options s’affichent à droite, où vous pouvez ajuster le fonctionnement de la dimension ou de la mesure dans Customer Journey Analytics.

Pour créer une vue de données :

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]**.

1. Sélectionnez **[!UICONTROL Créer une vue de données]**. Vous pouvez également sélectionner une vue de données existante dans la liste des vues de données pour la modifier.

1. Dans l’onglet [!UICONTROL **Configurer**], spécifiez un nom pour la vue de données et configurez ses paramètres de base, composants et options de calendrier.

   Pour plus d’informations sur chaque champ, voir [Configurer](/help/data-views/create-dataview.md#configure) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

   ![Configurer la vue de données](assets/dataview-configure.png)

1. Sélectionnez l’onglet [!UICONTROL **Composants**].

   L’onglet [!UICONTROL **Composants**] vous permet de définir les composants d’une vue de données, ce qui signifie que vous pouvez créer des mesures et des dimensions à partir d’éléments de schéma. Vous pouvez également utiliser des composants standard.

   ![Onglet Composants](assets/dataview-components.png)

1. À partir de l’onglet [!UICONTROL **Composants**], faites glisser les éléments de schéma du rail de gauche vers la section [!UICONTROL **Mesures**] ou [!UICONTROL **Dimensions**]. Les éléments de schéma que vous ajoutez deviennent des mesures ou des dimensions dans la vue de données.

   Pour plus d’informations sur les options disponibles lors de l’ajout de composants à une vue de données, voir [Composants](/help/data-views/create-dataview.md#components) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

1. Sélectionnez l’onglet [!UICONTROL **Paramètres**]. Ensuite, vous pouvez configurer des filtres à appliquer à l’ensemble de votre vue de données et configurer les mesures et le délai d’expiration de la session.

   Pour plus d’informations sur les options disponibles lors de la configuration des paramètres d’une vue de données, voir [Paramètres](/help/data-views/create-dataview.md#settings) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md).

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la configuration de votre vue de données.

1. Une fois tous les paramètres spécifiés, sélectionnez **[!UICONTROL Enregistrer et terminer]**.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
