---
title: Optimisation du marketing de compte
description: Découvrez comment optimiser le marketing de compte à l’aide de Customer Journey Analytics B2B edition.
solution: Customer Journey Analytics
feature: Use Cases
role: User
badgePremium: label="B2B edition"
exl-id: d5e44546-ea82-42eb-98df-19d51c71e9be
source-git-commit: 2fad11178853e08783b8f48671b504f50b6e0770
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 0%

---

# Optimisation du marketing de compte

{{draft-b2b}}

Une commercialisation efficace basée sur les comptes nécessite une compréhension approfondie du parcours d&#39;achat au niveau du compte. Vous pouvez ainsi déterminer les activités marketing les plus efficaces pour conclure une affaire.

Pour cela, vous devez analyser et explorer les éléments suivants :

* Impact marketing :

   * Sur l’ensemble des campagnes, canaux et contenus.
   * Sur les groupes d&#39;achat dans les comptes,

* Progression du pipeline de ventes.
* Opportunités de vente incitative et croisée.
* Intégrité du compte client.


Customer Journey Analytics B2B edition peut vous aider à optimiser le marketing de compte. Consultez les sections suivantes pour obtenir des exemples.


## Engagement marketing basé sur les comptes

Vous souhaitez identifier les expériences, en ligne et hors ligne, qui ont le plus d’impact sur les opportunités clôturées.

Utilisez la visualisation [Zone de travail de Parcours ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) pour mapper chaque interaction entre les comptes, les opportunités, les groupes d’achats, les campagnes et les canaux, afin d’obtenir des informations sur ce qui fonctionne dans le marketing de votre compte et sur les améliorations que vous pouvez apporter.

Une visualisation de zone de travail de parcours vous permet d’effectuer les opérations suivantes :

* Voir l&#39;histoire complète. Par exemple, vous pouvez afficher le chemin d’accès détaillé d’un compte ou d’un groupe d’achats à forte valeur spécifique à ** qui comprend toutes les interactions en ligne et hors ligne connues.
* Mettez en contexte les moments clés qui précèdent ou suivent des jalons importants (par exemple : un déclencheur de prospect qualifié par marketing ou la création d’opportunités).
* Prend en charge le personnel des ventes via l’historique des interactions de la visualisation sur des comptes spécifiques. Une telle visualisation permet des conversations pertinentes.

### Exemple

Vous souhaitez visualiser le parcours d’un formulaire de prospect à un formulaire fermé.

