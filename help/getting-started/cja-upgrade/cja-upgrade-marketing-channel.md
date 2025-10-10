---
title: Créer un champ dérivé de canal marketing pour Customer Journey Analytics
description: Découvrir comment créer un champ dérivé de canal marketing pour Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---

# Créer un champ dérivé de canal marketing pour Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Créer un champ dérivé de canal marketing"
>abstract="Les champs dérivés sont créés dans une vue de données.<br><br>L’utilisation d’une configuration de canal marketing par défaut ne prend que quelques minutes ; la création d’une configuration de canal marketing hautement personnalisée peut prendre plusieurs heures."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Lors de l’utilisation du connecteur source Analytics, les données des canaux marketing sont transmises dans Customer Journey Analytics par le biais de ce connecteur. Les règles de canal marketing sont toujours configurées dans la version standard d’Adobe Analytics et certaines règles ne sont pas prises en charge. Pour plus d’informations, consultez [Utilisation de dimensions de canal marketing](/help/use-cases/aa-data/marketing-channels.md).

Pour utiliser les canaux marketing dans Customer Journey Analytics lors de l’utilisation du SDK web Experience Platform, vous pouvez utiliser des champs dérivés dans une vue de données afin de recréer les mêmes canaux marketing et règles de traitement pour Customer Journey Analytics.

1. Dans Customer Journey Analytics, sélectionnez la vue de données dans laquelle vous souhaitez ajouter des canaux marketing.

1. Dans la vue de données, sélectionnez l’onglet **[!UICONTROL Composants]**.

1. Sélectionnez **[!UICONTROL Créer un champ dérivé]** dans le rail de gauche.

1. Dans la boîte de dialogue **[!UICONTROL Créer un champ dérivé]**, sélectionnez **[!UICONTROL Modèles de fonction]** dans le menu déroulant.

   ![Créer des modèles de fonction de champ dérivé](assets/derived-field-create.png)

1. Faites glisser le modèle **[!UICONTROL Canaux marketing]** sur la zone de travail vierge.

1. Personnalisez la logique de chaque canal marketing pour vous assurer qu’elle correspond à la logique que vous utilisez pour identifier chaque canal dans votre environnement Adobe Analytics.

   Vous pouvez modifier les noms des canaux de sortie ou ajouter une logique pour identifier des canaux supplémentaires spécifiques à votre organisation.

1. Dans la colonne de droite, indiquez un nom et une description pour le canal marketing.

1. Sélectionnez **[!UICONTROL Enregistrer]**.

   Votre nouveau champ dérivé est ajouté à Champs dérivés > conteneur, au sein des champs de schéma dans le rail de gauche de votre vue de données.

{{upgrade-final-step}}
