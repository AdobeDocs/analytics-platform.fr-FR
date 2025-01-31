---
title: Présentation de Customer Journey Analytics
description: Découvrez comment Customer Journey Analytics vous permet d’utiliser Analysis Workspace avec les données d’Experience Platform.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 93%

---

# Vue d’ensemble de Customer Journey Analytics

Customer Journey Analytics est une solution d’analyse Adobe qui vous permet d’utiliser toute la puissance d’Analysis Workspace avec les données d’Adobe Experience Platform. Elle permet de ventiler, filtrer, interroger et visualiser des données sur plusieurs années, en conjonction avec la capacité de Platform à contenir toutes sortes de schémas et types de données. Grâce au **Modèle de données d’expérience (XDM)**, les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. Le **service de requêtes d’Adobe Experience Platform** vous permet d’utiliser des outils et des frameworks compatibles avec SQL pour interroger et manipuler toutes vos données.

L’architecture de haut niveau de Customer Journey Analytics est présentée ici :

![Architecture de Customer Journey Analytics expliquée dans cette section.](assets/cja-architecture.png)


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analyse du Parcours client : Analytics for the Experience Business](https://video.tv.adobe.com/v/30090/?quality=12&learn=on){target="_blank"} pour une vidéo d’introduction à Customer Journey Analytics.

>[!ENDSHADEBOX]


## Comparaison entre Customer Journey Analytics et Adobe Analytics

Customer Journey Analytics étend la portée d’Adobe Analytics en offrant des fonctionnalités cross-canal simples d’utilisation et en supprimant les restrictions des versions précédentes d’Adobe Analytics. Quelques améliorations notables ont été apportées :

* **Variables et événements illimités** : Les concepts d’eVars, de props et d’événements n’existent plus. Les données sont principalement axées sur les dimensions et les mesures. Les jeux de données peuvent comporter un nombre illimité de dimensions et de mesures uniques.
* **Valeurs uniques illimitées** : Adobe Experience Platform nʼest soumis à aucune limitation de valeurs uniques.
* **Modification des données historiques** : avec Adobe Experience Platform, les données peuvent être supprimées ou corrigées.
* **Données cross-suites de rapports** : les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Platform.

>[!TIP]
>
>Si vous utilisez Adobe Analytics et souhaitez utiliser vos données Adobe Analytics dans Customer Journey Analytics, reportez-vous au guide de démarrage rapide [Ingestion et utilisation de données à partir de la version standard d’Adobe Analytics](../data-ingestion/analytics.md) dans le cadre de la section [Ingestion des données](../data-ingestion/data-ingestion.md).

La première version de Customer Journey Analytics inclut de nombreuses fonctionnalités incluses dans Adobe Analytics. Pour obtenir une liste complète, voir [Support pour les fonctionnalités Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## Cas d’utilisation clés

Customer Journey Analytics vous permet d’effectuer les opérations suivantes :

* **Observez le client dans un contexte de parcours** : Vous pouvez afficher et analyser les données de manière séquentielle, sur plusieurs canaux. Les données de votre centre d’appels, de systèmes de points de vente et de propriétés en ligne peuvent être combinées en une seule vue de rapports.
* **Mettez les informations à la disposition de tous** : Démocratisez l’accès aux données et permettez à un plus grand nombre de personnes de prendre des décisions commerciales avec des informations dérivées des données. Toute personne de l’entreprise responsable de tout aspect de l’expérience client peut prendre de vraies décisions plus rapidement, en fonction de données plus complètes.
* **Exploitez la puissance de la science des données pour vos analystes** : Customer Journey Analytics permet aux êtres humains normaux d’utiliser la science des données pour exploiter des informations et analyses approfondies.
* **Visualisez et interagissez avec vos jeux de données à l’aide de la création de rapports à la demande** : l’espace de travail peut utiliser n’importe quel jeu de données d’Adobe Experience Platform conforme à certaines règles de base.
* **Afficher des données non-Web** : Espace de travail ne se limite plus à une définition rigide d’un « accès » ou d’un « événement ». Les schémas personnalisés permettent un contrôle complet des données et des définitions.
* **Contrôlez davantage vos manipulations de données** : modifiez les données que vous avez chargées, créez des jeux de données et importez-les dans l’espace de travail. Adobe Experience Platform fournit des outils de requêtes, d’extraction, de transformation et de chargement via le service de requêtes Experience Platform.

## Conditions préalables

Avant de pouvoir démarrer avec Customer Journey Analytics, les conditions préalables suivantes doivent être remplies :

* Votre entreprise a un contrat actif avec Adobe Analytics pour Select, Prime ou Ultimate avec le module complémentaire Customer Journey Analytics. Si vous ne savez pas quel type de contrat vous avez ou si vous ne savez pas si vous disposez du module complémentaire Customer Journey Analytics, contactez votre équipe Adobe en charge des comptes.
* Votre entreprise a été configurée pour Adobe Experience Platform.
* Vous pouvez également acheter Customer Journey Analytics en tant que produit autonome, sans avoir besoin d’Adobe Analytics.

## Contrôle d’accès

Voir [Contrôle d’accès](/help/technotes/access-control.md).

## Mises à jour de terminologie

Plusieurs fonctionnalités de Customer Journey Analytics ont été renommées, par rapport à Adobe Analytics traditionnel, afin de s’aligner sur les normes de l’industrie. La terminologie mise à jour comprend :

* Les segments sont désormais appelés « Filtres ».
* Les suites de rapports virtuelles sont désormais appelées « Vues de données ».
* Les classifications sont désormais appelées « Jeux de données de recherche ».
* Les attributs du client sont désormais appelés « Jeux de données de profil ».
* Les conteneurs d’accès sont désormais appelés conteneurs « Événements ».
* Les conteneurs Visite sont désormais appelés conteneurs « Session ».
* Les conteneurs Visiteur sont désormais appelés conteneurs « Personne ».

## Autres fonctionnalités intégrées à Adobe Experience Platform

Customer Journey Analytics est l’une des fonctionnalités qui dépendent de la plateforme Adobe Experience Platform. Plusieurs autres fonctionnalités, également conçues sur Experience Platform, vous permettent de tirer le meilleur parti de vos données.

Adobe Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système et d’appliquer la science des données et le machine learning afin d’améliorer la conception et la diffusion d’expériences personnalisées. Les données client de la plateforme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plateforme, voir [Présentation de l’architecture de la plateforme Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=fr).

De l’ingestion de données à l’accès SQL direct, plusieurs composantes de la plateforme Experience Platform sont au cœur de Customer Journey Analytics et complètent ce dernier :

* [Service de requêtes Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) : utilisez du SQL standard pour récupérer des données d’Adobe Experience Platform, telles que des données de solution Adobe, des données propriétaires du client ou toute autre donnée de Platform. Il s’agit d’un outil sans serveur qui vous permet de joindre n’importe quel jeu de données et de capturer les résultats de la requête sous la forme d’un nouveau jeu de données à utiliser dans les rapports ou pour ingestion dans Profile Service. Vous pouvez utiliser le service de requêtes Experience Platform pour construire des écosystèmes d’analyse de données, créant ainsi une image des consommateurs sur leurs différents canaux d’interaction. Ces canaux peuvent inclure les systèmes de points de vente, Web, Mobile, CRM, etc.
* [Profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) :
* [Service d’identités](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr)

## Vidéos


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilisation des données dans Customer Journey Analytics](https://video.tv.adobe.com/v/32112/?quality=12&learn=on){target="_blank"} pour une présentation vidéo sur l’utilisation des données dans Customer Journey Analytics.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Architecture et intégration](https://video.tv.adobe.com/v/32483/?quality=12&learn=on){target="_blank"} pour une vidéo d’introduction sur l’architecture et l’intégration de Customer Journey Analytics.

>[!ENDSHADEBOX]


