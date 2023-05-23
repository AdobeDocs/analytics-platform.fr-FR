---
title: Connecteur SQL
description: Découvrez comment utiliser Query Service, Power BI et/ou Tableau pour accéder aux vues de données à l’aide du connecteur SQL.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 829f7556c731ce55ccf1e03e2dea69b12e4501e4
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 6%

---

# Connecteur SQL

{{release-limited-testing}}

Le [!DNL Customer Journey Analytics (CJA) SQL Connector] permet à SQL d’accéder au [vues de données](./data-views.md) que vous avez défini dans CJA. Il se peut que vos ingénieurs et analystes des données connaissent mieux Power BI, Tableau ou d’autres outils d’intelligence et de visualisation métier (appelés outils de BI). Ils peuvent désormais créer des rapports et des tableaux de bord en fonction des mêmes vues de données que celles utilisées par les utilisateurs de CJA lors de la création de leurs projets Analysis Workspace.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=fr) est l’interface SQL des données disponibles dans le lac de données d’Experience Platform. Avec le [!DNL CJA SQL Connector] activée, fonctionnalité de [!DNL Query Service] est étendu pour afficher vos vues de données CJA sous la forme de tableaux ou de vues dans un [!DNL Query Service] session. Par conséquent, les outils de Business Intelligence qui utilisent [!DNL Query Service] car leur interface PostgresSQL bénéficie en toute transparence de cette fonctionnalité étendue.

Les principaux avantages sont les suivants :

- Il n’est pas nécessaire de recréer une représentation équivalente des vues de données CJA dans l’outil de BI lui-même. <br/>Voir [Vue des données](data-views.md) pour plus d’informations sur les fonctionnalités des vues de données afin de comprendre ce qui doit être recréé.<br/>

- Plus grande cohérence dans les rapports et analyses entre les outils de BI et CJA.

- Combinez les données CJA avec d’autres sources de données déjà disponibles dans les outils de BI.

## Conditions préalables

Pour utiliser cette fonctionnalité, vous devez :

- Activez la variable [!UICONTROL Connecteur SQL CJA] dans votre organisation Experience Platform.

- Configurez la fonctionnalité pour les profils de produits, les groupes d’utilisateurs et/ou les utilisateurs individuels appropriés.<br/>
Les utilisateurs doivent avoir accès aux éléments suivants :
   - Experience Platform Query Service,
   - Projets de l’espace de travail CJA et
   - Consultations des données CJA qu’ils souhaitent utiliser.

- Utilisez expiration sur les informations d’identification non arrivées à expiration pour connecter les outils de BI au connecteur SQL CJA. Thr [Guide d’identification](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) fournit des informations supplémentaires sur la définition des informations d’identification arrivant à expiration ou non arrivant à expiration.

Voir [Contrôle d’accès](../admin/cja-access-control.md) dans la section Administration de CJA pour plus d’informations.


## Utilisation

Pour utiliser la variable [!DNL CJA SQL Connector] , vous pouvez utiliser SQL directement ou utiliser l’expérience de glisser-déposer disponible dans l’outil de BI spécifique.

### SQL

Vous pouvez utiliser cette fonctionnalité directement dans les instructions SQL à l’aide de Query Editor ou d’un client de ligne de commande PostgresSQL standard (CLI).

+++ Requêteur

Dans l’interface utilisateur de l’Experience Platform :

1. Sélectionner **[!UICONTROL ** Requêtes **]** de **[!UICONTROL ** GESTION DES DONNÉES **]** dans le rail de gauche.

2. Sélectionner ![Créer une requête](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Créer une requête **]**.

3. Pour exécuter la requête, saisissez votre instruction SQL et sélectionnez l’événement ![Play](assets/Smock_Play_18_N.svg) (ou appuyez sur MAJ + ENTRÉE).

+++


+++ Interface de ligne de commande PostgresSQL

