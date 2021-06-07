---
description: Utilisez les modèles dans Workspace et créez des modèles personnalisés.
title: Modèles
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
exl-id: 464032a1-6dae-4df5-b4db-b277788e88c2
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 92%

---

# Modèles

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer un projet d’après :

* **Projet vierge (par défaut)** : Pour obtenir des instructions, voir [Création d’un projet Analysis Workspace](/help/analysis-workspace/home.md).
* **Modèle standard** : Ces modèles sont créés par Adobe et livrés avec le produit.
* **Modèle personnalisé** : Ces modèles peuvent être créés, partagés ou supprimés par les utilisateurs disposant ou non de droits d’administration, à condition qu’ils aient reçu l’autorisation [!UICONTROL Analysis Workspace : enregistrer comme modèle] dans l’Admin Console. [En savoir plus...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Création d’un modèle personnalisé {#create-custom-template}

Les utilisateurs dotés de droits d’administration peuvent convertir n’importe quel projet qu’ils créent en un modèle personnalisé. Procédez comme suit :

1. Ouvrez le projet.
1. Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Enregistrer comme modèle]**.

   ![](assets/save_project_template.png)

   Le projet enregistré sera nommé avec le nom du projet en cours suivi du mot « (Modèle) ». Les administrateurs peuvent changer ce nom en modifiant le modèle.

   >[!NOTE]
   >
   >Par défaut, toutes les personnes de l’organisation ont accès aux modèles de projet. Vous pouvez organiser les modèles en leur appliquant des balises. (Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Informations et paramètres du projet]** pour modifier les balises et les descriptions.)

### Actions possibles sur les modèles personnalisés

![](assets/custom_templates.png)

| Action | Description |
|--- |--- |
| Modifier  le modèle | Permet à un administrateur de modifier le modèle en changeant sa source de données, en modifiant les composants, les visualisations, les périodes, etc.  Pour modifier un modèle personnalisé, procédez de l’une des manières suivantes :<ul><li>affichez la liste des modèles personnalisés dans Analysis Workspace, sélectionnez-en un, puis cliquez sur Modifier le modèle ; ou</li><li>dans Analytics, sélectionnez Composants > Projets, puis filtrez les projets en fonction des Modèles. Cliquez sur le nom du modèle à modifier.</li></ul>**Remarque :** après avoir modifié un modèle, deux options se présentent, selon le cas : Enregistrer ou Enregistrer sous. Ces deux options diffèrent comme suit :<ul><li>**Enregistrer :** met à jour le modèle personnalisé pour tous les utilisateurs. Si quelqu’un crée un projet d’après ce modèle personnalisé, il verra les modifications que vous avez apportées.</li><li>**Enregistrer sous :** crée une copie du modèle personnalisé avec vos modifications. (En mode de modification, le menu Partager > Partager le projet est désactivé.)</li></ul> |
| Rechercher des modèles | Dans la boîte de dialogue Modèles personnalisés, cliquez sur Rechercher des modèles. |
| Trier des modèles | Vous pouvez trier les modèles par ordre alphabétique, par pertinence et par date de création.  Dans la boîte de dialogue Modèles personnalisés, cliquez sur Tri. |
| Appliquer des balises à un modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Cliquez sur Ajouter des balises. |
| Modifier la description du modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Double-cliquez sur la description pour la modifier. |


## Modèles standard

Lorsque vous ouvrez un Workspace pour la première fois, les modèles sont disponibles dans le rail de gauche. Les modèles Analysis Workspace couvrent les cas d’utilisation courants. Ils sont regroupés en fonction du secteur industriel vertical auquel ils appartiennent et sont renseignés par différentes dimensions, différents filtres, mesures et visualisations, selon la vue de données sélectionnée.

Utilisez ces modèles prérenseignés tels quels ou adaptez-les en fonction de vos besoins (en ajoutant des mesures ou des visualisations, ou en les remplaçant, par exemple) et enregistrez-les sous un nouveau nom.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Voici les modèles disponibles et les questions auxquelles chaque modèle peut contribuer à répondre.

### Formation

Ces modèles standard vous guident dans la terminologie et les étapes courantes de création de votre première analyse dans Workspace. Il sont disponibles sous forme de modèle standard dans le modal Nouveau projet et remplacent l’exemple de projet qui existe aujourd’hui pour les nouveaux utilisateurs qui n’ont pas d’autres projets dans leur liste.

* **Tutoriel de formation - Analyse de recherche interne** : Le tutoriel de recherche interne vous aide à comprendre ce que vos visiteurs recherchent sur le site Web ou dans l’application, sans le trouver. L’analyse de ce type de données peut faire apparaître des opportunités d’optimisation du contenu.

* **Tutoriel de formation - Analyse marketing** : Ce tutoriel vous explique comment assembler une analyse marketing pour vos cadres, y compris les dimensions et mesures personnalisées importantes.

### Média

* **Consommation audio** : quel contenu est le plus consommé et attire le plus d’utilisateurs ?
* **Récence, fréquence, fidélité** : qui sont mes fidèles lecteurs ?


### Vente au détail

* **Performances de la campagne :** quelles campagnes génèrent le plus de recettes ?
* **Produits :** quels produits sont les plus performants ?

### Web

* **Acquisition :** quels sont les principaux facteurs orientant le trafic vers mon site web ?
* **Consommation de contenu :** où se rendent surtout les personnes sur mon site ?
* **Rétention :** quels types d’utilisateurs seront a priori les plus fidèles à mon site ?
* **Technologie :** quelle technologie utilisent les visiteurs de mon site ?

