---
title: Collecte de données dans Content Analytics
description: Vue d’ensemble de la collecte de données dans Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 97%

---

# Collecte de données dans Content Analytics

Cet article explique en détail comment Content Analytics collecte les données

## Définitions

Les définitions suivantes sont utilisées dans le cadre de cet article :

* **Expérience** : une expérience est définie comme le contenu textuel d’une page web entière. Pour la collecte de données, Content Analytics enregistre l’ID d’expérience qui est basé sur l’URL de la page. Ensuite, le texte de la page est capturé via le service de récupération.
* **Experience ID** : combinaison unique d’une URL appropriée (URL de base et paramètres déterminant le contenu de la page) et d’une [version d’expérience](manual.md#versioning).
   * Dans le cadre de la [configuration](configuration.md), vous spécifiez les paramètres pertinents pour toute URL complète donnée.
   * Vous définissez un [identifiant de version](manual.md#versioning) à utiliser afin de collecter correctement les modifications apportées à vos expériences.
* **Ressource** : une image. Content Analytics enregistre l’URL de la ressource.
* **ID de ressource** : URL de la ressource.
* **URL appropriée** : l’URL de base ainsi que tous les paramètres qui pilotent le contenu sur la page.


## Fonctionnalité

Content Analytics nécessite que le SDK Web Experience Platform Edge Network collecte des données d’événement de contenu. Cette collecte de données d’événement est associée à la collecte de données (existantes) de données d’événement comportemental par le biais de mécanismes tels qu’Experience Platform Edge Network (SDK Web, API du serveur) ou le connecteur source Analytics (par exemple, à l’aide d’AppMeasurement).

La bibliothèque Content Analytics collecte des données lorsque :

* Content Analytics est inclus dans la bibliothèque de balises chargée sur la page.
* L’URL de la page est configurée dans l’extension [Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, qui fait partie de la bibliothèque de balises incluse.


## Événement Content Analytics

Un événement Content Analytics comprend les éléments suivants :

* Champs standard
   * Date et heure
   * Identité
* Vues d’expérience (le cas échéant, et si configurées)
* Clics sur l’expérience (le cas échéant, et si configurés)
* Vues de ressources (le cas échéant, et si configurées)
* Clics sur les ressources (le cas échéant, et si configurés)

Les événements Content Analytics sont collectés comme une séquence des éléments suivants :

1. [Vue ou clic enregistrés](#recorded-view-or-click).
1. [Déclencheur permettant d’envoyer un événement Content Analytics](#trigger-to-send-a-content-analytics-event).

Content Analytics collecte les données de cette manière pour refléter cette séquence, au lieu de collecter une vue ou un clic séparément à partir de l’événement qui suit immédiatement. Cette méthode de collecte des données Content Analytics réduit également la quantité de données collectées.

### Vue ou clic enregistrés

Une vue de ressource est enregistrée lorsque :

* La ressource n’a pas été exclue conformément à la configuration de l’extension Content Analytics.
* La ressource est vue à 75 %.
* Cette ressource n’a pas encore été enregistrée pour cette page.

Un clic sur une ressource est enregistré dans les cas suivants :

* La ressource a été vue.
* La ressource n’a pas été exclue conformément à la configuration de l’extension Content Analytics.
* Un clic directement sur la ressource, qui est un lien, conduit à une autre page.

Une vue d’expérience est enregistrée lorsque :

* Les expériences sont activées dans la configuration Content Analytics.

Un clic sur une expérience est enregistré lorsque :

* Tout clic se produit sur un lien d’une page pour laquelle des expériences sont activées.


### Déclencheur pour envoyer un événement Content Analytics

Pour réduire le nombre d’appels quittant la page, Content Analytics collecte des informations mais ne les envoie pas immédiatement. Les informations d’interaction de contenu sont collectées et un événement contenant ces informations n’est envoyé que lorsque l’un des déclencheurs suivants se produit :

* Le SDK Web ou AppMeasurement envoie un événement.
* La visibilité passe à masquée, par exemple :
   * Charger une page
   * Basculer d’onglet à un autre
   * Réduire le navigateur
   * Fermer le navigateur
   * Verrouiller l’écran
* L’URL est modifiée en conséquence.
* Les vues de ressources enregistrées et prêtes à être envoyées dépassent le nombre de 32.

>[!NOTE]
>
>Les événements Content Analytics supplémentaires influencent probablement toute définition de taux de rebond basée sur le nombre d’événements dans une session ou sur une page.
>


## Schémas

Les données Content Analytics sont collectées dans des jeux de données dans Experience Platform, en fonction de schémas Content Analytics spécifiques. Les schémas de référence sont accessibles au public :

* [Schéma des ressources numériques](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schéma d’expérience digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schéma de contenu d’événement d’expérience](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
