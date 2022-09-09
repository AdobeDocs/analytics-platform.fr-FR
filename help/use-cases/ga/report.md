---
title: Rapport sur les données Google Analytics dans Customer Journey Analytics
description: Affiche des rapports utiles sur les données Google Analytics dans Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# Rapport sur les données Google Analytics dans Customer Journey Analytics

Une fois les données disponibles dans Customer Journey Analytics, les exemples suivants fournissent des scénarios utiles pour la création de rapports sur ces données.

## Visualisation des données web et dʼapplication sous forme de jeux de données combinés

Ce diagramme de Venn montre le chevauchement des utilisateurs de votre site web (à partir de vos données Google Analytics) et de votre application mobile (à partir de vos données Firebase) et de votre centre dʼappel. Vous pouvez également consulter les produits les plus performants, pas seulement sur le web, mais également dans lʼapplication mobile. Vous pouvez même obtenir le total des recettes des deux en utilisant une mesure calculée. Remarquez que les principaux produits racontent une autre histoire lorsque vous regardez les chiffres dʼaffaires combinés. Sans les jeux de données combinés, vous nʼauriez jamais su que la « casquette en sergé » était si performante.

![Jeux de données combinés](../assets/combined-datasets.png)

## Identifiez les raisons des appels et réduisez leur volume

Vous pouvez suivre la tendance du temps passé par le centre d’appels au cours des deux derniers mois pour déterminer le volume des appels. L’exemple suivant illustre les tendances de ces données au cours des deux derniers mois. L’exemple suivant illustre une tendance croissante, qui peut avoir un impact sur les coûts de l’entreprise.

![Volume d’appels](../assets/call-volume.png)

L’utilisation de la dimension &quot;Raison de l’appel&quot; peut indiquer des moyens d’améliorer l’expérience web, ce qui empêche les visiteurs d’appeler en premier lieu. L’exemple ci-dessus montre que le &quot;produit endommagé&quot; a un temps d’appel moyen de presque 3 minutes par appel, ce qui donne à votre entreprise un moyen précis d’améliorer l’expérience client et de réduire les coûts du centre d’appel.

Vous pouvez afficher les produits qui ont déclenché la plupart des appels à votre centre d’appels et le nombre de clients qui ont effectué ces appels. Le graphique à bulles montre que 20 000 personnes ont appelé, passé plus de 4 heures 30 minutes et renvoyé 33 unités du produit Men&#39;s short Sleeve Tee.

![Raison de lʼappel](../assets/call-reason.png)

En appliquant une ventilation de dimension de &quot;Raison de l’appel&quot;, l’exemple affiche un élément de dimension &quot;Produit endommagé&quot;. Lʼétape suivante consisterait à contacter le service de contrôle de la qualité pour savoir pourquoi les clients ont reçu des T-shirts abîmés.

Vous pouvez consulter les pages du site web qui ont envoyé des appels au centre d’appel. Ce rapport vous permet de savoir où se trouvent les expériences moins optimales sur le site web et d’aider vos responsables produits à résoudre ces problèmes. L’exemple suivant utilise une mesure calculée pour filtrer les données jusqu’aux sessions qui se sont terminées par un appel au centre d’appel. Il utilise également le modèle &quot;participation&quot; dans CJA. [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=fr#cja-workspace).

L’exemple suivant montre que les pages &quot;Panier&quot; et &quot;Informations sur le passage en caisse&quot; pilotent la plupart des appels.

![Contribution des pages](../assets/contributing-pages.png)

Le tableau de cohortes vous permet de voir le temps qu’il faut généralement aux utilisateurs pour appeler le centre d’appel après avoir consulté le site web. L’exemple suivant indique que la durée moyenne de cet exemple de jeu de données est comprise entre trois et quatre semaines.

![Cohorte](../assets/cohort.png)

## Utilisation de lʼattribution marketing avancée

CJA vous permet d’utiliser des modèles d’attribution sophistiqués sur les données cross-canal. Dans lʼexemple suivant, vous pouvez comparer les applications de lʼattribution de chiffre dʼaffaires Dernière touche, Première touche, En U et Algorithmique à la dimension Google Analytics Groupes de canaux.

![Attribution marketing](../assets/mktg-attribution.png)

A lʼaide dʼune mesure calculée, vous pouvez appliquer cette attribution à vos chiffres dʼaffaires du web et des applications mobiles, et même supprimer les retours de produits. Ainsi, vous pouvez connaître le chiffre dʼaffaires net réel de chaque canal marketing.

![Mesure calculée](../assets/calc-metric.png)

Attribution IQ vous permet également de filtrer vos données. Vous pouvez connaître lʼattribution par rapport à des ensembles spécifiques dʼutilisateurs, tels que ceux qui utilisent plusieurs appareils.

![Filtrer](../assets/filter.png)

Vous pouvez également attribuer les recettes de vos applications et web à votre contenu publicitaire Google. L’exemple de ce jeu de données a généré plus de recettes provenant de l’application mobile pilotée par des publicités Google en ligne que du web. En triant les publicités par recettes web et par application, vous obtenez une image différente de vos publicités Google les plus performantes.

![Publicité Google](../assets/google-ad.png)

La combinaison de jeux de données dans CJA vous permet de voir dans cet exemple que les publicités en ligne ont eu un impact sur les produits achetés sur votre application mobile. La visualisation suivante montre que les recettes des applications mobiles provenant des publicités Google représentent 14 000 à 15 000 $ supplémentaires, par rapport au Web seul.

![Google et 2](../assets/google-ad2.png)
