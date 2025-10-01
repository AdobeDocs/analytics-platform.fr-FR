---
title: Vue d’ensemble de Content Analytics
description: Vue d’ensemble de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 94%

---

# Vue d’ensemble de Content Analytics

Content Analytics aide les spécialistes marketing à comprendre comment le contenu affecte les indicateurs de performances clés (KPI) définis par une entreprise. En plus des données comportementales, Content Analytics collecte des données sur la manière dont le contenu est utilisé et sur son impact. Par exemple, les clientes et clients répondent-ils mieux à un ton, une palette de couleurs ou des thèmes spécifiques ? Ces informations, ainsi que les workflows et les modèles de création de rapports spécialement conçus, peuvent vous aider à effectuer une analyse encore meilleure et à obtenir des informations plus précises sur les données de parcours client dans Customer Journey Analytics.

Content Analytics utilise un **service de fonctionnalité** optimisé par l’IA et le machine learning pour ventiler le contenu en composants et attributs. En créant un profil de métadonnées structuré sur l’ensemble de votre contenu, vous pouvez analyser le contenu et les attributs de ce contenu qui génèrent les résultats commerciaux.

Outre la création de ce profil de métadonnées structuré, Content Analytics fournit un **service d’identités** qui identifie les ressources et les expériences à l’aide d’un identifiant unique. Le service d’identités peut reconnaître l’apparition d’une ressource identique à plusieurs endroits. Dans ce cas, les deux instances de ressources sont traitées de la même manière, ce qui permet d’obtenir une vue plus complète de l’utilisation et de la consommation du contenu.

## Valeur

Content Analytics apporte une valeur ajoutée réelle à un niveau croissant :

1. **Utilisation** de contenu : avec Content Analytics, vous obtenez des informations sur les ressources qui reçoivent des impressions et sur l’emplacement où elles les reçoivent. Ces informations vous aident à déterminer si les ressources sont sous-utilisées ou surutilisées sur vos propriétés web.
1. **Engagements** de contenu : Content Analytics peut fournir des informations d’engagement, telles que le taux moyen de clics publicitaires pour les ressources présentant certains attributs. Ces informations vous aident à déterminer si des types d’expériences spécifiques sont toujours efficaces.
1. **Parcours** de contenu : en outre, lorsque vous combinez cela à toutes les autres données disponibles dans Experience Platform, vous pouvez obtenir des informations supplémentaires sur vos parcours de contenu. Par exemple, si un contenu spécifique entraîne des conversions, en plus de l’engagement. Grâce à ces connaissances, vous pouvez déterminer le retour sur investissement des types de contenu.
1. **Personnalisation** de contenu : en définitive, Content Analytics vous permet d’agir sur vos informations et d’utiliser ces informations pour déterminer comment dépenser l’argent sur le contenu. Par exemple, dois-je envoyer des types spécifiques de contenu à des audiences spécifiques ? Quel contenu me fournit des opportunités de personnalisation élevée ?

## Terminologie

Content Analytics utilise les termes clés suivants :

![Ressources et expériences](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Expérience** : une expérience fait référence à tout le texte d’une page web qui est reproductible à l’aide de l’URL utilisée par la permière personne qui visite cette page web. Chaque expérience se voit attribuer un identifiant unique. Les modifications apportées à la page qui entraînent des modifications du code HTML entraînent la création d’une expérience.
* **Ressource** : une ressource est un élément de contenu individuel et unique, comme une image. Chaque ressource obtient également un identifiant unique et un ID de perception. Un ID de perception est un identifiant partagé avec des ressources visuellement identiques. Les ID de perception permettent d’éviter les doublons des ressources qui peuvent avoir une URL et donc des identifiants de ressource différents, mais qui sont en perception identiques.
* **Attribut** : un attribut est un élément de métadonnées descriptif associé à une expérience ou à une ressource. Voici quelques exemples d’un attribut : style de photographie, lisibilité, stratégie de persuasion, couleur de l’objet, couleur de l’arrière-plan.

## Fonctionnement

L’analyse du contenu utilise les données d’affichage d’images web dans les jeux de données d’événement d’Experience Platform pour [collecter des données d’événement de contenu](config/datacollection.md). et associe cette collecte de données de contenu à l’implémentation de collecte de données (existante) de données comportementales.

![Analyse du contenu - Fonctionnement](assets/aca-overview.gif)

1. Lorsqu’une personne visite un site [configuré pour Content Analytics](config/configuration.md) le SDK web Experience Platform enregistre les impressions et les interactions avec le contenu.
1. Le service d’identités et de fonctionnalités traite ces interactions. Ce processus consiste en un service de récupération qui revisite les versions publiques des URL configurées qui définissent les interactions. Pour toutes ces URL récupérées, le service d’identités identifie de manière unique les expériences et les ressources. Le service de fonctionnalités applique des services d’IA et de ML pour identifier des expériences ainsi que des métadonnées et attributs de ressources.
1. Les résultats de ces services ([composants, attributs et identités](/help/content-analytics/report/components.md)) sont utilisés pour mettre à jour les jeux de données Content Analytics spécifiques pertinents dans Experience Platform.
1. Les données Content Analytics, ainsi que les données comportementales et d’autres données de recherche, peuvent être utilisées dans une configuration Customer Journey Analytics ([Connexion](/help/connections/overview.md), [Vue de données](/help/data-views/data-views.md) et [Workspace](/help/analysis-workspace/home.md)). Cette configuration constitue la base des informations uniques au niveau global sur votre contenu. <br/>Vous pouvez démarrer rapidement vos rapports et analyses Content Analytics à l’aide du [modèle Content Analytics](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>Content Analytics exploite les services d’IA et de ML qui peuvent produire des résultats inexacts ou qui induisent en erreur. Par conséquent, examinez attentivement et validez les résultats générés par l’IA ou le ML.
>
>Vous pouvez utiliser l’onglet **[!UICONTROL Commentaires]**, disponible à partir de ![InfoOutline](/help/assets/icons/InfoOutline.svg) sur l’interface principale, pour fournir des commentaires sur les sorties générées par l’IA ou le ML.
>

>[!NOTE]
>
>Si vous disposez d’une licence pour le module complémentaire Privacy and Security Shield, sachez que les expériences et les ressources (toutes les données générées à partir de celles-ci), dans le cadre de Content Analytics, ne sont pas couvertes par l’étiquetage DULE ou les clés gérées par les clientes et les clients. En outre, Content Analytics n’est pas un service conforme à la loi HIPAA.
>


>[!MORELIKETHIS]
>
>[Création de rapports Content Analytics](report/report.md)
>>[Configurer Content Analytics](config/configuration.md)
>>[Calcul des rebonds et du taux de rebond dans Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)
>

