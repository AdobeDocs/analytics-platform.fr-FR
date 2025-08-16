---
description: Découvrez les fonctionnalités de reporting en temps réel dans Customer Journey Analytics.
title: Rapports En Temps Réel - Aperçu
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 3%

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

   * Le parcours de campagne que vous avez récemment lancé fonctionne-t-il réellement ?
   * Lorsque votre nouvelle page de produits est entrée en ligne, collectez-vous des données client à partir de la page ?
   * Votre événement multimédia en direct se passe-t-il correctement ?

Ne prenez pas en compte les rapports en temps réel pour les cas d’utilisation de la surveillance des opérations. Par exemple, pour répondre à la question de savoir si un site fonctionne correctement. Comme le bouton (bascule) [ Actualisation en temps réel ](use-real-time.md) se désactive automatiquement au bout de 30 minutes et que l’actualisation du rapport en temps réel cesse, vous ne devez pas utiliser un rapport en temps réel comme source fiable pour ces cas d’utilisation.


## Définition

L’aspect temps réel des rapports en temps réel pour Customer Journey Analytics est défini comme les données et les visualisations qui sont mises à jour dans les 6,5 minutes environ suivant le moment où les données sous-jacentes sont ingérées par la connexion associée.

Différents composants de la configuration de votre collecte de données déterminent la latence de création de rapports en temps réel.

![Création de rapports en temps réel](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Description | Latence |
|:---:|---|--:|
| 1 | Données collectées via les API/SDK Edge Network dans Edge Network. | &lt; 500 millisecondes |
| 2 | Données répliquées d’Edge Network vers le service de collecte et de validation de données dans Experience Platform Hub. | &lt; 5 minutes |
| 3 | Données collectées par le biais de connecteurs de diffusion en continu dans le service de collecte et de validation des données dans Experience Platform Hub. | &lt; 15 minutes |
| 4 | Données collectées via Adobe Analytics et transférées par le connecteur source Analytics vers le processeur des connecteurs source dans Experience Platform Hub. | &lt; 15 minutes |
| 5 | Données collectées via d’autres connecteurs source dans le processeur des connecteurs source d’Experience Platform Hub. | &lt; 24 heures |
| 6 | Données traitées par le processeur en temps réel pour un jeu de données consolidé pour les rapports en temps réel. | &lt; 90 secondes |

## Limites

Gardez à l’esprit les limites suivantes pour les rapports en temps réel :

* Les rapports en temps réel ne génèrent que des rapports sur les données disponibles sur une période mobile de 24 heures. Les données qui traversent cette période de 24 heures sont masquées pour les rapports en temps réel. Une fois que l’option [actualisation en temps réel](use-real-time.md) d’un rapport est désactivée ou automatiquement désactivée, toutes les données pertinentes pour un rapport sont à nouveau disponibles.
* Attribution, segmentation, mesures calculées, etc. ne fonctionnent que sur les données disponibles au cours de la période glissante de 24 heures.
* Les rapports en temps réel fonctionnent mieux sur les données au niveau de l’événement et de la session. Soyez prudent lorsque vous utilisez les rapports en temps réel pour les données au niveau de la personne. <!--Need to explain this a bit better --> Étant donné que seuls les événements de la période de 24 heures variable sont disponibles pour les rapports en temps réel, l’historique des événements d’une personne est également limité à cette fenêtre. Tenez compte des préférences en matière de données au niveau de l’événement et de la session lorsque vous sélectionnez une dimension et des mesures (calculées). Et lorsque vous utilisez des fonctionnalités telles que les répartitions, suivant ou précédent, et plus encore dans votre panneau Actualisation en temps réel activée .
* Vous ne pouvez pas combiner le groupement avec les rapports en temps réel. <!-- Do we need to explain this in more detail, why? --> Les rapports en temps réel portent sur les données au niveau des événements et des sessions, et sont moins pertinents pour les données basées sur les personnes.
* Aucune mesure de pulsation collectée sur les médias n’est disponible, à l’exception des mesures de démarrage et de fermeture des médias. Vous pouvez donc toujours utiliser les rapports en temps réel pour activer un cas d’utilisation de média.
* Lorsque vous utilisez les options [télécharger ou exporter](/help/analysis-workspace/export/download-send.md) pour télécharger un projet ou exporter des données d’un tableau à structure libre, tenez compte des points suivants :
   * Un projet CSV téléchargé ou un fichier CSV exporté contient les données en temps réel disponibles au moment du téléchargement ou de l’exportation.
   * Un projet PDF téléchargé contient des données en temps non réel, similaires aux données affichées lorsque l’actualisation en temps réel est désactivée.
