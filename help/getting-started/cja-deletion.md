---
title: Conséquences de la suppression
description: Que se passe-t-il lorsque vous supprimez des connexions, des jeux de données ou des lots dans Customer Journey Analytics ou Adobe Experience Platform ?
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 3f20520a2021d9b6066b0492ed11a1a4619ab1d4
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 94%

---

# Conséquences de la suppression

Tenez compte des éléments suivants avant de supprimer des connexions, des jeux de données ou des lots dans Customer Journey Analytics ou Adobe Experience Platform :

| Lorsque vous... | Ceci se produit : |
| --- | --- |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Espace de travail qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul> |
| Supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform] | La suppression d’un jeu de données dans AEP interrompt le flux de données entre ce jeu et les connexions qui l’incluent. Les données de ce jeu de données ne sont pas automatiquement supprimées des connexions CJA associées. |
| Supprime un jeu de données dans [!UICONTROL Customer Journey Analytics] | À l’heure actuelle, vous ne pouvez pas supprimer de jeu de données au sein d’une connexion qui a été enregistrée. Il vous faudrait supprimer la connexion entière et recommencer. (Cependant, vous pouvez supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform].) |
| Supprime un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé d’un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toute connexion [!UICONTROL Customer Journey Analytics] contenant ce lot spécifique. [!UICONTROL Customer Journey Analytics] est averti des lots supprimés dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] | Sʼil n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot nʼapparaîtra dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprimer des jeux de données de recherche dans [!UICONTROL Adobe Experience Platform] | Bien que la suppression de jeux de données soit possible pour d’autres connecteurs source, elle n’est actuellement pas prise en charge pour [Connecteur source des classifications Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=fr). Si vous supprimez un jeu de données par erreur, contactez lʼassistance clientèle Adobe. |
