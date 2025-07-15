---
description: Découvrez les fonctionnalités de reporting en temps réel dans Customer Journey Analytics.
title: Rapports En Temps Réel - Aperçu
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: e7a7a297e303a410c73598f373219644e50ede74
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Création de rapports en temps réel - Aperçu

Les rapports en temps réel dans Customer Journey Analytics affichent et mettent à jour en temps réel les données et les visualisations au sein d’un ou de plusieurs panneaux dans Analysis Workspace.

{{release-limited-testing}}

{{ultimate-package}}

## Cas d’utilisation

Cette section présente un aperçu des cas d’utilisation standard avec une ou plusieurs valeurs. Vous pouvez également obtenir des informations sur les cas dans lesquels il ne faut pas envisager de créer des rapports en temps réel.

* Les cas d’utilisation les plus pertinents pour le reporting en temps réel concernent les ventes, les promotions ou les lancements de produits majeurs.
Dans le cadre de ce lancement, vous souhaitez savoir :

   * Comment les ventes se comparent-elles à votre dernière vente ?
   * En quoi ce lancement de produit se compare-t-il au dernier ?
   * Vos promotions pour cette journée ou cet événement important fonctionnent-elles réellement ?

* Les cas d’utilisation de validation sont des cas d’utilisation pertinents, mais moins utiles pour les rapports en temps réel.
Vous souhaitez valider, par exemple :

   * Le parcours de campagne que vous avez lancé récemment fonctionne-t-il vraiment?
   * Lorsque votre nouvelle page de produits est entrée en ligne, collectez-vous des données client à partir de la page ?
   * Votre événement multimédia en direct se passe-t-il correctement ?

Ne prenez pas en compte les rapports en temps réel pour les cas d’utilisation de la surveillance des opérations. Par exemple, pour répondre à la question : un site fonctionne-t-il réellement ?


## Définition

L’aspect temps réel des rapports en temps réel pour Customer Journey Analytics est défini comme les données et les visualisations qui sont mises à jour dans les 5 minutes environ suivant le moment où les données sous-jacentes sont ingérées par le biais de la connexion associée.

## Limites

Vous devez tenir compte des limitations suivantes concernant les rapports en temps réel :

* Les rapports en temps réel ne génèrent que des rapports sur les données disponibles sur une période mobile de 24 heures. Les données qui dépassent cette période de 24 heures ne sont pas disponibles.
* Attribution, segmentation, mesures calculées, etc. ne fonctionnent que sur les données disponibles au cours de la période glissante de 24 heures.
* Les rapports en temps réel fonctionnent mieux sur les données au niveau de l’événement et de la session. Soyez prudent lorsque vous utilisez les rapports en temps réel pour les données au niveau de la personne. <!--Need to explain this a bit better --> Étant donné que seuls les événements de la période de 24 heures variable sont disponibles pour les rapports en temps réel, l’historique des événements d’une personne est également limité à cette fenêtre. Tenez compte de la préférence pour les données au niveau de l’événement et de la session lorsque vous sélectionnez des mesures (calculées) de dimension. Et lorsque vous utilisez des fonctionnalités telles que les répartitions, suivant ou précédent, et plus encore dans votre panneau Actualisation en temps réel activée .
* Vous ne pouvez pas combiner le groupement avec les rapports en temps réel. <!-- Do we need to explain this in more detail, why? --> Comme mentionné ci-dessus, les rapports en temps réel portent sur les données au niveau des événements et des sessions, et pas tant sur les données basées sur les personnes.
* Aucune mesure de pulsation collectée sur les médias n’est disponible, à l’exception des mesures de démarrage et de fermeture des médias. Vous pouvez donc toujours utiliser les rapports en temps réel pour activer un cas d’utilisation de média.
