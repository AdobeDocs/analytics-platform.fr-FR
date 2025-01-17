---
description: Présentation de l’utilisation de modèles par défaut dans Analysis Workspace.
title: Utiliser les modèles
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: 50d46d5b2d663e6f0b3951006db34bff0193417e
workflow-type: tm+mt
source-wordcount: '1630'
ht-degree: 2%

---

# Créer et gérer des modèles

Les administrateurs peuvent créer des modèles et les enregistrer pour que d’autres membres de leur société de connexion puissent les utiliser.

Les membres de la société de connexion peuvent utiliser ces modèles de société comme décrit dans la section [Utiliser des modèles](/help/analysis-workspace/templates/use-templates.md).

## Création d’un modèle

Pour créer un modèle pouvant être utilisé par des personnes de votre société de connexion :

1. Dans Analysis Workspace, créez un projet à l’état souhaité.

1. Sélectionnez [!UICONTROL **Projet**] > **[!UICONTROL Enregistrer comme modèle...]**.

   ![Modèle d’entreprise](assets/company-template-save.png)

1. Spécifiez les informations suivantes dans la boîte de dialogue [!UICONTROL Enregistrer en tant que modèle] :

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Nom]** | Attribuez un nom explicite au modèle. |
   | **[!UICONTROL Description]** | Fournissez une brève description du modèle qui décrit ses utilisations prévues. |
   | **[!UICONTROL Pourquoi utiliser ce modèle]** | Fournissez une brève explication pour informer les personnes de l’organisation sur la manière dont ce modèle peut être utilisé. Cette explication s’affiche sur la page Aperçu du modèle. |
   | **[!UICONTROL Canaux]** | Sélectionnez les canaux applicables qui s’appliquent à ce modèle. Vous pouvez sélectionner plusieurs canaux : **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-canal]**, **[!UICONTROL Centre d’appels]** et **[!UICONTROL En magasin]**.<p>Les sélections que vous choisissez déterminent l’emplacement d’affichage du modèle et les filtres qui s’appliquent aux utilisateurs qui y accèdent à partir de la page Modèles d’organisation .</p> |
   | **[!UICONTROL Cas d’utilisation]** | Sélectionnez tous les cas d’utilisation qui s’appliquent à ce modèle. Vous pouvez sélectionner plusieurs cas d’utilisation : **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** et **[!UICONTROL Journey Optimizer]**. <p>Les sélections que vous choisissez déterminent l&#39;emplacement du modèle sur la page Modèles d&#39;organisation. Les utilisateurs peuvent accéder au modèle ou filtrer la liste par cas d’utilisation. </p><p>**Remarque :** l’option **[!UICONTROL Journey Optimizer]** n’est disponible que si les données Journey Optimizer existent dans la vue de données que vous utilisez dans Customer Journey Analytics. Choisir **[!UICONTROL Journey Optimizer]** rend le modèle disponible pour une utilisation dans Adobe Journey Optimizer. Dans Journey Optimizer, un menu déroulant est disponible sur la page **[!UICONTROL Rapports]**, ce qui permet aux utilisateurs et aux utilisatrices de sélectionner ce modèle ou le modèle par défaut. Pour plus d’informations, consultez [Prise en main de l’expérience de création de rapports mise à jour](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) dans la documentation de Journey Optimizer. |
   | **[!UICONTROL Type d’activité Journey Optimizer]** | Choisissez le type d’activité Journey Optimizer à associer à ce modèle : **[!UICONTROL Campagnes]**, **[!UICONTROL Parcours]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Rapports]** ou **[!UICONTROL Abonnements]**. <p>Laissez ce champ vide si vous souhaitez que ce modèle soit associé à tous les types d’activité.</p><p>Ce champ s&#39;affiche uniquement si **[!UICONTROL Journey Optimizer]** est sélectionné dans le champ **[!UICONTROL Cas d&#39;utilisation]**.</p> |
   | **[!UICONTROL Activité Journey Optimizer]** | Choisissez l&#39;activité Journey Optimizer à associer à ce modèle. <p>Laissez ce champ vide si vous souhaitez que ce modèle soit associé à toutes les activités du type d&#39;activité sélectionné.</p><p>Ce champ s&#39;affiche uniquement si **[!UICONTROL Journey Optimizer]** est sélectionné dans le champ **[!UICONTROL Cas d&#39;utilisation]**.</p> |
   | **[!UICONTROL Étiquettes]** | Spécifiez les balises à appliquer au modèle. Les utilisateurs peuvent filtrer la liste des modèles en fonction des balises que vous ajoutez. |

