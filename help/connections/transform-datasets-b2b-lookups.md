---
title: Transformer Des Jeux De Données Pour Les Recherches B2B
description: Décrit comment transformer des données dans des jeux de données de schémas de recherche B2B spécifiques
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
autotag-review: '2026-05-19T08:48:44.273Z'
TQID: 'https://experienceleague.adobe.com/hE-nAiD8K4lHdZkC2YJpqpqfh2d3CY6tq4KiTJjEXs0'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: cf731116-8803-4027-85aa-9c0a126e8321
  - id: e0cfe18a-f68c-495b-bafc-f6bcc0392d6c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 10%

---

# Transformer les jeux de données pour les recherches B2B

Pour prendre en charge les recherches basées sur la personne sur les données B2B (y compris les comptes, les opportunités, les listes marketing et les campagnes), la transformation des jeux de données de recherche B2B peut améliorer la précision des données.

Cette transformation n’est disponible que pour les jeux de données contenant des données pour les schémas de recherche B2B, en fonction des classes suivantes :

* [Relation Personne/Compte d’entreprise XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [Relation Personne/XDM Business Opportunity](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [Membres de la liste XDM Business Marketing](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [Membres de XDM Business Campaign](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>Il existe une limite de 10 000 éléments maximum pour chaque ID. Cette limitation implique que pour un ID de personne donné, vous ne pouvez avoir que 10 000 comptes, 10 000 opportunités, 10 000 listes marketing ou 10 000 campagnes.

>[!PREREQUISITES]
>
>Pour que l’ingestion fonctionne correctement, vous devez vérifier que les données des jeux de données de recherche B2B sont renseignées pour les champs suivants (tels que définis dans les schémas de recherche B2B) :
>
>| Jeu de données contenant des données conformes au schéma | Champ renseigné avec des données |
>|---|---|
>| Relation Personne/Compte d’entreprise XDM | `accountPersonID` |
>| Personne de l’opportunité commerciale XDM | `opportunityPersonID` |
>| Liste XDM Business Marketing | `marketingListMemberID` |
>| Membres de XDM Business Campaign | `campaign.sourceKey` |
>

Pour activer la transformation pour un jeu de données de recherche B2B :

![Activer le jeu de données de transformation](/help/connections/assets/transform.gif)

* Vérifiez pour chaque jeu de données les valeurs suggérées pour **[!UICONTROL Clé]** et **[!UICONTROL Clé correspondante]**. Si vous modifiez les valeurs suggérées, un avertissement s’affiche vous demandant de continuer. Vous devez vous assurer que :

   * La valeur que vous sélectionnez pour **Clé** est basée sur le type de données ID de personne.
   * La valeur que vous sélectionnez pour **Clé correspondante** est définie comme champ d’identité principale pour le jeu de données d’événement.

* Sélectionnez les options pour importer de nouvelles données et un renvoi du jeu de données.

* Sélectionnez **[!UICONTROL Transformer le jeu de données pour les recherches B2B]**.

  Cette option transforme le jeu de données afin qu’il puisse être utilisé pour les recherches basées sur les personnes dans les scénarios B2B.


  >[!IMPORTANT]
  >
  >Une fois activée et lorsque la connexion est enregistrée, la transformation est irréversible. Vous ne pouvez pas modifier la clé, la clé correspondante et la configuration du jeu de données de transformation. Vous pouvez uniquement supprimer, ajouter et reconfigurer le jeu de données.

Pour activer la transformation pour un ou plusieurs jeux de données qui font déjà partie d’une connexion existante :

1. Supprimez les jeux de données de la connexion.
1. Enregistrez la connexion.
1. Ajoutez les jeux de données à la connexion lors de l’activation de la transformation des jeux de données.

## Informations générales

Les jeux de données non transformés, pour les schémas basés sur les quatre classes de schéma mentionnées ci-dessus, peuvent contenir plusieurs lignes pour un identifiant de personne unique. Les recherches basées sur une personne ne correspondent qu’à l’occurrence la plus récente de cet identifiant de personne, ce qui empêche une recherche correcte basée sur un ID de personne de comptes, d’opportunités, de listes marketing ou de campagnes.

La transformation modifie le jeu de données de chacune des quatre classes de schéma (orange dans l’illustration ci-dessous) de sorte que pour chaque identifiant de personne, un tableau (d’objet) soit créé pour les données pertinentes (comptes, opportunités, listes marketing ou campagnes) dans les jeux de données de recherche (rose dans l’illustration ci-dessous). Cette transformation permet un fonctionnement correct des recherches basées sur l’ID de personne.

![Schémas B2B](./assets/b2b-schemas.png)
