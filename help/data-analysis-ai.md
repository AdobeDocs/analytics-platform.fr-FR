---
description: Poser des questions sur l’analyse des données dans la documentation de Customer Journey Analytics
title: Visualiser des données avec l’agent Data Insights dans Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: cd92bde10b9cb473c4df791e91296a2a43b2ad84
workflow-type: tm+mt
source-wordcount: '2463'
ht-degree: 94%

---

# Visualiser des données avec l’agent Data Insights

>[!AVAILABILITY]
>
>L’agent Data Insights est disponible pour les clientes et clients éligibles pour une durée limitée. L’accès à l’agent Data Insights prendra fin le 30 novembre 2025. Pour continuer à utiliser l’agent Data Insights sans interruption, contactez votre représentant ou représentante de compte Adobe pour en savoir plus sur les licences associées.

L’agent Data Insights, accessible à partir de l’[Assistant IA](/help/ai-assistant.md) dans Customer Journey Analytics, est un agent de conversation d’IA générative qui répond rapidement et efficacement aux questions sur vos données. Il crée des visualisations pertinentes dans Analysis Workspace en utilisant les composants de votre vue de données et vos données réelles.

Utiliser l’agent Data Insights pour répondre à des questions sur des données dans Analysis Workspace peut vous faire gagner énormément de temps, que vous auriez sinon consacré à créer manuellement des visualisations dans Analysis Workspace et à vous familiariser avec les composants de votre vue de données.

![Agent Data Insights dans l’Assistant IA](assets/cja-ai-asst-da.gif)

## Fonctionnalités incluses ou non dans les capacités de traitement

| Fonctionnalité | Incluse dans les capacités de traitement | Hors des capacités de traitement |
| --- | --- | --- |
| **Types de visualisations** | <ul><li>Graphique linéaire</li><li>Multiligne</li><li>Tableau à structure libre</li><li>Barres</li><li>Anneau</li><li>Synthèse des chiffres</li></ul> | <ul><li>Flux</li><li>Abandon</li><li>Table de cohortes</li><li>Surface et aires empilées</li><li>Barres empilées</li><li>Puces</li><li>Combo</li><li>Histogramme</li><li>Barres horizontales et barres empilées horizontales</li><li>Synthèse des mesures clés</li><li>Nuage de points</li><li>Synthèse des modifications</li><li>Texte</li><li>Plan en arborescence</li><li>Venn</li><li>Analyse guidée : croissance active, tendances de conversion, engagement, impact de la première utilisation, fréquence, entonnoir, croissance nette, impact sur la publication, rétention, chronologie, tendances</li></ul> |
| **Actions Workspace et fonctionnalités de l’agent** | <ul><li>Créer et mettre à jour des visualisations<p>Génère un tableau à structure libre et les visualisations associées (ligne, barre, anneau, etc.).<p>Par exemple, *Quel est le bénéfice sur l’ensemble des SKU de février à mai ?*</p></li><li>Poser des questions à la suite du prompt initial<p>Répondez à un prompt dans le contexte de prompts précédents. Par exemple :</p> <ul><li>Prompt 1 : *Indique la tendance des événements à partir de mars.*</li><li>Prompt 2 : *Montre-moi les données de mars à avril à la place*</li></ul> </li><li>Détection de prompt hors des capacités de traitement<p>Si vous envoyez un prompt hors des capacités de traitement, par exemple *Exporte ce projet*, l’agent Data Insights vous informe que la question est hors des capacités de traitement.</p></li></ul> | <ul><li>Partager</li><li>Exporter</li><li>Télécharger</li><li>Gestion les préférences d’utilisateur et d’utilisatrice</li><li>Gérer la vue de données</li><li>Application des tableaux de bord Analytics</li><li>Attribution</li><li>Résumé ou réponse en ligne<p>L’agent Data Insights ne peut pas répondre en ligne dans le rail de conversation avec une réponse résumée d’un prompt d’utilisateur ou d’utilisatrice. Voici des exemples de prompts hors de portée : *Résume les informations de ma dernière invite* et *Résume les points forts de la visualisation en ligne.*</p></li></ul> |
| **Questions de clarification** | Si vous posez une question à laquelle l’agent Data Insights ne peut pas répondre en raison d’un manque de contexte ou si votre question est trop générique, l’agent Data Insights vous répond par une question de clarification ou en suggérant des options. <p>Les questions de clarification suivantes sont des exemples de questions liées aux composants :</p><ul><li>Mesure : *de quelle mesure « chiffre d’affaires » parlez-vous ?*</li><li>Dimension : *Sur laquelle des « régions » ci-dessous voulez-vous vous concentrer ?*</li><li>Segment : *quel segment « Compte » voulez-vous appliquer ?*</li><li>Période : *par « mois dernier », entendez-vous le dernier mois complet ou les 30 derniers jours ?*</li></ul><p>La question de clarification suivante est un exemple de question liée aux éléments de dimension :</p> <ul><li>De quel « nom de magasin » parlez-vous ? (Par exemple, magasin n° 5274, magasin n° 2949 etc.)</li></ul> | Les questions de clarification sont limitées aux composants et aux éléments de dimension. L’agent Data Insights ne peut pas clarifier des éléments tels que les vues de données, les visualisations, la granularité des données, la comparaison et la portée. Lorsque des questions de clarification ne peuvent pas être utilisées, l’agent se contente de répondre à la demande la plus probable. S’il renvoie une visualisation ou une granularité de données inattendue, vous pouvez poser une question complémentaire ou ajuster la visualisation et les données. |
| **Vérifiabilité et exactitude des données** | La vérifiabilité et l’exactitude des données peuvent être confirmées en affichant le tableau à structure libre et la visualisation des données générés. <p>Par exemple, si vous demandez à l’agent Data Insights d’*établir la tendance des commandes du mois dernier*, vous pouvez confirmer que la mesure correcte (« commandes ») et la période (« mois dernier ») ont été sélectionnées dans le panneau, la visualisation des données et le tableau à structure libre nouvellement générés. | L’agent Data Insights ne répond pas en vous informant des composants ou des visualisations qui ont été ajoutés.</p> |
| **Mécanismes de commentaires** | <ul><li>Pouces levés</li><li>Pouces baissés</li><li>Drapeau</li></ul> |  |


