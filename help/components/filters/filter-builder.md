---
description: Le Créateur de filtres propose un canevas permettant de faire glisser et de déposer des Dimensions de mesures, des filtres et des événements afin de filtrer les personnes en fonction d’opérateurs, de règles et d’une logique de hiérarchie de conteneurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs et actions des personnes entre les visites et les événements.
title: Créer des filtres
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: d045ecf73f7e15940510b764814fb853222e88cc
workflow-type: tm+mt
source-wordcount: '1396'
ht-degree: 23%

---

# Créateur de filtres

Le [!UICONTROL Créateur de filtres] vous permet de créer des filtres simples ou complexes qui identifient les attributs et actions des personnes entre les visites et les événements. Il fournit un canevas permettant de faire glisser et de déposer des dimensions de mesure, des événements ou d’autres filtres afin de filtrer les personnes selon une logique de hiérarchie, des règles et des opérateurs.

Pour plus d’informations sur la création de filtres rapides qui s’appliquent uniquement au projet dans lequel ils sont créés, voir [Filtres rapides](/help/components/filters/quick-filters.md).

## Accès au créateur de filtres

Vous pouvez accéder au Créateur de filtres de l’une des manières suivantes :

* **Navigation supérieure**: Cliquez sur **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Filtres]**.
* **[!UICONTROL Analysis Workspace]**: Avec un projet ouvert dans Analysis Workspace, sélectionnez **[!UICONTROL + Composants]** > **[!UICONTROL Créer un filtre]**.
* **[!UICONTROL Report Builder]**: [Utilisation de filtres dans le Report Builder](/help/report-builder/work-with-filters.md).

## Présentation des critères du créateur {#section_F61C4268A5974C788629399ADE1E6E7C}

Vous pouvez ajouter des définitions de règle et des conteneurs pour définir vos filtres. (Pour plus d’informations sur l’accès au créateur de filtres, voir [Accès au créateur de filtres](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Titre]**: Nommez le filtre.
1. **[!UICONTROL Description]**: Fournissez une description du filtre.
1. **[!UICONTROL Balises]**: [Balisage du filtre](/help/components/filters/manage-filters.md) vous créez en effectuant une sélection depuis une liste de balises existantes ou en créant une nouvelle balise.
1. **[!UICONTROL Définitions]**: C&#39;est là que vous vous trouvez [création et configuration de filtres](/help/components/filters/filters-overview.md), ajoutez des règles et imbriquez et séquencez des conteneurs.
1. **[!UICONTROL Afficher]** : (Sélecteur Conteneur supérieur.) Permet de sélectionner le niveau supérieur [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Personne], [!UICONTROL Session], [!UICONTROL Événement]). Le conteneur de niveau supérieur par défaut est le conteneur Événement .
1. **[!UICONTROL Options]** : icône (engrenage)

   * **[!UICONTROL + Ajouter un conteneur]**: Permet d’ajouter un nouveau conteneur (sous le conteneur de niveau supérieur) à la définition de filtre.
   * **[!UICONTROL Exclure]**: Permet de définir le filtre en excluant une ou plusieurs dimensions, filtres ou mesures.

1. **[!UICONTROL Dimensions]** : les composants sont glissés et déposés depuis la liste Dimensions (barre latérale orange).
1. **[!UICONTROL Opérateur]** : vous pouvez comparer et contraindre des valeurs en utilisant certains opérateurs.
1. **[!UICONTROL Valeur]**: Valeur que vous avez saisie ou sélectionnée pour la dimension, le filtre ou la mesure.
1. **[!UICONTROL Modèles d’attribution]**: Disponibles uniquement pour les dimensions, ces modèles déterminent les valeurs d’une dimension à filtrer. Les modèles de Dimension sont particulièrement utiles dans les filtres séquentiels.

   * **[!UICONTROL Répétitif]** (défaut) : inclut des instances et des valeurs persistantes pour la dimension.
   * **[!UICONTROL Instance]** : inclut des instances pour la dimension.
   * **[!UICONTROL Instances non répétitives]** : inclut des instances uniques (non répétées) pour la dimension. Il s’agit du modèle appliqué dans le flux lorsque les instances de répétition sont exclues.

   ![](assets/attribution-models.jpg)

   **Exemple : Filtre d’événement où eVar1 = A**

   | Exemple | A | A | A (persistante) | B | A | C |
   |---|---|---|---|---|---|---|
   | Répétitif | X | X | X | - | X | - |
   | Instance | X | X | - | - | X | - |
   | Instance non répétitive | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]** : affecte les opérateurs [!UICONTROL AND/OR/THEN] entre des conteneurs ou règles. L’opérateur THEN permet de [définition de filtres séquentiels](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Mesure]** : (barre latérale verte) qui a été glissée-déposée depuis la liste Mesures.
