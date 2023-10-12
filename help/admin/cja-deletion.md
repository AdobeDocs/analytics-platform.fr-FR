---
title: Conséquences de la suppression
description: Que se passe-t-il lorsque vous supprimez des connexions, des jeux de données ou des lots dans Customer Journey Analytics ou Adobe Experience Platform ?
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 34b19024769f94c01c8655d80445fac836ec20f9
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 75%

---

# Conséquences de la suppression

Tenez compte des éléments suivants avant de supprimer des connexions, des jeux de données ou des lots dans Customer Journey Analytics ou Adobe Experience Platform :

| Lorsque vous... | Ceci se produit : |
| --- | --- |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Espace de travail qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul>Notez que vous ne pouvez pas supprimer les connexions de Customer Journey Analytics liées à des environnements de test Adobe Experience Platform pour lesquels vous ne disposez pas d’autorisations. Même si vous disposez d’autorisations pour les vues de données créées sur ces connexions, vous ne pouvez pas supprimer les connexions tant que vous ne disposez pas des autorisations nécessaires pour les environnements de test Adobe Experience Platform sous-jacents. |
| Suppression d’un jeu de données dans [!UICONTROL Adobe Experience Platform] | La suppression d’un jeu de données dans AEP interrompt le flux de données entre ce jeu et les connexions qui l’incluent. Toutes les données de ce jeu de données sont automatiquement supprimées des connexions Customer Journey Analytics associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] | Lorsque vous supprimez un jeu de données d’une connexion dans Customer Journey Analytics, les vues de données et les projets qui s’appuyaient sur ce jeu de données ne fonctionneront plus. |
| Supprime un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé d’un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toute connexion [!UICONTROL Customer Journey Analytics] contenant ce lot spécifique. [!UICONTROL Customer Journey Analytics] est averti des lots supprimés dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] | Sʼil n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot nʼapparaîtra dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Suppression de jeux de données de recherche dans [!UICONTROL Adobe Experience Platform] | Bien que la suppression de jeux de données soit possible pour dʼautres connecteurs source, elle nʼest actuellement pas prise en charge pour le [Connecteur source de classifications Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=fr). Si vous supprimez un jeu de données par erreur, contactez lʼassistance clientèle Adobe. |