1. Dans l’interface utilisateur de l’Experience Platform, recherchez et copiez vos informations d’identification PostgresSQL :

   1. Sélectionner **[!UICONTROL ** Requêtes **]** à partir du rail de gauche (sous **[!UICONTROL ** GESTION DES DONNÉES **]**).

   2. Sélectionner **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   3. Pour copier la chaîne de connexion, utilisez ![Copier](assets/Smock_Copy_18_N.svg) dans le **[!UICONTROL ** PSQL, commande **]** .

2. Ouvrez votre interface de ligne de commande PostgresSQL.

3. Pour vous connecter et commencer à exécuter vos requêtes, collez la chaîne de connexion dans l’interface de ligne de commande PostgresSQL.

+++

Voir [Guide de l’interface utilisateur de Query Editor](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) pour plus d’informations.


### Outils BI

Actuellement, le connecteur SQL CJA est pris en charge pour Power BI et Tableau.

+++ Power BI

1. Dans l’interface utilisateur de Adobe Experience Platform, recherchez les détails de vos informations d’identification PostgresSQL.

   1. Sélectionner **[!UICONTROL ** Requêtes **]** à partir du rail de gauche (sous **[!UICONTROL ** GESTION DES DONNÉES **]**).

   2. Sélectionner **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   3. Utilisation ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base], [!UICONTROL Nom d’utilisateur], etc.) en cas de besoin dans Power BI.

2. En Power BI :

   1. Dans la fenêtre principale, sélectionnez **[!UICONTROL ** Obtenir des données **]** dans la barre d’outils supérieure.

   2. Sélectionner **[!UICONTROL ** Plus...**]** dans le rail de gauche.

   3. Dans le **Obtenir des données** écran, recherche `PostgresSQL` et sélectionnez la variable **[!UICONTROL ** Base de données PostgresSQL **]** dans la liste.

   4. Dans le **[!UICONTROL ** Base de données PostgressSQL **]** dialog :

      1. Coller **[!UICONTROL ** Hôte **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] into **[!UICONTROL ** Serveur **]** Champ de texte.

      2. Coller **[!UICONTROL ** Base **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] in **[!UICONTROL ** Base **]** Champ de texte.

         Ajouter `?FLATTEN` au **[!UICONTROL ** Base **]** , il se lit comme suit : `prod:all?FLATTEN` par exemple. Voir [Aplatissement des structures de données imbriquées à utiliser avec des outils de BI tiers](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) pour plus d’informations.

      3. Lorsque vous êtes invité à **[!UICONTROL ** Connectivité des données **]** mode, sélectionnez **[!UICONTROL ** DirectQuery **]** pour s’assurer que les structures de données sont aplaties correctement.

      4. Vous êtes invité à **[!UICONTROL ** Nom d’utilisateur **]** et **[!UICONTROL ** Mot de passe **]**. Utilisation des paramètres équivalents des requêtes Experience Platform [!UICONTROL Informations d’identification].
   5. Une fois la connexion établie, les tableaux Vue des données CJA apparaissent dans le **[!UICONTROL ** Navigateur **]**. Les tableaux de vue de données sont identifiés à l’aide de `dv_` dans leurs noms.


   6. Sélectionnez les tableaux de vue de données à utiliser, puis sélectionnez **[!UICONTROL ** Chargement **]**.

   Toutes les dimensions et mesures associées à un ou plusieurs tableaux sélectionnés apparaissent dans le volet de droite, prêtes à être utilisées dans vos visualisations.

   Voir [Connexion de Power BI à Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) pour plus d’informations.

+++

+++Tableau

1. Dans l’interface utilisateur de l’Experience Platform, recherchez les détails de vos informations d’identification PostgresSQL.

   1. Sélectionner **[!UICONTROL ** Requêtes **]** à partir du rail de gauche (sous **[!UICONTROL ** GESTION DES DONNÉES **]**).

   2. Sélectionner **[!UICONTROL ** Informations d’identification **]** dans la barre supérieure.

   3. Utilisation ![Copier](assets/Smock_Copy_18_N.svg) pour copier chacun des paramètres d’identification Postgres ([!UICONTROL Hôte], [!UICONTROL Port], [!UICONTROL Base], [!UICONTROL Nom d’utilisateur], etc.) si nécessaire dans Tableau.

