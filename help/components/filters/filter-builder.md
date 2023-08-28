---
description: Le Créateur de filtres propose un canevas permettant de faire glisser et de déposer des Dimensions de mesures, des filtres et des événements afin de filtrer les personnes en fonction d’opérateurs, de règles et d’une logique de hiérarchie de conteneurs. Cet outil de développement intégré vous permet de créer et d’enregistrer des filtres simples ou complexes qui identifient les attributs et actions des personnes entre les visites et les événements.
title: Créer des filtres
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 35c57e883794c74553ab14d6e99e55824d41d4be
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 23%

---

# Créateur de filtres

La variable [!UICONTROL Créateur de filtres] vous permet de créer des filtres simples ou complexes qui identifient les attributs et actions des personnes entre les visites et les événements. Il fournit un canevas permettant de faire glisser et de déposer des dimensions de mesure, des événements ou d’autres filtres afin de filtrer les personnes selon une logique de hiérarchie, des règles et des opérateurs.

Pour plus d’informations sur la création de filtres rapides qui s’appliquent uniquement au projet dans lequel ils sont créés, voir [Filtres rapides](/help/components/filters/quick-filters.md).

## Accès au créateur de filtres

Vous pouvez accéder au Créateur de filtres de l’une des manières suivantes :

* **Navigation supérieure**: cliquez sur **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Filtres]**.
* **[!UICONTROL Analysis Workspace]**: avec un projet ouvert dans Analysis Workspace, sélectionnez **[!UICONTROL + Composants]** > **[!UICONTROL Créer un filtre]**.
* **[!UICONTROL Report Builder]**: [Utilisation de filtres dans le Report Builder](/help/report-builder/work-with-filters.md).

## Présentation des critères du créateur {#section_F61C4268A5974C788629399ADE1E6E7C}

