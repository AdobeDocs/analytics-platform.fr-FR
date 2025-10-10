---
title: Conséquences de la suppression
description: Que se passe-t-il lorsque vous supprimez des connexions, des jeux de données ou des lots dans Customer Journey Analytics ou Adobe Experience Platform ?
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 928c79f9ccf30cc33e0f334f715bf3190a257019
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 64%

---

# Conséquences de la suppression

Tenez compte des éléments suivants avant de supprimer des connexions, des jeux de données ou des lots dans Customer Journey Analytics ou Adobe Experience Platform :

| Lorsque vous... | Ceci se produit : |
| --- | --- |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionneront plus.</li><li> De même, les projets Espace de travail qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul>Notez que vous ne pouvez pas supprimer les connexions Customer Journey Analytics qui : <ul><li>Sont liés à des sandbox Adobe Experience Platform pour lesquels vous ne disposez pas d’autorisations. Même si vous disposez d’autorisations sur les vues de données créées sur ces connexions, vous ne pouvez pas supprimer les connexions tant que vous ne disposez pas des autorisations sur les sandbox Adobe Experience Platform sous-jacents.</li><li>Sélectionnez l’option de compatibilité suivante pour une vue de données associée à la connexion : **[!UICONTROL Définir comme vue de données par défaut dans Adobe Journey Optimizer]**<p>Pour plus d’informations sur cette option de configuration, voir [Compatibilité](/help/data-views/create-dataview.md#compatibility) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md)</p></li></ul> |
| Supprimer un jeu de données dans [!UICONTROL Adobe Experience Platform] | La suppression d’un jeu de données dans AEP interrompt le flux de données entre ce jeu et les connexions qui l’incluent. Toutes les données de ce jeu de données sont automatiquement supprimées des connexions Customer Journey Analytics associées. |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] | Lorsque vous supprimez un jeu de données d’une connexion dans Customer Journey Analytics, les vues de données et les projets qui en dépendaient ne fonctionnent plus. |
| Supprime un lot dʼun jeu de données (dans [!UICONTROL Adobe Experience Platform]) | Si un lot est supprimé d’un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toute connexion [!UICONTROL Customer Journey Analytics] contenant ce lot spécifique. [!UICONTROL Customer Journey Analytics] est averti des lots supprimés dans [!UICONTROL Adobe Experience Platform]. |
| Supprime un lot **lorsqu’il est ingéré** dans [!UICONTROL Customer Journey Analytics] | Sʼil n’y a qu’un seul lot dans le jeu de données, aucune donnée ou donnée partielle de ce lot nʼapparaîtra dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 dʼentre eux ont déjà été ingérés lors de la suppression du jeu de données, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprimer des jeux de données de recherche dans [!UICONTROL Adobe Experience Platform] | Bien que la suppression de jeux de données soit possible pour dʼautres connecteurs source, elle nʼest actuellement pas prise en charge pour le [Connecteur source de classifications Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=fr). Si vous supprimez un jeu de données par erreur, contactez lʼassistance clientèle Adobe. |
