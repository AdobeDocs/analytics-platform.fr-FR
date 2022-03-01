---
title: Présentation de Customer Journey Analytics
description: Découvrez comment Customer Journey Analytics vous permet d’utiliser Analysis Workspace avec les données d’Experience Platform.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: e397ff4de0f65ebb0264eac3813046452c572256
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 87%

---

# Présentation de Customer Journey Analytics

Customer Journey Analytics est une fonctionnalité d’Analytics qui vous permet d’utiliser la puissance d’Analysis Workspace avec les données d’Adobe Experience Platform. Elle permet de ventiler, filtrer, interroger et visualiser des données sur plusieurs années, en conjonction avec la capacité de Platform à contenir toutes sortes de schémas et types de données. Grâce au **Modèle de données d’expérience (XDM)**, les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. **Experience Query Services** vous permet d’utiliser des outils et des structures compatibles avec SQL pour interroger et manipuler toutes vos données.

L’architecture de haut niveau de CJA est présentée ici :

![architecture](assets/cja-architecture.png)

Voici un aperçu vidéo du Customer Journey Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Comparaison de CJA à l’Adobe Analytics traditionnel

Customer Journey Analytics étend la portée d’Adobe Analytics en offrant des fonctionnalités cross-canal simples d’utilisation et en supprimant les restrictions des versions précédentes d’Adobe Analytics. Quelques améliorations notables ont été apportées :

* **Variables et événements illimités** : Les concepts d’eVars, de props et d’événements n’existent plus. Les données sont principalement axées sur les dimensions et les mesures. Les jeux de données peuvent comporter un nombre illimité de dimensions et de mesures uniques.
* **Valeurs uniques illimitées** : Adobe Experience Platform nʼest soumis à aucune limitation de valeurs uniques.
* **Modification des données historiques** : Avec Adobe Experience Platform, les données peuvent être supprimées ou corrigées.
* **Données cross-suites de rapports** : Les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Platform.

La première version de Customer Journey Analytics inclut de nombreuses fonctionnalités incluses dans Analysis Workspace. Pour obtenir une liste complète, voir [Support pour les fonctionnalités Customer Journey Analytics](cja-aa.md).

## Comparaison de CJA avec Analytics sur l’ensemble des appareils

[Analyses entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) s’intègre à [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en), à l’aide du graphique Co-op ou du graphique Privé, pour identifier la manière dont les périphériques numériques sont mappés aux personnes. Cross-Device Analytics est disponible pour les clients d’Adobe Analytics Ultimate.

CJA, quant à lui, s’intègre aux jeux de données Adobe Experience Platform et permet l’analyse cross-canal dans Analysis Workspace. Bien que CJA ne s’intègre pas encore aux graphiques d’identités Co-op ou Private, vous pouvez &quot;amener votre propre ID&quot; pour joindre des jeux de données. Ces jeux de données peuvent aller au-delà des données numériques pour inclure des points de contact en ligne et hors ligne. Les conditions préalables pour CJA sont décrites plus en détail ci-dessous.

## Cas d’utilisation clés

Customer Journey Analytics vous permet d’effectuer les opérations suivantes :

* **Observez le client dans un contexte de parcours** : Vous pouvez afficher et analyser les données de manière séquentielle, sur plusieurs canaux. Les données de votre centre d’appels, de systèmes de points de vente et de propriétés en ligne peuvent être combinées en une seule vue de rapports.
* **Mettez les informations à la disposition de tous** : Démocratisez l’accès aux données et permettez à un plus grand nombre de personnes de prendre des décisions commerciales avec des informations dérivées des données. Toute personne de l’entreprise responsable de tout aspect de l’expérience client peut prendre de vraies décisions plus rapidement, en fonction de données plus complètes.
* **Exploitez la puissance de la science des données pour vos analystes** : Customer Journey Analytics permet aux êtres humains normaux d’utiliser la science des données pour exploiter des informations et analyses approfondies.
* **Visualisez et interagissez avec vos jeux de données à l’aide de rapports ad hoc** : Espace de travail peut utiliser n’importe quel jeu de données d’Adobe Experience Platform conforme à certaines règles de base.
* **Afficher des données non-Web** : Espace de travail ne se limite plus à une définition rigide d’un « accès » ou d’un « événement ». Les schémas personnalisés permettent un contrôle complet des données et des définitions.
* **Contrôlez davantage vos manipulations de données** : Modifiez les données que vous avez transférées, créez de nouveaux jeux de données et importez-les dans Espace de travail. Adobe Experience Platform fournit des outils d’interrogation, d’extraction, de transformation et de transfert via l’Experience Cloud Query Service (Service d’interrogation Experience Cloud).

## Conditions préalables

Avant de pouvoir démarrer avec Customer Journey Analytics, les conditions préalables suivantes doivent être remplies :

