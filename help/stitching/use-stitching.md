---
title: Demander un rapprochement
description: Comment demander un groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 7%

---

# Demander un rapprochement


>[!IMPORTANT]
>
>L’assemblage des requêtes via Adobe n’est plus nécessaire et cette méthode est obsolète. [Activer l’assemblage dans l’interface utilisateur de connexions](use-stitching-ui.md).
>



Une fois que votre organisation remplit toutes les [conditions préalables](overview.md#prerequisites) et comprend les limites communes [limitations](overview.md#limitations) et les limites spécifiques aux méthodes de groupement ([basées sur les champs](fbs.md#limitations) et [basées sur les graphiques](gbs.md#limitations)), vous pouvez suivre les étapes suivantes pour demander et commencer à utiliser le groupement dans Customer Journey Analytics.

## Sélectionner des options

Le package Customer Journey Analytics auquel vous avez droit détermine les méthodes de groupement disponibles, les options pour la durée de renvoi initiale, l’intervalle de recherche en amont, la fréquence de relecture et le nombre maximal de jeux de données autorisés pour le groupement. Voir la description du produit [Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr) pour plus d’informations. Déterminez les options disponibles avant de demander de l’aide.

| | Customer Journey Analytics<br/>Select | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Méthodes de groupement disponibles | Rapprochement basé sur les champs | Assemblage basé sur les champs<br/>assemblage basé sur les graphiques | Assemblage basé sur les champs<br>assemblage basé sur les graphiques</li> |
| Durée de renvoi d’assemblage unique | 13 mois | 13 mois | 25 mois |
| Intervalle de recherche en amont et fréquence de relecture | 1 jour, tous les jours<br/>jusqu’à 7 jours, par semaine | 1 jour, tous les jours<br/>jusqu’à 14 jours, par semaine | 1 jour, tous les jours<br/>jusqu’à 30 jours, par semaine |
| Nombre maximal de jeux de données autorisés pour l’assemblage | 5 | 15 | 50 |

## Demande d’assistance

1. Contactez le service clientèle d’Adobe avec les informations suivantes :

   - Demande d’activation du groupement.
   - L’identifiant du jeu de données pour lequel vous souhaitez recréer la clé.
   - Nom de la colonne (chemin d’identité et espace de noms) de l’identifiant persistant du jeu de données souhaité (identifiant qui apparaît sur chaque ligne).
   - Si le jeu de données prend en charge `identityMap` :
      - Pour le groupement basé sur les champs, spécifiez l’espace de noms pour les ID persistants et de personne.
      - Pour le groupement basé sur les graphiques, spécifiez l’espace de noms de l’identifiant persistant et l’espace de noms d’identité à utiliser pour interroger le graphique d’identité.
   - Si le jeu de données ne prend pas en charge `identityMap` :
      - Pour le groupement basé sur les champs, le nom de colonne de l’ID de personne pour le jeu de données souhaité (l’identifiant de personne, qui agit également comme un lien entre les jeux de données dans le contexte d’une connexion).
      - Pour le groupement basé sur un graphique, espace de noms d’identité à utiliser pour interroger le graphique d’identité.
   - Votre préférence en termes d’intervalle de recherche en amont et de fréquence de relecture. Consultez votre package Customer Journey Analytics pour connaître les [&#x200B; options &#x200B;](#options) disponibles.
   - Nom de la sandbox.


2. Le service clientèle d’Adobe travaille avec l’ingénierie Adobe pour activer le groupement à la réception de votre demande. Une fois activé, un jeu de données recréé contenant une colonne d’ID groupée s’affiche dans Adobe Experience Platform. Le service clientèle d’Adobe peut fournir l’identifiant du nouveau jeu de données.
3. Lorsqu’il est activé pour la première fois, Adobe fournit un renvoi de données assemblées. Consultez votre package Customer Journey Analytics pour connaître l’option [&#x200B; disponible &#x200B;](#options).

4. Si vous souhaitez utiliser le jeu de données groupé dans une analyse cross-canal, vous devez ajouter le jeu de données groupé à une [connexion](../connections/overview.md) dans Customer Journey Analytics. Ajoutez ensuite tous les autres jeux de données requis pour l’analyse cross-canal et sélectionnez l’ID de personne approprié pour chaque jeu de données.

5. [Créez une vue de données](/help/data-views/create-dataview.md) basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, vous pouvez exécuter votre analyse de création de rapports Customer Journey Analytics sur les canaux et les appareils.
