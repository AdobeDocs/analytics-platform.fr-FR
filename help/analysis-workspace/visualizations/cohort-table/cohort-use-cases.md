---
description: Exemples de cas d’utilisation d’analyse des cohortes.
keywords: Analysis Workspace
title: Cas d’utilisation de l’analyse des cohortes
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '928'
ht-degree: 100%

---

# Cas d’utilisation de l’[!UICONTROL analyse des cohortes]

Exemples de cas d’utilisation d’[!UICONTROL analyse des cohortes].

## Cas d’utilisation d’interactions avec les applications

Supposons que vous souhaitiez analyser la manière dont les utilisateurs qui installent votre application l’utilisent au fil du temps. Est-ce qu’ils l’installent mais ne l’utilisent jamais ? Est-ce qu’ils l’utilisent pendant quelque temps, puis arrêtent de le faire ? Ou est-ce qu’ils continuent à l’utiliser au fil du temps ?

Vous pouvez créer une [!UICONTROL analyse des cohortes] sur six mois :

**Granularité** : mensuelle, de janvier 2015 à juin 2015

**Mesure d’inclusion** : installations de l’application

**Mesure de retour** : sessions ou lancements

Les visiteurs ne sont pas considérés comme   *`engaged`* durant les mois suivants, à moins qu’ils n’ouvrent une session ou au moins démarrent l’application. [!UICONTROL L’analyse des cohortes] présenterait alors les différents schémas d’utilisation où *`App Install`* survient toujours durant le mois 0. Il se peut que l’utilisation chute au mois 2, peu importe quand les utilisateurs ont installé l’application. (Pour ceux qui ont installé l’application en janvier 2015, le mois 2 équivaut à mars 2015 ; pour ceux qui ont installé l’application en février 2015, le mois 2 équivaut à avril 2015 ; etc.) Cette analyse permet d’envoyer un message électronique ou un message Push à tous les utilisateurs durant le deuxième mois après l’installation de l’application, afin de leur rappeler d’utiliser l’application.

## Cas d’utilisation de l’abonnement

Vous travaillez chez Adobe.com et proposez un abonnement gratuit à Creative Cloud, avec pour objectif que les utilisateurs passent de la version gratuite à la version d’évaluation de 30 jours voire à la version payante.

**Granularité** : mensuelle

**Mesure d’inclusion** : lien de téléchargement

**Mesure de retour** : achat de la version payante de Creative Cloud

À l’aide de cette [!UICONTROL analyse des cohortes], vous pouvez constater, par exemple, qu’entre 8 et 10 % des utilisateurs de la version gratuite de Creative Cloud effectuent la mise à niveau durant le premier mois suivant l’installation, peu importe la date d’installation. 12 à 15 % effectuent la mise à niveau durant le deuxième mois d’utilisation. Ensuite, les taux de mise à niveau chutent considérablement : entre 4 et 5 % au mois 3, entre 3 et 4 % au mois 4, et entre 1 et 2 % au mois 5.

En considérant que vous ne devez pas perdre de clients potentiels durant le mois 3, vous configurez une campagne par messagerie électronique conçue pour être diffusée au milieu du mois 3 auprès d’un échantillon d’utilisateurs afin d’offrir un bon de 50 € à ceux qui n’ont pas encore effectué la mise à niveau.

Revérifiez votre rapport d’analyse des cohortes quelques mois plus tard. Pour les cohortes formées après le lancement de la campagne, la conversion en abonnements payants à Creative Cloud au cours du mois 3 est passée de 4-5 % à 13-14 %, générant des centaines de milliers d’euros par cohorte, pour chaque cohorte mensuelle parvenant au mois 3 à partir de cette date.

## Cas d’utilisation de filtres de cohortes complexes

