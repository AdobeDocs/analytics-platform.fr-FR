---
title: Afficher l’activité de rapports dans le gestionnaire des activités de rapport
description: Découvrez comment utiliser le gestionnaire des activités de rapport pour diagnostiquer et corriger les problèmes de capacité pendant les heures de pointe de la création de rapports.
solution: Customer Journey Analytics
feature: Basics
exl-id: 1f5b2a42-162e-45a7-9fd4-8c1557f48bb8
role: Admin
source-git-commit: a530738bb02888d637e5ff4edaa1aa2535a9034c
workflow-type: ht
source-wordcount: '2043'
ht-degree: 100%

---

# Afficher l’activité de rapport {#view-reporting-activity}

Le [!UICONTROL gestionnaire des activités de rapport] permet aux administrateurs et administratrices de diagnostiquer et de résoudre rapidement les problèmes de capacité de rapport pendant les heures de pointe de la création de rapports.

Pour plus d’informations sur le gestionnaire des activités de rapport, y compris les principaux avantages et les exigences d’autorisation, consultez [Vue d’ensemble du gestionnaire des activités de rapport](/help/reporting-activity-manager/reporting-activity-overview.md).

## Pour toutes les connexions {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="Connexions"
>abstract="Ce tableau présente les connexions pour lesquelles vous disposez des droits de gestion de l’activité de création de rapports. Des informations sur chaque connexion sont disponibles dans chaque colonne du tableau."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_reportingactivitymanager_connections"
>title="Connexions"
>abstract="Ce tableau présente les connexions pour lesquelles vous disposez des droits de gestion de l’activité de création de rapports. Des informations sur chaque connexion sont disponibles dans chaque colonne du tableau."

<!-- markdownlint-enable MD034 -->


1. Dans Customer Journey Analytics, accédez à **[!UICONTROL Outils]** > **[!UICONTROL Gestionnaire des activités de rapport]**.

   Une liste de vos connexions de base activées s’affiche.

   ![Activité de rapport présentant la file d’attente des rapports](assets/reporting-activity1.png)

1. Pour afficher le nombre total de demandes de rapport pour toutes les connexions de votre organisation, développez [!UICONTROL **Afficher plus**] pour afficher le graphique [!UICONTROL **Demandes de rapport mensuelles**].

   Vous pouvez afficher le nombre de demandes de rapports au sein de votre organisation pour le mois en cours et le mois précédent.

   ![Activité de rapport présentant la file d’attente des rapports](assets/reporting-activity-monthly.png)

1. (Facultatif) Vous pouvez rechercher ou filtrer la liste des connexions :

   * Utilisez le champ de recherche pour rechercher une connexion particulière. Commencez à saisir le nom ou l’identifiant de la connexion et la liste des connexions est mise à jour au fur et à mesure que vous tapez.

   * Sélectionnez ![Filtrer](/help/assets/icons/Filter.svg) pour développer la liste des options de filtre. Vous pouvez filtrer par [!UICONTROL **Favoris**] ou [!UICONTROL **Statut**].

     Pour marquer une connexion comme faisant partie de vos favoris, sélectionnez l’icône en forme d’étoile à gauche du nom de la connexion.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Affichez les informations d’utilisation de chaque connexion. Les données affichées dans le tableau représentent l’activité de création de rapports pour la connexion au moment du dernier chargement de la page.

   Les colonnes suivantes sont disponibles :

   | Élément de lʼinterface utilisateur | Description |
   | --- | --- |
   | **[!UICONTROL Connexion]** | Connexion dont vous surveillez l’activité de création de rapports. |
   | **[!UICONTROL Vues des données]** | Affiche toutes les vues de données qui utilisent la connexion. La configuration des vues de données peut ajouter de la complexité aux demandes de création de rapports. |
   | **[!UICONTROL Utilisation des capacités]** | Pourcentage de la capacité de création de rapports de la connexion qui est utilisé, en temps réel. <p>**Note** : une capacité d’utilisation de 100 % ne signifie pas nécessairement que vous devez commencer immédiatement à annuler les demandes de création de rapports. Une capacité d’utilisation de 100 % peut être saine si le temps d’attente moyen est raisonnable. D’un autre côté, une capacité d’utilisation de 100 % peut suggérer un problème si le nombre de demandes en file d’attente augmente également.</p> |
   | **[!UICONTROL Demandes en attente]** | Nombre de demandes en attente de traitement. <!-- ??? --> |
   | **[!UICONTROL Durée de la file d’attente]** | Temps d’attente moyen avant que les demandes ne commencent à être traitées. <!-- ???? --> |
   | **[!UICONTROL Statut]** | Les statuts possibles sont les suivants : <ul><li>[!UICONTROL **Actif**] (bleu) : des rapports ont été exécutés sur la connexion au cours des 2 dernières heures. Les données affichées dans le tableau représentent la capacité de création de rapports pour la connexion au moment du dernier chargement de la page.</li><li>[!UICONTROL **Inactif**] (gris) : aucun rapport n’a été exécuté sur la connexion au cours des 2 dernières heures. Aucune donnée n’est donc affichée pour la connexion.</li></ul> |

   {style="table-layout:auto"}