## Gérer l’accès à l’agent Data Insights {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Activer pour Data Insights Agent"
>abstract="Cette option active cette vue de données pour une utilisation avec Data Insights Agent. Data Insights Agent est un agent de conversation d’IA génératif accessible à partir de l’assistant d’IA dans Customer Journey Analytics. Il vous permet d’analyser rapidement vos données à l’aide d’invites textuelles. Il crée des visualisations pertinentes dans Analysis Workspace en utilisant les composants de votre vue de données et vos données réelles."

<!-- markdownlint-enable MD034 -->

Les paramètres suivants régissent l’accès à l’agent Data Insights dans Customer Journey Analytics :

* **Accès à la solution** : l’agent Data Insights est disponible pour tous les clients et clientes Customer Journey Analytics dans le cadre d’un programme en accès limité jusqu’au 30 novembre 2025. Il n’est pas disponible dans Adobe Analytics.

* **Accès contractuel** : si vous ne pouvez pas utiliser l’agent Data Insights dans l’Assistant IA, contactez l’administrateur ou l’administratrice de votre entreprise ou l’équipe Adobe en charge des comptes. Avant que votre entreprise puisse utiliser l’agent Data Insights, vous devez accepter certaines conditions juridiques liées à l’IA générative.

* **Autorisations** : les autorisations nécessaires doivent être accordées dans l’[!UICONTROL Adobe Admin Console] avant que les utilisateurs et utilisatrices puissent accéder à l’agent Data Insights.

  Pour accorder des autorisations, [un administrateur ou une administratrice de profil de produit](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit effectuer les étapes suivantes dans l’[!UICONTROL Admin Console] :
   1. Dans l’**[!UICONTROL Admin Console]**, sélectionnez l’onglet **[!UICONTROL Produits]** pour afficher la page **[!UICONTROL Tous les produits et services]**.
   1. Sélectionnez **[!UICONTROL Customer Journey Analytics]**.
   1. Dans l’onglet **[!UICONTROL Profils de produit]**, sélectionnez le titre du profil de produit pour lequel vous souhaitez fournir un accès à [!UICONTROL Assistant IA : connaissance du produit].
   1. Dans le profil de produit spécifique, sélectionnez l’onglet **[!UICONTROL Autorisations]**.

      ![Onglet Autorisations dans l’Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Dans la ligne **[!UICONTROL Outils de création de rapports]** du tableau fourni, sélectionnez l’icône de modification ![Modifier](/help/assets/icons/Edit.svg).
   1. Recherchez ou faites défiler l’écran jusqu’à **[!UICONTROL Assistant IA : connaissance du produit]**, puis sélectionnez l’icône plus ![CercleAjouter](/help/assets/icons/AddCircle.svg) en regard de cette autorisation.

      L’autorisation **[!UICONTROL Assistant IA : connaissance du produit]** est ajoutée à la colonne **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions.png)

   1. Sélectionnez l’onglet **[!UICONTROL Outils des vues de données]**, puis sélectionnez l’icône plus ![Cercle d’ajout](/help/assets/icons/AddCircle.svg) en regard de l’autorisation **[!UICONTROL Agent Data Insights]**.

      L’autorisation **[!UICONTROL Agent Data Insights]** est ajoutée à la colonne **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajoutez une autorisation](assets/ai-assistant-permissions-dataviewtools.png).

   1. Sélectionnez l’onglet **[!UICONTROL Vues de données]** pour choisir les vues de données à activer pour l’agent Data Insights.

      >[!IMPORTANT]
      >
      >Tenez compte des points suivants lorsque vous activez les vues de données :
      >* Vous pouvez activer un maximum de 50 vues de données par organisation IMS. Si vous activez plus de 50 vues de données pour tous les profils de produit pour une organisation donnée, l’agent Data Insights utilisera les 50 vues de données les plus employées.
      >* L’agent Data Insights peut référencer les vues de données incluses à un moment donné le jour même de leur activation dans l’Admin Console.

   1. Recherchez ou faites défiler jusqu’aux vues de données à activer, puis sélectionnez l’icône plus ![CercleAjouter](/help/assets/icons/AddCircle.svg) en regard du nom de chaque vue de données.

      Chaque vue de données ajoutée est visible dans la colonne **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajoutez une autorisation](assets/ai-assistant-permissions-dataviews.png).

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

  Pour plus d’informations sur le contrôle d’accès, voir [Contrôle d’accès ](/help/technotes/access-control.md#access-control).

## Accès à l’agent Data Insights dans l’assistant IA

1. Accédez à [experience.adobe.com](https://experience.adobe.com/) et connectez-vous avec votre Adobe ID.

2. Sélectionnez **Customer Journey Analytics** sur la page d’accueil Experience Cloud.

3. Sélectionnez **[!UICONTROL Projet vierge]** dans la bannière en haut de la page des projets pour ouvrir un nouveau projet vierge.

4. Vérifiez que la vue de données sélectionnée pour le panneau est une vue de données qui a été activée pour être utilisée avec l’agent Data Insights, comme décrit dans la section [Gérer l’accès à l’agent Data Insights dans Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Sélectionnez l’icône de conversation de l’assistant IA en haut à droite de la page.

   Si vous ne voyez pas l’icône de conversation, contactez votre administrateur ou administratrice qui pourra activer les fonctionnalités suivantes dans l’Admin Console :

   * Outils de reporting : **[!UICONTROL Assistant IA : connaissance du produit]**

   * Outils des vues de données : **[!UICONTROL agent Data Insights]**

   Pour plus d’informations, voir [Gérer l’accès à l’agent Data Insights dans Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Icône de l’assistant IA](/help/assets/ai-asst-icon.png)

6. Dans la boîte de dialogue **[!UICONTROL Poser une question sur Customer Journey Analytics]** au bas de la page, posez une question sur la visualisation des données à l’aide de l’agent Data Insights.

   Pour plus d’informations, consultez les exemples suivants.

### Exemple 1

Supposons, par exemple, que vous vous intéressez aux commandes que votre entreprise a reçues en juillet.

**Prompt :** saisissez *« Tendance des commandes en juillet. »*

![Prompt IA](/help/assets/ai-asst-prompt1.png)

**Réponse :** l’agent Data Insights collecte des informations en examinant les données de la vue de données, y compris les mesures et les composants. Il traduit le prompt en dimensions et mesures appropriées dans la plage de données.

Comme vous pouvez le constater, il a généré automatiquement un graphique linéaire et un tableau à structure libre pour afficher les commandes du mois de juillet.

![Réponse au prompt : graphique linéaire et tableau à structure libre](/help/assets/ai-asst-result.png)

### Exemple 2

Ensuite, vous voulez comparer vos revenus par région.

**Prompt :** dans la fenêtre de prompt, saisissez *« Affiche le chiffre d’affaires par région. »*

**Réponse :** l’agent Data Insights comprend intelligemment que par « région », vous entendez « région des clientes et clients ». Il génère un graphique à barres qui présente au mieux le chiffre d’affaires par région :

![Graphique à barres](/help/assets/ai-asst-result2.png)

### Exemple 3

Ensuite, en plus d’analyser le chiffre d’affaires par région, vous souhaitez également afficher les données sur les bénéfices par région. Au lieu de répéter le prompt précédent, vous pouvez demander à l’agent Data Insights de mettre à jour le tableau à structure libre et la visualisation les plus récents.

**Prompt :** dans la fenêtre de prompt, saisissez *« Ajoute le bénéfice. »*

**Réponse :** le graphique à **[!UICONTROL barres]** reste la réponse la plus concise, mais la mesure de bénéfice a été ajoutée sous la forme d’une colonne dans le tableau à structure libre :

![Graphique à barres](/help/assets/ai-asst-result4.png)

### Exemple 4

Enfin, examinons le chiffre d’affaires par catégorie de produits.

**Prompt :** dans la fenêtre de prompt, saisissez *« Proportion du chiffre d’affaires par catégorie de produits. »*

**Réponse :** encore une fois, l’agent Data Insights sélectionne la visualisation la plus appropriée, soit la visualisation **[!UICONTROL en anneau]**, pour répondre à la question.

![Anneau](/help/assets/ai-asst-result3.png)

## Accès à Data Insights Agent dans toutes les applications Experience Cloud

Adobe Experience Platform Agent Orchestrator vous permet d’accéder aux fonctionnalités de Data Insights Agent dans plusieurs applications Adobe Experience Cloud, telles que Adobe Journey Optimizer et Real-Time CDP.

Agent Orchestrator interprète votre requête, détermine les agents spécialisés nécessaires et les orchestre pour fournir la réponse appropriée. Il effectue le suivi du contexte dans les interactions à plusieurs tours, de sorte que vous puissiez tirer parti naturellement des requêtes précédentes.

Pour plus d&#39;informations, voir [Adobe Experience Platform Agent Orchestrator](http://www.adobe.com/go/agent-orchestrator-home).

## Exemples de prompts de visualisation de données

Vous trouverez ci-dessous quelques exemples de prompts courants et les visualisations utilisées par l’agent Data Insights pour répondre à ces invites.

| Exemple de prompt | Visualisation attendue |
| --- | --- |
| Affiche les bénéfices en [mois] | Graphique linéaire<p>Demander une tendance ou une mesure au cours d’une certaine période renvoie par défaut une visualisation sous forme de graphique linéaire. |
| Tendance des commandes en [mois] | Graphique linéaire |
| Affiche le chiffre d’affaires par région en [mois] | Barres |
| Part du chiffre d’affaire par catégorie de produits | Anneau |
| Commandes par jour de la semaine, de janvier à mai | Barres |
| Affiche les commandes par genre, de mars à juin | Barres |
| Quel est le bénéfice pour les différents SKU de février à mai ? | Barres |
| Chiffre d’affaires par nom de magasin en [mois] | Barres |
| Quels ont été mes 10 principaux SKU par bénéfice en [mois] ? | Barres |
| Proportion d’achats par mois de l’année | Anneau |
| Bénéfice total en [mois] | Synthèse des chiffres<p>Demander le « total » d’une mesure sur une certaine période doit renvoyer une visualisation Synthèse des chiffres. |


## Bonnes pratiques pour les prompts

L’agent Data Insights traite le contexte fourni par chaque prompt d’utilisateur ou d’utilisatrice et tente de répondre intelligemment avec la visualisation et les composants les plus appropriés dans un tableau à structure libre.

Les réponses peuvent varier en fonction des mots et expressions spécifiques utilisés dans le prompt, et de légères modifications linguistiques peuvent entraîner des résultats différents.

Pour obtenir les meilleurs résultats, tenez compte des recommandations suivantes :

* **Faites preuve de précision :** incluez des termes exacts pour affiner la réponse. Voici un exemple de prompt spécifique : « Ventes du mois dernier en Californie »

* **Utilisez des mesures, des dimensions et des segments clairs :** l’ajout de mesures spécifiques (comme « chiffre d’affaires »), de dimensions (comme « nom du site web »), de segments (comme « utilisateurs et utilisatrices d’iPhone ») et de périodes (comme « trois derniers mois ») permet à l’agent Data Insights de se concentrer sur les données appropriées.

* **Posez des questions directes :** cela permet à l’agent Data Insights de fournir plus facilement des informations claires et pertinentes. Voici un exemple de question directe dans un prompt : « Quel est le chiffre d’affaires moyen par catégorie de produits cette année ? »

Consultez le tableau ci-dessous pour obtenir des exemples de termes et d’expressions que vous pouvez utiliser dans les prompts avec l’agent Data Insights, ainsi que les types de réponses attendus.

Ces exemples ont été conçus pour vous aider à vous familiariser avec la manière dont des mots ou des structures spécifiques peuvent influencer la sortie de l’agent Data Insight, afin de garantir des informations plus précises et plus utiles. L’agent Data Insights utilise l’IA générative. Les visualisations ou les données sélectionnées peuvent donc varier légèrement d’un prompt à l’autre.

| Résultat souhaité | Exemples de termes et d’expressions |
| --- | --- |
| Visualisation Synthèse des chiffres | <ul><li>Total</li></ul> |
| Composants de comparaison | <ul><li>Comparer</li><li>Ou</li><li>Contraste</li><li>D’une semaine à l’autre</li><li>D’un mois à l’autre</li><li>D’un trimestre à l’autre</li><li>D’une année à l’autre</li></ul> |
| Visualisation en anneau | <ul><li>Proportion</li><li>Part de</li><li>Répartition</li><li>Pourcentage</li><li>Contribution</li><li>Partie</li><li>Parties</li></ul> |
| Visualisation sous forme de lignes | <ul><li>Tendance</li><li>[Mesure] au cours de [Période]</li></ul> |
| Visualisation sous forme de graphique à barres | <ul><li>[Mesure] par [Dimension]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->


## Bonnes pratiques de configuration

Vous trouverez ci-dessous les bonnes pratiques pour votre configuration de Customer Journey Analytics (vue de données, mesures calculées, segments, etc.) pour vous assurer que l’agent Data Insights peut localiser les composants appropriés et renvoyer des réponses plus précises sans avoir à vous demander des informations supplémentaires.

* **Équilibrez les composants dont vous avez besoin**. N’ajoutez pas tous les champs de vos jeux de données en tant que composants de mesure ou de dimension à votre vue de données. Et plus particulièrement ceux que vous n’utiliserez certainement pas dans votre analyse. Par ailleurs, ne vous limitez pas strictement aux champs que vous prévoyez d’utiliser pour votre analyse. Une vue de données trop limitée entrave la flexibilité de votre analyse et la fonctionnalité de l’agent Data Insights.
* **Utilisez toujours des noms d’affichage conviviaux**. Assurez-vous que tous les champs que vous définissez dans votre vue de données, en tant que composant de mesure ou de dimension, ont un nom de composant convivial. Le processus de renommage des champs avec un nom convivial est particulièrement pertinent pour les champs des jeux de données du connecteur source Adobe Analytics. Ces champs ont souvent des noms non identifiables et non conviviaux, par exemple `eVar41` ou `prop25`.
* **Utilisez des noms distinctifs**. Les noms distinctifs sont particulièrement pertinents lorsque vous utilisez le même champ en tant que composant de mesure et de dimension dans votre vue de données. Ou bien lorsque vous utilisez un champ dans plusieurs composants du même type (par exemple, dans deux mesures différentes), chacun ayant des paramètres de composant différents.
* **Utilisez une convention de nommage des composants**. Vous pouvez utiliser une convention de nommage des composants pour les regrouper. Par exemple, avec **[!UICONTROL Commandes | Produit]** et **[!UICONTROL Commandes | Clientèle]**, il est possible de distinguer différentes mesures de commande qui peuvent exister dans vos données.
* **Utilisez le dictionnaire de données**. Ajoutez une description et d’autres données pertinentes pour les composants dans le dictionnaire de données. Actuellement, l’agent Data Insights n’utilise pas la description et les balises du dictionnaire de données, mais cela pourrait être le cas à l’avenir.
* **Utilisez des mesures calculées approuvées**. Convenez d’un processus pour n’utiliser que des mesures calculées approuvées en tant que composants dans votre vue de données, et évitez d’utiliser des mesures calculées expérimentales.
* **Partagez les segments obligatoires**. Veillez à partager les segments et à rendre visibles les segments obligatoires pour les prompts de l’agent Data Insights.
* **Normalisez les noms de composant dans les vues de données**. Si vous utilisez les mêmes champs en tant que composant dans plusieurs vues de données, veillez à utiliser un nom convivial unique et un identifiant unique pour ce composant. Un nom et un identifiant uniques permettent à l’agent Data Insights de changer de vue de données sans perte de contexte.

>[!MORELIKETHIS]
>
>[Paramètres de composant](/help/data-views/component-settings/overview.md)
>&#x200B;>[Dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md)
>&#x200B;>[Approuver une mesure calculée](/help/components/calc-metrics/cm-workflow/cm-approving.md)
>&#x200B;>[Partager des segments](/help/components/segments/seg-share.md)
>
