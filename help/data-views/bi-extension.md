---
title: Extension Customer Journey Analytics BI
description: Découvrez comment utiliser Power BI ou Tableau Desktop pour accéder aux vues de données à l’aide de l’extension Customer Journey Analytics BI.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 2f9cfc3fc7edaa21175d44dfb3f9bface5cf0d81
workflow-type: tm+mt
source-wordcount: '3247'
ht-degree: 48%

---

# Extension Customer Journey Analytics BI

{{select-package}}

Le [!DNL Customer Journey Analytics BI extension] permet à SQL d’accéder aux [vues de données](./data-views.md) que vous avez définies dans Customer Journey Analytics. Vos ingénieurs et analystes de données connaissent peut-être mieux Power BI, Tableau Desktop ou d’autres outils de Business Intelligence et de visualisation (également appelés outils de BI). Elles peuvent désormais créer des rapports et des tableaux de bord en fonction des vues de données des utilisateurs et utilisatrices de Customer Journey Analytics lors de la création de leurs projets Analysis Workspace.

Le [Query Service](https://experienceleague.adobe.com/fr/docs/experience-platform/query/home) d’Adobe Experience Platform est l’interface SQL des données disponibles dans le lac de données d’Experience Platform. Avec le [!DNL Customer Journey Analytics BI extension] activé, la fonctionnalité de [!DNL Query Service] est étendue pour afficher vos vues de données de Customer Journey Analytics sous la forme de tableaux ou de vues dans une session [!DNL Query Service]. Par conséquent, les outils de Business Intelligence qui utilisent [!DNL Query Service] comme interface PostgresSQL bénéficient en toute transparence de cette fonctionnalité étendue.

Les principaux avantages sont les suivants :

* Il n’est pas nécessaire de recréer une représentation équivalente des vues de données de Customer Journey Analytics dans l’outil de BI lui-même. <br/>Voir [Vues de données](data-views.md) pour plus d’informations sur les fonctionnalités des vues de données afin de comprendre ce qui doit être recréé.
* La cohérence des rapports et analyses entre les outils de BI et Customer Journey Analytics est améliorée.
* Il est possible de combiner des données de Customer Journey Analytics avec d’autres sources de données déjà disponibles dans les outils de BI.

## Conditions préalables

Pour utiliser cette fonctionnalité, vous pouvez utiliser des informations d’identification arrivant à expiration ou non expirantes pour connecter les outils de BI au [!DNL Customer Journey Analytics BI extension]. Le [guide des informations d’identification](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) fournit des informations supplémentaires sur la définition des informations d’identification arrivant à expiration ou non.
Vous trouverez ci-dessous des étapes supplémentaires pour configurer les autorisations CJA
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Expiration des informations d’identification

Pour utiliser des informations d’identification arrivant à expiration, vous pouvez :

* Octroi de l’accès à Experience Platform et Customer Journey Analytics.
* Accordez à l’administrateur de produit l’accès à Customer Journey Analytics afin que vous puissiez afficher, modifier, mettre à jour ou supprimer des connexions et des vues de données.

Vous pouvez également effectuer les opérations suivantes :

* Accordez l’accès aux vues de données auxquelles vous souhaitez accéder.
* Octroi de l’accès à l’extension Customer Journey Analytics BI.

### Informations d’identification sans date d’expiration

Pour utiliser des informations d’identification non expirantes :

* Créez des informations d’identification non expirantes dans Experience Platform.
* Accordez l’accès aux informations d’identification non expirantes en suivant les étapes mentionnées dans [Informations d’identification arrivant à expiration](#Expiring-credentials).

Consultez [ Contrôle d’accès au Parcours client ](../technotes/access-control.md) pour plus d’informations, en particulier les [autorisations supplémentaires d’administrateur de produit](../technotes/access-control.md#product-admin-additional-permissions) et les [autorisations de Customer Journey Analytics dans Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Utilisation

Pour utiliser la fonctionnalité [!DNL Customer Journey Analytics BI extension], vous pouvez utiliser SQL directement ou utiliser l’expérience de glisser-déposer disponible dans l’outil de BI spécifique.

### SQL

Vous pouvez utiliser cette fonctionnalité directement dans les instructions SQL à l’aide du requêteur ou d’un client d’interface de ligne de commande (CLI) PostgresSQL standard.

+++ Requêteur

Dans Adobe Experience Platform :

1. Sélectionnez **[!UICONTROL ** Requêtes **]** dans **[!UICONTROL ** Gestion des données **]** depuis le rail de gauche.

1. Sélectionnez ![Créer une requête](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Créer une requête **]**.

1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

1. Pour exécuter la requête, tapez votre instruction SQL et sélectionnez le bouton ![Lire](assets/Smock_Play_18_N.svg) (ou appuyez sur `[SHIFT]` + `[ENTER]`).

+++


+++ Interface de ligne de commande PostgresSQL

1. Recherchez et copiez vos informations d’identification PostgresSQL dans Adobe Experience Platform :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   1. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

   1. Pour copier la chaîne de commande, utilisez ![Copier](assets/Smock_Copy_18_N.svg) dans la section **[!UICONTROL ** Commande PSQL **]**.

1. Ouvrez une fenêtre de commande ou de terminal.

1. Pour vous connecter et commencer à exécuter vos requêtes, collez la chaîne de commande dans votre terminal.

+++

Voir le [guide de l’interface utilisateur de l’éditeur de requêtes](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) pour plus d’informations.


### Outils BI

Actuellement, le [!DNL Customer Journey Analytics BI extension] est pris en charge et testé pour les outils répertoriés ci-dessous. D’autres outils de BI utilisant l’interface PSQL peuvent également fonctionner, mais ne sont pas encore pris en charge officiellement.

+++ Power BI

1. Recherchez les détails de vos informations d’identification PostgresSQL dans Adobe Experience Platform :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   1. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

   1. Utilisez ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base de données], [!UICONTROL Nom d’utilisateur ou d’utilisatrice], etc.), en cas de besoin dans Power BI.

1. Dans Power BI :

   1. Dans la fenêtre principale, sélectionnez **[!UICONTROL ** Obtenir des données **]** dans la barre d’outils supérieure.

   1. Sélectionnez **[!UICONTROL Plus...]** dans le rail de gauche.

   1. Sur l’écran **Obtenir des données**, recherchez `PostgresSQL` et sélectionnez la **[!UICONTROL ** base de données PostgresSQL **]** dans la liste.

   1. Dans la boîte de dialogue **[!UICONTROL ** Base de données PostgressSQL **]**, réalisez les actions suivantes :

      1. Collez le paramètre **[!UICONTROL ** Host **]** des Requêtes Experience Platform [!UICONTROL Credentials] dans le champ de texte **[!UICONTROL ** Server **]**.

      1. Collez le paramètre **[!UICONTROL ** Database **]** dans le champ de texte **[!UICONTROL ** Database **]** à partir des Requêtes Experience Platform [!UICONTROL Credentials].

         Ajoutez `?FLATTEN` au paramètre **[!UICONTROL ** Base de données **]**, de sorte à lire `prod:cja?FLATTEN`, par exemple. Voir [Aplatissement des structures de données imbriquées à utiliser avec des outils de BI tiers](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) pour plus d’informations.

      1. Lorsque vous êtes invité au mode **[!UICONTROL Connectivité des données]**, sélectionnez **[!UICONTROL DirectQuery]**.

      1. Vous devez fournir un **[!UICONTROL Nom d’utilisateur ou d’utilisatrice]** et un **[!UICONTROL Mot de passe]**. Utilisez les mêmes paramètres d’[!UICONTROL Informations d’identification] que pour les requêtes Experience Platform.


   1. Une fois la connexion établie, les tableaux de la vue de données Customer Journey Analytics apparaissent dans Power BIs **[!UICONTROL ** Navigateur **]**.

   1. Sélectionnez les tableaux des vues de données à utiliser, puis sélectionnez **[!UICONTROL ** Charger **]**.

   Toutes les dimensions et mesures associées à un ou plusieurs tableaux sélectionnés s’affichent dans le volet de droite et sont prêtes à être utilisées dans vos visualisations.

   Voir [Connexion de Power BI à Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) pour plus d’informations. Voir aussi [Cas d’utilisation de l’extension BI](/help/use-cases/data-views/bi-extension-usecases.md) pour un exemple détaillé.

+++

+++Tableau Desktop

1. Recherchez les détails de vos informations d’identification PostgresSQL dans Adobe Experience Platform :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   1. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

   1. Utilisez ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d&#39;informations d&#39;identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base de données], [!UICONTROL Nom d&#39;utilisateur], etc.) si nécessaire dans Tableau Desktop.

1. Dans Tableau Desktop :

   1. Sélectionnez **[!UICONTROL ** Plus **]** depuis **[!UICONTROL ** Vers un serveur **]** dans le rail de gauche.

   1. Sélectionnez **[!UICONTROL ** PostgresSQL **]** dans la liste.

   1. Dans la boîte de dialogue [!UICONTROL PostgresSQL], réalisez les actions suivantes :

      1. Collez le paramètre **[!UICONTROL ** Host **]** des Requêtes Experience Platform [!UICONTROL Credentials] dans le champ de texte **[!UICONTROL ** Server **]**.

      1. Collez le paramètre **[!UICONTROL ** Port **]** des Requêtes Experience Platform [!UICONTROL Informations d’identification] dans le champ de texte **[!UICONTROL ** Port **]**.

      1. Collez le paramètre **[!UICONTROL ** Database **]** des Requêtes Experience Platform [!UICONTROL Credentials] dans le champ de texte **[!UICONTROL ** Database **]**.

         Ajoutez `%3FFLATTEN` au paramètre **[!UICONTROL ** Base de données **]**, de sorte à lire `prod:cja%3FFLATTEN`, par exemple. Voir [Aplatissement des structures de données imbriquées à utiliser avec des outils de BI tiers](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) pour plus d’informations.

      1. Sélectionnez **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice et mot de passe **]** dans la liste **[!UICONTROL ** Authentification **]**.

      1. Collez le paramètre **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice **]**.

      1. Collez le paramètre **[!UICONTROL ** Mot de passe **]** des Requêtes Experience Platform [!UICONTROL Informations d’identification] dans le champ de texte **[!UICONTROL ** Mot de passe **]**.

      1. Sélectionnez l’option **[!UICONTROL ** Se connecter **]**.

   1. Les vues de données Customer Journey Analytics s’affichent sous la forme de tableaux dans la liste **[!UICONTROL ** Tableau **]**.

   1. Faites glisser les tableaux à utiliser sur la zone de travail.

   Vous pouvez désormais utiliser les données des tableaux de vues de données pour créer vos rapports et visualisations.

   Voir [Connexion de Tableau à Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) pour plus d&#39;informations. Voir aussi [Cas d’utilisation de l’extension BI](/help/use-cases/data-views/bi-extension-usecases.md) pour un exemple détaillé.