## Pour une seule connexion

1. Dans Customer Journey Analytics, sélectionnez [!UICONTROL **Outils**] > [!UICONTROL **Gestionnaire des activités de rapport**].

1. Sélectionnez le titre lié de la connexion pour laquelle vous souhaitez afficher les détails.

   Les données des activités de rapport s’affichent pour la connexion que vous avez sélectionnée.

1. (Facultatif) Lorsqu’une connexion se charge pour la première fois dans le gestionnaire des activités de rapport, les données affichées représentent les mesures d’utilisation actuelles. Pour afficher les mesures mises à jour après le chargement initial, sélectionnez le bouton [!UICONTROL **Actualiser**] pour actualiser manuellement la page.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Utilisez les graphiques et le tableau disponibles pour comprendre l’activité de rapport dans la connexion.

   * [Afficher les graphiques](#view-graphs)

   * [Afficher le tableau](#view-table)

### Afficher les graphiques

Les graphiques suivants sont disponibles pour vous aider à mieux comprendre l’activité qui se produit dans la connexion.

Si les graphiques ne sont pas visibles, sélectionnez le bouton [!UICONTROL **Afficher les graphiques**].

#### Graphique d’utilisation {#utilization}

Le graphique d’utilisation montre l’activité de création de rapports pour la connexion sélectionnée au cours des 2 dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le pourcentage de capacité d’utilisation a été le plus élevé pendant cette minute.

* **Axe X** : capacité d’utilisation des rapports au cours des 2 dernières heures.
* **Axe Y** : pourcentage de capacité d’utilisation des rapports, par minute.

  ![Graphique d’utilisation](assets/utilization-graph.png)

#### Graphique Utilisateurs et utilisatrices distincts

Le graphique Utilisateurs et utilisatrices distincts montre l’activité de création de rapports pour la connexion sélectionnée au cours des 2 dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le nombre maximal d’utilisateurs et d’utilisatrices a été le plus élevé pendant cette minute.

* **Axe X** : activité de création de rapports sur la période des 2 dernières heures.
* **Axe Y** : nombre d’utilisateurs et d’utilisatrices qui ont envoyé des demandes de création de rapports, par minute.

  ![Graphique Utilisateurs et utilisatrices distincts](assets/distinct-users-graph.png)

#### Graphique Demandes

Le graphique Demandes indique le nombre de demandes traitées et mises en file d’attente pour la connexion sélectionnée au cours des 2 dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le nombre maximal de demandes a été le plus élevé pendant cette minute.

* **Axe X** : nombre de demandes traitées et mises en file d’attente au cours de la période des 2 dernières heures.
* **Axe Y** : nombre de demandes traitées (en vert) et de demandes mises en file d’attente (en violet), par minute.

  ![Graphique Utilisateurs et utilisatrices distincts](assets/requests-graph.png)

#### Graphique Mise en file d’attente

Le graphique Mise en file d’attente indique le temps d’attente moyen de la file d’attente (en secondes) pour les demandes de création de rapports pour la connexion sélectionnée au cours des 2 dernières heures.

Passez la souris sur le graphique pour afficher les points dans le temps où le temps d’attente moyen maximal a été le plus élevé pendant cette minute.

* **Axe X** : temps d’attente moyen des demandes de création de rapports dans la file d’attente au cours de la période des 2 dernières heures.
* **Axe Y** : temps d’attente moyen (en secondes).

  ![Graphique Utilisateurs et utilisatrices distincts](assets/queueing-graph.png)

### Afficher le tableau {#view-table}

Lorsque vous affichez le tableau, veuillez tenir compte des points suivants :

* Vous pouvez choisir d’afficher les données en choisissant l’un des onglets suivants en haut du tableau de données : [!UICONTROL **Demande**], [!UICONTROL **Utilisateur ou utilisatrice**], [!UICONTROL **Projet**] ou [!UICONTROL **Application**].

* Vous pouvez rechercher ou filtrer la liste des connexions :

   * Utilisez le champ de recherche pour rechercher une connexion particulière. Commencez à saisir le nom ou l’identifiant de la connexion et la liste des connexions est mise à jour au fur et à mesure que vous tapez.

   * Sélectionnez l’icône [!UICONTROL **Filtre**] ![Icône Filtre](assets/filter-icon.png) pour développer la liste des options de filtre. Vous pouvez filtrer par [!UICONTROL **Statut**], [!UICONTROL **Complexité**], [!UICONTROL **Application**], [!UICONTROL **Utilisateur ou utilisatrice**] ou [!UICONTROL **Projet**].

   * Vous pouvez sélectionner [!UICONTROL **Masquer les graphiques**] pour afficher uniquement le tableau.

![Onglets de tableau](assets/report-activity-tabs.png)

#### Afficher les données par demande

Lorsque vous sélectionnez l’onglet [!UICONTROL **Demande**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **ID de demande**] | Identifiant unique pouvant être utilisé à des fins de dépannage. Pour copier l’ID, sélectionnez la demande, puis sélectionnez l’option [!UICONTROL **Copier les ID de la demande**]. |
| [!UICONTROL **Durée d’exécution**] | Durée d’exécution de la requête. |
| [!UICONTROL **Heure de début**] | Heure à laquelle le traitement de la demande a commencé (en fonction de l’heure locale de l’administrateur ou de l’administratrice). |
| [!UICONTROL **Temps d’attente**] | Durée pendant laquelle la demande a été en attente avant d’être traitée. Cette valeur est généralement à « 0 » lorsque la capacité est suffisante. |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interfaces d’utilisation des créateurs : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels API à partir de la version d’API 2.0</li><li>Alertes<li>Export du tableau complet</li><li>Liens de partage avec tout le monde</li><li>Analyse guidée</li><li>Toute autre application interrogeant le moteur de création de rapports Analytics</li></li></ul><p>**Note :** si la valeur de cette colonne est [!UICONTROL **Inconnu**], cela signifie que les métadonnées de la demande ne sont pas disponibles pour l’utilisateur ou l’utilisatrice.</p> |
| [!UICONTROL **Utilisateur ou utilisatrice**] | Personne qui a lancé la demande. <p>**Note :** si la valeur de cette colonne est [!UICONTROL **Inconnu**], cela signifie que les métadonnées de la requête ne sont pas disponibles pour l’utilisateur ou l’utilisatrice.</p> |
| [!UICONTROL **Projet**] | Noms de projets Workspace enregistrés, ID de rapports d’API, etc. (Les métadonnées peuvent varier d’une application à l’autre.)<p>**Note :** si la valeur de cette colonne est [!UICONTROL **Inconnu**], cela signifie que le projet n’a pas été enregistré ou que les métadonnées de la requête ne sont pas disponibles pour l’utilisateur ou l’utilisatrice.</p> |
| [!UICONTROL **Statut**] | Indicateurs de statut : <ul><li>**En cours d’exécution** : la demande est en cours de traitement.</li><li>**En attente** : la demande est en attente de traitement.</li></ul> |
| [!UICONTROL **Complexité**] | Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande. <p>Valeurs possibles :</p> <ul><li>[!UICONTROL **Faible**]</li><li>[!UICONTROL **Moyen**]</li><li>[!UICONTROL **Élevé**]</li></ul>Cette valeur est influencée par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles**]</li><li>[!UICONTROL **Colonnes**]</li><li>[!UICONTROL **Segments**]</li></ul> |
| [!UICONTROL **Limites mensuelles**] | Nombre de mois inclus dans une demande. Une limite mensuelle importante ajoute à la complexité de la demande. |
| [!UICONTROL **Colonnes**] | Nombre de mesures et de répartitions dans la demande. Un nombre plus important de colonnes ajoute à la complexité de la demande. |
| [!UICONTROL **Segments**] | Nombre de segments appliqués à la demande. Un nombre important de segments ajoute à la complexité de la demande. |

{style="table-layout:auto"}

#### Afficher les données par utilisateur ou utilisatrice

Lorsque vous sélectionnez l’onglet [!UICONTROL **Utilisateur ou utilisatrice**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Utilisateur ou utilisatrice**] | Personne qui a lancé la demande. Si la valeur de cette colonne est [!UICONTROL **Non reconnu**], cela signifie que l’utilisateur ou l’utilisatrice se trouve dans une société de connexion pour laquelle vous ne disposez pas d’autorisations administratives. |
| [!UICONTROL **Nombre de demandes**] | Nombre de demandes initiées par l’utilisateur ou l’utilisatrice. |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’utilisateur ou à l’utilisatrice. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interfaces d’utilisation des créateurs : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels API à partir de la version d’API 2.0</li><li>Alertes<li>Export du tableau complet</li><li>Liens de partage avec tout le monde</li><li>Analyse guidée</li><li>Toute autre application interrogeant le moteur de création de rapports Analytics</li></li></ul> |
| [!UICONTROL **Complexité moyenne**] | Complexité moyenne des demandes initiées par l’utilisateur ou l’utilisatrice. <p>Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites mensuelles moyennes**]</li><li>[!UICONTROL **Colonnes moyennes**]</li><li>[!UICONTROL **Segments moyens**]</li></ul> |
| [!UICONTROL **Limites mensuelles moyennes**] | Nombre moyen de mois inclus dans les demandes. Une limite mensuelle importante ajoute à la complexité de la demande. |
| [!UICONTROL **Colonnes moyennes**] | Nombre moyen de mesures et de répartitions dans les demandes incluses. Un nombre plus important de colonnes ajoute à la complexité de la demande. |
| [!UICONTROL **Segments moyens**] | Nombre moyen de segments appliqués aux demandes incluses. Un nombre important de segments ajoute à la complexité de la demande. |