1. Sélectionnez [!UICONTROL **Enregistrer comme modèle**].

Pour plus d’informations sur la façon dont les utilisateurs peuvent créer un projet basé sur un modèle, voir [Créer un projet basé sur un modèle](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) dans [Utiliser des modèles](/help/analysis-workspace/templates/use-templates.md).

## Modification ou suppression d’un modèle

Les administrateurs peuvent modifier ou supprimer des modèles d’entreprise.

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**] puis, sous **[!UICONTROL Modèles]** dans le rail de gauche, sélectionnez **[!UICONTROL _login_company_name _templates]**.

1. Si vous affichez des modèles dans une vue Colonnes ![icône Vue Colonnes](assets/column-view-icon.png) :

   1. Accédez au modèle à modifier ou supprimer, puis sélectionnez l’icône d’informations en regard du nom du modèle.

      ![Informations sur le modèle d’entreprise](assets/company-template-info.png)

   1. Sélectionnez **[!UICONTROL Aperçu]**.

   1. Sélectionnez l’icône Plus , puis sélectionnez **[!UICONTROL Modifier]** ou **[!UICONTROL Supprimer]**.

      ![Modifier ou supprimer un modèle](assets/company-template-edit-delete.png)

1. Si vous affichez des modèles dans un mode Carte ![icône du mode Carte](assets/card-view-icon.png) :

   1. Recherchez le modèle à modifier ou à supprimer.

      ![Mode Carte de modèle d’entreprise](assets/company-template-cards.png)

   1. Pointez sur le modèle, puis sélectionnez **[!UICONTROL Aperçu]**.

   1. Sélectionnez l’icône Plus , puis sélectionnez **[!UICONTROL Modifier]** ou **[!UICONTROL Supprimer]**.

      ![Modification ou suppression de la carte de modèle d’entreprise](assets/company-template-card-edit-delete.png)

1. Si vous modifiez un modèle, apportez les modifications souhaitées, puis sélectionnez [!UICONTROL **Projet**] > **[!UICONTROL Enregistrer comme modèle...]**.

   ![Modèle d’entreprise](assets/company-template-save.png)

