---
title: Mettre à niveau Adobe Analytics vers Customer Journey Analytics
description: En savoir plus sur les étapes recommandées lors de la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 8%

---

# Préparation de votre organisation à la mise à niveau vers Customer Journey Analytics

Une partie d’une mise à niveau réussie (comme décrit dans [Mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)) consiste à préparer votre entreprise en se concentrant sur certaines considérations opérationnelles. Pour préparer votre organisation, il est recommandé de :

* Obtenir l’adhésion et l’alignement des principales parties prenantes

* Définir et documenter vos objectifs

* Fixer des échéanciers réalistes et réfléchis

* Définir clairement les responsabilités des contributeurs

## Adhésion et alignement des parties prenantes

Les principales parties prenantes et les décideurs de votre entreprise doivent s’aligner sur votre mise à niveau vers Customer Journey Analytics.

Les sections suivantes décrivent les moyens d’obtenir l’alignement des parties prenantes.

### Concentrez-vous sur la valeur

Insistez sur la valeur que Customer Journey Analytics apportera à votre entreprise et sur la manière dont elle accélérera la réalisation de vos objectifs commerciaux.

Le tableau suivant répertorie certaines fonctionnalités clés que vous pouvez mettre en évidence.

| Fonctionnalité | Avantage | Exemple |
|---------|----------|---------|
| **[Adaptation à tous les types de données](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home)** | Customer Journey Analytics est associé à la capacité d’Experience Platform à contenir tous les types et schémas de données. | Une organisation de vente au détail peut fournir une visibilité sur l’ensemble du parcours client en intégrant les types de données suivants dans une vue unique : <ul><li>Transactions de parcours de navigation web</li><li>Transactions sur application mobile</li><li>Transactions en magasin</li><li>Données de gestion de la relation client et de fidélité</li></ul> |
| **[Analyse cross-canal](/help/use-cases/cross-channel/cross-channel.md)** | Permet d’obtenir une vue consolidée unique du comportement des clients sur différents canaux en unifiant les données de diverses propriétés web, mobiles et hors ligne. | Une organisation de vente au détail qui collecte des données à partir de plusieurs canaux peut effectuer le type d’analyse suivant :<p>Un acheteur clique sur une annonce de référencement payant, navigue sur le jean en ligne, reçoit une notification push, puis effectue ses achats en magasin deux jours plus tard. Cette perspective unifiée permet une attribution cross-canal précise, montrant comment les points de contact numériques contribuent aux ventes en magasin. Il prend également en charge une segmentation plus précise, comme le ciblage des clients « parcourus en ligne, achetés en magasin » avec des offres personnalisées. En outre, il fournit un reporting clair sur le chiffre d’affaires pour tous les canaux dans un seul tableau de bord, remplaçant les informations fragmentées et compartimentées par une compréhension holistique du comportement des clients. |
| **[Traitement de la période de rapport](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Appliquez des paramètres rétroactifs et créez plusieurs versions de la persistance des variables sans avoir à modifier la manière dont les données sous-jacentes sont collectées. | Customer Journey Analytics vous permet de créer et d’ajuster des mesures, des dimensions et des modèles d’attribution à la volée sans avoir à réingérer ou à traiter de nouvelles données. Ainsi, une entreprise de vente au détail pourrait voir comment une campagne sociale récente a influencé les ventes en ligne et en magasin sans avoir à demander à l’ingénierie de recréer des jeux de données. Ils pouvaient modifier instantanément le modèle d’attribution de dernière touche en première touche ou l’attribution personnalisée basée sur des règles. |
| **[Analyse du contenu](/help/content-analytics/content-analytics.md)** | Aide les professionnels du marketing à comprendre l’impact du contenu sur les indicateurs de performances clés définis par une entreprise. En plus des données comportementales, Content Analytics collecte des données sur la manière dont le contenu est utilisé et sur son impact. | En intégrant des données web, des applications, des e-mails et même en magasin, une entreprise de vente au détail pourrait voir exactement comment chaque élément de contenu numérique qu’elle crée contribue au parcours et à la conversion des clients. <p>L&#39;organisation de vente au détail a pu constater qu&#39;un « Guide de style du denim d&#39;été » sur une plateforme de médias sociaux populaire entraîne un engagement élevé parmi les membres du programme de fidélité, et que ces membres sont 40 % plus susceptibles d&#39;acheter du denim en magasin d&#39;ici une semaine.</p> |

### Nommer un sponsor exécutif

Recherchez et nommez un sponsor exécutif au sein de votre organisation. Ce sponsor exécutif doit comprendre comment Customer Journey Analytics accélérera l’atteinte de vos objectifs commerciaux.

Le sponsor exécutif est essentiel, car il :

* Champion Customer Journey Analytics au sein de l’organisation

* Suppression des obstacles

* Approuver les ressources

### Obtenez l’appui des principaux dirigeants de votre organisation

Avec l’aide de votre sponsor exécutif, obtenez le soutien d’autres dirigeants clés de votre entreprise. Il est essentiel que les responsables des services suivants de votre entreprise comprennent les avantages de Customer Journey Analytics et qu’ils soient prêts à contribuer à une mise en œuvre réussie :

* Analytics  

* Marketing

* IT

* Mentions légales et conformité

* Unités commerciales individuelles

## Développement d’un plan de mise à niveau et de communication

### Développez un plan de mise à niveau et distribuez-le aux parties prenantes.

Un plan de mise à niveau peut inclure les informations suivantes :

* Description claire de la raison pour laquelle la mise à niveau est en cours. Par exemple, décrivez les avantages pour les utilisateurs et pour l’organisation ou l’entreprise dans son ensemble. Pour plus d’informations sur les avantages, voir [Focus on value](#focus-on-value).

* Calendrier général, par exemple la date prévue pour le début de la mise à niveau, plan des jalons clés et estimation de la date prévue pour la fin de la mise à niveau.

* Une indication du moment où les utilisateurs peuvent commencer à suivre des formations officielles pour apprendre à utiliser Customer Journey Analytics. Pour plus d’informations, voir [Formation des utilisateurs finaux dans l’ensemble de votre organisation](#train-end-users-throughout-your-organization).

* Informations sur les personnes qui dirigent la mise à niveau et sur la manière ou le moment où les personnes peuvent poser des questions.

### Créer un plan de communication

Un plan de communication peut inclure les considérations suivantes :

* Une cadence définie quant au moment où les communications seront envoyées aux parties prenantes et aux utilisateurs

* Un aperçu du type d’informations qui sera envoyé

* Plan indiquant qui enverra les communications

* Des boucles de commentaires définies pour permettre aux parties prenantes et aux utilisateurs de poser des questions ou de fournir des commentaires

## Évaluation et audit de votre implémentation Adobe Analytics

Procédez à une évaluation et à un audit approfondis de votre implémentation d’Adobe Analytics, en vous concentrant sur les domaines clés suivants :

* Utilisateurs actuels

* Accès utilisateur

* Projets

* Processus métier

* Composants personnalisés

Consultez les ressources suivantes pour faciliter la collecte de ces informations :

* [Inventaire Analytics](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/analytics-inventory)

  Fournit des informations sur le nombre de projets, de segments, de mesures calculées, de suites de rapports et d’utilisateurs au sein de votre organisation.

* [Préparez la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Fournit des informations sur la façon dont vous pouvez vous préparer à migrer des composants, des projets et des utilisateurs.

## Identifier les champions et les utilisateurs précoces

Identifiez des champions dans l’ensemble de votre organisation. Ces champions devraient être :

* Utilisateurs experts d’Adobe Analytics

* Aptitude à maîtriser rapidement Customer Journey Analytics

* Disponible pour être un conseiller et une aide pour les autres à mesure que Customer Journey Analytics est déployé plus largement

## Former les utilisateurs finaux dans l’ensemble de votre organisation

* Proposez une formation pratique axée sur les différences entre les modèles de données, les paradigmes de création de rapports et les nouvelles fonctionnalités de Customer Journey Analytics.

* Proposez des sessions en direct (ateliers ou heures de bureau) et des ressources à la demande (tutoriels vidéo, pages wiki dynamiques et documentation interne).

* Dirigez les utilisateurs vers des formations, des tutoriels et de la documentation pertinents sur Experience League.

  Les ressources suivantes peuvent vous aider à commencer :

   * [Tutoriels Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Qu’est-ce que Customer Journey Analytics ?](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Présentation de Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Prise en charge des fonctionnalités de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)

## Suivez les étapes de mise à niveau recommandées

Lorsque vous êtes prêt à lancer le processus de mise à niveau, suivez les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement dans le Guide de mise à niveau de Customer Journey Analytics. Pour accéder au guide à partir de Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Espace de travail]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.