+++

+++ Looker

1. Recherchez les détails de vos informations d’identification PostgresSQL dans Adobe Experience Platform :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   1. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

   1. Utilisez ![Copy](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’informations d’identification Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], etc.) si nécessaire dans Looker.

1. Dans l’outil de recherche :

   1. Sélectionnez **[!UICONTROL Admin]** dans le rail de gauche.
   1. Sélectionnez **[!UICONTROL Connexions]**.
   1. Sélectionnez **[!UICONTROL Ajouter une connexion]**.
   1. Dans l’écran **[!UICONTROL Connecter votre base de données à Looker]**, collez les valeurs appropriées lors de la configuration de votre nouvelle connexion. Veillez à sélectionner **[!UICONTROL PostgreSQL 9.5+]** comme dialecte.
   1. Sélectionnez **[!UICONTROL Tester]** pour tester la connexion.
   1. Une fois l’opération réussie, sélectionnez **[!UICONTROL Mettre à jour]** pour enregistrer la connexion.

   Vous pouvez désormais utiliser les données des tableaux de vues de données pour créer vos rapports et visualisations.

   Voir [Connexion de la recherche à Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/looker) pour plus d’informations. Voir aussi [Cas d’utilisation de l’extension BI](/help/use-cases/data-views/bi-extension-usecases.md) pour un exemple détaillé.

