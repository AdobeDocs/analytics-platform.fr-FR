---
description: Comment poser des questions d’analyse des données dans la documentation de Customer Journey Analytics
title: Assistant d’IA Analyse de données dans Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: 99f82353e41180a0090e84e58593d63fc5cbe803
workflow-type: tm+mt
source-wordcount: '1650'
ht-degree: 3%

---

# Visualiser les données à l’aide de l’assistant AI dans Customer Journey Analytics

L’assistant d’IA dans Customer Journey Analytics est un agent de conversation d’IA génératif qui répond rapidement et efficacement aux questions sur vos données. Il crée des visualisations pertinentes dans Analysis Workspace à l’aide de composants de votre vue de données et en utilisant vos données réelles.

L’utilisation de l’assistant d’IA pour répondre à des questions relatives aux données dans Analysis Workspace peut vous permettre de gagner d’innombrables heures que vous pourriez passer à créer manuellement des visualisations dans Analysis Workspace et à vous familiariser avec vos composants de vue de données.

![Assistant IA Analyse des données](assets/cja-ai-asst-da.gif)

## Fonctionnalités incluses ou non dans la portée de la version d’Alpha

### Fonctionnalités d’Alpha intégrées

| Fonctionnalité prise en charge | Description |
| --- | --- |
| **Création et mise à jour de visualisations** | Génère un tableau à structure libre et les visualisations associées (ligne, barre, anneau, etc.).<p>Exemple : *Quel est le bénéfice sur l’ensemble des SKU de février à mai ?* |
| **Types de visualisation pris en charge** | <ul><li>Ligne</li><li>Multiligne</li><li>Tableau à structure libre</li><li>Barre</li><li>Anneau</li><li>Nombre de résumés</li></ul> |
| **Détection d’invite hors de portée** | Si vous envoyez une invite hors de portée, telle que « exporter ce projet », l’assistant vous répond en vous informant que la question est hors de portée. |
| **Clarification des questions** | Si vous posez une question à laquelle l’assistant AI ne peut pas répondre dans un contexte suffisant ou si elle est trop générique, il répond par une question de clarification ou des suggestions d’options. Exemples : <p>**Composants**<ul><li>Mesure : *Quelle mesure « chiffre d’affaires » vouliez-vous dire ?*</li><li>Dimension : *Sur laquelle des « régions » ci-dessous voulez-vous vous concentrer ?*</li><li>Filtre : *Quel filtre « Compte » vouliez-vous appliquer ?*</li><li>Période : *Par « mois dernier », vouliez-vous dire le dernier mois complet ou les 30 derniers jours ?*</li></ul>**Éléments de Dimension** : de quel « nom de magasin » parlez-vous ? (par exemple, #5274 de magasin, #2949 de magasin, etc.). |
| **Multi-tour** | L’assistant d’IA répond à une invite avec le contexte de toutes les invites précédentes, ce qui permet aux utilisateurs et utilisatrices de mettre à jour les visualisations et de poser des questions de suivi. Exemple : <ul><li>Invite 1 : *Tendance des événements à partir de mars.*</li><li>Invite 2 : *afficher à la place les données de mars à avril*</li></ul> |
| **Vérifiabilité** | La vérifiabilité et l’exactitude des données peuvent être confirmées via le tableau à structure libre généré et la visualisation des données. Par exemple, si un utilisateur demande *Tendance des commandes le mois dernier*, vous pouvez confirmer que la mesure correcte (« commandes ») et la période (« mois dernier ») ont été sélectionnées dans le panneau, la visualisation des données et le tableau à structure libre nouvellement générés. |
| **Commentaires** | <ul><li>Pouces levés</li><li>Pouces baissés</li><li>Drapeau</li></ul> |

### Fonctionnalités Alpha hors de portée

| Fonction non prise en charge | Description |
| --- | --- |
| **Résumé ou réponse en ligne** | L’assistant d’IA ne peut pas répondre en ligne dans le rail de conversation avec une réponse récapitulative d’une invite utilisateur. Exemples d’invites hors de portée :<ul><li>*Donnez-moi un résumé des informations de ma dernière invite.*</li><li>*Résumer les points forts de la visualisation Ligne.*</li></ul> |
| **Clarification des questions** | Les questions de clarification sont limitées aux composants et aux éléments de dimension. L’assistant d’IA ne peut pas clarifier des éléments tels que les vues de données, les visualisations, la granularité des données, la comparaison et la portée. Lorsque des questions de clarification ne peuvent pas être utilisées, l&#39;Assistant utilise par défaut ce que vous demandez le plus probablement. Si elle renvoie une visualisation ou une granularité de données inattendue, vous pouvez ensuite utiliser la fonctionnalité multi-tour / mise à jour pour ajuster la visualisation et les données. |
| **Actions/fonctionnalités Workspace** | L’assistant d’IA ne peut pas agir pour un utilisateur dans Workspace, à part créer et mettre à jour des visualisations. Par exemple, il ne peut effectuer aucune des opérations suivantes :<ul><li>Boutons de l’interface utilisateur d’action contextuelle (ajouter au graphique, nouveau panneau, nouveau tableau)</li><li>Partager</li><li>Exporter</li><li>Télécharger</li><li>Gérer les préférences utilisateur</li><li>Traiter</li><li>Gérer la vue de données</li><li>Application Tableaux de bord Analytics</li><li>Attribution</li></ul> |
| **Types de visualisation non pris en charge** | <ul><li>Flux</li><li>Abandon</li><li>Tableau de cohortes</li><li>Aires, Aires empilées</li><li>Barres empilées</li><li>Puce</li><li>Combo</li><li>Histogramme</li><li>Barres horizontales, barres empilées horizontales</li><li>Résumé des mesures clés</li><li>Nuage de points</li><li>Synthèse des modifications</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Accéder à et utiliser la visualisation de données dans l’assistant AI

1. Accédez à [experience.adobe.com](https://experience.adobe.com/) et connectez-vous avec votre Adobe ID.

2. Sélectionnez **Customer Journey Analytics** sur la page d’accueil Experience Cloud.

3. Sélectionnez **[!UICONTROL Projet vierge]** dans la bannière en haut de la page des projets pour ouvrir un nouveau projet vierge.

4. Assurez-vous que la vue de données sélectionnée pour le panneau est identique à la vue de données activée pour une utilisation avec l’assistant AI pour les tests Alpha.

   Si vous n’êtes pas sûr, contactez le canal Slack d’Alpha.

5. Sélectionnez l’icône de conversation de l’assistant AI dans la zone supérieure droite de la page.

   Si vous ne voyez pas l’icône de conversation, contactez votre administrateur afin qu’il puisse activer les fonctionnalités suivantes dans Admin Console :

   * **[!UICONTROL Assistant IA : connaissance des produits]**

   * **[!UICONTROL Assistant IA : analyse des données]**

   Pour plus d’informations, les administrateurs peuvent consulter [ces instructions](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![Icône de l’assistant AI](/help/assets/ai-asst-icon.png)

6. Dans la boîte de dialogue **[!UICONTROL Demandez à propos de Customer Journey Analytics]** au bas de la page, posez une question sur la visualisation des données dans l’assistant d’IA.

   Pour plus d’informations, consultez les exemples suivants.

### Exemple 1

Supposons, par exemple, que vous soyez intéressé par les commandes que votre entreprise a reçues en juillet.

**Invite:** Saisissez *« Tendance des commandes en juillet. »*

![invite AI](/help/assets/ai-asst-prompt1.png)

**Réponse :** l’assistant d’IA collecte des informations en examinant les données de la vue de données, y compris les mesures et les composants. Cela traduit l’invite en dimensions et mesures appropriées dans la plage de données.

Comme vous pouvez le constater, il a généré automatiquement un graphique linéaire et un tableau à structure libre pour afficher les commandes pour juillet.

![Réponse à l’invite - graphique linéaire et tableau à structure libre](/help/assets/ai-asst-result.png)

### Exemple 2

Ensuite, vous devez comparer vos revenus par région.

**Invite :** dans la fenêtre d’invite, saisissez *« Afficher le chiffre d’affaires par région »*

**Réponse :** l’assistant d’IA comprend intelligemment que par « région », vous voulez dire « région du client ». Il génère un graphique à barres qui présente le mieux les recettes par région :

![Graphique à barres](/help/assets/ai-asst-result2.png)

### Exemple 3

Ensuite, en plus de comprendre le chiffre d’affaires par région, vous souhaitez également afficher les données de bénéfice par région. Au lieu de répéter l’invite précédente, vous pouvez demander à l’assistant AI de mettre à jour la visualisation la plus récente et le tableau à structure libre.

**Invite :** dans la fenêtre d’invite, saisissez *« Ajouter un bénéfice »*

**Réponse :** le graphique **[!UICONTROL Barres]** fournit toujours la réponse la plus concise, mais la mesure de profit a été ajoutée sous la forme d’une colonne dans le tableau à structure libre :

![Graphique à barres](/help/assets/ai-asst-result4.png)

### Exemple 4

Enfin, examinons les recettes par catégorie de produits.

**Invite :** dans la fenêtre d’invite, saisissez *« Proportion du chiffre d’affaires par catégorie de produits ».*

**Réponse :** nouveau, la visualisation de données dans l’assistant AI sélectionne la visualisation la plus appropriée, dans ce cas la visualisation **[!UICONTROL en anneau]**, pour répondre à la question.

![Anneau](/help/assets/ai-asst-result3.png)

## Exemples d’invites de visualisation de données

Vous trouverez ci-dessous quelques exemples d’invites courantes et des visualisations utilisées par l’assistant AI pour répondre à ces invites.

| Exemple d’invite | Visualisation attendue |
| --- | --- |
| Afficher les bénéfices en [mois] | Ligne<p>Demander une tendance ou une mesure au cours d’une certaine période par défaut renvoie une visualisation en lignes. |
| Tendance des commandes en [mois] | Ligne |
| Afficher le chiffre d’affaires par région en [mois] | Barre |
| Part des revenus par catégorie de produits | Anneau |
| Commandes par jour de la semaine, de janvier à mai | Barre |
| Afficher les commandes par genre, de mars à juin | Barre |
| Quel est le bénéfice entre les SKU de février à mai ? | Barre |
| Chiffre d’affaires par nom de magasin dans [Mois] | Barre |
| Quels ont été mes 10 principaux SKU par bénéfice au cours du [Mois] ? | Barre |
| Proportion d&#39;achats par mois de l&#39;année | Anneau |
| Bénéfice total en [mois] | Synthèse des chiffres<p>Demander le « total » d’une mesure sur une certaine période doit renvoyer une visualisation Synthèse des chiffres. |


## Bonnes pratiques en matière de promotion

L’assistant d’IA traite le contexte fourni par chaque invite utilisateur et tente de répondre intelligemment avec la visualisation et les composants les plus appropriés dans un tableau à structure libre.

Les réponses peuvent varier en fonction des mots et expressions spécifiques utilisés dans l’invite, et de légères modifications de la langue peuvent entraîner des résultats différents.

Pour obtenir les meilleurs résultats, tenez compte des recommandations suivantes :

* Soyez précis : incluez des termes exacts pour réduire la réponse. Voici un exemple d’invite spécifique : « Ventes du mois dernier en Californie »

* Utiliser des mesures et des filtres clairs : l’ajout de mesures spécifiques (telles que « Chiffre d’affaires »), de dimensions (telles que « nom du site web »), de filtres (tels que « utilisateurs d’iPhone ») et de périodes (telles que « trois derniers mois ») permet à l’assistant d’IA de se concentrer sur les données appropriées.

* Poser des questions directes : la formulation directe des questions permet à l’assistant d’IA de fournir plus facilement des informations claires et pertinentes. Voici un exemple de question directe dans une invite : « Quel est le chiffre d’affaires moyen par catégorie de produits cette année ? »

Consultez le tableau suivant d’exemples de termes et d’expressions que vous pouvez utiliser dans les invites avec la visualisation des données dans l’assistant AI, ainsi que les types de réponses attendus.

Ces exemples sont conçus pour vous aider à vous familiariser avec la manière dont des mots ou des structures spécifiques peuvent influencer la sortie de l’assistant d’IA, afin de garantir des informations plus précises et plus précieuses. L’assistant d’IA utilise l’IA générative, de sorte que les visualisations ou les données sélectionnées peuvent varier légèrement selon des invites similaires.

| Résultat souhaité | Exemples de termes et d’expressions |
| --- | --- |
| Visualisation Synthèse des chiffres | <ul><li>Total</li></ul> |
| Comparer les composants | <ul><li>Comparer</li><li>VS</li><li>Contraste</li><li>Semaine par semaine</li><li>Mois par mois</li><li>Trimestre par trimestre</li><li>D&#39;une année sur l&#39;autre</li></ul> |
| Visualisation en anneau | <ul><li>Proportion</li><li>Part de</li><li>Répartition</li><li>Pourcentage</li><li>Contribution</li><li>Partie</li><li>Parties</li></ul> |
| Visualisation sous forme de lignes | <ul><li>Tendance</li><li>[Mesure] dans [Période]</li></ul> |
| Visualisation sous forme de barres | <ul><li>[Mesure] par [Dimension]</li></ul> |

## Attentes en matière de test Alpha et commentaires demandés

Après avoir posé chaque question, examinez attentivement la réponse fournie par l&#39;assistant. Il est essentiel d’évaluer entièrement les visualisations générées avant de fournir des commentaires.

Tenez compte des points suivants lors de l’évaluation d’une réponse de l’assistant AI :

* Réponse du rail de conversation ou modèle : évaluez la réponse textuelle fournie par l’assistant. La réponse est-elle appropriée compte tenu du contexte de votre invite ?

* Visualisation/graphique : permet d’évaluer la visualisation. S’agit-il de la visualisation appropriée ou attendue pour votre question, ou vous attendiez-vous à une visualisation différente ?

* Tableau à structure libre : permet d’évaluer le tableau à structure libre. Les données du tableau à structure libre sont-elles correctes ? Ventilez-vous les données là où elles sont demandées? Les filtres appliqués sont-ils ceux que vous avez demandés ou attendus ?

* Message d’erreur / Hors-portée : si un message d’erreur générique indiquant que la question est hors de portée est fourni, indiquez si vous pensez que le message de hors-portée est approprié, compte tenu de votre invite. Votre invite était-elle vraiment dans la portée ?

**Pour chaque réponse, donnez un pouce vers le haut ou un pouce vers le bas, en fonction de la réponse.**

Après la sélection des pouces vers le haut ou vers le bas, veuillez effectuer une sélection pour les champs de commentaires à sélection multiple pertinents. Si vous souhaitez fournir des commentaires supplémentaires, ajoutez des notes dans la zone de texte ouverte.

## Questions et contact

* Envoyez vos questions et commentaires sur le canal Alpha Slack : #cja-assistant-data-alpha
