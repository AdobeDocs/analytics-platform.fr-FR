---
description: Exemples de cas d’utilisation d’analyse des cohortes.
keywords: Analysis Workspace
title: Cas d’utilisation de l’analyse des cohortes
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 75%

---


# [!UICONTROL Cas d’utilisation des Analyses] de cohortes

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Use case examples for [!UICONTROL Cohort Analysis].

## Cas d’utilisation d’interactions avec les applications

Supposons que vous souhaitiez analyser la manière dont les utilisateurs qui installent votre application l’utilisent au fil du temps. Est-ce qu’ils l’installent mais ne l’utilisent jamais ? Est-ce qu’ils l’utilisent pendant quelque temps, puis arrêtent de le faire ? Ou est-ce qu’ils continuent à l’utiliser au fil du temps ?

You can create a six-month [!UICONTROL Cohort Analysis]:

**Granularité** : mensuelle, de janvier 2015 à juin 2015

**Mesure d’inclusion** : installations de l’application

**Mesure de retour** : sessions ou lancements

Les visiteurs ne sont pas considérés comme *`engaged`* durant les mois suivants, à moins qu’ils n’ouvrent une session ou au moins démarrent l’application. [!UICONTROL L’Analyse] des cohortes vous montrera alors les schémas d’utilisation où *`App Install`* survient toujours le mois 0. Il se peut que l’utilisation chute au mois 2, peu importe quand les utilisateurs ont installé l’application. (Pour ceux qui ont installé l’application en janvier 2015, le mois 2 équivaut à mars 2015 ; pour ceux qui ont installé l’application en février 2015, le mois 2 équivaut à avril 2015 ; etc.) Cette analyse permet d’envoyer un message électronique ou un message Push à tous les utilisateurs durant le deuxième mois après l’installation de l’application, afin de leur rappeler d’utiliser l’application.

## Cas d’utilisation de l’abonnement

Vous travaillez chez Adobe.com et proposez un abonnement gratuit à Creative Cloud, avec pour objectif que les utilisateurs passent de la version gratuite à la version d’évaluation de 30 jours voire à la version payante.

**Granularité** : mensuelle

**Mesure d’inclusion** : lien de téléchargement

**Mesure de retour** : achat de la version payante de Creative Cloud

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. 12 à 15 % effectuent la mise à niveau durant le deuxième mois d’utilisation. Ensuite, les taux de mise à niveau chutent considérablement : entre 4 et 5 % au mois 3, entre 3 et 4 % au mois 4, et entre 1 et 2 % au mois 5.

En considérant que vous ne devez pas perdre de clients potentiels durant le mois 3, vous configurez une campagne par messagerie électronique conçue pour être diffusée au milieu du mois 3 auprès d’un échantillon d’utilisateurs afin d’offrir un bon de 50 € à ceux qui n’ont pas encore effectué la mise à niveau.

Revérifiez votre rapport d’analyse des cohortes quelques mois plus tard. Pour les cohortes formées après le lancement de la campagne, la conversion en abonnements payants à Creative Cloud au cours du mois 3 est passée de 4-5 % à 13-14 %, générant des centaines de milliers d’euros par cohorte, pour chaque cohorte mensuelle parvenant au mois 3 à partir de cette date.

## Cas d’utilisation de segments de cohortes complexes

Une grande chaîne d’hôtels cible plusieurs groupes de clients pour des promotions et suit leurs performances. Afin d’identifier les meilleurs groupes de cohortes d’utilisateurs à cibler, ils veulent créer des groupes de cohortes très spécifiques. Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## Cas d’utilisation d’adoption de la version de l’application

Une grande société d’assurance génère un engagement important de ses clients à l’aide de son application mobile. Toutefois, alors que de nouvelles fonctionnalités sont ajoutées à l’application, il est critique que ses clients la mettent à niveau vers la version la plus récente. They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. En outre, ils peuvent suivre à la fois la rétention et la perte de clientèle pour voir si des versions spécifiques de l’application détournent des clients de l’application au fil du temps. Par le biais de messages mobiles, ils peuvent réengager ces utilisateurs pour les inciter à mettre à niveau vers la version la plus récente afin de profiter de ses dernières fonctionnalités.

## Cas d’utilisation d’attractivité de campagne

Une multinationale du secteur des médias tire parti de campagnes ciblées pour attirer des utilisateurs vers ses diverses plates-formes et augmenter l’engagement. Les dépenses publicitaires par plate-forme reposent sur l’engagement et la rétention des clients. Par conséquent, les campagnes réussies sont essentielles au succès de son activité. They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. Ils peuvent ensuite identifier les aspects qui font la réussite d’une campagne et les appliquer à d’autres campagnes pour augmenter l’engagement sur leurs diverses plates-formes.

## Cas d’utilisation du lancement de produit

Un grand détaillant de vêtements dispose de nombreux segments spécifiques de clients qui génèrent de larges portions de recettes pour son activité. Chaque segment présente des produits spécifiques conçus et créés avec le segment à l’esprit. Avec chaque lancement de produit, ils veulent savoir comment le nouveau produit a dynamisé les ventes pour diverses cohortes au cours du temps. Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment&#39;s pre-launch and post-launch behavior and revenue. À l’aide de ces informations, ils peuvent identifier les produits qui génèrent de nouvelles recettes et ceux qui ne plaisent pas aux clients.

## Attractivité personnelle – Les utilisateurs les plus fidèles cas d’utilisation

Une grande compagnie aérienne doit la majeure partie de son succès et de ses recettes à ses clients récurrents et fidèles. Dans nombre de cas, ses voyageurs fidèles représentent la majorité de ses recettes, et elle doit impérativement retenir ces clients pour assurer son succès à long terme. Il est souvent difficile d’identifier les clients les plus fidèles et constants. However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. Ils ont ensuite pu cibler ces voyageurs avec des récompenses et des avantages pour les remercier de leur fidélité. De plus, en passant le type de cohorte de rétention à perte de clientèle, ils ont pu identifier les clients non récurrents mois après mois et cibler ces segments avec des promotions afin de les réengager et de s’assurer qu’ils restent des clients fidèles à l’avenir.
