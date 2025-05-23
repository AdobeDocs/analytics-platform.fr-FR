---
description: Comment poser des questions d’analyse des données dans la documentation de Customer Journey Analytics
title: Visualiser les données avec l’agent Data Insights dans Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: bef00aa251831cdb809a6243b5d5a8e2c0dda9bb
workflow-type: tm+mt
source-wordcount: '1872'
ht-degree: 3%

---

# Visualisation des données avec Data Insights Agent dans Customer Journey Analytics

{{release-limited-testing}}

>[!AVAILABILITY]
>
>Data Insights Agent est disponible pour les clients éligibles pendant une durée limitée. L’accès à Data Insights Agent prendra fin le 30 novembre 2025. Pour continuer à utiliser Data Insights Agent sans interruption, contactez votre représentant de compte Adobe pour en savoir plus sur les licences Data Insights Agent.

Data Insights Agent, accessible à partir de l’assistant d’IA dans Customer Journey Analytics, est un agent de conversation d’IA génératif qui répond rapidement et efficacement aux questions sur vos données. Il crée des visualisations pertinentes dans Analysis Workspace à l’aide de composants de votre vue de données et en utilisant vos données réelles.

L’utilisation de Data Insights Agent pour répondre aux questions relatives aux données dans Analysis Workspace peut vous faire gagner un nombre incalculable d’heures que vous pourriez passer à créer manuellement des visualisations dans Analysis Workspace et à vous familiariser avec vos composants de vue de données.

![Agent Data Insights dans l’assistant AI](assets/cja-ai-asst-da.gif)

## Fonctionnalités incluses ou non dans la portée

