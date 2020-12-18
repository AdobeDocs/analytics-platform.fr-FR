---
title: Ajouter des recherches globales à vos jeux de données
description: Utilisez des recherches globales pour augmenter le rapports avec des dimensions utiles en Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: b3c9757421537d2d84a78a4d37e9bfc362438d40
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# Ajouter des recherches globales à vos jeux de données

Les recherches globales permettent aux Customer Journey Analytics de générer des rapports sur certaines dimensions/attributs qui ne sont pas utiles par eux-mêmes mais qui sont utiles lorsqu’ils sont associés à d’autres données. Par exemple, les attributs des périphériques mobiles et les attributs des dimensions du système d’exploitation et du navigateur, tels que les numéros de version du navigateur. Une &quot;recherche globale&quot; est très similaire à un ensemble de données de recherche (appelé classifications en Adobe Analytics traditionnel). Cependant, les recherches globales sont applicables dans toutes les organisations Experience Cloud. Les recherches globales sont automatiquement appliquées à tous les jeux de données de événement qui contiennent certains champs de schéma XDM (voir ci-dessous pour les champs spécifiques).
Pour chaque emplacement de schéma classifié par l&#39;Adobe, un jeu de données de recherche global existe. Vous pouvez utiliser des jeux de données de recherche globaux avec Analytics Source Connector ou avec d’autres jeux de données personnalisés qui peuvent les accepter.

En Adobe Analytics traditionnel, ces dimensions s’affichent par elles-mêmes, alors qu’en CJA, vous devez les inclure activement lorsque vous créez des vues de données. Lorsqu’un utilisateur, dans le processus des connexions, sélectionne un jeu de données marqué comme un jeu avec une clé pour les recherches globales, l’interface utilisateur des vues de données sait qu’elle doit inclure toutes les dimensions de recherche globale disponibles pour le rapports. Le processus des vues de données sait inclure ces dimensions de recherche globales disponibles pour la vue de données. Les fichiers de recherche sont automatiquement mis à jour et disponibles, dans toutes les régions et pour tous les comptes. Ils sont stockés dans des organisations spécifiques à une région associées au client.

## Utilisation des recherches globales avec des jeux de données du connecteur de données d’Adobe

Les jeux de données de recherche globaux sont automatiquement appliqués au moment du rapport. Si vous utilisez le [Connecteur de données Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors) et que vous incorporez une dimension pour laquelle l’Adobe fournit une recherche globale, nous appliquons automatiquement cette recherche globale. Si un jeu de données de événement contient des champs [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en), nous pouvons lui appliquer des recherches globales.

## Utiliser des recherches globales avec des jeux de données personnalisés

Il doit y avoir dans le jeu de données de événement une clé compatible avec les jeux de données de recherche globaux. Tant que vous renseignez les champs XDM appropriés en ajoutant certains de nos mixins de schéma Adobe Experience Platform [standard ](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=en#mixins), vous pouvez faire en sorte que les jeux de données personnalisés fonctionnent avec les recherches globales.

## Champs de recherche globaux disponibles

* `browser`
   * `browser`,  `group_id`,  `id`
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

## Rapport sur les dimensions de recherche globales

Pour générer des rapports sur les dimensions de recherche globale, vous devez les ajouter lorsque vous créez une vue de données dans le Customer Journey Analytics :

![](assets/global-lookup.png)

Vous pouvez ensuite afficher les données de recherche dans Workspace :

![](assets/gl-reporting.png)

