---
description: Comment poser des questions relatives à l’analyse des données dans la documentation du Customer Journey Analytics
title: Assistant d’IA dans l’analyse des données en Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: ab8a4c65de59e725d7d181ee699d7a196988bf98
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 4%

---


# Assistant d’analyse des données IA en Customer Journey Analytics - Alpha

L’assistant d’analyse des données est un agent de conversation intelligent et contextuel qui peut vous aider à répondre plus rapidement et plus efficacement aux questions que vous pouvez vous poser sur vos données Analysis Workspace en Customer Journey Analytics.

L’assistant examine toutes les données d’une vue de données, y compris les différents types de mesures et de composants, et convertit votre invite en la bonne dimension, mesure et période pour cette analyse. Au lieu de devoir vous familiariser avec les composants de vue de données, puis les faire glisser et les déposer dans la meilleure combinaison pour répondre à votre question, vous pouvez simplement saisir la question dans l’assistant d’IA.

## Fonctionnalités intégrées ou hors plage pour la version Alpha

### Fonctionnalités intégrées

| Fonctionnalité prise en charge | Description |
| --- | --- |
| **Créer et mettre à jour des visualisations** | Génère un tableau à structure libre et la visualisation associée (par ex. ligne, barre, anneau, etc.).<p>Exemple : *Quel est le bénéfice entre les SKU de février à mai ?* |
| **Types de visualisation pris en charge** | <ul><li>Ligne</li><li>Multi-ligne</li><li>Tableau à structure libre</li><li>Barre</li><li>Anneau</li><li>Synthèse des chiffres</li></ul> |
| **Détection d’invite hors plage** | Si vous envoyez une invite qui n’est pas exhaustive (par exemple, &quot;Exportez ce projet&quot;), l’assistant répond en vous informant que la question est hors de portée. |
| **Clarification des questions** | Si vous posez une question dont le contexte n’est pas suffisant pour que l’assistant d’IA puisse répondre, ou si elle est trop générique, l’assistant d’IA répond par une question précise et/ou par des options suggérées. Exemples : <p>**Composants**<ul><li>Mesure : *Quelle mesure &quot;recettes&quot; voulez-vous dire ?*</li><li>Dimension : *Sur quelles &quot;régions&quot; souhaitez-vous vous concentrer ?*</li><li>Filtre : *Quel filtre &quot;Compte&quot; souhaitez-vous appliquer ?*</li><li>Plage de dates : *Par &quot;dernier mois&quot;, avez-vous parlé du dernier mois complet ou des 30 derniers jours ?*</li></ul>**Éléments de Dimension** : quel &quot;nom de magasin&quot; voulez-vous dire ? (par exemple, #5274 de magasin, #2949 de magasin, etc.) |
| **Multi-tour** | L’assistant d’IA répond à une invite avec le contexte de la ou des invite(s) précédente(s), ce qui permet aux utilisateurs de mettre à jour les visualisations et de poser des questions de suivi. Exemple : *Afficher les données de mars à avril à la place.* |
| **Commentaires** | <ul><li>Pouces vers le haut</li><li>Menu déroulant</li><li>Indicateur</li></ul> |

### Fonctionnalités hors plage

| Fonctionnalité non prise en charge | Description |
| --- | --- |
| **Résumé en ligne ou réponse** | L’assistant d’IA ne peut pas répondre en ligne dans le rail de conversation avec une réponse rapide de l’utilisateur. Exemples d’invites hors plage :<ul><li>*Donne-moi un résumé des insights de ma dernière invite.*</li><li>*Résumer les surbrillances à partir de la visualisation en ligne.*</li></ul> |
| **Clarification des questions** | Les questions clarifiantes sont limitées aux composants et aux éléments de dimension. L’assistant AI ne peut pas clarifier les vues de données, les visualisations, la granularité des données, la comparaison, la portée, etc. Sans clarifier les questions, l’assistant propose par défaut ce que vous cherchez probablement. S’il renvoie une visualisation ou une granularité de données inattendue, vous pouvez alors utiliser la fonctionnalité de mise à jour/à tour multiple pour ajuster la visualisation et les données. |
| **Actions/fonctionnalités Workspace** | L’assistant d’IA ne peut pas exécuter d’actions pour un utilisateur dans Workspace en plus de créer et de mettre à jour des visualisations. Par exemple, il ne peut pas effectuer les opérations suivantes :<ul><li>Boutons de l’interface utilisateur de l’action contextuelle (ajout au graphique, nouveau panneau, nouveau tableau)</li><li>Partager</li><li>Exporter</li><li>Télécharger</li><li>Gestion des préférences utilisateur</li><li>Traiter</li><li>Gérer la vue des données</li><li>Application de tableaux de bord Analytics</li><li>Attribution</li></ul> |
| **Types de visualisation non pris en charge** | <ul><li>Flux</li><li>Abandon</li><li>Tableau de cohortes</li><li>Surface, Aires empilées</li><li>Barres empilées</li><li>Puce</li><li>Combo</li><li>Histogramme</li><li>Barre horizontale, Barre empilée horizontale</li><li>Résumé des mesures clés</li><li>Nuage de points</li><li>Synthèse des modifications</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| **Explication et vérifiabilité** | Description ou citation transparente de la manière dont l’assistant d’IA a généré une réponse et vous permettant de confirmer que la réponse est correcte. |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Accès et utilisation de l’assistant d’analyse des données

1. Accédez à ce lien pour ouvrir Workspace dans l’organisation IMS Labs (dans l’étape) et vous connecter à votre Adobe ID.

1. Cliquez sur **[!UICONTROL Projet vierge]** dans la bannière située en haut de la page des projets pour ouvrir un nouveau projet vierge.

1. Cliquez sur l’icône de conversation de l’assistant d’IA en haut à droite.

   ![Icône de l’assistant d’IA](/help/assets/ai-asst-icon.png)

1. Dans la boîte de dialogue **[!UICONTROL Poser des questions sur le Customer Journey Analytics]** située en bas, posez une question d’analyse des données dans l’assistant d’IA.

### Exemple 1

Par exemple, supposons que vous soyez intéressé par les commandes que votre entreprise a reçues en juillet.

1. Saisissez &quot;Afficher les commandes en juillet&quot;.

   ![ ](/help/assets/ai-asst-prompt1.png) invite AI

1. L’assistant d’IA rassemble désormais des informations en analysant les données de la vue de données, y compris les mesures et les composants. Elle convertit l’invite en la ou les dimensions, mesures et plages de données appropriées.

   Comme vous pouvez le constater, il a automatiquement généré un graphique linéaire et un tableau à structure libre affichant les commandes pour le mois de juillet.

   ![Réponse à l’invite - graphique linéaire et tableau à structure libre](/help/assets/ai-asst-result.png)

### Exemple 2

Ensuite, vous souhaitez comparer vos recettes par région.

1. Dans la fenêtre d’invite, saisissez &quot;Afficher les recettes par région&quot;.

2. L’IA est suffisamment intelligente pour comprendre qu’en &quot;région&quot;, vous entendez &quot;région du client&quot;. Il génère un graphique à barres qui présente le mieux les recettes par région :

   ![Graphique à barres](/help/assets/ai-asst-result2.png)

### Exemple 3

Examinons maintenant les recettes par catégorie de produits.

1. Dans la fenêtre d’invite, saisissez &quot;Afficher les recettes par catégorie de produits&quot;.

2. Là encore, l’assistant d’analyse des données recherche la visualisation la plus appropriée, dans ce cas la visualisation **[!UICONTROL Anneau]**, pour répondre à la question.

   ![Anneau](/help/assets/ai-asst-result3.png)

### Exemple 4

Enfin, vous souhaitez savoir quel SKU est le plus rentable et où investir des ressources marketing.

1. Dans la fenêtre d’invite, demandez : &quot;Quel est le bénéfice entre les SKU de février à mai ?&quot;

1. Un simple graphique **[!UICONTROL Bar]** fournit la réponse la plus concise :

   ![Graphique à barres](/help/assets/ai-asst-result4.png)

## Exemples d’analyses de données

Voici quelques exemples d’invites courantes, et la visualisation utilisée par l’assistant d’IA pour répondre à ces invites.

| Exemple d’invite | Visualisation prévue |
| --- | --- |
| Afficher mes profits dans [Month] | Ligne<p>La demande d’une tendance ou d’une mesure au cours d’une période spécifique par défaut renvoie une visualisation en ligne. |
| Tendance des commandes dans le [mois] | Ligne |
| Afficher les recettes par région dans [Month] | Barre |
| Part du chiffre d’affaires par catégorie de produit | Anneau |
| Commandes par jour de la semaine, de janvier à mai | Barre |
| Afficher les commandes par genre de mars à juin | Barre |
| Quels sont les bénéfices réalisés par les SKU entre février et mai ? | Barre |
| Recettes par nom de magasin dans [Month] | Barre |
| Quels ont été mes 10 SKU les plus rentables en [Month] ? | Barre |
| Proportion des achats par mois de l&#39;année | Anneau |
| Bénéfice total en [Month] | Synthèse des chiffres<p>Si vous demandez le &quot;total&quot; d’une mesure sur une certaine période, vous devriez renvoyer une visualisation de nombre récapitulatif. |


## Bonnes pratiques en matière de promotion

À confirmer

## Alpha des attentes en matière de test et des commentaires demandés

Après avoir posé chaque question, examinez attentivement la réponse fournie par l&#39;assistant. Il est essentiel d’évaluer complètement les visualisations générées avant de fournir un retour.

Évaluer la réponse : la réponse est-elle correcte ?

Si l’assistant répond dans le rail de conversation : évaluez la réponse textuelle.

* Si une visualisation/un graphique s’affiche : évaluez la visualisation. S’agit-il de la visualisation appropriée/attendue pour votre question ?

* Si un tableau à structure libre s’affiche : évaluez le tableau à structure libre. Les données du tableau à structure libre sont-elles correctes ? Ventile-t-il les données là où elles sont demandées ? Les filtres appliqués sont-ils ceux que vous avez demandés ou attendus ?

* Si un message d’erreur générique indique que la question est hors de portée, indiquez si vous pensez que le message hors de portée est approprié à votre invite. Votre invite était-elle réellement en place ?

Pour chaque réponse, donnez un pouce vers le haut ou vers le bas, en fonction de la réponse.

Après avoir sélectionné les pouces vers le haut/bas, faites une sélection pour les zones de commentaire à sélection multiple appropriées. Si vous souhaitez fournir des commentaires supplémentaires, ajoutez des notes dans la zone de texte ouverte.

## Questions et contacts

* Email `taylorb@adobe.com` (PM)
* Envoyez des questions et des commentaires dans le canal de suivi des Alpha : #aep-cja-ai-assistant-testers ???


