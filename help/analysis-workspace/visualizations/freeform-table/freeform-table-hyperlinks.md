---
title: Création d’hyperliens dans un tableau à structure libre dans Analysis Workspace
description: Découvrez comment créer des hyperliens pour les éléments de dimension dans un tableau à structure libre dans Analysis Workspace
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: a6eeb4d35e9cbface2d8e880f976b2ad0aaf74a7
workflow-type: tm+mt
source-wordcount: '1737'
ht-degree: 1%

---

# Créer des hyperliens pour les dimensions dans un tableau à structure libre

Vous pouvez créer des hyperliens pour les éléments de dimension afin de les rendre cliquables dans un tableau à structure libre d’Analysis Workspace.

Cette fonctionnalité est particulièrement utile lors de la création d’hyperliens pour les types d’éléments de dimension suivants :

* Éléments de Dimension auxquels vous souhaitez lier des valeurs URL (par exemple, une dimension URL de page)

* Éléments de Dimension contenant des ventilations auxquelles vous souhaitez lier des valeurs d’URL (par exemple, une dimension Nom de page qui comporte une ventilation d’une dimension URL de page)

* Éléments de Dimension ou ventilations dont les valeurs font partie d’une URL à laquelle vous souhaitez créer un lien (par exemple, une dimension Nom de page qui fait partie d’une URL)

+++  Affichez une démonstration vidéo de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/3430411/?learn=on)

+++

## Création de liens hypertextes pour un ou plusieurs éléments de dimension

Tenez compte des points suivants lors de la création d’hyperliens pour les éléments de dimension :

* Les hyperliens que vous créez sont stockés dans le tableau à structure libre du projet Analysis Workspace. Les hyperliens ne persistent pas lors de l’utilisation des mêmes éléments de dimension ou de dimension dans un autre tableau ou dans un autre projet.

* Si vous modifiez la vue de données du tableau à structure libre, tous les liens hypertexte créés pour les dimensions ou les éléments de dimension du tableau sont toujours disponibles, à condition que la dimension existe dans la vue de données.

* La validité des URL n’est pas vérifiée lors de la création de l’hyperlien.

  Si vous créez un lien hypertexte dont l’URL est incorrecte ou si vous créez un lien hypertexte qui référence un élément de dimension sans valeur d’URL (en référençant directement l’élément de dimension ou en utilisant la variable `$value` ou `$breakdown` ), les utilisateurs qui cliquent sur l’hyperlien verront un message d’erreur indiquant que l’URL n’est pas valide.

* Les hyperliens créés pour un seul élément de dimension remplacent les hyperliens créés sur la dimension.

* Les hyperliens ne sont pas fonctionnels dans [fichiers de PDF téléchargés](/help/analysis-workspace/export/download-send.md).

Pour créer des hyperliens pour un ou plusieurs éléments de dimension :

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Créez un lien hypertexte pour un élément de dimension unique :** Cliquez avec le bouton droit de la souris sur l’élément de dimension du tableau pour lequel vous souhaitez créer l’hyperlien, puis sélectionnez [!UICONTROL **Création d’un lien hypertexte**].

     ![Création d’un lien hypertexte pour un élément de dimension unique](assets/hyperlink-single-add.png)

     La variable [!UICONTROL **Création d’un lien hypertexte**] s’affiche. Le nom de l’élément de dimension pour lequel vous créez un lien hypertexte s’affiche dans la boîte de dialogue.

     ![Création d’un lien hypertexte pour une boîte de dialogue d’un seul élément](assets/hyperlink-dialog-single.png)

   * **Créez des hyperliens pour tous les éléments de dimension d’une colonne de dimension :** Cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de colonne de dimension, puis sélectionnez [!UICONTROL **Création de liens hypertextes pour tous les éléments de dimension**].

     ![Création d’un lien hypertexte pour une dimension](assets/hyperlink-multiple-add.png)

     La variable [!UICONTROL **Création de liens hypertextes pour tous les éléments de dimension**] s’affiche. Le nom de la dimension pour laquelle vous créez des liens hypertexte s’affiche dans la boîte de dialogue.

     ![Boîte de dialogue Créer des liens hypertexte](assets/hyperlink-dialog-multiple.png)

