---
title: Collecte de données Content Analytics
description: Présentation de la collecte de données dans Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: f39cf7c386c42488d6607154fc7922911df5527c
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 1%

---

# Collecte de données Content Analytics

Cet article explique en détail comment Content Analytics collecte des données


## Définitions

Les définitions suivantes sont utilisées dans le cadre de cet article :

* **Expérience** : une expérience est définie comme le contenu textuel d’une page web entière. Pour la collecte de données, Content Analytics enregistre l’Experience ID qui est basé sur l’URL de la page. Plus tard, le texte de la page est capturé via le service de récupération.
* **Experience ID** : combinaison unique d’une URL appropriée (URL de base et paramètres déterminant le contenu de la page) et d’une [version d’expérience](manual.md#versioning).
   * Dans le cadre de la [configuration](configuration.md), vous spécifiez les paramètres pertinents pour toute URL complète donnée.
   * Vous définissez un [identifiant de version](manual.md#versioning) à utiliser afin de collecter correctement les modifications apportées à vos expériences.
* **Ressource** : une image. Content Analytics enregistre l’URL de la ressource.
* **ID de ressource** : URL de la ressource.
* **URL appropriée** : l’URL de base ainsi que tous les paramètres qui pilotent le contenu sur la page.


## Fonctionnalité

Content Analytics nécessite qu’Experience Platform Edge Network Web SDK collecte des données d’événement de contenu. Cette collecte de données d’événement est associée à la collecte de données (existantes) de données d’événement comportemental par le biais de mécanismes tels qu’Experience Platform Edge Network (Web SDK, API du serveur) ou le connecteur source Analytics (par exemple, à l’aide d’AppMeasurement).

La bibliothèque Content Analytics collecte des données lorsque :

* Content Analytics est inclus dans la bibliothèque de balises chargée sur la page.
* L’URL de la page est configurée dans l’extension [Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, qui fait partie de la bibliothèque de balises incluse.



## Événement Content Analytics

Un événement Content Analytics comprend :

* Champs standard
   * Horodatage
   * Identité
* Vues d’expérience (le cas échéant, et si configurées)
* Clics sur l’expérience (le cas échéant, et si configuré)
* Vues des ressources (le cas échéant, et si elles sont configurées)
* Clics sur les ressources (le cas échéant, et si elles sont configurées)


Les événements Content Analytics sont collectés comme une séquence de :

1. [Affichage enregistré ou clic](#recorded-view-or-click).
1. [Déclencheur permettant d’envoyer un événement Content Analytics](#trigger-to-send-a-content-analytics-event).

Content Analytics collecte les données de cette manière pour refléter cette séquence, au lieu de collecter une vue ou un clic séparément de la collecte de l’événement qui suit immédiatement cette vue ou ce clic. Cette méthode de collecte des données d’analyse de contenu réduit également la quantité de données collectées.

### Vue enregistrée ou clic

Une vue de ressource est enregistrée lorsque :

* La ressource n’a pas été exclue par configuration de l’extension Content Analytics.
* L’actif est en vue à 75 %.
* Cette ressource n’a pas encore été enregistrée pour cette page.

Un clic sur une ressource est enregistré dans les cas suivants :

* La ressource a été consultée.
* La ressource n’a pas été exclue par configuration de l’extension Content Analytics.
* Un clic directement sur la ressource, qui est un lien, mène à une autre page.

Une vue d’expérience est enregistrée lorsque :

* Les expériences sont activées dans la configuration Content Analytics.

Un clic sur une expérience est enregistré lorsque :

* Tout clic se produit sur un lien de la page pour lequel les expériences sont activées.


### Déclencheur d’envoi d’un événement Content Analytics

Pour réduire le nombre d’appels quittant la page, Content Analytics collecte des informations mais ne les envoie pas immédiatement. Les informations d’interaction de contenu sont collectées et un événement contenant ces informations n’est envoyé que lorsque l’un des déclencheurs suivants se produit :

* Web SDK ou AppMeasurement envoie un événement. La date et l’heure de cet événement sont
* La visibilité passe à masquée, par exemple :
   * Déchargements de page
   * Basculer l’onglet
   * Réduire le navigateur
   * Fermer le navigateur
   * Verrouiller l’écran
* L’URL change, ce qui entraîne la modification d’une URL appropriée.
* Les vues de ressources enregistrées et prêtes à être envoyées dépassent le nombre de 32.


## Schémas

Les données Content Analytics sont collectées dans des jeux de données dans Experience Platform, en fonction de schémas Content Analytics spécifiques. Les schémas de référence sont accessibles au public :

* [Schéma des ressources numériques](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schéma d’expérience digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schéma de contenu d’événement d’expérience](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