* Votre entreprise a un contrat actif avec Adobe Analytics pour Select, Prime ou Ultimate avec le module complémentaire Customer Journey Analytics. Si vous ne savez pas quel type de contrat vous avez, ou si vous ne savez pas si vous disposez du module complémentaire CJA, contactez le gestionnaire de compte de votre entreprise.
* Votre entreprise a été configurée pour Adobe Experience Platform.

## Autorisations d’accès administrateur

Pour créer des connexions, ajouter des jeux de données, etc., vous avez besoin des autorisations suivantes dans l’[Admin Console](https://adminconsole.adobe.com/enterprise/) :

* Pour accéder à Customer Journey Analytics ou établir une connexion, vous devrez être ajouté en tant quʼadministrateur au **produit Customer Journey Analytics** dans lʼ[Admin Console](https://adminconsole.adobe.com/enterprise/). Les autorisations suivantes sont accordées aux administrateurs de produits :
   * Créer/mettre à jour/supprimer des connexions ou des vues de données
   * Mettre à jour/supprimer des projets, filtres, mesures calculées ou filtres créés par dʼautres utilisateurs
   * Partager un projet d’espace de travail avec tous les utilisateurs
* Le simple fait de devenir administrateur de produit dans Customer Journey Analytics ne suffit pas à créer, mettre à jour ou supprimer une connexion. Pour créer une connexion à un jeu de données Experience Platform, vous avez également besoin d’autorisations Experience Platform. En particulier, vous devez faire partie d’un **profil de produit Experience Platform** qui vous donne les autorisations suivantes :
   * Afficher des schémas
   * Gérer des schémas
   * Afficher des espaces de noms d’identités
   * Afficher des jeux de données

Pour plus d’informations sur les autorisations Experience Platform, voir [Contrôle d’accès dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en).

>[!NOTE]
>
>Vous ne pouvez pas autoriser des mesures ou des dimensions individuelles dans Customer Journey Analytics, comme vous le pouvez dans Adobe Analytics traditionnel. Les mesures et dimensions peuvent être modifiées dans [vues de données](/help/data-views/data-views.md) et sont donc sujets à des modifications dans CJA, qui modifie également le reporting rétroactivement.

### Accès utilisateur

Les non-administrateurs de produit (utilisateurs) de Customer Journey Analytics ne peuvent pas afficher de vues de données ou de connexions, mais peuvent créer des filtres, des projets et des mesures calculées.

## Mises à jour de terminologie

Plusieurs fonctionnalités de CJA ont été renommées, par rapport à Adobe Analytics traditionnel, afin de s’aligner sur les normes de l’industrie. La terminologie mise à jour comprend :

* Les segments sont désormais appelés « Filtres ».
* Les suites de rapports virtuelles sont désormais appelées « Vues de données ».
* Les classifications sont désormais appelées « Jeux de données de recherche ».
* Les attributs du client sont désormais appelés « Jeux de données de profil ».
* Les conteneurs d’accès sont désormais appelés conteneurs « Événements ».
* Les conteneurs Visite sont désormais appelés conteneurs « Session ».
* Les conteneurs Visiteur sont désormais appelés conteneurs « Personne ».

## Autres fonctionnalités intégrées à Adobe Experience Platform

Customer Journey Analytics est l’une des fonctionnalités qui dépendent de la plate-forme Adobe Experience Platform. Plusieurs autres fonctionnalités, également conçues sur Experience Platform, vous permettent de tirer le meilleur parti de vos données.

Adobe Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système et d’appliquer la science des données et l’apprentissage automatique afin d’améliorer la conception et la diffusion d’expériences personnalisées. Les données client de la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plate-forme, voir [Présentation de l’architecture de la plate-forme Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

De l’ingestion de données à l’accès SQL direct, plusieurs composants de la plate-forme Experience Platform sont au cœur de Customer Journey Analytics et agissent en conjonction avec ce dernier :

* [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) : Utilisez du SQL standard pour récupérer les données d’Adobe Experience Platform, telles que les données de la solution Adobe, les données propriétaires du client ou toute autre donnée de Platform. Il s’agit d’un outil sans serveur qui vous permet de joindre n’importe quel jeu de données et de capturer les résultats de la requête sous la forme d’un nouveau jeu de données à utiliser dans les rapports, Data Science Workspace ou pour ingestion dans Profile Service. Vous pouvez utiliser Query Service pour construire des écosystèmes d’analyse de données, créant ainsi une image des consommateurs sur leurs différents canaux d’interaction. Ces canaux peuvent inclure les systèmes de points de vente, Web, Mobile, CRM, etc.
* [Profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) :
* [Service d’identité](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) :
* [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html?lang=en) dans l’option « développeur » : vous pouvez utiliser une intelligence artificielle (IA) prédéfinie et des modèles d’apprentissage automatique dans Adobe Experience Platform pour influencer divers points du parcours des clients. En découvrant des informations cachées, vous pouvez formuler de meilleures prédictions tout au long du parcours des clients, suggérer les meilleures étapes à suivre ou automatiser des processus lourds.

## Vidéos

* Utilisation des données en Customer Journey Analytics :

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Architecture et intégrations de Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

