---
title: Gestion des connexions
description: Décrit comment gérer les connexions aux jeux de données Platform.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 22%

---


# Gestion des connexions

Une fois que vous avez créé une ou plusieurs connexions, vous pouvez les gérer dans le Gestionnaire [!UICONTROL Connexions]. Vous pouvez

* Supprimer une connexion.
* Renommer une connexion.
* Créer une vue de données à partir d’une connexion.
* Démarrer et arrêter la diffusion des données.

![Gestionnaire de connexions](assets/connections-manager.png)

1. Cliquez sur l’onglet **[!UICONTROL Connexions]**.

2. Sélectionnez la ou les connexions à modifier ou à gérer.

3. Procédez de l’une des manières suivantes :

   | Action | Description |
   |---|---|
   | [!UICONTROL Supprimer] | La suppression d’une connexion ne supprime pas le jeu de données, car les données sont toujours présentes dans [!DNL Adobe Experience Platform]. Voir &quot;Supprimer les connexions&quot; ci-dessous. |
   | [!UICONTROL Renommer] | Vous pouvez renommer la connexion avec un nom plus explicite. |
   | [!UICONTROL Créer une Vue de données] | Ce lien vous conduit au [Créateur de vues de données](/help/data-views/create-dataview.md). |
   | [!UICONTROL Début ou arrêt de la diffusion des données] | &quot;Diffusion en flux continu&quot; signifie que si de nouveaux lots sont ajoutés à l’un des jeux de données de la connexion, ces nouvelles données seront introduites dans [!UICONTROL Customer Journey Analytics] pour rapports. |

## Suppression de connexions

| Et si je... | Ceci se produit |
| --- | --- |
| Supprimer une connexion dans [!UICONTROL Customer Journey Analytics] ? | Un message d&#39;erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform] ? | La suppression d&#39;un jeu de données dans AEP interrompt le flux de données de ce jeu de données vers toute connexion incluant ce jeu de données. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] ? | Actuellement, vous ne pouvez pas supprimer un jeu de données dans une connexion qui a été enregistrée. Vous devrez supprimer toute la connexion et tout le début. (Cependant, vous pouvez supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform].) |
| Supprimer un lot d&#39;un jeu de données (dans [!UICONTROL Adobe Experience Platform]) ? | Si un lot est supprimé d&#39;un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toute connexion [!UICONTROL Customer Journey Analytics] contenant ce lot spécifique. [!UICONTROL Analyse du parcours du client ] averti des lots supprimés dans  [!UICONTROL Adobe Experience Platform]. |
| Supprimez un lot **lorsqu&#39;il est ingéré** dans [!UICONTROL Customer Journey Analytics] ? | S&#39;il n&#39;y a qu&#39;un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot n&#39;apparaîtra dans [!UICONTROL Customer Journey Analytics]. L&#39;ingestion sera annulée. Si, par exemple, le jeu de données contient 5 lots et que 3 d&#39;entre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