1. **[!UICONTROL Opérateur de comparaison]** : vous pouvez comparer et contraindre des valeurs en utilisant certains opérateurs.
1. **[!UICONTROL Valeur]**: Valeur que vous avez saisie ou sélectionnée pour la dimension, le filtre ou la mesure.
1. **[!UICONTROL X]**: (Supprimer) Permet de supprimer cette partie de la définition de filtre.
1. **[!UICONTROL Publication Experience Cloud]**: La publication d’un filtre Adobe Analytics sur l’Experience Cloud vous permet d’utiliser le filtre correspondant à l’activité marketing dans [!DNL Audience Manager] et dans d’autres canaux d’activation. [En savoir plus...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=fr)
1. **[!UICONTROL Bibliothèque d’audiences]**: Les services d’audience d’Adobe gèrent la traduction des données de personne en filtres d’audience. Ainsi, la création et la gestion des audiences sont similaires à la création et à l’utilisation de filtres, avec la possibilité de partager le filtre d’audience avec l’Experience Cloud. [En savoir plus...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr)
1. **[!UICONTROL Rechercher]**: Permet d’effectuer une recherche dans la liste des dimensions, filtres ou mesures.
1. **[!UICONTROL Dimensions]** : (Liste) cliquez sur l’en-tête pour développer la liste.
1. **[!UICONTROL Mesures]** : cliquez sur l’en-tête pour développer la liste.
1. **[!UICONTROL Filtres]**: Cliquez sur l’en-tête pour développer la liste.
1. **[!UICONTROL Sélecteur de vue de données]**: Permet de sélectionner la suite de rapports sous laquelle ce filtre sera enregistré. Vous pouvez toujours utiliser le filtre dans toutes les vues de données.
1. **[!UICONTROL Aperçu du filtre]**: Vous permet de prévisualiser les mesures clés afin de vérifier si votre filtre est valide et de déterminer sa largeur. Représente la ventilation du jeu de données que vous pouvez vous attendre à voir si vous appliquez ce filtre. Affiche 3 cercles concentriques et une liste afin d’afficher le nombre et le pourcentage de correspondances pour [!UICONTROL Événement], [!UICONTROL Personne], et [!UICONTROL Session] pour une exécution de filtre par rapport à un jeu de données. Ce graphique est mis à jour immédiatement une fois que vous avez créé ou apporté des modifications à votre définition de filtre.
1. **[!UICONTROL Compatibilité des produits]**: Fournit une liste des produits Adobe Analytics (Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Data Warehouse) avec lequel le filtre que vous avez créé est compatible. La plupart des filtres sont compatibles avec tous les produits. Néanmoins, tous les opérateurs et dimensions ne sont pas compatibles avec l’ensemble des produits Analytics, notamment   [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Ce graphique est mis à jour immédiatement une fois que vous avez apporté des modifications à votre définition de filtre.
1. **[!UICONTROL Enregistrer]** ou **[!UICONTROL Annuler]**: Enregistre ou annule le filtre. Après avoir cliqué sur **[!UICONTROL Enregistrer]**, vous accédez au Gestionnaire de filtres où vous pouvez gérer le filtre.

Les filtres avec plages de dates incorporées fonctionnent toujours différemment dans Analysis Workspace par rapport aux filtres [!UICONTROL Reports &amp; Analytics]: Dans Workspace, un filtre avec une plage de dates incorporée remplace la plage de dates du panneau. En revanche, [!UICONTROL Reports &amp; Analytics] indique l’intersection de la plage de dates du rapport et de la plage de dates incorporée du filtre.

## Création d’un filtre {#build-filters}

1. Faites simplement glisser une Dimension, un filtre ou un événement de mesure du volet de gauche vers le [!UICONTROL Définitions] champ .

   ![](assets/drag_n_drop_dimension.png)

1. Définissez l’[opérateur](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=fr) dans le menu déroulant.
1. Saisissez ou sélectionnez une valeur pour l’élément sélectionné.
1. Ajoutez des conteneurs supplémentaires, le cas échéant, en utilisant les règles **[!UICONTROL AND]**, **[!UICONTROL OR]** ou **[!UICONTROL THEN]**.
1. Après avoir placé les conteneurs et défini les règles, consultez les résultats du filtre dans le graphique de validation en haut à droite. Le programme de validation indique le pourcentage et le nombre absolu de pages vues, de visites et de personnes uniques qui correspondent au filtre que vous avez créé.
1. Sous **[!UICONTROL Balises]**, [tag](/help/components/filters/manage-filters.md) le conteneur en sélectionnant une balise existante ou en en créant une.
1. Cliquez sur **[!UICONTROL Enregistrer]** pour enregistrer le filtre.

   Vous accédez au [Gestionnaire de filtres](/help/components/filters/manage-filters.md), où vous pouvez baliser, partager et gérer votre filtre de plusieurs manières.

## Ajout d’un conteneur {#section_1C38F15703B44474B0718CEF06639EFD}

Vous pouvez [créer une structure de conteneurs](/help/components/filters/filters-overview.md) et y placer des règles logiques et des opérateurs.

1. Cliquez sur **[!UICONTROL Options > Ajouter un conteneur]**.

   Une nouvelle [!UICONTROL **Événement**] le conteneur s’ouvre sans [!UICONTROL **Événement**] (Page vue) identifiée.

   ![](assets/new_container.png)

1. Modifiez le type de conteneur, le cas échéant.
1. Faites glisser une Dimension, un filtre ou un événement du panneau de gauche vers le conteneur.
1. Continuez à ajouter des conteneurs à partir du bouton de niveau supérieur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur]** situé en haut de la définition ou ajoutez des conteneurs depuis un conteneur pour imbriquer la logique.

   **OU**

   Sélectionnez une ou plusieurs règles, puis cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur d’après la sélection]**. Votre sélection devient ainsi un conteneur distinct.

