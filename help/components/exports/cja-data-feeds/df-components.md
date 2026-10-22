---
title: Composants disponibles dans les flux de données Customer Journey Analytics
description: Découvrez les dimensions et mesures requises, non prises en charge, restreintes ou devant être remplacées lorsque vous créez des flux de données Customer Journey Analytics.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 5006a5e7f48fb107cc32cf56051062cc88f35c8e
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 40%
---
# Disponibilité des composants dans les flux de données

{{release-limited-testing}}

Tous les composants Customer Journey Analytics ne peuvent pas être utilisés dans les flux de données. Certaines dimensions sont incluses dans chaque flux de données, certains composants ne peuvent pas être inclus et certaines mesures doivent être remplacées par un substitut.

Utilisez les informations suivantes pour comprendre les composants que vous pouvez inclure lorsque vous [créez un flux de données](/help/components/exports/cja-data-feeds/create-feed.md).

## Dimensions obligatoires {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="Dimensions obligatoires"
>abstract="Chaque flux de données doit inclure certaines dimensions, identifiées par un libellé **Obligatoire** en regard du nom de la dimension. Ces dimensions fournissent la structure minimale nécessaire à l’analyse au niveau de l’événement."

<!-- markdownlint-enable MD034 -->

Les dimensions suivantes sont incluses par défaut dans chaque flux de données et ne peuvent pas être supprimées :

