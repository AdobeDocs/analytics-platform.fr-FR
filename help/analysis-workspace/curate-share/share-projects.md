---
description: Partage de projets et rôles de projets dans Workspace
keywords: Analysis Workspace sharing
title: Projets Share Workspace
translation-type: tm+mt
source-git-commit: 3a2cb7ad15f1491ef4fe6fdcb3135b29675c40e8
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 5%

---


# Projets Share Workspace

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Le partage met un projet à la disposition d’autres utilisateurs Analysis Workspace de votre entreprise. Les [traitements](curate.md) appliqués sont répercutés lorsque les destinataires ouvrent le projet.

## Rôles de projet {#Roles}

Vous pouvez ajouter des destinataires à l’un des trois rôles de projet. Les rôles de projet sont liés à l’utilisateur et à un ID de projet spécifique. Les rôles de projet sont indépendants des autorisations d’utilisateur gérées dans la console [d’administration](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/admin-getting-started.html)Adobe Experience Cloud.

| Rôle | Contrôle du projet |
|---|---|
| Peut modifier | Recipients can **[!UICONTROL Save]** changes to a project and function as co-owners. Ce rôle est utile si vous souhaitez cogérer un projet avec d&#39;autres collègues ; cela inclut la modification, la suppression et la modification des listes de destinataire pour un projet partagé. <br>Remarque : L’Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. Il est donc recommandé qu’un seul utilisateur modifie un projet à la fois. Si les projets sont enregistrés en même temps, la dernière version est conservée. |
| Peut dupliquer | Les Destinataires peuvent **[!UICONTROL enregistrer sous]** et avoir accès au rail de gauche. Les interactions de projet ne sont pas limitées dans ce rôle. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui comprennent les données de votre entreprise et comment utiliser l’Analysis Workspace, mais que vous ne souhaitez pas que votre projet soit modifié. |
| Peut afficher | Les Destinataires ne peuvent pas enregistrer sous et n’ont pas accès au rail de gauche. Les interactions avec les projets sont également limitées. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui connaissent moins bien la structure de données de votre entreprise, Analysis Workspace ou Adobe Analytics en général. Cependant, vous souhaitez toujours qu’ils consomment des données et des informations dans un environnement sûr.<br>En savoir plus sur l’expérience [du projet](/help/analysis-workspace/curate-share/view-only-projects.md)Can vue. |

>[!IMPORTANT]
> Les destinataires de projet ajoutés avant le 18 juin 2020 ont été migrés dans un rôle de projet. Les utilisateurs administrateurs ont effectué la migration vers le rôle **[!UICONTROL Can edit]** et les utilisateurs non administrateurs ont effectué la migration vers le rôle de duplicata **** Can. Ces rôles offrent la même expérience de projet qu&#39;auparavant. En outre, tous les groupes (y compris &quot;Tous&quot;) ont migré vers le rôle duplicata **** Can.

### Aucun rôle n&#39;est affecté (destinataires de lien de projet)

Si un destinataire n’est pas affecté à un rôle et reçoit un lien vers le projet (**[!UICONTROL Partager]>[!UICONTROL Obtenir le lien]** du projet), il sera placé dans un rôle par défaut. Les administrateurs reçoivent **[!UICONTROL Can edit]** et les non-administrateurs reçoivent **[!UICONTROL Can duplicata]**.

### Plusieurs rôles attribués

Si un destinataire est placé dans plusieurs rôles, il obtient toujours l’expérience la plus élevée. Cela peut se produire si un destinataire est ajouté à la fois en tant qu’individu et dans le cadre d’un groupe. Par exemple, si un destinataire reçoit le rôle **[!UICONTROL Peut modifier]** en tant qu’individu et le rôle vue **** Can en tant que membre d’un groupe, il reçoit un contenu **[!UICONTROL Peut modifier]** le projet.

### Administrateurs et rôles

Les administrateurs placés dans un duplicata **** Can ou une vue **** Can recevront ces expériences limitées lorsqu’ils ouvriront un projet. Si vous le souhaitez, un administrateur peut augmenter son rôle pour **[!UICONTROL pouvoir modifier]** à tout moment via **[!UICONTROL Composants]>[!UICONTROL Projets]**.

## Ajouter les destinataires au projet partagé {#Add}

