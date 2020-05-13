---
title: Présentation de Customer Journey Analytics
description: Présentation des analyses de parcours client
translation-type: tm+mt
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 7%

---


# Présentation de Customer Journey Analytics

Customer Journey Analytics est une fonctionnalité d’analyse qui vous permet d’utiliser la puissance d’Analyse Workspace avec les données d’Adobe Experience Platform. Il peut ventiler, filtrer, requête et visualiser des années de données, et est combiné avec la capacité de Plateforme à contenir toutes sortes de schémas et types de données. Grâce au modèle de données d’ **expérience (XDM)**, les données peuvent être représentées et organisées de manière uniforme, prêtes à être combinées et explorées. **Experience Requête Services** vous permet d’utiliser des outils et des structures compatibles SQL pour requête et manipuler toutes vos données.

## Comparaison de CJA à Adobe Analytics traditionnel

Les analyses de parcours des clients étendent la portée d’Analytics en offrant des fonctionnalités intercanaux simples d’utilisation et en supprimant les restrictions des versions précédentes d’Adobe Analytics. Quelques améliorations notables ont été apportées :

* **Variables et événements** illimités : Les concepts d’eVars, de props et de événements n’existent plus. Les données sont principalement axées sur les dimensions et les mesures. Les ensembles de données peuvent comporter un nombre illimité de dimensions et de mesures uniques.
* **Valeurs** uniques illimitées : La plate-forme Adobe Experience Platform n’est limitée à aucune limite unique, telle que les valeurs uniques de 500 000 dans les suites de rapports traditionnelles.
* **Modifier les données** historiques : Avec Adobe Experience Platform, les données peuvent être supprimées ou corrigées.
* **Données** inter-Report Suites : Les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Platform.

La première version de Customer Journey Analytics inclut de nombreuses fonctionnalités incluses dans Analyse Workspace. Pour obtenir une liste complète, reportez-vous à la page Prise en charge [des fonctionnalités d’analyse du parcours](cja-aa.md)client.

## Comparaison de CJA avec les analyses multipériphériques

[Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/components/cda/cda-home.html) sur plusieurs périphériques s’intègre au service d’identité de la plate-forme Adobe Experience Platform, en utilisant le graphique Co-op ou le graphique privé, afin d’identifier comment les périphériques numériques s’adaptent aux utilisateurs. Il est disponible pour les clients d’Adobe Analytics Ultimate.

CJA s’intègre aux jeux de données Adobe Experience Platform et permet l’analyse entre canaux dans Analyse Workspace. Bien que CJA ne s&#39;intègre pas encore aux graphiques d&#39;identité Co-op ou Private, vous pouvez &quot;amener votre propre ID&quot; pour joindre des jeux de données, et ces jeux de données peuvent aller au-delà des données numériques pour inclure des points de contact en ligne et hors ligne. Les conditions préalables à la CJA sont décrites plus en détail ci-dessous.

## Cas d’utilisation clés

Les analyses de parcours client vous permettent d’effectuer les opérations suivantes :

* **Consultez le client dans un contexte** de voyage : Vous pouvez vue et analyser les données de manière séquentielle, sur plusieurs canaux. Les données de votre centre d’appels, des systèmes POS et des propriétés en ligne peuvent être combinées en une seule vue de rapports.
* **Mettez les informations à la disposition de tous**: Démocratiser l&#39;accès aux données et permettre à un plus grand nombre de personnes de prendre des décisions commerciales avec des informations dérivées des données. Toute personne de l’entreprise responsable de tout aspect de l’expérience client peut prendre de vraies décisions plus rapidement, en fonction de données plus complètes.
* **Exploiter la puissance des données scientifiques pour vos analystes**: Les analyses de parcours des clients permettent aux êtres humains normaux d’utiliser les données scientifiques pour déverrouiller les perspectives et l’analyse profondes.
* **Visualisez et interagissez avec vos jeux de données à l’aide de rapports** ad hoc : Workspace peut utiliser n’importe quel jeu de données d’Adobe Experience Platform conforme à certaines règles de base.
* **Vue de données** non Web : Workspace ne se limite plus à une définition rigide d’un &quot;accès&quot; ou d’un &quot;événement&quot;. Les schémas personnalisés permettent un contrôle complet des données et des définitions.
* **Contrôlez davantage vos manipulations** de données : Modifiez les données que vous avez téléchargées, créez de nouveaux jeux de données et importez-les dans Workspace. Adobe Experience Platform fournit des outils d’interrogation, d’extraction, de transformation et de chargement via Experience Cloud Requête Service.