{style="table-layout:auto"}

#### Afficher les données par projet

Lorsque vous sélectionnez l’onglet [!UICONTROL **Projet**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Projet**] | Projet dans lequel les demandes ont été initiées. |
| [!UICONTROL **Nombre de demandes**] | Nombre de demandes associées au projet. |
| [!UICONTROL **Nombre d’utilisateurs et d’utilisatrices**] | Nombre d’utilisateurs et d’utilisatrices associés au projet. <!-- ??? --> |
| [!UICONTROL **Application**] | Les applications prises en charge par le [!UICONTROL Gestionnaire des activités de rapport] sont les suivantes : <ul><li>Interface utilisateur d’Analysis Workspace</li><li>Projets planifiés d’espace de travail</li><li>Report Builder</li><li>Interfaces d’utilisation des créateurs : Segment, Mesures calculées, Annotations, Audiences, etc.</li><li>Appels API à partir de la version d’API 2.0</li><li>Alertes<li>Export du tableau complet</li><li>Liens de partage avec tout le monde</li><li>Analyse guidée</li><li>Toute autre application interrogeant le moteur de création de rapports Analytics</li></li></ul> |
| [!UICONTROL **Complexité moyenne**] | Complexité moyenne des demandes incluses dans le projet. <p>Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p><ul><li>[!UICONTROL **Limites mensuelles moyennes**]</li><li>[!UICONTROL **Colonnes moyennes**]</li><li>[!UICONTROL **Segments moyens**]</li></ul> |
| [!UICONTROL **Limites mensuelles moyennes**] | Nombre moyen de mois inclus dans les demandes. Une limite mensuelle importante ajoute à la complexité de la demande. |
| [!UICONTROL **Colonnes moyennes**] | Nombre moyen de mesures et de répartitions dans les demandes incluses. Un nombre plus important de colonnes ajoute à la complexité de la demande. |
| [!UICONTROL **Segments moyens**] | Nombre moyen de segments appliqués aux demandes incluses. Un nombre important de segments ajoute à la complexité de la demande. |

