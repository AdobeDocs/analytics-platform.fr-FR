---
description: Découvrez comment analyser les résultats des tests A/B dans le panneau d’expérimentation CJA.
title: Panneau d’expérience
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 69331f1ad3699c4a01d782fe11d4f2212c703190
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 7%

---

# Panneau d’expérience

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Le **[!UICONTROL Expérience]** permet aux analystes de comparer différentes variations d’expérience utilisateur, de marketing ou de messagerie afin de déterminer quelle est la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation (en ligne, hors ligne, à partir de solutions d’Adobe, de Adobe Journey Optimizer et même de données BYO (apportez-vous).

>[!IMPORTANT]
>
>À ce stade, [Adobe Analytics pour Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=fr) (A4T) données importées dans Adobe Experience Platform via le connecteur source Analytics **cannot** sont analysées dans la variable [!UICONTROL Expérience] du panneau. Nous attendons une résolution de ce problème en 2023.

## Contrôle d’accès

Le panneau Expérience est disponible pour tous les utilisateurs de Customer Journey Analytics (CJA). Aucun droit d’administrateur ou autre autorisation n’est requis. Toutefois, la configuration (étapes 1 et 2 ci-dessous) nécessite des actions que seuls les administrateurs peuvent effectuer.

## Étape 1 : Créer une connexion à un ou plusieurs jeux de données d’expérience

Le schéma de données recommandé est que les données de l’expérience se trouvent dans un tableau d’objets contenant les données de l’expérience et les données des variantes dans deux dimensions distinctes. Si vos données d’expérience se trouvent dans une seule dimension avec des données d’expérience et de variante dans une chaîne délimitée, vous pouvez utiliser la variable [substring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=en#) dans les vues de données pour les diviser en deux pour les utiliser dans le panneau.

Une fois que les données de l’expérience ont été [ingéré](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) dans Adobe Experience Platform, [créer une connexion dans CJA ;](/help/connections/create-connection.md) à un ou plusieurs jeux de données d’expérience.

## Étape 2 : Ajout d’étiquettes contextuelles dans les vues de données

Dans les paramètres des vues de données CJA, les administrateurs peuvent ajouter [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure et à des services CJA comme [!UICONTROL Expérience] peuvent utiliser ces libellés à des fins pratiques. Deux libellés prédéfinis sont utilisés pour le panneau Expérience :

* [!UICONTROL Expérience]
* [!UICONTROL Variante]

Dans votre vue de données contenant des données d’expérimentation, sélectionnez deux dimensions, l’une avec les données d’expérimentation et l’autre avec les données de variante. Puis étiquetez ces dimensions avec la variable **[!UICONTROL Expérience]** et le **[!UICONTROL Variante]** libellés.

![libellé du contexte](../assets/context-label.png)

Sans ces étiquettes, le panneau Expérience ne fonctionne pas, puisqu’il n’y aura aucune expérience à utiliser.

## Étape 3 : Configuration du panneau Expérience

1. Dans CJA Workspace, faites glisser le panneau Expérimentation dans un projet.

![test panel](../assets/experiment.png)

>[!IMPORTANT]
>Si la configuration nécessaire dans les vues de données CJA n’a pas été effectuée, vous recevrez un message à cet effet avant de pouvoir continuer.

1. Configurez les paramètres d’entrée du panneau.

   | Paramètre | Définition |
   | --- | --- |
   | **[!UICONTROL Expérience]** | Ensemble de variations d’une expérience qui ont été exposées aux utilisateurs finaux afin de déterminer la meilleure expérience à conserver perpétuellement. Une expérience est composée de deux variantes ou plus, dont l’une est considérée comme la variante témoin. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec la variable  **[!UICONTROL Expérience]** libellé dans les vues de données et l’équivalent de 3 mois de données d’expérience. |
   | **[!UICONTROL Variante de contrôle]** | L’une des deux modifications ou plus de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. Une variante doit être sélectionnée comme contrôle, et une seule variante peut être considérée comme la variante de contrôle. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec la variable  **[!UICONTROL Variante]** dans les vues de données. Ce paramètre récupère les données de variante associées à cette expérience. |
   | **[!UICONTROL Mesures de succès]** | Mesure ou mesure avec laquelle un utilisateur compare des variantes. La variante ayant le résultat le plus souhaitable pour la mesure de conversion (la plus élevée ou la plus faible) est déclarée &quot;variante la plus performante&quot; d’une expérience. Vous pouvez ajouter jusqu’à 5 mesures. |
   | **[!UICONTROL Mesure de normalisation]** | La base ([!UICONTROL Personnes], [!UICONTROL Sessions]ou [!UICONTROL Événements]) sur laquelle un test sera exécuté. Par exemple, un test peut comparer les taux de conversion de plusieurs variantes où **[!UICONTROL Taux de conversion]** est calculé comme **[!UICONTROL Conversions par session]** ou **[!UICONTROL Conversions par personne]**. |
   | **[!UICONTROL Période]** | La période est automatiquement définie en fonction du premier accès reçu dans CJA pour l’expérience sélectionnée. Vous pouvez le modifier afin de limiter ou d’étendre la période à une période plus spécifique si nécessaire. |

1. Cliquez sur **[!UICONTROL Créer]**.

## Étape 4 : Interprétation de la sortie du panneau

Le panneau Expérience renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de vos expériences. Un filtre global est ajouté pour tenir compte des personnes ou des sessions exposées à plusieurs variations. Ce filtre ne peut pas être modifié ni supprimé. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés. Vous pouvez à tout moment modifier le panneau en cliquant sur le crayon de modification en haut à droite.

Vous obtenez également un résumé textuel qui indique si l’expérience est concluante ou non et résume le résultat. La conclusion repose sur la signification statistique. (Voir la &quot;méthodologie statistique&quot; ci-dessous.) La variante la plus performante n’est fournie que pour une expérience concluante et sélectionnée en fonction du taux de conversion des variantes significatives. Vous pouvez afficher des nombres de synthèse pour la variante la plus performante avec l’effet élévateur et le degré de confiance les plus élevés.

Les nombres de synthèse et de synthèse de texte ne sont générés que pour la première mesure de succès sélectionnée dans l’entrée du panneau.

>[!NOTE]
>
>L’effet élévateur et le degré de confiance sont également des fonctions de mesures calculées avancées dans CJA, ce qui vous permet de créer vos propres mesures d’effet élévateur et de confiance.

![sortie d’expérience](../assets/exp-output1.png)

Pour chaque mesure de succès sélectionnée, un tableau à structure libre et une tendance de taux de conversion sont affichés :

![sortie d’expérience](../assets/exp-output2.png)

Le [!UICONTROL Ligne] Le graphique vous donne la variable [!UICONTROL Contrôle] versus [!UICONTROL Variante de contrôle] performance :

![sortie d’expérience](../assets/exp-output3.png)
>[!NOTE]
>
>Ce panneau ne prend actuellement pas en charge l’analyse des tests A/A.

## Méthodologie statistique

A suivre.
