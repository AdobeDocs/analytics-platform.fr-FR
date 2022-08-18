---
description: Découvrez comment analyser les résultats des tests A/B dans le panneau d’expérimentation CJA.
title: Panneau d’expérience
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# Panneau d’expérience

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Le **[!UICONTROL Expérience]** vous permet de comparer différentes variations d’expérience utilisateur, de marketing ou de messagerie afin de déterminer quelle est la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation (en ligne, hors ligne, à partir de solutions d’Adobe, de Adobe Journey Optimizer et même de données BYO (apportez-vous).

>[!IMPORTANT]
>
>À ce stade, [Adobe Analytics pour Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=fr) (A4T) les données ne peuvent pas être évaluées dans la variable [!UICONTROL Expérience] du panneau.

## Contrôle d’accès

Le panneau Expérience est disponible pour tous les utilisateurs de Customer Journey Analytics (CJA). Aucun droit d’administrateur ou autre autorisation n’est requis. Toutefois, la configuration nécessite des étiquettes dans les vues de données que seuls les administrateurs peuvent attribuer.

## Terminologie

* **Expérience**: Une expérience est un ensemble de variations d’une expérience qui a été exposée aux utilisateurs finaux afin de déterminer la meilleure expérience à conserver perpétuellement. Une expérience est composée de plusieurs variations, dont l’une est considérée comme la variation témoin.

* **Variation**: L’une des deux modifications ou plus de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. Une variation doit être sélectionnée comme contrôle et une seule variation peut être considérée comme étant la variation de contrôle.

* **Contrôle**: Variation spécifique qui représente le statu quo, ou l’état par défaut de l’expérience d’un utilisateur. À quoi sont comparées toutes les autres variations.

* **Mesure de normalisation**: Base (sessions ou personnes) sur laquelle un test sera exécuté. Par exemple, un test peut comparer les taux de conversion de plusieurs variations où le taux de conversion est calculé sous la forme de conversions par session ou de conversions par personne.

* **Mesure de conversion**: Mesure avec laquelle un utilisateur compare des variations. La variation avec le résultat le plus souhaitable pour la mesure de conversion (le plus élevé ou le plus faible) est déclarée &quot;gagnante&quot; d’une expérience.

## Étape 1 : Créer une connexion à un ou plusieurs jeux de données d’expérience

Une fois que les données de l’expérience ont été [ingéré](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) dans Adobe Experience Platform, [créer une connexion dans CJA ;](/help/connections/create-connection.md) à un ou plusieurs jeux de données d’expérience.

## Étape 2 : Ajout d’étiquettes contextuelles dans les vues de données

Dans les paramètres des vues de données CJA, les administrateurs peuvent ajouter [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure et à des services CJA comme [!UICONTROL Expérience] peuvent utiliser ces libellés à des fins pratiques. Deux libellés prédéfinis sont utilisés pour le panneau Expérience :

* [!UICONTROL Expérience]
* [!UICONTROL Variante]

Dans votre vue de données contenant des données d’expérimentation, sélectionnez deux dimensions, l’une avec les données d’expérimentation et l’autre avec les données de variante. Puis étiquetez ces dimensions avec la variable **[!UICONTROL Expérience]** et le **[!UICONTROL Variante]** libellés.

![libellé du contexte](assets/context-label.png)

Sans ces libellés, le panneau Expérience ne fonctionne pas.

## Étape 3 : Configuration du panneau Expérience

1. Dans CJA Workspace, faites glisser le panneau Expérimentation dans un projet.

![test panel](assets/experiment.png)




