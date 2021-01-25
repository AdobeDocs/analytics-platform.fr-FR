---
title: Gestion des connexions
description: Décrit comment gérer les connexions aux jeux de données Platform.
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---


# Gestion des connexions

Une fois que vous avez créé une ou plusieurs connexions, vous pouvez les gérer dans le gestionnaire de [!UICONTROL connexions]. Vous pouvez

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
   | [!UICONTROL Supprimer] | La suppression d’une connexion ne supprime pas le jeu de données, car les données sont toujours présentes dans [!DNL Adobe Experience Platform]. Voir « Suppression des connexions » ci-dessous. |
   | [!UICONTROL Renommer] | Vous pouvez renommer la connexion avec un nom plus explicite. |
   | [!UICONTROL Créer une vue de données] | Ce lien vous conduit au [Créateur de vues de données](/help/data-views/create-dataview.md). |
   | [!UICONTROL Démarrer ou arrêter la diffusion de données en flux continu] | « Diffusion en flux continu » signifie que si de nouveaux lots sont ajoutés à l’un des jeux de données de la connexion, ces nouvelles données sont importées dans [!UICONTROL Customer Journey Analytics] pour la création de comptes-rendus de performance. |

## Suppression des connexions

| Et si je… | Ceci se produit |
| --- | --- |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] ? | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprime un jeu de données dans [!UICONTROL Adobe Experience Platform] ? | La suppression d’un jeu de données dans AEP interrompt le flux de données entre ce jeu et les connexions qui l’incluent. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprime un jeu de données dans [!UICONTROL Customer Journey Analytics] ? | À l’heure actuelle, vous ne pouvez pas supprimer de jeu de données au sein d’une connexion qui a été enregistrée. Il vous faudrait supprimer la connexion entière et recommencer. (Toutefois, vous pouvez supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform].) |
| Supprime un lot d’un jeu de données (dans [!UICONTROL Adobe Experience Platform]) ? | Si un lot est supprimé d’un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toute connexion [!UICONTROL Customer Journey Analytics] contenant ce lot spécifique. [!UICONTROL Customer Journey Analytics] est averti des lots supprimés dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lors de son ingestion** dans [!UICONTROL Customer Journey Analytics] ? | Si le jeu de données ne contient qu’un seul lot, aucune des données ou données partielles de ce lot n’apparaît dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 d’entre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