1. Choisissez l’une des options suivantes :

   * [!UICONTROL **Utiliser la valeur de l’élément de dimension comme URL**]: sélectionnez cette option pour les éléments de dimension qui comportent des valeurs d’URL, telles qu’une dimension URL de page.

     Par exemple, si vous utilisez une dimension URL de page où la valeur de chaque élément de dimension est une URL, la sélection de cette option crée un lien hypertexte vers l’URL.

   * [!UICONTROL **Création d’une URL personnalisée**]: spécifiez une URL personnalisée statique ou dynamique. Sélectionnez cette option pour créer des hyperliens pour les éléments de dimension qui ne comportent pas de valeurs d’URL.

     Par exemple, si vous utilisez une dimension Nom de page où la valeur de chaque élément de dimension correspond au nom d’une page (et non à une URL complète), sélectionnez cette option pour spécifier un lien hypertexte à utiliser comme lien pour l’élément de dimension.

     Si vous souhaitez créer des URL dynamiques pour plusieurs éléments de dimension, vous pouvez utiliser la variable `$value` et `$breakdown` dans votre URL personnalisée. Pour plus d’informations, consultez le tableau ci-dessous.

     Pour créer une URL personnalisée, indiquez les informations suivantes :

     | Champ | Description |
     |---------|----------|
     | [!UICONTROL **URL personnalisée**] | Spécifiez une URL personnalisée à utiliser pour l’hyperlien. Les URL doivent être saisies en tant qu’URL complètes. Par exemple : <https://www.example.com><p>L’URL personnalisée que vous créez peut être statique ou dynamique :</p> <ul><li>**URL statiques :** Si vous créez un lien hypertexte pour un élément de dimension individuel, une URL statique peut suffire. <p>Prenons l’exemple suivant : par exemple, si vous disposez d’un élément de dimension Nom de page , vous pouvez créer une URL statique qui lie les utilisateurs à la page web spécifique que vous souhaitez associer au nom de la page.</p><p>Supposons que vous souhaitiez créer des hyperliens pour une liste d’éléments de dimension, chacun liant à sa définition respective dans la documentation d’une page de wiki interne.</p><p>Pour ce faire, créez une URL statique pour chaque élément de dimension. Par exemple :</p><p>https://wiki.internal.company_name/page_name#item_definition</p></li><li>**URL dynamiques :** Si vous créez un lien hypertexte pour plusieurs éléments de dimension ou tous les éléments de dimension d’une colonne de dimension, une URL dynamique est probablement plus pratique. <p>Pour rendre dynamiques les URL personnalisées, vous devez inclure dans l’URL des variables qui permettent à l’URL de changer dynamiquement en fonction de la valeur de la dimension elle-même ou de la valeur de la dimension de ventilation.</p><p>Lors de l’utilisation de variables, les éléments de dimension contenant des caractères non valides dans les URL (espaces, par exemple) sont codés au format URL.</p><p>Les variables suivantes sont disponibles : (**Remarque**: bien que vous puissiez utiliser ces variables dans la même URL, il est probablement plus courant de les utiliser séparément.)</p> <ul><li>**`$value`:** Permet d’insérer la valeur de l’élément de dimension dans l’URL que vous spécifiez. <p>Prenons comme exemple le scénario suivant :</p><p>Supposons que vous souhaitiez créer des hyperliens pour tous les éléments de dimension Nom de page dans un tableau à structure libre, où la valeur de chaque élément de dimension fait partie de l’URL d’une page web. Dans ce cas, vous pouvez créer une seule URL personnalisée qui s’ajuste dynamiquement pour chaque élément de dimension. </p><p>Pour ce faire, ajoutez la variable `$value` à la fin de l’URL personnalisée que vous spécifiez. Par exemple :</p> <p>https://company-name.com/browse/product#\$value</p><p>Lorsque cette URL personnalisée est appliquée aux éléments de dimension Nom de page dont les valeurs sont &quot;ProductY&quot; et &quot;ProductZ&quot;, les liens hypertexte générés ressemblent à ceci : </p><p>https://company-name.com/browse/product#ProductY</p><p>et</p><p> https://company-name.com/browse/product#ProductZ </p><p>![utilisation de valeurs dans les liens hypertexte](assets/table-hyperlinks-vaule.png)</p><p>**Conseil**: si vous ajoutiez uniquement la variable `$value` dans le champ URL personnalisée , ce serait la même chose que de sélectionner la variable [!UICONTROL **Utiliser la valeur de l’élément de dimension**] lors de la création de l’URL.</p></li><li>**`$breakdown`:** Permet d’insérer la valeur de l’élément de dimension de ventilation dans l’URL que vous spécifiez. Cela vous permet d’utiliser une dimension avec un nom convivial dans votre rapport (comme une dimension Nom de produit) tout en créant l’hyperlien basé sur une dimension de ventilation qui peut être moins conviviale (comme un ID de produit ou une dimension URL de page).<p>Lors du référencement d’une dimension de ventilation, il est plus courant de n’avoir qu’un seul élément de ventilation pour un élément de dimension donné. S’il existe plusieurs éléments de ventilation pour un élément de dimension donné, la valeur du premier élément de ventilation est utilisée dans l’URL. Si aucun élément de ventilation n’est répertorié, l’URL n’est pas valide. Le même ordre de tri est appliqué aux éléments de ventilation que celui appliqué au tableau.</p><p>Vous pouvez définir la dimension de ventilation dans la variable [!UICONTROL **Dimension de ventilation**] ci-dessous.</p> <p>Examinez l’exemple de scénario décrit pour la variable [!UICONTROL **Dimension de ventilation**] ci-dessous.</p></li></ul> |
     | [!UICONTROL **Dimension de ventilation (facultatif)**] | Commencez à saisir le nom de la dimension de ventilation à utiliser, puis sélectionnez-la dans la liste déroulante. <p>Si vous sélectionnez une dimension de ventilation dans ce champ, vous devez la référencer à l&#39;aide de la variable `$breakdown` dans l’URL que vous spécifiez dans la variable [!UICONTROL **URL personnalisée**] champ .</p><p>Prenons comme exemple le scénario suivant :</p><p>Supposons que vous souhaitiez créer des hyperliens pour tous les éléments de dimension Nom du produit dans un tableau à structure libre. Chaque élément de dimension Nom du produit contient la ventilation d’une dimension ID de produit.</p></p>Dans ce cas, vous pouvez créer des hyperliens pour chaque dimension Nom du produit qui redirige les utilisateurs vers la page du produit à l’aide de la valeur de la dimension de ventilation ID du produit. </p><p>Pour ce faire, ajoutez la variable `$breakdown` à la fin de l’URL personnalisée que vous spécifiez dans la variable [!UICONTROL **URL personnalisée**] champ . Par exemple :</p><p>https://company-name.com/browse/product/$breakdown</p><p>Lorsque cette URL personnalisée est appliquée à vos éléments de dimension Nom du produit qui comportent des éléments de dimension de ventilation dont les valeurs sont &quot;ProductY&quot; et &quot;ProductZ&quot;, les liens hypertexte générés ressemblent à ceci :</p><p>https://company-name.com/browse/product/ProductY</p><p>et</p><p>https://company-name.com/browse/product/ProductZ</p><p>Vous pouvez ensuite sélectionner la dimension ID de produit dans la variable [!UICONTROL **Dimension de ventilation**] field </p><p>![utilisation de ventilations dans des liens hypertexte](assets/table-hyperlinks-breakdown.png)</p> |

