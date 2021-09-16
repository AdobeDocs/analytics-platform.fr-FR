---
title: Création ou modification d’une vue de données
description: Tous les paramètres que vous pouvez ajuster pour créer ou modifier une vue de données.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 384679788d140a01a12e1c830b47099398a920b1
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 18%

---

# Création ou modification d’une vue de données

La création dʼune vue de données implique soit la création de mesures et de dimensions à partir dʼéléments de schéma, soit lʼutilisation de composants standard. La plupart des éléments de schéma peuvent être une dimension ou une mesure selon les besoins de votre entreprise. Une fois que vous avez fait glisser un élément de schéma dans une vue de données, des options s’affichent à droite, où vous pouvez ajuster le fonctionnement de la dimension ou de la mesure dans CJA.

## Configuration d’une vue de données

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]** .
2. Cliquez sur **[!UICONTROL Ajouter]** pour créer une vue de données ou cliquez sur une vue de données existante pour la modifier.

![Nouvelle vue de données](assets/new-data-view.png)

### Paramètres

Fournit des paramètres globaux pour la vue de données.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Connexion] | Ce champ relie la vue de données à la connexion que vous avez établie précédemment, qui contient un ou plusieurs jeux de données Adobe Experience Platform. |
| [!UICONTROL Nom] | Obligatoire. Nom de la vue de données. Cette valeur apparaît dans la liste déroulante supérieure droite d’Analysis Workspace. |
| [!UICONTROL Description] | Facultatif. Adobe recommande une description détaillée afin que les utilisateurs comprennent pourquoi la vue de données existe et à qui elle est conçue. |

### Conteneurs

Désigne le nom des conteneurs pour la vue de données. Les noms de conteneur sont fréquemment utilisés dans [Filtres](/help/components/filters/filters-overview.md#Filter-containers).

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Nom du conteneur de personnes] | [!UICONTROL Personne] (par défaut). Le conteneur [!UICONTROL Personne] inclut chaque session et événement pour les visiteurs au cours de la période spécifiée. Si votre organisation utilise un autre terme (par exemple, &quot;Visiteur&quot; ou &quot;Utilisateur&quot;), vous pouvez renommer le conteneur ici. |
| [!UICONTROL Nom du conteneur de sessions] | [!UICONTROL Session] (par défaut). Le conteneur [!UICONTROL Session] permet dʼidentifier les interactions de pages, les campagnes ou les conversions pour une session spécifique. Vous pouvez renommer ce conteneur en &quot;Visite&quot; ou tout autre terme préféré par votre organisation. |
| [!UICONTROL Nom du conteneur d’événements] | [!UICONTROL Événement] (par défaut). Le conteneur [!UICONTROL Événement] définit des événements individuels dans un jeu de données. Si votre organisation utilise un autre terme (par exemple, &quot;Accès&quot; ou &quot;Pages vues&quot;), vous pouvez renommer le conteneur ici. |

### Calendrier

Indique le format du calendrier que la vue de données doit suivre. Vous pouvez avoir plusieurs vues de données basées sur la même [connexion](/help/connections/create-connection.md) et leur donner différents types de calendrier ou fuseaux horaires. Ces vues de données peuvent permettre aux équipes qui utilisent différents types de calendrier de répondre à leurs besoins respectifs avec les mêmes données sous-jacentes.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Fuseau horaire] | Choisissez le fuseau horaire dans lequel vous souhaitez que vos données soient présentées. Si vous choisissez un fuseau horaire qui fonctionne à l’heure d’été, les données sont automatiquement ajustées pour refléter cette situation. Au printemps, lorsque les horloges s&#39;ajustent une heure à l&#39;avance, un intervalle d&#39;une heure est présent. À l’automne, lorsque les horloges prennent une heure de retard, une heure est répétée pendant le décalage de l’heure d’été. |
| [!UICONTROL Type de calendrier] | Déterminez comment les semaines du mois sont regroupées.<br>**Grégorien :** format de calendrier standard. Les trimestres sont regroupés par mois.<br>**4-5-4 Vente au détail :** un calendrier de vente au détail 4-5-4 normalisé. Les premier et dernier mois du trimestre comprennent 4 semaines, tandis que le deuxième mois du trimestre comprend 5 semaines.<br>**Personnalisé (4-5-4) :** similaire au calendrier 4-5-4, sauf que vous pouvez choisir le premier jour de l’année et l’année où la semaine &quot;supplémentaire&quot; se produit.<br>**Personnalisé (4-4-5) :**  les premier et deuxième mois de chaque trimestre comprennent 4 semaines, tandis que la dernière semaine de chaque trimestre comprend 5 semaines.<br>**Personnalisé (5-4-4) :** le premier mois de chaque trimestre comprend 5 semaines, tandis que le deuxième et le troisième mois de chaque trimestre comprend 4 semaines. |
| [!UICONTROL Premier mois de l’] année et  [!UICONTROL premier jour de la semaine] | Visible pour le type de calendrier grégorien. Indiquez le mois où vous souhaitez que l’année civile commence et le jour où vous souhaitez que chaque semaine commence. |
| [!UICONTROL Premier jour de l’année en cours] | Visible pour les types de calendrier personnalisés. Indiquez le jour de l’année où vous souhaitez que l’année en cours commence. Le calendrier formate automatiquement le premier jour de chaque semaine en fonction de cette valeur. |
| [!UICONTROL Année au cours de laquelle la semaine « supplémentaire » a lieu] | Avec la plupart des calendriers de 364 jours (52 semaines de 7 jours chacune), chaque année accumule les jours restants jusqu’à ce qu’ils forment une semaine supplémentaire. Cette semaine supplémentaire est alors ajoutée au dernier mois de cette année. Indiquez à quelle année vous souhaitez ajouter la semaine supplémentaire. |

