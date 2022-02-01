---
title: Création ou modification d’une vue de données
description: Tous les paramètres que vous pouvez ajuster pour créer ou modifier une vue de données.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 100%

---

# Création ou modification d’une vue de données

La création dʼune vue de données implique soit la création de mesures et de dimensions à partir dʼéléments de schéma, soit lʼutilisation de composants standard. La plupart des éléments de schéma peuvent être une dimension ou une mesure selon les besoins de votre entreprise. Une fois que vous avez fait glisser un élément de schéma dans une vue de données, des options s’affichent à droite, où vous pouvez ajuster le fonctionnement de la dimension ou de la mesure dans CJA.

## Configuration d’une vue de données

1. Connectez-vous sur [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]**.
2. Cliquez sur **[!UICONTROL Ajouter]** pour créer une vue de données ou cliquez sur une vue de données existante pour la modifier.

![Nouvelle vue de données](assets/new-data-view.png)

### Paramètres de la vue de données

Fournit des paramètres globaux pour la vue de données.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Connexion] | Ce champ relie la vue de données à la connexion que vous avez établie précédemment, qui contient un ou plusieurs jeux de données Adobe Experience Platform. |
| [!UICONTROL Nom] | Obligatoire. Nom de la vue de données. Cette valeur apparaît dans la liste déroulante supérieure droite d’Analysis Workspace. |
| [!UICONTROL Description] | Facultatif. Adobe recommande une description détaillée afin que les utilisateurs comprennent pourquoi la vue de données existe et pour qui elle a été conçue. |

### Conteneurs

Désigne le nom des conteneurs pour la vue de données. Les noms de conteneur sont fréquemment utilisés dans [Filtres](/help/components/filters/filters-overview.md#Filter-containers).

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Nom du conteneur de personnes] | [!UICONTROL Personne] (par défaut). Le conteneur [!UICONTROL Personne] inclut chaque session et événement pour les visiteurs au cours dʼune période indiquée. Si votre organisation utilise un autre terme (par exemple, « Visiteur » ou « Utilisateur »), vous pouvez renommer le conteneur ici. |
| [!UICONTROL Nom du conteneur de sessions] | [!UICONTROL Session] (par défaut). Le conteneur [!UICONTROL Session] permet dʼidentifier les interactions de pages, les campagnes ou les conversions pour une session spécifique. Vous pouvez renommer ce conteneur en « Visite » ou tout autre terme de votre choix. |
| [!UICONTROL Nom du conteneur d’événements] | [!UICONTROL Événement] (par défaut). Le conteneur [!UICONTROL Événement] définit des événements individuels dans un jeu de données. Si votre organisation utilise un autre terme (par exemple, « Accès » ou « Pages vues »), vous pouvez renommer le conteneur ici. |

### Calendrier

Indique le format du calendrier que la vue de données doit suivre. Vous pouvez avoir plusieurs vues de données basées sur la même [connexion](/help/connections/create-connection.md) et leur donner différents types de calendrier ou fuseaux horaires. Ces vues de données peuvent permettre aux équipes qui utilisent différents types de calendrier de répondre à leurs besoins respectifs avec les mêmes données sous-jacentes.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Fuseau horaire] | Choisissez le fuseau horaire dans lequel vous souhaitez que vos données soient présentées. Si vous choisissez un fuseau horaire qui fonctionne à l’heure d’été, les données sont automatiquement ajustées pour refléter cette situation. Au printemps, lorsque les horloges avancent d’une heure, un intervalle d’une heure est présent. À l’automne, lorsque les horloges reculent d’une heure, une heure est répétée pendant le changement d’heure. |
| [!UICONTROL Type de calendrier] | Déterminez comment les semaines du mois sont regroupées.<br>**Grégorien :** format de calendrier standard. Les trimestres sont regroupés par mois.<br>**Vente au détail 4-5-4 :** un calendrier de vente au détail 4-5-4 normalisé. Les premier et dernier mois du trimestre contiennent 4 semaines, tandis que le deuxième mois du trimestre contient 5 semaines.<br>**Personnalisé (4-5-4) :** similaire au calendrier 4-5-4, sauf que vous pouvez choisir le premier jour de l’année et l’année où la semaine « supplémentaire » se produit.<br>**Personnalisé (4-4-5) :** les premier et deuxième mois de chaque trimestre contiennent 4 semaines, tandis que la dernière semaine de chaque trimestre contient 5 semaines.<br>**Personnalisé (5-4-4) :** le premier mois de chaque trimestre contient 5 semaines, tandis que le deuxième et le troisième mois de chaque trimestre contient 4 semaines. |
| [!UICONTROL Premier mois de l’année] et [!UICONTROL premier jour de la semaine] | Visible pour le type de calendrier grégorien. Indiquez le mois où vous souhaitez que l’année civile commence et le jour où vous souhaitez que chaque semaine commence. |
| [!UICONTROL Premier jour de l’année en cours] | Visible pour les types de calendrier personnalisés. Indiquez le jour de l’année où vous souhaitez que l’année en cours commence. Le calendrier formate automatiquement le premier jour de chaque semaine en fonction de cette valeur. |
| [!UICONTROL Année au cours de laquelle la semaine « supplémentaire » a lieu] | Avec la plupart des calendriers de 364 jours (52 semaines de 7 jours chacune), chaque année accumule les jours restants jusqu’à ce qu’ils forment une semaine supplémentaire. Cette semaine supplémentaire est alors ajoutée au dernier mois de cette année. Indiquez à quelle année vous souhaitez ajouter la semaine supplémentaire. |

