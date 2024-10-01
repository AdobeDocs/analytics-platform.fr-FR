---
title: Création d’hyperliens dans un tableau à structure libre dans Analysis Workspace
description: Découvrez comment créer des hyperliens pour les éléments de dimension dans un tableau à structure libre dans Analysis Workspace
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: bc03cd75c03d41c5d0f8c2bc54bedc115b723211
workflow-type: tm+mt
source-wordcount: '1609'
ht-degree: 1%

---

# Créer des hyperliens pour les dimensions dans un tableau à structure libre

Vous pouvez créer des hyperliens pour les éléments de dimension afin de les rendre cliquables dans un tableau à structure libre d’Analysis Workspace.

Cette fonctionnalité est particulièrement utile lors de la création d’hyperliens pour les types d’éléments de dimension suivants :

* Éléments de Dimension possédant des valeurs d’URL (par exemple, une dimension URL de page)

* Éléments de Dimension contenant des ventilations qui comportent des valeurs d’URL (par exemple, une dimension Nom de page qui comporte une ventilation d’une dimension URL de page)

* Éléments de Dimension ou ventilations dont les valeurs font partie d’une URL (par exemple, une dimension Nom de page qui fait partie d’une URL)

+++ Affichez une démonstration vidéo de cette fonctionnalité.

