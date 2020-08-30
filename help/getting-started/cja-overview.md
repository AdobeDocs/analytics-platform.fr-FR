---
title: Présentation de Customer Journey Analytics
description: Introduction à Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 100%

---


# Présentation de Customer Journey Analytics

Customer Journey Analytics est une fonctionnalité d’Analytics qui vous permet d’utiliser la puissance d’Analysis Workspace avec les données d’Adobe Experience Platform. Elle permet de ventiler, filtrer, interroger et visualiser des données sur plusieurs années, en conjonction avec la capacité de Platform à contenir toutes sortes de schémas et types de données. Grâce au **Modèle de données d’expérience (XDM)**, les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. **Experience Query Services** vous permet d’utiliser des outils et des structures compatibles avec SQL pour interroger et manipuler toutes vos données.

## Comparaison de CJA à l’Adobe Analytics traditionnel

Customer Journey Analytics étend la portée d’Analytics en offrant des fonctionnalités cross-canal simples d’utilisation et en supprimant les restrictions des versions précédentes d’Adobe Analytics. Quelques améliorations notables ont été apportées :

* **Variables et événements illimités** : Les concepts d’eVars, de props et de événements n’existent plus. Les données sont principalement axées sur les dimensions et les mesures. Les jeux de données peuvent comporter un nombre illimité de dimensions et de mesures uniques.
* **Valeurs uniques illimitées** : Adobe Experience Platform ne comporte aucune limite unique, alors que les suites de rapports traditionnelles limitent les valeurs uniques à 500 000.
* **Modification des données historiques** : Avec Adobe Experience Platform, les données peuvent être supprimées ou corrigées.
* **Données cross-suites de rapports** : Les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Platform.

La première version de Customer Journey Analytics inclut de nombreuses fonctionnalités incluses dans Analysis Workspace. Pour obtenir une liste complète, voir [Support pour les fonctionnalités Customer Journey Analytics](cja-aa.md).

## Comparaison de CJA avec Cross-Device Analytics (Analyses cross-appareils)

[Cross-Device Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/components/cda/cda-home.html) s’intègre au service d’identité de la plate-forme Adobe Experience Platform, en utilisant le graphique Co-op ou le graphique Private, afin d’identifier comment les appareils numériques font correspondre les utilisateurs. Cross-Device Analytics est disponible pour les clients d’Adobe Analytics Ultimate.

CJA s’intègre aux jeux de données Adobe Experience Platform et permet l’analyse cross-canal dans Analysis Workspace. Bien que CJA ne s’intègre pas encore aux graphiques d’identité Co-op ou Private, vous pouvez « amener votre propre ID » (système « bring your own ID ») pour joindre des jeux de données, et ces jeux de données peuvent aller au-delà des données numériques pour inclure des points de contact en ligne et hors ligne. Les conditions préalables pour CJA sont décrites plus en détail ci-dessous.

## Cas d’utilisation clés

Customer Journey Analytics vous permet d’effectuer les opérations suivantes :

* **Observez le client dans un contexte de parcours** : Vous pouvez afficher et analyser les données de manière séquentielle, sur plusieurs canaux. Les données de votre centre d’appels, de systèmes de points de vente et de propriétés en ligne peuvent être combinées en une seule vue de rapports.
* **Mettez les informations à la disposition de tous** : Démocratisez l’accès aux données et permettez à un plus grand nombre de personnes de prendre des décisions commerciales avec des informations dérivées des données. Toute personne de l’entreprise responsable de tout aspect de l’expérience client peut prendre de vraies décisions plus rapidement, en fonction de données plus complètes.
* **Exploitez la puissance de la science des données pour vos analystes** : Customer Journey Analytics permet aux êtres humains normaux d’utiliser la science des données pour exploiter des informations et analyses approfondies.
* **Visualisez et interagissez avec vos jeux de données à l’aide de rapports ad hoc** : Workspace peut utiliser n’importe quel jeu de données d’Adobe Experience Platform conforme à certaines règles de base.
* **Afficher des données non-Web** : Workspace ne se limite plus à une définition rigide d’un « accès » ou d’un « événement ». Les schémas personnalisés permettent un contrôle complet des données et des définitions.
* **Contrôlez davantage vos manipulations de données** : Modifiez les données que vous avez transférées, créez de nouveaux jeux de données et importez-les dans Workspace. Adobe Experience Platform fournit des outils d’interrogation, d’extraction, de transformation et de transfert via l’Experience Cloud Query Service (Service d’interrogation Experience Cloud).

