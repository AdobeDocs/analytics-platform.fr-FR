---
description: Découvrez les fonctionnalités de reporting en temps réel dans Customer Journey Analytics.
title: Rapports En Temps Réel - Aperçu
feature: Real-time Reporting
role: User
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 6%

---

# Création de rapports en temps réel - Aperçu

Les rapports en temps réel dans Customer Journey Analytics affichent et mettent à jour en temps réel les données et les visualisations au sein d’un ou de plusieurs panneaux dans Analysis Workspace.

{{ultimate-package}}

>[!TIP]
>
>Si vous avez droit au package Ultimate, mais ne voyez pas le bouton [Actualisation en temps réel](use-real-time.md), créez un ticket d’assistance clientèle pour demander à activer le compte rendu des performances en temps réel pour votre organisation.


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

## Fonctionnement

Les rapports en temps réel utilisent un jeu de données consolidé complètement distinct du [jeu de données consolidé (combiné)](/help/connections/combined-dataset.md) utilisé pour les rapports standard. Utilisez le bouton (bascule) [Actualisation en temps réel](use-real-time.md) pour basculer entre :

* Création de rapports en temps réel sur un jeu de données consolidé contenant jusqu’à 24 heures de données en continu.
* Création de rapports standard sur le jeu de données consolidé qui contient jusqu’à 13 mois de données glissantes (ou plus si vous disposez d’une licence pour le module complémentaire de capacité de données étendue).

![Reporting en temps réel](assets/real-time-reporting-latencies.svg){zoomable="yes"}

### Latences

La manière dont vous collectez les données détermine la latence des rapports en temps réel dans Customer Journey Analytics. L’illustration ci-dessus et le tableau ci-dessous montrent les latences approximatives pour divers scénarios de collecte de données lors de l’utilisation de rapports en temps réel et (à titre de comparaison) standard.

| | Collecte de données | Rapport en temps réel <br/> latence (approx. inférieur à) | <br/> standard de latence pour les rapports (approx. inférieur à) |
|:---:|---|--:|--:|
| 1 | SDK/API d’Edge Network dans Edge Network | 7 minutes | 95 minutes |
| 2 | Connecteurs de diffusion en continu | 17 minutes | 105 minutes |
| 3 | Connecteur source Adobe Analytics | 17 minutes | 105 minutes |
| 4 | Autres connecteurs source dans les connecteurs source (y compris les données par lot) | 25 heures | 25 heures |

Si une interruption de service se produit pendant plus d’une demi-heure, les données en temps réel ne sont pas renvoyées avec des données une fois les problèmes résolus. Au lieu de cela, la création de rapports en temps réel récupère des données en temps réel à partir du moment où les services recommencent à fonctionner. Aucune donnée n’est perdue pendant cette période et toujours disponible en utilisant les fonctionnalités de création de rapports standard en dehors de la création de rapports en temps réel.

## Limites

Gardez à l’esprit les limites suivantes pour les rapports en temps réel :

* Les rapports en temps réel ne génèrent que des rapports sur les données disponibles sur une période mobile de 24 heures. Données qui sont supérieures à   L’ancienne version de 24 heures n’est pas disponible pour les rapports en temps réel. Une fois que l’option [actualisation en temps réel](use-real-time.md) d’un rapport est désactivée ou automatiquement désactivée, toutes les données pertinentes sont à nouveau disponibles à partir du [jeu de données consolidé](/help/connections/combined-dataset.md) généralement utilisé pour la création de rapports dans Customer Journey Analytics.
* Attribution, segmentation, mesures calculées, etc. ne fonctionnent que sur les données disponibles au cours de la période glissante de 24 heures. Par exemple, un segment *Visiteurs réguliers* inclut très peu de personnes dans un rapport en temps réel, car le rapport inclut uniquement les personnes qui ont consulté plusieurs fois au cours des dernières 24 heures. Une limitation similaire s’applique lorsque vous créez un rapport en temps réel sur les personnes qui ont cliqué précédemment sur une campagne qui n’est plus active.
* Les rapports en temps réel fonctionnent mieux sur les données au niveau de l’événement et de la session. Soyez prudent lorsque vous utilisez les rapports en temps réel pour les données au niveau de la personne. Puisque seuls les événements de la période de 24 heures variable sont disponibles pour les rapports en temps réel, l’historique des événements d’une personne est également limité à cette fenêtre. Tenez compte des préférences en matière de données au niveau de l’événement et de la session lorsque vous sélectionnez une dimension et des mesures (calculées). Et lorsque vous utilisez des fonctionnalités telles que les répartitions, suivant ou précédent, et plus encore dans votre panneau Actualisation en temps réel activée .
* Vous ne pouvez pas combiner le groupement avec les rapports en temps réel. Les rapports en temps réel portent sur les données au niveau des événements et des sessions, et sont moins pertinents pour les données basées sur les personnes.
* Aucune mesure de pulsation collectée sur les médias n’est disponible, à l’exception des mesures de démarrage et de fermeture des médias. Vous pouvez donc toujours utiliser les rapports en temps réel pour activer un cas d’utilisation de média.
* Lorsque vous utilisez les options [télécharger ou exporter](/help/analysis-workspace/export/download-send.md) pour télécharger un projet ou exporter des données d’un tableau à structure libre, tenez compte des points suivants :
   * Un projet CSV téléchargé ou un fichier CSV exporté contient les données en temps réel disponibles au moment du téléchargement ou de l’exportation.
   * Un projet PDF téléchargé contient des données en temps non réel, similaires aux données affichées lorsque l’actualisation en temps réel est désactivée.
