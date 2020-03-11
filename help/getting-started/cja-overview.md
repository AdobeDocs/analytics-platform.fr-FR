---
title: Présentation de l’analyse du parcours du client
description: Présentation de l’analyse du parcours du client
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Présentation de l’analyse du parcours du client

Customer Journey Analytics est une fonctionnalité d’analyse qui vous permet d’utiliser la puissance de   Workspace avec les données d’Adobe Experience Platform. Il peut ventiler, filtrer,  et visualiser des années de données, et est combiné avec la capacité de Platform à contenir tous les types et tous les types de de données. En utilisant le modèle de données d’ **expérience (XDM)**, les données peuvent être représentées et organisées uniformément, prêtes à être combinées et explorées. **Experience  Services** vous permet d’utiliser des outils et des structures compatibles SQL pour et manipuler toutes vos données.

## Comparaison de CJA avec Adobe Analytics traditionnel

Les analyses de parcours des clients étendent la portée d’Analytics en offrant des fonctionnalités  cross-simples d’utilisation et en supprimant les restrictions des versions précédentes d’Adobe Analytics. Quelques améliorations notables ont été apportées :

* **Variables et** de illimités : Les concepts d’eVars, de props et de  n’existent plus. Les données sont principalement axées sur les dimensions et les mesures. Les ensembles de données peuvent avoir un nombre illimité de dimensions et de mesures uniques.
* **Valeurs** uniques illimitées : Adobe Experience Platform n’est limitée à aucune limite unique, telle que les valeurs uniques de 500 000 dans les suites de rapports traditionnelles.
* **Modifier les données** historiques : Avec Adobe Experience Platform, les données peuvent être supprimées ou corrigées.
* **Données** inter-suites de rapports : Les implémentations existantes de plusieurs jeux de données peuvent être combinées dans Platform.

La première version de Customer Journey Analytics inclut de nombreuses fonctionnalités incluses dans   Workspace de. Pour une  complète, reportez-vous à la page Prise en charge [des fonctionnalités d’analyse du parcours](cja-aa.md)client.

## Comparaison de CJA avec les analyses multipériphériques

[Analytics](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) sur plusieurs périphériques s’intègre au service d’identité d’Adobe Experience Platform, en utilisant le graphique Co-op ou le graphique privé, afin d’identifier la manière dont les périphériques numériques sont mappés aux personnes. Il est disponible pour les clients d’Adobe Analytics Ultimate.

CJA s’intègre aux jeux de données d’Adobe Experience Platform et active  croisé dans l’espace de travail de. Bien que CJA ne s’intègre pas encore aux graphiques d’identité Co-op ou Private, vous pouvez &quot;rassembler votre propre ID&quot; pour joindre des ensembles de données, et ces ensembles de données peuvent aller au-delà des données numériques pour inclure des points de contact en ligne et hors ligne. Les conditions préalables de la CJA sont décrites plus en détail ci-dessous.

## Cas d&#39;utilisation clés

Les analyses de parcours du client vous permettent d’effectuer les opérations suivantes :

* **Consultez le client dans un contexte** de voyage : Vous pouvez et analyser les données de manière séquentielle, sur plusieurs  de. Les données du centre d’appels, des systèmes POS et des propriétés en ligne peuvent être combinées en un seul  de .
* **Mettez les informations à la disposition de tous**: Démocratiser l&#39;accès aux données et permettre à un plus grand nombre de personnes de prendre des décisions commerciales avec des informations dérivées des données. Toute personne de l’entreprise responsable de n’importe quel aspect de l’expérience client peut prendre de vraies décisions plus rapidement, sur la base de données plus complètes.
* **Exploitez la puissance des sciences des données pour vos analystes**: Les analyses de parcours des clients permettent aux humains normaux d’utiliser la science des données pour déverrouiller des connaissances approfondies et   des.
* **Visualisez et interagissez avec vos jeux de données à l’aide de** ad hoc : Workspace peut utiliser n’importe quel jeu de données d’Adobe Experience Platform en conformité avec certaines règles de base.
* **données** non Web : Workspace ne se limite plus à une définition rigide d’un accès ou d’un . Les  personnalisées permettent un contrôle complet des données et des définitions.
* **Contrôlez mieux vos manipulations** de données : Modifiez les données que vous avez téléchargées, créez de nouveaux jeux de données et importez-les dans Workspace. Adobe Experience Platform fournit des outils d’interrogation, d’extraction, de transformation et de chargement par le biais du service  Experience Cloud.

