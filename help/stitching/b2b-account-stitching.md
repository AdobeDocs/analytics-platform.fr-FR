---
title: Assemblage des comptes B2B
description: Découvrez comment l’assemblage de comptes B2B dans Customer Journey Analytics enrichit les jeux de données d’événements avec des informations de compte et permet une analyse de parcours complète de vos données B2B.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: ff99ee131e9bae9fc2815fb54e5b5c14577450f7
workflow-type: tm+mt
source-wordcount: 994
ht-degree: 2%

---

# Assemblage des comptes B2B

L’assemblage de comptes B2B enrichit vos jeux de données d’événements avec des informations de compte et permet une analyse complète sur l’ensemble du parcours client dans Customer Journey Analytics. Lorsque les événements ne disposent pas d’un identifiant de compte, ce que Customer Journey Analytics B2B edition exige pour l’ingestion, l’assemblage de comptes dérive et ajoute automatiquement ces informations à l’aide d’un [&#x200B; jeu de données de mappage personne-compte &#x200B;](#prerequisites) que vous fournissez.

Sans assemblage de comptes, tout événement qui ne contient pas d’identifiant de compte est ignoré lors de l’ingestion. L’assemblage des comptes élimine cet obstacle en recherchant le compte associé à la personne sur chaque événement, en ajoutant l’identifiant de compte à mesure que l’événement est ingéré et de manière rétroactive.

>[!NOTE]
>
>L’assemblage de comptes B2B nécessite que vous ayez droit au [B2B edition Customer Journey Analytics](/help/getting-started/cja-b2b-edition.md) dans votre environnement avant de pouvoir configurer la fonctionnalité.

L’assemblage de comptes effectue les opérations suivantes sur vos jeux de données :

* **Élever l’identité de la personne** : l’ID de personne sur chaque événement est élevé à l’espace de noms d’identité de votre choix à l’aide du graphique d’identité.
* **Ajouter les informations de compte manquantes** : pour les événements contenant un ID de personne, le [mappage personne à compte](#prerequisites) est utilisé pour dériver et ajouter les informations de compte. Toutes les informations de compte sur l’événement lui-même sont utilisées comme méthode de secours.

## Conditions préalables

Avant d’activer l’assemblage de comptes B2B, préparez les jeux de données suivants dans Adobe Experience Platform :

| Jeu de données | Obligatoire | Description |
|---|---|---|
| **jeu de données personne à compte** | Obligatoire | Un jeu de données de recherche (enregistrement, série non temporelle) qui contient au minimum un ID de personne (avec espace de noms) et un ID de compte. Ces identifiants sont utilisés pour dériver le mappage de la relation personne-compte. |

>[!IMPORTANT]
>
>Le champ ID de personne de votre jeu de données **[!UICONTROL personne à compte]** doit être marqué comme une identité dans votre schéma.

## Activer l’assemblage des comptes

Vous activez et configurez l’assemblage des comptes B2B au niveau de la connexion, puis activez l’assemblage des comptes sur des jeux de données d’événement individuels au sein de cette connexion.

### Configurer les paramètres d’assemblage B2B

1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Connexions]** et [créer une connexion](/help/connections/create-connection.md#create-a-connection) ou [modifier une connexion existante](/help/connections/create-connection.md#edit-a-connection).

1. Dans **[!UICONTROL Paramètres de connexion]**, définissez l’ID de Principal **&#x200B;**&#x200B;sur ![Création](/help/assets/icons/Building.svg) **[!UICONTROL Compte]**.

1. Sélectionnez **[!UICONTROL Ouvrir la configuration de groupement B2B]**.

   ![Configuration de l’assemblage des comptes B2B &#x200B;](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >Une configuration de groupement B2B précédemment configurée pour une connexion non enregistrée est indiquée par **[!UICONTROL _Modifications non enregistrées_]**. Vous ne pouvez pas modifier les **[!UICONTROL conteneurs facultatifs]** pour une configuration de groupement B2B précédemment configurée.

1. Dans la boîte de dialogue **[!UICONTROL Configuration du groupement B2B]** :

   ![Configuration de groupement B2B](assets/b2b-stitching-configuration.png)

   1. Configurez la section **[!UICONTROL Personne]** :

      * Sélectionnez un **[!UICONTROL Espace de noms d’identifiant de personne]** par exemple **[!UICONTROL E-mail]** auquel vous souhaitez que tout ID de personne soit élevé. Ce champ est requis.

   1. Configurez la section **[!UICONTROL Compte]** sous **[!UICONTROL Personne à compte]**.

      | Champ | Obligatoire | Description |
      |---|:---:|---|
      | **[!UICONTROL Jeu de données Personne à compte]** | ![Obligatoire](/help/assets/icons/Required.svg) | Sélectionnez la recherche (jeu de données d’enregistrement ou de série non temporelle) qui mappe les personnes aux comptes. |
      | **[!UICONTROL Champ Personne]** | ![Obligatoire](/help/assets/icons/Required.svg) | Sélectionnez le champ du jeu de données contenant l’ID de personne. Ce champ doit être marqué comme une identité et ne peut pas être identique au champ **[!UICONTROL Compte]** ou **[!UICONTROL Heure de début]**. |
      | **[!UICONTROL Champ de compte]** | ![Obligatoire](/help/assets/icons/Required.svg) | Sélectionnez le champ du jeu de données contenant l’identifiant de compte. Ce champ ne peut pas être identique au champ **[!UICONTROL Personne]** ou **[!UICONTROL Heure de début]**. |
      | **Champ Heure de début** | | Sélectionnez un champ d’horodatage qui indique le moment où la relation personne à compte est devenue active. |

      >[!NOTE]
      >
      >Si une erreur se produit lors du chargement des options du champ, les menus déroulants s’affichent vides et un indicateur d’erreur s’affiche sous chaque champ affecté. Vérifiez le schéma du jeu de données et réessayez.

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour fermer la boîte de dialogue **[!UICONTROL Configuration du groupement B2B]** et revenir aux paramètres de connexion.

   1. L’indicateur **[!UICONTROL _Modifications non enregistrées_]** s’affiche en regard du bouton **Ouvrir la configuration de groupement B2B** jusqu’à ce que vous [enregistriez](#save) la connexion.


### Activer l’assemblage B2B sur les jeux de données d’événement

Après avoir configuré l’assemblage B2B au niveau de la connexion, vous devez activer l’assemblage de comptes B2B individuellement pour chaque jeu de données d’événement que vous souhaitez assembler.

1. Dans Paramètres de connexion, sélectionnez **[!UICONTROL Ajouter des jeux de données]** ou ouvrez les paramètres d’un jeu de données d’événement existant.<br/>Voir [Ajouter des jeux de données](/help/connections/create-connection.md#add-datasets) ou [Modifier un jeu de données](/help/connections/create-connection.md#edit-a-dataset) pour plus d’informations.

1. Pour le jeu de données d’événement spécifique pour lequel vous souhaitez configurer l’assemblage des comptes B2B, activez **[!UICONTROL Activer l’assemblage des personnes en compte]**.

>[!BEGINTABS]

>[!TAB Activé]

Lorsque l’option **[!UICONTROL Activer l’assemblage des personnes en comptes]** est **activée**, vous avez configuré l’assemblage des comptes B2B pour le jeu de données.

* La configuration d’un ID de personne est requise. Cet ID de personne est utilisé pour rechercher l’ID de compte en fonction du [jeu de données personne à compte](#prerequisites).
* La configuration d’un identifiant de compte est facultative.

Assemblage de comptes ![B2B sur le jeu de données d’événement sur &#x200B;](assets/b2b-event-dataset-stitching-on.png)

>[!TAB  Désactivé ]

Lorsque l’option **[!UICONTROL Activer l’assemblage des personnes en comptes]** est **désactivée**, vous n’avez *pas* configuré l’assemblage des comptes B2B pour le jeu de données.

* La configuration d’un identifiant de compte est requise.
* La configuration d’un ID de personne est facultative.

Assemblage de comptes ![B2B sur le jeu de données d’événement désactivé](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### Enregistrer

Une fois que vous avez configuré la configuration de groupement B2B et que vous avez terminé d’ajouter ou de modifier des jeux de données, sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer la connexion.

>[!IMPORTANT]
>
>Une fois une connexion enregistrée, la configuration de groupement B2B devient immuable. Pour afficher vos paramètres après l’enregistrement, sélectionnez **Ouvrir la configuration de groupement B2B**. Tous les champs s’affichent en lecture seule. En outre, si le jeu de données utilisé pour le mappage [personne à compte](#prerequisites) est supprimé dans Experience Platform, cette connexion sera supprimée.

## Planning de mise à jour des données

L’assemblage des comptes extrait quotidiennement le mappage d’identité de votre [jeu de données personne à compte](#prerequisites) et utilise ces informations pour mettre à jour les jeux de données activés pour l’assemblage selon le planning suivant :

| Relecture | Fréquence | Fenêtre Données |
|---|---|---|
| Court terme | Hebdomadaire | 7 derniers jours |
| À long terme | Mensuel | 3 derniers mois |

## Confidentialité et hygiène des données

L’assemblage des comptes respecte les demandes standard de confidentialité et d’hygiène pour les identités de personne, en cohérence avec le comportement d’assemblage B2C. Si un ID de personne est ensuite supprimé par le biais d’une demande d’accès à des informations personnelles ou d’hygiène, le groupement associé effectué à l’aide du graphique d’identité est inversé.

Les entités B2B telles que les comptes, les identifiants de compte et les identifiants de compte globaux qui sont ajoutés aux événements par le biais du groupement ne sont pas supprimées dans le cadre des demandes d’accès à des informations personnelles ou d’hygiène. Ces valeurs ne contiennent pas d’informations d’identification personnelle, il n’existe donc aucune obligation légale de les supprimer.

>[!MORELIKETHIS]
>
>* [Présentation du groupement](overview.md)
>* [Configurer une connexion pour B2B](../connections/create-connection.md)
>* [Questions fréquentes sur le groupement](faq.md)