| Nom de la dimension | Notes | Flux de données | Autres rapports |
|---|---|---|---|
| Date et heure UTC | Date et heure de l’événement, représentées dans le fuseau horaire UTC. Prend en charge la granularité inférieure à la seconde (micro-seconde). | Obligatoire | Non disponible |
| ID de ligne | Identifiant unique pour chaque ligne incluse dans le flux de données. | Obligatoire | Non disponible |
| Identifiant de session | Identifiant unique pour chaque session incluse dans le flux de données. | Obligatoire | Non disponible |
| ID de personne | Identifiant de personne pour la vue de données et la connexion | Obligatoire | Norme facultative |
| ID de compte {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Identifiant de compte lors de l’utilisation du conteneur Compte | Obligatoire | Norme facultative |

## Dimensions non prises en charge {#unsupported-dimensions}

Les dimensions standard de Customer Journey Analytics ne peuvent pas être incluses dans les flux de données. Le tableau suivant répertorie ces dimensions :

| Nom de la dimension | Notes | Flux de données |
|---|---|---|
| 5 minutes | Intervalles de cinq minutes lorsque des événements se sont produits (arrondi à l’unité inférieure) | Non disponible |
| 15 minutes | Intervalles de quinze minutes lorsque des événements se sont produits (arrondi à l’unité inférieure) | Non disponible |
| 30 minutes | Intervalles de trente minutes lorsque des événements se sont produits (arrondi à l’unité inférieure) | Non disponible |
| Jour | Jour où un événement s’est produit | Non disponible |
| Jour de la semaine | Jour de la semaine où un événement s’est produit | Non disponible |
| Jour du mois | Jour du mois où un événement s’est produit | Non disponible |
| Heure | Heure à laquelle l’événement s’est produit (arrondie à l’unité inférieure) | Non disponible |
| Heure de la journée | Heure du jour où un événement s’est produit (arrondie à l’unité inférieure) | Non disponible |
| Minute | Minute à laquelle un événement s’est produit (arrondi à l’unité inférieure) | Non disponible |
| Minute de l’heure | Minute de l’heure à laquelle un événement s’est produit (arrondie à l’unité inférieure) | Non disponible |
| Mois | Mois au cours duquel un événement s’est produit | Non disponible |
| Mois de l’année | Mois de l’année au cours duquel un événement s’est produit | Non disponible |
| Trimestre | Trimestre au cours duquel un événement s’est produit | Non disponible |
| Trimestre de l’année | Trimestre de l’année au cours duquel un événement s’est produit | Non disponible |
| Second | Deuxième occurrence (arrondi à l’unité inférieure) | Non disponible |
| Semaine | Semaine au cours de laquelle un événement s’est produit | Non disponible |
| Semaine de l’année | Semaine de l’année au cours de laquelle un événement s’est produit | Non disponible |
| Année | Année au cours de laquelle un événement s’est produit | Non disponible |

## Mesures non prises en charge {#unsupported-metrics}

Les mesures standard Customer Journey Analytics suivantes ne peuvent pas être incluses dans les flux de données :

| Nom de la mesure | Notes | Flux de données |
|---|---|---|
| Profil des visiteurs Adobe | | Non disponible |
| Union des opportunités Adobe | | Non disponible |
| Profil d’opportunités Adobe | | Non disponible |
| Union des comptes Adobe | | Non disponible |
| Profil des comptes Adobe | | Non disponible |
| Union des groupes d’achat Adobe | | Non disponible |
| Profil de groupes d’achats Adobe | | Non disponible |
| Union des comptes globaux Adobe | | Non disponible |
| Profil de comptes globaux Adobe | | Non disponible |
| Union des personnes Adobe | | Non disponible |
| Profil de personnes Adobe | | Non disponible |

## Dimensions qui ne peuvent pas être utilisées ensemble {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="Les données de l’agent utilisateur et les données de recherche de périphérique ne peuvent pas exister dans la même configuration de flux de données."

<!-- markdownlint-enable MD034 -->

Certaines dimensions ne peuvent pas être utilisées conjointement dans les jeux de données Experience Platform. Un flux de données peut inclure des dimensions de l’un des groupes suivants, mais pas des deux :

* Les dimensions **Agent utilisateur** et **ID mobile**. <!--UI shows "Type identifier" for device.typeID; align with docs name "Mobile ID" (open question for Danny Carmen).-->

* Dimensions de recherche d’appareil, telles que les dimensions du navigateur, de l’appareil mobile et du système d’exploitation. Pour obtenir la liste complète, voir [Dimensions de recherche d’appareil](#device-lookup-dimensions).

>[!NOTE]
>
>Si vous utilisez le SDK Web, cette restriction est appliquée dans les flux de données avant que les données n’arrivent dans un jeu de données Experience Platform. Pour plus d’informations, voir [Configurer la recherche d’appareil](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure#geolocation-device-lookup) dans [Créer et configurer des flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure) dans le guide Collecte de données .

### Résoudre les conflits de dimension

Lorsque vous ajoutez des dimensions qui ne peuvent pas être utilisées ensemble, une boîte de dialogue s’affiche. Elle répertorie les dimensions qui seront ajoutées, celles qui ne seront pas ajoutées ou celles qui seront supprimées. Ce qui se passe dépend de l’endroit du conflit :

* **Les dimensions que vous ajoutez sont en conflit avec les dimensions déjà présentes dans le flux de données** : les dimensions que vous ajoutez sont prioritaires. La boîte de dialogue vous invite à ajouter votre sélection et à supprimer les dimensions en conflit du flux de données.

* **Les dimensions que vous ajoutez sont en conflit les unes avec les autres** : les dimensions **Agent utilisateur** et **ID mobile** sont prioritaires. La boîte de dialogue vous invite à les ajouter ; les dimensions de recherche d’appareil de votre sélection ne sont pas ajoutées.

Pour conserver le flux de données inchangé, sélectionnez **[!UICONTROL Annuler]**.

<!--Open questions for Danny Carmen: behavior when a batch contains both groups and the feed already has conflicting dimensions; whether "add all" adds the full selection or only the listed dimensions.-->

### Dimensions de recherche d’appareil {#device-lookup-dimensions}

Les dimensions suivantes ne peuvent pas être incluses dans le même flux de données que les dimensions **Agent utilisateur** ou **ID mobile**.

>[!NOTE]
>
>La liste suivante utilise les noms de dimension par défaut. Les dimensions renommées dans votre vue de données apparaissent dans les flux de données avec leurs noms personnalisés.

<!--Engineering lists 30 device lookup fields; this list has 28. Likely missing: environment.operatingSystemIDStr and environment.browserIDStr. Confirm display names with Danny Carmen.-->

* Type de navigateur
* Navigateur
* Identifiant de navigateur
* Fabricant du dispositif portable
* Type d’appareil mobile
* Prise en charge de l&#39;audio sur le dispositif portable
* DRM mobile
* Java VM de mobile
* Services d&#39;informations mobiles
* Prise en charge des images sur le dispositif portable
* Profondeur de couleur du dispositif portable
* Protocoles Net mobile
* Numéro d’appareil mobile
* Mobile - Longueur max. d’adresse e-mail
* Mobile - Décoration de courrier
* Mobile - Presser pour parler
* Largeur d’écran du périphérique mobile
* Longueur maximale d’URL de navigateur mobile
* Système d’exploitation mobile (obsolète)
* Hauteur d’écran du périphérique mobile
* Prise en charge de la vidéo sur le dispositif portable
* Prise en charge des cookies sur le dispositif portable
* Mobile - Longueur max. du signet
* Taille d’écran du périphérique mobile
* Nom de l’appareil mobile
* Types de systèmes d’exploitation
* Systèmes d’exploitation
* Identifiant du système d’exploitation

## Mesures nécessitant un substitut {#substitute-metrics}

Les mesures Customer Journey Analytics suivantes doivent être remplacées :

| Nom de la mesure | Notes | Flux de données |
|---|---|---|
| Comptes [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | En fonction de l’identifiant de compte spécifié dans la connexion | Non disponible. Utilisez un nombre distinct de l’ID de compte. |
| Groupe d&#39;achat {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Groupes d&#39;achat basés sur l&#39;ID de groupe d&#39;achat dans la connexion | Non disponible. Utiliser le nombre distinct de l&#39;ID du groupe d&#39;achat. |
| Événements | Nombre de lignes de tous les jeux de données d’événements dans une connexion | Non disponible. Utilisez un nombre distinct de l’ID de ligne. |
| Comptes globaux [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | En fonction de l’identifiant de comptes globaux dans la connexion | Non disponible. Utilisez un nombre distinct de l’identifiant de comptes globaux. |
| Opportunités [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Opportunités basées sur l’ID d’opportunité dans la connexion | Non disponible. Utiliser le nombre distinct de l’ID d’opportunité. |
| Personnes | En fonction de l’ID de personne spécifié dans une connexion | Non disponible. Utilisez un nombre distinct de l’ID de personne. |
| Conversations | Nombre de conversations | Non disponible. Utilisez un nombre distinct de l’ID de conversation. |
| Fins de session | Nombre d’événements qui étaient le dernier événement d’une session | Non disponible |
| Débuts de session | Nombre d’événements qui ont été le premier événement d’une session | Non disponible |
| Sessions | En fonction des paramètres de session de la vue de données | Non disponible. Utilisez un nombre distinct de l’ID de session. |
| Durée (secondes) | Additionne le temps entre deux valeurs de dimension différentes | Non disponible |

## Composants standard facultatifs {#optional-standard-components}

| Nom du composant | Type | Notes | Flux de données |
|---|---|---|---|
| Matin/après-midi | Dimension de répartition temporelle | Matin ou après-midi | Non disponible |
| ID de lot | Dimension | Identifiant d’un lot Experience Platform | Disponible |
| Identifiant du jeu de données | Dimension | Identifiant d’un jeu de données Experience Platform | Disponible |
| Jour du mois | Dimension de répartition temporelle | 1-31 | Non disponible |
| Jour de la semaine | Dimension de répartition temporelle | Du lundi au dimanche | Non disponible |
| Jour de l’année | Dimension de répartition temporelle | 1-366 | Non disponible |
| Profondeur de l’événement | Dimension | Valeur numérique séquentielle (1, 2, 3, etc.) affecté à chaque interaction d’événement dans une session<p>Se réinitialise au début de chaque nouvelle session</p> | Disponible |
| Heure de la journée | Dimension de répartition temporelle | 0-23 | Non disponible |
| Mois de l’année | Dimension de répartition temporelle | Janvier-Décembre | Non disponible |
| Premières sessions | Mesure | Première session définie par une personne dans la fenêtre de création de rapports | Non disponible |
| Sessions récurrentes | Mesure | Sessions qui n’étaient pas la première session d’une personne | Non disponible |
| Espace de noms de l’ID de personne | Dimension | Type d’ID dont est constitué l’ID de personne (par exemple, e-mail ou ID de cookie) | Disponible |
| Identifiant de compte global {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | Identifiant de compte global lors de l’utilisation du conteneur de compte global | Disponible |
| ID de l’opportunité {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | ID de l’opportunité lors de l’utilisation du conteneur d’opportunités | Disponible |
| ID de groupe d&#39;achat {type=Informative url="https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimension | ID groupe d&#39;achat lors de l&#39;utilisation du conteneur groupe d&#39;achat | Disponible |
| Trimestre de l’année | Dimension de répartition temporelle | T1, T2, T3, T4 | Non disponible |
| Session répétée | Mesure | Sessions qui n’ont pas été la toute première session d’une personne | Non disponible |
| Type de session | Dimension | Deux valeurs : Première fois ou Récurrent | Non disponible |
| Temps passé par événement | Dimension | Regroupe la mesure Durée de la visite dans des regroupements événement . | Non disponible |
| Temps passé par session | Dimension | Regroupe la mesure Durée de la visite dans des regroupements de session | Non disponible |
| Durée par personne | Dimension | Regroupe la mesure Temps passé dans des regroupements Personne . | Non disponible |
| Week-end/Jour de semaine | Dimension de répartition temporelle | Week-end ou jour de la semaine | Non disponible |
