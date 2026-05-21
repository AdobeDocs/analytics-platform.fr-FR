---
title: Collecte de données Content Analytics
description: Découvrez comment les données sont collectées dans Content Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
TQID: https://experienceleague.adobe.com/B2j6BrXAHMu-3LKI61LbK01i-UdpMlELsqYSfAWYDCo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1093
ht-degree: 52%

---


# Collecte de données dans Content Analytics

Cet article explique en détail comment Content Analytics collecte les données

## Définitions

Les définitions suivantes sont utilisées dans le cadre de cet article :

* **Expérience** :
   * Pour le canal **web**, une expérience est définie comme le contenu textuel d’une page web entière. Pour la collecte de données, Content Analytics enregistre l’Experience ID basé sur l’URL de la page. Ensuite, le texte de la page est capturé via le service de récupération.
   * Pour le canal **mobile**, une expérience est définie et suivie dans l’application mobile à l’aide de l’extension Content Analytics pour Adobe Experience Platform Mobile SDK.
* **Experience ID** :
   * Pour le canal web, l’ID d’expérience est une combinaison unique de l’URL appropriée (URL de base plus tous les paramètres qui génèrent du contenu sur la page) et de la [version de l’expérience](manual.md#versioning).
      * Dans le cadre de la [configuration](configuration.md), vous spécifiez les paramètres pertinents pour toute URL complète donnée.
      * Vous définissez un [identifiant de version](manual.md#versioning) à utiliser afin de collecter correctement les modifications apportées à vos expériences.
   * Pour le canal **mobile**, l’ID d’expérience est la valeur renvoyée par à l’aide de l’appel API `registerExperience`.
* **Ressource** : une image. Content Analytics enregistre l’URL de la ressource.
* **ID de ressource** : URL de la ressource.
* **URL appropriée** : l’URL de base ainsi que tous les paramètres qui pilotent le contenu sur la page.


## Fonctionnalité

Content Analytics nécessite Experience Platform Edge Network Web SDK (pour le canal web) et Experience Platform Edge Network Mobile SDK (pour le canal mobile) pour collecter des données d’événement de contenu. Ces données d’événement sont combinées avec des données comportementales existantes à l’aide d’Experience Platform Edge Network (Web SDK, Mobile SDK ou API du serveur) ou d’un connecteur source Analytics, tel qu’Adobe AppMeasurement.

La bibliothèque Content Analytics collecte des données lorsque :

* Content Analytics est inclus dans la bibliothèque de balises chargée sur la page ou utilisée dans l’application mobile.
* L’URL de la page et l’URL de la ressource sont configurées dans l’extension web [&#128279;](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, qui fait partie de la bibliothèque de balises incluse.
* L’URL de la ressource, l’emplacement de la ressource ou l’emplacement de l’expérience ne sont pas exclus dans l’extension mobile Content Analytics [&#128279;](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).


## Événement Content Analytics

Cette section décrit les spécificités des événements Web Content Analytics. Voir [Tracking d’expérience](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/) pour plus d’informations sur les événements Content Analytics mobiles.
Un événement Content Analytics comprend les éléments suivants :

* Champs standard
   * Date et heure
   * Identité
* Vues d’expérience (le cas échéant, et si configurées)
* Clics sur l’expérience (le cas échéant, et si configurés)
* Vues de ressources (le cas échéant, et si configurées)
* Clics sur les ressources (le cas échéant, et si configurés)

Les événements Content Analytics sont collectés comme une séquence des éléments suivants :

1. Un [affichage enregistré ou clic](#recorded-view-or-click).
1. Déclencheur [&#x200B; pour envoyer un événement Content Analytics](#trigger-to-send-a-content-analytics-event).

Content Analytics collecte les données de cette manière pour refléter cette séquence, au lieu de collecter une vue ou un clic séparément à partir de l’événement qui suit immédiatement. Cette méthode de collecte des données d’analyse de contenu réduit également la quantité de données collectées.

### Vue ou clic enregistrés

Une vue de ressource est enregistrée lorsque :

* La ressource n’a pas été exclue conformément à la configuration de l’extension Content Analytics.
* La ressource est vue à 75 %.
* Cette ressource n’a pas encore été enregistrée pour cette page.

Un clic sur une ressource est enregistré dans les cas suivants :

* La ressource a été vue.
* La ressource n’a pas été exclue conformément à la configuration de l’extension Content Analytics.
* Un clic direct sur la ressource, qui est un lien, mène à une autre page.

Une vue d’expérience est enregistrée lorsque :

* Les expériences sont activées dans la configuration Content Analytics.

Un clic sur une expérience est enregistré lorsque :

* Tout clic sur un lien activé déclenche une expérience.


### Déclencheur pour envoyer un événement Content Analytics

Pour réduire le nombre de requêtes réseau envoyées à partir de la page, Content Analytics collecte des informations mais ne les envoie pas immédiatement. Les informations d’interaction de contenu sont collectées et un événement contenant ces informations n’est envoyé que lorsque l’un des déclencheurs suivants se produit :

* Web SDK ou Adobe AppMeasurement envoient un événement.
* La visibilité passe à masquée, par exemple :
   * Charger une page
   * Basculer d’onglet à un autre
   * Réduire le navigateur
   * Fermer le navigateur
   * Verrouiller l’écran
* L’URL est modifiée en conséquence.
* Les vues de ressources enregistrées et prêtes à être envoyées dépassent 32.

>[!NOTE]
>
>Les événements Content Analytics supplémentaires influencent probablement toute définition de taux de rebond basée sur le nombre d’événements dans une session ou sur une page.
>

## Identités

Cette section explique comment Content Analytics gère les identités.

### Web

Content Analytics gère les identités du canal web de la manière suivante :

* L’ECID est automatiquement renseigné dans la partie `identityMap` du schéma Content Analytics.
* Si vous avez besoin d’autres valeurs d’identité dans le `identityMap`, vous devez définir ces valeurs dans le rappel `onBeforeEventSend` dans l’extension Web SDK.
* Le groupement basé sur les champs n’est pas pris en charge, car le schéma est détenu par le système. Vous ne pouvez donc pas ajouter un autre champ au schéma pour prendre en charge le groupement basé sur les champs.


Pour vous assurer que les données d’identité Content Analytics et les données d’identité des données Web SDK sont correctement regroupées au niveau du champ, modifiez l’option de rappel de la SDK Web [activé avant l’envoi de l’événement](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"}.

1. Accédez à la propriété **[!UICONTROL Balises]** qui contient l’extension du SDK Web Adobe Experience Platform et l’extension Adobe Content Analytics.
1. Sélectionnez ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensions]**.
1. Sélectionnez l’extension **[!UICONTROL SDK Web Adobe Experience Platform]**.
1. Sélectionnez **[!UICONTROL Configurer]**.
1. Dans la section **[!UICONTROL Instances SDK]**, faites défiler l’écran jusqu’à **[!UICONTROL Collecte de données]** - Rappel **[!UICONTROL OnBeforeEventSend]**.

   ![Rappel OnBeforeEventSend](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Sélectionnez **[!UICONTROL &lt;/> Fournir le code du rappel OnBeforeEventSend]**.
1. Ajoutez le code suivant :

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Rappel OnBeforeEventSend](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le code.
1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer l’extension.
1. [Publiez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview) les mises à jour de la propriété Balises.


### Mobile

Consultez les sections [Extension du service d’identité pour Experience Cloud ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/) et [Extension mobile d’identité pour Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) pour plus d’informations sur l’utilisation des identités dans votre application mobile.

Dès que l’identité change dans l’application mobile, le [lot](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings) actuel de données Content Analytics est réinitialisé afin de démarrer une nouvelle collecte de données Content Analytics pour la nouvelle identité.

## Schémas

Experience Platform collecte des données Content Analytics dans des jeux de données en fonction de schémas Content Analytics spécifiques. Les schémas de référence sont accessibles au public :

* [Schéma des ressources numériques](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Schéma d’expérience digitale](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Schéma de contenu des événements d’expérience](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