| Fonctionnalité | Dans la portée | Hors de portée |
| --- | --- | --- |
| **Types de visualisation** | <ul><li>Ligne</li><li>Multiligne</li><li>Tableau à structure libre</li><li>Barre</li><li>Anneau</li><li>Nombre de résumés</li></ul> | <ul><li>Flux</li><li>Abandons</li><li>Table de cohortes</li><li>Aires, Aires empilées</li><li>Barres empilées</li><li>Puces</li><li>Combo</li><li>Histogramme</li><li>Barres horizontales, barres empilées horizontales</li><li>Résumé des mesures clés</li><li>Dispersion</li><li>Synthèse des modifications</li><li>Text</li><li>Plan en arborescence</li><li>Venn</li></ul> |
| **Actions de Workspace et fonctionnalités de l’agent** | <ul><li>Création et mise à jour de visualisations<p>Génère un tableau à structure libre et les visualisations associées (ligne, barre, anneau, etc.).<p>Par exemple, *Quel est le bénéfice sur l’ensemble des SKU de février à mai ?*</p></li><li>Poser des questions de suivi</li><li>Répondre à une invite dans le contexte à partir d’une invite précédente<p>Par exemple :</p> <ul><li>Invite 1 : *Tendance des événements à partir de mars.*</li><li>Invite 2 : *afficher à la place les données de mars à avril*</li></ul> </li><li>Détection d’invite hors de portée<p>Si vous envoyez une invite hors de portée, par exemple *Exporter ce projet*, Data Insights Agent vous informe que la question est hors de portée.</p></li></ul> | <ul><li>Boutons de l’interface utilisateur d’action contextuelle (ajouter au graphique, nouveau panneau, nouveau tableau)</li><li>Partager</li><li>Exporter</li><li>Télécharger</li><li>Gérer les préférences utilisateur</li><li>Traiter</li><li>Gérer la vue de données</li><li>Application Tableaux de bord Analytics</li><li>Attribution</li><li>Résumé ou réponse en ligne<p>Data Insights Agent ne peut pas répondre en ligne dans le rail de conversation avec une réponse récapitulative d’une invite utilisateur. Voici des exemples d’invites hors de portée : *Donnez-moi un résumé des informations de ma dernière invite* et *Résumez les points forts de la visualisation en ligne.*</p></li></ul> |
| **Clarification des questions** | Si vous posez une question à laquelle Data Insights Agent ne peut pas répondre en raison d’un manque de contexte ou si votre question est trop générique, Data Insights Agent vous répond par une question de clarification ou des suggestions d’options. <p>Les questions de clarification suivantes sont des exemples de questions liées aux composants :</p><ul><li>Mesure : *Quelle mesure « chiffre d’affaires » vouliez-vous dire ?*</li><li>Dimension : *Sur laquelle des « régions » ci-dessous voulez-vous vous concentrer ?*</li><li>Segment : *Quel segment de « Compte » vouliez-vous appliquer ?*</li><li>Période : *Par « mois dernier », vouliez-vous dire le dernier mois complet ou les 30 derniers jours ?*</li></ul><p>La question de clarification suivante est un exemple de question liée aux éléments de dimension :</p> <ul><li>Quel « nom de magasin » vouliez-vous dire ? (par exemple, #5274 de magasin, #2949 de magasin, etc.).</li></ul> | Les questions de clarification sont limitées aux composants et aux éléments de dimension. Data Insights Agent ne peut pas clarifier des éléments tels que les vues de données, les visualisations, la granularité des données, la comparaison et la portée. Lorsque des questions de clarification ne peuvent pas être utilisées, l’agent utilise par défaut ce que vous demandez le plus probablement. Si elle renvoie une visualisation ou une granularité de données inattendue, vous pouvez poser une question complémentaire ou ajuster la visualisation et les données. |
| **Vérifiabilité et exactitude des données** | La vérifiabilité et l’exactitude des données peuvent être confirmées en affichant le tableau à structure libre généré et la visualisation des données. <p>Par exemple, si vous demandez à Data Insights Agent d’*Établir la tendance des commandes le mois dernier*, vous pouvez confirmer que la mesure correcte (« commandes ») et la période (« mois dernier ») ont été sélectionnées dans le panneau, la visualisation des données et le tableau à structure libre nouvellement générés. | Data Insights Agent ne répond pas en vous informant des composants ou des visualisations qui ont été ajoutés.</p> |
| **Mécanismes de retour d’informations** | <ul><li>Pouces levés</li><li>Pouces baissés</li><li>Drapeau</li></ul> |  |


## Gestion de l’accès à Data Insights Agent dans Customer Journey Analytics

Les paramètres suivants régissent l’accès à Data Insights Agent dans Customer Journey Analytics :

* **Accès à la solution** : Data Insights Agent est disponible pour tous les clients Customer Journey Analytics dans le cadre d’un programme d’accès limité jusqu’au 30 novembre 2025. Il n’est pas disponible dans Adobe Analytics.

* **Accès contractuel** : si vous ne pouvez pas utiliser Data Insights Agent dans l’assistant AI, contactez l’administrateur ou l’administratrice de votre entreprise ou l’équipe chargée du compte Adobe. Avant que votre entreprise puisse utiliser Data Insights Agent, vous devez accepter certains termes juridiques liés à l’IA générative.

* **Autorisations** : les autorisations nécessaires doivent être accordées dans le [!UICONTROL Adobe Admin Console] pour que les utilisateurs puissent accéder à Data Insights Agent.

  Pour accorder des autorisations, un [administrateur de profil de produit](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit effectuer les étapes suivantes dans l’[!UICONTROL Admin Console] :
   1. Dans **[!UICONTROL Admin Console]**, sélectionnez l’onglet **[!UICONTROL Produits]** pour afficher la page **[!UICONTROL Tous les produits et services]**.
   1. Sélectionnez **[!UICONTROL Customer Journey Analytics]**.
   1. Dans l’onglet **[!UICONTROL Profils de produit]**, sélectionnez le titre du profil de produit pour lequel vous souhaitez fournir un accès à [!UICONTROL Assistant AI : connaissance du produit].
   1. Dans le profil de produit spécifique, sélectionnez l’onglet **[!UICONTROL Autorisations]**.

      ![Onglet Autorisations dans Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Dans la ligne **[!UICONTROL Outils de création de rapports]** du tableau fourni, sélectionnez l’icône de modification ![Modifier](/help/assets/icons/Edit.svg).
   1. Faites défiler l’écran jusqu’à ou recherchez **[!UICONTROL Assistant IA : connaissance du produit]**, puis sélectionnez l’icône plus ![Ajouter un cercle](/help/assets/icons/AddCircle.svg) en regard de cette autorisation.

      L’autorisation **[!UICONTROL Assistant AI : Connaissance des produits]** est ajoutée à la colonne **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions.png).

   1. Sélectionnez l’onglet **[!UICONTROL Outils de vues de données]**, puis sélectionnez l’icône plus ![AddCircle](/help/assets/icons/AddCircle.svg) en regard de l’autorisation **[!UICONTROL Data Insights Agent]**.

      L&#39;autorisation **[!UICONTROL Data Insights Agent]** est ajoutée à la colonne **[!UICONTROL Éléments d&#39;autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions-dataviewtools.png).

   1. Sélectionnez l’onglet **[!UICONTROL Vues de données]** pour choisir les vues de données à activer pour Data Insights Agent.

      >[!IMPORTANT]
      >
      >Le Data Insights Agent peut référencer les vues de données incluses à un moment donné le jour même de leur activation dans Admin Console.

   1. Recherchez ou accédez aux vues de données à activer, puis sélectionnez l’icône plus ![AddCircle](/help/assets/icons/AddCircle.svg) en regard du nom de chaque vue de données.

      Chaque vue de données ajoutée est visible dans la colonne **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions-dataviews.png).

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

  Pour plus d’informations sur le contrôle d’accès, voir [ Contrôle d’accès ](/help/technotes/access-control.md#access-control).

## Accès à Data Insights Agent dans l’assistant d’IA

1. Accédez à [experience.adobe.com](https://experience.adobe.com/) et connectez-vous avec votre Adobe ID.

2. Sélectionnez **Customer Journey Analytics** sur la page d’accueil Experience Cloud.

3. Sélectionnez **[!UICONTROL Projet vierge]** dans la bannière en haut de la page des projets pour ouvrir un nouveau projet vierge.

4. Assurez-vous que la vue de données sélectionnée pour le panneau est une vue de données activée pour une utilisation avec Data Insights Agent, comme décrit dans la section [Gérer l’accès à Data Insights Agent dans Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Sélectionnez l’icône de conversation de l’assistant AI dans la zone supérieure droite de la page.

   Si vous ne voyez pas l’icône de conversation, contactez votre administrateur afin qu’il puisse activer les fonctionnalités suivantes dans Admin Console :

   * Outils de création de rapports : **[!UICONTROL Assistant IA : Connaissance des produits]**

   * Outils De Vue De Données : **[!UICONTROL Data Insights Agent]**

   Pour plus d’informations, voir [Gérer l’accès à Data Insights Agent dans Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Icône de l’assistant AI](/help/assets/ai-asst-icon.png)

6. Dans la boîte de dialogue **[!UICONTROL Demandez à propos de Customer Journey Analytics]** au bas de la page, posez une question sur la visualisation des données à l’aide de Data Insights Agent.

   Pour plus d’informations, consultez les exemples suivants.

### Exemple 1

Supposons, par exemple, que vous soyez intéressé par les commandes que votre entreprise a reçues en juillet.

**Invite:** Saisissez *« Tendance des commandes en juillet. »*

![invite AI](/help/assets/ai-asst-prompt1.png)

**Réponse :** Data Insights Agent collecte des informations en examinant les données de la vue de données, y compris les mesures et les composants. Cela traduit l’invite en dimensions et mesures appropriées dans la plage de données.

Comme vous pouvez le constater, il a généré automatiquement un graphique linéaire et un tableau à structure libre pour afficher les commandes pour juillet.

![Réponse à l’invite - graphique linéaire et tableau à structure libre](/help/assets/ai-asst-result.png)

### Exemple 2

Ensuite, vous devez comparer vos revenus par région.

**Invite :** dans la fenêtre d’invite, saisissez *« Afficher le chiffre d’affaires par région »*

**Réponse :** Data Insights Agent comprend intelligemment que par « région », vous voulez dire « région du client ». Il génère un graphique à barres qui présente le mieux les recettes par région :

![Graphique à barres](/help/assets/ai-asst-result2.png)

### Exemple 3

Ensuite, en plus de comprendre le chiffre d’affaires par région, vous souhaitez également afficher les données de bénéfice par région. Au lieu de répéter l’invite précédente, vous pouvez demander à Data Insights Agent de mettre à jour le tableau à structure libre et de visualisation le plus récent.

**Invite :** dans la fenêtre d’invite, saisissez *« Ajouter un bénéfice »*

**Réponse :** le graphique **[!UICONTROL Barres]** fournit toujours la réponse la plus concise, mais la mesure de profit a été ajoutée sous la forme d’une colonne dans le tableau à structure libre :

![Graphique à barres](/help/assets/ai-asst-result4.png)

### Exemple 4

Enfin, examinons les recettes par catégorie de produits.

**Invite :** dans la fenêtre d’invite, saisissez *« Proportion du chiffre d’affaires par catégorie de produits ».*

**Réponse :** encore une fois, Data Insights Agent sélectionne la visualisation la plus appropriée, dans ce cas la visualisation **[!UICONTROL en anneau]**, pour répondre à la question.

![Anneau](/help/assets/ai-asst-result3.png)

## Exemples d’invites de visualisation de données

Vous trouverez ci-dessous quelques exemples d’invites courantes et des visualisations utilisées par Data Insights Agent pour répondre à ces invites.

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

Data Insights Agent traite le contexte fourni par chaque invite utilisateur et tente de répondre intelligemment avec la visualisation et les composants les plus appropriés dans un tableau à structure libre.

Les réponses peuvent varier en fonction des mots et expressions spécifiques utilisés dans l’invite, et de légères modifications de la langue peuvent entraîner des résultats différents.

Pour obtenir les meilleurs résultats, tenez compte des recommandations suivantes :

* **Soyez précis :** incluez des termes exacts pour réduire la réponse. Voici un exemple d’invite spécifique : « Ventes du mois dernier en Californie »

* **Utiliser des mesures, des dimensions et des segments clairs :** l’ajout de mesures spécifiques (telles que « Chiffre d’affaires »), de dimensions (telles que « nom du site web »), de segments (tels que « utilisateurs d’iPhone ») et de périodes (telles que « trois derniers mois ») permet à Data Insights Agent de se concentrer sur les données appropriées.

* **Poser des questions directes :** le fait de poser des questions directement permet à Data Insights Agent de fournir plus facilement des informations claires et pertinentes. Voici un exemple de question directe dans une invite : « Quel est le chiffre d’affaires moyen par catégorie de produits cette année ? »

Consultez le tableau ci-dessous pour obtenir des exemples de termes et d’expressions que vous pouvez utiliser dans les invites avec Data Insights Agent, ainsi que les types de réponses attendus.

Ces exemples sont conçus pour vous aider à vous familiariser avec la manière dont des mots ou des structures spécifiques peuvent influencer la sortie de l’agent Data Insight, afin de garantir des informations plus précises et plus précieuses. Data Insights Agent utilise l’IA générative, de sorte que les visualisations ou les données sélectionnées peuvent varier légèrement entre des invites similaires.

| Résultat souhaité | Exemples de termes et d’expressions |
| --- | --- |
| Visualisation Synthèse des chiffres | <ul><li>Total</li></ul> |
| Comparer les composants | <ul><li>Comparer</li><li>VS</li><li>Contraste</li><li>Semaine par semaine</li><li>Mois par mois</li><li>Trimestre par trimestre</li><li>D&#39;une année sur l&#39;autre</li></ul> |
| Visualisation en anneau | <ul><li>Proportion</li><li>Part de</li><li>Répartition</li><li>Pourcentage</li><li>Contribution</li><li>Partie</li><li>Parties</li></ul> |
| Visualisation sous forme de lignes | <ul><li>Tendance</li><li>[Mesure] dans [Période]</li></ul> |
| Visualisation sous forme de barres | <ul><li>[Mesure] par [Dimension]</li></ul> |

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

