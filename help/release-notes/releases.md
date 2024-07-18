---
description: Explique la stratégie de mise à jour continue des fonctionnalités pour Customer Journey Analytics
title: Stratégie de mise à jour des fonctionnalités de Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 100%

---

# Stratégie de mise à jour des fonctionnalités de Customer Journey Analytics

Les mises à jour de Customer Journey Analytics fonctionnent sur un modèle de diffusion continu qui permet une approche évolutive et progressive du déploiement des fonctionnalités.

## Stratégie de mise à jour

[!UICONTROL Analysis Workspace] utilise des indicateurs de fonctionnalité (également appelés « bascules ») pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet de les tester à échelle contrôlée avant la mise à jour complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Tests limités** : la mise à jour par étapes commence par un test réalisé par les utilisateurs et utilisatrices internes d’Adobe. Elle est ensuite mise à la disposition d’un petit groupe de comptes clients afin de s’assurer que la fonctionnalité répond aux besoins et aux attentes des clientes et clients.

* **Début du déploiement** : le déploiement d’une mise à jour par phases commence par la phase Tests limités. La mise à jour passe à une disponibilité de 0 % à 100 % pour les clients en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une même organisation bénéficient de la même expérience.

* **Disponibilité générale** : la fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et la mise à jour est terminée.

Selon les mises à jour de fonctionnalité, la chronologie peut varier entre la mise en production et la disponibilité générale. L’objectif est que la mise à jour soit courte, afin qu’elle atteigne la disponibilité générale dans un délai de 2 mois à compter de la mise en production.

## Indicateurs de fonctionnalités

Les indicateurs de fonctionnalités permettent de contrôler la visibilité des nouvelles fonctionnalités pendant la mise à jour. Adobe recommande d’autoriser `app.launchdarkly.com` via le pare-feu de votre organisation pour une expérience optimale lors des mises à jour. Ces indicateurs sont supprimés une fois qu’une fonctionnalité est disponible pour toutes les personnes. Voir [Domaines utilisés par Customer Journey Analytics](../technotes/domains.md) pour plus d’informations.

Vous pouvez à tout moment afficher vos indicateurs de fonctionnalités actifs sous **Aide > À propos de Workspace > Indicateurs de fonctionnalités actifs**.

## Avantages

Les mises à jour par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement prêtes avant la disponibilité générale. Cela permet également de mettre les fonctionnalités à disposition tout de suite plutôt que de respecter une fenêtre de mise à jour mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
| --- | --- |
| Puis-je demander un accès anticipé à une fonctionnalité ? | Non. Aucun accès anticipé ne sera accordé.<br>Si vous voulez tester les concepts Analytics en avant-première, nous vous encourageons à essayer [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=fr) pour faire part de vos commentaires sur nos innovations de pointe. |
| Cette stratégie de mise à jour affecte-t-elle mon accès aux fonctionnalités ? | Non. Quand une fonctionnalité atteint la disponibilité générale, vous avez accès à la fonctionnalité à condition qu’elle soit incluse dans votre package Analytics. |
