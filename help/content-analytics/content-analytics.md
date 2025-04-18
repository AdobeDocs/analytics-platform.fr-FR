---
title: Vue d’ensemble de Content Analytics
description: Vue d’ensemble de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 28a0abd3415a167e6dd3de3b77bd49b78fc003cd
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 48%

---

# Vue d’ensemble de Content Analytics

{{release-limited-testing}}

Content Analytics aide les spécialistes marketing à comprendre comment le contenu affecte les indicateurs de performances clés définis par une entreprise. En plus des données comportementales, Content Analytics collecte des données sur la manière dont le contenu est utilisé et sur la manière dont le contenu oriente l’impact. Par exemple, les clients répondent-ils mieux à une tonalité de voix spécifique, à une palette de couleurs spécifique ou à des thèmes spécifiques ? Ces informations, ainsi que les workflows et les modèles de création de rapports spécialement conçus, peuvent vous aider à effectuer une analyse encore meilleure et à obtenir des informations plus précises sur les données de parcours client dans Customer Journey Analytics.

Content Analytics utilise un **service de fonctionnalité** optimisé par l’IA et le machine learning pour ventiler le contenu en composants et attributs. En créant un profil de métadonnées structuré sur l’ensemble de votre contenu, vous pouvez analyser le contenu et les attributs de ce contenu qui génèrent les résultats commerciaux.

Outre la création de ce profil de métadonnées structuré, Content Analytics fournit un **service d’identités** qui identifie les ressources et les expériences à l’aide d’un identifiant unique. Le service d’identités peut reconnaître l’apparition d’une ressource identique à plusieurs endroits. Lorsque cela se produit, les instances de cette ressource sont traitées comme la même ressource, ce qui permet d’obtenir une vue plus holistique de l’utilisation et de la consommation du contenu.

## Valeur

Content Analytics apporte une valeur ajoutée réelle à un niveau croissant :

1. **Utilisation** de contenu : avec Content Analytics, vous obtenez des informations sur les ressources qui reçoivent des impressions et sur l’emplacement où elles les reçoivent. Ces informations vous aident à déterminer si les ressources sont sous-utilisées ou surutilisées sur vos propriétés web.
1. **Engagements** de contenu : Content Analytics peut fournir des informations d’engagement, telles que le taux moyen de clics publicitaires pour les ressources présentant certains attributs. Ces informations vous aident à déterminer si des types d’expériences spécifiques sont toujours efficaces.
1. **Parcours** de contenu : en outre, lorsque vous combinez cela à toutes les autres données disponibles dans Experience Platform, vous pouvez obtenir des informations supplémentaires sur vos parcours de contenu. Par exemple, si un contenu spécifique entraîne des conversions, en plus de l’engagement. Grâce à ces connaissances, vous pouvez déterminer le retour sur investissement des types de contenu.
1. **Personnalisation** de contenu : en définitive, Content Analytics vous permet d’agir sur vos informations et d’utiliser ces informations pour déterminer comment dépenser l’argent sur le contenu. Par exemple, dois-je envoyer des types spécifiques de contenu à des audiences spécifiques ? Quel contenu me fournit des opportunités de personnalisation élevée ?

## Terminologie

Content Analytics utilise les termes clés suivants :

![Ressources et expériences](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Expérience** : une expérience est tout le texte d’une page web qui est reproductible à l’aide de l’URL utilisée par l’utilisateur initial qui a visité la page web. Chaque expérience obtient un identifiant unique. Les modifications apportées à la page qui entraînent des modifications dans l’HTML de la page entraînent une nouvelle expérience.
* **Ressource** : une ressource est un élément de contenu individuel et unique, comme une image. Chaque ressource obtient également un identifiant unique et un identifiant de perception. Un identifiant de perception est un identifiant partagé avec des ressources visuellement identiques. Les identifiants perceptuels permettent de dédupliquer des ressources qui peuvent avoir une URL de ressource différente et, par conséquent, un identifiant de ressource différent, mais qui sont perceptuellement identiques.
* **Attribut** : un attribut est un élément de métadonnées descriptif associé à une expérience ou à une ressource. Voici quelques exemples d’un attribut : style de photographie, lisibilité, stratégie de persuasion, couleur de l’objet, couleur de l’arrière-plan.

## Fonctionnement

Content Analytics utilise les données d’affichage d’images web collectées dans les jeux de données d’événements d’Experience Platform. Ces données peuvent être collectées à l’aide des différentes méthodes disponibles : Experience Platform Edge Network (SDK web, API du serveur) ou connecteur source Analytics.

![Content Analytics - Fonctionnement](assets/aca-overview.gif)


1. Lorsqu’un utilisateur visite un site, [configuré pour Content Analytics](config/configuration.md), le SDK Web Experience Platform enregistre les impressions et les interactions avec le contenu.
1. Le service d’identité et de fonctionnalité traite ces interactions. Ce processus consiste en un service de récupération qui revisite les versions publiques des URL configurées qui définissent les interactions. Pour toutes ces URL récupérées, le service d’identités identifie de manière unique les expériences et les ressources. Le service de fonctionnalité applique des services d’IA/ML pour découvrir des expériences et des métadonnées et attributs de ressources.
1. Les résultats de ces services ([composants, attributs et identités](/help/content-analytics/report/components.md)) sont utilisés pour mettre à jour les jeux de données d’analyse de contenu spécifiques pertinents dans Experience Platform.
1. Les données d’analyse de contenu, ainsi que les données comportementales et d’autres données de recherche, peuvent être utilisées dans une configuration Customer Journey Analytics ([Connexion](/help/connections/overview.md), [Vue de données](/help/data-views/data-views.md) et [Workspace](/help/analysis-workspace/home.md)). Cette configuration fournit la base des informations uniques au niveau de la macro sur votre contenu. <br/>Vous pouvez démarrer rapidement vos rapports et analyses Content Analytics à l’aide du modèle [Content Analytics](/help/content-analytics/report/report.md#template).

>[!NOTE]
>
>Content Analytics exploite les services d’IA/ML qui peuvent produire des résultats inexacts ou trompeurs. Par conséquent, faites preuve de jugement pour examiner et valider les résultats générés par l&#39;IA/ML.
>
>Vous pouvez utiliser l’onglet **[!UICONTROL Commentaires]**, disponible à partir de ![InfoOutline](/help/assets/icons/InfoOutline.svg) sur l’interface principale, pour fournir des commentaires sur les sorties générées par l’IA/ML.
>

>[!NOTE]
>
>Si vous disposez d’une licence pour le module complémentaire Privacy and Security Shield, sachez que les expériences et les ressources (toutes les données générées à partir de celles-ci), soumises à Content Analytics, ne sont pas couvertes par l’étiquetage DULE ou les clés gérées par le client.
>

>[!NOTE]
>
>Content Analytics [envoie des événements supplémentaires](config/datacollection.md#content-analytics-event) qui affectent probablement toute définition de taux de rebond basée sur le nombre d’événements dans une session ou une page.
>

>[!MORELIKETHIS]
>
>[Création de rapports Content Analytics](report/report.md)
>[Configurer Content Analytics](config/configuration.md)
>[Calcul des bounces et du taux de bounce dans Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)
>