{style="table-layout:auto"}

#### Afficher les données par application

Lorsque vous sélectionnez l’onglet [!UICONTROL **Application**], les colonnes suivantes sont disponibles dans le tableau :

| Colonne | Description |
| --- | --- |
| [!UICONTROL **Application**] | Application dans laquelle les demandes ont été initiées. |
| [!UICONTROL **Nombre de demandes**] | Nombre de demandes associées à l’application. |
| [!UICONTROL **Nombre d’utilisateurs et d’utilisatrices**] | Nombre d’utilisateurs et d’utilisatrices associés à l’application. <!--???--> |
| [!UICONTROL **Nombre de projets**] | Nombre de projets associés à l’application. <!--???--> |
| [!UICONTROL **Complexité moyenne**] | Complexité moyenne des demandes associées à l’application. <p>Le traitement de toutes les demandes ne prend pas le même temps. La complexité de la demande peut vous donner une idée générale du temps nécessaire pour traiter la demande.</p><p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :</p>La valeur de cette colonne est basée sur un score déterminé par les valeurs des colonnes suivantes :<ul><li>[!UICONTROL **Limites mensuelles moyennes**]</li><li>[!UICONTROL **Colonnes moyennes**]</li><li>[!UICONTROL **Segments moyens**]</li></ul> |
| [!UICONTROL **Limites mensuelles moyennes**] | Nombre moyen de mois inclus dans les demandes. Une limite mensuelle importante ajoute à la complexité de la demande. |
| [!UICONTROL **Colonnes moyennes**] | Nombre moyen de mesures et de répartitions dans les demandes incluses. Un nombre plus important de colonnes ajoute à la complexité de la demande. |
| [!UICONTROL **Segments moyens**] | Nombre moyen de segments appliqués aux demandes incluses. Un nombre important de segments ajoute à la complexité de la demande. |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
