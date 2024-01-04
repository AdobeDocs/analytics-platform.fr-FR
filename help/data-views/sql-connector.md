---
title: Connecteur SQL
description: Découvrez comment utiliser Query Service, Power BI et/ou Tableau pour accéder aux vues de données à l’aide du connecteur SQL.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 1827a637-6c0f-43f2-862a-928089340d30
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '2789'
ht-degree: 100%

---

# Connecteur SQL

{{release-limited-testing}}

{{select-package}}

Le [!DNL Customer Journey Analytics SQL Connector] permet à SQL d’accéder aux [vues de données](./data-views.md) que vous avez définies dans Customer Journey Analytics. Il se peut que les personnes chargées de votre ingénierie et de votre analyse des données maîtrisent bien Power BI, Tableau ou d’autres outils de Business Intelligence et de visualisation (appelés outils de BI). Elles peuvent désormais créer des rapports et des tableaux de bord en fonction des vues de données des utilisateurs et utilisatrices de Customer Journey Analytics lors de la création de leurs projets Analysis Workspace.

Le [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) d’Adobe Experience Platform est l’interface SQL des données disponibles dans le lac de données d’Experience Platform. Avec le [!DNL Customer Journey Analytics SQL Connector] activé, la fonctionnalité de [!DNL Query Service] est étendue pour afficher vos vues de données de Customer Journey Analytics sous la forme de tableaux ou de vues dans une session [!DNL Query Service]. Par conséquent, les outils de Business Intelligence qui utilisent [!DNL Query Service] comme interface PostgresSQL bénéficient en toute transparence de cette fonctionnalité étendue.

Les principaux avantages sont les suivants :

- Il n’est pas nécessaire de recréer une représentation équivalente des vues de données de Customer Journey Analytics dans l’outil de BI lui-même. <br/>Voir [Vue de données](data-views.md) pour plus d’informations sur les fonctionnalités des vues de données afin de comprendre ce qui doit être recréé.<br/>

- La cohérence des rapports et analyses entre les outils de BI et Customer Journey Analytics est améliorée.

- Il est possible de combiner des données de Customer Journey Analytics avec d’autres sources de données déjà disponibles dans les outils de BI.

## Conditions préalables

Pour utiliser cette fonctionnalité, vous devez :

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- Configurer la fonctionnalité pour les profils de produits, les groupes d’utilisateurs et d’utilisatrices et/ou les utilisateurs et utilisatrices individuels.<br/>
Les utilisateurs et utilisatrices doivent avoir accès aux éléments suivants :
   - Query Service d’Experience Platform ;
   - projets Workspace Customer Journey Analytics ;
   - vues de données Customer Journey Analytics à utiliser.

- Utilisez des informations d’identification expirant ou n’expirant pas pour connecter les outils de BI au connecteur SQL Customer Journey Analytics. Le [Guide d’identification](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=fr) fournit des informations supplémentaires sur la définition des informations d’identification expirant ou n’expirant pas.

Voir [Contrôle d’accès](../admin/cja-access-control.md) dans la section Administration de Customer Journey Analytics pour plus d’informations.


## Utilisation

Pour utiliser la fonctionnalité [!DNL Customer Journey Analytics SQL Connector], vous pouvez utiliser SQL directement ou utiliser l’expérience de glisser-déposer disponible dans l’outil de BI spécifique.

### SQL

Vous pouvez utiliser cette fonctionnalité directement dans les instructions SQL à l’aide du requêteur ou d’un client d’interface de ligne de commande (CLI) PostgresSQL standard.

+++ Requêteur

Dans l’interface utilisateur d’Experience Platform :

1. Sélectionnez **[!UICONTROL ** Requêtes **]** dans **[!UICONTROL ** Gestion des données **]** depuis le rail de gauche.

2. Sélectionnez ![Créer une requête](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Créer une requête **]**.

3. Pour exécuter la requête, saisissez votre instruction SQL et sélectionnez le bouton ![Lecture](assets/Smock_Play_18_N.svg) (ou appuyez sur MAJ+ENTRÉE).

+++


+++ Interface de ligne de commande PostgresSQL