## Conditions préalables

Avant de pouvoir début avec Customer Journey Analytics, les conditions préalables suivantes doivent être remplies :

* Votre entreprise a un contrat actif avec Adobe Analytics pour Select, Prime ou Ultimate avec le module complémentaire Analyse de parcours du client. Si vous ne savez pas quel type de contrat vous avez ou si vous ne savez pas si vous disposez du module complémentaire CJA, contactez le gestionnaire de compte de votre organisation.
* Votre entreprise a été configurée pour Adobe Experience Platform.

## Autorisations d’accès utilisateur

Pour créer des connexions, ajouter des jeux de données, etc., vous avez besoin des autorisations suivantes dans la console [d&#39;](https://adminconsole.adobe.com/enterprise/)administration :

* Pour gérer les jeux de données dans la plateforme d’expérience, vous devez faire partie d’un Profil de produits de plate-forme qui vous donne l’autorisation &quot;Gérer les jeux de données&quot;. Pour plus d’informations, voir [Contrôle d&#39;accès dans Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Pour créer une connexion à un jeu de données de plateforme, vous devez faire partie d&#39;un Profil de produits de plateforme qui vous accorde les autorisations suivantes :
   * Schémas de Vue
   * Jeu de données de Vue
   * Gérer les Espaces de nommage d&#39;identité
   * Vue Sandbox
* Pour accéder à l’analyse de parcours du client ou établir une connexion, vous devez également être ajouté à un Profil produit d’analyse de parcours du client dans la console [](https://adminconsole.adobe.com/enterprise/)d’administration.

### Mises à jour de terminologie

Plusieurs fonctions de la CJA ont été renommées pour être conformes aux normes de l&#39;industrie. Voici quelques noms mis à jour :

* Les segments sont désormais appelés &quot;Filtres&quot;.
* Les suites de rapports virtuelles sont désormais connues sous le nom de &quot;Vues&quot;.
* Les classifications sont désormais connues sous le nom de &quot;jeux de données de recherche&quot;.
* Les attributs du client sont désormais appelés &quot;jeux de données de Profil&quot;.
* Les conteneurs d’accès sont maintenant appelés conteneurs &quot;Événements&quot;.
* Les conteneurs de visite sont désormais appelés conteneurs de session.
* Les conteneurs Visiteurs sont maintenant appelés conteneurs &quot;Personne&quot;.

## Autres fonctionnalités intégrées à Adobe Experience Platform

Customer Journey Analytics est l’une des fonctionnalités qui dépendent de la plate-forme Adobe Experience Platform. Plusieurs autres fonctionnalités, également intégrées à Platform, vous permettent de tirer le meilleur parti de vos données.

Adobe Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système et d’appliquer les sciences des données et l’apprentissage automatique afin d’améliorer la conception et la diffusion d’expériences personnalisées. Les données client de la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un schéma et de lots de données. Pour plus d’informations sur la plate-forme, voir Présentation [de l’architecture des plateformes](https://www.adobe.io/apis/experienceplatform/home/overview.html)Adobe Experience Platform.

De la gestion des données à l’accès SQL direct, plusieurs composants de la plate-forme d’expérience sont au coeur de l’analyse du parcours client et agissent en conjonction avec celle-ci :

* [Requête Service](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Utilisez SQL standard pour récupérer les données d’Adobe Experience Platform, telles que les données de la solution Adobe, les données propriétaires du client ou toute autre donnée de la plate-forme. Il s’agit d’un outil sans serveur qui vous permet de joindre n’importe quel jeu de données et de capturer les résultats de la requête sous la forme d’un nouveau jeu de données à utiliser dans rapports, Data Science Workspace ou pour l’assimilation dans Profil Service. Vous pouvez utiliser Requête Service pour construire des écosystèmes d&#39;analyse de données, en créant une image des consommateurs sur leurs différents canaux d&#39;interaction. Ces canaux peuvent inclure les systèmes Point of Sale, Web, Mobile, CRM, etc.
* [Profil client en temps réel](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Service d’identité](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) dans l’option &quot;développeur&quot; : vous pouvez utiliser l’intelligence artificielle prédéfinie (IA) et les modèles d’apprentissage automatique dans Adobe Experience Platform pour influencer divers points du parcours des clients. En découvrant des informations cachées, vous pouvez faire de meilleures prédictions tout au long du parcours du client, suggérer les meilleures étapes à suivre ou automatiser des processus encombrants.
