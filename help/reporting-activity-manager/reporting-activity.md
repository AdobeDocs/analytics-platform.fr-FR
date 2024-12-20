---
title: Afficher l’activité de création de rapports dans le Gestionnaire d’activités de création de rapports
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
solution: Customer Journey Analytics
feature: Basics
exl-id: 1f5b2a42-162e-45a7-9fd4-8c1557f48bb8
role: Admin
source-git-commit: 31381cd397a821cc3ff1b3c15ae968a7260a6e9e
workflow-type: tm+mt
source-wordcount: '2016'
ht-degree: 8%

---

# Afficher l’activité de rapport {#view-reporting-activity}

Le [!UICONTROL Gestionnaire d’activités de création de rapports] permet aux administrateurs de diagnostiquer et de corriger rapidement les problèmes de capacité de création de rapports pendant les heures de pointe de la création de rapports.

Pour plus d’informations sur le gestionnaire d’activités de création de rapports, y compris les principaux avantages et les exigences en matière d’autorisation, consultez la [présentation du gestionnaire d’activités de création de rapports](/help/reporting-activity-manager/reporting-activity-overview.md).

## Pour toutes les connexions {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="Connexions"
>abstract="Ce tableau présente les connexions pour lesquelles vous disposez des droits de gestion de l’activité de création de rapports. Des informations sur chaque connexion sont disponibles dans chaque colonne du tableau."

<!-- markdownlint-enable MD034 -->


1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire d’activités de création de rapports]**.

   Une liste de vos connexions de base activées s’affiche.

   ![Activité de création de rapports affichant la file d’attente des rapports](assets/reporting-activity1.png)

1. Pour afficher le nombre total de requêtes de rapport pour toutes les connexions de votre organisation, développez [!UICONTROL **Afficher plus**] afin d’afficher le graphique [!UICONTROL **Requêtes de rapport mensuelles**].

   Vous pouvez afficher le nombre de requêtes de rapport au sein de votre organisation pour le mois en cours et le mois précédent.

   ![Activité de création de rapports affichant la file d’attente des rapports](assets/reporting-activity-monthly.png)

1. (Facultatif) Vous pouvez rechercher ou filtrer la liste des connexions :

   * Utilisez le champ de recherche pour rechercher une connexion spécifique. Commencez à saisir le nom ou l’identifiant de la connexion et la liste des mises à jour de connexion au fur et à mesure que vous tapez.

   * Sélectionnez ![Filter](/help/assets/icons/Filter.svg) pour développer la liste des options de filtre. Vous pouvez filtrer par [!UICONTROL **Favoris**] ou [!UICONTROL **État**].

     Pour marquer une connexion comme favori, sélectionnez l’icône en forme d’étoile à gauche du nom de la connexion.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Affichez les informations sur l’utilisation de chaque connexion. Les données affichées dans le tableau représentent l’activité de reporting pour la connexion au moment du dernier chargement de la page.

   Les colonnes suivantes sont disponibles :

   | Élément de lʼinterface utilisateur | Description |
   | --- | --- |
   | **[!UICONTROL Connexion]** | La connexion dont vous surveillez l’activité de création de rapports. |
   | **[!UICONTROL Vues des données]** | Affiche toutes les vues de données qui utilisent la connexion. La configuration des vues de données peut ajouter de la complexité aux requêtes de création de rapports. |
   | **[!UICONTROL Utilisation de la capacité]** | Pourcentage de la capacité de reporting de la connexion utilisée, en temps réel. <p>**Remarque** Une capacité d’utilisation de 100 % ne suggère pas nécessairement que vous devriez commencer immédiatement à annuler les demandes de création de rapports. La capacité d’utilisation de 100 % peut être saine si le temps d’attente moyen est raisonnable. D’un autre côté, une capacité d’utilisation de 100 % peut suggérer un problème si le nombre de requêtes en file d’attente augmente également.</p> |
   | **[!UICONTROL Requêtes en file d&#39;attente]** | Nombre de demandes en attente de traitement. <!-- ??? --> |
   | **[!UICONTROL Délai d’attente de file d’attente]** | Temps d’attente moyen avant que les requêtes ne commencent à être traitées. <!-- ???? --> |
   | **[!UICONTROL Statut]** | Les états possibles sont les suivants : <ul><li>[!UICONTROL **Actif**] (bleu) : les rapports ont été exécutés sur la connexion au cours des deux dernières heures. Les données affichées dans le tableau représentent la capacité de création de rapports pour la connexion au moment du dernier chargement de la page.</li><li>[!UICONTROL **Inactif**] (gris) : aucun rapport n’a jamais été exécuté sur la connexion au cours des deux dernières heures. Aucune donnée n’est donc affichée pour la connexion.</li></ul> |

   {style="table-layout:auto"}

## Pour une connexion unique

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Gestionnaire d’activités de création de rapports**].

