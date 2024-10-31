---
description: Comment poser des questions relatives à l’analyse des données dans la documentation du Customer Journey Analytics
title: Assistant d’IA dans l’analyse des données en Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 1442aa9be5e6a6dc283ba559a2ff6c46de862425
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 3%

---


# Assistant d’analyse des données IA en Customer Journey Analytics - Alpha

L’assistant d’analyse des données est un agent de conversation intelligent et contextuel qui peut vous aider à répondre plus rapidement et plus efficacement aux questions que vous pouvez vous poser sur vos données Analysis Workspace en Customer Journey Analytics.

L’assistant examine toutes les données d’une vue de données, y compris les différents types de mesures et de composants, et convertit votre invite en la bonne dimension, mesure et période pour cette analyse. Au lieu de devoir vous familiariser avec les composants de vue de données, puis les faire glisser et les déposer dans la meilleure combinaison pour répondre à votre question, vous pouvez simplement saisir la question dans l’assistant d’IA.

## Fonctionnalités intégrées ou hors plage pour la version Alpha

Fonctionnalités intégrées :

| Fonctionnalité prise en charge | Description |
| --- | --- |
| Créer et mettre à jour des visualisations | Génère un tableau à structure libre et la visualisation associée (par ex. ligne, barre, anneau, etc.).<p>Exemple : *Quel est le bénéfice entre les SKU de février à mai ?* |
| Types de visualisation pris en charge | Visualisations Ligne, Multiligne, Structure libre, Barre, Anneau, Synthèse des chiffres |
| Détection d’invite hors portée | Si vous envoyez une invite qui n’est pas exhaustive (par exemple, &quot;Exportez ce projet&quot;), l’assistant répond en vous informant que la question est hors de portée. |
| Clarification des questions | Si vous posez une question dont le contexte n’est pas suffisant pour que l’assistant d’IA puisse répondre, ou si elle est trop générique, l’assistant d’IA répond par une question précise et/ou par des options suggérées. Exemples : <p>**Composants**<ul><li>Mesure : *Quelle mesure &quot;recettes&quot; voulez-vous dire ?*</li><li>Dimension : *Sur quelles &quot;régions&quot; souhaitez-vous vous concentrer ?*</li><li>Filtre : *Quel filtre &quot;Compte&quot; souhaitez-vous appliquer ?*</li><li>Plage de dates : *Par &quot;dernier mois&quot;, avez-vous parlé du dernier mois complet ou des 30 derniers jours ?*</li></ul>**Éléments de Dimension** : quel &quot;nom de magasin&quot; voulez-vous dire ? (par exemple, #5274 de magasin, #2949 de magasin, etc.) |
| Multi-tour | L’assistant d’IA répond à une invite avec le contexte de la ou des invite(s) précédente(s), ce qui permet aux utilisateurs de mettre à jour les visualisations et de poser des questions de suivi. Exemple : *Afficher les données de mars à avril à la place.* |
| Commentaires | <ul><li>Pouces vers le haut</li><li>Menu déroulant</li><li>Indicateur</li></ul> |

Fonctionnalités hors plage :

| Fonctionnalité non prise en charge | Description |
| --- | --- |
| Résumé en ligne ou réponse | L’assistant d’IA ne peut pas répondre en ligne dans le rail de conversation avec une réponse rapide de l’utilisateur. Exemples d’invites hors plage :<ul><li>*Donne-moi un résumé des insights de ma dernière invite.*</li><li>*Résumer les surbrillances à partir de la visualisation en ligne.*</li></ul> |
| Clarification des questions | Les questions clarifiantes sont limitées aux composants et aux éléments de dimension. L’assistant AI ne peut pas clarifier les vues de données, les visualisations, la granularité des données, la comparaison, la portée, etc. Sans clarifier les questions, l’assistant propose par défaut ce que l’utilisateur est le plus susceptible de demander. S’il renvoie une visualisation ou une granularité de données inattendue, l’utilisateur peut alors utiliser la fonctionnalité de multi-tour/mise à jour pour ajuster la visualisation et les données. |
| Actions/fonctionnalités Workspace | L’assistant d’IA ne peut pas exécuter d’actions pour un utilisateur dans Workspace en plus de créer et de mettre à jour des visualisations. Par exemple, il ne peut pas effectuer les opérations suivantes :<ul><li>Boutons de l’interface utilisateur de l’action contextuelle (ajout au graphique, nouveau panneau, nouveau tableau)</li><li>Partager</li><li>Exporter</li><li>Télécharger</li><li>Gestion des préférences utilisateur</li><li>Traiter</li><li>Gérer la vue des données</li><li>Application de tableaux de bord Analytics</li><li>Attribution</li></ul> |
| Types de visualisation non pris en charge | <ul><li>Flux</li><li>Abandon</li><li>Tableau de cohortes</li><li>Surface, Aires empilées</li><li>Barres empilées</li><li>Puce</li><li>Combo</li><li>Histogramme</li><li>Barre horizontale, Barre empilée horizontale</li><li>Résumé des mesures clés</li><li>Nuage de points</li><li>Synthèse des modifications</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| Explication et vérification | Description ou citation transparente de la manière dont l’assistant d’IA a généré une réponse et vous permettant de confirmer que la réponse est correcte. |

## Accès aux fonctionnalités dans l’interface utilisateur du Customer Journey Analytics

[Avons-nous même besoin de cette section pour l&#39;Alpha ?]

Les paramètres suivants régissent l’accès à la fonctionnalité de l’assistant d’analyse des données :

* **Accès aux solutions** : l’assistant d’analyse des données AI est disponible pour les clients Customer Journey Analytics Prime et Ultimate. Elle n’est pas disponible dans Adobe Analytics.

Il est également disponible dans Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP et d’autres applications Experience Platform.

* **Accès contractuel** : si vous ne pouvez pas utiliser l’assistant d’IA, contactez l’administrateur ou le représentant du compte d’Adobe de votre entreprise. Avant de pouvoir utiliser l’assistant d’analyse des données, votre entreprise doit accepter certaines dispositions légales relatives à GenAI.

* **Autorisations** : dans le [!UICONTROL Adobe Admin Console], l’autorisation [!UICONTROL Outils de création de rapports] **[!UICONTROL Assistant d’IA : analyse des données]** détermine l’accès à cet outil. Un [ administrateur de profil de produit ](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes dans l’ [!UICONTROL Admin Console] :
   1. Accédez à **[!UICONTROL Admin Console]** > **[!UICONTROL Produits et services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Profils de produit]**
   1. Sélectionnez le titre du profil de produit pour lequel vous souhaitez donner accès à [!UICONTROL Assistant IA : connaissance du produit].
   1. Dans le profil de produit spécifique, sélectionnez **[!UICONTROL Autorisations]**.
   1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier les **[!UICONTROL outils de création de rapports]**.
   1. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) pour ajouter **l’assistant d’IA : analyse des données** à **[!UICONTROL éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions.png).

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

Voir [Contrôle d’accès](/help/technotes/access-control.md#access-control) pour plus d’informations.

## Accès à l’assistant d’analyse des données




## Utilisation de l’assistant d’analyse des données

1. Dans Customer Journey Analytics, accédez à l’environnement de test configuré.

1. Ouvrez un projet Workspace.


## Exemples d’analyses de données

Voici quelques exemples de la réponse de l’assistant d’IA aux invites et des visualisations attendues :



## Bonnes pratiques en matière de promotion

À confirmer

## Alpha des attentes en matière de test et des commentaires demandés

TB D

## Questions et contacts

Email `taylorb@adobe.com` (PM)
Envoi de questions et de commentaires dans le canal de suivi des Alpha




