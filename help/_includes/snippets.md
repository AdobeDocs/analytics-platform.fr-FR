---
source-git-commit: 486cd26bfacbae0072e14ec078ceca66909ac0ec
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 63%

---
# Extraits

## Phase de tests limités de publication {#release-limited-testing}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).

## Section Phase de tests limités de publication {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cette section se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités de Customer Journey Analytics](/help/release-notes/releases.md).

## Sélectionner un package {#select-package}

>[!NOTE]
>
>Vous devez disposer de la variable **Sélectionner** afin d’utiliser les fonctionnalités décrites dans cette section. Contactez votre administrateur si vous ne savez pas quel package de Customer Journey Analytics vous disposez.


## Critères de filtre du dictionnaire de données {#dd-filter-criteria}

1. (Facultatif) Sélectionnez l’icône **Filtrer** ![icône du filtre du dictionnaire de données](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), puis sélectionnez l’une des options de filtre suivantes pour filtrer la liste des composants :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Approuvés**] | Afficher uniquement les composants marqués comme approuvés par l’administration. |
   | [!UICONTROL **Favoris**] | Affichez uniquement les composants figurant dans votre liste de favoris. Pour plus d’informations sur l’ajout de composants à votre liste de favoris, consultez la section [Présentation des composants](/help/components/overview.md). |
   | [!UICONTROL **Dimensions**] | Afficher uniquement les composants qui sont des dimensions. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Mesures**] | Afficher uniquement les composants qui sont des mesures. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Filtres**] | Afficher uniquement les composants qui sont des filtres. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Périodes**] | Afficher uniquement les composants qui sont des périodes. (Cette option est également disponible sous l’onglet [!UICONTROL **Filtres rapides**] lorsque vous accédez au dictionnaire de données pour la première fois). |
   | [!UICONTROL **Tout afficher**] | Permet d’afficher tous les composants. Cette option est réservée à l’administration. |
   | [!UICONTROL **Non approuvé**] | Permet de n’afficher que les composants qui n’ont pas encore été marqués comme approuvés par l’administration. Cette option est utile pour l’administration pour identifier les composants qui doivent être examinés et approuvés. Cette option est réservée à l’administration. |
   | [!UICONTROL **Description manquante**] | Afficher uniquement les composants qui n’ont pas encore de description dans le champ de description. Cette option est réservée à l’administration. |
   | [!UICONTROL **Afficher les doublons**] | Afficher uniquement les composants portant le même nom ou la même description qu’un autre composant dans la vue de données sélectionnée. Cela inclut les composants que vous créez ainsi que ceux fournis par Adobe. Les noms ou descriptions doivent correspondre exactement pour s’afficher en tant que doublons. Cette option est réservée à l’administration. |
   | [!UICONTROL **Aucune donnée récente**] | Afficher uniquement les composants qui n’ont collecté aucune donnée au cours des 90 derniers jours. Cette option est réservée à l’administration. |
   | [!UICONTROL **Créé par Adobe**] <!-- I don't see this option--> | Afficher uniquement les composants créés par Adobe. Les composants créés par l’administration ou une autre personne de votre organisation ne s’affichent pas. |

   {style="table-layout:auto"}

## Informations sur le composant Dictionnaire de données {#dd-component-information}

| Option | Fonction |
|---------|----------|
| [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administration.</p><p>Les administrateurs voient une option pour [!UICONTROL **Ne pas approuver**]. La sélection de cette option marque le composant comme &quot;Non approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Non approuvé**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administration.</p><p>Un bouton dédié permet à l’administration d’[!UICONTROL **Approuver**] le composant. Celui-ci est alors marqué comme « Approuvé » pour les utilisateurs et utilisatrices.</p> |
| [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administration Analytics, comme décrit dans la section [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md)). |
| [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants sont affichés dans les 5 types de composants principaux : Mesure, Mesure calculée, Dimension, Filtre et Période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous êtes en droit de consulter s’affichent.</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Avant de traiter les composants que les utilisateurs voient, appliquez d’abord la variable **Tout afficher** filtre pour vous assurer que vous voyez des composants qui n’ont pas été partagés avec vous et qui peuvent avoir été ajoutés par un autre administrateur.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similaire à**] | <p>Permet d’afficher les composants dotés de noms similaires au composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants sont affichés dans les 5 types de composants principaux : Mesure, Mesure calculée, Dimension, Filtre et Période.</p><p>Seuls les composants que vous êtes en droit de consulter s’affichent.</p><p>Tous les composants en double dans votre vue de données s’affichent ici. L’administration d’Analytics doit identifier et supprimer tous les composants en double, comme décrit dans la section [Surveiller l’intégrité du dictionnaire de données](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Avant de traiter les composants que les utilisateurs voient, appliquez d’abord la variable **Tout afficher** filtre pour vous assurer que vous voyez des composants qui n’ont pas été partagés avec vous et qui peuvent avoir été ajoutés par un autre administrateur.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Remarque :** actuellement, la section **Similaire à** comprend uniquement les composants que vous créez, et non ceux fournis par Adobe. Les composants fournis par Adobe seront ajoutés dans une version ultérieure.</p> |
| [!UICONTROL **Balises**] | Affiche toutes les balises associées au composant. L’administration peut ajouter des balises lors de la modification du composant. |
| [!UICONTROL **Type de composant**] | Répertorie le type de composant qu’il est, qu’il s’agisse d’une Dimension, d’une mesure, d’un filtre ou d’une plage de dates. |
| [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur ou de l’utilisatrice ayant créé le composant. |
| [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
| [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lors de l’affichage des options Filtres, Mesures, Mesures calculées et Périodes. |

{style="table-layout:auto"}

## Options de tri des composants {#components-sort-options}

| Option | Fonction |
|---------|----------|
| [!UICONTROL **Recommandé**] | Trie les composants avec ceux qui sont recommandés en haut de la liste. Les composants utilisés le plus souvent et le plus récemment par vous ou par d’autres membres de votre organisation sont répertoriés plus haut dans la liste. |
| [!UICONTROL **Alphabétique**] | Trie les composants par ordre alphabétique. |
| [!UICONTROL **Catégorique**] | Trie les composants en fonction du type de composant (dimension, mesure, filtre, période). |

{style="table-layout:auto"}

## Comparaison de temps {#apply-time-comparison}

Vous pouvez comparer la période actuelle à une période précédente. Si vous sélectionnez une option dans ce menu, chaque point de données reçoit une contrepartie pointillée de couleur similaire. Cette contrepartie représente la même mesure dans la période précédente sélectionnée. Cette option double le nombre d’éléments du graphique et des lignes du tableau.

Les options de comparaison de temps disponibles comprennent la période précédente, 13 semaines précédentes, 52 semaines précédentes et une période personnalisée. Si vous sélectionnez Période personnalisée, d’autres options s’affichent pour vous permettre de sélectionner le nombre et la granularité. Si vous sélectionnez Aucun, la comparaison de dates est supprimée.