1. Sélectionnez le titre associé de la connexion pour laquelle vous souhaitez afficher les détails.

   Les données de l&#39;activité de reporting s&#39;affichent pour la connexion que vous avez sélectionnée.

1. (Facultatif) Lors du premier chargement d’une connexion dans le Gestionnaire des activités de création de rapports, les données affichées représentent les mesures d’utilisation actuelles. Pour afficher les mesures mises à jour après le chargement initial, cliquez sur le bouton [!UICONTROL **Actualiser**] pour actualiser manuellement la page.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Utilisez les graphiques et les tableaux disponibles pour comprendre l’activité de reporting dans la connexion.

   * [Affichage des graphiques](#view-graphs)

   * [Afficher le tableau](#view-table)

### Affichage des graphiques

Les graphiques suivants sont disponibles pour vous aider à mieux comprendre l’activité en cours dans la connexion.

Si les graphiques ne sont pas visibles, cliquez sur le bouton [!UICONTROL **Afficher les graphiques**] .

#### Graphique d’utilisation {#utilization}

Le graphique Utilisation montre l’utilisation des rapports pour la connexion sélectionnée au cours des deux dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le pourcentage de capacité d’utilisation était le plus élevé pour cette minute.

* **Axe X** : capacité d’utilisation des rapports au cours des deux dernières heures.
* **Axe Y** : pourcentage de la capacité d’utilisation des rapports, par minute.

  ![graphique d’utilisation](assets/utilization-graph.png)

#### Graphique Utilisateurs distincts

Le graphique Utilisateurs distincts présente l’activité de création de rapports pour la connexion sélectionnée au cours des deux dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le nombre maximal d’utilisateurs était le plus élevé pour cette minute.

* **Axe X** : l’activité de création de rapports sur la dernière période de 2 heures.
* **Axe Y** : nombre d’utilisateurs qui ont effectué des demandes de création de rapports, par minute.

  ![Graphique Utilisateurs distincts](assets/distinct-users-graph.png)

#### Graphique des requêtes

Le graphique Requêtes indique le nombre de requêtes traitées et en file d’attente pour la connexion sélectionnée au cours des deux dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le nombre maximal de requêtes était le plus élevé pour cette minute.

* **Axe X** : nombre de requêtes traitées et en file d’attente au cours de la dernière période de 2 heures.
* **Axe Y** : nombre de requêtes traitées (en vert) et en file d’attente (en violet), par minute.

  ![Graphique Utilisateurs distincts](assets/requests-graph.png)

#### Graphique en file d’attente

Le graphique de mise en file d’attente affiche le temps d’attente moyen de la file d’attente (en secondes) pour les demandes de création de rapports pour la connexion sélectionnée au cours des deux dernières heures.

Passez la souris sur le graphique pour afficher les points dans lesquels le temps d’attente moyen maximal était le plus élevé pour cette minute.

* **Axe X** : temps d’attente moyen de la file d’attente pour les demandes de création de rapports sur la dernière période de 2 heures.
* **Axe Y** : temps d’attente moyen (en secondes).

  ![Graphique Utilisateurs distincts](assets/queueing-graph.png)

### Afficher le tableau {#view-table}

Lors de l’affichage du tableau, tenez compte des points suivants :

* Vous pouvez choisir d’afficher les données en choisissant l’un des onglets suivants en haut du tableau de données : [!UICONTROL **Request**], [!UICONTROL **User**], [!UICONTROL **Project**] ou [!UICONTROL **Application**].

* Vous pouvez rechercher ou filtrer la liste des connexions :

   * Utilisez le champ de recherche pour rechercher une connexion spécifique. Commencez à saisir le nom ou l’identifiant de la connexion et la liste des mises à jour de connexion au fur et à mesure que vous tapez.

   * Sélectionnez l’icône [!UICONTROL **Filtrer**] ![Icône Filtrer](assets/filter-icon.png) pour développer la liste des options de filtre. Vous pouvez filtrer par [!UICONTROL **État**], [!UICONTROL **Complexité**], [!UICONTROL **Application**], [!UICONTROL **Utilisateur**] ou [!UICONTROL **Projet**].

   * Vous pouvez sélectionner [!UICONTROL **Masquer les graphiques**] pour n’afficher que le tableau.

![onglets de table](assets/report-activity-tabs.png)

#### Afficher les données par requête

Lorsque vous sélectionnez l’onglet [!UICONTROL **Requête**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **ID de demande**] | Identifiant unique pouvant être utilisé à des fins de dépannage. Pour copier l’ID, sélectionnez la requête, puis sélectionnez l’option [!UICONTROL **Copier les ID de requête**]. |
| [!UICONTROL **Durée d’exécution**] | Durée d’exécution de la requête. |
| [!UICONTROL **Heure de début**] | Lorsque le traitement de la demande a commencé (en fonction de l’heure locale de l’administrateur). |
| [!UICONTROL **Temps d’attente**] | Durée pendant laquelle la requête a été en attente avant d’être traitée. Cette valeur est généralement égale à &quot;0&quot; lorsque la capacité est suffisante. |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur du créateur : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels API de l’API 2.0</li><li>Alertes<li>Export du tableau complet</li><li>Partager avec n’importe qui lien</li><li>Analyse guidée</li><li>Toute autre application qui interroge le moteur de reporting Analytics</li></li></ul><p>**Remarque :** Si la valeur de cette colonne est [!UICONTROL **Inconnu**], cela signifie que les métadonnées de requête ne sont pas disponibles pour l’utilisateur.</p> |
| [!UICONTROL **Utilisateur**] | L’utilisateur qui a initié la requête. <p>**Remarque :** Si la valeur de cette colonne est [!UICONTROL **Inconnu**], cela signifie que les métadonnées de requête ne sont pas disponibles pour l’utilisateur.</p> |
| [!UICONTROL **Projet**] | Noms de projet Workspace enregistrés, identifiants de rapport d’API, etc. (Les métadonnées peuvent varier d’une application à l’autre.)<p>**Remarque :** Si la valeur de cette colonne est [!UICONTROL **Inconnu**], cela signifie que le projet n’a pas été enregistré ou que les métadonnées de requête ne sont pas disponibles pour l’utilisateur.</p> |
| [!UICONTROL **Statut**] | Indicateurs de statut : <ul><li>**En cours d’exécution** : la demande est en cours de traitement.</li><li>**En attente** : la demande est en attente de traitement.</li></ul> |
| [!UICONTROL **Complexité**] | Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête. <p>Valeurs possibles :</p> <ul><li>[!UICONTROL **Low**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **High**]</li></ul>Cette valeur est influencée par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles**]</li><li>[!UICONTROL **Colonnes**]</li><li>[!UICONTROL **Segments**]</li></ul> |
| [!UICONTROL **Limites mensuelles**] | Nombre de mois inclus dans une requête. Plus de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Colonnes**] | Nombre de mesures et de ventilations dans la requête. Plus de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Segments**] | Le nombre de segments appliqués à la requête. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Affichage des données par utilisateur