+++

+++ Notebook Jupyter

1. Recherchez les détails de vos informations d’identification PostgresSQL dans Adobe Experience Platform :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   1. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

   1. Utilisez ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’informations d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base de données], [!UICONTROL Nom d’utilisateur], etc.) si nécessaire dans le notebook Jupyter.

1. Dans le notebook Jupyter :

   1. Veillez à utiliser les bibliothèques requises.
   1. Utilisez les valeurs appropriées lors de la configuration et de l’exécution de la connexion.
   1. Testez votre connexion en exécutant une requête appropriée.

   En cas de réussite, vous pouvez utiliser les données pour créer des rapports et des visualisations.

   Voir [Connecter le notebook Jupyter à Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/jupyter-notebook) pour plus d’informations. Voir aussi [Cas d’utilisation de l’extension BI](/help/use-cases/data-views/bi-extension-usecases.md) pour un exemple détaillé.

+++

+++ RStudio

1. Recherchez les détails de vos informations d’identification PostgresSQL dans Adobe Experience Platform :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   1. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   1. Sélectionnez la base de données `cja` de votre sandbox dans la liste des bases de données du menu déroulant **[!UICONTROL Base de données]**. Par exemple `prod:cja`.

   1. Utilisez ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’informations d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base de données], [!UICONTROL Nom d’utilisateur], etc.) si nécessaire dans le notebook Jupyter.

