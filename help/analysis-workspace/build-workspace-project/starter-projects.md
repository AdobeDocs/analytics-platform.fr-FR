---
description: Modèles dans Workspace
title: Modèles
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1420'
ht-degree: 95%

---


# Modèles

>[!NOTE] Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer un projet d’après :

* **Projet vierge (par défaut)** : Pour obtenir des instructions, voir [Création d’un projet Analysis Workspace](/help/analysis-workspace/home.md).
* **Modèle standard** : Ces modèles sont créés par Adobe et livrés avec le produit.
* **Modèle** personnalisé : Ces modèles peuvent être créés, partagés ou supprimés par les utilisateurs disposant de droits d’administration ou par des non-administrateurs, à condition qu’ils aient obtenu l’ [!UICONTROL Analysis Workspace : Autorisation Enregistrer en tant que modèle] dans l’Admin Console. [En savoir plus...](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-console/permissions/product-profile.html)

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
| Modifier le modèle | Permet à un administrateur de modifier le modèle en changeant sa source de données, en modifiant les composants, les visualisations, les périodes, etc.  Pour modifier un modèle personnalisé, procédez de l’une des manières suivantes :<ul><li>affichez la liste des modèles personnalisés dans Analysis Workspace, sélectionnez-en un, puis cliquez sur Modifier le modèle ; ou</li><li>dans Analytics, sélectionnez Composants > Projets, puis filtrez les projets en fonction des Modèles. Cliquez sur le nom du modèle à modifier.</li></ul>**Remarque :** après avoir modifié un modèle, deux options se présentent, selon le cas : Enregistrer ou Enregistrer sous. Ces deux options diffèrent comme suit :<ul><li>**Enregistrer :** met à jour le modèle personnalisé pour tous les utilisateurs. Si quelqu’un crée un projet d’après ce modèle personnalisé, il verra les modifications que vous avez apportées.</li><li>**Enregistrer sous :** crée une copie du modèle personnalisé avec vos modifications. (En mode de modification, le menu Partager > Partager le projet est désactivé.)</li></ul> |
| Rechercher des modèles | Dans la boîte de dialogue Modèles personnalisés, cliquez sur Rechercher des modèles. |
| Trier des modèles | Vous pouvez trier les modèles par ordre alphabétique, par pertinence et par date de création.  Dans la boîte de dialogue Modèles personnalisés, cliquez sur Tri :. |
| Appliquer des balises à un modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Cliquez sur Ajouter des balises. |
| Modifier la description du modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Double-cliquez sur la description pour la modifier. |


## Modèles standard

Lorsque vous ouvrez un Workspace pour la première fois, les modèles sont disponibles dans le rail de gauche. Les modèles Analysis Workspace couvrent les cas d’utilisation courants. Ils sont groupés selon le marché vertical auquel ils appartiennent et comprennent différents segments, dimensions, mesures et visualisations, selon la suite de rapports sélectionnée.

Utilisez ces modèles prérenseignés tels quels ou adaptez-les en fonction de vos besoins (en ajoutant des mesures ou des visualisations, ou en les remplaçant, par exemple) et enregistrez-les sous un nouveau nom.

[Modèles standard dans Analysis Workspace sur YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=6) (2:46)

Voici les modèles disponibles et les questions auxquelles chaque modèle peut contribuer à répondre.

### Formation

Ces modèles standard vous guident dans la terminologie et les étapes courantes de création de votre première analyse dans Workspace. Il sont disponibles sous forme de modèle standard dans le modal Nouveau projet et remplacent l’exemple de projet qui existe aujourd’hui pour les nouveaux utilisateurs qui n’ont pas d’autres projets dans leur liste.

* **Tutoriel de formation - Analyse de recherche interne** : Le tutoriel de recherche interne vous aide à comprendre ce que vos visiteurs recherchent sur le site Web ou dans l’application, sans le trouver. L’analyse de ce type de données peut faire apparaître des opportunités d’optimisation du contenu.

* **Tutoriel de formation - Analyse marketing** : Ce tutoriel vous explique comment assembler une analyse marketing pour vos cadres, y compris les dimensions et mesures personnalisées importantes.

### Publicité

>[!IMPORTANT]
>
>Les modèles Publicité sont accessibles uniquement si votre suite de rapports est activée pour Advertising Cloud.

* **Moteurs de recherche payante** : ce modèle ventile les tendances publicitaires, les plateformes publicitaires, les mots-clés, les comptes, les campagnes, etc.

### Commerce