1. Sélectionnez [!UICONTROL **Créer**].

   Les utilisateurs qui affichent le tableau à structure libre voient les éléments de dimension liés par un lien hypertexte. Lorsque vous cliquez sur un élément de dimension, les utilisateurs sont redirigés vers les pages liées par un lien hypertexte dans un onglet de navigateur distinct.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Enregistrer le projet](/help/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.

## Modification des hyperliens

Vous pouvez modifier des hyperliens créés sur des dimensions ou des éléments de dimension dans un tableau à structure libre.

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Modification d’un lien hypertexte pour un élément de dimension unique :** Cliquez avec le bouton droit de la souris sur l’élément de dimension du tableau dans lequel vous souhaitez modifier l’hyperlien.

     ![Modification d’un hyperlien pour un élément de dimension unique](assets/hyperlink-single-edit.png)

   * **Modifier des hyperliens pour tous les éléments de dimension d’une colonne de dimension :** Cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de colonne de dimension.

     ![Editer un hyperlien pour une dimension](assets/hyperlink-dimension-edit.png)

1. Sélectionner [!UICONTROL **Modifier le lien hypertexte**] dans le menu contextuel.

   La variable [!UICONTROL **Modification des liens hypertextes pour les éléments de dimension**] s’affiche.

1. Pour plus d’informations sur les options de configuration de la modification de l’hyperlien, voir Étape 3 dans la section [Création de liens hypertextes pour un ou plusieurs éléments de dimension](#create-hyperlinks-for-one-or-more-dimension-items) section ci-dessus, puis sélectionnez [!UICONTROL **Appliquer**] une fois vos mises à jour terminées.

1. [Enregistrer le projet](/help/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.

## Suppression de liens hypertexte

Vous pouvez supprimer des hyperliens créés pour les éléments de dimension dans un tableau à structure libre.

>[!NOTE]
>
>Dans un tableau à structure libre, si vous supprimez une dimension contenant des liens hypertexte, les liens hypertextes ne sont pas conservés si vous réajoutez la même dimension au tableau à structure libre.

Pour supprimer des hyperliens d’éléments de dimension :

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Supprimez un lien hypertexte d’un seul élément de dimension :** Cliquez avec le bouton droit de la souris sur l’élément de dimension du tableau dans lequel vous souhaitez supprimer l’hyperlien.

     ![Suppression d’un lien hypertexte d’un seul élément de dimension](assets/hyperlink-single-remove.png)

   * **Supprimez les hyperliens de tous les éléments de dimension d’une colonne de dimension :** Cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de colonne de dimension.

     ![Suppression d’un lien hypertexte d’une dimension](assets/hyperlink-dimension-remove.png)

1. Sélectionner [!UICONTROL **Supprimer un lien hypertexte**] dans le menu contextuel.

   L’hyperlien est supprimé de l’élément de dimension unique (si vous avez sélectionné un élément de dimension unique) ou de tous les éléments de dimension (si vous avez sélectionné le nom de dimension dans l’en-tête de colonne de dimension).

1. [Enregistrer le projet](/help/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.
