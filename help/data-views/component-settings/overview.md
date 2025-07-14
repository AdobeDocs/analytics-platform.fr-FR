---
title: Paramètres de composant
description: Affichez les paramètres principaux d’un composant de vue de données.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: f3bd60d6a371a16e606d9af60e3359d8128a3c9f
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 90%

---

# Paramètres de composant {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Paramètres de composant"
>abstract="Affichez et configurez le nom, la description et d’autres paramètres associés à un composant. Cochez cette case pour masquer ce composant aux utilisateurs et utilisatrices ne faisant pas partie de l’équipe d’administration dans les rapports. Les administrateurs et les administratrices peuvent toujours accéder au composant en sélectionnant **[!UICONTROL Afficher tous les composants]** dans un projet Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Libellés de contexte"
>abstract="La suppression d’un libellé de contexte peut avoir un impact sur des panneaux ou des rapports spécifiques lorsque le composant est requis."

<!-- markdownlint-enable MD034 -->


Les informations suivantes décrivent les paramètres utilisés par un composant de vue de données.

![Paramètres des composants décrits dans cette section](../assets/component-settings.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Type de composant] | Obligatoire. Permet de modifier un composant de mesure en dimension ou vice versa. La modification de la sélection de cette liste déroulante déplace le composant vers sa zone de composants incluse respective. |
| [!UICONTROL &#x200B; Nom du composant &#x200B;] | Obligatoire. Permet de définir le nom convivial qui apparaîtra dans Analysis Workspace. Vous pouvez renommer un composant pour lui donner un nom spécifique à la vue de données. |
| [!UICONTROL Description] | Facultatif, mais recommandé. Fournit des informations sur le composant à d’autres utilisateurs. |
| [!UICONTROL Balises] | Facultatif. Permet de marquer le composant avec des balises personnalisées ou prêtes à lʼemploi pour faciliter la recherche/filtrage dans lʼinterface utilisateur Analysis Workspace. |
| [!UICONTROL Libellés de contexte] | Facultatif. Un menu déroulant des libellés système disponibles qui peuvent être appliqués à un composant. <p>Ces libellés peuvent être requis dans les cas suivants :</p> <ul><li>Pour définir un ensemble de composants que vous pouvez utiliser dans les rapports d’expérimentation à l’aide du [panneau Expérimentation](/help/analysis-workspace/c-panels/experimentation.md) dans les projets Analysis Workspace.<p>Pour plus d’informations, voir [Intégrer à Journey Optimizer](/help/integrations/ajo.md#data-view) et [Rapports Target](/help/integrations/at.md).</p></li><li>Pour définir un ensemble de composants, vous pouvez utiliser la visualisation des cartes dans les projets Analysis Workspace.<p>Pour plus d’informations, voir [Ajouter des libellés de contexte dans les vues de données](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) dans [Mapper](/help/analysis-workspace/visualizations/map.md).</p><p>**Remarque :** la visualisation des cartes est en phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement.</p></li><li>Lorsque vous utilisez des modèles fournis par Adobe. Par défaut, certains modèles fournis par Adobe ne fonctionnent pas, car ils contiennent des composants qui ne figurent pas dans votre vue de données.<p>Pour chaque composant manquant, un libellé de contexte correspondant est disponible dans votre vue de données. Vous devez soit ajouter le libellé de contexte correspondant à un composant qui se trouve déjà dans votre vue de données, soit ajouter un nouveau composant à votre vue de données et y ajouter le libellé de contexte.</p><p>Pour plus d’informations, voir [Ajouter les composants manquants à la vue de données d’un modèle donné](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) dans l’article [Créer et gérer des modèles](/help/analysis-workspace/templates/create-templates.md).</p> |
| [!UICONTROL Nom du champ de schéma] | Nom du champ de schéma. |
| [!UICONTROL Type de jeu de données] | Obligatoire. Champ non modifiable qui indique le type de jeu de données (événement, recherche ou profil) dʼoù provient le composant. |
| [!UICONTROL Jeu de données] | Champ non modifiable indiquant le jeu de données d’où provient le composant. Ce champ peut contenir plusieurs jeux de données. |
| [!UICONTROL Type de schéma] | Champ non modifiable affichant le type de données du composant. Alors que vous pouvez utiliser n’importe quel type de champ de schéma pris en charge dans Platform, tous les types de champs ne sont pas pris en charge dans Customer Journey Analytics. Les types de données pris en charge sont les suivants : `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` et `Boolean`. Seul le type de données de schéma `String` est actuellement autorisé dans les jeux de données de recherche. |
| [!UICONTROL ID du composant] | Obligatoire. Lʼ[API Customer Journey Analytics](https://adobe.io/cja-apis/docs) utilise ce champ pour référencer le composant. Chaque composant d’une vue de données doit être unique. Adobe génère automatiquement un identifiant pour chaque composant ; vous pouvez toutefois cliquer sur l’icône de modification et modifier l’identifiant du composant. La modification de cet identifiant de composant rompt tous les projets Workspace existants qui contiennent ce composant. Bien que chaque composant ait besoin d’un identifiant unique dans une seule vue de données, vous pouvez utiliser le même identifiant de composant dans d’autres vues de données. Si vous utilisez le même ID de composant dans d’autres vues de données, vous pouvez rendre les projets Workspace compatibles entre les vues de données. <br/>Pour les composants basés sur un profil et une recherche, l’ID du composant comporte un préfixe d’ID basé sur l’ID du jeu de données (par exemple : `642b28fcc1f0ee1c074265a0.person.name.firstName`). Lorsque vous souhaitez réutiliser un composant basé sur un profil ou une recherche, comme `person.name.firstName`, dans votre projet Workspace, et configurer ce composant dans différentes vues de données, assurez-vous de renommer l’ID de composant de manière unique (par exemple, `myUniqueID.person.name.firstName`) dans vos vues de données. |
| [!UICONTROL Chemin d’accès] | Obligatoire. Champ non modifiable qui indique le chemin dʼaccès du schéma dʼoù provient le composant. |
| [!UICONTROL Libellés d’utilisation des données] | Tout libellé d’utilisation des données affecté à ce composant dans Adobe Experience Platform. [En savoir plus](/help/data-views/data-governance.md). |
| [!UICONTROL Masquer le composant dans le reporting] | Permet de traiter le composant en dehors de la vue de données pour les non-administrateurs. Les administrateurs peuvent toujours y accéder en cliquant sur [!UICONTROL Afficher tous les composants] dans un projet Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Paramètres du type de composant](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


