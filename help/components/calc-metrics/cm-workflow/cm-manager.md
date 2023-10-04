---
description: Le Gestionnaire de mesures calculées offre plusieurs manières d’organiser les mesures, par exemple le partage, le filtrage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.
title: Gestionnaire de mesures calculées
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 17%

---

# Gestionnaire de mesures calculées

La page des mesures calculées offre plusieurs manières d’organiser les mesures, par exemple le partage, le filtrage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.

Le Gestionnaire de mesures calculées vous présente tous les filtres que vous possédez et qui ont été partagés avec vous. Les utilisateurs de niveau administrateur peuvent consulter toutes les mesures personnalisées de l’entreprise. Cet aperçu présente l’interface utilisateur et les fonctionnalités du gestionnaire de mesures calculées.

![](assets/calc-metric-manager.png)

## Accès au gestionnaire des mesures calculées

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Mesures calculées**].

## Actions disponibles dans le gestionnaire de mesures calculées

Dans le gestionnaire des mesures calculées, vous pouvez :

* [Filtrage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Marquage des mesures calculées comme favoris](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approbation des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Balisage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Partage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportez une mesure calculée dans un fichier CSV.

* [Copie de mesures calculées](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Suppression des mesures calculées

## Configuration des colonnes

Vous pouvez configurer les informations affichées pour chaque mesure calculée dans le Gestionnaire de mesures calculées en configurant les colonnes qui s’affichent.

Pour configurer les colonnes visibles dans le gestionnaire de mesures calculées :

1. Dans Customer Journey Analytics, sélectionnez la variable **[!UICONTROL Composants]** , puis sélectionnez **[!UICONTROL Mesures calculées]**.

1. Dans le gestionnaire des mesures calculées, sélectionnez la variable **Personnalisation des colonnes** icon ![Icône Personnaliser les colonnes](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le gestionnaire de mesures calculées.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Favoris | Affiche les icônes d’étoile en regard de chaque mesure calculée, ce qui vous permet de marquer les mesures calculées comme favorites. Pour plus d’informations, voir [Marquage des mesures calculées comme favoris](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Titre et description | Ces valeurs sont fournies dans le créateur de mesures calculées. Pour modifier le titre et la description, cliquez sur le lien du titre pour ouvrir le créateur de mesures calculées. |
   | Suite de rapports | Indique dans quelle suite de rapports la mesure a été enregistrée en dernier. |
   | Propriétaire | Indique qui possède la mesure personnalisée. En tant que non administrateur, vous ne pouvez consulter que les mesures que vous possédez ou celles qui ont été partagées avec vous. |
   | Balises | Affiche les balises qui ont été appliquées à la mesure, soit par vous, soit par des personnes qui ont partagé la mesure calculée avec vous. |
   | Partagé avec | Répertorie les individus ou les groupes (administrateur uniquement) ou toutes les personnes (administrateur uniquement) avec lesquelles vous avez partagé la mesure calculée. <p>Lorsqu’une mesure calculée est partagée, une icône de partage s’affiche en regard du nom de la mesure calculée.</p> |
   | Date de modification | Indique la date de la dernière modification de la mesure personnalisée. |
   | Utilisation dans | Indique le nombre de composants dans lesquels la mesure calculée est actuellement utilisée. <p>Par exemple, si la mesure calculée est utilisée dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche comme [!UICONTROL **42 composants**].</p> <p>Sélectionnez la valeur de cette colonne pour voir la répartition de l’utilisation de la mesure calculée (par exemple, [!UICONTROL **Projets (40)**], [!UICONTROL **Alertes (2)**]).</p><p>Les mesures calculées peuvent être utilisées dans l’un des types de composants suivants :</p> <ul><li>Projets</li><li>Projets planifiés</li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs et utilisatrices de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</p><p>Vous pouvez utiliser la variable [Dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) ainsi que ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre entreprise.</p><p>La variable [!UICONTROL **Utilisé dans**] ne s’affiche pas par défaut. [Configuration des colonnes](#configure-columns) pour l’afficher.</p> |
   | Dernière utilisation | Affiche la date de la dernière utilisation de la mesure calculée dans l’un des types de composants suivants : <ul><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li></ul> <p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise ou s’il doit être supprimé.</p><p>Ces informations n’incluent pas l’utilisation de l’API ou du Report Builder.</p><p>Vous pouvez utiliser la variable [Dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) ainsi que ces informations pour vous aider à effectuer le suivi et à mieux comprendre comment les composants sont utilisés dans votre entreprise. |

   {style="table-layout:auto"}