1. Spécifiez les informations suivantes dans la boîte de dialogue [!UICONTROL Enregistrer en tant que modèle] :

   | Champ | Description |
   |---------|----------|
   | **[!UICONTROL Nom]** | Attribuez un nom explicite au modèle. |
   | **[!UICONTROL Description]** | Fournissez une brève description du modèle qui décrit ses utilisations prévues. |
   | **[!UICONTROL Pourquoi utiliser ce modèle]** | Fournissez une brève explication pour informer les personnes de l’organisation sur la manière dont ce modèle peut être utilisé. Cette explication s’affiche sur la page Aperçu du modèle. |
   | **[!UICONTROL Canaux]** | Sélectionnez les canaux applicables qui s’appliquent à ce modèle. Vous pouvez sélectionner plusieurs canaux : **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-canal]**, **[!UICONTROL Centre d’appels]** et **[!UICONTROL En magasin]**. Si aucun canal n’est sélectionné, le modèle est inclus avec tous les canaux.<p>Les sélections que vous choisissez déterminent l’emplacement d’affichage du modèle et les filtres qui s’appliquent aux utilisateurs qui y accèdent à partir de la page Modèles d’organisation .</p> |
   | **[!UICONTROL Cas d’utilisation]** | Sélectionnez tous les cas d’utilisation qui s’appliquent à ce modèle. Vous pouvez sélectionner plusieurs cas d’utilisation : **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** et **[!UICONTROL Journey Optimizer]**. <p>Les sélections que vous choisissez déterminent l&#39;emplacement du modèle sur la page Modèles d&#39;organisation. Les utilisateurs peuvent accéder au modèle ou filtrer la liste par cas d’utilisation. </p><p>**Remarque :** choisir **[!UICONTROL Journey Optimizer]** rend également le modèle disponible dans Adobe Journey Optimizer. Dans Journey Optimizer, un menu déroulant est disponible sur la page **[!UICONTROL Rapports]** et permet aux utilisateurs de sélectionner ce modèle ou le modèle par défaut. Pour plus d’informations, consultez [Prise en main de l’expérience de création de rapports mise à jour](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) dans la documentation de Journey Optimizer. |
   | **[!UICONTROL Type d’activité Journey Optimizer]** | Choisissez le type d’activité Journey Optimizer à associer à ce modèle : **[!UICONTROL Campagnes]**, **[!UICONTROL Parcours]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Rapports]** ou **[!UICONTROL Abonnements]**. <p>Laissez ce champ vide si vous souhaitez que ce modèle soit associé à tous les types d’activité.</p><p>Ce champ s&#39;affiche uniquement si **[!UICONTROL Journey Optimizer]** est sélectionné dans le champ **[!UICONTROL Cas d&#39;utilisation]**.</p> |
   | **[!UICONTROL Activité Journey Optimizer]** | Choisissez l&#39;activité Journey Optimizer à associer à ce modèle. <p>Laissez ce champ vide si vous souhaitez que ce modèle soit associé à toutes les activités du type d&#39;activité sélectionné.</p><p>Ce champ s&#39;affiche uniquement si **[!UICONTROL Journey Optimizer]** est sélectionné dans le champ **[!UICONTROL Cas d&#39;utilisation]**.</p> |
   | **[!UICONTROL Étiquettes]** | Spécifiez les balises à appliquer au modèle. Les utilisateurs peuvent filtrer la liste des modèles en fonction des balises que vous ajoutez. |

1. Sélectionnez [!UICONTROL **Enregistrer comme modèle**].

## Renommer, baliser ou approuver des modèles

Les administrateurs peuvent renommer, baliser et approuver les modèles d’entreprise.

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**], puis sélectionnez l’onglet **[!UICONTROL Projets]** dans le rail de gauche.

1. Sélectionnez l’icône de filtre pour filtrer la liste des projets.

1. Dans le rail de filtre, sélectionnez **AUTRES FILTRES** puis **Modèles d’entreprise**.

   Une liste des modèles d’entreprise s’affiche. Aucun projet standard ne s’affiche sauf ceux épinglés.

   Les modèles d’entreprise peuvent être identifiés par l’icône ![modèles](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) qui précède le nom du modèle.

   ![Afficher les filtres de modèles d’entreprise](assets/company-templates-filter.png)

1. Cliquez sur l’icône des points de suspension **...** en regard d’un modèle pour afficher les options disponibles.

   ![Actions du modèle d’entreprise](assets/company-templates-actions.png)

1. Sélectionnez **[!UICONTROL Renommer]**, **[!UICONTROL Balise]** ou **[!UICONTROL Approuver]**.

   Vous pouvez également supprimer un modèle, ou en supprimer un, comme décrit dans la section [Modifier ou supprimer des modèles](#edit-or-delete-templates).

1. (Facultatif) Pour revenir à la vue normale, dans le rail de filtre, désélectionnez **[!UICONTROL Modèles d’entreprise]**.

## Ajouter les composants manquants à la vue de données d’un modèle donné

Par défaut, certains modèles fournis par Adobe ne peuvent pas être utilisés, car ils contiennent des composants qui ne figurent pas dans votre vue de données.

Pour chaque composant manquant, un libellé de contexte correspondant est disponible dans votre vue de données. Vous devez soit ajouter le libellé de contexte correspondant à un composant qui se trouve déjà dans votre vue de données, soit ajouter un nouveau composant à votre vue de données et y ajouter le libellé de contexte.

Pour ajouter des composants manquants à un modèle :

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**] puis, sous **[!UICONTROL Modèles]** dans le rail de gauche, sélectionnez **[!UICONTROL Modèles d’Adobe]**.