2. Dans Tableau :

   1. Sélectionner **[!UICONTROL ** Plus **]** de **[!UICONTROL ** Vers un serveur **]** dans le rail de gauche.

   2. Sélectionner **[!UICONTROL ** PostgresSQL **]** dans la liste.

   3. Dans le [!UICONTROL PostgresSQL] dialog :

      1. Coller **[!UICONTROL ** Hôte **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] into **[!UICONTROL ** Serveur **]** Champ de texte.

      2. Coller **[!UICONTROL ** Port **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] into **[!UICONTROL ** Port **]** Champ de texte.

      3. Coller **[!UICONTROL ** Base **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] into **[!UICONTROL ** Base **]** Champ de texte.

         Ajouter `%3FFLATTEN` au **[!UICONTROL ** Base **]** , il se lit comme suit : `prod:all%3FFLATTEN` par exemple. Voir [Aplatissement des structures de données imbriquées à utiliser avec des outils de BI tiers](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) pour plus d’informations.

      4. Sélectionner **[!UICONTROL ** Nom d’utilisateur et mot de passe **]** de **[!UICONTROL ** Authentification **]** liste.

      5. Coller **[!UICONTROL ** Nom d’utilisateur **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] into **[!UICONTROL ** Nom d’utilisateur **]** Champ de texte.

      6. Coller **[!UICONTROL ** Mot de passe **]** Paramètre des requêtes Experience Platform [!UICONTROL Informations d’identification] into **[!UICONTROL ** Mot de passe **]** Champ de texte.

      7. Sélectionner **[!UICONTROL ** Se connecter **]**.
   4. Les vues de données CJA s’affichent sous forme de tableaux dans la variable **[!UICONTROL ** Tableau **]** liste. Les tableaux de vue de données comportent le préfixe `dv_`.

   5. Faites glisser les tableaux à utiliser sur la zone de travail.

   Vous pouvez désormais utiliser les données des tableaux d’affichage de données pour créer vos rapports et visualisations.

   Voir [Connexion de Tableau à Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) pour plus d’informations.

+++

Voir [Connexion des clients à Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) pour une vue d’ensemble des différents outils disponibles et pour plus d’informations.

## Fonction

Par défaut, vos vues de données ont un nom sécurisé généré à partir de leur nom convivial. Par exemple, la vue de données nommée [!UICONTROL Mes données web] possède le nom de la vue `dv_my_web_data`.

Si vous souhaitez utiliser les identifiants de vue de données comme noms de table, vous pouvez ajouter le `CJA_USE_IDS` sur le nom de la base de données lors de la connexion. Par exemple : `prod:all?CJA_USE_IDS` affiche vos vues de données avec des noms tels que `dv_ABC123`.

### Gouvernance des données

Les paramètres liés à la gouvernance des données dans Customer Journey Analytics sont hérités de Adobe Experience Platform. L’intégration entre CJA et la gouvernance de données Adobe Experience Platform permet l’étiquetage des données CJA sensibles et l’application des politiques de confidentialité.

Les étiquettes de confidentialité et les politiques créées sur les jeux de données consommés par Experience Platform peuvent être affichées dans le workflow des vues de données CJA. Par conséquent, les données interrogées à l’aide du connecteur SQL CJA affichent des avertissements ou des erreurs appropriés lorsque vous ne respectez pas les étiquettes et stratégies de confidentialité définies.

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

### Imbriqué et aplati

