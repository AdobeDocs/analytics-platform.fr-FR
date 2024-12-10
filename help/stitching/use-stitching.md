---
title: Utilisation de l’assemblage
description: Utilisation du groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 5e25cb4d974ab85cca3aa2bb777675e12f63038b
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 9%

---

# Utilisation de l’assemblage

Une fois que votre organisation a satisfait à toutes les [conditions préalables](#prerequisites) et comprend les [limites](#limitations) et les limites spécifiques aux méthodes de groupement ([basées sur les champs](#limitations-1) et [basées sur des graphiques](#limitations-2)), vous pouvez suivre ces étapes pour commencer à utiliser le groupement en Customer Journey Analytics.

## Options de sélection

Le module de Customer Journey Analytics que vous êtes autorisé à utiliser détermine les méthodes de regroupement disponibles, les options relatives à la durée de renvoi initiale, l’intervalle de recherche en amont, la fréquence de relecture et le nombre maximal de jeux de données autorisés pour le regroupement. Pour plus d’informations, voir la [description du produit Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=fr) . Déterminez les options disponibles avant de demander l’assistance.

| | Customer Journey Analytics<br/>Select | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Méthodes de groupement disponibles | <li>Groupement basé sur les champs</li> | <li>Groupement basé sur les champs</li><li>Groupement basé sur les graphiques</li> | <li>Groupement basé sur les champs</li><li>Groupement basé sur les graphiques</li> |
| Durée de renvoi groupé une fois | 13 mois | 13 mois | 25 mois |
| Intervalle de recherche en amont et fréquence de relecture | <li>1 jour, tous les jours</li><li>jusqu’à 7 jours, hebdomadaire</li> | <li>1 jour, tous les jours</li><li>jusqu’à 14 jours, hebdomadaire</li> | <li>1 jour, tous les jours</li><li>jusqu’à 30 jours, hebdomadaire</li> |
| Nombre maximal de jeux de données autorisés pour le groupement | 5 | 10 | 50 |

## Demande d’assistance

1. Contactez le service clientèle d’Adobe avec les informations suivantes :

   - Demande d’activation du groupement.
   - Identifiant du jeu de données pour le jeu de données que vous souhaitez recomposer.
   - Nom de colonne (chemin d’identité et espace de noms) de l’identifiant persistant du jeu de données souhaité (l’identifiant qui apparaît sur chaque ligne).
   - Pour le groupement basé sur les champs, nom de colonne de l’identifiant transitoire pour le jeu de données souhaité (l’identifiant de personne, qui agit également comme un lien entre les jeux de données dans le contexte d’une connexion). Pour le groupement basé sur un graphique, l’espace de noms d’identité à utiliser pour l’interrogation du graphique d’identités.
   - Votre préférence en termes de intervalle de recherche en amont et de fréquence de relecture. Consultez votre package de Customer Journey Analytics pour connaître les [options](#options) disponibles.
   - Nom de la sandbox.


2. Le service clientèle d’Adobe travaille avec le service d’ingénierie d’Adobe pour activer l’assemblage à la réception de votre demande. Une fois activé, un nouveau jeu de données recomposées contenant une nouvelle colonne d’identifiant assemblé s’affiche dans Adobe Experience Platform. Le service clientèle d’Adobe peut fournir l’identifiant du nouveau jeu de données.

3. Lorsque l’Adobe est activé pour la première fois, il fournit un renvoi des données assemblées. Consultez votre package de Customer Journey Analytics pour l’ [option](#options) disponible.

4. Si vous souhaitez utiliser le nouveau jeu de données assemblé dans une analyse cross-canal, vous devez ajouter le nouveau jeu de données assemblé à une [connexion](../connections/overview.md) dans Customer Journey Analytics. Ajoutez ensuite tout autre jeu de données requis pour l’analyse cross-canal, puis sélectionnez l’identifiant de personne correct pour chaque jeu de données.

5. [Créez une vue de données](/help/data-views/create-dataview.md) basée sur la connexion.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Une fois la vue de données configurée, vous pouvez exécuter l’analyse des rapports du Customer Journey Analytics sur les canaux et les appareils.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->