Lorsque vous sélectionnez l’onglet [!UICONTROL **User**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Utilisateur**] | L’utilisateur qui a initié la requête. Si la valeur de cette colonne est [!UICONTROL **Non reconnu**], cela signifie que l’utilisateur se trouve dans une société de connexion dans laquelle vous ne disposez pas d’autorisations d’administration. |
| [!UICONTROL **Nombre de requêtes**] | Nombre de requêtes initiées par l’utilisateur. |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’utilisateur. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur du créateur : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels API de l’API 2.0</li><li>Alertes<li>Export du tableau complet</li><li>Partager avec n’importe qui lien</li><li>Analyse guidée</li><li>Toute autre application qui interroge le moteur de reporting Analytics</li></li></ul> |
| [!UICONTROL **Complexité moyenne**] | La complexité moyenne des requêtes initiées par l’utilisateur. <p>Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites moy.**]</li><li>[!UICONTROL **Nombre moyen de colonnes**]</li><li>[!UICONTROL **Nombre moyen de segments**]</li></ul> |
| [!UICONTROL **Limites moy.**] | Nombre moyen de mois inclus dans les requêtes. Plus de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Nombre moyen de colonnes**] | Nombre moyen de mesures et de ventilations dans les requêtes incluses. Plus de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Nombre moyen de segments**] | Nombre moyen de segments appliqués aux requêtes incluses. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Affichage des données par projet

