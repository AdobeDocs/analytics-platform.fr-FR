---
description: Utilisation de filtres rapides dans Analysis Workspace pour Customer Journey Analytics
title: Filtres rapides
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a8e1913fb22414610214f5c0a03f6ef7f3b4f8f0
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 6%

---

# Filtres rapides

Vous pouvez créer des filtres rapides dans un projet afin de contourner la complexité du [Créateur de filtres](/help/components/filters/create-filters.md) complet. Filtres rapides

* S’appliquer uniquement aux projets dans lesquels ils ont été créés (vous pouvez modifier ce paramètre).
* Autoriser jusqu’à 3 règles
* Ne prenez pas en charge les conteneurs imbriqués ni les règles séquentielles.
* Fonctionnement des projets avec plusieurs suites de rapports

Pour une comparaison des effets des filtres rapides par rapport aux filtres de liste de composants complète, accédez à [ici](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> Les filtres rapides sont actuellement en test limité et ne sont pas encore disponibles en général.

## Conditions préalables

N’importe qui peut créer un segment rapide. Cependant, vous avez besoin de l’autorisation Création de segments dans la balise [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) pour pouvoir enregistrer un segment rapide ou l’ouvrir dans le créateur de segments.

## Création de filtres rapides

Dans un tableau à structure libre, cliquez sur l’icône filter+ dans l’en-tête du panneau :

![](assets/quick-seg1.png)

| Paramètre | Description |
| --- | --- |
| Nom | Le nom par défaut d’un filtre est une combinaison des noms des règles du filtre. Vous pouvez renommer le filtre en un nom plus convivial. |
| Inclure/exclure | Vous pouvez inclure ou exclure des composants dans votre définition de filtre, mais pas les deux. |
| Conteneur d’accès/de visites/de visiteurs | Les filtres rapides incluent un [conteneur de filtres](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=fr#filter-containers) uniquement qui vous permet d’inclure une dimension/mesure/plage de dates dans (ou de l’exclure) le filtre.  Visiteur contient les données principales spécifiques au visiteur pour les visites et les pages vues. Un conteneur [!UICONTROL Visite] permet de définir des règles pour ventiler les données du visiteur selon les visites, et un conteneur [!UICONTROL Accès] permet de ventiler les informations du visiteur selon des pages vues spécifiques. Le conteneur par défaut est [!UICONTROL Accès]. |
| Composants (Dimension/mesure/période) | Définissez jusqu’à 3 règles en ajoutant des composants (dimensions et/ou mesures et/ou plages de dates) et leurs valeurs. Il existe trois façons de trouver le composant approprié :<ul><li>Commencez la saisie et le créateur [!UICONTROL Filtre rapide] recherche automatiquement le composant approprié.</li><li>Utilisez la liste déroulante pour trouver le composant.</li><li>Glissez et déposez les composants à partir du rail de gauche.</li></ul> |
| Opérateur | Utilisez le menu déroulant pour trouver les opérateurs standards et les opérateurs [!UICONTROL Comptage distinct]. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/components/filteration/segment-reference/seg-operators.html?lang=en) |
| Signe plus (+) | Ajouter une autre règle |
| Qualificateurs ET/OU | Vous pouvez ajouter des qualificateurs &quot;AND&quot; ou &quot;OR&quot; aux règles, mais vous ne pouvez pas mélanger &quot;AND&quot; et &quot;OR&quot; dans une seule définition de filtre. |
| Appliquer | Appliquez ce filtre au panneau. Si le filtre ne contient aucune donnée, vous serez invité à poursuivre. |
| Ouvrir le Builder | Ouvre le Créateur de filtres. Une fois que vous avez enregistré ou appliqué le filtre dans le Créateur de filtres, il n’est plus considéré comme un &quot;Filtre rapide&quot;. Il devient une partie de la bibliothèque de filtres de liste de composants. |
| Annuler | Annuler ce filtre rapide : ne l’appliquez pas. |
| Période | Le programme de validation utilise la période du panneau pour sa recherche de données. Cependant, toute période appliquée dans un filtre rapide remplace la période du panneau en haut du panneau. |
| Aperçu (en haut à droite) | Vous permet de voir si vous disposez d’un filtre valide et quelle est la largeur du filtre. Représente la ventilation du jeu de données que vous pouvez vous attendre à voir lorsque vous appliquez ce filtre. Un avis peut vous indiquer que ce filtre ne contient aucune donnée. Dans ce cas, vous pouvez poursuivre ou modifier la définition du filtre. |

Voici un exemple de filtre qui combine des dimensions et des mesures :

![](assets/quick-seg2.png)

Le filtre s’affiche en haut. Notez sa barre latérale bleue, par opposition à la barre latérale bleue pour les filtres au niveau du composant dans la bibliothèque de filtres sur la gauche.

![](assets/quick-seg3.png)

## Modification des filtres rapides

1. Pointez sur le filtre rapide et sélectionnez l’icône en forme de crayon.
1. Modifiez la définition du filtre ou le nom du filtre.

## Enregistrer les filtres rapides

Vous pouvez choisir d’enregistrer les filtres rapides dans le [!UICONTROL Créateur de filtres rapides] ou dans le [!UICONTROL Créateur de filtres].

>[!IMPORTANT]
>Une fois le filtre enregistré ou appliqué, vous ne pouvez plus le modifier dans le Créateur de filtres rapides, mais uniquement dans le Créateur de filtres standard.

### Enregistrer dans le créateur de filtres rapides

1. Une fois le filtre rapide appliqué, passez la souris dessus et sélectionnez l’icône d’information (&quot;i&quot;).
1. Cliquez sur **[!UICONTROL Mettre à disposition tous les projets et ajoutez-les à votre liste de composants]**.
1. (Facultatif) Renommez le filtre.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

La barre latérale du filtre passe du bleu réparti par bandes au bleu plus clair. Il apparaît désormais dans la liste de vos composants dans le rail de gauche.

### Enregistrer dans le Créateur de filtres

1. Pointez sur le filtre rapide et sélectionnez l’icône d’information (&quot;i&quot;).
1. Sélectionnez **[!UICONTROL Enregistrer le filtre]**.
1. Laissez le nom tel quel ou renommez le filtre.

   Revenez à Workspace et remarquez que le filtre comporte désormais une barre latérale bleue claire. Cela indique qu’il ne peut plus être modifié/ouvert dans le Créateur de filtres rapides. Et en l&#39;enregistrant, il devient une partie de la liste des composants.

   ![](assets/quick-seg4.png)

Après avoir appliqué le filtre, vous pouvez choisir de l’ajouter à votre liste de composants de filtre et de le rendre disponible pour tous vos projets.

1. Pointez sur le filtre enregistré et sélectionnez l’icône en forme de crayon.

1. Dans la partie supérieure du Créateur de filtres, remarquez cette boîte de dialogue :

   ![](assets/project-only.png)

1. Cochez la case en regard de **[!UICONTROL Mettre tous les projets à disposition et ajoutez-les à votre liste de composants.]**
1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Le filtre apparaît désormais dans la liste des composants de filtre pour tous vos projets.
1. Vous pouvez également [partager le filtre](/help/components/filters/manage-filters.md) avec d’autres personnes de votre entreprise.

## Que sont les filtres de projet uniquement ?

Les filtres Projet uniquement sont des filtres rapides ou des filtres de projet Workspace ad hoc. Lorsque vous les modifiez/ouvrez dans le [!UICONTROL Créateur de filtres], la zone Projet uniquement s’affiche.

Si vous APPLIQUEZ un filtre rapide dans le créateur mais ne cochez pas la case &quot;Mettre à disposition&quot;, il s’agit toujours d’un filtre réservé au projet, mais il ne peut plus être ouvert dans le [!UICONTROL Créateur de filtres rapides]. Si vous cochez la case et cliquez sur **[!UICONTROL Enregistrer]**, il s’agit désormais d’un filtre de liste de composants.
