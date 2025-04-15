---
description: Comment poser des questions d’analyse des données dans la documentation de Customer Journey Analytics
title: Visualiser les données avec l’agent Data Insights dans Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: ab78583eb36d6158630724fbab9eb8148bcdbe23
workflow-type: tm+mt
source-wordcount: '1878'
ht-degree: 3%

---

# Visualiser les données avec l’agent Data Insights dans Customer Journey Analytics

L’agent Data Insights, qui fait partie de l’assistant d’IA dans Customer Journey Analytics, est un agent de conversation d’IA génératif qui répond rapidement et efficacement aux questions sur vos données. Il crée des visualisations pertinentes dans Analysis Workspace à l’aide de composants de votre vue de données et en utilisant vos données réelles.

L’utilisation de l’agent Data Insights pour répondre aux questions relatives aux données dans Analysis Workspace peut vous permettre de gagner d’innombrables heures que vous pourriez passer à créer manuellement des visualisations dans Analysis Workspace et à vous familiariser avec vos composants de vue de données.

![Agent Data Insights dans l’assistant AI](assets/cja-ai-asst-da.gif)

## Fonctionnalités incluses ou non dans la portée de l’application Beta

### Fonctionnalités de Beta intégrées

| Fonctionnalité prise en charge | Description |
| --- | --- |
| **Création et mise à jour de visualisations** | Génère un tableau à structure libre et les visualisations associées (ligne, barre, anneau, etc.).<p>Exemple : *Quel est le bénéfice sur l’ensemble des SKU de février à mai ?* |
| **Types de visualisation pris en charge** | <ul><li>Ligne</li><li>Multiligne</li><li>Tableau à structure libre</li><li>Barres</li><li>Anneau</li><li>Nombre de résumés</li></ul> |
| **Détection d’invite hors de portée** | Si vous envoyez une invite qui est hors de portée, telle que « exporter ce projet », l’agent Data Insights répond en vous informant que la question est hors de portée. |
| **Clarification des questions** | Si vous posez une question à laquelle l’agent Data Insights ne peut pas répondre en raison d’un contexte suffisant ou si elle est trop générique, l’agent Data Insights répond par une question de clarification ou des options suggérées. Exemples : <p>**Composants**<ul><li>Mesure : *Quelle mesure « chiffre d’affaires » vouliez-vous dire ?*</li><li>Dimension : *Sur laquelle des « régions » ci-dessous voulez-vous vous concentrer ?*</li><li>Filtre : *Quel segment de « Compte » vouliez-vous appliquer ?*</li><li>Période : *Par « mois dernier », vouliez-vous dire le dernier mois complet ou les 30 derniers jours ?*</li></ul>**Éléments de Dimension** : de quel « nom de magasin » parlez-vous ? (par exemple, #5274 de magasin, #2949 de magasin, etc.). |
| **Multi-tour** | L’agent Data Insights répond à une invite avec le contexte de toutes les invites précédentes, ce qui permet aux utilisateurs et utilisatrices de mettre à jour les visualisations et de poser des questions de suivi. Exemple : <ul><li>Invite 1 : *Tendance des événements à partir de mars.*</li><li>Invite 2 : *afficher à la place les données de mars à avril*</li></ul> |
| **Vérifiabilité** | La vérifiabilité et l’exactitude des données peuvent être confirmées via le tableau à structure libre généré et la visualisation des données. Par exemple, si un utilisateur demande *Tendance des commandes le mois dernier*, vous pouvez confirmer que la mesure correcte (« commandes ») et la période (« mois dernier ») ont été sélectionnées dans le panneau, la visualisation des données et le tableau à structure libre nouvellement générés. |
| **Commentaires** | <ul><li>Pouces levés</li><li>Pouces baissés</li><li>Drapeau</li></ul> |

### Fonctionnalités de Beta hors de portée

| Fonction non prise en charge | Description |
| --- | --- |
| **Résumé ou réponse en ligne** | L’agent Data Insights ne peut pas répondre en ligne dans le rail de conversation avec une réponse récapitulative d’une invite utilisateur. Exemples d’invites hors de portée :<ul><li>*Donnez-moi un résumé des informations de ma dernière invite.*</li><li>*Résumer les points forts de la visualisation Ligne.*</li></ul> |
| **Clarification des questions** | Les questions de clarification sont limitées aux composants et aux éléments de dimension. L’agent Data Insights ne peut pas clarifier des éléments tels que les vues de données, les visualisations, la granularité des données, la comparaison et la portée. Lorsque des questions de clarification ne peuvent pas être utilisées, l’agent utilise par défaut ce que vous demandez le plus probablement. Si elle renvoie une visualisation ou une granularité de données inattendue, vous pouvez ensuite utiliser la fonctionnalité multi-tour / mise à jour pour ajuster la visualisation et les données. |
| **Actions/fonctionnalités Workspace** | L’agent Data Insights ne peut pas agir sur un utilisateur dans Workspace en dehors de la création et de la mise à jour de visualisations. Par exemple, il ne peut effectuer aucune des opérations suivantes :<ul><li>Boutons de l’interface utilisateur d’action contextuelle (ajouter au graphique, nouveau panneau, nouveau tableau)</li><li>Partager</li><li>Exporter</li><li>Télécharger</li><li>Gérer les préférences utilisateur</li><li>Traiter</li><li>Gérer la vue de données</li><li>Application Tableaux de bord Analytics</li><li>Attribution</li></ul> |
| **Types de visualisation non pris en charge** | <ul><li>Flux</li><li>Abandon</li><li>Tableau de cohortes</li><li>Aires, Aires empilées</li><li>Barres empilées</li><li>Puce</li><li>Combo</li><li>Histogramme</li><li>Barres horizontales, barres empilées horizontales</li><li>Résumé des mesures clés</li><li>Dispersion</li><li>Synthèse des modifications</li><li>Text</li><li>Plan en arborescence</li><li>Venn</li></ul> |

## Gérer l’accès à l’agent Data Insights dans Customer Journey Analytics

Les paramètres suivants régissent l’accès à l’agent Data Insights dans Customer Journey Analytics :

* **Accès à la solution** : l’agent Data Insights est disponible pour les clients Customer Journey Analytics Prime et Ultimate. Il n’est pas disponible dans Adobe Analytics.

* **Accès contractuel** : si vous ne pouvez pas utiliser l’agent Data Insights dans l’assistant AI, contactez l’administrateur ou l’administratrice de votre entreprise ou le représentant ou représentante de compte Adobe. Avant que votre organisation puisse utiliser l’agent Data Insights, vous devez accepter certains termes juridiques liés à GenAI.

* **Autorisations** : dans [!UICONTROL Adobe Admin Console], l’autorisation [!UICONTROL Outils de création de rapports] **[!UICONTROL Assistant AI : Visualisation des données]** détermine l’accès à cet outil. Un [administrateur de profil de produit](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) doit suivre les étapes suivantes dans l’[!UICONTROL Admin Console] :
   1. Accédez à **[!UICONTROL Admin Console]** > **[!UICONTROL Produits et services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Profils de produit]**
   1. Sélectionnez le titre du profil de produit pour lequel vous souhaitez fournir un accès à [!UICONTROL Assistant AI : connaissance du produit].
   1. Dans le profil de produit spécifique, sélectionnez **[!UICONTROL Autorisations]**.
   1. Sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier **[!UICONTROL Outils de reporting]**.
   1. Sélectionnez ![AjouterCercle](/help/assets/icons/AddCircle.svg) pour ajouter **Assistant AI : Connaissance des produits** et **Assistant AI : Analyse des données** à **[!UICONTROL Éléments d’autorisation inclus]**.

      ![Ajouter une autorisation](assets/ai-assistant-permissions.png).

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les autorisations.

Voir [Contrôle d’accès](/help/technotes/access-control.md#access-control) pour plus d’informations.

## Accéder à l’agent Data Insights dans l’assistant d’IA

1. Accédez à [experience.adobe.com](https://experience.adobe.com/) et connectez-vous avec votre Adobe ID.

2. Sélectionnez **Customer Journey Analytics** sur la page d’accueil Experience Cloud.

3. Sélectionnez **[!UICONTROL Projet vierge]** dans la bannière en haut de la page des projets pour ouvrir un nouveau projet vierge.

4. Assurez-vous que la vue de données sélectionnée pour le panneau est identique à la vue de données activée pour une utilisation avec l’agent Data Insights pour le test Beta.

   Si vous n’êtes pas sûr, contactez le canal Beta Slack.

5. Sélectionnez l’icône de conversation de l’assistant AI dans la zone supérieure droite de la page.

   Si vous ne voyez pas l’icône de conversation, contactez votre administrateur afin qu’il puisse activer les fonctionnalités suivantes dans Admin Console :

   * **[!UICONTROL Assistant IA : connaissance des produits]**

   * **[!UICONTROL Assistant IA : analyse des données]**

   Pour plus d’informations, les administrateurs peuvent consulter [ces instructions](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![Icône de l’assistant AI](/help/assets/ai-asst-icon.png)

6. Dans la boîte de dialogue **[!UICONTROL Demandez à propos de Customer Journey Analytics]** au bas de la page, posez une question sur la visualisation des données à l’aide de l’agent Data Insights.

   Pour plus d’informations, consultez les exemples suivants.

### Exemple 1

Supposons, par exemple, que vous soyez intéressé par les commandes que votre entreprise a reçues en juillet.

**Invite:** Saisissez *« Tendance des commandes en juillet. »*

![invite AI](/help/assets/ai-asst-prompt1.png)

**Réponse :** l’agent Data Insights collecte des informations en examinant les données de la vue de données, y compris les mesures et les composants. Cela traduit l’invite en dimensions et mesures appropriées dans la plage de données.

Comme vous pouvez le constater, il a généré automatiquement un graphique linéaire et un tableau à structure libre pour afficher les commandes pour juillet.

![Réponse à l’invite - graphique linéaire et tableau à structure libre](/help/assets/ai-asst-result.png)

### Exemple 2

Ensuite, vous devez comparer vos revenus par région.

**Invite :** dans la fenêtre d’invite, saisissez *« Afficher le chiffre d’affaires par région »*

**Réponse :** l’agent Data Insights comprend intelligemment que par « région », vous voulez dire « région du client ». Il génère un graphique à barres qui présente le mieux les recettes par région :

![Graphique à barres](/help/assets/ai-asst-result2.png)

### Exemple 3

Ensuite, en plus de comprendre le chiffre d’affaires par région, vous souhaitez également afficher les données de bénéfice par région. Au lieu de répéter l’invite précédente, vous pouvez demander à l’agent Data Insights de mettre à jour le tableau à structure libre et de visualisation le plus récent.

**Invite :** dans la fenêtre d’invite, saisissez *« Ajouter un bénéfice »*

**Réponse :** le graphique **[!UICONTROL Barres]** fournit toujours la réponse la plus concise, mais la mesure de profit a été ajoutée sous la forme d’une colonne dans le tableau à structure libre :

![Graphique à barres](/help/assets/ai-asst-result4.png)

### Exemple 4

Enfin, examinons les recettes par catégorie de produits.

**Invite :** dans la fenêtre d’invite, saisissez *« Proportion du chiffre d’affaires par catégorie de produits ».*

**Réponse :** nouveau, l’agent Data Insights sélectionne la visualisation la plus appropriée, dans ce cas la visualisation **[!UICONTROL en anneau]**, pour répondre à la question.

![Anneau](/help/assets/ai-asst-result3.png)

## Exemples d’invites de visualisation de données

Vous trouverez ci-dessous quelques exemples d’invites courantes et des visualisations utilisées par l’agent Data Insights pour répondre à ces invites.

| Exemple d’invite | Visualisation attendue |
| --- | --- |
| Afficher les bénéfices en [mois] | Ligne<p>Demander une tendance ou une mesure au cours d’une certaine période par défaut renvoie une visualisation en lignes. |
| Tendance des commandes en [mois] | Ligne |
| Afficher le chiffre d’affaires par région en [mois] | Barres |
| Part des revenus par catégorie de produits | Anneau |
| Commandes par jour de la semaine, de janvier à mai | Barres |
| Afficher les commandes par genre, de mars à juin | Barres |
| Quel est le bénéfice entre les SKU de février à mai ? | Barres |
| Chiffre d’affaires par nom de magasin dans [Mois] | Barres |
| Quels ont été mes 10 principaux SKU par bénéfice au cours du [Mois] ? | Barres |
| Proportion d&#39;achats par mois de l&#39;année | Anneau |
| Bénéfice total en [mois] | Synthèse des chiffres<p>Demander le « total » d’une mesure sur une certaine période doit renvoyer une visualisation Synthèse des chiffres. |


## Bonnes pratiques en matière de promotion

L’agent Data Insights traite le contexte fourni par chaque invite utilisateur et tente de répondre intelligemment avec la visualisation et les composants les plus appropriés dans un tableau à structure libre.

Les réponses peuvent varier en fonction des mots et expressions spécifiques utilisés dans l’invite, et de légères modifications de la langue peuvent entraîner des résultats différents.

Pour obtenir les meilleurs résultats, tenez compte des recommandations suivantes :

* Soyez précis : incluez des termes exacts pour réduire la réponse. Voici un exemple d’invite spécifique : « Ventes du mois dernier en Californie »

* Utiliser des mesures et des segments clairs : l’ajout de mesures spécifiques (telles que « Chiffre d’affaires »), de dimensions (telles que « nom du site web »), de segments (tels que « utilisateurs d’iPhone ») et de périodes (telles que « trois derniers mois ») permet au Data Insights Agent de se concentrer sur les données appropriées.

* Poser des questions directes : la formulation directe des questions permet à l’agent Data Insights de fournir plus facilement des informations claires et pertinentes. Voici un exemple de question directe dans une invite : « Quel est le chiffre d’affaires moyen par catégorie de produits cette année ? »

Consultez le tableau suivant d’exemples de termes et d’expressions que vous pouvez utiliser dans les invites avec l’agent Data Insights, ainsi que les types de réponses attendus.

Ces exemples sont conçus pour vous aider à vous familiariser avec la manière dont des mots ou des structures spécifiques peuvent influencer la sortie de l’agent Data Insight, afin de garantir des informations plus précises et plus précieuses. L’agent Data Insights utilise l’IA générative, de sorte que les visualisations ou les données sélectionnées peuvent varier légèrement selon des invites similaires.

| Résultat souhaité | Exemples de termes et d’expressions |
| --- | --- |
| Visualisation Synthèse des chiffres | <ul><li>Total</li></ul> |
| Comparer les composants | <ul><li>Comparer</li><li>VS</li><li>Contraste</li><li>Semaine par semaine</li><li>Mois par mois</li><li>Trimestre par trimestre</li><li>D&#39;une année sur l&#39;autre</li></ul> |
| Visualisation en anneau | <ul><li>Proportion</li><li>Part de</li><li>Répartition</li><li>Pourcentage</li><li>Contribution</li><li>Partie</li><li>Parties</li></ul> |
| Visualisation sous forme de lignes | <ul><li>Tendance</li><li>[Mesure] dans [Période]</li></ul> |
| Visualisation sous forme de barres | <ul><li>[Mesure] par [Dimension]</li></ul> |

## Attentes en matière de test Beta et commentaires demandés

Après avoir posé chaque question, examinez attentivement la réponse fournie par l&#39;assistant. Il est essentiel d’évaluer entièrement les visualisations générées avant de fournir des commentaires.

Tenez compte des points suivants lors de l’évaluation d’une réponse de l’agent Data Insights :

* Réponse du rail de conversation ou modèle : évaluez la réponse textuelle fournie. La réponse est-elle appropriée compte tenu du contexte de votre invite ?

* Visualisation/graphique : permet d’évaluer la visualisation. S’agit-il de la visualisation appropriée ou attendue pour votre question, ou vous attendiez-vous à une visualisation différente ?

* Tableau à structure libre : permet d’évaluer le tableau à structure libre. Les données du tableau à structure libre sont-elles correctes ? Ventilez-vous les données là où elles sont demandées? Les segments appliqués sont-ils ceux que vous avez demandés ou attendus ?

* Message d’erreur / Hors-portée : si un message d’erreur générique indiquant que la question est hors de portée est fourni, indiquez si vous pensez que le message de hors-portée est approprié, compte tenu de votre invite. Votre invite était-elle vraiment dans la portée ?

**Pour chaque réponse, donnez un pouce vers le haut ou un pouce vers le bas, en fonction de la réponse.**

Après la sélection des pouces vers le haut ou vers le bas, veuillez effectuer une sélection pour les champs de commentaires à sélection multiple pertinents. Si vous souhaitez fournir des commentaires supplémentaires, ajoutez des notes dans la zone de texte ouverte.

## Questions et contact

* Envoyez vos questions et commentaires sur le canal Beta Slack : #data-insights-agent-in-cja-beta
