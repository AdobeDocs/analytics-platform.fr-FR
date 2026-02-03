---
title: Assemblage des demandes
description: Découvrez comment demander un groupement.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 26%

---

# Demander un rapprochement


>[!IMPORTANT]
>
>L’assemblage des requêtes via Adobe n’est plus nécessaire et cette méthode est obsolète. [Activer l’assemblage dans l’interface utilisateur de connexions](use-stitching-ui.md).
>

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

## Limites

- Appliquez également toute modification que vous apportez au schéma du jeu de données d’événement source au nouveau schéma du jeu de données groupé.

- Si vous supprimez le jeu de données source, le jeu de données groupé cesse le traitement et est supprimé par le système.

- Les libellés d’utilisation des données ne sont pas propagés automatiquement au schéma du jeu de données groupé. Si des libellés d’utilisation des données sont appliqués au schéma du jeu de données source, vous devez appliquer manuellement ces libellés d’utilisation des données au schéma du jeu de données groupé. Consultez [Gérer les libellés d’utilisation des données dans Experience Platform &#x200B;](https://experienceleague.adobe.com/fr/docs/experience-platform/data-governance/labels/overview) pour plus d’informations.