1. Dans l’interface utilisateur d’Experience Platform, recherchez et copiez vos informations d’identification PostgresSQL :

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   2. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   3. Pour copier la chaîne de connexion, utilisez ![Copier](assets/Smock_Copy_18_N.svg) dans la section **[!UICONTROL ** Commande PSQL **]**.

2. Ouvrez votre interface de ligne de commande PostgresSQL.

3. Pour vous connecter et commencer à exécuter vos requêtes, collez la chaîne de connexion dans l’interface de ligne de commande PostgresSQL.

+++

Voir [Guide de l’interface utilisateur du requêteur](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=fr) pour plus d’informations.


### Outils de BI

Actuellement, le connecteur SQL Customer Journey Analytics est pris en charge et testé uniquement pour Power BI et Tableau. D’autres outils de BI utilisant l’interface PSQL peuvent également fonctionner, mais ne sont pas encore pris en charge officiellement.

+++ Power BI

1. Dans l’interface utilisateur d’Adobe Experience Platform, recherchez les détails de vos informations d’identification PostgresSQL.

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   2. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   3. Utilisez ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base de données], [!UICONTROL Nom d’utilisateur ou d’utilisatrice], etc.), en cas de besoin dans Power BI.

2. Dans Power BI :

   1. Dans la fenêtre principale, sélectionnez **[!UICONTROL ** Obtenir des données **]** dans la barre d’outils supérieure.

   2. Sélectionnez **[!UICONTROL ** Plus...**]** dans le rail de gauche.

   3. Sur l’écran **Obtenir des données**, recherchez `PostgresSQL` et sélectionnez la **[!UICONTROL ** base de données PostgresSQL **]** dans la liste.

   4. Dans la boîte de dialogue **[!UICONTROL ** Base de données PostgressSQL **]**, réalisez les actions suivantes :

      1. Collez le paramètre **[!UICONTROL ** Hôte **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Serveur **]**.

      2. Collez le paramètre **[!UICONTROL ** Base de données **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Base de données **]**.

         Ajoutez `?FLATTEN` au paramètre **[!UICONTROL ** Base de données **]**, de sorte à lire `prod:cja?FLATTEN`, par exemple. Voir [Aplatissement des structures de données imbriquées à utiliser avec des outils de BI tiers](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=fr) pour plus d’informations.

      3. En mode **[!UICONTROL ** Connectivité des données **]**, sélectionnez **[!UICONTROL ** DirectQuery **]** pour vous assurer que les structures de données sont aplaties correctement.

      4. Vous devez fournir un **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice **]** et un **[!UICONTROL ** Mot de passe **]**. Utilisez les mêmes paramètres d’[!UICONTROL Informations d’identification] que pour les requêtes Experience Platform.


   5. Une fois la connexion établie, les tableaux des vue de données de Customer Journey Analytics s’affichent dans le **[!UICONTROL ** Navigateur **]** de Power BI. Les tableaux des vues de données sont identifiés à l’aide de `dv_` dans leurs noms.


   6. Sélectionnez les tableaux des vues de données à utiliser, puis sélectionnez **[!UICONTROL ** Charger **]**.

   Toutes les dimensions et mesures associées à un ou plusieurs tableaux sélectionnés s’affichent dans le volet de droite et sont prêtes à être utilisées dans vos visualisations.

   Voir [Connecter Power BI à Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=fr) pour plus d’informations.

+++

+++Tableau

1. Dans l’interface utilisateur d’Experience Platform, recherchez les détails de vos informations d’identification PostgresSQL.

   1. Sélectionnez **[!UICONTROL ** Requêtes **]** depuis le rail de gauche (sous **[!UICONTROL ** Gestion des données **]**).

   2. Sélectionnez **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   3. Utilisez ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’informations d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base de données], [!UICONTROL Nom d’utilisateur ou d’utilisatrice], etc.) en cas de besoin dans Tableau.

