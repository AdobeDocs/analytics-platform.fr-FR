---
title: Analyse Chronologie
description: Observez les événements de session au niveau de la personne au fil du temps pour trouver des modèles d’expérience.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
TQID: https://experienceleague.adobe.com/17wzuDrTYs5VGC85jXh3eacQKO0-590t0K-XfggT6D4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 594
ht-degree: 97%

---

# Analyse de la [!UICONTROL chronologie] {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Chronologie"
>abstract="Observez les événements de session au niveau de l’utilisateur ou de l’utilisatrice au fil du temps."

<!-- markdownlint-enable MD034 -->

L’analyse ![Chronologie](/help/assets/icons/Timeline.svg) **[!UICONTROL Chronologie]** vous permet d’observer les événements de session au niveau de la personne au fil du temps, afin de trouver des modèles d’expérience et de raconter de meilleures histoires d’utilisation. Le rail de gauche vous permet de filtrer le flux par valeurs de propriété et segments. Le rail de droite vous permet de sélectionner, dans une liste randomisée, les utilisateurs et utilisatrices qui correspondent aux critères de filtre. La zone centrale affiche le flux de la personne sélectionnée par session, composé de la date et de l’heure, des valeurs de propriété et de la durée. La durée n’est pas disponible pour le dernier événement d’une session donnée.


>[!NOTE]
>
>L’analyse [!UICONTROL Chronologie] nécessite que le composant standard **[!UICONTROL ID de personne]** soit disponible dans la [vue de données](/help/data-views/component-reference.md#optional). L’inclusion de l’ID de personne dans une vue de données est gérée par votre administrateur ou administratrice Customer Journey Analytics, ce qui permet à votre organisation de contrôler entièrement la confidentialité des personnes pouvant accéder à ces données.
><br/>Si aucune vue de données n’est associée au composant [!UICONTROL ID de personne], le message suivant s’affiche :
>
>* **Admins** : *la propriété PersonID est requise pour cette analyse. Ajoutez l’ID de personne à la vue de données.*
>* **Non-admins** : *La propriété PersonID est requise pour cette analyse. Contactez votre administrateur ou administratrice Customer Journey Analytics pour ajouter l’ID de personne à la vue de données.*

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/timeline)



## Cas d’utilisation

Les cas d’utilisation de cette analyse sont les suivants :

* **Exploration par friction** : si vous constatez une forte baisse dans l’analyse [analyse en entonnoir](funnel.md), vous pouvez créer un segment de ces utilisateurs et utilisatrices et appliquer le segment dans cette analyse pour étudier les causes potentielles.
* **Comportement d’erreur** : si les utilisateurs et utilisatrices rencontrent une erreur de produit, vous pouvez découvrir ce qu’ils faisaient avant ou après avoir vu cette erreur.
* **Validation de la collecte de données** : les administrateurs et administratrices des données peuvent filtrer cette analyse sur leur propre ID de personne pour vérifier que l’implémentation de leur organisation fonctionne comme prévu.

## Interface

Consultez [Interface](../overview.md#interface) pour une vue d’ensemble de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Dimension]** : dimension pour laquelle vous souhaitez afficher les valeurs diffusées. Le flux au centre affiche les valeurs de la dimension sélectionnée. Vous pouvez également appliquer des filtres pour réduire le flux à des données plus pertinentes. Les opérateurs valides pour le filtre comprennent [!UICONTROL Est égal à], [!UICONTROL N’est pas égal à], [!UICONTROL Commence par], [!UICONTROL Se termine par], [!UICONTROL Contient], [!UICONTROL Ne contient pas &#x200B;], [!UICONTROL Existe] et [!UICONTROL N’existe pas].
* **[!UICONTROL Segments]** : segments que vous souhaitez analyser. Le segment sélectionné filtre vos données pour se concentrer uniquement sur les personnes qui correspondent à vos critères de segment. Si vous souhaitez limiter l’analyse à un ID de personne spécifique, vous pouvez le filtrer dans le panneau de droite. Un segment est pris en charge pour cette analyse.

### Paramètres du graphique

L’analyse [!UICONTROL Chronologie] propose les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Montrer en tant que]** : affiche les valeurs de propriété de votre choix.
   * [!UICONTROL Tout afficher] : affiche toutes les valeurs de propriété dans une session.
   * [!UICONTROL Surligner] : met visuellement en surbrillance les valeurs de propriété dans une session qui correspondent aux filtres de requête.
   * [!UICONTROL Afficher seulement] : affiche uniquement les valeurs de propriété dans une session qui correspondent aux filtres de requête.

### Période

Période souhaitée pour votre analyse. Ce paramètre comporte deux composants :

* **[!UICONTROL Intervalle]** : granularité de la date selon laquelle vous souhaitez afficher les données de tendance. Ce paramètre n’a aucune incidence sur les analyses hors tendances telles que Chronologie.
* **[!UICONTROL Date]** : date de début et de fin. Les paramètres prédéfinis de période flottante et les périodes personnalisées enregistrées précédemment sont disponibles pour votre commodité. Vous pouvez également utiliser le sélecteur de calendrier pour choisir une période fixe.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
