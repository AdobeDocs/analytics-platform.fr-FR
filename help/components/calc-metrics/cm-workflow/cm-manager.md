---
description: Le Gestionnaire de mesures calculées offre plusieurs manières d’organiser les mesures, par exemple le partage, le filtrage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.
title: Gestionnaire de mesures calculées
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: 94a8589378b1aee2b6cc8371f92b3f9801ed1ec3
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 13%

---

# Gestionnaire de mesures calculées

La page des mesures calculées offre plusieurs manières d’organiser les mesures, par exemple le partage, le filtrage, le balisage, l’approbation, la copie, la suppression et le marquage en tant que favoris.

Le Gestionnaire de mesures calculées vous présente tous les filtres que vous possédez et qui ont été partagés avec vous. Les utilisateurs de niveau administrateur peuvent consulter toutes les mesures personnalisées de l’entreprise. Cet aperçu présente l’interface utilisateur et les fonctionnalités du gestionnaire de mesures calculées.

![Fenêtre de mesures calculées montrant les filtres disponibles.](assets/calc-metric-manager.png)

## Accès au gestionnaire des mesures calculées

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Composants**] > [!UICONTROL **Mesures calculées**].

## Actions disponibles dans le gestionnaire de mesures calculées

Dans le gestionnaire des mesures calculées, vous pouvez :

* [Filtrer des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Marquer des mesures calculées en tant que Favoris](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approbation des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Baliser des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Partage des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportez une mesure calculée dans un fichier CSV.

* [Copier des mesures calculées](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Suppression des mesures calculées

## Configuration des colonnes

Vous pouvez configurer les informations affichées pour chaque mesure calculée dans le Gestionnaire de mesures calculées en configurant les colonnes qui s’affichent.

Pour configurer les colonnes visibles dans le gestionnaire de mesures calculées :

1. Dans Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Composants]**, puis sélectionnez **[!UICONTROL Mesures calculées]**.

1. Dans le gestionnaire des mesures calculées, sélectionnez l’icône **Personnaliser les colonnes** ![Icône Personnaliser les colonnes](assets/customize-columns-icon.png), puis sélectionnez les colonnes à afficher dans le gestionnaire des mesures calculées.

   Les colonnes suivantes sont disponibles :

   | Titre de la colonne | Description |
   |---|---|
   | Favoris | Affiche les icônes d’étoile en regard de chaque mesure calculée, ce qui vous permet de marquer les mesures calculées comme favorites. Pour plus d’informations, voir [Marquer les mesures calculées comme favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Titre et description | Ces valeurs sont fournies dans le créateur de mesures calculées. Pour modifier le titre et la description, cliquez sur le lien du titre pour ouvrir le créateur de mesures calculées. |
   | Suite de rapports | Indique dans quelle suite de rapports la mesure a été enregistrée en dernier. |
   | Propriétaire | Indique qui possède la mesure personnalisée. En tant que non administrateur, vous ne pouvez consulter que les mesures que vous possédez ou celles qui ont été partagées avec vous. |
   | Balises | Affiche les balises qui ont été appliquées à la mesure, soit par vous, soit par des personnes qui ont partagé la mesure calculée avec vous. |
   | Partagé avec | Répertorie les individus ou les groupes (administrateur uniquement) ou toutes les personnes (administrateur uniquement) avec lesquelles vous avez partagé la mesure calculée. <p>Lorsqu’une mesure calculée est partagée, une icône de partage s’affiche en regard du nom de la mesure calculée.</p> |
   | Date de modification | Indique la date de la dernière modification de la mesure personnalisée. |
   | Utilisation dans | Indique l’endroit où les mesures calculées sont actuellement utilisées et le nombre de fois où elles sont utilisées dans chaque zone. <p>Par exemple, si la mesure calculée est utilisée dans 40 projets et 2 alertes, la valeur de cette colonne s’affiche sous la forme [!UICONTROL **42 composants**]. <p>Sélectionnez la valeur de cette colonne pour voir la répartition de l’utilisation des mesures calculées (par exemple, [!UICONTROL **Projets (40)**], [!UICONTROL **Fiches d’évaluation mobiles (2)**]). De plus, vous pouvez afficher la liste des éléments pour lesquels les mesures calculées sont utilisées. Par exemple, pour voir la liste des projets dans lesquels ils sont utilisés, sélectionnez le lien [!UICONTROL **Projets (40)**] .</p><p>Chacune des zones suivantes indique le nombre d’instances de mesures calculées utilisées dans cette zone :</p> <ul><li>[!UICONTROL **Projets**]<p>Contient les mesures calculées [créées dans le créateur de mesures calculées ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) et disponibles pour tous les projets.</p></li><li>[!UICONTROL **Composants ad hoc**]<p>Contient des mesures calculées [créées en tant que mesures calculées rapides](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) et disponibles uniquement dans un seul projet.</p></li><li>[!UICONTROL **Projets planifiés**]</li><li>[!UICONTROL **Fiches d’évaluation mobiles**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>La sélection de cette option télécharge un fichier CSV, avec les colonnes de données suivantes :</p><ul><li>Nom du Report Builder</li><li>Dernier accès</li><li>Dernier identifiant utilisateur IMS accessible</li><li>Dernier nom d’utilisateur</li></ul></li></ul><p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise, où il est utilisé et s’il doit être supprimé ou modifié.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li><li>La colonne [!UICONTROL **Utilisé dans**] ne s’affiche pas par défaut. [Configurez les colonnes](#configure-columns) pour les afficher.</li><li>Ces informations n’incluent pas l’utilisation de l’API ou du Data Warehouse.</li><li>Si cette colonne ne contient pas de données pour un composant donné mais qu’elle a une date [!UICONTROL **Dernière utilisation**], le composant peut avoir été utilisé dans une analyse sans avoir été enregistré.</li><li>Les informations d’utilisation sont disponibles à partir de septembre 2023.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation.</p> |
   | Dernière utilisation | Affiche la date de la dernière utilisation de la mesure calculée dans l’un des types de composants suivants : <ul><li>Mesures calculées</li><li>Projets</li><li>Projets planifiés</li></ul> <p>Ces informations peuvent vous aider à déterminer si un composant est utile aux utilisateurs de votre entreprise ou s’il doit être supprimé.</p><p>Tenez compte des points suivants lorsque vous affichez cette colonne :</p><ul><li>Ces informations n’incluent pas l’utilisation de l’API, du Report Builder ou du Data Warehouse.</li><li>Pour certains composants, cette colonne peut ne pas contenir de données si le composant a été utilisé pour la dernière fois avant septembre 2023.</li><li>Ces informations sont disponibles uniquement pour les administrateurs système.</li></ul><p>Vous pouvez utiliser le [dictionnaire de données](/help/components/data-dictionary/data-dictionary-overview.md) avec ces informations pour vous aider à suivre et à mieux comprendre comment les composants sont utilisés dans votre organisation. |

   {style="table-layout:auto"}