2. Dans Tableau :

   1. Sélectionnez **[!UICONTROL ** Plus **]** depuis **[!UICONTROL ** Vers un serveur **]** dans le rail de gauche.

   2. Sélectionnez **[!UICONTROL ** PostgresSQL **]** dans la liste.

   3. Dans la boîte de dialogue [!UICONTROL PostgresSQL], réalisez les actions suivantes :

      1. Collez le paramètre **[!UICONTROL ** Hôte **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Serveur **]**.

      2. Collez le paramètre **[!UICONTROL ** Port **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Serveur **]**.

      3. Collez le paramètre **[!UICONTROL ** Base de données **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Base de données **]**.

         Ajoutez `%3FFLATTEN` au paramètre **[!UICONTROL ** Base de données **]**, de sorte à lire `prod:cja%3FFLATTEN`, par exemple. Voir [Aplatissement des structures de données imbriquées à utiliser avec des outils de BI tiers](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=fr) pour plus d’informations.

      4. Sélectionnez **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice et mot de passe **]** dans la liste **[!UICONTROL ** Authentification **]**.

      5. Collez le paramètre **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Nom d’utilisateur ou d’utilisatrice **]**.

      6. Collez le paramètre **[!UICONTROL ** Mot de passe **]** des [!UICONTROL Informations d’identification] des requêtes Experience Platform dans le champ de texte **[!UICONTROL ** Mot de passe **]**.

      7. Sélectionnez **[!UICONTROL ** Se connecter **]**.

   4. Les vues de données Customer Journey Analytics s’affichent sous forme de tableaux dans la liste **[!UICONTROL ** Tableau **]**. Les tableaux des vues de données comportent le préfixe `dv_`.

   5. Faites glisser les tableaux à utiliser sur la zone de travail.

   Vous pouvez désormais utiliser les données des tableaux de vues de données pour créer vos rapports et visualisations.

   Voir [Connecter Tableau à Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=fr) pour plus d’informations.

+++

Voir [Connecter des clients à Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=fr) pour une vue d’ensemble des différents outils disponibles et pour plus d’informations.

## Fonctionnalité

Par défaut, vos vues de données ont un nom de tableau sécurisé généré à partir de leur nom convivial. Par exemple, la vue de données nommée [!UICONTROL Mes données web] possède le nom de vue `dv_my_web_data`.

Pour utiliser les identifiants de vue de données comme noms de table, vous pouvez ajouter le paramètre optionnel `CJA_USE_IDS` sur le nom de la base de données lors de la connexion. Par exemple, `prod:all?CJA_USE_IDS` affiche vos vues de données avec des noms tels que `dv_ABC123`.

### Gouvernance des données

Les paramètres liés à la gouvernance de données dans Customer Journey Analytics sont hérités d’Adobe Experience Platform. L’intégration entre Customer Journey Analytics et la gouvernance de données Adobe Experience Platform permet l’étiquetage des données Customer Journey Analytics sensibles et l’application des politiques de confidentialité.

Les libellés et les politiques de confidentialité créés sur les jeux de données consommés par Experience Platform peuvent être affichés dans le workflow des vues de données Customer Journey Analytics. Par conséquent, les données interrogées à l’aide du connecteur SQL Customer Journey Analytics affichent des avertissements ou des erreurs appropriés lorsque vous ne respectez pas les libellés et politiques de confidentialité définis.

### Liste des vues de données