Lorsque vous sélectionnez l’onglet [!UICONTROL **Projet**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Projet**] | Projet sur lequel les demandes ont été initiées. |
| [!UICONTROL **Nombre de requêtes**] | Nombre de requêtes associées au projet. |
| [!UICONTROL **Nombre d&#39;utilisateurs**] | Nombre d’utilisateurs associés au projet. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interface utilisateur du créateur : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels API de l’API 2.0</li><li>Alertes<li>Export du tableau complet</li><li>Partager avec n’importe qui lien</li><li>Analyse guidée</li><li>Toute autre application qui interroge le moteur de reporting Analytics</li></li></ul> |
| [!UICONTROL **Complexité moyenne**] | La complexité moyenne des demandes incluses dans le projet. <p>Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites moy.**]</li><li>[!UICONTROL **Nombre moyen de colonnes**]</li><li>[!UICONTROL **Nombre moyen de segments**]</li></ul> |
| [!UICONTROL **Limites moy.**] | Nombre moyen de mois inclus dans les requêtes. Plus de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Nombre moyen de colonnes**] | Nombre moyen de mesures et de ventilations dans les requêtes incluses. Plus de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Nombre moyen de segments**] | Nombre moyen de segments appliqués aux requêtes incluses. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

#### Affichage des données par application

Lorsque vous sélectionnez l’onglet [!UICONTROL **Application**] , les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Application**] | L’application dans laquelle les requêtes ont été initiées. |
| [!UICONTROL **Nombre de requêtes**] | Nombre de requêtes associées à l’application. |
| [!UICONTROL **Nombre d&#39;utilisateurs**] | Nombre d’utilisateurs associés à l’application. <!--???--> |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’application. <!--???--> |
| [!UICONTROL **Complexité moyenne**] | La complexité moyenne des demandes associées à l’application. <p>Toutes les demandes ne nécessitent pas le même temps de traitement. La complexité de la requête peut vous aider à obtenir une idée générale du temps nécessaire au traitement de la requête.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites moy.**]</li><li>[!UICONTROL **Nombre moyen de colonnes**]</li><li>[!UICONTROL **Nombre moyen de segments**]</li></ul> |
| [!UICONTROL **Limites moy.**] | Nombre moyen de mois inclus dans les requêtes. Plus de limites de mois ajoute à la complexité de la requête. |
| [!UICONTROL **Nombre moyen de colonnes**] | Nombre moyen de mesures et de ventilations dans les requêtes incluses. Plus de colonnes ajoute à la complexité de la requête. |
| [!UICONTROL **Nombre moyen de segments**] | Nombre moyen de segments appliqués aux requêtes incluses. Plus de segments ajoute à la complexité de la requête. |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
