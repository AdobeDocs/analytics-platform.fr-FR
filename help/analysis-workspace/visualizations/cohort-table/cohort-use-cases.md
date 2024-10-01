---
description: Découvrez des exemples de cas d’utilisation pour l’analyse des cohortes.
keywords: Analysis Workspace
title: Cas d’utilisation de l’analyse des cohortes
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 388042e24a7b9d33ac88e05a68689308e6258339
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 51%

---

# [!UICONTROL Cas d’utilisation de l’analyse des cohortes]

Cet article décrit quelques exemples de cas d’utilisation pour l’ [!UICONTROL analyse des cohortes].

## Cas d’utilisation d’interactions avec les applications

Supposons que vous souhaitiez analyser la manière dont les utilisateurs qui installent votre application l’utilisent au fil du temps. Est-ce qu’ils l’installent mais ne l’utilisent jamais ? Est-ce qu’ils l’utilisent pendant quelque temps, puis arrêtent de le faire ? Ou est-ce qu’ils continuent à l’utiliser au fil du temps ?

Vous pouvez créer une [!UICONTROL analyse des cohortes] sur six mois :

**Granularité** : mensuelle, de janvier 2015 à juin 2015

**Mesure d’inclusion** : installations de l’application

**Mesure de retour** : sessions ou lancements

Les personnes ne sont pas considérées comme *fiancées* au cours des mois suivants, sauf si elles ont une session ou lancent au moins l’application. L’ [!UICONTROL analyse des cohortes] présenterait alors les schémas d’utilisation où l’ *installation de l’application* a toujours lieu au mois 0. Il se peut que l’utilisation chute au mois 2, peu importe quand les utilisateurs ont installé l’application. (Pour les utilisateurs qui ont installé l’application en janvier 2015, le mois 2 équivaut à mars 2015. Pour les personnes ayant installé l’application en février 2015, le mois 2 équivaut à avril 2015, etc.) Cette analyse vous permet d’envoyer un message électronique ou un message push à tous les utilisateurs au cours du deuxième mois après l’installation de l’application afin de leur rappeler d’utiliser l’application.

## Cas d’utilisation de l’abonnement

Vous travaillez chez Adobe.com et proposez un abonnement gratuit à Creative Cloud, avec pour objectif que les utilisateurs passent de la version gratuite à la version d’évaluation de 30 jours voire à la version payante.

**Granularité** : mensuelle

**Mesure d’inclusion** : lien de téléchargement

**Mesure de retour** : achat de la version payante de Creative Cloud

En utilisant l’ [!UICONTROL analyse des cohortes], vous pouvez constater, par exemple, qu’entre 8 % et 10 % des utilisateurs de Creative Cloud gratuits effectuent la mise à niveau le premier mois suivant l’installation. Quelle que soit la date d’installation des utilisateurs. 12 à 15 % effectuent la mise à niveau durant le deuxième mois d’utilisation. Ensuite, les taux de mise à niveau chutent considérablement : entre 4 et 5 % au mois 3, entre 3 et 4 % au mois 4, et entre 1 et 2 % au mois 5.

Vous ne souhaitez pas perdre des clients potentiels au cours du mois 3. Ainsi, vous configurez une campagne par e-mail conçue pour être diffusée au milieu du troisième mois auprès d’un échantillon d’utilisateurs. Offrir un bon de 50 € aux utilisateurs qui n’ont pas encore effectué la mise à niveau.

Consultez vos rapports d’analyse des cohortes quelques mois plus tard. Pour les cohortes formées après le lancement de la campagne, la conversion en abonnements au Creative Cloud payant au cours du mois 3 est passée de 4-5 % à 13-14 %. Cette augmentation des conversions se traduit par des centaines de milliers de dollars par cohorte, pour chaque cohorte mensuelle qui atteint le mois 3 à partir de ce moment.

## Cas d’utilisation de filtres de cohortes complexes