Dans l’interface de ligne de commande PostgreSQL standard, vous pouvez répertorier vos vues à l’aide de `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Imbrication et aplatissement

Par défaut, le schéma de vos vues de données utilise des structures imbriquées, tout comme les schémas XDM d’origine. L’intégration prend également en charge l’option `FLATTEN`. Vous pouvez utiliser cette option pour forcer l’aplatissement du schéma des vues de données (et de tout autre tableau de la session). L’aplatissement permet une utilisation plus facile dans les outils de BI qui ne prennent pas en charge les schémas structurés. Voir [Utiliser les structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=fr) pour plus d’informations.

### SQL pris en charge

Voir [Référence SQL de Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=fr) pour obtenir une référence complète sur le type de SQL pris en charge.

Consultez le tableau ci-dessous pour obtenir des exemples de langage SQL à utiliser.

+++ Exemples

| Modèle | Exemple |
|---|---|
| Découverte de schéma | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Classé/Répartition | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/> filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/> AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| Clause HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Valeurs de dimension Distinct, top <br/> | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Totaux des mesures | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| <br/>Répartitions<br/> multi-dimensions et top-distincts | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Sous-sélection : filtrage <br/>Résultat supplémentaire<br/> | <pre>SELECT dim1, m1<br/>FROM (<br/> SELECT dim1, SUM(metric1) AS m1<br/> FROM dv1<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br> GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Sous-sélection : <br/>jonction avec le <br/>jeu de données non présent dans<br/> Customer Journey Analytics | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/> SELECT dim1, SUM(metric1) AS m1<br/> FROM dv1<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/> GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| Sous-sélection : <br/>requêtes dans les<br/> vues de données | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/> SELECT dim1 AS key, SUM(metric1) AS m1<br/> FROM dv1<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/> GROUP BY dim1<br/><br/> UNION<br/><br/> SELECT dim2 AS key, SUM(m1) AS m1<br/> FROM dv2<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/> GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Sous-sélection : <br/>sources en niveaux, <br/>filtrage <br/>et aggregation | Niveaux utilisant les sous-sélections :<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/> SELECT \_.dim1,\_.m1<br/> FROM (<br/> SELECT \* FROM dv1<br/> WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>) \_<br/> WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Niveaux utilisant CTE WITH :<br/><pre>WITH rows AS (<br/> WITH \_ AS (<br/> SELECT * FROM data_ares<br/> WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>)<br/> SELECT _.item, _.units FROM _<br/> WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Sélectionne l’emplacement où <br/>les mesures sont antérieures<br/> ou sont mélangées avec <br/>les dimensions | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensions

Vous pouvez sélectionner l’une des dimensions disponibles par défaut ou définies dans la vue de données. Vous sélectionnez une dimension en fonction de son identifiant.

### Mesures

Les mesures disponibles à la sélection sont les suivantes :

- mesures disponibles par défaut ;

- mesures définies dans la vue de données ;

- mesures calculées compatibles avec la vue de données à laquelle l’utilisateur ou l’utilisatrice a accès.

La mesure est sélectionnée en fonction de son identifiant enveloppé dans une expression `SUM(metric)`, comme avec les autres sources SQL.

Vous pouvez utiliser :

- `SELECT COUNT(*)` ou `COUNT(1)` pour obtenir la mesure Occurrences.

- `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` pour comptabiliser les valeurs distinctes approximatives d’une dimension. Voir les détails dans [Comptage des valeurs distinctes](#counting-distincts).

- [Calculs intégrés](#inline-calculations) pour combiner des mesures à la volée et/ou effectuer des calculs sur celles-ci.

#### Comptage des valeurs distinctes

En raison de la nature sous-jacente du fonctionnement de Customer Journey Analytics, la seule dimension pour laquelle vous pouvez obtenir un comptage des valeurs distinctes exact est la dimension `adobe_personid`. Les instructions SQL suivantes `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` renvoient la valeur de la mesure Personnes par défaut, qui est le nombre de personnes distinctes. Pour les autres dimensions, un nombre distinct approximatif est renvoyé.

#### Mesures conditionnelles

Vous pouvez incorporer une clause `IF` ou `CASE` dans les fonctions `SUM` ou `COUNT` pour ajouter un filtrage supplémentaire spécifique à une mesure sélectionnée. L’ajout de ces clauses est similaire à l’application d’un filtre à une colonne de mesures dans un tableau de rapport Workspace.

Exemples :

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Calculs intégrés

Vous pouvez appliquer des expressions de mesure supplémentaires dans votre `SELECT` au lieu d’effectuer les calculs dans une mesure calculée. Le tableau suivant répertorie les types d’expressions pris en charge.

| Opérateur ou Fonction | Détails |
|---|---|
| `+`, `-`, `*`, `/`, et `%` | Ajouter, soustraire, multiplier, diviser et modulaire/reste |
| `-X` ou `+X` | Modifier le signe ou la mesure où X est l’expression de mesure |
| `PI()` | π constant |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` et `TANH` | Fonctions mathématiques unaires |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Fonctions mathématiques binaires |

{style="table-layout:auto"}

### Colonnes spéciales

**Date et heure**

La colonne spéciale `timestamp` fournit les périodes de la requête. Une période peut être définie par une expression `BETWEEN` ou une paire de vérifications `timestamp` `>`, `>=`, `<`, `<=` (avec `AND`).
La valeur `timestamp` est facultative. Si aucune plage complète n’est fournie, les valeurs par défaut sont utilisées :

