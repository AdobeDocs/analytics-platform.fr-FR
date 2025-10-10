---
title: Paramètres de composant
description: Affichez les paramètres principaux d’un composant de vue de données.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: aa635d52007a3032d8c3f90a779d1b70213dee9e
workflow-type: tm+mt
source-wordcount: '3738'
ht-degree: 55%

---

# Paramètres de composant {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Paramètres de composant"
>abstract="Affichez et configurez le nom, la description et d’autres paramètres associés à un composant. Cochez cette case pour masquer ce composant aux utilisateurs et utilisatrices ne faisant pas partie de l’équipe d’administration dans les rapports. Les administrateurs et les administratrices peuvent toujours accéder au composant en sélectionnant **[!UICONTROL Afficher tous les composants]** dans un projet Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Libellés de contexte"
>abstract="La suppression d’un libellé de contexte peut avoir un impact sur des panneaux ou des rapports spécifiques lorsque le composant est requis."

<!-- markdownlint-enable MD034 -->


Les informations suivantes décrivent les paramètres utilisés par un composant de vue de données.

![Paramètres des composants décrits dans cette section](../assets/component-settings.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Type de composant] | Obligatoire. Permet de modifier un composant de Mesure en Dimension ou inversement. La modification de la sélection de cette liste déroulante déplace le composant vers sa zone de composants incluse respective. |
| [!UICONTROL  Nom du composant ] | Obligatoire. Permet de définir le nom convivial qui apparaîtra dans Analysis Workspace. Vous pouvez renommer un composant pour lui donner un nom spécifique à la vue de données. |
| [!UICONTROL Description] | Facultatif, mais recommandé. Fournit des informations sur le composant à d’autres utilisateurs. |
| [!UICONTROL Balises] | Facultatif. Permet de baliser le composant avec des balises personnalisées ou prêtes à l’emploi pour faciliter la recherche/le filtrage dans l’interface utilisateur d’Analysis Workspace. |
| [!UICONTROL Libellés de contexte] | Facultatif. Menu déroulant des libellés [contextuels](#context-labels) définis par le système disponibles pouvant être appliqués à un composant. |
| [!UICONTROL Nom du champ de schéma] | Nom du champ de schéma. |
| [!UICONTROL Type de jeu de données] | Obligatoire. Champ non modifiable qui indique le type de jeu de données (événement, recherche ou profil) dʼoù provient le composant. |
| [!UICONTROL Jeu de données] | Champ non modifiable indiquant le jeu de données d’où provient le composant. Ce champ peut contenir plusieurs jeux de données. |
| [!UICONTROL Type de schéma] | Champ non modifiable affichant le type de données du composant. Alors que vous pouvez utiliser n’importe quel type de champ de schéma pris en charge dans Platform, tous les types de champs ne sont pas pris en charge dans Customer Journey Analytics. Les types de données pris en charge sont les suivants : `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` et `Boolean`. Seul le type de données de schéma `String` est actuellement autorisé dans les jeux de données de recherche. |
| [!UICONTROL ID du composant] | Obligatoire. Lʼ[API Customer Journey Analytics](https://www.adobe.io/cja-apis/docs) utilise ce champ pour référencer le composant. Chaque composant d’une vue de données doit être unique. Adobe génère automatiquement un identifiant pour chaque composant ; vous pouvez toutefois cliquer sur l’icône de modification et modifier l’identifiant du composant. La modification de cet identifiant de composant rompt tous les projets Workspace existants qui contiennent ce composant. Bien que chaque composant ait besoin d’un identifiant unique dans une seule vue de données, vous pouvez utiliser le même identifiant de composant dans d’autres vues de données. Si vous utilisez le même ID de composant dans d’autres vues de données, vous pouvez rendre les projets Workspace compatibles entre les vues de données. <br/>Pour les composants basés sur un profil et une recherche, l’ID du composant comporte un préfixe d’ID basé sur l’ID du jeu de données (par exemple : `642b28fcc1f0ee1c074265a0.person.name.firstName`). Lorsque vous souhaitez réutiliser un composant basé sur un profil ou une recherche, comme `person.name.firstName`, dans votre projet Workspace, et configurer ce composant dans différentes vues de données, assurez-vous de renommer l’ID de composant de manière unique (par exemple, `myUniqueID.person.name.firstName`) dans vos vues de données. |
| [!UICONTROL Chemin d’accès] | Obligatoire. Champ non modifiable qui indique le chemin dʼaccès du schéma dʼoù provient le composant. |
| [!UICONTROL Libellés d’utilisation des données] | Tout libellé d’utilisation des données attribué à ce composant dans Adobe Experience Platform. [En savoir plus](/help/data-views/data-governance.md). |
| [!UICONTROL Masquer le composant dans le reporting] | Permet de traiter le composant en dehors de la vue de données pour les non-administrateurs. Les administrateurs peuvent toujours y accéder en cliquant sur [!UICONTROL Afficher tous les composants] dans un projet Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Paramètres du type de composant](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Étiquettes de contexte

Les libellés de contexte sont des balises définies par le système appliquées aux composants dans une vue de données. Lorsque des libellés de contexte sont appliqués aux composants (dimension ou mesures), Customer Journey Analytics a pour instruction d’utiliser automatiquement ces composants libellés de contexte dans certaines visualisations ou fonctionnalités.

Les libellés de contexte vous permettent de fournir un contexte sémantique à des éléments de données individuels.  En règle générale, Customer Journey Analytics n’a pas besoin de connaître la signification sémantique d’une dimension ou d’une mesure pour effectuer son analyse.  Cependant, certaines situations (modèles de projet et quelques visualisations sélectionnées) nécessitent que Customer Journey Analytics comprenne la signification sémantique pour effectuer un certain type d’analyse. Des libellés de contexte sont créés pour ces situations.

Les libellés de contexte fonctionnent au niveau du composant (dimension ou mesure) et permettent une grande flexibilité dans la vue de données pour le client. Par exemple, vous pouvez attribuer un libellé de contexte à une dimension après avoir appliqué plusieurs transformations de post-traitement à un champ. Ou même à une dimension basée sur un champ dérivé.  Les libellés de contexte fournissent une couche d’abstraction par-dessus les composants et les champs.

Pour des raisons de commodité, les libellés de contexte par défaut intelligents sont appliqués automatiquement aux composants en fonction des champs avec un chemin XDM spécifique. Par exemple, le libellé de contexte **[!UICONTROL Commerce : Catégorie de produits]** est automatiquement appliqué à une dimension **[!UICONTROL Nom de la catégorie]** basée sur le chemin d’accès au schéma `productListItems.productCategories.categoryName`. Vous pouvez toutefois déplacer le libellé de contexte vers un autre composant sans problème.

Pour rationaliser les modèles de projet fournis par Adobe, plusieurs intégrations (telles que Journey Optimizer, Content Analytics, etc.) configurent des vues de données dans lesquelles les composants prêts à l’emploi sont construits d’une manière spécifique. Les libellés de contexte appropriés sont automatiquement appliqués. Là encore, vous pouvez simplement déplacer l’un de ces libellés de contexte vers d’autres composants créés dans la vue de données et votre composant personnalisé est utilisé à la place.

Les libellés de contexte sont également pertinents pour la divulgation des modèles de projet. Les modèles de projet forment rapidement la base de création de rapports pour plusieurs cas d’utilisation spécifiques différents. Cependant, tous les modèles n’ont pas de sens pour toutes les vues de données et vous ne souhaitez pas afficher les modèles non applicables. Les libellés de contexte sont utilisés pour afficher les modèles en fonction de l’inclusion ou non des libellés de contexte dans la vue de données sélectionnée.  Vous pouvez simplement ajouter d’autres libellés de contexte à votre vue de données (composants) pour que d’autres modèles soient disponibles. Vous pouvez également supprimer les libellés de contexte pour masquer des modèles spécifiques.

>[!NOTE]
>
>Vous pouvez appliquer plusieurs libellés de contexte à un composant, mais vous ne pouvez pas appliquer un seul libellé de contexte à plusieurs composants dans une vue de données.
>

Les avantages des libellés de contexte sont les suivants :

* **Convivialité** : il n’est pas nécessaire de sélectionner à nouveau le même composant dans chaque panneau ou visualisation.
* **Déverrouille la fonctionnalité** : certaines visualisations (telles que [Carte](/help/analysis-workspace/visualizations/map.md)) nécessitent des connaissances sur le composant associé à la latitude et à la longitude. L’attribution de libellés de contexte affiche ces informations dans la visualisation.
* **Cohérence** : tous les membres de votre organisation qui travaillent sur un ou plusieurs projets basés sur une vue de données qui utilise des libellés de contexte adoptent le même comportement.
* **Visibilité des fonctionnalités et des modèles** : certaines visualisations et fonctionnalités n’apparaissent que lorsque le libellé de contexte approprié est attribué. Par exemple :

   * Une visualisation [Carte](/help/analysis-workspace/visualizations/map.md) ne s’affiche correctement que lorsque Customer Journey Analytics sait quels composants représentent la latitude et la longitude.
   * Des [modèles](/help/analysis-workspace/templates/use-templates.md) spécifiques ne sont visibles que lorsque les libellés de contexte corrects sont appliqués et que les composants associés sont disponibles.

Des libellés de contexte peuvent être requis dans les cas suivants :

* Pour définir un ensemble de composants, vous pouvez utiliser dans les rapports d’expérience à l’aide du [panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md) dans les projets Analysis Workspace.

  Pour plus d’informations, voir [Intégrer à Journey Optimizer](/help/integrations/ajo.md#data-view) et [Rapports Target](/help/integrations/at.md).

* Pour définir un ensemble de composants, vous pouvez utiliser dans la visualisation [Carte](/help/analysis-workspace/visualizations/map.md) des projets Analysis Workspace.

  Pour plus d’informations, voir [Ajouter des libellés de contexte dans les vues de données](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) dans [Mapper](/help/analysis-workspace/visualizations/map.md).

  **Remarque** : la visualisation des cartes est en phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement.

* Pour afficher les [modèles fournis par Adobe](/help/analysis-workspace/templates/use-templates.md). Certains modèles fournis par Adobe peuvent ne pas fonctionner, car certains composants ne figurent pas dans votre vue de données.

  Pour chaque composant manquant, un libellé de contexte correspondant est disponible dans votre vue de données. Vous devez ajouter le libellé de contexte correspondant à un composant qui se trouve déjà dans votre vue de données. Ou vous devez ajouter un nouveau composant à votre vue de données et ajouter le libellé de contexte au composant (s’il n’est pas déjà fourni automatiquement).

  Pour plus d’informations, voir [Ajouter les composants manquants à la vue de données d’un modèle donné](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) dans l’article [Créer et gérer des modèles](/help/analysis-workspace/templates/create-templates.md).


Les groupes de libellés de contexte suivants sont disponibles, chacun avec une liste de libellés de contexte spécifiques.

+++ Campagne

| Nom | Description |
|------|-------------|
| Code de suivi | Code de suivi. |
| Instances de code de suivi | Instances de code de suivi. |

+++

+++ Commerce

| Nom | Description |
|------|-------------|
| Ajouts au panier | Ajouts au panier |
| Ouvertures de panier | Le panier s’ouvre. |
| Retraits du panier | Retraits du panier |
| Consultations du panier | Consultations du panier |
| Passages en caisse | Paiements. |
| Commandes | Commandes. |
| Produit | Produit. |
| Catégorie de produits | Catégorie de produits. |
| Vues de produit | Consultations de produit. |
| Chiffre dʼaffaires | Chiffre d’affaires. |
| Magasin | Stocker. |
| Unités | Unités. |

+++

+++ Expérimentation

| Nom | Description |
|------|-------------|
| Expérience d’expérimentation | Une expérience est un ensemble de variations d’une expérience qui ont été présentées aux utilisateurs finaux afin de déterminer laquelle il est préférable de conserver à perpétuité. |
| Variante d’expérimentation | La variante est l’une de deux, ou plusieurs, modifications de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. |

+++

+++ Média

| Nom | Description |
|------|-------------|
| Identifiant de contenu | Identifiant du contenu. |
| Temps passé sur le contenu | Durée du contenu. |
| Épisode | Épisode. |
| Type d’événement | Type d’événement. |
| Passé sur le média | Durée du média. |
| Saison | Saison. |
| Secondes depuis le dernier appel | Secondes Depuis Le Dernier Appel. |
| Programme | Afficher. |
| Temps jusqu’au début | Heure de début. |
| Durée totale de la mémoire tampon | Durée totale de la mémoire tampon. |
| Durée totale de pause | Durée totale de pause. |
| Durée de la vidéo | Durée de la vidéo. |
| Nom de la vidéo | Nom de la vidéo. |

+++

+++ Centre d’appel

| Nom | Description |
|------|-------------|
| Nom du centre d’appel | Nom du centre d’appel. |
| Coûts des appels | Frais d&#39;appel. |
| Heures d’appel | Heures d’appel. |
| Durée de l’appel | Durée de l’appel. |
| Raison de lʼappel | Raison de l’appel. |
| Score de l’enquête sur les appels | Score de l’enquête d’appel. |
| Appels | Appels. |

+++

+++ Démographie

| Nom | Description |
|------|-------------|
| Genre | Sexe. |

+++

+++ Environnement

| Nom | Description |
|------|-------------|
| Navigateur | Navigateur. |
| Type de navigateur | Type de navigateur. |
| Langue | Langue. |
| Système d’exploitation | Système d’exploitation. |
| Groupe du système d’exploitation | Groupe de systèmes d’exploitation. |
| Nom du système d’exploitation | Nom du système d’exploitation. |

+++

+++ Général

| Nom | Description |
|------|-------------|
| Nom de l’action | Nom de l’action. |
| Actions | Actions. |
| Canal d’interaction | Canal d’interaction. |

+++

+++ Géo

| Nom | Description |
|------|-------------|
| Ville géographique | Ville géographique. |
| Pays géographique | Pays géographique. |
| DMA géographique | Géodatage. |
| Région géographique | Région géographique. |
| Latitude | Latitude. |
| Longitude | Longitude. |
| Point d’intérêt | Point d&#39;intérêt. |
| État | État. |

+++

+++ Canal marketing

| Nom | Description |
|------|-------------|
| Canal Première touche | Canal Première touche. |
| Détails du canal Première touche | Détails du canal de première touche. |
| Canal Dernière touche | Canal Dernière touche. |
| Détails du canal Dernière touche | Détails du canal Dernière touche. |
| Canal marketing | Canal marketing. |

+++

+++ Mobile

| Nom | Description |
|------|-------------|
| ID de l’application | ID de l’application. |
| Opérateur de téléphonie mobile | Opérateur mobile. |
| Blocages mobiles | Accidents mobiles. |
| Nom de l’appareil mobile | Nom de l’appareil mobile. |
| Type d’appareil mobile | Type d’appareil mobile. |
| Nom de message in-app mobile | Nom du message mobile dans l’application. |
| Installations mobiles | Installations mobiles. |
| Lancements mobiles | Lancements mobiles. |
| Fabricant du dispositif portable | Fabricant du dispositif portable. |
| Annulations de messages mobiles | Message mobile annulé. |
| Clics sur des messages mobiles | Clics sur les messages mobiles. |
| Impressions de messages mobiles | Impressions de messages mobiles. |
| Opt-in pour les messages push mobiles | Opt-in des notifications push des messages mobiles. |
| Nom du message push mobile | Nom du message push mobile. |
| Mises à niveau mobiles | Mises à niveau mobiles. |
| Temps passé par action minutée | Durée par action minutée. |

+++

+++ Recherche

| Nom | Description |
|------|-------------|
| Moteur de recherche | Moteur de recherche. |
| Mot-clé de moteur de recherche | Mot-clé du moteur de recherche. |
| Moteur de recherche naturel | Moteur de recherche naturel. |
| Mot-clé de moteur de recherche naturel | Mot-clé naturel du moteur de recherche. |
| Moteur de recherche payant | Moteur de recherche payant. |
| Mot-clé de moteur de recherche payant | Mot-clé payant pour le moteur de recherche. |

+++

+++ Enquête

| Nom | Description |
|------|-------------|
| Enquête | Enquête. |
| Réponse à l’enquête | Réponse à un questionnaire. |
| Fin de l’enquête | Questionnaire terminé. |
| Question d’enquête | Question de l&#39;enquête. |
| Début de l’enquête | L’enquête démarre. |

+++

+++ Web

| Nom | Description |
|------|-------------|
| Durée moyenne par page | Durée moyenne de la page. |
| Rebonds | Rebonds. |
| Page d’accès | Page d’accès |
| Quitter la page | Page de sortie. |
| Page | Page. |
| Pages vues | Pages vues. |
| Référent | Référent. |
| Type de référent | Type de référent. |
| Domaine référent | Domaine référent. |
| Domaine référent d’origine | Domaine référent original. |
| Actualisations | Rechargements. |
| Visites de page unique | Visites sur une seule page. |
| Sections du site | Sections du site. |

+++

+++ B2B

| Nom | Description |
|------|-------------|
| Nom de compte | Nom du compte. |
| Nom du groupe d’achat | Nom du groupe d&#39;achat |
| Nom de l’opportunité | Nom de l’opportunité |

+++

+++ Content Analytics

| Nom | Description |
|------|-------------|
| Gauche absolue de la ressource | Ressource absolue gauche. |
| Première position absolue de la ressource | Asset Absolute Top. |
| Attributs de la ressource | Attributs de ressource. |
| Couleurs de l’arrière-plan de la ressource | Couleurs d’arrière-plan des ressources. |
| Positions des caméras de la ressource | Positions de la caméra de la ressource. |
| Proximités des caméras de la ressource | Les Proximités Des Caméras De Ressources. |
| Paramètres de la caméra de la ressource | Paramètres de la caméra de la ressource. |
| Clics sur la ressource | Clics sur les ressources. |
| Ressource créée par | Ressource Créée Par. |
| Date de création de la ressource | Date de création de la ressource |
| Hauteur d’affichage de la ressource | Hauteur d’affichage de la ressource. |
| Largeur d’affichage de la ressource | Largeur d’affichage de la ressource. |
| Couleurs du premier plan de la ressource | Couleurs de premier plan de la ressource. |
| ID de la ressource | ID de ressource. |
| Types d’image de la ressource | Types d’images des ressources. |
| Dernière mise à jour de la ressource par | Dernière mise à jour de la ressource. |
| Date de la dernière mise à jour de la ressource | Date de la dernière mise à jour de la ressource. |
| Conditions d’éclairage de la ressource | Conditions d’éclairage des ressources. |
| URL du lien de la ressource | Url Asset Link. |
| Nom de la ressource | Nom de la ressource. |
| Catégories de personnes de la ressource | Catégories de ressources/personnes. |
| ID de perception de ressource | Identificateur unique des ressources qui sont sensiblement identiques. |
| Styles de photographie de la ressource | Styles de photographie de ressources. |
| Scènes de ressource | Scènes de ressources. |
| Source de la ressource | Source des ressources. |
| Balises de la ressource | Balises de ressources. |
| Type de ressource | Type de ressource. |
| Vues de la ressource | Vues des ressources. |
| Diffusion d’attention visuelle de la ressource | Répartition de l’attention visuelle des ressources. |
| Densité du contenu visuel de la ressource | Densité du contenu visuel des ressources. |
| Attributs de l’expérience | Attributs d’expérience. |
| Canal d’expérience | Canal d’expérience. |
| Clics de l’expérience | Clics sur l’expérience. |
| Nombre d’émoticônes de l’expérience | Nombre d’émoticônes d’expérience. |
| Nombre de hashtags de l’expérience | Nombre de hashtags d’expérience. |
| Profondeur horizontale de l’expérience en pourcentage | Profondeur horizontale en pourcentage de l’expérience. |
| Mots-clés de l’expérience | Mots-clés d’expérience. |
| Émotions marketing de l’expérience | Expérimentez les émotions marketing. |
| Narrations de l’expérience | Récits d’expérience. |
| Stratégies de persuasion de l’expérience | Expérience : stratégies de persuasion. |
| Nombre de mots de lisibilité de l’expérience par nombre de phrases | Nombre De Mots De Lisibilité De L’Expérience Par Nombre De Phrases. |
| Score de lisibilité de l’expérience | Score de lisibilité de l’expérience. |
| Nombre de phrases pour la lisibilité de l’expérience | Nombre de phrases de lisibilité de l’expérience. |
| Nombre de mots d’arrêt pour la lisibilité de l’expérience | Nombre de mots vides de lisibilité de l’expérience. |
| Nombre de citations de texte pour la lisibilité de l’expérience | Nombre de guillemets de texte lisibles par l’expérience. |
| Nombre de mots pour la lisibilité de l’expérience | Nombre de mots de lisibilité de l’expérience. |
| Source de l’expérience | Experience Source. |
| Tons de l’expérience | Tonalités d’expérience. |
| Profondeur verticale de l’expérience en pourcentage | Profondeur verticale en pourcentage de l’expérience. |
| Vues de l’expérience | Vues d’expérience. |

+++

+++ Journey Optimizer

| Nom | Description |
|------|-------------|
| Erreur d’action (AJO) | Nombre d’erreurs générées par les actions de parcours. |
| Erreur d’exécution d’action | Condition d’erreur qui empêchait l’exécution du parcours d’exécuter l’action. |
| Libellé d’action (AJO) | Le client ou la cliente a généré le nom d’affichage de l’élément avec lequel la personne finale a interagi. |
| Autres sorties (AJO) | Nombre de sorties qui n’ont pas eu lieu du fait qu’un profil a atteint un nœud de fin ou en raison d’échecs liés à une erreur. |
| Installations d’applications (AJO) | Nombre d’installations d’applications. |
| Lancements d’application (AJO) | Nombre de lancements d’une application mobile. |
| Identifiant de lot (AJO) | GUID créé à l’appel de chaque nouvelle instance de lot pour une action de parcours ou de campagne planifiée. Par exemple : si un Parcours planifié ou une action de campagne s’exécute à 8 h et à 10 h, il y aura deux batchInstanceID différents. |
| Date et heure des instances de lot (AJO) | Date et heure de l’instance de lot. |
| Rebonds pour les canaux sortants (obsolètes) | Nombre total de messages rejetés sur les canaux sortants. |
| Nom de l’action de campagne (AJO) | Nom de l’action de campagne. |
| Identifiant de campagne (AJO) | Identifiant de la campagne. |
| Nom de campagne (AJO) | Nom de la campagne. |
| Identifiant de version de la campagne (AJO) | Identifiant de version de la campagne. |
| Canal | Canal avec lequel ces données doivent être corrélées. |
| Clics (AJO) | Nombre total de clics sur tous les canaux. |
| Rejets de politique de consentement (AJO) | Nombre d’actions de parcours rejetées en raison d’une ou de plusieurs politiques de consentement. |
| Erreur de décision de contenu (AJO) | Messages d’erreur générés par les nœuds de décision de contenu du parcours. |
| Erreurs de décision de contenu (AJO) | Nombre d’erreurs générées par les nœuds de décision de contenu du parcours. |
| Nom du nœud de décision de contenu (AJO) | Nom du nœud de décision de contenu du parcours. |
| ID de corrélation | ID de corrélation. |
| Nombre d’offres (AJO) | Nombre d’éléments d’offre dans la proposition. |
| Clé de liaison de l’élément de décision | Identifiant composite qui combine l’ID d’élément avec l’ID de requête Experience Decisioning, ce qui permet la persistance des données dans les interactions. |
| Fournisseur de décision (AJO) | Le fournisseur qui a été invité à prendre la décision. Cette dimension est utilisée lorsque plusieurs services peuvent prendre des décisions pour le même emplacement ou la même activité. |
| Fournisseur de décision (conservé) (AJO) | Fournisseur de décision avec liaison de persistance activée. |
| Identifiant de politique de décision (AJO) | Identifiant de la politique de décision utilisée lors de la décision des éléments à inclure dans cette proposition. |
| Mesure de déduplication (AJO) | Mesure de déduplication. |
| Diffusions (obsolètes) | Nombre total de messages diffusés. |
| Affichages (AJO) | Ce nombre affiche les messages AJO. Ce nombre inclut les ouvertures d’e-mail, les affichages web et les affichages dans les applications. Les plateformes mobiles ne signalent pas les affichages de SMS et de messages push, ils ne sont donc pas comptabilisés. |
| Refusé (AJO) | Compte chaque fois que le message in-app est fermé par le SDK Adobe, quelle que soit l’action choisie par la personne finale pour le fermer. |
| ID du Dry Run (AJO) | Identifiant unique pour le Dry Run |
| Ouvertures d’e-mails par des robots (AJO) | Nombre total d’ouvertures d’e-mail effectuées par des robots. |
| Ouvertures d’e-mail (AJO) | Nombre total d’ouvertures d’e-mails. |
| Domaine de la personne destinataire de l’e-mail (AJO) | Domaine de l’adresse électronique. |
| Objet de l’e-mail | Objet de l’e-mail, non personnalisé. |
| ID d’événement | Identifiant unique de l’événement de série temporelle. |
| ID de critères de sortie (AJO) | ID des critères de sortie utilisés pour déterminer si le parcours doit être fermé. |
| Nom de critères de sortie (AJO) | Nom des critères de sortie. |
| Identifiant de l’expérience (AJO) | Identifiant de l’expérience. |
| Nom de l’expérience (AJO) | Nom de l’expérience. |
| Nombre des offres de secours (AJO) | Nombre d’offres de secours. |
| Erreur de récupération | Condition d’erreur qui empêchait l’exécution du parcours d’exécuter la récupération. |
| Clics entrants (AJO) | Nombre total de clics sur les canaux entrants. |
| Rejets entrants (AJO) | Nombre total d’ignorances sur les canaux entrants. |
| Impressions entrantes (AJO) | Nombre total d’impressions sur les canaux entrants. |
| Envois entrants (AJO) | Nombre total d’envois sur les canaux entrants. |
| Déclenché entrant (AJO) | La proposition a été choisie pour être affichée par le SDK Adobe. D’autres facteurs peuvent empêcher son affichage réel. |
| Optimisé pour l’heure d’envoi (AJO) | L&#39;exécution du message est-elle SendTimeOptimized ? |
| Est un parcours de test | L’événement fait-il partie de l’exécution d’un parcours de test ? |
| Message de test (AJO) | Le message est-il envoyé en tant qu’exécution de test ? |
| ID d’élément (conservé) (AJO) | ID de l’élément pour lequel la liaison de persistance est activée. |
| Identifiant de l’élément (AJO) | Identifiant de l’élément. |
| Nom de l’élément (AJO) | Nom de l’élément. |
| Nom d’élément (conservé) (AJO) | Nom de l’élément pour lequel la liaison de persistance est activée. |
| Erreur d’action de parcours (AJO) | Messages d’erreur générés par des actions de parcours. |
| Nom du nœud d’action du parcours | Nom de nœud de l’action de parcours. |
| Entrées du parcours | True si l’événement d’étape était un événement d’entrée de parcours pour un profil. |
| Fin du parcours (AJO) | La fin du parcours. |
| Nom du nœud d’événement de parcours | Cette valeur est définie chaque fois qu’un segment ou un événement externe se produit dans un parcours. |
| Motif d’exclusion du parcours | Raison de l’exclusion de l’instance de parcours. |
| Nom de la règle d’exclusion du parcours | Nom de la règle à l’origine du refus d’entrée dans le parcours. |
| Exclusions du parcours (AJO) | Indiquez si l’événement d’étape en cours a entraîné l’abandon du parcours pour un profil. Cela se produit généralement en raison de l’application de règles de limitation ou de simultanéité, qui empêchent toute progression ultérieure dans le parcours. |
| Type de sortie du parcours (AJO) | Type de sortie survenu pour l’instance de parcours. |
| Échecs du parcours | Indique l’état actuel de l’étape qui a terminé son exécution. |
| ID du parcours | Identifiant du parcours. |
| Nom du parcours | Nom du parcours. |
| Nom et version du parcours | Nom et version du parcours. |
| ID de version du parcours | Identifiant de version du parcours. |
| JourneyExits | True si l’étape actuelle entraînait la fin d’une instance du parcours. Il s’agit de la dernière étape d’un parcours pour un profil donné qui a été exécutée avec succès. |
| Conversions de pages de destination (AJO) | Nombre total de conversions sur la page de destination. |
| Identifiant de page de destination (AJO) | Identifiant unique de la page de destination. |
| Source de la page de destination (AJO) | Source de la page de destination. |
| Vues de la page de destination (AJO) | Nombre total de vues sur la page de destination. |
| Clics sur la page de destination (AJO) | Nombre total de clics sur la page de destination. |
| URL de lien (AJO) | URL sur laquelle l’utilisateur ou l’utilisatrice a cliqué. |
| Raison du rebond du message (AJO) | Raison du rebond du message. |
| Raison de l’erreur du message (AJO) | Raison de l’erreur du message. |
| Raison d’exclusion du message (AJO) | Raison de l’exclusion. |
| Catégorie d’échec de message (AJO) | Catégorie d’échec . |
| Raison de l’échec du message (AJO) | Raison de l’échec. |
| Type d’échec de message (AJO) | Type d’échec. |
| Identifiant de message (AJO) | Identifiant de message avec lequel ces données doivent être corrélées. |
| Langue du message (AJO) | Langue du message. |
| Nom du message (AJO) | Nom du message. |
| Reprise de message (AJO) | Nombre de reprises. |
| Statut du message (AJO) | Statut du message (par exemple, envoyé, rebond, erreur, etc.) |
| Type de message (AJO) | Si le message est de type marketing ou transactionnel. |
| Statut des commentaires sur les messages (obsolètes) | Statut du retour d’informations. |
| Entrées de nœud | True si l’événement d’étape était un événement d’entrée de nœud pour un profil. |
| ID du nœud | Identifiant du nœud de parcours. |
| Nom du nœud | Nom du nœud du parcours. |
| Type de nœud | Type de nœud du parcours. |
| Espace de noms d’identité d’actions de campagnes orchestrées (AJO) | Espace de noms d’identité de l’action de campagne orchestrée. |
| Nom de l’action de campagne orchestrée (AJO) | Nom de l’action de la campagne orchestrée. |
| Identifiant du nœud d’action de campagne orchestrée (AJO) | Identifiant d’action de la campagne orchestrée. |
| Identifiant de campagne orchestrée (AJO) | Identifiant de la campagne orchestrée. |
| Nom de la campagne orchestrée (AJO) | Nom de la campagne orchestrée. |
| Identifiant de version de campagne orchestrée (AJO) | ID de version de la campagne orchestrée. |
| Clics sortants (AJO) | Nombre total de clics sur les canaux sortants. |
| Erreurs sortantes (obsolètes) | Nombre total de messages en erreur sur les canaux sortants. |
| Exclusions sortantes (obsolètes) | Nombre total d’événements d’exclusion sur les canaux sortants. |
| Envois sortants (obsolètes) | Nombre total de messages envoyés sur les canaux sortants. |
| Point d’intérêt | point d’intérêt. |
| ID de la proposition (AJO) | Identifiant de la proposition. |
| Actions personnalisées de notification push (AJO) | Nombre total d’actions personnalisées dans l’interaction avec des notifications push. |
| Interactions des notifications push (AJO) | Nombre de fois où une application mobile est lancée en raison d’une interaction de message push direct. |
| Plateforme de notifications push (AJO) | Service de fournisseur de notifications push, par exemple APNS ou FCM. |
| Titre de notification push | Titre de notification push, non personnalisé. |
| ID de stratégie de classement (AJO) | ID de stratégie de classement. |
| Nom de la politique de consentement rejetée | Nom de la politique de consentement rejetée correspondante. |
| Comptage des reprises (AJO) | Nombre de tentatives d’envoi d’un message avant succès ou échec. |
| Nom de la règle | Nom de la règle à l’origine du refus d’entrée dans le parcours. |
| Type de sélection (AJO) | Il s’agit du type de sélection utilisé lorsqu’un élément est dérivé dans le cadre d’une décision. |
| Envois (obsolètes) | Nombre total de messages envoyés sur tous les canaux. |
| Message SMS entrant (AJO) | Réponse entrante par SMS, par exemple arrêt, démarrage, abonnement, etc. |
| Messages SMS entrants (AJO) | Réponse entrante par SMS, par exemple arrêter, démarrer, s’abonner, etc. |
| Type de message SMS (AJO) | Fournisseur SMS, par exemple : inbound, inboundReply ou send. |
| Fournisseur de SMS (AJO) | Fournisseur de SMS, par exemple Sinch ou Twilio. |
| Taux de plaintes relatives au spam (AJO) | Nombre total de plaintes pour spam. |
| Nom de la stratégie (AJO) | Nom de stratégie. Nom de stratégie duquel l’élément a été dérivé. |
| Nom de stratégie (conservé) (AJO) | Nom de la stratégie pour laquelle la liaison de persistance est activée. |
| Ajouts à la liste d’abonnements (AJO) | Nombre total d’ajouts à une liste d’abonnements. |
| ID de liste d’abonnements (AJO) | Identifiant unique de la liste d’abonnements. |
| Suppressions de la liste d’abonnements (AJO) | Nombre total de suppressions d’une liste d’abonnements. |
| Surface (AJO) | Surface du canal sur laquelle le message a été affiché. |
| Ciblés (obsolètes) | Nombre de fois où une proposition a été ciblée sur une personne. Il s’agit du nombre de fois où une proposition a été envisagée d’être affichée pour une personne. |
| Nom de la règle de ciblage (AJO) | Nom de la règle de ciblage. |
| Événement de test (AJO) | Événement de test. |
| Temps jusqu’au début | Heure de début. |
| Durée totale de la mémoire tampon | Durée totale de la mémoire tampon. |
| Durée totale de pause | Durée totale de pause. |
| Type de trafic (AJO) | Type de trafic du classement. |
| Identifiant de traitement (AJO) | Identifiant du traitement sélectionné pour l’expérience. |
| Nom du traitement (AJO) | Nom du traitement pour l’expérience. |
| Visiteurs et visiteuses uniques dans l’expérience (AJO) | Visiteurs uniques dans l’expérience. |
| Désabonnements (AJO) | Nombre total de désabonnements. |
| Libellé de l’URL (AJO) | Libellé convivial pour l’URL. |
| Identifiant d’URL (AJO) | Identifiant unique de l’URL sur laquelle l’utilisateur ou l’utilisatrice a cliqué. |

+++
