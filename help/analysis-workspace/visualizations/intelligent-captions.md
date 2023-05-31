---
description: Utilisez des légendes intelligentes pour générer des informations en langage naturel afin de faire rapidement apparaître les tendances dans les visualisations.
title: Légendes intelligentes
feature: Visualizations
role: User, Admin
exl-id: 7e61ac12-a68e-4639-b021-f04762af4709
source-git-commit: 48648a29b92ff81b98a7efa8f6f1cb3f49d4bf81
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---

# Légendes intelligentes

Les sous-titres intelligents utilisent l’apprentissage automatique avancé et l’IA générique pour fournir des informations précieuses en langage naturel aux visualisations Workspace. La version initiale fournit des informations générées automatiquement pour la variable [Ligne](line.md) visualisation. (D’autres visualisations suivront.)

Les sous-titres intelligents sont conçus pour :

* Analystes qui ont besoin de récits à partager avec d’autres utilisateurs. Les analystes ont besoin de ces informations pour être en mesure de fournir un contexte à leurs utilisateurs.
* Utilisateurs professionnels qui souhaitent découvrir rapidement des offres à emporter de haut niveau.

Les sous-titres sont disponibles pour tous les utilisateurs de CJA et ne nécessitent pas d’autorisations spéciales.

## Lancement de sous-titres intelligents {#launch}

Pour lancer des sous-titres générés automatiquement pour une visualisation en ligne, cliquez sur le bouton **[!UICONTROL Légendes intelligentes]** en haut à droite de la visualisation.

![lancement de légendes intelligentes](assets/intell-caps-1.png)

Des informations sur le langage naturel sont maintenant générées.

* Des sous-titres sont générés chaque fois que les données sélectionnées sous-jacentes changent dans le tableau qui alimente la visualisation.

* S’il existe plusieurs mesures dans le tableau, les sous-titres ne sont générés que pour la première mesure ou la mesure actuellement sélectionnée par l’utilisateur.

* Si vous enregistrez le projet à ce stade et que vous le rechargez ultérieurement, les sous-titres sont automatiquement mis à jour avec de nouvelles données. Il en va de même pour les projets planifiés et les fichiers de PDF exportés à partir de ce projet.

## Affichage et interprétation des légendes {#view}

Voici un exemple de sous-titres :

![Sous-titres](assets/captions.png)

## Copier dans le presse-papiers {#copy}

Vous pouvez copier les sous-titres dans un presse-papiers et les coller dans un Powerpoint ou un autre outil. Recherchez le **[!UICONTROL Copie de sous-titres dans le Presse-papiers]** en haut à droite de la boîte de dialogue des sous-titres.

## Modifier les sous-titres {#edit}

Vous pouvez modifier les sous-titres, par exemple masquer ou afficher une catégorie spécifique d’informations. Par exemple, si vous ne souhaitez pas connaître l’ordre minimum, vous pouvez simplement le masquer et cliquer sur Appliquer pour qu’il ne s’affiche plus.

1. Cliquez sur **[!UICONTROL Modifier l’affichage des légendes intelligentes]** en regard de l’icône du Presse-papiers.

1. Dans la boîte de dialogue de modification, cliquez sur l’icône représentant un oeil en regard de l’aperçu que vous souhaitez masquer.

1. Cliquez sur **[!UICONTROL Appliquer]**.

Procédez de la même manière pour afficher les sous-titres.

## Exporter les sous-titres {#export}

Vous pouvez **exporter des sous-titres via PDF**, tant que le projet est enregistré avec les sous-titres générés.

## Désactivation des légendes {#toggle}

Si vous préférez ne pas générer de sous-titres intelligents, vous pouvez désactiver cette fonction en accédant aux préférences de visualisation et en décochant la case **[!UICONTROL Afficher les légendes intelligentes]**.

![paramètres de légende](assets/toggle-captions.png)