- Si seul un minimum est fourni (`timestamp > X` ou ` timestamp >= X`), la plage est comprise entre X et maintenant.

- Si seul un maximum est fourni (`timestamp < X` ou `timestamp <= X`), la plage est comprise entre X-30 jours et X.

- Si rien n’est indiqué, la période est comprise entre maintenant-30 jours et maintenant.

La plage de date et heure est convertie en filtre global de plage de dates dans RankedRequest.
Le champ de date et heure peut également être utilisé dans les fonctions Date-Heure pour analyser et tronquer la date et l’heure de l’événement.

**Période**

La colonne spéciale `daterange` fonctionne de la même manière que `timestamp`. Toutefois, le filtrage est limité à des jours complets. La `daterange` est également facultative et présente les mêmes valeurs par défaut que `timestamp`.
Le champ `daterange` peut également être utilisé dans les fonctions de date et d’heure pour analyser et tronquer la date de l’événement.

**filterId**

La colonne spéciale `filterId`, optionnelle, sert à appliquer à la requête un filtre défini en externe. L’application d’un filtre défini en externe à une requête est similaire au glissement d’un filtre sur un panneau de Workspace. Plusieurs ID de filtre peuvent être fournis (`AND`).

### Clause WHERE

La clause WHERE est traitée en trois étapes :

1. Recherche de la période dans le champ spécial `timestamp`.

2. Recherche de tous les `filterId` définis en externe à inclure dans le filtrage.

3. Conversion des expressions restantes en filtres ad hoc.

La gestion est effectuée en analysant le premier niveau de `AND` dans la clause `WHERE`. Chaque expression de niveau supérieur (avec `AND`) doit correspondre à l’une des expressions ci-dessus. Tout élément, s’il est plus profond que le premier niveau de `AND` ou si la clause `WHERE` utilise `OR` au niveau supérieur, est traité comme un filtre ad hoc.

### ORDER BY

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
| [CAST (Type de colonne AS)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | La diffusion de type n’est pas prise en charge actuellement, mais aucune erreur n’est générée. La fonction `CAST` est ignorée. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analysez une chaîne d’heure en tant que date et heure à utiliser dans une clause `WHERE`. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analysez une chaîne d’heure en tant que date et heure à utiliser dans une clause `WHERE`, en fournissant éventuellement un format pour cette chaîne d’heure. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analysez une chaîne de date en tant que date et heure à utiliser dans une clause `WHERE`. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analysez une chaîne de date en tant que date et heure à utiliser dans une clause `WHERE`, en fournissant éventuellement un format pour cette chaîne de date. |

{style="table-layout:auto"}

### Prise en charge des fonctions de dimension

Ces fonctions peuvent être utilisées sur les dimensions des clauses `SELECT` et `WHERE` ou dans les mesures conditionnelles.

**Fonctions de chaîne**

| Fonction | Exemple | Détails |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Générez une identité de dimension dynamique sur le champ transmis. |

{style="table-layout:auto"}

**Fonctions de date et d’heure**

| Fonction | Exemple | Détails |
|---|---|---|
| [YEAR(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [MONTH(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [DAY(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [DAYOFWEEK(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’identifiant de l’élément au lieu de la valeur, car vous avez besoin du numéro et non du nom convivial. |
| [DAYOFYEAR(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [WEEK(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [QUARTER(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [HOUR(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’identifiant de l’élément au lieu de la valeur, car vous avez besoin du numéro et non du nom convivial. |
| [MINUTE(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [EXTRACT(partie de date FROM ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’ID d’élément au lieu de la valeur de certaines parties de cette fonction, car vous avez besoin du numéro et non du nom convivial.<br/>Les parties prises en charge sont les suivantes :<br>- Mots-clés : `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Chaînes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [DATE_PART(partie, date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’ID d’élément au lieu de la valeur de certaines parties de cette fonction, car vous avez besoin du numéro et non du nom convivial.<br/>Les parties de chaîne prises en charge sont les suivantes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [DATE_TRUNC(granularité, date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis.<br/>Les granularités de chaîne prises en charge sont les suivantes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |

{style="table-layout:auto"}
