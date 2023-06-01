---
title: Paramètres de composant
description: Affichez les paramètres principaux d’un composant de vue de données.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c0a3fd138b21c2aa0ac6c11e182f58f57a056b42
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 76%

---

# Paramètres de composant

Paramètres principaux utilisés par un composant de vue de données.

![Paramètres de composant](../assets/component-settings.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Type de composant] | Obligatoire. Permet de modifier un composant de la mesure à la Dimension ou de l’autre manière. Si vous modifiez cette sélection de liste déroulante, le composant est déplacé vers sa zone de composants incluse respective. |
| [!UICONTROL Nom du composant] | Obligatoire. Permet de définir le nom convivial qui apparaîtra dans Analysis Workspace. Vous pouvez renommer un composant pour lui donner un nom spécifique à la vue de données. |
| [!UICONTROL Description] | Facultatif, mais recommandé. Fournit des informations sur le composant à d’autres utilisateurs. |
| [!UICONTROL Balises] | Facultatif. Permet de marquer le composant avec des balises personnalisées ou prêtes à lʼemploi pour faciliter la recherche/filtrage dans lʼinterface utilisateur Analysis Workspace. |
| [!UICONTROL Libellés de contexte] | Facultatif. Liste déroulante des libellés disponibles définis par le système qui peuvent être appliqués à un composant. Ces libellés peuvent être nécessaires pour définir un ensemble de composants utilisés pour la création de rapports dans les projets ou les panneaux Analysis Workspace. |
| [!UICONTROL Nom du champ de schéma] | Nom du champ de schéma. |
| [!UICONTROL Type de jeu de données] | Obligatoire. Champ non modifiable qui indique le type de jeu de données (événement, recherche ou profil) dʼoù provient le composant. |
| [!UICONTROL Jeu de données] | Champ non modifiable indiquant le jeu de données d’où provient le composant. Ce champ peut contenir plusieurs jeux de données. |
| [!UICONTROL Type de schéma] | Champ non modifiable affichant le type de données du composant. Alors que vous pouvez utiliser n’importe quel type de champ de schéma pris en charge dans Platform, tous les types de champs ne sont pas pris en charge dans CJA. Les types de données pris en charge sont les suivants : `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` et `Boolean`. Seule la variable `String` le type de données de schéma est actuellement autorisé dans les jeux de données Lookup. |
| [!UICONTROL ID du composant] | Obligatoire. [LʼAPI CJA](https://adobe.io/cja-apis/docs) utilise ce champ pour référencer le composant. Chaque composant d’une vue de données doit être unique. Adobe génère automatiquement un identifiant pour chaque composant ; vous pouvez toutefois cliquer sur l’icône de modification et modifier l’identifiant du composant. La modification de cet identifiant de composant rompt tous les projets Workspace existants qui contiennent ce composant. Bien que chaque composant ait besoin d’un identifiant unique dans une seule vue de données, vous pouvez utiliser le même identifiant de composant dans d’autres vues de données. Si vous utilisez le même ID de composant dans d’autres vues de données, vous pouvez rendre les projets Workspace compatibles entre les vues de données. <br/>Pour les composants basés sur un profil et une recherche, l’identifiant du composant comporte un préfixe d’identifiant basé sur l’identifiant du jeu de données (par exemple : `642b28fcc1f0ee1c074265a0.person.name.firstName`). Lorsque vous souhaitez réutiliser un composant basé sur un profil ou une recherche, comme `person.name.firstName`, dans votre projet Workspace, et configurez ce composant dans différentes vues de données, assurez-vous de renommer l’ID de composant de manière unique (par exemple : `myUniqueID.person.name.firstName`) dans vos vues de données. |
| [!UICONTROL Chemin d’accès] | Obligatoire. Champ non modifiable qui indique le chemin dʼaccès du schéma dʼoù provient le composant. |
| [!UICONTROL Libellés d’utilisation des données] | Tout libellé d’utilisation des données affecté à ce composant dans Adobe Experience Platform. [En savoir plus](/help/data-views/data-governance.md) |
| [!UICONTROL Masquer le composant dans le reporting] | Permet de traiter le composant en dehors de la vue de données pour les non-administrateurs. Les administrateurs peuvent toujours y accéder en cliquant sur [!UICONTROL Afficher tous les composants] dans un projet Analysis Workspace. |

{style="table-layout:auto"}

Voici une vidéo sur les paramètres des composants dans les vues de données :

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