>[!VIDEO](https://video.tv.adobe.com/v/3430411/?learn=on)

{{videoaa}}

+++

## Création de liens hypertextes pour un ou plusieurs éléments de dimension

Tenez compte des points suivants lors de la création d’hyperliens pour les éléments de dimension :

* Les hyperliens que vous créez sont stockés dans le tableau à structure libre du projet Analysis Workspace. Les hyperliens ne persistent pas lors de l’utilisation des mêmes éléments de dimension ou de dimension dans un autre tableau ou dans un autre projet.

* Si vous modifiez la vue de données du tableau à structure libre, tous les liens hypertexte créés pour les dimensions ou les éléments de dimension du tableau sont toujours disponibles. Cette fonctionnalité suppose que la dimension existe toujours dans la vue de données.

* La validité des URL n’est pas vérifiée lors de la création de l’hyperlien. Si vous

   * créer un lien hypertexte dont l’URL n’est pas valide, ou
   * créer un lien hypertexte qui référence un élément de dimension qui ne possède pas de valeur d’URL (en référençant directement l’élément de dimension ou en utilisant les variables `$value` ou `$breakdown`),

  les utilisateurs qui cliquent sur l’hyperlien voient alors apparaître un message d’erreur indiquant que l’URL n’est pas valide.

* Les hyperliens créés pour un seul élément de dimension remplacent les hyperliens créés sur la dimension.

* Les liens hypertextes ne sont pas fonctionnels dans les [fichiers de PDF téléchargés](/help/analysis-workspace/export/download-send.md).

Pour créer des hyperliens pour un ou plusieurs éléments de dimension :

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Créer un lien hypertexte pour un élément de dimension unique :** Cliquez avec le bouton droit de la souris sur l’élément de dimension dans le tableau pour lequel vous souhaitez créer le lien hypertexte, puis sélectionnez [!UICONTROL **Créer un lien hypertexte**].

      1. Ouvrez le menu contextuel de l’élément de dimension.
      1. Sélectionnez [!UICONTROL **Créer un lien hypertexte**] dans le menu contextuel.

         La boîte de dialogue [!UICONTROL **Créer un lien hypertexte**] s’affiche. Le nom de l’élément de dimension pour lequel vous créez un lien hypertexte s’affiche dans la boîte de dialogue.

         ![Créer un lien hypertexte pour une boîte de dialogue d’un seul élément](assets/hyperlink-dialog-single.png)

   * **Créez des hyperliens pour tous les éléments de dimension dans une colonne de dimension :** Cliquez avec le bouton droit sur le nom de la dimension dans l’en-tête de colonne de dimension, puis sélectionnez [!UICONTROL **Créer des hyperliens pour tous les éléments de dimension**].

      1. Ouvrez le menu contextuel dans l’en-tête de colonne de dimension.
      1. Sélectionnez [!UICONTROL **Créer un lien hypertexte pour tous les éléments de dimension**] dans le menu contextuel.

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         La boîte de dialogue [!UICONTROL **Créer des hyperliens pour tous les éléments de dimension**] s’affiche. Le nom de la dimension pour laquelle vous créez des liens hypertexte s’affiche dans la boîte de dialogue.

         ![Boîte de dialogue Créer des liens hypertexte](assets/hyperlink-dialog-multiple.png)

1. Choisissez l’une des options suivantes :

   * [!UICONTROL **Utilisez la valeur de l’élément de dimension comme URL**] : sélectionnez cette option pour les éléments de dimension qui possèdent des valeurs d’URL, telles qu’une dimension URL de page.

     Par exemple, si vous utilisez une dimension URL de page où la valeur de chaque élément de dimension est une URL, la sélection de cette option crée un lien hypertexte vers l’URL.

   * [!UICONTROL **Créer une URL personnalisée**] : spécifiez une URL personnalisée statique ou dynamique. Sélectionnez cette option pour créer des hyperliens pour les éléments de dimension qui ne comportent pas de valeurs d’URL.

     Par exemple : vous utilisez une dimension Nom de page où la valeur de chaque élément de dimension correspond au nom d’une page (et non à une URL complète). Sélectionnez ensuite cette option pour spécifier un lien hypertexte à utiliser comme lien pour l’élément de dimension.

     Si vous souhaitez créer des URL dynamiques pour plusieurs éléments de dimension, vous pouvez utiliser les variables `$value` et `$breakdown` dans votre URL personnalisée. Pour plus d’informations, consultez le tableau ci-dessous.

     Pour créer une URL personnalisée, indiquez les informations suivantes :

     | Champ | Description |
     |---------|----------|
     | [!UICONTROL **URL personnalisée**] | Spécifiez une URL personnalisée à utiliser pour l’hyperlien. Les URL doivent être saisies en tant qu’URL complètes. Par exemple : <https://www.example.com><p>L’URL personnalisée que vous créez peut être statique ou dynamique :</p> <ul><li>**URL statiques :** Vous pouvez spécifier une URL statique pour un seul élément de dimension ou pour tous les éléments de dimension lorsque vous souhaitez que les éléments soient tous liés à la même URL. Par exemple : `https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**URL dynamiques :** Vous pouvez créer une URL dynamique si vous souhaitez créer des liens hypertexte uniques pour plusieurs éléments de dimension ou pour tous les éléments de dimension d’une colonne de dimension.<p>Pour rendre dynamiques les URL personnalisées, vous devez inclure une variable dans l’URL afin de modifier l’URL en fonction de la valeur de la dimension ou de la valeur de la dimension de ventilation.</p><p>Lors de l’utilisation de variables, les éléments de dimension contenant des caractères non valides dans les URL (espaces, par exemple) sont codés au format URL.</p><p>Les variables suivantes sont disponibles : (**Remarque** : Bien que vous puissiez utiliser ces variables dans la même URL, il est plus courant de les utiliser séparément.)</p> <ul><li>**`$value`:** Permet d’insérer la valeur de l’élément de dimension dans l’URL que vous spécifiez. <p>Supposons que vous souhaitiez créer des hyperliens pour tous les éléments de dimension Nom de page dans un tableau à structure libre, où la valeur de chaque élément de dimension fait partie de l’URL d’une page web. Dans ce cas, vous pouvez créer une seule URL personnalisée qui s’ajuste dynamiquement pour chaque élément de dimension. <br/>Par exemple : `https://company-name.com/browse/product#\$value`</p><p>Lorsque cette URL personnalisée est appliquée à vos éléments de dimension Nom de page dont les valeurs sont &quot;ProductY&quot; et &quot;ProductZ&quot;, les liens hypertexte générés ressemblent à ceci : <br/>`https://company-name.com/browse/product#ProductY` et<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![utiliser des valeurs dans des liens hypertexte](assets/table-hyperlinks-vaule.png)</p><p>**Conseil** : L’ajout de la variable `$value` dans le champ URL personnalisée revient à sélectionner l’option [!UICONTROL **Utiliser la valeur de l’élément de dimension**] lors de la création de l’URL.</p></li><li>**`$breakdown`:** Permet d’insérer la valeur de l’élément de dimension de ventilation dans l’URL que vous spécifiez. Avec `$breakdown`, vous pouvez utiliser une dimension avec un nom convivial dans votre rapport (comme une dimension Nom de produit). Générez également un lien hypertexte basé sur une dimension de ventilation qui peut être moins conviviale (comme un ID de produit ou une dimension URL de page).<p>Lors du référencement d’une dimension de ventilation, il est plus courant de n’avoir qu’un seul élément de ventilation pour un élément de dimension donné. S’il existe plusieurs éléments de ventilation pour un élément de dimension donné, la valeur du premier élément de ventilation est utilisée dans l’URL. Si aucun élément de ventilation n’est répertorié, l’URL n’est pas valide. Le même ordre de tri est appliqué aux éléments de ventilation que celui appliqué au tableau.</p><p>Vous spécifiez la dimension de ventilation dans le champ [!UICONTROL **Dimension de ventilation**] ci-dessous.</p> <p>Examinez l’exemple de scénario décrit pour le champ [!UICONTROL **Dimension de ventilation**] ci-dessous.</p></li></ul> |
     | [!UICONTROL **Dimension de ventilation (facultatif)**] | Commencez à saisir le nom de la dimension de ventilation à utiliser, puis sélectionnez-la dans la liste déroulante. <p>Si vous sélectionnez une dimension de ventilation dans ce champ, vous devez la référencer à l’aide de la variable `$breakdown` dans l’URL que vous spécifiez dans le champ [!UICONTROL **URL personnalisée**].</p><p>Supposons que vous souhaitiez créer des hyperliens pour tous les éléments de dimension Nom du produit dans un tableau à structure libre. Chaque élément de dimension Nom du produit contient la ventilation d’une dimension ID de produit.</p></p>Dans ce cas, vous pouvez créer des hyperliens pour chaque dimension Nom du produit qui redirige les utilisateurs vers la page du produit à l’aide de la valeur de la dimension de ventilation ID du produit. </p><p>Ajoutez la variable `$breakdown` à la fin de l’URL personnalisée que vous spécifiez dans le champ [!UICONTROL **URL personnalisée**]. Par exemple :</p><p>`https://company-name.com/browse/product/$breakdown`</p>Lorsque cette URL personnalisée est appliquée à vos éléments de dimension Nom du produit (qui comportent des éléments de dimension de ventilation dont les valeurs sont &quot;ProductY&quot; et &quot;ProductZ&quot;), les hyperliens générés ressemblent à :<br/>`https://company-name.com/browse/product/ProductY` et<br/>`https://company-name.com/browse/product/ProductZ`</p><p>Vous pouvez ensuite sélectionner la dimension ID de produit dans le champ [!UICONTROL **Dimension de ventilation**]. </p><p>![utiliser des ventilations dans des hyperliens](assets/table-hyperlinks-breakdown.png)</p> |

1. Sélectionnez [!UICONTROL **Créer**].

   Les utilisateurs qui affichent le tableau à structure libre voient les éléments de dimension liés par un lien hypertexte. Lorsque vous cliquez sur un élément de dimension, les utilisateurs sont redirigés vers les pages liées par un lien hypertexte dans un onglet de navigateur distinct.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Enregistrez le projet](/help/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.

## Modification des hyperliens

Vous pouvez modifier des hyperliens créés sur des dimensions ou des éléments de dimension dans un tableau à structure libre.

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Modifier un lien hypertexte pour un seul élément de dimension :**

      1. Ouvrez le menu contextuel de l’élément de dimension.
      1. Sélectionnez [!UICONTROL **Modifier l’hyperlien**] dans le menu contextuel.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **Modifier des hyperliens pour tous les éléments de dimension dans une colonne de dimension :**

      1. Ouvrez le menu contextuel dans l’en-tête de colonne de dimension.
      1. Sélectionnez **[!UICONTROL Modifier l’hyperlien pour tous les éléments de dimension]** dans le menu contextuel.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. Sélectionnez [!UICONTROL **Modifier les hyperliens pour tous les éléments de dimension**] dans le menu contextuel.

   La boîte de dialogue [!UICONTROL **Modifier les hyperliens pour les éléments de dimension**] s’affiche.

1. Pour plus d’informations sur les options de configuration pour la modification de l’hyperlien, reportez-vous à l’étape 3 de la section [Création d’hyperliens pour un ou plusieurs éléments de dimension](#create-hyperlinks-for-one-or-more-dimension-items) ci-dessus, puis sélectionnez [!UICONTROL **Appliquer**] lorsque vous avez terminé de vos mises à jour.

1. [Enregistrez le projet](/help/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.

## Suppression de liens hypertexte

Vous pouvez supprimer des hyperliens créés pour les éléments de dimension dans un tableau à structure libre.

>[!NOTE]
>
>Dans un tableau à structure libre, si vous supprimez une dimension contenant des liens hypertexte, les liens hypertextes ne sont pas conservés si vous réajoutez la même dimension au tableau à structure libre.

Pour supprimer des hyperliens d’éléments de dimension :

1. Dans un tableau à structure libre d’Analysis Workspace, effectuez l’une des opérations suivantes :

   * **Supprimer un lien hypertexte d’un seul élément de dimension :**

      1. Ouvrez le menu contextuel de l’élément de dimension.
      1. Sélectionnez [!UICONTROL **Supprimer l’hyperlien**] dans le menu contextuel.
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **Supprimer des hyperliens de tous les éléments de dimension d’une colonne de dimension :**

      1. Ouvrez le menu contextuel dans l’en-tête de colonne de dimension.
      1. Sélectionnez **[!UICONTROL Supprimer l’hyperlien pour tous les éléments de dimension]** dans le menu contextuel.

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   L’hyperlien est supprimé de l’élément de dimension unique si vous avez sélectionné un seul élément de dimension. Ou de tous les éléments de dimension si vous avez sélectionné le nom de la dimension dans l’en-tête de colonne de dimension.

1. [Enregistrez le projet](/help/analysis-workspace/build-workspace-project/save-projects.md) pour enregistrer vos modifications.
