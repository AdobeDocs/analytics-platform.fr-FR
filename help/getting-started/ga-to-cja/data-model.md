---
title: Mappage du modèle de données GA4 avec Customer Journey Analytics
description: Découvrez comment le modèle de données basé sur les événements de GA4 se traduit en schémas et jeux de données XDM dans Customer Journey Analytics.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# Mappage du modèle de données GA4 avec Customer Journey Analytics

GA4 et Customer Journey Analytics sont toutes deux des plateformes basées sur des événements, ce qui rend la traduction du modèle de données entre elles plus directe qu’elle ne l’était à partir d’Universal Analytics. Comprendre comment les événements et paramètres de GA4 correspondent aux champs et aux jeux de données XDM de Customer Journey Analytics facilite l’interprétation des rapports et la collaboration avec votre équipe d’implémentation.

## Modèle de données basé sur les événements de GA4

Chaque interaction dans GA4 est un **événement** : une action nommée avec un ensemble facultatif de **paramètres** qui fournissent un contexte. Il n’existe pas de types d’objet distincts pour les pages vues, les sessions ou les objectifs ; il s’agit uniquement d’événements.

| Type d’événement GA4 | Exemples |
|---|---|
| Collecté automatiquement | `page_view`, `session_start`, `first_visit`, `scroll` |
| Mesure améliorée | `file_download`, `video_start`, `form_submit` |
| Recommandé | `purchase`, `add_to_cart`, `sign_up` |
| Personnalisé | Tout nom d’événement défini |

Chaque événement peut comporter jusqu’à 25 paramètres. Par exemple, un événement `purchase` inclut généralement `transaction_id`, `value`, `currency` et `items` en tant que paramètres.

## Stockage des données par Customer Journey Analytics

Customer Journey Analytics obtient ses données de **Adobe Experience Platform**. Les données dans Platform sont stockées dans des **jeux de données**, chacun conforme à un **schéma** créé à l’aide du **modèle de données d’expérience (XDM)**. XDM est le standard ouvert d’Adobe pour la représentation des données d’expérience client.

Trois types de jeux de données sont utilisés dans Customer Journey Analytics :

| Type de jeu de données CJA | Équivalent GA4 | Ce qu’il contient |
|---|---|---|
| [!UICONTROL Jeu de données d’événement] | Flux d’événements GA4 | Interactions de série temporelle (pages vues, clics, achats) |
| [!UICONTROL Jeu de données du profil] | Propriétés de l’utilisateur GA4 | Attributs au niveau de la personne (champs CRM, statut de fidélité, données démographiques) |
| [!UICONTROL Jeu de données de recherche] | Dimensions personnalisées GA4 utilisées comme tables de référence | Données de référence clé-valeur (catalogue de produits, noms de campagne) |

Customer Journey Analytics ne comporte pas d’eVars, de props ou d’événements de succès. Toutes les dimensions et mesures sont directement issues des champs de schéma XDM. Le nombre de valeurs de dimension uniques n’est pas limité.

## Événements collectés automatiquement

GA4 collecte automatiquement un ensemble d’événements via son SDK. Le tableau suivant mappe ces événements à leurs équivalents XDM ou Customer Journey Analytics.

| Événement collecté automatiquement GA4 | Équivalent XDM/Customer Journey Analytics |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` (champ XDM standard) |
| `session_start` | Début de session (automatique, par définition de session de vue de données) |
| `first_visit` | [!UICONTROL Première session] segment |
| `scroll` | Événement personnalisé (nécessite un mappage d’implémentation explicite) |
| `click` | Champs `xdm.web.webInteraction` (implémentation requise) |
| `video_start` / `video_complete` | Champs de schéma Media Collection (avec les services de médias en flux continu Adobe) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order` (schéma XDM commerce standard) |
| `add_to_cart` | `xdm.commerce.productListAdds` (schéma XDM commerce standard) |

>[!NOTE]
>
>Plusieurs événements de mesure améliorée de GA4 (comme défilement, téléchargement de fichier ou vidéo) nécessitent un mappage explicite aux champs XDM lors de l’implémentation de à l’aide de Web SDK. Ils ne collectent pas automatiquement les données de la même manière que le SDK de GA4 les traite.

## Événements et paramètres personnalisés

Dans GA4, les événements personnalisés ont un nom et jusqu’à 25 paramètres. Dans Customer Journey Analytics, les événements personnalisés correspondent aux champs de schéma XDM personnalisés définis lors de l’implémentation :

* Le **nom de l’événement** devient une valeur de champ dans un champ XDM (généralement [`xdm.eventType`](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/classes/experienceevent)).
* Chaque **paramètre** devient un champ de schéma XDM distinct. Tout champ XDM peut être exposé en tant que dimension ou mesure lors de la [configuration d’une vue de données](/help/data-views/component-settings/overview.md).

>[!NOTE]
>
>Les chemins d’accès spécifiques aux champs XDM pour les événements personnalisés de votre organisation sont déterminés lors de l’implémentation de Web SDK. Collaborez avec votre équipe d’implémentation pour comprendre votre mappage de champs spécifique avant de créer des rapports. Voir [Concevoir votre schéma](../cja-upgrade/cja-upgrade-schema-architect.md) pour plus d’informations.

## Propriétés de l’utilisateur

Les propriétés utilisateur GA4 sont des attributs persistants définis sur un utilisateur (par exemple, `membership_tier` ou `account_type`). Dans Customer Journey Analytics, ils correspondent aux **jeux de données de profil** dans Platform.

Un jeu de données Profil est ingéré séparément des données d’événement et joint à celui-ci dans Customer Journey Analytics à l’aide d’un ID de personne partagé. Les ID de personne courants utilisés dans ce contexte comprennent un ID de client ou un hachage d’e-mail. Une fois joints, ces attributs de profil sont disponibles en tant que dimensions dans Analysis Workspace avec vos données au niveau de l’événement.

Cette approche offre à Customer Journey Analytics plus de flexibilité que le modèle de propriétés utilisateur de GA4 : GA4 vous limite aux propriétés utilisateur définies dans son SDK, tandis que les jeux de données de profil Customer Journey Analytics peuvent inclure n’importe quel attribut de n’importe quel système (CRM, plateforme de fidélité, enregistrements d’assistance), à condition qu’il partage un identifiant joignable.

Si votre organisation doit toujours importer des données GA dans Adobe Experience Platform, consultez [Ingestion de données historiques Google Analytics](/help/use-cases/third-party/ga/backfill.md) et [Configuration des données Google Analytics en flux continu](/help/use-cases/third-party/ga/streaming.md) pour les guides de configuration destinés aux administrateurs.
