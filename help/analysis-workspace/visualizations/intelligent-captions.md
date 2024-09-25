---
description: Utilisez des légendes intelligentes pour générer des informations en langage naturel afin d’afficher rapidement les tendances dans les visualisations.
title: Légendes intelligentes
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: dae2282717d5d84862259d5b056fbfeb2d068cce
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 4%

---

# Légendes intelligentes

Les sous-titres intelligents utilisent le machine learning avancé et l’IA générative pour fournir des informations précieuses en langage naturel aux visualisations Workspace. La version initiale fournit des informations générées automatiquement pour la visualisation [Line](line.md). D’autres visualisations suivront.

Les sous-titres intelligents sont conçus pour :

* Analystes qui ont besoin de récits à partager avec d’autres utilisateurs. Les analystes ont besoin de ces informations pour être en mesure de fournir un contexte à leurs utilisateurs.
* Utilisateurs professionnels qui souhaitent découvrir rapidement des offres de haut niveau.

Les sous-titres sont disponibles pour tous les utilisateurs de Customer Journey Analytics et ne nécessitent pas d’autorisations spéciales.

## Lancement de sous-titres intelligents {#launch}

Pour lancer des sous-titres générés automatiquement pour une visualisation en ligne, cliquez sur l’icône **[!UICONTROL Sous-titres intelligents]** en haut à droite de la visualisation.

![Fenêtre d’analyse de lancement présentant les légendes intelligentes de la tendance des vues de produits. ](assets/intell-caps-1.png)

Des informations sur le langage naturel sont maintenant générées.

Gardez à l’esprit que :

* Vous avez besoin d’un minimum de 3 points de données pour générer les légendes avec succès. Dans le cas contraire, une erreur &quot;Pas assez de données à analyser&quot; peut s’afficher.

* Des sous-titres sont générés chaque fois que les données sélectionnées sous-jacentes changent dans le tableau qui alimente la visualisation.

* S’il existe plusieurs mesures dans le tableau, les sous-titres ne sont générés que pour la première mesure ou la mesure actuellement sélectionnée par l’utilisateur.

* Si vous enregistrez le projet à ce stade et que vous le rechargez ultérieurement, les sous-titres sont automatiquement mis à jour avec de nouvelles données. Il en va de même pour les projets planifiés et les fichiers de PDF exportés à partir de ce projet.

## Affichage et interprétation des légendes {#view}

Voici un exemple de sous-titres :

![ Sous-titres intelligents pour la visualisation en ligne, y compris le caractère saisonnier, le nombre minimum, le nombre maximal, le pic et le déclin.](assets/captions.png)

## Copier dans le presse-papiers {#copy}

Vous pouvez copier les sous-titres dans un presse-papiers et les coller dans un PowerPoint ou d’autres outils. Sélectionnez ![Copier les sous-titres dans le Presse-papiers](/help/assets/icons/Copy.svg) en haut à droite de la boîte de dialogue des sous-titres.

## Modifier les sous-titres {#edit}

Vous pouvez modifier les sous-titres, par exemple masquer ou afficher une catégorie spécifique d’informations. Par exemple, si vous ne souhaitez pas obtenir d’informations sur l’ordre minimal, vous pouvez simplement masquer cette information et cliquer sur Appliquer. et il ne s’affichera plus.

1. Sélectionnez ![Modifier l’affichage des sous-titres intelligents](/help/assets/icons/EditInLight.svg) dans la boîte de dialogue Intelligent captions.

1. Basculez entre ![Visibility](/help/assets/icons/Visibility.svg) pour afficher un aperçu spécifique (comme **[!UICONTROL Min]**) ou ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) pour masquer un aperçu spécifique (comme **[!UICONTROL Spike]**).

   ![Modifier des sous-titres intelligents](assets/edit-intelligent-captions.png)

1. Sélectionnez **[!UICONTROL Appliquer]**.


## Fournir des commentaires

Vous pouvez fournir des commentaires sur les sous-titres intelligents générés.

1. Sélectionnez ![Autres actions](/help/assets/icons/More.svg) dans la boîte de dialogue Intelligent captions.

1. Sélectionnez ![Bonne réponse](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Bonne réponse]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Mauvaise réponse]** ou ![Indicateur](/help/assets/icons/Flag.svg) **[!UICONTROL Rapport]**.

1. Dans la boîte de dialogue **[!UICONTROL Merci pour vos commentaires]**, fournissez vos commentaires et sélectionnez **[!UICONTROL Envoyer]** pour envoyer vos commentaires.

## Exporter les sous-titres {#export}

Vous pouvez **exporter des sous-titres via PDF** tant que le projet est enregistré avec les sous-titres générés.

## Désactivation des légendes {#toggle}

Si vous préférez ne pas afficher de sous-titres intelligents, vous pouvez désactiver cette fonction.

1. Accédez à [Préférences de visualisation](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Décochez la case **[!UICONTROL Afficher les sous-titres intelligents]**.

   ![Options de visualisation en ligne présentant l’option permettant de décocher Afficher les sous-titres intelligents.](assets/toggle-captions.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la préférence.





## Sous-titres intelligents dans les Fiches d’évaluation mobiles

Des sous-titres intelligents sont également disponibles dans le Customer Journey Analytics [Fiches d’évaluation mobiles](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).

## Accès aux fonctionnalités

Les paramètres suivants régissent l’accès aux sous-titres intelligents :

* **Accès aux solutions** : la fonctionnalité de sous-titres intelligents est disponible en Customer Journey Analytics, mais pas dans Adobe Analytics.

* **Accès contractuel** : si vous ne pouvez pas utiliser de sous-titres intelligents, contactez l’administrateur ou le représentant du compte d’Adobe de votre entreprise. Avant de pouvoir utiliser Intelligent dans votre entreprise, vous devez accepter certaines dispositions légales relatives à GenAI.

* **Autorisations** : dans le [!UICONTROL Adobe Admin Console], l’autorisation [!UICONTROL Outils de création de rapports] **[!UICONTROL Sous-titres intelligents]** détermine l’accès. Un [ administrateur de profil de produit ](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes dans l’ [!UICONTROL Admin Console] :
   1. Accédez à **[!UICONTROL Admin Console]** > **[!UICONTROL Produits et services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Profils de produit]**.
   1. Sélectionnez le titre du profil de produit pour lequel vous souhaitez donner accès aux sous-titres intelligents.
   1. Dans le profil de produit spécifique, sélectionnez **[!UICONTROL Autorisations]**.
   1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier les **[!UICONTROL outils de création de rapports]**.
   1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) pour ajouter **Intelligent Captions** aux **[!UICONTROL éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](./assets/intelligent-captions-permissions.png)

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

Voir [Contrôle d’accès](/help/technotes/access-control.md#access-control) pour plus d’informations.