* **Magento : Marketing et commerce** : ce modèle ventile la conversion de votre commerce électronique en fonction de l’attribution du canal marketing et fournit des informations par mot-clé de recherche, page d’entrée, emplacement géographique, etc. Pour une présentation vidéo, voir >[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Média

* **Consommation audio** : quel contenu est le plus consommé et attire le plus d’utilisateurs ?
* **Récence, fréquence, fidélité** : qui sont mes fidèles lecteurs ?

### Mobile

>[!IMPORTANT]
>
>Les modèles mobiles sont accessibles uniquement si votre suite de rapports est activée pour Mobile.

* **Message :** est axé sur les performances de la messagerie in-app et push.
* **Emplacement :** comprend une carte représentant les données de positionnement.
* **Mesures clés :** sachez de quelle façon se comportent les mesures clés de votre application.
* **Utilisation de l’application :** combien d’utilisateurs, de lancements et de premiers lancements de l’application avait l’application et quelle est la durée de session moyenne ?
* **Acquisition :** contrôlez les performances des liens d’acquisition mobile.
* **Performances :** quelles sont les performances de l’application et où les utilisateurs rencontrent-ils des problèmes ?
* **Rétention :** qui sont mes fidèles utilisateurs et que font-ils ?
* **Parcours :** quels sont les schémas d’utilisation dominants de mon application ?

### Vente au détail

* **Performances de la campagne :** quelles campagnes génèrent le plus de recettes ?
* **Produits :** quels produits sont les plus performants ?

### Web

* **Acquisition :** quels sont les principaux facteurs orientant le trafic vers mon site web ?
* **Consommation de contenu :** où se rendent surtout les personnes sur mon site ?
* **Rétention :** quels types d’utilisateurs seront a priori les plus fidèles à mon site ?
* **Technologie :** quelle technologie utilisent les visiteurs de mon site ?

### Personnes

>[!NOTE] Le modèle Personnes et la mesure Personnes associée peuvent être utilisés uniquement dans le cadre d’[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/fr-FR/device-co-op/using/data/people.html).

Ce modèle repose sur la mesure Personnes, qui est une version dédupliquée de la mesure Visiteurs uniques. La mesure Personnes permet d’évaluer à quelle fréquence les internautes utilisent différents appareils pour interagir avec votre marque. Le modèle permet d’accomplir ce qui suit :

* Segmenter vos données pour les États-Unis/le Canada et le reste du monde. Device Co-op est actuellement uniquement disponible aux États-Unis.
* Comparer côte à côte les mesures Personnes et Visiteurs uniques.
* Afficher le « taux de compression », une mesure calculée qui détermine à quel point le résultat de la mesure Personnes, en pourcentage, est plus petit que celui de la mesure Visiteurs uniques.
* Comparer les nombres totaux de types de périphériques utilisés par vos clients.
* Afficher le nombre moyen de périphériques utilisés par personne.
* Découvrir comment utiliser l’empilement des segments avec la mesure Personnes.
* Découvrir comment l’utilisation d’Experience Cloud ID dans votre environnement améliore l’efficacité de la mesure Personnes.

### Journey IQ : Modèle d’analyse entre appareils

<!-->This content is mirrored in the CDA doc.<-->

Ce modèle vous permet de visualiser des données de performances cruciales entre appareils. Il est disponible uniquement pour les clients qui ont accès à [l’Analyse entre appareils](https://docs.adobe.com/content/help/fr-FR/analytics/components/cda/cda-home.html) (CDA).

* **Note spéciale à l’intention des membres du graphique Co-op** : Indique la partie de votre suite de rapports qui contient des visiteurs dans les régions où le graphique Co-op est pris en charge et les régions où il n’est pas pris en charge.
* **Identification des utilisateurs** : indique la fréquence à laquelle les visiteurs de votre site sont identifiés à l’aide de méthodes basées sur les analyses entre appareils.
* **Mesure de la taille des audiences** : affiche une comparaison entre « Appareils uniques » et « Personnes ». La proportion de ces deux nombres est connue sous le nom de « Compression entre appareils », une mesure calculée visible dans ce panneau. Cette mesure de compression dépend d’un large éventail de facteurs :
   * **Utilisation du graphique Co-op ou du graphique Privé** : En général, les entreprises qui utilisent le Device Co-op ont tendance à voir de meilleurs taux de compression que les celles qui utilisent le graphique Privé.
   * **Taux de connexion** : plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de regrouper les visiteurs entre plusieurs appareils. Les sites qui présentent un faible taux de connexion ont aussi de faibles taux de compression.
   * **Couverture d’Experience Cloud ID** : seuls les visiteurs avec un ECID peuvent être regroupés. Un pourcentage plus faible de visiteurs qui accèdent à votre site en utilisant un ECID correspond à des taux de compression plus faibles.
   * **Utilisation de plusieurs appareils** : si les visiteurs qui se rendent sur votre site n’utilisent pas plusieurs appareils, les taux de compression sont plus faibles.
   * **Granularité des rapports** : la compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs appareils sont moindres au cours d’un seul jour qu’au cours d’un mois entier. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.
* **Segments basés sur les personnes** : contient une liste déroulante de segments qui vous permet d’afficher des données spécifiques à l’appareil. Ce panneau encourage l’expérimentation de segments afin de déterminer comment l’inclusion ou l’exclusion de types d’appareils affectent les rapports.
* **Analyse du parcours entre appareils** : fournit des rapports de flux et d’abandons en fonction du type d’appareil.
* **Attribution entre appareils** : combine les fonctionnalités Journey IQ et Attribution IQ.
* **Autres conseils et astuces** : rubriques utiles sur la CDA qui vous permettent de mieux l’utiliser.