---
title: Transformer des jeux de données pour les recherches B2B
description: Décrit comment transformer des données dans des jeux de données de schémas de recherche B2B spécifiques.
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: eef9b420f1016254dece0a916b82bc99e2ca866e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# Transformer des jeux de données pour les recherches B2B

Pour prendre en charge les recherches basées sur les personnes sur les données B2B (y compris les comptes, les opportunités, les listes marketing et les campagnes), la transformation des jeux de données de recherche B2B est nécessaire.

Cette transformation n’est disponible que pour les jeux de données avec des données pour les schémas de recherche B2B, en fonction des classes suivantes :

* [Relation avec la personne du compte XDM ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [Relation de personne d’opportunité commerciale XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [ Membres de la liste XDM Business Marketing ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [ Membres XDM Business Campaign ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>Pour chaque identifiant, la limite est de 10 000 éléments au maximum. Cette limitation implique que pour un ID de personne donné, vous ne pouvez avoir que 10 000 comptes, ou 10 000 opportunités, ou 10 000 listes marketing, ou 10 000 campagnes.


Pour activer la transformation d’un tel jeu de données :

![Activer le jeu de données de transformation](assets/transform-dataset.gif)

* Assurez-vous de sélectionner l’identifiant correct pour **[!UICONTROL Clé]** et **[!UICONTROL Clé correspondante]**, par exemple `personKey.sourceKey`.

* Sélectionnez les options d’importation de nouvelles données et de renvoi de jeux de données.

* Sélectionnez **[!UICONTROL Transformer le jeu de données pour les recherches B2B]**.

  Cette option transforme le jeu de données afin qu’il puisse être utilisé pour les recherches basées sur des personnes dans les scénarios B2B.


  >[!IMPORTANT]
  >
  >Une fois activée et une fois la connexion enregistrée, la transformation est irréversible. Vous ne pouvez pas modifier le paramètre de transformation d’un jeu de données une fois qu’une connexion est enregistrée, sauf en supprimant et en ajoutant à nouveau le jeu de données à la connexion.

Pour activer la transformation d’un ou de plusieurs jeux de données qui font déjà partie d’une connexion existante :

1. Supprimez les jeux de données de la connexion.
1. Enregistrez la connexion.
1. Ajoutez les jeux de données à la connexion lors de l’activation de la transformation pour les jeux de données.

## Informations générales

Les jeux de données non transformés, pour les schémas basés sur les quatre classes de schémas mentionnées ci-dessus, peuvent contenir plusieurs lignes pour un identifiant de personne unique. Les recherches basées sur une personne ne correspondent qu’à l’occurrence la plus récente de cet identifiant de personne, ce qui empêche une recherche de comptes, d’opportunités, de listes marketing ou de campagnes basée sur un identifiant de personne approprié.

La transformation modifie le jeu de données de chacune des quatre classes de schémas (en orange dans l’illustration ci-dessous) de sorte que pour chaque identifiant de personne, un tableau (objet) est créé pour les données pertinentes (comptes, opportunités, listes marketing ou campagnes) dans les jeux de données de recherche (en rose dans l’illustration ci-dessous). Cette transformation permet un bon fonctionnement des recherches basées sur les ID de personne.

![Schémas B2B](./assets/b2b-schemas.svg)