Une grande chaîne d’hôtels cible plusieurs groupes de clients pour des promotions et suit leurs performances. Afin d’identifier les meilleurs groupes de cohortes d’utilisateurs à cibler, ils veulent créer des groupes de cohortes très spécifiques. À l’aide des critères d’[!UICONTROL inclusion] et de [!UICONTROL retour] augmentés au sein des tableaux de [!UICONTROL cohortes], ils sont en mesure de définir exactement les groupements de cohortes adaptés avec plusieurs mesures et filtres pour identifier les groupes de clients peu performants dans le but de les cibler avec des promotions et des offres afin d’augmenter les réservations.

## Cas d’utilisation d’adoption de la version de l’application

Une grande société d’assurance génère un engagement important de ses clients à l’aide de son application mobile. Toutefois, alors que de nouvelles fonctionnalités sont ajoutées à l’application, il est critique que ses clients la mettent à niveau vers la version la plus récente. Ils peuvent analyser et comparer toutes les versions de l’application côte à côte à l’aide de la cohorte de [!UICONTROL dimension personnalisée] afin de déterminer les clients possédant certaines versions de l’application à cibler. En outre, ils peuvent suivre à la fois la rétention et la perte de clientèle pour voir si des versions spécifiques de l’application détournent des clients de l’application au fil du temps. Par le biais de messages mobiles, ils peuvent réengager ces utilisateurs pour les inciter à mettre à niveau vers la version la plus récente afin de profiter de ses dernières fonctionnalités.

## Cas d’utilisation d’attractivité de campagne

Une multinationale du secteur des médias tire parti de campagnes ciblées pour attirer des utilisateurs vers ses diverses plates-formes et augmenter l’engagement. Les dépenses publicitaires par plate-forme reposent sur l’engagement et la rétention des clients. Par conséquent, les campagnes réussies sont essentielles au succès de son activité. Ils utilisent notre nouvelle fonctionnalité Cohorte de [!UICONTROL dimension personnalisée] dans les tableaux de [!UICONTROL cohortes] pour comparer diverses campagnes côte à côte afin d’identifier les campagnes qui parviennent le mieux à acquérir et retenir des utilisateurs pour accroître l’engagement. Ils peuvent ensuite identifier les aspects qui font la réussite d’une campagne et les appliquer à d’autres campagnes pour augmenter l’engagement sur leurs diverses plates-formes.

## Cas d’utilisation du lancement de produit

Un grand détaillant de vêtements dispose de nombreux filtres spécifiques de clients qui génèrent de larges portions du chiffre dʼaffaires de son activité. Chaque filtre présente des produits spécifiques conçus et créés avec le filtre à l’esprit. Avec chaque lancement de produit, ils veulent savoir comment le nouveau produit a dynamisé les ventes pour diverses cohortes au cours du temps. Au moyen du nouveau paramètre [!UICONTROL Tableau de latence] dans l’[!UICONTROL analyse des cohortes], ils peuvent analyser le comportement et le chiffre dʼaffaires d’un filtre donné de clients, avant et après le lancement. À l’aide de ces informations, ils peuvent identifier les produits qui génèrent de nouvelles recettes et ceux qui ne plaisent pas aux clients.

## Attractivité personnelle – Les utilisateurs les plus fidèles   cas d’utilisation

Une grande compagnie aérienne doit la majeure partie de son succès et de ses recettes à ses clients récurrents et fidèles. Dans nombre de cas, ses voyageurs fidèles représentent la majorité de ses recettes, et elle doit impérativement retenir ces clients pour assurer son succès à long terme. Il est souvent difficile d’identifier les clients les plus fidèles et constants. Néanmoins, le nouveau paramètre [!UICONTROL Calcul variable] dans l’[!UICONTROL analyse des cohortes] leur a permis d’analyser les filtres de clients fidèles et de déterminer les voyageurs récurrents mois après mois. Ils ont ensuite pu cibler ces voyageurs avec des récompenses et des avantages pour les remercier de leur fidélité. De plus, en passant le type de cohorte de rétention à perte de clientèle, ils ont pu identifier les clients non récurrents mois après mois et cibler ces filtres avec des promotions afin de les réengager et de s’assurer qu’ils restent des clients fidèles à l’avenir.
