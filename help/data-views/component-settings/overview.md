---
title: Paramètres de composant
description: Affichez les paramètres principaux d’un composant de vue de données.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 3f20520a2021d9b6066b0492ed11a1a4619ab1d4
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 99%

---

# Paramètres de composant

Paramètres principaux utilisés par un composant de vue de données.

![Paramètres de composant](../assets/component-settings.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Type de composant] | Obligatoire. Permet de modifier un composant de mesure en dimension ou vice versa. La modification de cette liste déroulante déplace le composant vers sa zone de composants incluse respective. |
| [!UICONTROL Nom du composant] | Obligatoire. Permet de définir le nom convivial qui apparaîtra dans Analysis Workspace. Vous pouvez renommer un composant pour lui donner un nom spécifique à la vue de données. |
| [!UICONTROL Description] | Facultatif, mais recommandé. Fournit des informations sur le composant à d’autres utilisateurs. |
| [!UICONTROL Balises] | Facultatif. Permet de marquer le composant avec des balises personnalisées ou prêtes à lʼemploi pour faciliter la recherche/filtrage dans lʼinterface utilisateur Analysis Workspace. |
| [!UICONTROL Nom du champ] | Nom du champ de schéma. |
| [!UICONTROL Type de jeu de données] | Obligatoire. Champ non modifiable qui indique le type de jeu de données (événement, recherche ou profil) dʼoù provient le composant. |
| [!UICONTROL Jeu de données] | Champ non modifiable indiquant le jeu de données d’où provient le composant. Ce champ peut contenir plusieurs jeux de données. |
| [!UICONTROL Type de schéma] | Champ non modifiable affichant le type de données du composant.  Alors que vous pouvez utiliser n’importe quel type de champ de schéma pris en charge dans Platform, tous les types de champs ne sont pas pris en charge dans CJA. Les types de données pris en charge sont les suivants : `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` et `Boolean`. Seul le type de données de schéma `String` est actuellement autorisé dans les jeux de données de recherche. |
| [!UICONTROL ID du composant] | Obligatoire. [LʼAPI CJA](https://adobe.io/cja-apis/docs) utilise ce champ pour référencer le composant. Chaque composant d’une vue de données doit être unique. Adobe génère automatiquement un identifiant pour chaque composant ; vous pouvez toutefois cliquer sur l’icône de modification et modifier l’identifiant du composant. La modification de cet identifiant de composant rompt tous les projets Espace de travail existants qui contiennent ce composant. Bien que chaque composant ait besoin d’un identifiant unique dans une seule vue de données, vous pouvez utiliser le même identifiant de composant dans d’autres vues de données. Si vous utilisez le même ID de composant dans d’autres vues de données, vous pouvez rendre les projets Espace de travail. compatibles entre les vues de données. |
| [!UICONTROL Chemin du schéma] | Obligatoire. Champ non modifiable qui indique le chemin dʼaccès du schéma dʼoù provient le composant. |
| [!UICONTROL Masquer le composant dans le reporting] | Permet de traiter le composant en dehors de la vue de données pour les non-administrateurs. Les administrateurs peuvent toujours y accéder en cliquant sur [!UICONTROL Afficher tous les composants] dans un projet Analysis Workspace. |

Voici une vidéo sur les paramètres des composants dans les vues de données :

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