1. Sélectionnez l’icône de filtre pour filtrer la liste des modèles.

1. Sélectionnez **[!UICONTROL Non prêt à l’emploi]** pour afficher les modèles qui nécessitent des composants qui ne figurent pas dans votre vue de données.

   ![Utiliser un modèle sans composants](assets/template-not-ready.png)

1. Recherchez un modèle qui n’est pas encore prêt à être utilisé avec votre vue de données.

1. Effectuez l’une des opérations suivantes :

   * **Si vous affichez des modèles dans une vue Colonnes** ![icône Vue Colonnes](assets/column-view-icon.png) :

      1. Accédez au modèle qui n’est pas encore prêt à être utilisé avec votre vue de données, puis sélectionnez l’icône d’informations à côté du nom du modèle.

         ![Informations sur le modèle d’entreprise](assets/company-template-info.png)

      1. Sélectionnez **[!UICONTROL Aperçu]**.

         ![Page d’aperçu du modèle](assets/template-preview.png)

   * **Si vous affichez des modèles dans un mode Carte** ![icône du mode Carte](assets/card-view-icon.png) :

      1. Recherchez le modèle qui n’est pas encore prêt à être utilisé avec votre vue de données.

         ![Mode Carte de modèle d’entreprise](assets/company-template-cards.png)

      1. Pointez sur le modèle, puis sélectionnez **[!UICONTROL Aperçu]**.

         ![Page d’aperçu du modèle](assets/template-preview.png)

1. Dans la section **[!UICONTROL Composants manquants]**, une liste des composants manquants de la vue de données s’affiche. Sélectionnez **[!UICONTROL Ajouter ces composants à la vue de données]**.

   La page de configuration de la vue de données s’affiche dans un nouvel onglet.

1. Sélectionnez l’onglet **[!UICONTROL Composants]** pour la vue de données.

   ![Onglet Composants de la vue de données](assets/template-dataview.png)

1. Pour chaque composant répertorié comme manquant dans le modèle, effectuez l’une des opérations suivantes dans l’onglet **[!UICONTROL Composants]** :

   * Dans la section **[!UICONTROL Composants inclus]**, sélectionnez un composant déjà inclus dans la vue de données que vous souhaitez utiliser pour le composant manquant.

   * Ajoutez un nouveau composant à la vue de données que vous souhaitez utiliser pour le composant manquant, puis sélectionnez le composant.

     Pour ajouter un nouveau composant à la vue de données, recherchez dans la liste des champs de schéma, puis faites-le glisser dans la section **[!UICONTROL Composants inclus]**.

1. Une fois le composant sélectionné, recherchez le menu déroulant **[!UICONTROL Libellés de contexte]** dans la colonne de droite.

   ![Onglet Composants de la vue de données](assets/template-dataview-context-label.png)

1. Dans le menu déroulant **[!UICONTROL Libellés de contexte]**, sélectionnez le libellé de contexte qui porte le même nom que le composant manquant.

1. Sélectionnez **[!UICONTROL Enregistrer et continuer]**.

1. Pour chaque composant manquant, répétez le processus d’ajout du libellé de contexte correspondant à un composant dans la vue de données.


## Accès à un modèle d’entreprise

Comme pour les modèles fournis par Adobe, les utilisateurs de l’entreprise peuvent accéder aux modèles créés par les administrateurs.

Pour plus d’informations sur l’accès à un modèle d’entreprise, voir [Accès et exécution d’un modèle](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) dans [Utilisation de modèles](/help/analysis-workspace/templates/use-templates.md).

## Masquer l’onglet Modèles

Les administrateurs peuvent masquer l’onglet Modèles pour tous les utilisateurs de leur entreprise.

1. Accédez à **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Préférences]** > **[!UICONTROL Société]**.
1. Sélectionnez l’option **[!UICONTROL Masquer l’onglet Modèles]**.
