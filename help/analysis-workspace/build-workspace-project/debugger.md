---
description: Découvrez comment utiliser le débogueur pour résoudre les problèmes liés à votre projet dans Analysis Workspace.
keywords: Analysis Workspace
feature: Workspace Basics
title: Débogueur de projet
role: User
source-git-commit: 4d902bab01c1c795cb7d852066128f6b9db0823a
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 3%

---

# Débogueur de projet

Le débogueur de projet vous aide, ainsi que le support Adobe, à résoudre les problèmes liés à vos projets dans Analysis Workspace. L’assistance Adobe peut vous demander d’activer le débogueur pour résoudre les problèmes liés aux tickets que vous avez signalés à l’assistance Adobe. Le temps de chargement des visualisations ou les composants rompus dans vos visualisations sont des exemples de problèmes.

>[!NOTE]
>
>Pour utiliser le débogueur, vous devez avoir un accès **Modifier** ou **Copier** [ au projet](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-25744).
>


## Activer le débogueur

>[!IMPORTANT]
>
>Enregistrez votre projet avant d’activer le débogueur.
>

Pour activer le débogueur :

1. Sélectionnez **[!UICONTROL Aide]** > **[!UICONTROL Activer le débogueur]** dans le menu du projet Analysis Workspace.
1. Sélectionnez **[!UICONTROL OK]** dans la boîte de dialogue **[!UICONTROL Activer Debugger]**.
1. Confirmez lorsque le navigateur vous invite à recharger la page ou le site.


## Utiliser le débogueur

Lorsque vous avez activé le débogueur, toutes les visualisations de votre projet comportent une icône ![Bug](/help/assets/icons/Bug.svg) supplémentaire.

Pour utiliser le débogueur pour une visualisation spécifique :

1. Sélectionnez ![Bogue](/help/assets/icons/Bug.svg) en haut de la visualisation.

   ![Menu contextuel du débogueur](assets/debugger-context-menu.png)

1. Sélectionnez l’action appropriée dans le menu contextuel. Les actions disponibles dépendent de la visualisation et indiquent le type de débogage que vous souhaitez effectuer. Par exemple, si vous sélectionnez **[!UICONTROL Anomalies]**, vous pouvez déboguer la fonctionnalité d’anomalies dans la visualisation.
1. Dans le sous-menu, sélectionnez une date et heure.
1. Une fenêtre de débogage **[!UICONTROL Oberon XML]** s’ouvre avec des détails sur les fonctionnalités spécifiques exécutées par la visualisation. Consultez ci-dessous un exemple de sortie d’une requête d’anomalie.

   ![Requête de débogage Output](assets/debugger-oberon.png)

   Les détails sont les suivants :

   * **[!UICONTROL Date et heure de la demande]**
   * **[!UICONTROL Date et heure de la réponse]**
   * **[!UICONTROL Heure de la requête]**
   * **[!UICONTROL Durée de la file]**
   * **[!UICONTROL Temps de traitement serveur]**
   * **[!UICONTROL Heure de recherche]**
   * **[!UICONTROL Complexité]**
   * **[!UICONTROL Limites mensuelles]**
   * **[!UICONTROL Colonnes]**
   * **[!UICONTROL Segments]**
   * **[!UICONTROL XML]** **[!UICONTROL Requête]** et **[!UICONTROL Réponse]**
   * **[!UICONTROL demande cURL]**
   * **[!UICONTROL JSON]** **[!UICONTROL Requête]** et **[!UICONTROL Réponse]**

1. Utilisez ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier tout le champ dans le presse-papiers]** pour copier toutes les informations de débogage dans le presse-papiers. Collez les informations dans l’éditeur ou l’outil de votre choix. Les informations comprennent :

   * XML (requête)
   * XML (réponse)
   * JSON (requête)
   * JSON (réponse)
   * Requête cURL

1. ** Utilisez ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier dans le presse-papiers]d sous **[!UICONTROL Requête cURL]** pour copier la requête dans le presse-papiers.
1. Pointez sur l’une des zones de texte **[!UICONTROL Requête]** ou **[!UICONTROL Réponse]** pour afficher et sélectionnez ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier dans le presse-papiers]** pour copier le contenu de cette zone de texte (XML ou JSON) dans le presse-papiers.

1. Échangez toutes les informations que vous avez copiées et que l’assistance Adobe a demandées pour résoudre les problèmes liés aux visualisations dans votre projet Analysis Workspace.

1. Sélectionnez **[!UICONTROL Annuler]** pour fermer la fenêtre de débogage **[!UICONTROL Oberon XML]** et revenir à votre projet.

Répétez les étapes ci-dessus pour toute autre visualisation dont vous souhaitez résoudre les problèmes.

## Désactiver le débogueur

>[!IMPORTANT]
>
>Avant de désactiver le débogueur, enregistrez les modifications apportées à votre projet et que vous souhaitez conserver dans le cadre de l’exercice de débogage.
>

Pour désactiver le débogueur :

1. Sélectionnez **[!UICONTROL Aide]** > **[!UICONTROL Désactiver le débogueur]** dans le menu du projet Analysis Workspace.
1. Sélectionnez **[!UICONTROL OK]** dans la boîte de dialogue **[!UICONTROL Désactiver le débogueur]**.
1. Confirmez lorsque le navigateur vous invite à recharger la page ou le site.