## Définition des composants d’une vue de données

Vous pouvez ensuite créer des mesures et des dimensions à partir dʼéléments de schéma. Vous pouvez également utiliser des composants standard.

1. Connectez-vous sur [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]**.
1. Cliquez sur **[!UICONTROL Ajouter]** pour créer une vue de données ou cliquez sur une vue de données existante pour la modifier.
1. Cliquez sur l’onglet **[!UICONTROL Composants]**.

   ![Onglet Composants](assets/components-tab.png)

   Vous pouvez voir la [!UICONTROL connexion] en haut à gauche qui contient les jeux de données et ses [!UICONTROL champs de schéma] en dessous. Notez que les composants déjà inclus sont des composants standard requis (générés par le système) pour toutes les vues de données. Par défaut, Adobe applique le filtre **[!UICONTROL Contient des données]**. Ainsi, seuls les champs de schéma contenant des données apparaissent. Si vous souhaitez un champ qui ne contient pas de données, supprimez ce filtre.

1. Faites maintenant glisser un champ de schéma, tel que `pageTitle` du rail de gauche vers la section Mesures ou Dimensions.

   Vous pouvez faire glisser plusieurs fois le même champ de schéma vers les sections des dimensions ou des mesures et configurer la même dimension ou mesure de différentes manières. Par exemple, à partir du champ `pageTitle`, vous pouvez créer une dimension appelée « Pages de produits » et une autre « Pages dʼerreurs », en utilisant différents [Paramètres de composant](component-settings/overview.md) à droite.

   ![Tabulation 3](assets/components-tab-3.png)

   Si vous faites glisser un dossier de champ de schéma depuis le rail de gauche, il est automatiquement classé dans les sections standard. Les champs de chaîne se retrouvent dans la section [!UICONTROL Dimensions] et les types de schémas numériques se retrouvent dans la section [!UICONTROL Mesures]. Vous pouvez également cliquer sur **[!UICONTROL Ajouter tout]** et tous les champs de schéma sont ajoutés à leurs emplacements respectifs.

1. Une fois le composant sélectionné, plusieurs paramètres sʼaffichent sur la droite. Configurez le composant à l’aide des [paramètres du composant](component-settings/overview.md). Les paramètres de composant disponibles dépendent du fait que le composant soit une dimension/mesure et du type de données de schéma. Les paramètres incluent :

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Comportement]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Inclure/Exclure les valeurs]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Déduplication des mesures]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Pas d’option de valeur]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistance]](component-settings/persistence.md)
   * [[!UICONTROL Classification des valeurs]](component-settings/value-bucketing.md)

## Dupliquer les mesures ou les dimensions

La duplication des mesures ou des dimensions ainsi que la modification ultérieure des paramètres spécifiques est un moyen facile de créer plusieurs mesures ou dimensions à partir d’un seul champ de schéma. Sélectionnez tout simplement le paramètre [!UICONTROL Dupliquer] sous le nom de la mesure ou de la dimension en haut à droite. Ensuite, modifiez la nouvelle mesure ou dimension et enregistrez-la sous un nom plus explicite.

![Dupliquer](assets/duplicate.png)

## Filtrer les champs de schéma ou les jeux de données

Vous pouvez filtrer les champs de schéma dans le rail gauche à l’aide des types de données suivants :

![Champs de filtrage](assets/filter-fields.png)

Vous pouvez également filtrer par jeux de données et selon quʼun champ de schéma contient des données ou quʼil sʼagit dʼune identité. Par défaut, Adobe applique le filtre **[!UICONTROL Contient des données]** à toutes les vues de données.

![Filtrer les autres](assets/filter-other.png)

## Paramètres onglet

1. Connectez-vous sur [Customer Journey Analytics](https://analytics.adobe.com) et accédez à l’onglet **[!UICONTROL Vues de données]**.
1. Cliquez sur **[!UICONTROL Ajouter]** pour créer une vue de données ou cliquez sur une vue de données existante pour la modifier.
1. Cliquez sur l’onglet **[!UICONTROL Paramètres]**.

### Filtre global

Vous pouvez ajouter des filtres qui sʼappliquent à lʼensemble de votre vue de données. Ce filtre sera appliqué à tout rapport exécuté dans Espace de travail. Faites glisser un filtre de la liste du rail de gauche vers le champ [!UICONTROL Ajouter des filtres].

### Paramètres de session

Déterminez la période d’inactivité entre les événements avant l’expiration d’une session et le début d’une nouvelle session.

Une période est requise. Vous pouvez également forcer le démarrage d’une nouvelle session lorsqu’un événement contient une mesure spécifique.

Une fois tous les paramètres spécifiés, cliquez sur **[!UICONTROL Enregistrer et terminer]**.