1. Dans RStudio :

   1. Veillez à utiliser les bibliothèques requises.
   1. Utilisez les valeurs appropriées lors de la configuration et de l’exécution de la connexion.
   1. Testez votre connexion en exécutant une requête appropriée.

   En cas de réussite, vous pouvez utiliser les données pour créer des rapports et des visualisations.

   Voir [Connexion de RStudio à Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/rstudio) pour plus d’informations. Consultez également la section [Cas d’utilisation de l’extension BI](/help/use-cases/data-views/bi-extension-usecases.md) pour un exemple détaillé (qui utilise le package RPostgres à la place).

+++

Voir [Connecter des clients à Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) pour une vue d’ensemble des différents outils disponibles et pour plus d’informations.

Voir [Cas d’utilisation](/help/use-cases/data-views/bi-extension-usecases.md) pour savoir comment réaliser un certain nombre de cas d’utilisation à l’aide de l’extension Customer Journey Analytics BI.

## Fonctionnalité

Par défaut, vos vues de données ont un nom de tableau sécurisé généré à partir de leur nom convivial. Par exemple, la vue de données nommée [!UICONTROL Ma vue de données web] porte le nom `my_web_data_view`. Vous pouvez définir un nom préféré à utiliser dans votre outil BI pour votre vue de données. Voir [Paramètres des vues de données](create-dataview.md#settings) pour plus d’informations.

Pour utiliser les identifiants de vue de données comme noms de table, vous pouvez ajouter le paramètre optionnel `CJA_USE_IDS` sur le nom de la base de données lors de la connexion. Par exemple, `prod:cja?CJA_USE_IDS` affiche vos vues de données avec des noms tels que `dv_ABC123`.

### Gouvernance des données

Les paramètres liés à la gouvernance de données dans Customer Journey Analytics sont hérités d’Adobe Experience Platform. L’intégration entre Customer Journey Analytics et la gouvernance de données Adobe Experience Platform permet l’étiquetage des données Customer Journey Analytics sensibles et l’application des politiques de confidentialité.

Les libellés et les politiques de confidentialité créés sur les jeux de données consommés par Experience Platform peuvent être affichés dans le workflow des vues de données Customer Journey Analytics. Par conséquent, les données interrogées à l’aide du [!DNL Customer Journey Analytics BI extension] affichent les avertissements ou les erreurs appropriés en cas de non-respect des étiquettes de confidentialité et des politiques définies.

### Liste des vues de données

Dans l’interface de ligne de commande PostgreSQL standard, vous pouvez répertorier vos vues à l’aide de `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Imbrication et aplatissement

Par défaut, le schéma de vos vues de données utilise des structures imbriquées, tout comme les schémas XDM d’origine. L’intégration prend également en charge l’option `FLATTEN`. Vous pouvez utiliser cette option pour forcer l’aplatissement du schéma des vues de données (et de tout autre tableau de la session). L’aplatissement permet une utilisation plus facile dans les outils de BI qui ne prennent pas en charge les schémas structurés. Voir [Utiliser les structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) pour plus d’informations.


### Valeurs par défaut et limites

Les valeurs par défaut et limites supplémentaires suivantes s’appliquent lors de l’utilisation de l’extension BI :

* L’extension BI requiert une limite de lignes pour les résultats de la requête. La valeur par défaut est de 50, mais vous pouvez la remplacer dans SQL à l’aide de `LIMIT n`, où `n` est comprise entre 1 et 50000.
* L’extension BI requiert une période pour limiter les lignes utilisées pour les calculs. La valeur par défaut est celle des 30 derniers jours, mais vous pouvez la remplacer dans votre clause de `WHERE` SQL à l’aide des colonnes [`timestamp`](#timestamp) ou [`daterange`](#date-range) spéciales.
* L’extension BI requiert des requêtes agrégées. Vous ne pouvez pas utiliser du SQL comme `SELECT * FROM ...` pour obtenir les lignes brutes sous-jacentes. À un niveau élevé, vos requêtes agrégées doivent utiliser :
   * Sélectionnez des totaux à l’aide de `SUM` et/ou `COUNT`.<br/> Par exemple, `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Sélectionnez des mesures réparties par dimension. <br/>Par exemple, `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Sélectionnez des valeurs de mesure distinctes.<br/>Par exemple, `SELECT DISTINCT dimension1 FROM ...`

     Voir pour plus d’informations [SQL pris en charge](#supported-sql).


### SQL pris en charge

Voir [Référence SQL de Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview) pour obtenir une référence complète sur le type de SQL pris en charge.

Consultez le tableau ci-dessous pour obtenir des exemples de langage SQL que vous pouvez utiliser.

+++ Exemples

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>Modèle</th>
            <th>Exemple</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Découverte de schéma </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>Classement ou répartition </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> clause </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>Distinct, haut 
valeurs de dimension </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>Totaux des mesures </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>Multi-dimension
répartitions
et top-distincts </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>Sous-sélectionner :
Filtrer les éléments supplémentaires
resultats </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  GROUP BY dim1
)
OÙ dim1 dans ('A', 'B')</code></pre>
            </td>
        </tr>
        <tr>
            <td>Sous-sélectionner :
Requête sur
vues de données </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>Sous-sélectionner : 
Source superposée, 
le filtrage, 
et agrégation </td>
            <td>Superposé à l’aide de sous-sélections :
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
Calques utilisant CTE AVEC :
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>Sélectionne où le
les mesures viennent avant
 ou sont mélangés à
les dimensions </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### Dimensions

Vous pouvez sélectionner l’une des dimensions disponibles par défaut ou définies dans la vue de données. Vous sélectionnez une dimension en fonction de son identifiant.

### Mesures

Les mesures disponibles à la sélection sont les suivantes :

* L’une des mesures disponibles par défaut ;
* Défini dans la vue de données ;
* Mesures calculées compatibles avec la vue de données à laquelle l’utilisateur a accès.

La mesure est sélectionnée en fonction de son identifiant enveloppé dans une expression `SUM(metric)`, comme avec les autres sources SQL.

Vous pouvez utiliser :

* `SELECT COUNT(*)` ou `COUNT(1)` pour obtenir la mesure Occurrences.
* `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` pour comptabiliser les valeurs distinctes approximatives d’une dimension. Voir les détails dans [Comptage de valeurs distinctes](#counting-distinct-values).
* [Calculs intégrés](#inline-calculations) pour combiner des mesures à la volée et/ou faire des calculs dessus.

#### Comptage des valeurs distinctes

En raison de la nature sous-jacente du fonctionnement de Customer Journey Analytics, la seule dimension pour laquelle vous pouvez obtenir un comptage des valeurs distinctes exact est la dimension `adobe_personid`. Les instructions SQL suivantes `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` renvoient la valeur de la mesure Personnes par défaut, qui correspond au nombre de personnes distinctes. Pour les autres dimensions, un nombre distinct approximatif est renvoyé.

#### Mesures conditionnelles

Vous pouvez incorporer une clause `IF` ou `CASE` dans les fonctions `SUM` ou `COUNT` pour ajouter un filtrage supplémentaire spécifique à une mesure sélectionnée. L’ajout de ces clauses est similaire à l’application d’un filtre à une colonne de mesures dans un tableau de rapport Workspace.

Exemples :

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Calculs intégrés

Vous pouvez appliquer des mathématiques supplémentaires aux expressions de mesure dans votre `SELECT`. Ces calculs peuvent être utilisés au lieu de définir les calculs dans une mesure calculée. Le tableau suivant répertorie les types d’expressions pris en charge.

| Opérateur ou Fonction | Détails |
|---|---|
| `+`, `-`, `*`, `/`, et `%` | Ajouter, soustraire, multiplier, diviser et modulaire/reste |
| `-X` ou `+X` | Modifier le signe ou la mesure où X est l’expression de mesure |
| `PI()` | π constant |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` et `TANH` | Fonctions mathématiques unaires |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Fonctions mathématiques binaires |

{style="table-layout:auto"}

### Colonnes spéciales

#### Horodatage

La colonne spéciale `timestamp` fournit les périodes de la requête. Une période peut être définie par une expression `BETWEEN` ou une paire de vérifications `timestamp` `>`, `>=`, `<`, `<=` (avec `AND`).
La valeur `timestamp` est facultative. Si aucune plage complète n’est fournie, les valeurs par défaut sont utilisées :

* Si seul un minimum est fourni (`timestamp > X` ou ` timestamp >= X`), la plage est comprise entre X et maintenant.
* Si seul un maximum est fourni (`timestamp < X` ou `timestamp <= X`), la plage va de X moins 30 jours à X.
* Si rien n’est fourni, la plage va de maintenant moins 30 jours à maintenant.

La plage d’horodatage est convertie en filtre global de plage de dates dans RankedRequest.
Le champ d’horodatage peut également être utilisé dans les fonctions date/heure pour analyser ou tronquer l’horodatage de l’événement.

#### Période

La colonne spéciale `daterange` fonctionne de la même manière que `timestamp` ; toutefois, le filtrage est limité à jours complets. La `daterange` est également facultative et présente les mêmes valeurs par défaut que `timestamp`.
Le champ `daterange` peut également être utilisé dans les fonctions date/heure pour analyser ou tronquer la date de l’événement.

La colonne spéciale `daterangeName` peut être utilisée pour filtrer votre requête à l’aide d’une période nommée telle que `Last Quarter`.

>[!NOTE]
>
>Power BI ne prend pas en charge les mesures `daterange` inférieures à un jour (heure, 30 minutes, 5 minutes, etc.).
>

#### ID de filtre

La colonne spéciale `filterId`, optionnelle, sert à appliquer à la requête un filtre défini en externe. L’application d’un filtre défini en externe à une requête est similaire au glissement d’un filtre sur un panneau de Workspace. Plusieurs identifiants de filtre peuvent être utilisés en les `AND`.

En plus de `filterId`, vous pouvez utiliser `filterName` pour utiliser le nom d’un filtre au lieu de l’identifiant.

### Clause Where

La clause `WHERE` est gérée en trois étapes :

1. Recherchez la période dans les champs spéciaux `timestamp`, `daterange` ou `daterangeName`.

1. Recherchez les `filterId` ou `filterName` définis de manière externe à inclure dans le filtrage.

1. Conversion des expressions restantes en filtres ad hoc.

La gestion est effectuée en analysant le premier niveau de `AND` dans la clause `WHERE`. Chaque expression `AND` de niveau supérieur doit correspondre à l’une des valeurs ci-dessus. Tout élément, s’il est plus profond que le premier niveau de `AND` ou si la clause `WHERE` utilise `OR` au niveau supérieur, est traité comme un filtre ad hoc.

### Ordre de tri

Par défaut, la requête trie les résultats selon la première mesure sélectionnée dans l’ordre décroissant. Vous pouvez remplacer l’ordre de tri par défaut en spécifiant `ORDER BY ... ASC` ou `ORDER BY ... DESC`. Si vous utilisez `ORDER BY`, vous devez spécifier `ORDER BY` sur la première mesure sélectionnée.

Vous pouvez également inverser l’ordre en utilisant `-` (moins) devant la mesure. Les deux instructions ci-dessous donnent le même ordre :

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Prise en charge des fonctions générales

| Fonction | Exemple | Détails |
|---|---|---|
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | La diffusion de type n’est pas prise en charge actuellement, mais aucune erreur n’est générée. La fonction `CAST` est ignorée. |
| [Date et heure](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analysez une chaîne d’heure en tant que date et heure à utiliser dans une clause `WHERE`. |
| [To timestamp](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analysez une chaîne d’heure en tant que date et heure à utiliser dans une clause `WHERE`, en fournissant éventuellement un format pour cette chaîne d’heure. |
| [Date](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analysez une chaîne de date en tant que date et heure à utiliser dans une clause `WHERE`. |
| [À ce jour](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analysez une chaîne de date en tant que date et heure à utiliser dans une clause `WHERE`, en fournissant éventuellement un format pour cette chaîne de date. |

{style="table-layout:auto"}

### Prise en charge des fonctions Dimension

Ces fonctions peuvent être utilisées sur les dimensions des clauses `SELECT` et `WHERE` ou dans les mesures conditionnelles.

**Fonctions de chaîne**

| Fonction | Exemple | Détails |
|---|---|---|
| [Inférieur](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Générez une identité de dimension dynamique sur le champ transmis. |

{style="table-layout:auto"}

**Fonctions date-heure**

| Fonction | Exemple | Détails |
|---|---|---|
| [Année](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Mois](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Jour](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Jour de la semaine](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’identifiant de l’élément au lieu de la valeur, car vous avez besoin du numéro et non du nom convivial. |
| [Jour de l’année](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Semaine](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Trimestre](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Heure](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’identifiant de l’élément au lieu de la valeur, car vous avez besoin du numéro et non du nom convivial. |
| [Minute](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [Extraire](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’ID d’élément au lieu de la valeur de certaines parties de cette fonction, car vous avez besoin du numéro et non du nom convivial.<br/>Les parties prises en charge sont les suivantes :<br>- Mots-clés : `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Chaînes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [Date (partie)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’ID d’élément au lieu de la valeur de certaines parties de cette fonction, car vous avez besoin du numéro et non du nom convivial.<br/>Les parties de chaîne prises en charge sont les suivantes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [Date (tronquée)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis.<br/>Les granularités de chaîne prises en charge sont les suivantes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |

{style="table-layout:auto"}

### Prise en charge partielle

Certaines fonctionnalités SQL ne sont que partiellement prises en charge avec l’extension BI et ne renvoient pas les mêmes résultats que ceux d’autres bases de données.  Cette fonctionnalité spécifique est utilisée dans le langage SQL généré par divers outils de BI, pour lesquels l’extension BI n’a pas de correspondance exacte. Par conséquent, l’extension BI se concentre sur une implémentation limitée qui couvre l’utilisation minimale de l’outil BI sans générer d’erreurs. Voir le tableau ci-dessous pour plus d’informations.

| Fonction | Exemple | Détails |
|---|---|---|
| MIN() ET MAX() | ``MIN(daterange)`` ou <br/> ``MAX(daterange)`` | `MIN()` sur `timestamp`, `daterange` ou tout autre `daterangeX` comme `daterangeday` reviendra il y a 2 ans.<br/><br/> `MAX()` sur `timestamp`, `daterange` ou l’un des `daterangeX` tels que `daterangeday` renvoie la date/l’heure actuelle.<br/><br/>`MIN()` ou `MAX()` sur une autre dimension, mesure ou expression renvoie 0. |

{style="table-layout:auto"}
