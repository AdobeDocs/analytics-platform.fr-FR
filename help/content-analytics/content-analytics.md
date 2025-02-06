---
title: Présentation de Content Analytics
description: Présentation de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: c63fa8f776fcf3390d312fb44ae6c422e7fa7222
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---

# Présentation de Content Analytics

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{#release-limited-testing}

L’analyse de contenu aide les spécialistes marketing à comprendre comment le contenu affecte les indicateurs de performances clés définis par une entreprise. Outre les fonctionnalités traditionnelles basées au niveau micro pour tester des éléments de contenu (par exemple, des tests A/B), Content Analytics fournit des informations sur la manière dont le contenu génère de l’impact au niveau macro. Par exemple, les clients répondent-ils mieux à une tonalité de voix spécifique, à une palette de couleurs spécifique ou à des thèmes spécifiques ?

Content Analytics utilise un service de fonctionnalité **** IA) et de machine learning pour ventiler le contenu en composants et attributs. En créant un profil de métadonnées structuré sur l’ensemble de votre contenu, vous pouvez analyser le contenu et les attributs de ce contenu qui génèrent les résultats commerciaux.

Outre la création de ce profil de métadonnées structurées, Content Analytics fournit un **service d’identités** qui identifie les ressources et les expériences à l’aide d’un identifiant unique. Le service d’identités comprend si une ressource, par exemple, a été redimensionnée, recadrée ou enregistrée dans un autre format de fichier. Le service affecte toutes les variantes de cette ressource au même identifiant unique. Par conséquent, le service d’identités vous permet d’agréger les performances d’une ressource en fonction de ses différents formulaires et emplacements.

## Valeur

L’analyse de contenu offre une valeur ajoutée à un niveau croissant :

1. Contenu **utilisation** : avec Content Analytics, vous obtenez des informations sur les ressources qui reçoivent des impressions et sur l’emplacement où elles le sont. Ces informations vous aident à déterminer si les ressources sont sous-utilisées ou surutilisées sur vos propriétés web.
1. Contenu **engagements** : Content Analytics peut fournir des informations d’engagement, telles que le taux moyen de clics publicitaires pour les ressources présentant certains attributs. Ces informations vous aident à déterminer si des types d’expériences spécifiques sont toujours efficaces.
1. **parcours de contenu** : de plus, lorsqu’ils sont combinés à toutes les autres données disponibles dans l’Experience Platform, vous pouvez obtenir des informations supplémentaires sur vos parcours de contenu. Par exemple, si un contenu spécifique entraîne des conversions, en plus de l’engagement. Grâce à ces connaissances, vous pouvez déterminer le retour sur investissement des types de contenu.
1. Contenu **personnalisation** : en fin de compte, l’analyse de contenu vous permet d’agir sur vos informations et d’utiliser ces informations pour déterminer comment dépenser l’argent sur le contenu. Par exemple, dois-je envoyer des types spécifiques de contenu à des audiences spécifiques ? Quel contenu me fournit des opportunités de personnalisation élevée ?

## Terminologie

Content Analytics utilise les termes clés suivants :

![Assets et expériences](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Expérience** : une expérience est tout le texte d’une page web qui est reproductible à l’aide de l’URL utilisée par l’utilisateur initial qui visite cette page web. Chaque expérience obtient un identifiant unique.
* **Ressource** : une ressource est un élément de contenu individuel et unique, comme une image. Chaque ressource reçoit également un identifiant unique.
* **Attribut** : un attribut est un élément de métadonnées descriptif associé à une expérience ou à une ressource. Voici quelques exemples d’un attribut : style de photographie, lisibilité, stratégie de persuasion, couleur de l’objet, couleur de l’arrière-plan.

## Fonctionnement

Content Analytics utilise les données d’affichage d’images web collectées dans les jeux de données d’événements d’Experience Platform. Ces données peuvent être collectées à l’aide des différentes méthodes disponibles : Edge Network Experience Platform (Web SDK, API du serveur) ou connecteur source Analytics.

![Content Analytics - Fonctionnement](assets/how-it-works.png)


1. La partie détection du service de fonctionnalité est déclenchée lors de tout nouvel instantané de données arrivant à un jeu de données d’événement activé pour Content Analytics.
1. Le service de détection des fonctionnalités détermine les données de cet instantané qui sont pertinentes pour l’analyse de contenu et revisite l’expérience et les ressources de ces vues d’images web.
1. Lors de la révision, des données d’analyse de contenu spécifiques sont collectées au moyen d’une configuration appropriée du SDK web Experience Platform et de l’Edge Network Experience Platform. Les données sont ensuite envoyées à un jeu de données d’analyse de contenu dédié et aux jeux de données de recherche pertinents.
1. Le service Featurization Assembler et le service d’identités traitent les données revisitées.
1. Les résultats de ces services (composants, attributs et identités) sont utilisés pour mettre à jour les jeux de données d’analyse de contenu spécifiques pertinents dans Experience Platform.
1. Les données d’analyse de contenu, ainsi que les données comportementales et d’autres jeux de données de recherche, peuvent ensuite être utilisées dans une configuration de Customer Journey Analytics (Connexion, Vue de données et Workspace). Cette configuration fournit la base des informations uniques au niveau des macros sur votre contenu.

>[!MORELIKETHIS]
>
>[Utilisation de Content Analytics (d.c.d.)](#value)
>[Configurer Content Analytics](config/configuration.md)
