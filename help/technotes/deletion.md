---
title: Conséquences de la suppression
description: Comprenez l’implication de la suppression ou de la réinitialisation d’objets Customer Journey Analytics ou Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: c8b646b7e92663ed9c7e8454a336d25e34415cbe
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 11%

---

# Conséquences de la suppression et de la réinitialisation

La suppression ou la réinitialisation d’objets Customer Journey Analytics ou Experience Platform a des implications. Ces implications sont décrites dans cet article.

## Customer Journey Analytics

Tenez compte des implications suivantes avant de supprimer des connexions, des vues de données ou des jeux de données dans Customer Journey Analytics :

| Action | Implications |
| --- | --- |
| Supprime une connexion dans [!UICONTROL Customer Journey Analytics] | Un message d’erreur indique que :<ul><li>Les vues de données créées pour la connexion supprimée ne fonctionnent plus.</li><li> De même, tous les projets Workspace qui dépendent des vues de données dans la connexion supprimée cesseront de fonctionner.</li></ul>Notez que vous ne pouvez pas supprimer les connexions Customer Journey Analytics qui :<ul><li>Sont liés à des sandbox Adobe Experience Platform pour lesquels vous ne disposez pas d’autorisations. Même si vous disposez d’autorisations sur les vues de données créées sur ces connexions, vous ne pouvez pas supprimer les connexions tant que vous ne disposez pas des autorisations sur les sandbox Adobe Experience Platform sous-jacents.</li><li>Sélectionnez l’option de compatibilité suivante pour une vue de données associée à la connexion : **[!UICONTROL Définir comme vue de données par défaut dans Adobe Journey Optimizer]**<p>Pour plus d’informations sur cette option de configuration, voir [Compatibilité](/help/data-views/create-dataview.md#compatibility) dans [Créer ou modifier une vue de données](/help/data-views/create-dataview.md)</p></li></ul> |
| Supprimer un jeu de données dans [!UICONTROL Customer Journey Analytics] | Lorsque vous supprimez un jeu de données d’une connexion dans Customer Journey Analytics, les vues de données et les projets qui reposent sur ce jeu de données ne fonctionnent plus. |
| Supprime une vue de données dans [!UICONTROL Customer Journey Analytics] | Lorsque vous supprimez une vue de données dans Customer Journey Analytics, les panneaux d’un projet Workspace qui reposent sur cette vue de données ne fonctionnent plus correctement. |



## Experience Platform

Tenez compte des implications suivantes avant de supprimer des jeux de données ou des lots, ou lorsque vous réinitialisez ou supprimez des sandbox dans Experience Platform :

| Action | Implications |
| --- | --- |
| Supprimer un jeu de données dans [!UICONTROL Experience Platform] | Le flux de données de ce jeu de données dans Experience Platform s’arrête à toutes les connexions qui incluent ce jeu de données. Toutes les données de ce jeu de données sont automatiquement supprimées des connexions Customer Journey Analytics associées. |
| Supprimer un lot d’un jeu de données dans [!UICONTROL Experience Platform] | Si un lot est supprimé d’un jeu de données [!UICONTROL Adobe Experience Platform], le même lot est supprimé de toutes les connexions [!UICONTROL Customer Journey Analytics] qui contiennent ce lot spécifique. [!UICONTROL Customer Journey Analytics] est averti des lots supprimés dans [!UICONTROL Adobe Experience Platform]. |
| Supprimez un lot d’[!UICONTROL Experience Platform] **pendant son ingestion** dans [!UICONTROL Customer Journey Analytics] | Si le jeu de données ne contient qu’un seul lot, aucune des données ou données partielles de ce lot n’apparaît dans [!UICONTROL Customer Journey Analytics]. L’ingestion est restaurée. Si, par exemple, le jeu de données contient 5 lots et que 3 d’entre eux ont déjà été ingérés lors de la suppression du quatrième lot, les données de ces 3 lots apparaissent dans [!UICONTROL Customer Journey Analytics]. |
| Supprimer des jeux de données de recherche dans [!UICONTROL Experience Platform] | Bien que la suppression de jeux de données soit possible pour d’autres connecteurs source, la suppression de jeux de données [ Connecteur Source Analytics Classifications ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications) n’est pas prise en charge. Si vous supprimez un jeu de données par erreur, contactez l’assistance clientèle. |
| Suppression ou réinitialisation d’un sandbox dans Experience Platform | Lorsque vous [supprimez un sandbox Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox), tous les schémas, jeux de données, lots, politiques et autres éléments de ce sandbox sont également supprimés. Le sandbox n’existe plus, ainsi que l’identifiant et le nom du sandbox.<br/>Lorsque vous [réinitialisez un sandbox Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox), tous les schémas, jeux de données, lots, politiques et autres éléments de ce sandbox sont supprimés. Bien que le nom et les autorisations du sandbox restent inchangés, l’identifiant du sandbox est modifié une fois la réinitialisation terminée.<br/><br/>Customer Journey Analytics utilise l’identifiant et le nom du sandbox pour associer une connexion à un sandbox. Par conséquent : <ul><li>Les connexions associées au sandbox supprimé ou réinitialisé sont supprimées.</li><li>Les vues de données (et toutes les définitions de composant, telles que les champs dérivés, dans la vue de données) basées sur les connexions supprimées sont supprimées.</li><li>Les composants qui reposent sur les vues de données supprimées sont supprimés. Segments, mesures calculées, annotations, alertes, audiences publiées et exportations, par exemple.</li><li>Les panneaux dans les projets Workspace qui font référence aux vues de données supprimées deviennent inutilisables. Ces panneaux affichent les erreurs **[!UICONTROL Vue de données inconnue]**. Supprimez ces panneaux ou, si possible, associez-les à une vue de données existante.</li><li>Vous ne devriez plus interroger les données (historiques) de la connexion supprimée qui est déjà disponible dans Customer Journey Analytics à l’aide de Query Service ou des outils qui reposent sur l’extension BI. L’assistance ou l’ingénierie d’Adobe finit par supprimer ces données de Customer Journey Analytics.</li></ul>Comme les implications d’une réinitialisation ou d’une suppression d’un sandbox dans Experience Platform sont importantes, tenez compte des points suivants avant de réinitialiser ou de supprimer un sandbox :<ul><li>Répertoriez vos connexions pour savoir quelles connexions appartiennent à quels sandbox.</li><li>Répertoriez les vues de données pour comprendre quelles vues de données sont associées à quelles connexions.</li><li>Identifiez les projets Workspace importants et identifiez les vues de données auxquelles ces projets font référence dans leurs panneaux.</li><li>Identifiez les intégrations avec les outils qui utilisent l’extension BI et comprenez les vues de données sur lesquelles ces intégrations reposent.</li></ul> |
