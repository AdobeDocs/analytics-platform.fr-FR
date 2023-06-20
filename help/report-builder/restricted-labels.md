---
title: Que sont les libellés restreints dans Report Builder ?
description: Décrit les libellés restreints dans Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 60%

---

# Libellés restreints dans Report Builder

En règle générale, les paramètres liés à la gouvernance de données dans Customer Journey Analytics sont hérités d’Adobe Experience Platform. L’intégration entre la gouvernance des données Customer Journey Analytics et Adobe Experience Platform permet d’étiqueter les données de Customer Journey Analytics sensibles et d’appliquer les politiques de confidentialité.

Les étiquettes de confidentialité et les stratégies créées sur les jeux de données consommés par l’Experience Platform peuvent être affichées dans le workflow de vues de données du Customer Journey Analytics. Ces étiquettes arrêtent ou avertissent les utilisateurs qui créent des mesures et/ou des dimensions à partir de champs sensibles. Pour plus d’informations sur les jeux de données, consultez la [Présentation des jeux de données](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=fr)

En outre, lorsque des données sont exportées à partir d’un Customer Journey Analytics (par le biais de rapports, d’exports, d’API, etc.), des avertissements ou des libellés sont ajoutés afin d’informer les utilisateurs qu’un rapport contient des informations sensibles qui doivent être traitées d’une manière spécifique.

Cette intégration vous permet de gérer la conformité plus facilement. Les gestionnaires de données de votre entreprise peuvent définir des politiques pour restreindre l’utilisation. Par conséquent, vos utilisateurs Customer Journey Analytics peuvent utiliser les données avec plus de confiance, en sachant qu’elles sont conformes aux stratégies définies par les gestionnaires de données.

Pour plus d’informations, voir [Customer Journey Analytics et gouvernance des données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=fr)

## Afficher des données limitées dans Report Builder

Deux stratégies définies par l’Adobe sont affichées dans Customer Journey Analytics et affectent le reporting, le téléchargement et le partage :

* Politique Application d’Analytics
* Politique Application du téléchargement

Les composants affectés par ces politiques sont grisés. Lorsque vous passez la souris sur un composant auquel une stratégie est appliquée, une note s’affiche pour indiquer les éléments suivants : **Des politiques ont été appliquées à ce champ pour interdire l’utilisation de ces données.** Pour plus d’informations, voir [Étiquettes et politiques](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=fr).

![](assets/rb-restricted-label.png)

## Mettre à jour les rapports contenant des données limitées

Dans les cas où un utilisateur a créé un rapport Report Builder avec des éléments de données ultérieurement limités, un message d’erreur s’affiche lorsque le rapport est actualisé.

![](assets/error-restricted-data.png)