## Définition des composants d’une vue de données

Vous pouvez ensuite créer des mesures et des dimensions à partir dʼéléments de schéma. Vous pouvez également utiliser des composants standard.

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]** .
1. Cliquez sur **[!UICONTROL Ajouter]** pour créer une vue de données ou cliquez sur une vue de données existante pour la modifier.
1. Cliquez sur l’onglet **[!UICONTROL Composants]** .

![Onglet Composants](assets/components-tab.png)

Vous pouvez voir la [!UICONTROL connexion] en haut à gauche qui contient les jeux de données et ses [!UICONTROL champs de schéma] en dessous. Gardez les éléments suivants à l’esprit :

    * Les composants déjà inclus sont les composants standard requis (générés par le système).
    * Adobe applique le filtre **[!UICONTROL Contient des données]** par défaut, de sorte que seuls les champs de schéma contenant des données s’affichent. Si vous recherchez un champ qui ne contient pas de données, supprimez le filtre.

1. Faites glisser un champ de schéma, tel que `pageTitle`, depuis le rail de gauche vers la section Mesures ou Dimensions .

   Vous pouvez faire glisser plusieurs fois le même champ de schéma vers les sections des dimensions ou des mesures et configurer la même dimension ou mesure de différentes manières. Par exemple, à partir du champ `pageTitle` , vous pouvez créer une dimension appelée &quot;Pages de produits&quot;, et une autre &quot;Pages d’erreur&quot;, en utilisant différents [paramètres de composant](component-settings/overview.md) sur la droite.

   ![Onglet 3](assets/components-tab-3.png)

   Si vous faites glisser un dossier de champ de schéma depuis le rail de gauche, il est automatiquement trié en sections standard. Les champs de chaîne se retrouvent dans la section [!UICONTROL Dimensions] et les types de schémas numériques se retrouvent dans la section [!UICONTROL Mesures] . Vous pouvez également cliquer sur **[!UICONTROL Ajouter tout]** et tous les champs de schéma sont ajoutés à leurs emplacements respectifs.

1. Une fois que vous avez sélectionné le composant, plusieurs paramètres s’affichent à droite. Configurez le composant à l’aide des [paramètres du composant](component-settings/overview.md). Les paramètres de composant disponibles dépendent si le composant est une dimension/mesure et le type de données de schéma. Les paramètres incluent :

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Comportement]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Inclure/Exclure les valeurs]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Déduplication des mesures]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Pas d’option de valeur]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistance]](component-settings/persistence.md)
   * [[!UICONTROL Classification des valeurs]](component-settings/value-bucketing.md)

Si nécessaire, vous pouvez utiliser les fonctionnalités suivantes :

* **[!UICONTROL Dupliquer]** : La duplication de mesures ou de dimensions, puis la modification de paramètres spécifiques, est un moyen facile de créer plusieurs mesures ou dimensions à partir d’un seul champ de schéma. Sélectionnez le paramètre [!UICONTROL Dupliquer] sous le nom de la mesure ou des dimensions en haut à droite. Modifiez la nouvelle dimension ou mesure et enregistrez-la sous un nom plus explicite.

   ![Dupliquer](assets/duplicate.png)

* **[!UICONTROL Filtre]** : Vous pouvez filtrer les champs de schéma dans le rail de gauche selon les types de données suivants :

   ![Champs de filtrage](assets/filter-fields.png)

   Vous pouvez également filtrer par jeux de données et selon quʼun champ de schéma contient des données ou quʼil sʼagit dʼune identité. Par défaut, Adobe applique initialement le filtre **[!UICONTROL Contient les données]** à toutes les vues de données.

   ![Filtrer les autres](assets/filter-other.png)

## Paramètres

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]** .
1. Cliquez sur **[!UICONTROL Ajouter]** pour créer une vue de données ou cliquez sur une vue de données existante pour la modifier.
1. Cliquez sur l’onglet **[!UICONTROL Paramètres]** .

### Filtre global

Vous pouvez ajouter des filtres qui s’appliquent à une vue de données entière. Ce filtre est appliqué à tout rapport exécuté dans Workspace. Faites glisser un filtre de la liste du rail de gauche vers le champ [!UICONTROL Ajouter des filtres].

### Paramètres de session

Déterminez la période d’inactivité entre les événements avant l’expiration d’une session et le début d’une nouvelle session.

Une période est requise. Vous pouvez également forcer le démarrage d’une nouvelle session lorsqu’un événement contient une mesure spécifique.

Une fois tous les paramètres spécifiés, cliquez sur **[!UICONTROL Enregistrer et terminer]**.
