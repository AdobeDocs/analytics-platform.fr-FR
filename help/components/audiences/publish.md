---
title: Créer et publier des audiences
description: Découvrez comment publier des audiences à partir de Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 78%

---

# Créer et publier des audiences {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="Fréquence d’actualisation"
>abstract="Découvrez la fréquence à laquelle l’appartenance d’une audience est réévaluée.<br/>Les audiences uniqes ne sont évaluées qu’une seule fois."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="Limite d’audience"
>abstract="L’actualisation des audiences est limitée en fonction de la fréquence à laquelle elles s’actualisent."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="Actualiser l’intervalle de recherche en amont"
>abstract="Définissez le nombre de jours de recherche en amont à partir desquels une audience est évaluée."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="Limite de taille d’audience"
>abstract="Les audiences ne peuvent pas dépasser 20 millions de membres."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="Espaces de noms inclus"
>abstract="Les identités de cette audience sont composées des espaces de noms ci-dessous."

<!-- markdownlint-enable MD034 -->




Cette rubrique explique comment créer et publier des audiences identifiées dans Customer Journey Analytics dans le [profil client en temps réel](https://experienceleague.adobe.com/fr/docs/experience-platform/profile/home) dans Adobe Experience Platform pour le ciblage et la personnalisation de la clientèle.

Lisez cette [vue d’ensemble](/help/components/audiences/audiences-overview.md) pour vous familiariser avec le concept des audiences Customer Journey Analytics.

## Créer et publier une audience {#create}

1. Pour créer et publier une audience, effectuez l’une des opérations suivantes :

   | Méthode de création | Détails |
   | --- | --- |
   | Depuis l’interface **[!UICONTROL Audiences]** | Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Audiences]** dans le menu principal de Customer Journey Analytics. L’interface Audiences s’affiche. Sélectionnez **[!UICONTROL Créer une audience]** et le [!UICONTROL Créateur d’audience] s’ouvre. |
   | Depuis une visualisation dans Analysis Workspace | De nombreuses visualisations dans Analysis Workspace vous permettent de créer une audience à l’aide du menu contextuel. Par exemple, vous pouvez sélectionner **[!UICONTROL Créer une audience]** dans le menu contextuel d’un élément dans un [Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ou d’un nœud dans une [Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).<p>L’utilisation de cette méthode préremplit le segment dans le créateur d’audiences avec la dimension ou l’élément de dimension que vous avez sélectionné.</p><p>Les visualisations suivantes vous permettent de créer une audience à l’aide du menu de clic droit :</p><ul><li>[Table de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Abandon](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Flux](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Tableau à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[Zone de travail de parcours](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Note :** les audiences ne peuvent pas inclure de mesures calculées. Si vous essayez de créer une audience qui contient une mesure calculée, la mesure calculée n’est pas incluse dans la définition de l’audience.</p> |
   | À partir de l’interface utilisateur de création/modification de segment | Cochez la case qui indique **[!UICONTROL Créer une audience à partir de ce segment]**. L’utilisation de cette méthode préremplit le segment. Consultez [Créer des filtres](/help/components/filters/create-filters.md) pour plus d’informations. |

   {style="table-layout:auto"}

1. Créez l’audience à l’aide du [créateur d’audiences](#audience-builder).

1. Interprétez les données à l’aide du panneau [Aperçu de la date](#data-preview).

1. Sélectionnez **[!UICONTROL [!UICONTROL Afficher les ID d’échantillon]]** pour afficher un échantillon d’identifiants dans cette audience. Dans la boîte de dialogue **[!UICONTROL ID d’échantillon]**, vous pouvez utiliser ![Rechercher](/help/assets/icons/Search.svg) [!UICONTROL *Rechercher des ID d’échantillon*] pour rechercher des ID d’échantillon.

1. Vérifiez deux fois la configuration de votre audience et sélectionnez **[!UICONTROL Publier]**.
Vous recevez un message de confirmation indiquant que l’audience est publiée. Il suffit d’une minute ou deux pour que cette audience s’affiche dans Experience Platform.

1. Sélectionnez **[!UICONTROL Afficher l’audience dans AEP]** dans le même message et vous naviguerez vers l’[interface d’utilisation des segments](https://experienceleague.adobe.com/fr/docs/experience-platform/segmentation/ui/overview) dans Adobe Experience Platform. Plus d’informations ci-dessous.

## Créateur d’audiences

Configurez ces paramètres pour définir ou mettre à jour votre audience.

![Capture d’écran de la section Création d’une audience affichant les paramètres décrits dans la section suivante.](assets/create-audience.png)

| Paramètre | Description |
| --- | --- |
| ![Données](/help/assets/icons/Data.svg) | Sélectionnez une vue de données à utiliser pour la création de l’audience. |
| **[!UICONTROL Nom]** | Nom de l’audience. Par exemple, `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Étiquettes]** | Toutes les balises que vous souhaitez affecter à l’audience à des fins d’organisation. Vous pouvez sélectionner une ou plusieurs balises préexistantes ou en saisir une nouvelle. |
| **[!UICONTROL Description]** | Description de l’audience pour la différencier des autres. Par exemple, `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Fréquence d’actualisation]** | Fréquence à laquelle vous souhaitez actualiser l’audience.<p/>Vous pouvez choisir entre les options suivantes : <ul><li>Audience **[!UICONTROL ponctuelle]** : audience (par défaut) qui n’a pas besoin d’être actualisée. Par exemple, cette option peut s’avérer utile pour des campagnes ponctuelles spécifiques.<br/>Vous devez spécifier une **[!UICONTROL Période ponctuelle]**. Vous pouvez utiliser ![Calendrier](/help/assets/icons/Calendar.svg) pour saisir une période.</li><li>Audience actualisable. Vous avez les choix suivants :<ul><li>**[!UICONTROL Toutes les 4 heures]** : audience qui s’actualise toutes les 4 heures.</li><li>**[!UICONTROL Quotidien]** : audience qui s’actualise quotidiennement.</li><li>**[!UICONTROL Hebdomadaire]** : audience qui s’actualise toutes les semaines.</li><li>**[!UICONTROL Mensuel]** : audience qui s’actualise tous les mois.</li></ul></li>Pour actualiser les audiences, vous devez indiquer les informations suivantes :<ul><li>**[!UICONTROL Actualiser l’intervalle de recherche en amont]**. Définissez le nombre de jours de recherche en amont à partir desquels une audience est évaluée. Vous pouvez effectuer un choix parmi des options ou définir une heure personnalisée. La durée maximale est de 90 jours.</li><li>**[!UICONTROL Date d’expiration]** : permet de définir à quel moment l’audience cesse d’être actualisée. Vous pouvez utiliser ![Calendrier](/help/assets/icons/Calendar.svg) pour sélectionner une date. La valeur par défaut est d’un an à compter de la date de création. Les audiences arrivant à expiration sont traitées de la même manière que les rapports planifiés arrivant à expiration. L’administrateur ou l’administratrice reçoit un e-mail un mois avant l’expiration de l’audience.</li></ul> Notez qu’il existe une limite de 75 à 150 actualisations d’audience, selon vos droits Customer Journey Analytics.</li></ul> |
| **[!UICONTROL Filtrer]** | Les filtres sont la principale entrée de l’audience. Faites glisser un ou plusieurs segments depuis le panneau ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** vers la zone Segment . Vous pouvez utiliser ![Rechercher](/help/assets/icons/Search.svg) [!UICONTROL *Rechercher des segments*] pour rechercher des segments. Vous pouvez ajouter jusqu’à 20 segments. Les segments peuvent être joints à l’aide d’opérateurs **[!UICONTROL Et]** ou **[!UICONTROL Ou]**.<p>Lors de la création d’une audience à partir d’une visualisation dans Analysis Workspace (un tableau à structure libre ou une zone de travail de Parcours, par exemple), tous les segments appliqués au panneau ou à la colonne sont conservés. Vous pouvez supprimer tous les segments qui sont automatiquement appliqués.</p> |
| **[!UICONTROL Prévisualisation des données]** | Sélectionnez ![Infos](/help/assets/icons/Info.svg) pour afficher ou masquer la [Prévisualisation des données](#data-preview) pour la période sélectionnée. |

## Prévisualisation des données

Le panneau Prévisualisation des données fournit les informations suivantes.

| Élément | Description |
| --- | --- |
| **[!UICONTROL Total personnes]** | Résumé du nombre total de personnes dans cette audience. La taille maximale est de 20 millions de personnes. Si votre audience dépasse 20 millions de personnes, vous devez réduire la taille de l’audience avant de pouvoir la publier. |
| **[!UICONTROL Limite de taille d’audience]** | Visualisation indiquant à quel point cette audience est éloignée de la limite de 20 millions. |
| **[!UICONTROL Retour dʼaudience estimé]** | Vous pouvez utiliser cette valeur pour recibler les personnes de cette audience qui reviennent sur votre site, application mobile ou autre canal.<p>Ici, vous pouvez sélectionner la période (**[!UICONTROL 7 prochains jours]**, **[!UICONTROL 2 prochaines semaines]**, **[!UICONTROL Mois prochain]**) pour l’estimation du nombre de clientes et clients susceptibles de revenir. |
| **[!UICONTROL Retour estimé]** | Ce nombre vous donne une estimation du nombre de clientes et clients récurrents sur la période que vous avez sélectionnée. Ce nombre est prédit à l’aide du taux d’attrition historique pour cette audience. |
| **[!UICONTROL Prévisualiser les mesures]** | Vous pouvez sélectionner une mesure spécifique pour voir la manière dont les données de cette mesure sont basées sur l’audience que vous définissez.  Chaque mesure Prévisualisation affiche un total pour la mesure en fonction de l’audience. Et un pourcentage de la mesure basée sur l’audience à partir du total global de la mesure, tel que défini par la vue de données. Par exemple, 381 personnes (la mesure que vous avez sélectionnée) sont le résultat de votre définition d’audience, soit 5 % du nombre total de personnes disponibles dans la vue de données. Vous pouvez sélectionner n’importe quelle mesure disponible dans votre vue de données. |
| **[!UICONTROL Espaces de noms inclus]** | Espaces de noms spécifiques associés aux personnes de votre audience. Par exemple, ECID, identifiant CRM, adresses électroniques, etc. |
| **[!UICONTROL Sandbox]** | La [sandbox Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/sandbox/home) dans laquelle réside cette audience. Lorsque vous publiez cette audience sur Platform, vous ne pouvez l’utiliser que dans les limites de ce sandbox. |

{style="table-layout:auto"}

## Que se passe-t-il une fois une audience créée et publiée ? {#after-audience-created}

Une fois que vous avez créé et publié une audience dans Customer Journey Analytics, elle est disponible dans Experience Platform. Un segment de diffusion en continu Adone Experience Platform n’est créé que si votre organisation est configurée pour la segmentation en continu.

* L’audience dans Platform partage le même nom et la même description que l’audience Customer Journey Analytics. Le nom est ajouté avec l’identifiant d’audience Customer Journey Analytics afin de s’assurer que l’audience est unique.
* Toute modification apportée au nom ou à la description de l’audience dans Customer Journey Analytics est répercutée dans Experience Platform.
* Si une audience est supprimée dans Customer Journey Analytics, elle reste disponible dans Experience Platform jusqu’à l’expiration de son appartenance à un profil. L’appartenance à un profil expire après 420 jours pour les audiences ponctuelles et après 16 jours pour les audiences récurrentes.

## Considérations relatives à la latence {#latency}

À plusieurs moments avant, pendant et après la publication de l’audience, des latences peuvent se produire. Voici un aperçu des latences possibles.

![Latences dans la publication d’audiences, comme décrit dans cette section.](assets/latency-diagram.svg)

|  | Point de latence | Durée de latence |
| --- | --- | --- |
| Pas d’affichage | Adobe Analytics vers le connecteur source Analytics (A4T) | Jusqu’à 30 minutes |
| 1 | Ingestion de données dans le lac de données (à partir du connecteur source Analytics ou d’autres sources) | Jusqu’à 90 minutes |
| 2 | Ingestion de données du lac de données d’Experience Platform dans Customer Journey Analytics | Jusqu’à 90 minutes |
| 3 | Publication d’audiences dans le profil client en temps réel, y compris la création automatique du segment de diffusion en continu et la possibilité pour le segment d’être prêt à recevoir les données. | Quelques secondes |
| 4 | Fréquence d’actualisation des audiences | <ul><li>Actualisation ponctuelle (latence inférieure à 5 minutes)</li><li>Actualiser toutes les 4 heures, tous les jours, toutes les semaines, tous les mois (la latence va de pair avec le taux d’actualisation) |
| 5 | Création d’une destination dans Adobe Experience Platform : activation du nouveau segment | 1-2 heures |

{style="table-layout:auto"}

## Utiliser les audiences Customer Journey Analytics dans Experience Platform {#audiences-aep}

Customer Journey Analytics récupère toutes les combinaisons d’espace de noms et d’identifiants de votre audience publiée et les diffuse dans Real-Time Customer Data Platform. Customer Journey Analytics envoie l’audience à Experience Platform avec l’identité principale définie sur l’élément sélectionné en fonction de ce qui a été sélectionné comme [!UICONTROL ID de personne] lors de la configuration de la connexion.

Real-Time Customer Data Platform examine ensuite chaque combinaison espace de noms/ID et recherche un profil dont elle peut faire partie. Un profil est essentiellement un groupe d’espaces de noms, d’identifiants et d’appareils liés. Si un profil est trouvé, il ajoute l’espace de noms et l’identifiant aux autres identifiants de ce profil en tant qu’attribut d’appartenance à un segment. Par exemple, <user@adobe.com> peut être ciblé sur tous leurs appareils et canaux. Si aucun profil n’est trouvé, un nouveau profil est créé.

Pour afficher les audiences Customer Journey Analytics dans Platform, procédez comme suit :

1. Développez **[!UICONTROL Client ou cliente]** dans le panneau de gauche, puis sélectionnez **[!UICONTROL Audiences]**. <!-- is there a folder called "Customer Journey Analytics? -->

1. Sélectionnez l’onglet **[!UICONTROL Parcourir]**.

1. Pour localiser l’audience que vous avez publiée à partir de Customer Journey Analytics, effectuez l’une des opérations suivantes :

   ![Option Audiences dans le panneau de gauche](assets/aep-audiences.png)

   * Triez le tableau selon la colonne **[!UICONTROL Origine]** pour afficher les audiences qui affichent [!UICONTROL **Customer Journey Analytics**] comme origine.

   * Filtrez ![Filtre](/help/assets/icons/Filter.svg) selon l’**[!UICONTROL Origine]** et sélectionnez **[!UICONTROL Customer Journey Analytics]**.

   * Utilisez le champ de recherche ![Rechercher](/help/assets/icons/Search.svg).

Pour plus d’informations sur l’utilisation des audiences dans Platform, consultez la section [Audiences](https://experienceleague.adobe.com/fr/docs/experience-platform/segmentation/ui/segment-builder) dans le [guide de l’interface d’utilisation du créateur de segments](https://experienceleague.adobe.com/fr/docs/experience-platform/segmentation/ui/segment-builder) dans la documentation d’Experience Platform.

### Comprendre les incohérences dans le nombre d’audiences

Des incohérences dans le nombre d’audiences peuvent se produire entre Customer Journey Analytics et Real-Time Customer Data Platform.

<!--
![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)
-->

#### Comptages estimatifs et déterministes

La méthodologie par laquelle le nombre d’adhésions à l’audience est calculé diffère entre les deux applications, comme décrit ci-dessous.

* **Customer Journey Analytics** : la mesure **[!UICONTROL Nombre total de personnes]** dans Customer Journey Analytics est une valeur estimée. Cela signifie que le nombre est une estimation basée sur les règles de l’audience et qu’il peut varier entre les intervalles d’actualisation.
* **Real-Time Customer Data Platform** : le nombre dans Real-Time Customer Data Platform est déterministe, en fonction des tâches d’évaluation quotidiennes, et fixe au moment où l’audience termine sa publication sur le portail d’audiences.

#### Intervalle et taux de publication

Les audiences publient sur Real-Time Customer Data Platform à un taux de 1 500 enregistrements par seconde (RPS). Par exemple, la publication complète d’une audience de 20 millions de membres prendra environ 3,7 heures (20 millions/1 500 RPS/3 600 secondes par heure). Pendant ce temps, des différences d’appartenance à l’audience entre les deux applications sont probables.

#### Fragmentation du profil

Si des profils importés de Customer Journey Analytics existent déjà dans Real-Time Customer Data Platform, ils ne sont pas comptabilisés comme de nouveaux profils. Cela peut entraîner un nombre de profils inférieur aux prévisions dans Real-Time Customer Data Platform.

#### Audiences par lots ou en flux continu

Les audiences Customer Journey Analytics ne sont pas incluses dans la tâche d’évaluation quotidienne par lots et restent fixes jusqu’au prochain intervalle de publication. En revanche, d’autres audiences par lots dans Real-Time Customer Data Platform sont réévaluées toutes les 24 heures.

### Points essentiels à retenir

* **Nombres estimés dans Customer Journey Analytics** : comprenez que le nombre **[!UICONTROL Total de personnes]** dans Customer Journey Analytics est une estimation et peut varier en raison des données de diffusion en continu et des comportements d’identité.
* **Nombre déterministe dans Real-Time Customer Data Platform** : le nombre dans Real-Time Customer Data Platform est fixe et ne change que lors de la prochaine période de publication.
* **Fragmentation de profil** : sachez que les profils existants dans Real-Time Customer Data Platform peuvent ne pas contribuer au nombre de nouveaux profils lors de l’import depuis Customer Journey Analytics.

En différenciant clairement ces aspects, vous pouvez mieux comprendre et gérer les données de votre audience dans Customer Journey Analytics et Real-Time Customer Data Platform.—>

## Questions fréquentes {#faq}

Questions fréquentes sur la publication d’audiences.

+++**Que se passe-t-il si un utilisateur ou une utilisatrice n’est plus membre d’une audience dans Customer Journey Analytics ?**

Dans ce cas, un événement de sortie est transmis par Customer Journey Analytics à Experience Platform.

+++

+++**Que se passe-t-il si vous supprimez une audience dans Customer Journey Analytics ?**

Lorsqu’une audience Customer Journey Analytics est supprimée, elle ne s’affiche plus dans l’interface d’utilisation d’Experience Platform. Cependant, aucun profil associé à cette audience n’est supprimé dans Experience Platform.

+++

+++**Si un profil correspondant n’existe pas dans Real-Time Customer Data Platform, un nouveau profil est-il créé ?**

Oui.

+++

+++**Est-ce que Customer Journey Analytics envoie les données d’audience sous la forme d’événements de pipeline ou d’un fichier plat également destiné au lac de données ?**

Customer Journey Analytics diffuse les données dans Real-Time Customer Data Platform par pipeline. Ces données sont également collectées dans un jeu de données système dans le lac de données.

+++

+++**Quelles sont les identités envoyées par Customer Journey Analytics ?**

Les paires identité/espace de noms utilisées dans la [configuration de la connexion](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection). Plus précisément, l’étape à laquelle un utilisateur ou une utilisatrice sélectionne le champ qu’il ou elle souhaite utiliser comme ID de personne.

+++

+++**Quel ID est choisi comme identité principale ?**

Voir ci-dessus. Une seule identité par personne Customer Journey Analytics est envoyée.

+++

+++**Real-Time Customer Data Platform traite-t-il également les messages Customer Journey Analytics ? Est-ce que Customer Journey Analytics peut ajouter des identités à un graphique d’identités de profil par le biais du partage d’audiences ?**

Non. Une seule identité par personne est envoyée. Real-Time Customer Data Platform n’aurait donc pas à consommer d’extrémités de graphique.

+++

+++**À quel moment de la journée des actualisations quotidiennes, hebdomadaires et mensuelles se produisent-elles ? Quel jour de la semaine les actualisations hebdomadaires ont-elles lieu ?**

Le moment de l’actualisation est basé sur la date de publication de l’audience d’origine et correspond à cette heure de la journée (et à ce jour de la semaine ou du mois).

+++

+++**Est-il possible de configurer l’heure d’actualisation quotidienne, hebdomadaire et mensuelle ?**

Non, les utilisateurs et utilisatrices ne peuvent pas configurer l’heure de l’actualisation.

+++


## Étapes suivantes

* Pour gérer cette audience, accédez à l’[interface utilisateur de gestion](/help/components/audiences/manage.md).
