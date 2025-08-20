---
description: Découvrez les fonctionnalités de reporting en temps réel dans Customer Journey Analytics.
title: Rapports En Temps Réel - Aperçu
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: d0067d8271b7628f0d174d1fa647ba1b4558ffb4
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 2%

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


## Latences

La manière dont vous collectez les données détermine la latence en temps réel des rapports en temps réel pour Customer Journey Analytics . L’illustration et le tableau ci-dessous montrent les latences approximatives pour divers scénarios de collecte de données lors de l’utilisation de rapports standard et en temps réel.

L’illustration souligne également que les rapports en temps réel utilisent un jeu de données consolidé complètement distinct du [jeu de données consolidé (combiné)](/help/connections/combined-dataset.md) utilisé pour les rapports standard. Utilisez le bouton (bascule) [Actualisation en temps réel](use-real-time.md) pour basculer entre :

* Création de rapports en temps réel sur un jeu de données consolidé contenant jusqu’à 24 heures de données en continu.
* Création de rapports standard sur le jeu de données consolidé qui contient jusqu’à 13 mois de données glissantes (ou plus si vous disposez d’une licence pour le module complémentaire de capacité de données étendue).

![Création de rapports en temps réel](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Collecte de données | Latence des rapports en temps réel | Latence de création de rapports standard |
|:---:|---|--:|--:|
| 1 | SDK/API d’Edge Network dans Edge Network | &approx; &lt; 00h:06m:30s | &approx; &lt; 01h:35m:00s |
| 2 | Connecteurs de diffusion en continu | &approx; &lt; 00h:16m:30s | &approx; &lt; 01h:45m:00s |
| 3 | Connecteur source Adobe Analytics | &approx; &lt; 00h:16m:30s | &approx; &lt; 01h:45m:00s |
| 4 | Autres connecteurs source dans les connecteurs source (y compris les données par lot) | &approx; &lt; 24h:01m:30s | &approx; &lt; 25h:30m:00s |

## Limites

Gardez à l’esprit les limites suivantes pour les rapports en temps réel :

* Les rapports en temps réel ne génèrent que des rapports sur les données disponibles sur une période mobile de 24 heures. Données qui sont supérieures à   L’ancienne version de 24 heures n’est pas disponible pour les rapports en temps réel. Une fois que l’option [actualisation en temps réel](use-real-time.md) d’un rapport est désactivée ou automatiquement désactivée, toutes les données pertinentes sont à nouveau disponibles à partir du [jeu de données consolidé](/help/connections/combined-dataset.md) généralement utilisé pour la création de rapports dans Customer Journey Analytics.
* Attribution, segmentation, mesures calculées, etc. ne fonctionnent que sur les données disponibles au cours de la période glissante de 24 heures. Par exemple, un segment *Visiteurs réguliers* inclut très peu de personnes dans un rapport en temps réel, car le rapport inclut uniquement les personnes qui ont consulté plusieurs fois au cours des dernières 24 heures. Une limitation similaire s’applique lorsque vous créez un rapport en temps réel sur les personnes qui ont cliqué précédemment sur une campagne qui n’est plus active.
* Les rapports en temps réel fonctionnent mieux sur les données au niveau de l’événement et de la session. Soyez prudent lorsque vous utilisez les rapports en temps réel pour les données au niveau de la personne. <!--Need to explain this a bit better --> Étant donné que seuls les événements de la période de 24 heures variable sont disponibles pour les rapports en temps réel, l’historique des événements d’une personne est également limité à cette fenêtre. Tenez compte des préférences en matière de données au niveau de l’événement et de la session lorsque vous sélectionnez une dimension et des mesures (calculées). Et lorsque vous utilisez des fonctionnalités telles que les répartitions, suivant ou précédent, et plus encore dans votre panneau Actualisation en temps réel activée .
* Vous ne pouvez pas combiner le groupement avec les rapports en temps réel. <!-- Do we need to explain this in more detail, why? --> Les rapports en temps réel portent sur les données au niveau des événements et des sessions, et sont moins pertinents pour les données basées sur les personnes.
* Aucune mesure de pulsation collectée sur les médias n’est disponible, à l’exception des mesures de démarrage et de fermeture des médias. Vous pouvez donc toujours utiliser les rapports en temps réel pour activer un cas d’utilisation de média.
* Lorsque vous utilisez les options [télécharger ou exporter](/help/analysis-workspace/export/download-send.md) pour télécharger un projet ou exporter des données d’un tableau à structure libre, tenez compte des points suivants :
   * Un projet CSV téléchargé ou un fichier CSV exporté contient les données en temps réel disponibles au moment du téléchargement ou de l’exportation.
   * Un projet PDF téléchargé contient des données en temps non réel, similaires aux données affichées lorsque l’actualisation en temps réel est désactivée.
