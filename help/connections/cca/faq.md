---
title: FAQ sur les analyses entre canaux
description: Questions fréquentes sur les analyses entre canaux
translation-type: tm+mt
source-git-commit: dd4e7e5cd04db6483f0e4a1f3161f23f8a5a8294
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 20%

---


# Questions fréquentes

## Comment puis-je utiliser l&#39;ACC pour voir comment les gens passent d&#39;un canal à l&#39;autre ?

Vous pouvez utiliser une visualisation Flux avec la dimension ID du jeu de données.

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension &quot;ID du jeu de données&quot; vers l’emplacement central intitulé &quot;Dimension ou élément&quot;.
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension ID de jeu de données, vous pouvez utiliser un jeu de données de recherche.

## Jusqu&#39;où remonte le retour des visiteurs de l&#39;ACR ?

La fenêtre de recherche de reprise dépend de la fréquence souhaitée de lecture des données [replay](replay.md). Par exemple, si vous configurez la DPA pour qu&#39;elle relaie les données une fois par semaine, la fenêtre de recherche de reprise est de 7 jours. Si vous configurez la DPA pour qu&#39;elle relaie les données tous les jours, la fenêtre de recherche de reprise est d&#39;un jour.

## Comment les périphériques partagés sont-ils gérés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’ID transitoire remplace l’ID persistant, de sorte que les périphériques partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même périphérique).

## Comment l&#39;ACC gère-t-elle les situations où une seule personne a un grand nombre d&#39;identifiants persistants ?

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’identifiants persistants. Par exemple, une personne efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Le nombre d’identifiants persistants n’est pas pertinent en faveur de l’identifiant transitoire. Un utilisateur unique peut appartenir à un certain nombre d&#39;appareils sans que cela n&#39;ait d&#39;incidence sur la capacité de l&#39;ACC de s&#39;accrocher à l&#39;ensemble des appareils.

## Une fois que j’ai contacté mon gestionnaire de compte pour obtenir les informations souhaitées, combien de temps faut-il pour que le jeu de données récupéré soit disponible ?

L’assemblage en direct est disponible environ une semaine après l’activation de l’Adobe dans Analytics sur les canaux croisés. La disponibilité des renvois dépend de la quantité de données existantes. Les petits jeux de données (moins d&#39;un million de événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard de événements par jour) peuvent prendre une semaine ou plus.

## Comment Analytics sur plusieurs canaux gère-t-il les demandes liées aux RMR et aux ACCP ?

L&#39;Adobe traite les demandes du RMPD et de l&#39;ACCP conformément aux lois locales et internationales. Adobe offre le [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) à envoyer des demandes d&#39;accès aux données et de suppression. Les requêtes s’appliquent à la fois aux jeux de données d’origine et aux jeux de données avec clé.