Pour ajouter des destinataires à votre projet partagé :

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**.
S&#39;il y a des modifications non enregistrées, vous serez invité à enregistrer d&#39;abord votre projet.
1. Ajoutez des destinataires ou des groupes de destinataires.
Pour obtenir la description de chaque rôle, reportez-vous à l’icône d’aide en haut de l’écran.
1. (Facultatif) Partagez des composants de projet incorporés (segments, mesures calculées et plages de dates) avec tous les destinataires.
Une fois partagés, ces composants s’affichent dans la liste déroulante Composants de l’espace de travail du destinataire. Notez que ce paramètre n’est pas conservé. Il s’agit d’une action unique au moment du partage.
1. (Facultatif) Définissez cette page comme landing page pour les destinataires.
Ce paramètre est ponctuel ; c’est une action unique au moment du partage.
1. Cliquez sur Partager.
Vous pouvez également cliquer sur **[!UICONTROL Traiter et Partager]** pour appliquer automatiquement la gestion du projet. Si un projet a déjà été partagé, ces boutons indiqueront **[!UICONTROL Mettre à jour]** et **[!UICONTROL Traiter et mettre à jour]**. En savoir plus sur la gestion [des](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-workspace/curate-share/curate.html)projets.

![](assets/share-proj-modal.png)

## Partager sur des groupes de destinataires {#Groups}

Tous les utilisateurs peuvent partager des projets dans des groupes, qui sont un ensemble de destinataires. Dans Adobe Analytics, les groupes sont définis par profils de produits dans la console [d’administration](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/admin-getting-started.html)Adobe Experience Cloud.

* Les administrateurs peuvent partager des données avec n’importe quel groupe, y compris &quot;Tous&quot;.
* Les non-administrateurs peuvent partager avec des groupes dont ils sont membres, à l’exception de &quot;Tous&quot;.

## Share a project link {#Links}

Vous pouvez obtenir un lien vers un projet sous **[!UICONTROL Partager]>[!UICONTROL Obtenir le lien]** du projet. Lorsque vous cliquez dessus, les destinataires doivent se connecter avant d’accéder au projet. Si le destinataire n’a pas été placé dans un rôle, il recevra un rôle par défaut. Les administrateurs reçoivent **[!UICONTROL Can edit]** et les non-administrateurs reçoivent **[!UICONTROL Can duplicata]**.

## Partage de projets dans le gestionnaire de projets {#Manager}

Les projets peuvent également être partagés à partir de **[!UICONTROL Composants]>[!UICONTROL Projets]**. Un seul projet peut être partagé en suivant les mêmes étapes que celles décrites ci-dessus.  Si plusieurs projets sont sélectionnés pour être partagés, des destinataires seront ajoutés à la liste existante de destinataires pour chaque projet.

Par exemple :

* Le projet A est partagé aux destinataires 1, 2, 3
* Le projet B est partagé aux destinataires 4, 5, 6

Si les projets A et B sont sélectionnés, les destinataires 4 et 7 sont ajoutés aux listes de partage. La nouvelle liste de partage pour chaque projet est désormais la suivante :

* Projet A : 1, 2, 3, 4, 7
* Projet B : 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Questions fréquentes {#FAQs}

| Question | Réponse |
|---|---|
| Que se passe-t-il si deux éditeurs enregistrent un projet en même temps ? | Les modifications ne sont pas fusionnées et la dernière version enregistrée du projet sera conservée. Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. |
| En tant qu’administrateur, quelle expérience de projet vais-je voir ? | Les administrateurs placés dans un duplicata **** Can ou une vue **** Can recevront ces expériences limitées lorsqu’ils ouvriront un projet. Si vous le souhaitez, un administrateur peut augmenter son rôle pour **[!UICONTROL pouvoir modifier]** à tout moment via **[!UICONTROL Composants]>[!UICONTROL Projets]**. |
| Que se passe-t-il si un destinataire est placé dans un rôle en tant qu&#39;individu et un autre rôle en tant que membre d&#39;un groupe ? | Si un destinataire est placé dans plusieurs rôles, il recevra toujours l’expérience la plus élevée. Par exemple, si un destinataire reçoit le rôle **[!UICONTROL Peut modifier]** en tant qu’individu et le rôle vue **** Can en tant que membre d’un groupe, il reçoit un contenu **[!UICONTROL Peut modifier]** le projet. |
| Quelle expérience obtient un destinataire s’il ouvre un lien de projet ? | Les Destinataires reçoivent le rôle que vous leur avez attribué dans le module de partage. Si un destinataire n’est pas affecté à un rôle et reçoit un lien vers le projet (**[!UICONTROL Partager]>[!UICONTROL Obtenir le lien]** du projet), il sera placé dans un rôle par défaut. Les administrateurs reçoivent **[!UICONTROL Can edit]** et les non-administrateurs reçoivent **[!UICONTROL Can duplicata]**. |
