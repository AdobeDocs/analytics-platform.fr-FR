---
description: Utilisation de filtres rapides dans Analysis Workspace pour Customer Journey Analytics
title: Filtres rapides
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 76%

---

# Filtres rapides

Vous pouvez créer des filtres rapides dans un projet afin de contourner la complexité du [Créateur de filtres](/help/components/filters/create-filters.md) complet. Filtres rapides

* Appliquer comme [filtres projet uniquement](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html#project-only).
* Autoriser jusqu’à 3 règles
* Ne pas prendre en charge les conteneurs imbriqués ni les règles séquentielles.

Pour une comparaison des effets des filtres rapides par rapport aux filtres de liste de composants complète, accédez [ici](/help/components/filters/filters-overview.md).

Voici une vidéo sur les filtres rapides (notez qu’elle utilise le terme &quot;segments rapides&quot; à la place.) Toutefois, la fonctionnalité est la même.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Conditions préalables {#prereqs}

N’importe qui peut créer un filtre rapide. Toutefois, vous avez besoin de l’autorisation Création de filtre dans la variable [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) pour enregistrer un filtre rapide ou l’ouvrir dans le Créateur de filtres.

## Création de filtres rapides {#create}

Dans un tableau à structure libre, cliquez sur l’icône filter+ dans l’en-tête du panneau :

![Filtre de segments](assets/quick-seg1.png)

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Nom] | Le nom par défaut d’un filtre est une combinaison des noms des règles du filtre. Vous pouvez donner un nom plus convivial au filtre. |
| [!UICONTROL Inclure/exclure] | Vous pouvez inclure ou exclure des composants dans votre définition de filtre, mais pas les deux. |
| [!UICONTROL Conteneur d’accès/de visites/de visiteurs] | Les filtres rapides incluent un [conteneur de filtres](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers) uniquement qui vous permet d’inclure une dimension/mesure/période dans le filtre (ou de l’en exclure). [!UICONTROL Visiteur] contient les données principales spécifiques au visiteur pour les visites et les pages vues. Un conteneur [!UICONTROL Visite] permet de définir des règles pour ventiler les données du visiteur selon les visites, et un conteneur [!UICONTROL Accès] permet de ventiler les informations du visiteur selon des pages vues spécifiques. Le conteneur par défaut est [!UICONTROL Accès]. |
| [!UICONTROL Composants] (Dimension/mesure/période) | Définissez jusqu’à 3 règles en ajoutant des composants (dimensions, mesures, périodes ou valeurs de dimension). Il existe trois façons de trouver le composant approprié :<ul><li>Commencez la saisie et le créateur [!UICONTROL Filtre rapide] recherche automatiquement le composant approprié.</li><li>Utilisez la liste déroulante pour trouver le composant.</li><li>Glissez et déposez les composants à partir du rail de gauche.</li></ul> |
| [!UICONTROL Opérateur] | Utilisez le menu déroulant pour trouver les opérateurs standards et les opérateurs [!UICONTROL Comptage distinct]. Voir [Opérateurs de filtres](operators.md). |
| Signe plus (+) | Ajouter une autre règle |
| Qualificateurs AND/OR | Vous pouvez ajouter des qualificateurs « AND » ou « OR » aux règles, mais vous ne pouvez pas mélanger « AND » et « OR » dans une seule définition de filtre. |
| [!UICONTROL Appliquer] | Appliquez ce filtre au panneau. Si le filtre ne contient aucune donnée, vous serez invité à poursuivre. |
| [!UICONTROL Ouvrir le Builder] | Ouvre le créateur de filtres. Une fois le filtre enregistré ou appliqué dans le Créateur de filtres, il n’est plus considéré comme un « Filtre rapide ». Il devient une partie de la bibliothèque de filtres de liste de composants. |
| [!UICONTROL Annuler] | Annulez ce filtre rapide : ne l’appliquez pas. |
| [!UICONTROL Période] | Le programme de validation utilise la période du panneau pour sa recherche de données. Cependant, toute période appliquée dans un filtre rapide remplace la période du panneau en haut du panneau. |
| Aperçu (en haut à droite) | Vous permet de voir si vous disposez d’un filtre valide et quelle est la largeur du filtre. Représente la ventilation du jeu de données auquel vous pouvez vous attendre si vous appliquez ce filtre. Vous pourriez recevoir un avis indiquant que ce filtre ne contient aucune donnée. Dans ce cas, vous pouvez poursuivre ou modifier la définition du filtre. |

Voici un exemple de filtre qui combine des dimensions et des mesures :

![Exemple de définition de filtre](assets/quick-seg2.png)

Le filtre s’affiche en haut. Notez sa barre latérale bleue, par opposition à la barre latérale bleue pour les filtres au niveau du composant dans la bibliothèque de filtres sur la gauche.

![Filtrer les emplacements des composants](assets/quick-seg3.png)

## Modification des filtres rapides {#edit}

1. Survolez le filtre rapide et sélectionnez l’icône en forme de crayon.
1. Modifiez la définition du filtre ou le nom du filtre.
1. Cliquez sur [!UICONTROL Appliquer].

## Enregistrer les filtres rapides {#save}

Vous pouvez choisir d’enregistrer les filtres rapides dans le [!UICONTROL Créateur de filtres rapides] ou dans le [!UICONTROL Créateur de filtres].

>[!IMPORTANT]
>Une fois le filtre enregistré ou appliqué, vous ne pouvez plus le modifier dans le Créateur de filtres rapides, mais uniquement dans le Créateur de filtres standard.

### Enregistrer dans le créateur de filtres rapides {#save2}

1. Une fois le filtre rapide appliqué, passez la souris dessus et sélectionnez l’icône d’information (« i »).
1. Cliquez sur **[!UICONTROL Rendre disponible pour tous vos projets et ajouter l’élément à votre liste de composants]**.
1. (Facultatif) Renommez le filtre.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Notez comment la barre latérale du filtre passe de bleu rayé à bleu clair. Il apparaît désormais dans la liste de vos composants dans le rail de gauche.

### Enregistrer dans le Créateur de filtres {#save3}

1. Survolez le filtre rapide et sélectionnez l’icône d’information (« i »).
1. Sélectionnez **[!UICONTROL Enregistrer le filtre]**.
1. Laissez le nom tel quel ou renommez le filtre.

   Revenez à Espace de travail et remarquez que le filtre comporte désormais une barre latérale bleu clair. Cela indique qu’il ne peut plus être modifié/ouvert dans le Créateur de filtres rapides. Et en l’enregistrant, il devient une partie de la liste des composants.

   ![Filtrer la liste des composants](assets/quick-seg4.png)

Après avoir appliqué le filtre, vous pouvez choisir de l’ajouter à votre liste de composants de filtre et de le rendre disponible pour tous vos projets.

1. Survolez le filtre enregistré et sélectionnez l’icône en forme de crayon.

1. Dans la partie supérieure du Créateur de filtres, remarquez cette boîte de dialogue :

   ![Boîte de dialogue Filtre](assets/project-only.png)

1. Cochez la case en regard de **[!UICONTROL Rendre disponible pour tous les projets à disposition et ajouter l’élément à votre liste de composants.]**
1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Le filtre apparaît désormais dans la liste des composants de filtre pour tous vos projets.
1. Vous pouvez également [partager le filtre](/help/components/filters/manage-filters.md) avec d’autres personnes de votre entreprise.

## Que sont les filtres Projet uniquement ? {#project-only}

Les filtres de projet uniquement sont des filtres qui s’appliquent uniquement au projet actuel dans lequel ils ont été créés. Ils ne sont pas disponibles dans d’autres projets et ne peuvent pas être partagés avec d’autres utilisateurs. Elles sont destinées à une exploration rapide de vos données sans avoir à créer et enregistrer un filtre dans le rail de gauche. Il est possible de créer des filtres uniques par projet dans la zone de dépôt du panneau à l’aide de filtres rapides ou [filtres ad hoc](/help/components/filters/ad-hoc-filters.md).

Si vous ouvrez un filtre de projet uniquement dans la variable [!UICONTROL Créateur de filtres], une notification de projet uniquement s’affiche. Si vous ne cochez pas la case &quot;Rendre ce filtre disponible&quot;. et cliquez sur **[!UICONTROL APPLIQUER]**, le segment reste un filtre réservé au projet.

>[!NOTE]
>
>Si vous appliquez un filtre rapide à partir du Créateur de filtres, il ne peut plus être ouvert dans le [!UICONTROL Créateur de filtres rapides].

![Case à cocher « Sʼapplique au projet uniquement » décochée](assets/project-only-unchecked.png)

Si vous cochez la case &quot;Rendre ce filtre disponible&quot;. et cliquez sur **[!UICONTROL ENREGISTRER]**, le filtre devient disponible dans la liste des composants du rail de gauche pour être utilisé dans d’autres projets. Il peut également être partagé avec d’autres utilisateurs à partir du Gestionnaire de filtres.

![Case à cocher « Sʼapplique au projet uniquement » cochée](assets/project-only-checked.png)

