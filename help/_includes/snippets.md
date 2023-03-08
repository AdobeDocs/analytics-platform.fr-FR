---
source-git-commit: 02ff498456fb3d770b9e3c73c3847ac5a55cd705
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 70%

---
# Extraits

## Phase de tests limités de publication {#release-limited-testing}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).

## Section Phase de tests limités de publication {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cette section se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).

## Critères de filtre du dictionnaire de données {#dd-filter-criteria}

1. (Facultatif) Sélectionnez l’icône **Filtrer** ![icône du filtre du dictionnaire de données](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png), puis sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme approuvés par l’administration. |
   | [!UICONTROL **Favoris**] | Afficher uniquement les composants qui se trouvent dans votre liste de Favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, voir [Présentation des composants](/help/components/overview.md). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des dimensions. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Filtres**] | Afficher uniquement les composants qui sont des filtres. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). <!--this is Filters in CJA--> |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Tout afficher**] | Afficher tous les composants. Cette option est réservée à l’administration. |
   | [!UICONTROL **Non approuvé**] | Afficher uniquement les composants qui ne sont pas encore marqués comme Approuvés par un administrateur. En tant qu’administrateur, cela s’avère utile pour identifier les composants qui nécessitent votre révision et votre approbation. Cette option est réservée à l’administration. |
   | [!UICONTROL **Description manquante**] | Afficher uniquement les composants qui n’ont pas encore de description dans le champ de description. Cette option est réservée à l’administration. |
   | [!UICONTROL **Afficher les doublons**] | Afficher uniquement les composants qui ont le même libellé ou la même description qu’un autre composant de la suite de rapports sélectionnée. Cela inclut les composants que vous créez ainsi que ceux fournis par Adobe. Les libellés ou descriptions doivent correspondre exactement pour apparaître comme des doublons. Cette option est réservée à l’administration. |
   | [!UICONTROL **Aucune donnée récente**] | Afficher uniquement les composants qui n’ont collecté aucune donnée au cours des 90 derniers jours. Cette option est réservée à l’administration. |
   | [!UICONTROL **Créé par Adobe**] <!-- I don't see this option--> | Afficher uniquement les composants créés par Adobe. Les composants créés par l’administration ou une autre personne de votre organisation ne s’affichent pas. |

   {style="table-layout:auto"}

## Informations sur le composant Dictionnaire de données {#dd-component-information}

| Option | Fonction |
|---------|----------|
| [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administration.</p><p>Les administrateurs voient une option pour [!UICONTROL **Ne pas approuver**]. La sélection de cette option marque le composant comme &quot;Non approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Non approuvé**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administrateur.</p><p>Les administrateurs voient une option pour [!UICONTROL **Approuver**]. La sélection de cette option marque le composant comme &quot;Approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administration Analytics, comme décrit dans la section [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md)). |
| [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants sont affichés sur les 5 types de composants Principaux : Mesure, mesure calculée, Dimension, filtre et période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous êtes autorisé à consulter s’affichent.</p><p>Les administrateurs voient les options pour [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Ces options permettent aux administrateurs de traiter les composants visibles par les utilisateurs dans cette section.</p> |
| [!UICONTROL **Similaire à**] | <p>Affiche les composants dotés de libellés similaires au composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants sont affichés sur les 5 types de composants Principaux : Mesure, mesure calculée, Dimension, filtre et période.</p><p>Seuls les composants que vous êtes autorisé à consulter s’affichent.</p><p>Tous les composants en double de votre suite de rapports s’affichent à l’écran. L’administration Analytics doit identifier et supprimer tous les composants en double, comme décrit dans la section [Surveiller l’intégrité du dictionnaire de données](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Les administrateurs voient les options pour [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Ces options permettent aux administrateurs de traiter les composants visibles par les utilisateurs dans cette section.</p> |
| [!UICONTROL **Balises**] | Affiche toutes les balises associées au composant. L’administration peut ajouter des balises lors de la modification du composant. |
| [!UICONTROL **Type de composant**] | Répertorie le type de composant qu’il est, qu’il s’agisse d’une Dimension, d’une mesure, d’un filtre ou d’une plage de dates. |
| [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur ou de l’utilisatrice ayant créé le composant. |
| [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
| [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lors de l’affichage des options Filtres, Mesures, Mesures calculées et Périodes. |

{style="table-layout:auto"}