Par défaut, le schéma de vos vues de données utilise des structures imbriquées, tout comme les schémas XDM d’origine. L’intégration prend également en charge la variable `FLATTEN` . Vous pouvez utiliser cette option pour forcer l’aplatissement du schéma des vues de données (et de tout autre tableau de la session). L’aplatissement permet une utilisation plus facile dans les outils de BI qui ne prennent pas en charge les schémas structurés. Voir [Utilisation de structures de données imbriquées dans Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) pour plus d’informations.

### SQL pris en charge

Voir [Référence SQL de Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) pour obtenir une référence complète sur le type de SQL pris en charge.

Voir le tableau Modèles ci-dessous pour obtenir un aperçu des modèles et des exemples.

+++Modèles

| Modèle | Exemple |
|---|---|
| Découverte de schéma | <pre>SÉLECTIONNEZ * DEPUIS dv1 OÙ 1=0</pre> |
| Classement / Ventilation | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>GROUPE PAR dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39; ET<br/>  filterId = &#39;12345&#39;<br/>GROUPE PAR dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39; ET<br/>  ET (dim2 = &#39;A&#39; OU dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;)<br/>GROUPE PAR dim1</pre> |
| Clause HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>GROUPE PAR dim1<br/>AVANT m1 > 100</pre> |
| Distinct, haut <br/>valeurs de dimension | <pre>SÉLECTIONNEZ DISTINCT dim1 DE dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>GROUPE PAR dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>OÙ \`horodatage\` >= ’2022-01-01’ ET \`horodatage\` &lt; ’2022-01-02’<br/>GROUPE PAR dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Totaux des mesures | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;</pre> |
| Multidimension<br/>ventilations<br/>et segment supérieur | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>GROUPE PAR dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>GROUPE PAR 1, 2<br/>COMMANDER PAR 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Sous-sélection :<br/>Résultat supplémentaire<br/>filtrage | <pre>SELECT dim1, m1<br/>DE (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;</br>  GROUPE PAR dim1<br/>)<br/>OÙ dim1 dans (&#39;A&#39;, &#39;B&#39;)</pre> |
| Sous-sélection :<br/>Rejoindre<br/>jeu de données non dans<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>DE (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>  GROUPE PAR dim1<br/>) a<br/>RECHERCHES DE JOINTURE GAUCHE b SUR a.dim1 = b.key</pre> |
| Sous-sélection :<br/>Requête dans<br/>data-views | <pre>SELECT key, SUM(m1) AS total<br/>DE (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>  GROUPE PAR dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>  GROUPE PAR dim2<br/>GROUP BY key<br/>Total ORDER BY</pre> |
| Sous-sélection : <br/>Source mise en page, <br/>filtrage, <br/>et agrégation | Mise en page à l’aide de sous-sélections :<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>DE (<br/>  SELECT \_.dim1,\_.m1<br/>  DE (<br/>    SÉLECTIONNEZ \* DEPUIS dv1<br/>    OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>  ) \_<br/>  OÙ \_.dim1 dans (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) lignes<br/>GROUPE PAR 1<br/>Total ORDER BY</pre><br/>Calques utilisant CTE AVEC :<br/><pre>Avec des lignes AS (<br/>  AVEC \_ AS (<br/>    SELECT * FROM data_ares<br/>    OÙ \`horodatage\` ENTRE &#39;2021-01-01&#39; ET &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.Units FROM _<br/>  OÙ _.item N’EST PAS NULL<br/>)<br/>SELECT rows.item, SUM(rows.Units) AS Units<br/>À partir des lignes OÙ rows.item dans (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUPE PAR rows.item</pre> |
| Sélectionne l’emplacement où la variable<br/>les mesures sont antérieures à<br/> ou sont mélangés avec<br/>les dimensions | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>OÙ \`horodatage\` ENTRE &#39;2022-01-01&#39; ET &#39;2022-01-02&#39;<br/>GROUPE PAR 2</pre> |

{style="table-layout:auto"}

+++

### Dimensions

Vous pouvez sélectionner l’une des dimensions disponibles par défaut ou définies dans la vue de données. Vous sélectionnez une dimension en fonction de son identifiant.

### Mesures

Les mesures disponibles pour sélection sont les suivantes :

- l’une des mesures disponibles par défaut,

- défini dans la vue de données,

- mesures calculées compatibles avec la vue de données à laquelle l’utilisateur a accès.

Vous sélectionnez une mesure en fonction de son identifiant enveloppé dans une `SUM(metric)` comme vous le feriez avec d’autres sources SQL.

Vous pouvez utiliser:

- `SELECT COUNT(*)` ou `COUNT(1)` pour obtenir la mesure occurrences.

- `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` pour comptabiliser les valeurs distinctes approximatives d’une dimension. Voir les détails dans [Comptage des différences](#counting-distincts).

- [Calculs en ligne](#inline-calculations) pour combiner des mesures à la volée et/ou effectuer des calculs sur celles-ci.

#### Comptage des différences

En raison de la nature sous-jacente du fonctionnement de CJA, la seule dimension pour laquelle vous pouvez obtenir un comptage distinct exact est la `adobe_personid` dimension. Les instructions SQL suivantes `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` renvoient la valeur de la mesure Visiteurs par défaut qui est le nombre de personnes distinctes. Pour les autres dimensions, un nombre distinct approximatif est renvoyé.

#### Mesures conditionnelles

Vous pouvez incorporer une `IF` ou `CASE` dans la section `SUM` ou `COUNT` pour ajouter un filtrage supplémentaire spécifique à une mesure sélectionnée. L’ajout de ces clauses est similaire à l’application d’un filtre à une colonne de mesures dans un tableau de rapport Workspace.

Exemples :

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Calculs en ligne

Vous pouvez appliquer des expressions de mesure supplémentaires dans votre `SELECT` au lieu de définir les maths dans une mesure calculée. Le tableau suivant répertorie les types d’expressions pris en charge.

| Opérateur ou fonction | Détails |
|---|---|
| `+`, `-`, `*`, `/`, et `%` | Ajouter, soustraire, multiplier, diviser et modulaire/reste |
| `-X` ou `+X` | Modification du signe ou d’une mesure où X est l’expression de mesure |
| `PI()` | constant |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, et `TANH` | Fonctions mathématiques unitaires |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Fonctions mathématiques binaires |

{style="table-layout:auto"}

### Colonnes spéciales

**Horodatage**

Le `timestamp` une colonne spéciale est utilisée pour fournir les plages de dates de la requête. Une période peut être définie à l’aide d’une `BETWEEN` expression ou une paire de `timestamp` `>`, `>=`, `<`, `<=` vérifications `AND`ensemble.
Le `timestamp` est facultatif et si aucune plage complète n’est fournie, les valeurs par défaut sont utilisées :

- Si seul un minimum est fourni (`timestamp > X` ou ` timestamp >= X`), la plage est comprise entre X et maintenant.

- Si seul un maximum est fourni (`timestamp < X` ou `timestamp <= X`), la plage est comprise entre X-30 jours et X.

- Si rien n’est indiqué, la période est comprise entre maintenant et 30 jours.

La plage d’horodatage est convertie en filtre global de plage de dates dans RankedRequest.
Le champ d’horodatage peut également être utilisé dans les fonctions Date-Time pour analyser et tronquer l’horodatage de l’événement.

**Période**

Le `daterange` La colonne spéciale fonctionne de la même manière que  `timestamp`, toutefois, le filtrage est limité à des jours complets. Le `daterange` est également facultatif et présente les mêmes valeurs par défaut que `timestamp`.
Le `daterange` peut également être utilisé dans les fonctions de date et d’heure pour analyser et tronquer la date de l’événement.

**filterId**

Le `filterId` une colonne spéciale est optionnelle et sert à appliquer un filtre défini de l&#39;extérieur à la requête. L’application d’un filtre défini en externe à une requête est similaire au fait de faire glisser un filtre sur un panneau de Workspace. Plusieurs ID de filtre peuvent être fournis par `AND`- Je les prends.

### Clause WHERE

La clause WHERE est traitée en trois étapes :

1. Recherchez la période dans la variable `timestamp` champ spécial.

2. Recherche de toute définition en externe `filterId`s à inclure dans le filtrage.

3. Convertissez les expressions restantes en filtres ad hoc.

La gestion est effectuée en analysant le premier niveau de `AND`s dans la variable `WHERE` clause . Chaque niveau supérieur `AND`l’expression ed doit correspondre à l’une des expressions ci-dessus. Tout ce qui est plus profond que le premier niveau de `AND`s, ou, si la variable `WHERE` clause uses `OR`s au niveau supérieur, est traité comme un filtre ad hoc.

### ORDER BY

Par défaut, la requête trie les résultats selon la première mesure sélectionnée dans l’ordre décroissant. Vous pouvez remplacer l’ordre de tri par défaut en spécifiant `ORDER BY ... ASC` ou `ORDER BY ... DESC`. Si vous utilisez `ORDER BY`, vous devez spécifier `ORDER BY` sur la première mesure sélectionnée.

Vous pouvez également retourner l’ordre en utilisant `-` (moins) devant la mesure. Les deux instructions ci-dessous génèrent le même ordre :

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Prise en charge générale des fonctions

| Fonction | Exemple | Détails |
|---|---|---|
| [CAST(type AS de colonne)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | La diffusion de type n’est actuellement pas prise en charge, mais aucune erreur n’est générée. Le `CAST` est ignorée. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analyse d’une chaîne d’heure en tant qu’horodatage à utiliser dans une variable `WHERE` clause . |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analyse d’une chaîne d’heure en tant qu’horodatage à utiliser dans une variable `WHERE` , éventuellement en fournissant un format pour cette chaîne d’heure. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analyse d’une chaîne de date en tant qu’horodatage à utiliser dans une variable `WHERE` clause . |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analyse d’une chaîne de date en tant qu’horodatage à utiliser dans une variable `WHERE` , éventuellement en fournissant un format pour cette chaîne de date. |

{style="table-layout:auto"}

### Prise en charge des fonctions de Dimension

Ces fonctions peuvent être utilisées sur des dimensions dans la variable `SELECT`, `WHERE` ou dans les mesures conditionnelles.

**Fonctions de chaîne**

| Fonction | Exemple | Détails |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Générez une identité de dimension dynamique sur le champ transmis. |

{style="table-layout:auto"}

**Fonctions de date et d’heure**

| Fonction | Exemple | Détails |
|---|---|---|
| [YEAR(date ou date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [MOIS(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [DAY (date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [DAYOFWEEK (date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’identifiant de l’élément au lieu de la valeur, car vous avez besoin du numéro et non du nom convivial. |
| [DAYOFYEAR(date ou date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [SEMAINE(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [TRIMESTRE (date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [HEURE (date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’identifiant de l’élément au lieu de la valeur, car vous avez besoin du numéro et non du nom convivial. |
| [MINUTE(date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. |
| [EXTRACT(partie DE la date ou de la date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’ID d’élément au lieu de la valeur de certaines parties de cette fonction, car vous avez besoin du numéro et non du nom convivial.<br/>Les parties prises en charge sont les suivantes :<br>- Mots-clés : `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Chaînes :  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |
| [DATE_PART(partie, date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis. Utilisez l’ID d’élément au lieu de la valeur de certaines parties de cette fonction, car vous avez besoin du numéro et non du nom convivial.<br/>Les parties de chaîne prises en charge sont les suivantes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |
| [DATE_TRUNC(granularité, date ou date-heure)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Générez une identité de dimension dynamique sur le champ transmis.<br/>Les granularités de chaîne prises en charge sont les suivantes : `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |

{style="table-layout:auto"}

