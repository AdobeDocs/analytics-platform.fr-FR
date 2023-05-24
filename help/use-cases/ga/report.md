---
title: Rapport sur les données Google Analytics dans Customer Journey Analytics
description: Affiche des rapports utiles sur les données Google Analytics dans Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 92%

---

# Rapport sur les données Google Analytics dans Customer Journey Analytics

Une fois les données disponibles dans Customer Journey Analytics, les exemples suivants constituent des scénarios utiles pour la création de rapports sur ces données.

## Visualisation des données web et dʼapplication sous forme de jeux de données combinés

Ce diagramme de Venn montre le chevauchement des utilisateurs de votre site web (à partir de vos données Google Analytics) et de votre application mobile (à partir de vos données Firebase) et de votre centre dʼappel. Vous pouvez également consulter les produits les plus performants, pas seulement sur le web, mais également dans lʼapplication mobile. Vous pouvez même obtenir le chiffre dʼaffaires total des deux à lʼaide dʼune mesure calculée. Remarquez que les principaux produits racontent une autre histoire lorsque vous regardez les chiffres dʼaffaires combinés. Sans les jeux de données combinés, vous nʼauriez jamais su que la « casquette en sergé » était si performante.

![Jeux de données combinés](../assets/combined-datasets.png)

## Identifiez les raisons des appels et réduisez leur volume

Vous pouvez établir une tendance du temps passé au centre d’appel au cours des deux derniers mois pour déterminer le volume des appels. L’exemple suivant illustre la tendance de ces données sur les deux derniers mois. L’exemple suivant montre une tendance à la hausse, ce qui peut avoir un impact sur les coûts organisationnels.

![Volume des appels](../assets/call-volume.png)

L’utilisation de la dimension &quot;Raison de l’appel&quot; peut indiquer des moyens d’améliorer l’expérience web, ce qui empêche les personnes d’appeler en premier lieu. L’exemple ci-dessus montre que le temps d’appel moyen pour un « produit endommagé » est de près de 3 minutes. À la lueur de ces informations précieuses, votre organisation peut améliorer l’expérience client et réduire les frais encourus par le centre d’appel.

Vous pouvez voir quels produits sont à l’origine de la plupart des appels vers votre centre d’appel et le nombre de clients qui ont passé ces appels. Le graphique à bulles indique que 20 000 personnes ont appelé, ont passé plus de 4 heures 30 minutes au téléphone et ont renvoyé 33 unités du produit « T-shirt à manches courtes pour hommes ».

![Raison de lʼappel](../assets/call-reason.png)

En appliquant une répartition de dimension de « Raison de l’appel », l’exemple affiche un élément de dimension « Produit endommagé ». Lʼétape suivante consisterait à contacter le service de contrôle de la qualité pour savoir pourquoi les clients ont reçu des T-shirts abîmés.

Vous pouvez consulter les pages du site Web qui ont envoyé des appels au centre d’appel. Ce rapport permet de savoir où se trouvent les expériences moins performantes sur le site Web et dʼaider vos responsables de produits à résoudre ces problèmes. L’exemple suivant utilise une mesure calculée avec un modèle d’attribution de participation pour filtrer les données jusqu’aux sessions qui se sont terminées par un appel au centre d’appel.

L’exemple suivant montre que les pages « Panier » et « Informations sur la commande » génèrent la plupart des appels.

![Pages de contribution](../assets/contributing-pages.png)

La table de cohorte vous permet de voir combien de temps il faut généralement aux utilisateurs pour appeler le centre d’appels après avoir consulté le site Web. L’exemple suivant indique que la durée moyenne de cet exemple de jeu de données est comprise entre trois et quatre semaines.

![Cohorte](../assets/cohort.png)

## Utiliser lʼattribution marketing avancée

CJA vous permet d’utiliser des modèles d’attribution sophistiqués sur vos données cross-canal. Dans lʼexemple suivant, vous pouvez comparer les applications de lʼattribution de chiffre dʼaffaires Dernière touche, Première touche, En U et Algorithmique à la dimension Groupes de canaux de Google Analytics.

![Attribution marketing](../assets/mktg-attribution.png)

A lʼaide dʼune mesure calculée, vous pouvez appliquer cette attribution à vos chiffres dʼaffaires du web et des applications mobiles, et même supprimer les retours de produits. Ainsi, vous pouvez connaître le chiffre dʼaffaires net réel de chaque canal marketing.

![Mesure calculée](../assets/calc-metric.png)

Attribution IQ vous permet également de filtrer vos données. Vous pouvez connaître lʼattribution par rapport à des ensembles spécifiques dʼutilisateurs, tels que ceux qui utilisent plusieurs appareils.

![Filtrer](../assets/filter.png)

Vous pouvez également attribuer votre revenu issu du site Web et de l’application à votre contenu publicitaire Google. L’exemple de ce jeu de données a généré plus de chiffre d’affaires à partir de l’application mobile pilotée par de Google Ads en ligne qu’à partir du Web. En triant les annonces en fonction des revenus tirés du Web et des applications, vous obtenez une vision différente des Google Ads les plus performantes.

![Annonce Google](../assets/google-ad.png)

La combinaison de jeux de données dans CJA vous permet de voir dans cet exemple que les annonces en ligne ont eu un impact sur les produits achetés sur votre application mobile. Vous pouvez maintenant constater que le chiffre d’affaires des applications mobiles généré par Google Ads représente entre 14 000 et 15 000 dollars de plus, par rapport au Web seul.

![Annonce Google 2](../assets/google-ad2.png)