## Conditions préalables

Avant de pouvoir  à l’aide de Customer Journey Analytics, les conditions préalables suivantes doivent être remplies :

* Votre entreprise a un contrat actif avec Adobe Analytics pour Select, Prime ou Ultimate avec le module complémentaire d’analyse du parcours du client. Si vous ne savez pas quel type de contrat vous avez ou si vous n’êtes pas sûr d’avoir le module complémentaire CJA, contactez le gestionnaire de compte de votre entreprise.
* Votre entreprise a été configurée pour Adobe Experience Platform.

## Autorisations d’accès utilisateur

Pour créer des connexions, ajouter des jeux de données, etc., vous devez disposer des autorisations suivantes dans la console [d’administration](https://adminconsole.adobe.com/enterprise/):

* Pour gérer les jeux de données dans la plateforme d’expérience, vous devez faire partie d’un de produits de plateforme qui vous donne l’autorisation &quot;Gérer les jeux de données&quot;. Pour plus d’informations, reportez-vous à la section  [dans Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Pour créer une connexion à un jeu de données de plateforme, vous devez faire partie d’un de produits de plateforme qui vous donne les autorisations suivantes :
   * View Schemas
   *  de données
   * Gérer les  d&#39;identité 
   * Sandbox
* Pour accéder à l’analyse de parcours du client ou établir une connexion, vous devez également être ajouté à un de produits d’analyse de parcours du client dans la console [d’](https://adminconsole.adobe.com/enterprise/)administration.

### Mises à jour terminologiques

Plusieurs fonctions de la CJA ont été renommées pour s’aligner sur les normes de l’industrie. Voici quelques noms mis à jour :

* Les segments sont désormais appelés &quot;&quot;.
* Les suites de rapports virtuelles sont désormais connues sous le nom de &quot;&quot;.
* Les classifications sont désormais connues sous le nom de &quot;jeux de données de recherche&quot;.
* Les attributs du client sont désormais appelés &quot;jeux de données &quot;.
* Les d’accès sont désormais connus sous le nom de &quot;&quot; .
* Les  de visite sont désormais connues sous le nom de  &quot;session&quot;.
* Les sont désormais connus sous le nom de  &quot;Personne&quot;.

## Autres fonctionnalités intégrées à Adobe Experience Platform

Les analyses de parcours des clients sont l’une des fonctionnalités parmi de nombreuses autres qui reposent sur la plate-forme Adobe Experience Platform. Plusieurs autres fonctionnalités, également intégrées à Platform, vous permettent de tirer le meilleur parti de vos données.

Adobe Experience Platform vous permet de centraliser et de normaliser les données et le contenu des clients à partir de n’importe quel système, et d’appliquer les sciences des données et l’apprentissage automatique afin d’améliorer la conception et la  des expériences personnalisées. Les données du client dans la plate-forme sont stockées sous forme de jeux de données, qui se composent d’un  et de lots de données. Pour plus d’informations sur la plate-forme, voir Présentation [de l’architecture](https://www.adobe.io/apis/experienceplatform/home/overview.html)Adobe Experience Platform.

De l’intégration des données à l’accès SQL direct, plusieurs composants de la plateforme Experience Platform sont au coeur des analyses de parcours du client et agissent en même temps :

* [Service](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html) : Utilisez SQL standard pour récupérer les données d’Adobe Experience Platform, telles que les données de solution Adobe, les données propriétaires du client ou toute autre donnée de plateforme. Il s’agit d’un outil sans serveur qui vous permet de joindre n’importe quel jeu de données et de capturer les résultats  du sous la forme d’un nouveau jeu de données à utiliser dans, Data Science Workspace ou pour l’assimilation dans le service de  de données. Vous pouvez utiliser le service de  pour créer des données  des écosystèmes de , en créant une image des consommateurs dans leurs différents d&#39;interaction. Ces  peuvent inclure les systèmes Point of Sale, Web, Mobile, CRM, etc.
* [Profil client en temps réel](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Service d’identité](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) dans l’option &quot;développeur&quot; : vous pouvez utiliser l’intelligence artificielle (IA) prédéfinie et les modèles d’apprentissage automatique dans Adobe Experience Platform pour influencer divers points du parcours du client. En découvrant des informations cachées, vous pouvez faire de meilleures prédictions tout au long du parcours du client, suggérer les meilleures étapes à suivre ou automatiser des processus encombrants.