## Utilisation de périodes {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Vous pouvez créer des filtres qui contiennent des périodes flottantes afin de répondre aux questions sur les campagnes ou les événements en cours.

Par exemple, vous pouvez facilement créer un filtre qui inclut &quot;toutes les personnes qui ont effectué un achat au cours des 60 derniers jours&quot;.

Vous créez un conteneur Session et, dans celui-ci, ajoutez le conteneur [!UICONTROL 60 derniers jours] période et mesure [!UICONTROL Les commandes sont supérieures ou égales à 1], avec un opérateur ET.

Voici une vidéo sur l’utilisation de périodes flottantes dans les filtres :

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Empilage de filtres {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

L&#39;empilement de filtres fonctionne en combinant les critères de chaque filtre à l&#39;aide d&#39;un opérateur &quot;et&quot;, puis en appliquant les critères combinés. Vous pouvez le faire dans un projet Workspace directement ou dans le créateur de filtres.

Par exemple, l’empilement d’un filtre &quot;utilisateurs de téléphone mobile&quot; et d’un filtre &quot;géographie États-Unis&quot; renvoie des données uniquement pour les utilisateurs de téléphone mobile aux États-Unis.

Considérez ces filtres comme des blocs de création ou des modules que vous pouvez inclure dans une bibliothèque de filtres pour que les utilisateurs les utilisent à leur guise. Ainsi, vous pouvez réduire considérablement le nombre de filtres nécessaires. Supposons, par exemple, que vous ayez 40 filtres :

* 20 pour les utilisateurs de téléphone mobile dans différents pays (États-Unis_mobile, Allemagne_mobile, France_mobile, Brésil_mobile, etc.)
* 20 pour les utilisateurs de tablette dans différents pays (États-Unis_tablette, Allemagne_tablette, France_tablette, Brésil_tablette, etc.)

En utilisant l’empilement des filtres, vous pouvez réduire votre nombre de filtres à 22 et les empiler selon vos besoins. Vous devez créer les filtres suivants :

* un filtre pour les utilisateurs mobiles ;
* un filtre pour les utilisateurs de tablette
* 20 filtres pour les différents pays

>[!NOTE]
>
>Lors de l’empilement de deux filtres, ils sont par défaut associés à une instruction AND. qui ne peut pas être changée en instruction OR.

1. Accédez au Créateur de filtres.

1. Indiquez un titre et une description pour le filtre.

1. Cliquez sur **[!UICONTROL Afficher les filtres]** pour afficher la liste des filtres dans le volet de navigation de gauche.

1. Faites glisser les filtres à empiler vers le canevas de définition de filtre.

1. Sélectionnez [!UICONTROL **Enregistrer**].