Une grande chaîne d’hôtels cible plusieurs groupes de clients pour des promotions et suit leurs performances. Pour identifier les meilleurs groupes de cohortes d’utilisateurs à cibler, ils veulent créer des groupes de cohortes très spécifiques. À l’aide des critères [!UICONTROL d’inclusion] et de [!UICONTROL retour] augmentés dans les tableaux [!UICONTROL Cohort], la chaîne d’hôtels est en mesure de définir les groupements de cohortes adaptés avec plusieurs mesures et filtres. Ainsi, la chaîne d’hôtels peut identifier les groupes de clients peu performants pour cibler les clients avec des promotions et des offres afin d’augmenter les réservations.

## Cas d’utilisation d’adoption de la version de l’application

Une grande société d’assurance génère l’engagement des clients à l’aide de son application mobile. Toutefois, alors que de nouvelles fonctionnalités sont ajoutées à l’application, il est critique que ses clients la mettent à niveau vers la version la plus récente. Ils peuvent analyser et comparer toutes les versions de l’application côte à côte à l’aide de la cohorte de [!UICONTROL dimension personnalisée] afin de déterminer les clients possédant certaines versions de l’application à cibler. En outre, ils peuvent suivre à la fois la rétention et la perte de clientèle pour voir si des versions spécifiques de l’application détournent des clients de l’application au fil du temps. Par le biais de messages mobiles, ils peuvent réengager ces utilisateurs pour les inciter à mettre à niveau vers la version la plus récente afin de profiter de ses dernières fonctionnalités.

## Cas d’utilisation d’attractivité de campagne

Une multinationale du secteur des médias tire parti de campagnes ciblées pour attirer des utilisateurs vers ses diverses plates-formes et augmenter l’engagement. Les dépenses publicitaires par plateforme reposent sur l’engagement et la rétention des clients. Par conséquent, les campagnes réussies sont essentielles au succès de son activité. Ils utilisent la nouvelle fonction de cohorte [!UICONTROL Dimension personnalisée] dans les tableaux [!UICONTROL de cohorte] pour comparer diverses campagnes côte à côte afin d’identifier les campagnes qui parviennent le mieux à acquérir et retenir des utilisateurs pour augmenter l’engagement. Ils peuvent ensuite identifier les aspects qui font la réussite d’une campagne et les appliquer à d’autres campagnes pour augmenter l’engagement sur leurs diverses plates-formes.

## Cas d’utilisation du lancement de produit

Un grand détaillant de vêtements dispose de nombreux filtres spécifiques de clients qui génèrent de larges portions du chiffre dʼaffaires de son activité. Chaque filtre présente des produits spécifiques conçus et créés avec le filtre à l’esprit. Avec chaque lancement de produit, ils veulent savoir comment le nouveau produit a dynamisé les ventes pour diverses cohortes au cours du temps. Au moyen du nouveau paramètre [!UICONTROL Tableau de latence] dans l’[!UICONTROL analyse des cohortes], ils peuvent analyser le comportement et le chiffre dʼaffaires d’un filtre donné de clients, avant et après le lancement. À l’aide de ces informations, ils peuvent identifier les produits qui génèrent de nouvelles recettes et ceux qui ne plaisent pas aux clients.

## Attractivité individuelle : la plupart des utilisateurs fidèles utilisent le cas

Une grande compagnie aérienne doit la majeure partie de son succès et de ses recettes à ses clients récurrents et fidèles. Dans nombre de cas, ses voyageurs fidèles représentent la majorité de ses recettes, et elle doit impérativement retenir ces clients pour assurer son succès à long terme. Il est souvent difficile d’identifier les clients les plus fidèles et constants. Cependant, en utilisant le nouveau paramètre [!UICONTROL Calcul variable] dans [!UICONTROL l’analyse des cohortes], la compagnie aérienne peut analyser les filtres client fidèles et déterminer quels voyageurs étaient des acheteurs réguliers d’un mois à l’autre. La compagnie aérienne peut également cibler ces voyageurs avec des récompenses et des avantages pour leur fidélité. De plus, en passant le type Cohort de rétention à perte de clientèle, la compagnie aérienne peut identifier les clients qui ne sont pas des acheteurs réguliers d’un mois à l’autre et cibler ces clients avec des promotions. Ainsi, la compagnie aérienne peut réengager ces clients et s&#39;assurer qu&#39;ils restent des clients fidèles à l&#39;avenir.
