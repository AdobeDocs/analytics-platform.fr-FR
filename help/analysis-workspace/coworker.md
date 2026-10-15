---
title: Analyse et création de projets Workspace avec un collègue
description: Utilisez l’expérience intégrée au produit pour que Coworker résume le projet ouvert, trouve des informations et crée des panneaux, des tableaux et des segments à partir d’invites en langage naturel.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 8b1f9d95fb38c0fcb1a7f3d9b41bf3cfb9355ed9
workflow-type: tm+mt
source-wordcount: '1897'
ht-degree: 0%
---
# Utiliser l’expérience intégrée au produit pour Coworker

{{release-limited-testing}}

L’expérience intégrée au produit pour Coworker est disponible dans un panneau de conversation sur le côté droit d’Analysis Workspace. Coworker utilise le projet ouvert comme contexte, de sorte que vous puissiez poser des questions sur votre analyse ou demander à Coworker de créer le projet sans avoir besoin d’expliquer ce qu’il contient.

## Comprendre le collègue dans Workspace

### Conditions préalables

* **Coworker est activé pour votre organisation** : l’expérience intégrée au produit pour Coworker est désactivée par défaut. Un administrateur Customer Journey Analytics doit l’activer pour l’organisation avant que les utilisateurs puissent y accéder.

  Si vous ne pouvez pas accéder à Coworker dans Workspace, contactez votre administrateur. Pour plus d’informations, voir [Préférences de l’organisation IMS](/help/analysis-workspace/user-preferences.md#ims-organization-preferences). <!-- need to update this section with the new toggle -->

<!-- **[PLACEHOLDER: Permissions and product profile requirements. Include the Admin Console steps to grant access, if applicable.]** -->

* **Accès aux vues de données** : un collègue utilise vos autorisations existantes d’Analysis Workspace et de vues de données. Il ne peut pas accéder aux données ou composants auxquels vous n’avez pas déjà accès.

### Choisir entre l’application Coworker dans Workspace et l’application Coworker

L’expérience intégrée au produit pour Coworker possède de nombreuses fonctionnalités similaires à celles de l’application [&#128279;](https://experienceleague.adobe.com/fr/docs/cx-enterprise-coworker/content/chat/analytics-chat), y compris les compétences auxquelles vous avez accès. Cependant, il existe des différences importantes qui déterminent dans quels cas vous pouvez utiliser l’un plutôt que l’autre :

| | Expérience intégrée au produit pour Coworker | Application de collègue |
| --- | --- | --- |
| **Quand l’utiliser** | Vous souhaitez créer un projet que vous prévoyez de conserver, de partager avec d’autres utilisateurs ou de mettre à jour au fil du temps. | Vous voulez une réponse rapide. Vous pouvez choisir de transformer l’analyse en projet Workspace ultérieurement, si nécessaire. |
| **Contexte** | Centré sur le projet<p>Utilise le projet Workspace ouvert comme point de départ. Vous pouvez vous référer aux panneaux, tableaux et composants qui se trouvent déjà dans le projet et les créer.</p> | Axé sur la vue de données<p>Utilise les vues de données auxquelles vous avez accès ou celles que vous avez définies comme préférence dans la mémoire de collègue. Vous décrivez ce que vous souhaitez analyser dans votre invite.</p> |
| **Utilisateur type** | Analystes qui créent et valident des analyses dans Workspace. | Utilisateurs professionnels qui souhaitent des réponses sans avoir besoin d’accéder à Workspace ou d’en apprendre plus. |
| **Output** | Coworker ajoute des panneaux, des tableaux et des composants directement au projet Workspace. <p>Le cas échéant, il répond également dans le chat.</p> | Les réponses et les analyses sont fournies dans la conversation, avec la possibilité de les ouvrir dans Analysis Workspace. |

### Ce que vous pouvez faire avec Coworker

#### Poser des questions sur le projet ouvert

Vous pouvez poser à vos collègues des questions telles que :

* Résumez le projet.
* Recherchez des informations et signalez les anomalies dans les données.
* Exécutez une analyse des causes profondes sur un panneau.
* Expliquez comment effectuer une opération dans Analysis Workspace, par exemple comment ajouter un graphique en courbes ou colorer les cellules d’un tableau en fonction de leurs valeurs.
* Expliquez un composant, tel qu’une mesure ou une dimension.

Pour plus d’informations, voir [Poser des questions sur un projet](#ask-questions-about-a-project).

#### Créer et modifier le projet ouvert

Vous pouvez demander à un collègue de faire des choses comme :

* Créez un panneau à structure libre avec les dimensions, mesures et périodes que vous spécifiez.
* Ajoutez des panneaux au projet. Coworker ajoute de nouveaux panneaux sans remplacer vos panneaux existants.
* Ventilez un tableau ou ajoutez des colonnes de comparaison.
* Modifiez la période ou le type de visualisation d’un panneau, par exemple en changeant un tableau en graphique en courbes.
* Renommer un panneau.
* Appliquez un segment existant par nom, créez un segment à partir d’une description en langage clair ou copiez un segment et modifiez sa logique.
* Créez des périodes et des mesures calculées simples.
* Ajoutez des descriptions pour une visualisation de texte qui contient des informations sur le projet.
* Créez un projet avec plusieurs panneaux ou copiez un projet et adaptez-le à une autre audience ou région.
* Enregistrez le projet.

Pour plus d’informations, voir [Mettre à jour un projet](#update-a-project).

### Lorsque Coworker met à jour le projet ou les réponses dans la conversation

Un collègue décide s’il doit répondre dans le panneau de conversation ou modifier le projet en fonction de ce que vous demandez. Pour plus d’informations, voir [Mettre à jour un projet](#update-a-project) et [Poser des questions sur un projet](#ask-questions-about-a-project).

Vous pouvez également être explicite sur ce que vous souhaitez que Coworker fasse. Par exemple, vous pouvez utiliser des expressions telles que _dans le chat_ ou _dites-le moi simplement_ pour obtenir une réponse dans le panneau de chat, ou des expressions telles que _ajouter au projet_ ou _dans ce tableau_ pour mettre à jour le projet.

## Utiliser un collègue avec vos projets

Un collègue peut voir chaque panneau et tableau dans le projet ouvert. Vous pouvez demander à un collègue de répondre à des questions sur le projet ou de vous aider à le mettre à jour.

>[!TIP]
>
>Vous pouvez interrompre Coworker ou mettre à jour le projet à tout moment :
>
>* **Diriger ou arrêter une tâche** : pendant que le collègue travaille, appuyez sur **Maj+Entrée** pour lui donner plus de direction, ou appuyez sur **Échap** pour l’arrêter.
>
>* **Apporter des mises à jour à un projet dans Workspace** : si vous modifiez le projet pendant que Coworker travaille, Coworker reconnaît vos modifications.

### Mettre à jour un projet

Lorsque vous demandez à un collègue de créer ou de modifier quelque chose dans le projet, ce dernier met à jour le projet en conséquence. Cela inclut les requêtes qui commencent par des mots tels que _ajouter_, _créer_, _modifier_, _ventiler_, _modifier_ et _comparer_. Par exemple, vous pouvez demander à un collègue d’ajouter des panneaux et des tableaux, de ventiler des données ou de créer des segments.

1. Dans Customer Journey Analytics, ouvrez un projet Workspace existant ou créez-en un.

1. **[ESPACE RÉSERVÉ : comment ouvrir le panneau Collègue, comme le nom et l’emplacement de l’icône. Ajoutez une capture d’écran.]**

1. Dans le panneau de conversation, décrivez ce que vous souhaitez que Coworker fasse.

   Le tableau suivant répertorie des exemples d’invites.

   | Invite | Ce que fait un collègue |
   | --- | --- |
   | _Afficher les sessions par page pour le mois dernier_ | Ajoute un nouveau panneau à structure libre avec la dimension, la mesure et la période que vous spécifiez. Les panneaux existants ne sont pas remplacés. |
   | _Ventilez ce tableau par appareil_ | Ajoute la répartition au tableau que vous avez référencé. |
   | _Dans ce tableau, ajoutez une comparaison avec le mois dernier_ | Ajoute une colonne de comparaison au tableau que vous avez référencé. |
   | _Remplacez la période de ce panneau par le mois dernier_ | Met à jour la période du panneau. |
   | _Transformer ce tableau en graphique linéaire_ | Modifie le type de visualisation du panneau. |
   | _Renommez ce panneau en Performances mobiles_ | Renomme le panneau. |
   | _Appliquer le segment Utilisateurs mobiles à ce panneau_ | Applique le segment existant au panneau. Mon collègue ne connaît pas la définition de segment. Vérifiez donc que le segment contient ce que vous attendiez. |
   | _Créez un segment pour les visiteurs du Canada_ | Crée le segment et l’ajoute au projet. Le segment apparaît dans la liste des composants après l’actualisation de la page. |
   | _Copiez le segment Visiteurs canadiens et remplacez-le par Visiteurs mexicains_ | Crée une copie du segment avec la logique mise à jour et l’ajoute au projet. |
   | _Créer une période pour les 6 dernières semaines_ | Crée la période. La période apparaît dans la liste des composants sans actualisation. |
   | _Créer une mesure calculée pour le chiffre d’affaires par session_ | Crée la mesure calculée. Collègue peut créer des mesures calculées simples. |
   | _Ajoutez à ce panneau une description qui explique la baisse du nombre de visites_ | Ajoute la description au panneau. |
   | _Ajoutez une visualisation Texte avec les informations clés_ | Ajoute une visualisation Texte contenant les informations au projet. |
   | _Créez un projet avec des panneaux pour le trafic, la conversion et le chiffre d’affaires_ | Crée un projet avec un panneau pour chaque zone que vous décrivez. |
   | _Copiez ce projet et adaptez-le à la région EMEA_ | Crée une copie du projet et l’adapte à la région que vous spécifiez. |
   | _Enregistrer le projet_ | Enregistre le projet. |
   | _Annuler la répartition ajoutée_ | Annule la modification que vous spécifiez. |
   | _Supprimer les anciens panneaux_ | Répertorie les panneaux qu’il prévoit de supprimer et attend votre confirmation avant de les supprimer. |

1. Passez en revue les modifications apportées par Coworker au projet. Pour plus d&#39;informations, voir [Vérifier les résultats d&#39;un collègue](#verify-coworker-results).

### Poser des questions sur un projet

Lorsque vous posez des questions sur un projet, Coworker répond dans le panneau de conversation. Cela inclut des demandes telles que _expliquer_, _résumer_, _discuter_ et _en savoir plus_. Les résultats de l’analyse des causes profondes et les compétences similaires restent également dans le panneau de conversation jusqu’à ce que vous demandiez à votre collègue de les ajouter au projet.

1. Dans Customer Journey Analytics, ouvrez un projet Workspace existant ou créez-en un.

1. **[ESPACE RÉSERVÉ : comment ouvrir le panneau Collègue, comme le nom et l’emplacement de l’icône. Ajoutez une capture d’écran.]**

1. Dans le panneau de conversation, décrivez ce que vous souhaitez que Coworker fasse.

   Le tableau suivant répertorie des exemples d’invites.

   | Invite | Ce que fait un collègue |
   | --- | --- |
   | _Résumer ce projet_ | Fournit un résumé dans le panneau de conversation et propose de l’ajouter au projet sous forme de visualisation Texte. |
   | _Obtenez des informations sur ce projet_ | Fournit des informations dans le panneau de conversation et propose d’ajouter les résultats au projet. |
   | _Signaler toute anomalie dans ce panneau_ | Décrit les anomalies dans le panneau de conversation. Si vous demandez à un collègue d’afficher des anomalies sur une visualisation, celles-ci peuvent ne pas apparaître. Voir [Limites actuelles](#current-limitations). |
   | _Effectuer une analyse des causes profondes de la baisse du nombre de visites sur mobile_ | Fournit l’analyse dans le panneau de conversation et propose d’ajouter les résultats au projet. |
   | _Comment appliquer une couleur aux cellules en fonction de leurs valeurs ?_ | Décrit les étapes du panneau de conversation. |
   | _Explication de la mesure Taux de rebond_ | Décrit le composant dans le panneau de conversation. L’explication ne provient pas du [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md). La prise en charge des définitions de dictionnaire de données est prévue pour une version ultérieure. |

1. Examinez la réponse fournie par Coworker. Pour plus d&#39;informations, voir [Vérifier les résultats d&#39;un collègue](#verify-coworker-results).

## Vérifier les résultats du collaborateur

Coworker vous aide à vérifier l&#39;exactitude de ses résultats. Gardez les points suivants à l’esprit lorsque vous les examinez :

* **Le collaborateur montre son travail** : les segments, mesures et filtres que le collaborateur utilise pour répondre à une question sont ajoutés au projet afin que vous puissiez les vérifier.

* **Clarification des questions** : lorsqu’une demande est vague ou correspond à plusieurs composants, un collègue pose une question de clarification ou suggère des options parmi lesquelles choisir. Par exemple, si plusieurs mesures correspondent au nom que vous avez utilisé, Coworker suggère les mesures correspondantes.

* **Notes de qualité des données** : le collègue inclut des notes de qualité des données dans ses réponses. Par exemple, si vous comparez un mois qui vient juste de commencer à un mois complet, Coworker vous indique que la comparaison est basée sur des données partielles.

## Limites actuelles

L’expérience intégrée au produit pour Coworker présente les limites suivantes :

* **Définitions de segment** : lorsque vous faites référence à un segment par son nom, Coworker ne connaît pas la définition du segment. Un collègue peut déduire ce que contient le segment en fonction de son nom. Vérifiez la définition de segment avant de vous fier aux résultats.

* **Dictionnaire de données** : le collègue n’est pas connecté au [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md). Il ne peut pas utiliser les définitions du dictionnaire de données pour expliquer les mesures et les dimensions.

* **Composants approuvés** : Mon collègue ne donne pas la préférence aux composants approuvés par rapport aux composants similaires.

* **Copie de panneaux** : un collègue ne peut pas copier ni dupliquer un panneau.

* **Nouveaux segments dans la liste des composants** : les segments créés par Coworker n’apparaissent pas dans la liste des composants dans le rail de gauche tant que vous n’avez pas actualisé la page. Les périodes créées par Coworker n’ont pas été actualisées.

* **Détection des anomalies** : lorsque vous demandez à un collègue d’afficher des anomalies sur une visualisation, les anomalies peuvent ne pas apparaître.

* **Historique des conversations** : les conversations sont enregistrées pour chaque utilisateur et non pour le projet. Les autres utilisateurs qui ouvrent le projet ne peuvent pas voir votre conversation avec Coworker. Pour partager du contexte avec d’autres utilisateurs, ajoutez-le aux descriptions des panneaux du projet.

* **Plusieurs onglets de navigateur** : si vous ouvrez la même conversation dans plusieurs onglets de navigateur, il se peut que Coworker perde la trace de ce sur quoi elle travaille.

* **Langues autres que l’anglais** : dans les vues de données qui utilisent une langue autre que l’anglais, Coworker peut utiliser une combinaison de l’anglais et de la langue de la vue de données dans ses réponses.


