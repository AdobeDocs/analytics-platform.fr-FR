---
description: Explique la stratégie de mise à jour continue des fonctionnalités pour Customer Journey Analytics
title: Mise à jour des fonctionnalités de Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: 44a140fdd5069cbe806f694377802215bcf50b31
workflow-type: ht
source-wordcount: '359'
ht-degree: 100%

---

# Mise à jour des fonctionnalités de Customer Journey Analytics

Les mises à jour de Customer Journey Analytics fonctionnent sur un modèle de diffusion continu qui permet une approche évolutive et progressive du déploiement des fonctionnalités.

## Stratégie de mise à jour

[!UICONTROL Analysis Workspace] utilise des indicateurs de fonctionnalité (également appelés « bascules ») pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet de les tester à échelle contrôlée avant la mise à jour complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Début du déploiement** : le déploiement d’une version par phases commence par des tests limités réalisés par les utilisateurs d’Adobe internes. La mise à jour passe à une disponibilité de 0 % à 100 % pour les clients en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une même organisation bénéficient de la même expérience.

* **Disponibilité générale** : la fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et la mise à jour est terminée.

Selon les mises à jour de fonctionnalité, la chronologie peut varier entre la mise en production et la disponibilité générale. L’objectif est que la mise à jour soit courte, afin qu’elle atteigne la disponibilité générale dans un délai de 2 mois à compter de la mise en production.

## Indicateurs de fonctionnalités

Les indicateurs de fonctionnalités permettent de contrôler la visibilité des nouvelles fonctionnalités pendant la mise à jour. Adobe recommande d’ajouter `app.launchdarkly.com` à la [liste autorisée](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=fr) de votre pare-feu pour une expérience optimale lors de la mise à jour. Peu de temps après avoir atteint la disponibilité générale, l’indicateur est retiré.

Vous pouvez à tout moment afficher vos indicateurs de fonctionnalités actifs sous **Aide > À propos de Workspace > Indicateurs de fonctionnalités actifs**.

## Avantages

Les mises à jour par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement prêtes avant la disponibilité générale. Cela permet également de mettre les fonctionnalités à disposition tout de suite plutôt que de respecter une fenêtre de mise à jour mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
| --- | --- |
| Puis-je demander un accès anticipé à une fonctionnalité ? | Non. Aucun accès anticipé ne sera accordé.<br>Si vous voulez tester les concepts Analytics en avant-première, nous vous encourageons à essayer [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=fr) pour faire part de vos commentaires sur nos innovations de pointe. |
| Cette stratégie de mise à jour affecte-t-elle mon accès aux fonctionnalités ? | Non. Quand une fonctionnalité atteint la disponibilité générale, vous avez accès à la fonctionnalité à condition qu’elle soit incluse dans votre pack Analytics. |