1. Visualisation [Création et configuration d’une zone de travail de Parcours ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
1. Configurez **[!UICONTROL Compte]** comme mesure de Principal ****.
1. Veillez à sélectionner **[!UICONTROL Compte]** comme conteneur de zone de travail de Parcours ****.

   ![Cas d’utilisation B2B - optimiser le marketing de compte - Zone de travail de parcours - Configuration](assets/b2b-uc-optimize-marketing-journey-canvas-config.png)

1. Sélectionnez la **[!UICONTROL Version]**.
1. Faites glisser et déposez des nœuds sur la zone de travail et connectez les nœuds pour illustrer le parcours de compte. Par exemple : de **[!UICONTROL Formulaire de prospect : étape 1]** formulaire à **[!UICONTROL Opportunité. Créé]**.

   ![Cas d’utilisation B2B - optimiser le marketing de compte - Zone de travail de parcours ](assets/b2b-uc-optimize-marketing-journey-canvas.png)


## Segmentation des cohortes

Vous souhaitez identifier des groupes d’acheteurs clés afin de les activer pour d’autres canaux tels que les médias achetés, les e-mails, les réseaux sociaux.

Utilisez la visualisation [Tableau de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) pour regrouper les entités B2B (comptes, opportunités, groupes d’achats) en fonction d’un point de départ partagé (comme une date d’avance de qualification du marché (MQL)). Et suivez la progression de chacune de ces entités au fil du temps aux étapes ou jalons suivants.

Une visualisation de tableau de cohorte vous permet d’effectuer les opérations suivantes :

* Analysez la vitesse à laquelle les cohortes de comptes ou d’opportunités atteignent des jalons clés (par exemple : d’un prospect qualifié marketing à un prospect qualifié commercial) sur des semaines ou des mois.
* Déterminez si certaines cohortes (par segment, source de campagne, type de groupe d&#39;achat) se déplacent plus rapidement dans le cycle de vente que d&#39;autres cohortes.
* Évaluez si les initiatives stratégiques (par exemple : campagnes marketing) sont corrélées à des délais de progression plus courts pour les cohortes suivantes.

### Exemple

Vous souhaitez afficher les cohortes mensuelles d’opportunités closes.

1. [Création et configuration d’une visualisation Tableau de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
1. Utilisez **[!UICONTROL Opportunité créée]** comme mesure **[!UICONTROL Critères d’inclusion]**. Sélectionnez **[!UICONTROL >=]** comme opérateur et saisissez la valeur `1`.
1. Utilisez la mesure **[!UICONTROL Closed-Won]** comme mesure **[!UICONTROL Critères de retour]**. Sélectionnez **[!UICONTROL >=]** comme opérateur et saisissez la valeur `1`.
1. Sélectionnez **[!UICONTROL Opportunité]** comme conteneur.

   ![Cas d’utilisation B2B - segmentation de cohorte - tableau de cohorte - configuration](assets/b2b-uc-optimize-marketing-cohort-table-config.png)

1. Sélectionnez **[!UICONTROL Créer]**. Consultez ci-dessous un exemple de tableau de cohortes.

   ![Cas d’utilisation B2B - segmentation de cohorte - tableau de cohorte](assets/b2b-uc-optimize-marketing-cohort-table.png)


## Événements en personne

Vous souhaitez créer des rapports sur le compte engagé et l’activité de visionnage pour plusieurs événements en personne. Vous pouvez ainsi analyser et optimiser l&#39;impact de la participation à des événements en personne.

Une visualisation [flux](/help/analysis-workspace/visualizations/c-flow/flow.md) vous permet de visualiser les chemins empruntés par les utilisateurs, mais aussi désormais par les comptes ou les groupes d’achats, entre les interactions ou les étapes au fil du temps.

Une visualisation de flux permet d’effectuer les opérations suivantes :

* Identifiez les séquences de points de contact les plus fréquentes parcourues par les entités B2B (par exemple : de *Visite de site* à *Téléchargement du livre blanc* en *Demande de démonstration*).
* Visualisez la façon dont les comptes ou les groupes d’achats naviguent de manière non linéaire (par exemple : boucler, ignorer des étapes ou emprunter des itinéraires inattendus).
* Concentrez-vous sur le flux avant ou après une interaction critique (par exemple : une demande de démonstration) pour comprendre les facteurs qui contribuent à ou les actions qui suivent l’interaction.

### Exemple

Vous souhaitez visualiser l’influence sur la génération de MQL (leads qualifiés pour le marketing).

1. [Créer et configurer une visualisation Flux](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
1. Sélectionnez **[!UICONTROL Qualifié MQL]** pour **[!UICONTROL Se terminer par]**.
1. Sélectionnez **[!UICONTROL Type de contenu]** pour **[!UICONTROL Dimension de cheminement]**.
1. Sélectionnez **[!UICONTROL Afficher les paramètres avancés]**.
1. Saisissez `5` pour **[!UICONTROL Nombre de colonnes]**.
1. Sélectionnez **[!UICONTROL Compte]** pour le **[!UICONTROL Conteneur de flux]**.

   ![Cas d’utilisation B2B - événements en personne - configuration de flux](assets/b2b-uc-optimize-marketing-flow-config.png)

1. Sélectionnez la **[!UICONTROL Version]**.

   ![Cas d’utilisation B2B - événements en personne - configuration de flux](assets/b2b-uc-optimize-marketing-flow.png)