## Conditions préalables

Avant de pouvoir démarrer avec Customer Journey Analytics, les conditions préalables suivantes doivent être remplies :

* Votre entreprise a un contrat actif avec Adobe Analytics pour Select, Prime ou Ultimate avec le module complémentaire Customer Journey Analytics. Si vous ne savez pas quel type de contrat vous avez ou si vous ne savez pas si vous disposez du module complémentaire CJA, contactez le gestionnaire de compte de votre organisation.
* Votre entreprise a été configurée pour Adobe Experience Platform.

## Autorisations d’accès utilisateur

Pour créer des connexions, ajouter des jeux de données, etc., vous avez besoin des autorisations suivantes dans l’[Admin Console](https://adminconsole.adobe.com/enterprise/) :

* Pour gérer les jeux de données dans Experience Platform, vous devez faire partie d’un Profil de produits Platform qui vous accorde l’autorisation « Gérer les jeux de données ». Pour plus d’informations, voir [Contrôle d’accès dans Adobe Experience Platform](https://docs.adobe.com/content/help/fr-FR/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Pour créer une connexion à un jeu de données Platform, vous devez faire partie d’un Profil de produits de plateforme qui vous accorde les autorisations suivantes :
   * Afficher schémas
   * Afficher jeux de données
   * Gérer les Espaces de nommage d’identité
   * Afficher les sandbox
* Pour accéder à Customer Journey Analytics ou établir une connexion, vous devez également être ajouté à un Profil produit Customer Journey Analytics dans l’[Admin Console](https://adminconsole.adobe.com/enterprise/).

### Mises à jour de terminologie

Plusieurs fonctions de CJA ont été renommées pour être conformes aux normes de l’industrie. Voici quelques noms mis à jour :

* Les segments sont désormais appelés « Filtres ».
* Les suites de rapports virtuelles sont désormais appelées « Vues ».
* Les classifications sont désormais appelées « Jeux de données de recherche ».
* Les attributs du client sont désormais appelés « Jeux de données de profil ».
* Les conteneurs d’accès sont désormais appelés conteneurs « Événements ».
* Les conteneurs Visite sont désormais appelés conteneurs « Session ».
* Les conteneurs Visiteur sont désormais appelés conteneurs « Personne ».

## Autres fonctionnalités intégrées à Adobe Experience Platform

Customer Journey Analytics est l’une des fonctionnalités qui dépendent de la plate-forme Adobe Experience Platform. Plusieurs autres fonctionnalités, également conçues sur Platform, vous permettent de tirer le meilleur parti de vos données.

Adobe Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système et d’appliquer la science des données et l’apprentissage automatique afin d’améliorer la conception et la diffusion d’expériences personnalisées. Les données client de la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plate-forme, voir [Présentation de l’architecture de la plate-forme Adobe Experience Platform](https://docs.adobe.com/content/help/fr-FR/experience-platform/landing/home.translate.html).

De l’ingestion de données à l’accès SQL direct, plusieurs composants de la plate-forme Experience Platform sont au cœur de Customer Journey Analytics et agissent en conjonction avec ce dernier :

* [Query Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/query/home.translate.html) : Utilisez du SQL standard pour récupérer les données d’Adobe Experience Platform, telles que les données de la solution Adobe, les données propriétaires du client ou toute autre donnée de Platform. Il s’agit d’un outil sans serveur qui vous permet de joindre n’importe quel jeu de données et de capturer les résultats de la requête sous la forme d’un nouveau jeu de données à utiliser dans les rapports, Data Science Workspace ou pour ingestion dans Profile Service. Vous pouvez utiliser Query Service pour construire des écosystèmes d’analyse de données, créant ainsi une image des consommateurs sur leurs différents canaux d’interaction. Ces canaux peuvent inclure les systèmes de points de vente, Web, Mobile, CRM, etc.
* [Profil client en temps réel](https://docs.adobe.com/content/help/fr-FR/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md) :
* [Service d’identité](https://docs.adobe.com/content/help/fr-FR/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md) :
* [Data Science Workspace](https://docs.adobe.com/content/help/fr-FR/experience-platform/data-science-workspace/home.translate.html) dans l’option « développeur » : vous pouvez utiliser une intelligence artificielle (IA) prédéfinie et des modèles d’apprentissage automatique dans Adobe Experience Platform pour influencer divers points du parcours des clients. En découvrant des informations cachées, vous pouvez formuler de meilleures prédictions tout au long du parcours des clients, suggérer les meilleures étapes à suivre ou automatiser des processus lourds.
