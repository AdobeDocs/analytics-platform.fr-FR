---
title: Collecte de données Content Analytics
description: Présentation de la collecte de données dans Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Collecte de données Content Analytics

Cet article explique en détail comment Content Analytics collecte des données


## Définitions

Les définitions suivantes sont utilisées dans le cadre de cet article :

* **Expérience** : une expérience est définie comme le contenu textuel d’une page web entière. Pour la collecte de données, Content Analytics enregistre l’Experience ID. Content Analytics n’enregistre pas le texte sur la page.
* **Ressource** : une image. Content Analytics enregistre l’URL de la ressource.
* **URL appropriée** : l’URL de base ainsi que tous les paramètres qui pilotent le contenu sur la page.
* **Experience ID** : combinaison unique d’URL appropriée et de version d’expérience.
   * Dans le cadre de la [configuration](configuration.md), vous spécifiez les paramètres pertinents pour toute URL complète donnée.
   * Vous pouvez définir l’[identifiant de version](manual.md#versioning) utilisé. Pour la collecte de données, la version n’est pas prise en compte. Seule l’URL appropriée est collectée.

## Fonctionnalité

La bibliothèque Content Analytics collecte des données lorsque :

* Content Analytics est inclus dans la bibliothèque de balises chargée sur la page.
* L’URL de la page est configurée dans l’extension [Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, qui fait partie de la bibliothèque de balises incluse.


### Événement Content Analytics

Un événement Content Analytics comprend :

* Champs standard
   * Horodatage
   * Identité
* Vues d’expérience (le cas échéant, et si configurées)
* Clics sur l’expérience (le cas échéant, et si configuré)
* Vues des ressources (le cas échéant, et si elles sont configurées)
* Clics sur les ressources (le cas échéant, et si elles sont configurées)

#### Vues ou clics enregistrés

Une vue de ressource est enregistrée lorsque :

* La ressource n’a pas été exclue par configuration de l’extension ACA.
* L’actif est en vue à 75 %.
* Cette ressource n’a pas encore été enregistrée pour cette page.

Un clic sur une ressource est enregistré dans les cas suivants :

* La ressource a été consultée.
* La ressource n’a pas été exclue par configuration de l’extension ACA.
* Un clic directement sur la ressource, qui est un lien, mène à une autre page.

Une vue d’expérience est enregistrée lorsque :

* Les expériences sont activées dans la configuration Content Analytics.

Un clic sur une expérience est enregistré lorsque :

* Tout clic se produit sur un lien de la page pour lequel les expériences sont activées.


#### Événements envoyés

Les événements Content Analytics sont envoyés lorsque les deux conditions suivantes se produisent :

* Le contenu est envoyé, ce qui se produit lorsque :

   * Une vue de ressource ou un clic est enregistré.
   * Une vue d’expérience ou un clic est enregistré.

* Un déclencheur permettant d’envoyer un événement est déclenché lorsque :

   * Web SDK ou AppMeasurement envoie un événement.
   * La visibilité passe à masquée, par exemple :
      * Déchargements de page
      * Basculer l’onglet
      * Réduire le navigateur
      * Fermer le navigateur
      * Verrouiller l’écran
   * L’URL change, ce qui entraîne la modification d’une URL appropriée.
   * Les vues de ressources dépassent la limite de lot de 32.


## Schémas

Les données Content Analytics sont collectées dans des jeux de données dans Experience Platform, en fonction de schémas Content Analytics spécifiques. Les schémas de référence sont disponibles publiquement et sont utilisés dans une implémentation par défaut de Content Analytics.

* [Schéma des ressources numériques](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schéma d’expérience digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schéma de contenu d’événement d’expérience](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
