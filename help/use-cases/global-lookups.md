---
title: Ajouter des recherches globales à vos jeux de données
description: Utilisez les recherches globales pour augmenter le nombre de rapports avec des dimensions utiles dans Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
translation-type: tm+mt
source-git-commit: e19e9b7d7a88232e1eeb7ddaa739389e26763c1a
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 95%

---

# Ajouter des recherches globales à vos jeux de données

Les recherches globales améliorent la capacité de Customer Journey Analytics à rendre compte de certaines dimensions ou attributs qui ne sont pas utiles en soi, mais qui le sont lorsqu’ils sont associés à d’autres données. Il s’agit par exemple des attributs des appareils mobiles et des attributs des dimensions du système d’exploitation et du navigateur, tels que les numéros de version des navigateurs. Une « recherche globale » est très similaire à un jeu de données de recherche (connu sous le nom de classifications dans Adobe Analytics traditionnel). Cependant, les recherches globales sont applicables dans toutes les organisations Experience Cloud. Les recherches globales sont automatiquement appliquées à tous les jeux de données d’événements qui contiennent certains champs de schéma XDM (voir ci-dessous pour les champs spécifiques).
Pour chaque emplacement de schéma classifié par Adobe, un jeu de données de recherche globale existe. Vous pouvez utiliser des jeux de données de recherche globale avec Analytics Source Connector ou avec d’autres jeux de données personnalisés qui peuvent les prendre en charge.

Dans Adobe Analytics traditionnel, ces dimensions s’affichent par elles-mêmes, alors que dans CJA, vous devez les inclure activement lorsque vous créez des vues de données. Lorsqu’un utilisateur, dans le processus Connexions, sélectionne un jeu de données qui est marqué comme étant un jeu avec une clé pour les recherches globales, alors l’interface utilisateur des vues de données sait qu’il inclut toutes les dimensions de recherche globale disponibles pour le compte-rendu des performances. Le processus des vues de données sait inclure ces dimensions de recherche globale disponibles pour la vue de données. Les fichiers de recherche sont automatiquement tenus à jour et disponibles, dans toutes les régions et pour tous les comptes. Ils sont stockés dans des organisations spécifiques à une région associées au client.

## Utilisation des recherches globales avec des jeux de données d’Adobe Data Connector

Les jeux de données de recherche globale sont automatiquement appliqués au moment du compte-rendu. Si vous utilisez [Analytics Data Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=fr-FR#connectors) et que vous incorporez une dimension pour laquelle Adobe fournit une recherche globale, nous appliquons automatiquement cette recherche globale. Si un jeu de données d’événement contient des champs [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr-FR), nous pouvons lui appliquer des recherches globales.

## Utiliser des recherches globales avec des jeux de données personnalisés

Une clé doit être présente dans le jeu de données de événement compatible avec les jeux de données de recherche globaux. Tant que vous renseignez les champs XDM appropriés en ajoutant certains de nos [mixins de schéma Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=fr-FR#mixins) standard, vous pouvez faire en sorte que les jeux de données personnalisés fonctionnent avec les recherches globales.

## Champs de recherche globale disponibles

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`,  `group_id`,  `id`
* `os_group`
   * `os_group`,  `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Compte-rendu sur les dimensions de recherche globale

Pour signaler les dimensions de recherche globale, vous devez les ajouter lorsque vous créez une vue de données dans Customer Journey Analytics :

![](assets/global-lookup.png)

Vous pouvez ensuite afficher les données de recherche dans Workspace :

![](assets/gl-reporting.png)
