---
description: Découvrez comment utiliser les flux de données pour extraire des données brutes de Customer Journey Analytics. Découvrez les conditions préalables requises afin d’utiliser les flux de données pour les étapes suivantes.
keywords: flux de clics;flux de données;flux des données;Flux de données
title: Flux de données Analytics - Vue d’ensemble
feature: Components
hide: true
hidefromtoc: true
source-git-commit: b0b86424399ea79deca8f1d522d52354dfaaa8c7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# Présentation des flux de données

Les flux de données sont un moyen puissant d’extraire des données brutes de Customer Journey Analytics. Il est possible d’utiliser ces données brutes sur d’autres plateformes en dehors d’Adobe à la discrétion de votre entreprise. Les données sont diffusées sous la forme de lots horaires à la fin de chaque heure ou sous la forme de lots quotidiens à la fin de chaque jour.

## Conditions préalables

Assurez-vous de respecter l’ensemble des exigences suivantes avant d’utiliser les flux de données.

* Une implémentation fonctionnelle avec des données ingérées dans Adobe Customer Journey Analytics. <!-- For more information, see Data ingestion overview - add link -->
* Votre compte est un administrateur de produit Analytics ou votre compte appartient à un profil de produit ayant accès aux flux de données. <!--???-->
* Un compartiment configuré sur Amazon S3, Google Cloud Platform, Azure RBAC ou Azure SAS.<!--Which cloud providers do we support??-->
* (Hérité : obligatoire uniquement pour les types de destination FTP et SFTP hérités) disposer d’un site FTP et d’informations d’identification à portée de main (informations d’identification FTP fournies par votre organisation)<!--Delete???-->

## Comparaison des flux de données dans Customer Journey Analytics et Adobe Analytics

La fonctionnalité de flux de données dans Customer Journey Analytics est différente d’Adobe Analytics. Pour plus d’informations, voir [Comparer des flux de données dans Customer Journey Analytics et Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).


## Étapes suivantes

Les ressources suivantes vous aident à comprendre le workflow de base de l’obtention des flux de données. Une fois que vous avez compris le workflow de base, vous pouvez travailler avec des équipes au sein de votre organisation pour stocker ou ingérer des données brutes dans une base de données.

* Bonnes pratiques relatives aux flux de données <!--add link--> : bonnes pratiques pour la création et la gestion des flux de données.
* Créer un flux de données <!--add link--> : détails techniques pour la création d’un flux de données, expliquant plus en détail les champs individuels
* Gérer les flux de données <!--add link--> : en savoir plus sur la navigation dans l’interface des flux de données
* Contenu du flux de données <!--add link--> : comprendre ce qui se trouve dans le <!-- Is this still the output users can download from the destination? I aske Jun. --> de fichiers compressé.
* Définitions des colonnes de données <!--add link--> : liste complète de toutes les colonnes disponibles.

>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigation dans l’interface du flux de données](https://video.tv.adobe.com/v/3428562?captions=fre_fr&quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rechercher votre identifiant de flux de données](https://video.tv.adobe.com/v/3418480?captions=fre_fr&quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]
