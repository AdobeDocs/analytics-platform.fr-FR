---
description: Les administrateurs et administratrices sont chargés de surveiller l’intégrité du dictionnaire de données. Cela inclut le fait de savoir si les composants collectent des données, sont approuvés, contiennent des descriptions et sont exempts de doublons.
title: Surveiller l’intégrité du dictionnaire de données
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 7c679fcbf52d2a5832d16bf138bd197f11f4ceb7
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 87%

---

# Surveiller l’intégrité du dictionnaire de données {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Dictionnaire de données"
>abstract="Lorsque cette option est sélectionnée, le composant principal est partagé avec toutes les personnes ayant accès aux composants en double (les propriétaires et les personnes avec lesquelles les composants sont partagés). Ces personnes peuvent ensuite sélectionner le composant principal dans la liste des composants pour les projets futurs. Cependant, elles ne peuvent pas modifier le composant, même si elles étaient propriétaires d’un composant en double qui a été consolidé. <br/>Cette option est disponible uniquement lorsque le composant principal est un segment, une mesure calculée ou une période. Les mesures et dimensions sont toujours disponibles pour l’ensemble des utilisateurs et utilisatrices."
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="Partager le composant principal"
>abstract="Lorsque cette option est sélectionnée, le composant principal est partagé avec toutes les personnes ayant accès aux composants en double (les propriétaires et les personnes avec lesquelles les composants sont partagés). Ces personnes peuvent ensuite sélectionner le composant principal dans la liste des composants pour les projets futurs. Cependant, elles ne peuvent pas modifier le composant, même si elles étaient propriétaires d’un composant en double qui a été consolidé."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="Supprimer les doublons remplacés"
>abstract="Lorsque cette option est sélectionnée, les doublons consolidés ne sont plus disponibles. Désélectionnez cette option si vous souhaitez que les doublons restent disponibles."

<!-- markdownlint-enable MD034 -->

Les administrateurs et administratrices de Customer Journey Analytics sont chargés de la maintenance d’un dictionnaire de données intègre.

## Caractéristiques d’un dictionnaire de données intègre

Dans un dictionnaire de données intègre, tous les composants :

* sont utilisés et collectent des données ;

* contiennent des descriptions utiles pour que les utilisateurs et utilisatrices sachent comment les utiliser au mieux ;

* sont exempts de doublons superflus ;

* sont approuvés par l’administrateur ou l’administratrice.

## Vérifier l’intégrité de votre dictionnaire de données

Pour identifier les problèmes d’intégrité dans votre dictionnaire de données :

1. Ouvrez un projet Analysis Workspace.

1. Sélectionnez l’icône du dictionnaire de données sur le côté gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![Vue de l’administrateur du dictionnaire de données affichant l’intégrité du dictionnaire](assets/data-dictionary-admin.png)

1. Assurez-vous que la vue de données appropriée est sélectionnée dans le menu déroulant.

1. Sur l’onglet [!UICONTROL **Intégrité du dictionnaire**], sélectionnez [!UICONTROL **Affichage**] en regard de l’une des options suivantes :

   * [!UICONTROL **composants sans description**],

   * [!UICONTROL **composants avec doublons**],

   * [!UICONTROL **composants sans données connectées**].

   Selon ce que vous sélectionnez, le segment approprié est appliqué au dictionnaire de données et seuls les composants appropriés sont affichés.

1. Modifiez l’un des composants pour améliorer l’intégrité du dictionnaire de données. Pour plus d’informations sur la modification d’un composant dans le dictionnaire de données, voir [Modifier les entrées de composant dans le dictionnaire de données](/help/components/data-dictionary/edit-entries-data-dictionary.md).
