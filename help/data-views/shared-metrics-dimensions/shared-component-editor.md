---
title: Éditeur de composant partagé
description: Créer ou modifier des dimensions et des mesures partagées.
exl-id: 3f6a808a-d6ac-4a47-a5e2-63b9f17952e8
TQID: https://experienceleague.adobe.com/vHmMlOpgjLAVzEg9t-MORtrHKsbqBABVcDFkuMlo5FM
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 0%

---

# Éditeur de composant partagé

L’éditeur de composant partagé vous permet de créer ou de modifier des dimensions et des mesures partagées. Il partage de nombreux éléments d’interface utilisateur lors de la [création ou modification d’une vue de données](/help/data-views/create-dataview.md), mais ces interfaces ont des objectifs distincts :

* L’éditeur de composant de vue de données vous permet de créer et de modifier des composants spécifiques à cette vue de données. Vous ne pouvez pas modifier les dimensions ou mesures partagées dans l’éditeur de composant de vue de données. Dans cette interface, les dimensions et mesures partagées peuvent être identifiées par une icône ![icône de composant partagé](/help/assets/icons/CCLibrary.svg) en regard du nom du composant.
* L’éditeur de composant partagé vous permet de créer et de modifier des dimensions et des mesures partagées. Vous ne pouvez pas modifier les composants qui appartiennent à une seule vue de données dans l’éditeur de composants partagés.

![Capture d’écran de l’éditeur de composants](assets/component-editor.png)

Le coin supérieur droit comprend trois boutons :

* **[!UICONTROL Fermer]** ou **[!UICONTROL Annuler]** : si toutes les modifications sont enregistrées, le bouton **[!UICONTROL Fermer]** ferme l’éditeur. Si des modifications ne sont pas enregistrées, le bouton **[!UICONTROL Annuler]** ferme l’éditeur sans enregistrer ces modifications.
* **[!UICONTROL Enregistrer]** : enregistre tous les composants et conserve l’éditeur ouvert.
* **[!UICONTROL Enregistrer et terminer]** : enregistre tous les composants et ferme l’éditeur.

L’interface comprend trois colonnes/sections principales :

* **Sélecteur de champ de schéma** : recherchez le ou les champs de schéma souhaités et faites-les glisser vers la zone des composants inclus.
   * **Connexion** : connexion active. Modifiez la connexion active dans le [gestionnaire des mesures et dimensions partagées](smd-overview.md).
   * **Liste des composants** : vous pouvez choisir entre sélectionner [!UICONTROL Champs de schéma] (nouvelles dimensions et mesures partagées) ou [!UICONTROL Mesures et dimensions] (composants partagés existants) dans le menu déroulant.
   * **Rechercher** : utilisez l’icône ![Rechercher](/help/assets/icons/Search.svg) pour rechercher du texte dans le champ de schéma souhaité ou le composant partagé par nom. Vous pouvez également utiliser des filtres ![icône de filtre](/help/assets/icons/Filter.svg) pour réduire la liste des composants. Le filtre `Is not deprecated` est actif par défaut.
   * **Créer un champ dérivé** : permet de [créer un champ dérivé](/help/data-views/derived-fields/derived-fields.md).
* **Composants inclus** : composants que vous configurez pour être partagés. Lors de la création de composants partagés, vous pouvez faire glisser plusieurs champs de schéma vers cette zone pour créer plusieurs composants simultanément. Lors de la modification des composants partagés, vous pouvez sélectionner plusieurs composants à modifier, ce qui répertorie tous les composants sélectionnés dans cette zone.
* **Paramètres des composants** : lors de la sélection d’un composant dans la zone des composants inclus, tous les paramètres disponibles peuvent être configurés dans cette colonne. Voir [Paramètres des composants](/help/data-views/component-settings/overview.md) pour connaître toutes les options disponibles pour les dimensions et les mesures. Maj + clic sur plusieurs éléments dans la zone des composants inclus vous permet de modifier simultanément n’importe quel champ commun.
