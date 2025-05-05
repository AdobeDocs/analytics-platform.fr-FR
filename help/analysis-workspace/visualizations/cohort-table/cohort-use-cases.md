---
description: Découvrez des exemples de cas d’utilisation pour l’analyse des cohortes.
keywords: Analysis Workspace
title: Cas d’utilisation de l’analyse des cohortes
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 52%

---

# Cas d’utilisation de l’[!UICONTROL analyse des cohortes]

Cet article décrit quelques exemples de cas d’utilisation de l’[!UICONTROL &#x200B; Analyse des cohortes &#x200B;].

## Cas d’utilisation d’interactions avec les applications

Supposons que vous souhaitiez analyser la manière dont les utilisateurs qui installent votre application l’utilisent au fil du temps. Est-ce qu’ils l’installent mais ne l’utilisent jamais ? Est-ce qu’ils l’utilisent pendant quelque temps, puis arrêtent de le faire ? Ou est-ce qu’ils continuent à l’utiliser au fil du temps ?

Vous pouvez créer une [!UICONTROL analyse des cohortes] sur six mois :

**Granularité** : mensuelle, de janvier 2015 à juin 2015

**Mesure d’inclusion** : installations de l’application

**Mesure de retour** : sessions ou lancements

Les personnes ne sont pas comptabilisées comme *engagées* les mois suivants, à moins qu’elles n’ouvrent une session ou au moins lancent l’application. L’[!UICONTROL analyse des cohortes] vous montre alors les schémas d’utilisation dans lesquels l’*installation de l’application* se produit toujours au mois 0. Il se peut que l’utilisation chute au mois 2, peu importe quand les utilisateurs ont installé l’application. (Pour les utilisateurs qui ont installé l’application en janvier 2015, le mois 2 est mars 2015. Pour les personnes qui ont installé l’application en février 2015, le mois 2 est avril 2015, etc.) Cette analyse permet d’envoyer un e-mail ou un message push à tous les utilisateurs au cours du deuxième mois suivant l’installation de l’application pour leur rappeler d’utiliser l’application.

## Cas d’utilisation de l’abonnement

Vous travaillez chez Adobe.com et proposez un abonnement gratuit à Creative Cloud, avec pour objectif que les utilisateurs passent de la version gratuite à la version d’évaluation de 30 jours voire à la version payante.

**Granularité** : mensuelle

**Mesure d’inclusion** : lien de téléchargement

**Mesure de retour** : achat de la version payante de Creative Cloud

Grâce à l’analyse des cohortes [!UICONTROL Cohort Analysis], vous pouvez constater, par exemple, qu’entre 8 et 10 % des utilisateurs de Creative Cloud bénéficient d’une mise à niveau gratuite au cours du premier mois suivant l’installation. Quel que soit le moment auquel les utilisateurs et utilisatrices ont installé. 12 à 15 % effectuent la mise à niveau durant le deuxième mois d’utilisation. Ensuite, les taux de mise à niveau chutent considérablement : entre 4 et 5 % au mois 3, entre 3 et 4 % au mois 4, et entre 1 et 2 % au mois 5.

Vous ne voulez pas perdre de clients potentiels au troisième mois. Vous avez donc configuré une campagne par e-mail conçue pour être envoyée au milieu du troisième mois à un échantillon d’utilisateurs. Offrir un coupon de 50 $ aux utilisateurs qui n&#39;ont pas encore effectué la mise à niveau.

Consultez à nouveau vos rapports d’analyse des cohortes quelques mois plus tard. Pour les cohortes formées après le lancement de la campagne, la conversion en abonnements Creative Cloud payants au troisième mois a augmenté de 4-5 % à 13-14 %. Cette augmentation de la conversion se traduit par des centaines de milliers de dollars par cohorte, pour chaque cohorte mensuelle qui atteint le troisième mois à partir de ce moment.

## Cas d’utilisation des segments de cohorte complexes

Une grande chaîne d’hôtels cible plusieurs groupes de clients pour des promotions et suit leurs performances. Pour identifier les meilleurs groupes de cohortes d’utilisateurs à cibler, ils souhaitent créer des groupes de cohortes très spécifiques. En utilisant les critères augmentés [!UICONTROL Inclusion] et [!UICONTROL Retour] dans les tableaux [!UICONTROL Cohorte], la chaîne hôtelière est en mesure de définir exactement les groupements de cohortes adaptés avec plusieurs mesures et segments. Ainsi, la chaîne hôtelière peut identifier les groupes de clients peu performants pour cibler les clients avec des promotions et des offres afin d&#39;augmenter les réservations.

## Cas d’utilisation d’adoption de la version de l’application

Une grande compagnie d&#39;assurance stimule l&#39;engagement des clients grâce à son application mobile. Toutefois, alors que de nouvelles fonctionnalités sont ajoutées à l’application, il est critique que ses clients la mettent à niveau vers la version la plus récente. Ils peuvent analyser et comparer toutes les versions de l’application côte à côte à l’aide de la cohorte de [!UICONTROL dimension personnalisée] afin de déterminer les clients possédant certaines versions de l’application à cibler. En outre, ils peuvent suivre à la fois la rétention et la perte de clientèle pour voir si des versions spécifiques de l’application détournent des clients de l’application au fil du temps. Par le biais de messages mobiles, ils peuvent réengager ces utilisateurs pour les inciter à mettre à niveau vers la version la plus récente afin de profiter de ses dernières fonctionnalités.

## Cas d’utilisation d’attractivité de campagne

Une multinationale du secteur des médias tire parti de campagnes ciblées pour attirer des utilisateurs vers ses diverses plates-formes et augmenter l’engagement. Les dépenses publicitaires par plateforme reposent sur l’engagement et la rétention des clients. Par conséquent, les campagnes réussies sont essentielles au succès de son activité. Ils utilisent la nouvelle fonctionnalité de cohorte [!UICONTROL Custom Dimension] des tableaux [!UICONTROL de cohortes] pour comparer côte à côte différentes campagnes afin d’identifier les campagnes les plus efficaces pour acquérir et fidéliser les utilisateurs et utilisatrices afin d’augmenter l’engagement. Ils peuvent ensuite identifier les aspects qui font la réussite d’une campagne et les appliquer à d’autres campagnes pour augmenter l’engagement sur leurs diverses plates-formes.

## Cas d’utilisation du lancement de produit

Un grand détaillant de vêtements dispose de nombreux segments spécifiques de clients qui génèrent de larges portions de recettes pour son activité. Chaque segment présente des produits spécifiques conçus et créés avec le segment à l’esprit. Avec chaque lancement de produit, ils veulent savoir comment le nouveau produit a dynamisé les ventes pour diverses cohortes au cours du temps. Au moyen du nouveau paramètre [!UICONTROL Tableau de latence] dans l’[!UICONTROL analyse des cohortes], ils peuvent analyser le comportement et les recettes d’un segment donné de clients, avant et après le lancement. À l’aide de ces informations, ils peuvent identifier les produits qui génèrent de nouvelles recettes et ceux qui ne plaisent pas aux clients.

## Attractivité personnelle - Cas d’utilisation des utilisateurs et utilisatrices les plus fidèles

Une grande compagnie aérienne doit la majeure partie de son succès et de ses recettes à ses clients récurrents et fidèles. Dans nombre de cas, ses voyageurs fidèles représentent la majorité de ses recettes, et elle doit impérativement retenir ces clients pour assurer son succès à long terme. Il est souvent difficile d’identifier les clients les plus fidèles et constants. Cependant, en utilisant le nouveau paramètre [!UICONTROL Calcul variable] dans [!UICONTROL Analyse des cohortes], la compagnie aérienne peut analyser les segments de clients fidèles et déterminer quels voyageurs étaient des acheteurs récurrents mois après mois. La compagnie aérienne peut également cibler ces voyageurs avec des récompenses et des avantages pour les remercier de leur fidélité. En outre, en passant le type de cohorte de rétention à perte de clientèle, la compagnie aérienne peut identifier les clients qui ne sont pas des acheteurs récurrents mois après mois et cibler ces clients avec des promotions. Ainsi, la compagnie aérienne peut renouer le dialogue avec ces clients et s&#39;assurer qu&#39;ils restent des clients fidèles à l&#39;avenir.