Vous pouvez ajouter des définitions de règle et des conteneurs pour définir vos filtres. (Pour plus d’informations sur l’accès au créateur de filtres, voir [Accès au créateur de filtres](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

| Élément de lʼinterface utilisateur | Description |
| --- | --- |
| **[!UICONTROL Titre]** | Nommer le filtre |
| **[!UICONTROL Description]** | Fournissez une description détaillée du filtre. |
| **[!UICONTROL Balises]** | [Balisage du filtre](/help/components/filters/manage-filters.md) vous créez en effectuant une sélection depuis une liste de balises existantes ou en créant une nouvelle balise. |
| **[!UICONTROL Définitions]** | C&#39;est là que vous vous trouvez [création et configuration de filtres](/help/components/filters/filters-overview.md), ajoutez des règles et imbriquez et séquencez des conteneurs. |
| **[!UICONTROL Inclure]** | (Sélecteur Conteneur supérieur.) Permet de sélectionner le niveau supérieur. [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Personne], [!UICONTROL Session], [!UICONTROL Événement]). Le conteneur de niveau supérieur par défaut est le conteneur Événement . |
| **[!UICONTROL Options]** | Icône (engrenage) | <ul><li>**[!UICONTROL + Ajouter un conteneur]**: vous permet d’ajouter un nouveau conteneur (sous le conteneur de niveau supérieur) à la définition de filtre.</li><li>**[!UICONTROL Exclure]**: vous permet de définir le filtre en excluant une ou plusieurs dimensions, filtres ou mesures.</li></ul> |
| **[!UICONTROL Dimensions]** | Les composants sont déplacés et déposés depuis la liste Dimensions (barre latérale orange). |
| **[!UICONTROL Opérateur]** | Vous pouvez comparer et contraindre des valeurs en utilisant certains opérateurs. (est égal à, n’est pas égal à, contient, contient tous les, etc.) |
| **[!UICONTROL Valeur]** | Valeur que vous avez saisie ou sélectionnée pour la dimension, le filtre ou la mesure. |
| **[!UICONTROL Modèles d’attribution]** | Disponibles uniquement pour les dimensions, ces modèles déterminent les valeurs d’une dimension à filtrer. Les modèles de Dimension sont particulièrement utiles dans les filtres séquentiels.<ul><li>**[!UICONTROL Répétitif]** (défaut) : inclut des instances et des valeurs persistantes pour la dimension.</li><li>**[!UICONTROL Instance]** : inclut des instances pour la dimension.</li><li>**[!UICONTROL Instances non répétitives]** : inclut des instances uniques (non répétées) pour la dimension. Il s’agit du modèle appliqué dans le flux lorsque les instances de répétition sont exclues.</li></ul>Pour obtenir un exemple, reportez-vous à la section &quot;Modèles d’attribution&quot; ci-dessous. |
| **[!UICONTROL Et/Ou/Alors]** | Affecte les opérateurs [!UICONTROL ET/OU/ALORS] aux conteneurs ou règles. L’opérateur ALORS permet de [définition de filtres séquentiels](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Mesure]** | (Barre latérale verte) Mesure qui a été glissée-déposée depuis la liste Mesures. |
| **[!UICONTROL X]** | (Supprimer) Permet de supprimer cette partie de la définition de filtre. |
| **[!UICONTROL Créer une audience à partir du filtre]** | La création d&#39;une audience à partir d&#39;un filtre permet de la partager avec Adobe Experience Platform pour l&#39;activation. [En savoir plus...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Composant Recherche]** | Permet d’effectuer une recherche dans la liste des dimensions, filtres ou mesures. |
| **[!UICONTROL Dimensions]** | (Liste) La liste des dimensions que vous pouvez inclure dans le filtre. Cliquez sur l’en-tête pour développer la liste. |
| **[!UICONTROL Mesures]** | La liste des mesures que vous pouvez inclure dans le filtre. Cliquez sur l’en-tête pour développer la liste. |
| **[!UICONTROL Filtres]** | La liste des filtres existants que vous pouvez inclure dans le filtre. Cliquez sur l’en-tête pour développer la liste. |
| **[!UICONTROL Sélecteur de vue de données]** | Permet de sélectionner la suite de rapports sous laquelle ce filtre sera enregistré. Vous pouvez toujours utiliser le filtre dans toutes les vues de données. |
| **[!UICONTROL Aperçu du filtre]** | Vous permet de prévisualiser les mesures clés afin de vérifier si votre filtre est valide et de déterminer sa largeur. Représente la ventilation du jeu de données que vous pouvez vous attendre à voir si vous appliquez ce filtre. Affiche 3 cercles concentriques et une liste afin d’afficher le nombre et le pourcentage de correspondances pour [!UICONTROL Personnes], [!UICONTROL Sessions], et [!UICONTROL Exécution des rapports] pour une exécution de filtre par rapport à un jeu de données.<p>Ce graphique est mis à jour immédiatement une fois que vous avez créé ou apporté des modifications à votre définition de filtre. |
| **[!UICONTROL Enregistrer]** ou **[!UICONTROL Annuler]** | Enregistre ou annule le filtre. Après avoir cliqué **[!UICONTROL Enregistrer]**, vous accédez au Gestionnaire de filtres où vous pouvez gérer le filtre. |

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

## Ajout d’un conteneur {#containers}

Vous pouvez [créer une structure de conteneurs](/help/components/filters/filters-overview.md) et y placer des règles logiques et des opérateurs.

1. Cliquez sur **[!UICONTROL Options > Ajouter un conteneur]**.

   Une nouvelle [!UICONTROL **Événement**] le conteneur s’ouvre sans [!UICONTROL **Événement**] (Page vue) identifiée.

   ![](assets/new_container.png)

1. Modifiez le type de conteneur, le cas échéant.
1. Faites glisser une Dimension, un filtre ou un événement du panneau de gauche vers le conteneur.
1. Continuez à ajouter des conteneurs à partir du bouton de niveau supérieur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur]** situé en haut de la définition ou ajoutez des conteneurs depuis un conteneur pour imbriquer la logique.

   **OU**

   Sélectionnez une ou plusieurs règles, puis cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur d’après la sélection]**. Votre sélection devient ainsi un conteneur distinct.

## Utilisation de périodes {#date-ranges}

Vous pouvez créer des filtres qui contiennent des périodes flottantes afin de répondre aux questions sur les campagnes ou les événements en cours.

Par exemple, vous pouvez facilement créer un filtre qui inclut &quot;toutes les personnes qui ont effectué un achat au cours des 60 derniers jours&quot;.

Vous créez un conteneur Session et, dans celui-ci, ajoutez le conteneur [!UICONTROL 60 derniers jours] période et mesure [!UICONTROL Les commandes sont supérieures ou égales à 1], avec un opérateur ET.

Voici une vidéo sur l’utilisation de périodes flottantes dans les filtres :

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Empilage de filtres {#stack}

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

1. Fournissez un titre et une description pour le filtre.

1. Cliquez sur **[!UICONTROL Afficher les filtres]** pour afficher la liste des filtres dans la navigation de gauche.

1. Faites glisser les filtres à empiler vers le canevas de définition de filtre.

1. Sélectionnez [!UICONTROL **Enregistrer**].

## Modèles d’attribution {#attribution}

![](assets/attribution-models.jpg)

**Exemple : filtre d’événement où eVar1 = A**

| Exemple | A | A | A (persistante) | B | A | C |
|---|---|---|---|---|---|---|
| Répétitif | X | X | X | - | X | - |
| Instance | X | X | - | - | X | - |
| Instance non répétitive | X | - | - | - | X | - |