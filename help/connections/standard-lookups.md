---
title: Ajout de recherches standard à vos jeux de données
description: Utilisez les recherches standard pour augmenter les rapports avec des dimensions utiles dans Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: 6c5fb7b3964cbf2bb5158733a2ede9b54f9415a5
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 31%

---

# Ajout de recherches standard à vos jeux de données

Les recherches standard (également appelées recherches fournies par l’Adobe) améliorent la capacité de Customer Journey Analytics à créer des rapports sur certaines dimensions/attributs qui ne sont pas utiles par elles-mêmes, mais qui le sont lorsqu’elles sont jointes à d’autres données. Il s’agit par exemple des attributs des appareils mobiles et des attributs des dimensions du système d’exploitation et du navigateur, tels que les numéros de version des navigateurs. Une &quot;recherche standard&quot; est similaire à un jeu de données de recherche. Les recherches standard s’appliquent à toutes les organisations Experience Cloud. Elles sont automatiquement appliquées à tous les jeux de données d’événements qui contiennent certains champs de schéma XDM (voir ci-dessous pour les champs spécifiques). Il existe un jeu de données de recherche standard pour chaque emplacement de schéma classifié par l’Adobe.

Dans Adobe Analytics traditionnel, ces dimensions s’affichent par elles-mêmes, alors que dans CJA, vous devez les inclure activement lorsque vous créez des vues de données. Dans le workflow Connexions , vous sélectionnez un jeu de données marqué comme étant celui avec une clé pour la recherche standard. L’interface utilisateur des vues de données sait automatiquement inclure toutes les dimensions de recherche standard disponibles pour la création de rapports. Les fichiers de recherche sont automatiquement tenus à jour et disponibles, dans toutes les régions et pour tous les comptes. Ils sont stockés dans des organisations spécifiques à une région associées au client.

## Utilisation de recherches standard avec des jeux de données du connecteur de données d’Adobe

Les jeux de données de recherche standard sont automatiquement appliqués au moment du rapport. Si vous utilisez Analytics Data Connector et que vous incorporez une dimension pour laquelle Adobe fournit une recherche standard, nous appliquons automatiquement cette recherche standard. Si un jeu de données d’événement contient des champs XDM, nous pouvons lui appliquer des recherches standard.

### Champs de recherche standard disponibles

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
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

## Rapport sur les dimensions de recherche standard

Pour générer des rapports sur les dimensions de recherche standard, vous devez les ajouter lorsque vous créez une vue de données dans Customer Journey Analytics :

![](assets/global-lookup.png)

Vous pouvez ensuite afficher les données de recherche dans Workspace :

![](assets/gl-reporting.png)
