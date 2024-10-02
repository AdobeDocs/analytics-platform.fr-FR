---
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '3646'
ht-degree: 34%

---
# Extraits

## Phase de tests limités de publication {#release-limited-testing}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités du Customer Journey Analytics](/help/release-notes/releases.md).

## Section Phase de tests limités de publication {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cette section se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de mise à jour du Customer Journey Analytics, voir [Versions des fonctionnalités du Customer Journey Analytics](/help/release-notes/releases.md).

## Sélectionner un package {#select-package}

>[!NOTE]
>
>Pour utiliser la fonctionnalité décrite dans cette section, vous devez disposer du package **Select** ou d’une version ultérieure. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

## Package Prime {#prime-package}

>[!NOTE]
>
>Pour utiliser la fonctionnalité décrite dans cette section, vous devez disposer du package **Prime** ou d’une version ultérieure. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.

## Package Ultimate {#ultimate-package}

>[!NOTE]
>
>Vous devez disposer du package **Ultimate** pour utiliser la fonctionnalité décrite dans cette section. Contactez votre administrateur ou administratrice si vous ne savez pas de quel package Customer Journey Analytics vous disposez.


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
| [!UICONTROL **Approuvés**] | <p>Indique que le composant a été révisé et approuvé par l’administration.</p><p>Les administrateurs voient une option pour [!UICONTROL **Ne plus approuver**]. La sélection de cette option marque le composant comme &quot;Non approuvé&quot; pour les utilisateurs.</p> |
| [!UICONTROL **Non approuvé**] | <p>Indique que le composant n’a pas encore été révisé et approuvé par l’administration.</p><p>Un bouton dédié permet à l’administration d’[!UICONTROL **Approuver**] le composant. Celui-ci est alors marqué comme « Approuvé » pour les utilisateurs et utilisatrices.</p> |
| [!UICONTROL **Description**] | Décrit la fonction prévue du composant. (Ces informations sont ajoutées par l’administration Analytics, comme décrit dans la section [Ajouter des descriptions de composant](/help/components/add-component-descriptions.md)). |
| [!UICONTROL **Fréquemment utilisé avec**] | <p>Affiche les composants les plus couramment utilisés avec le composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants sont affichés dans les 5 types de composants principaux : Mesure, Mesure calculée, Dimension, Filtre et Période.</p><p>Cette liste est basée sur les données des 90 derniers jours. Seuls les composants que vous êtes en droit de consulter s’affichent.</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Avant de traiter les composants que les utilisateurs voient, appliquez d&#39;abord le filtre **Tout afficher** pour vous assurer que vous voyez tous les composants qui ne sont pas partagés avec vous et qui peuvent avoir été ajoutés par un autre administrateur.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similaire à**] | <p>Permet d’afficher les composants dotés de noms similaires au composant que vous visualisez actuellement.</p><p>Jusqu’à 5 composants sont affichés dans les 5 types de composants principaux : Mesure, Mesure calculée, Dimension, Filtre et Période.</p><p>Seuls les composants que vous êtes en droit de consulter s’affichent.</p><p>Tous les composants en double dans votre vue de données s’affichent ici. L’administration d’Analytics doit identifier et supprimer tous les composants en double, comme décrit dans la section [Surveiller l’intégrité du dictionnaire de données](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>L’administration peut personnaliser les composants visibles par les utilisateurs et utilisatrices au sein de cette section en sélectionnant les composants souhaités dans les champs déroulants [!UICONTROL **Toujours inclure**] et [!UICONTROL **Toujours exclure**]. Avant de traiter les composants que les utilisateurs voient, appliquez d&#39;abord le filtre **Tout afficher** pour vous assurer que vous voyez tous les composants qui ne sont pas partagés avec vous et qui peuvent avoir été ajoutés par un autre administrateur.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Remarque :** actuellement, la section **Similaire à** comprend uniquement les composants que vous créez, et non ceux fournis par Adobe. Les composants fournis par Adobe seront ajoutés dans une version ultérieure.</p> |
| [!UICONTROL **Compatibilité des produits**] | Indique où cette mesure calculée peut être utilisée en Customer Journey Analytics. <p>Les valeurs possibles sont les suivantes :</p><ul><li>[!UICONTROL **Partout dans Customer Journey Analytics**] : la mesure calculée peut être utilisée dans tous les Customer Journey Analytics, y compris dans Analysis Workspace, Report Builder, etc.</li><li>[!UICONTROL **Partout en Customer Journey Analytics (hors expérimentation)**] : la mesure calculée peut être utilisée dans tous les Customer Journey Analytics, à l’exception du panneau Expérience.</li> <p>Pour plus d’informations sur les critères qui déterminent si une mesure calculée peut être utilisée avec l’expérimentation, voir [ Utilisation des mesures calculées dans le panneau Expérience](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) dans le [panneau Expérience](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Balises**] | Affiche toutes les balises associées au composant. L’administration peut ajouter des balises lors de la modification du composant. |
| [!UICONTROL **Type de composant**] | Répertorie le type de composant qu’il est, qu’il s’agisse d’une Dimension, d’une mesure, d’un filtre ou d’une plage de dates. |
| [!UICONTROL **Créé par**] | Affiche le nom de l’utilisateur ou de l’utilisatrice ayant créé le composant. |
| [!UICONTROL **Aperçu**] | Affiche un aperçu de l’apparence du composant dans Analysis Workspace. |
| [!UICONTROL **Date de la dernière modification**] | Affiche le jour de la dernière modification du composant. Cette section s’affiche lors de l’affichage des options Filtres, Mesures, Mesures calculées et Périodes. |

{style="table-layout:auto"}

## Options de tri des composants {#components-sort-options}

| Option | Fonction |
|---------|----------|
| **[!UICONTROL Recommandé]** | Triez les composants pour chaque type (dimension, mesure, filtre et période) selon leur recommandation. Les composants utilisés le plus fréquemment et le plus récemment par vous ou par d’autres membres de votre organisation s’affichent plus haut dans chaque liste. |
| **[!UICONTROL Dernière modification]** | Triez les composants pour chaque type (dimension, mesure, filtre et période) en fonction de leur date de dernière modification. Les composants modifiés le plus récemment apparaissent plus haut dans chaque liste. |
| **[!UICONTROL Alphabétique]** | Triez les composants pour chaque type (dimension, mesure, filtre et période) par ordre alphabétique croissant. |
| **[!UICONTROL Catégorique]** | Triez les composants pour chaque type (dimension, mesure, filtre et période) en fonction de leur catégorie. Par exemple, les composants d’affichage de données traités et non traités. |

{style="table-layout:auto"}

## Comparaison de temps {#apply-time-comparison}

Vous pouvez comparer la période actuelle à une période précédente. Si vous sélectionnez une option dans ce menu, chaque point de données reçoit une contrepartie pointillée de couleur similaire. Cette contrepartie représente la même mesure dans la période précédente sélectionnée. Cette option double le nombre d’éléments du graphique et des lignes du tableau.

Les options de comparaison de temps disponibles comprennent la période précédente, 13 semaines précédentes, 52 semaines précédentes et une période personnalisée. Si vous sélectionnez Période personnalisée, d’autres options s’affichent pour vous permettre de sélectionner le nombre et la granularité. Si vous sélectionnez Aucun, la comparaison de dates est supprimée.


## Vidéo de démonstration Adobe Analytics {#videoaa}

Cette vidéo présente les fonctionnalités d’Adobe Analytics. Toutefois, la fonctionnalité est également disponible dans Customer Journey Analytics. Gardez à l’esprit les différences suivantes en termes de terminologie.

| Adobe Analytics | Customer Journey Analytics |
|:---:|:---:|
| Segments | Filtres |
| Visiteur | Personne |
| Visite | Session |
| Accès | Événement |


## Panneau Filtres {#filterspanel}

1. Sélectionnez ![Filter](/help/assets/icons/Filter.svg) pour ouvrir le panneau Filtres. Si vous avez besoin d’espace supplémentaire pour la liste Filtres, vous pouvez sélectionner à nouveau ![Filtre](/help/assets/icons/Filter.svg) pour fermer le panneau.
1. Sélectionnez des filtres dans l’une des sections de filtre disponibles.


## Section Filtre de balise {#tagfiltersection}

| Balises | Description |
|---|---|
| ![Balises](/help/assets/filter-tag.png){width="300"} | La section **[!UICONTROL Balises]** vous permet de filtrer par balises. <ul><li>Vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des balises* pour rechercher des balises que vous pouvez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs balises. Les balises disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent :<ul><li>**(1)** : nombre de balises sélectionnées (si une ou plusieurs balises sont sélectionnées).</li><li>**2︎⃣** : nombre de balises disponibles pour les éléments résultant du filtre actuel.</li><li>7︎⃣ : nombre d’éléments associés à la balise spécifique.</li></ul></li></ul> |


## Section Filtre de vue de données {#dataviewfiltersection}

| Vue de données | Description |
|---|---|
| ![Vues de données](/help/assets/filter-dataview.png){width="300"} | La section **[!UICONTROL Vue des données]** vous permet de filtrer les données selon les vues. <ul><li>Vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des vues de données* pour rechercher des vues de données que vous pouvez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs vues de données. Les vues de données disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent :<ul><li>**(2)** : nombre de vues de données sélectionnées (si une ou plusieurs vues de données sont sélectionnées).</li><li>**3︎⃣** : nombre de vues de données disponibles pour les éléments résultant du filtre actuel.</li><li>4︎⃣ : nombre d’éléments associés à la vue de données spécifique.</li></ul></li></ul> |

## Section Filtre d’état activé {#enabledstatusfiltersection}

| État activé | Description |
|---|---|
| ![État activé](/help/assets/filter-enabledstatus.png){width="300"} | La section **[!UICONTROL État activé]** vous permet de filtrer selon l’état activé. <ul><li>Vous pouvez sélectionner plusieurs états.</li><li>Les chiffres indiquent :<ul><li>**(2)** : nombre d’états sélectionnés (si un ou plusieurs états sont sélectionnés).</li><li>**2︎⃣** : nombre d’états disponibles pour les éléments résultant du filtre actuel.</li><li>1︎⃣ : nombre d’éléments associés à l’état spécifique.</li></ul></li></ul> |

## Section Filtre de type {#typefiltersection}

| Type | Description |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | La section **[!UICONTROL Type]** vous permet de filtrer par type. <ul><li>Vous pouvez sélectionner plusieurs types.</li><li>Les chiffres indiquent :<ul><li>**(2)** : nombre de types sélectionnés (si un ou plusieurs types sont sélectionnés).</li><li>**1︎⃣** : nombre de types disponibles pour les éléments résultant du filtre actuel.</li><li>3︎⃣ : nombre d’éléments associés au type spécifique.</li></ul></li></ul> |

## Section Filtre du propriétaire {#ownerfiltersection}

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/assets/filter-owners.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des propriétaires* pour rechercher des propriétaires que vous pouvez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. Les propriétaires disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent :<ul><li>**(2)** : nombre de propriétaires sélectionnés (si un ou plusieurs propriétaires sont sélectionnés).</li><li>**3︎⃣** : nombre de propriétaires disponibles pour les éléments résultant du filtre actuel.</li><li>4︎⃣ : nombre d’éléments associés au propriétaire spécifique.</li></ul></li></ul> |

## Section Autres filtres {#otherfiltersfiltersection}

| Autres filtres | Description |
|---|---|
| ![Autres filtres](/help/assets/filter-other.png){width="300"} | La section **[!UICONTROL Autres filtres]** vous permet de filtrer selon d’autres filtres prédéfinis.<ul><li>Vous pouvez sélectionner une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Tout afficher]**</li><li>**[!UICONTROL Partagé avec moi]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approuvés]**</li><li>**[!UICONTROL Favoris]**</li></ul> Ce que vous pouvez sélectionner dépend de votre rôle et de vos autorisations.</li><li>Vous pouvez sélectionner plusieurs autres filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtres.</li><li>Les chiffres indiquent :<ul><li>**(1)** : nombre d’autres filtres sélectionnés (si un ou plusieurs autres filtres sont sélectionnés).</li><li>**5︎⃣** : nombre d’autres filtres disponibles pour les éléments résultant du filtre actuel.</li><li>4︎⃣ : nombre d’éléments associés à l’autre filtre spécifique.</li></ul></li></ul> |

## Section Filtre de période  {#daterangefiltersection}

| Période appliquée | Description |
|---|---|
| ![Période](/help/assets/filter-daterange.png){width="300"} | La section Période appliquée vous permet de filtrer les données selon une période applicable aux éléments.<ol><li>Sélectionnez une plage de dates.</li><li>Dans la fenêtre contextuelle du calendrier, définissez une période ou sélectionnez l’un des paramètres prédéfinis disponibles.<br>Vous pouvez également spécifier une période directement dans la section Période du panneau Filtre.</li></ol><ul><li>Les chiffres indiquent :<ul><li>**(1)** : nombre de périodes modifiées à partir des paramètres prédéfinis par défaut.</li><li>**5︎⃣** : nombre de plages de dates disponibles pour les éléments résultant du filtre actuel.</li></ul> |


## Modèles d’attribution {#attribution-models-details}

Un modèle d’attribution détermine les éléments de dimension qui reçoivent du crédit pour une mesure lorsque plusieurs valeurs sont affichées dans l’intervalle de recherche en amont d’une mesure. Les modèles d’attribution ne s’appliquent que lorsque plusieurs éléments de dimension sont définis dans l’intervalle de recherche en amont. Si un seul élément de dimension est défini, celui-ci obtient un crédit de 100 %, quel que soit le modèle d’attribution utilisé.

| Icône | Modèle d’attribution | Définition |
| :---: | :--- | --- |
| ![Dernière touche](/help/assets/icons/AttributeLastTouch.svg) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. Ce modèle d’attribution est généralement la valeur par défaut d’une mesure pour laquelle aucun modèle d’attribution n’est spécifié autrement. Les entreprises utilisent généralement ce modèle lorsque le temps de conversion est relativement court, comme lors de l’analyse des mots-clés de recherche interne. |
| ![Première touche](/help/assets/icons/AttributeFirstTouch.svg) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont des attributions. Les entreprises utilisent généralement ce modèle pour comprendre la notoriété de la marque ou l’acquisition de clients. |
| ![Linéaire](/help/assets/icons/AttributeLinear.svg) | Linéaire | Attribue le même crédit à chaque point de contact affiché menant à une conversion. Elle s’avère utile lorsque les cycles de conversion sont plus longs ou nécessitent un engagement plus fréquent de la part des clients. Les entreprises utilisent généralement ce modèle d’attribution qui mesure l’efficacité des notifications d’applications mobiles ou avec des produits par abonnement. |
| ![Participation](/help/assets/icons/AttributeParticipation.svg) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Chaque point de contact recevant un crédit de 100 %, les données de mesure s’élèvent généralement à plus de 100 %. Si un élément de dimension apparaît plusieurs fois, ce qui entraîne une conversion, les valeurs sont dédupliquées à 100 %. Ce modèle d’attribution est idéal lorsque vous souhaitez identifier les points de contact les plus exposés. Les organisations multimédias utilisent généralement ce modèle pour calculer la vitesse du contenu. Les entreprises de vente au détail utilisent généralement ce modèle pour déterminer les parties de leur site qui sont essentielles à la conversion. |
| ![Même touche](/help/assets/icons/AttributeSameTouch.svg) | Même touche | Attribue un crédit de 100 % au même événement que celui où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même événement qu’une conversion, il est placé sous &quot;Aucun&quot;. Ce modèle d’attribution est parfois assimilé à l’absence de modèle d’attribution. Elle s’avère utile dans les cas où vous ne souhaitez pas que les valeurs d’autres événements affectent la manière dont une mesure accorde du crédit aux éléments de dimension. Les équipes produit ou de conception peuvent utiliser ce modèle pour évaluer l’efficacité d’une page où une conversion se produit. |
| ![En forme de U](/help/assets/icons/AttributeUShaped.svg) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est attribué aux deux. Ce modèle d’attribution est mieux utilisé dans les scénarios où vous évaluez le plus les premières et les dernières interactions, mais ne souhaitez pas entièrement ignorer les interactions supplémentaires entre les deux. |
| ![Courbe J](/help/assets/icons/AttributeJCurve.svg) | Courbe en J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la dernière interaction et 25 % à la première. Tout comme en forme de U, ce modèle d’attribution favorise la première et la dernière interactions, mais favorise plus fortement la dernière interaction. |
| ![Inverse J](/help/assets/icons/AttributeInverseJ.svg) | En forme de J inversé | Attribue un crédit de 60 % au premier point de contact, de 20 % au dernier point de contact et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la première interaction et 25 % à la dernière. Tout comme en forme de J, ce modèle d’attribution favorise la première et la dernière interactions, mais favorise plus fortement la première interaction. |
| ![Décroissance temporelle](/help/assets/icons/AttributeTimeDecay.svg) | Décroissance temporelle | Suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de sept jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2^(-t/halflife)`, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont ensuite normalisés à 100 %. Idéal pour les scénarios où vous souhaitez mesurer l’attribution par rapport à un événement spécifique et significatif. Plus une conversion se produit après cet événement, moins le crédit est attribué. |
| ![Personnalisé](/help/assets/icons/AttributeCustom.svg) | Personnalisé | Permet de spécifier les pondérations à attribuer au premier point de contact, au dernier point de contact et aux points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne totalisent pas 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les premiers et derniers points de contact sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. Ce modèle est idéal pour les analystes qui souhaitent un contrôle total sur leur modèle d’attribution et qui ont des besoins spécifiques que d’autres modèles d’attribution ne remplissent pas. |
| ![Algorithmique](/help/assets/icons/AttributeAlgorithmic.svg) | Algorithmique | Utilise des techniques statistiques pour déterminer de manière dynamique la distribution optimale du crédit pour la mesure sélectionnée. L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.<br>À un haut niveau, l’attribution est calculée en tant que coalition de joueurs auxquels un excédent doit être réparti équitablement. La répartition de l&#39;excédent de chaque coalition est déterminée en fonction de l&#39;excédent précédemment créé par chaque sous-coalition (ou des éléments de dimension ayant participé précédemment) de manière récurrente. Pour plus de détails, voir les documents originaux de John Harsanyi et de Lloyd Shapley :<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Intervalle de recherche en amont des attributions {#attribution-lookback-window}

Un intervalle de recherche en amont est la durée pendant laquelle une conversion doit faire une recherche en amont pour inclure des points de contact. Si un élément de dimension est défini en dehors de l’intervalle de recherche en amont, la valeur n’est incluse dans aucun calcul d’attribution.

* **14 jours** : recherche jusqu’à 14 jours à partir du moment où la conversion a eu lieu.
* **30 Days** : recherche jusqu’à 30 jours à partir du moment où la conversion a eu lieu.
* **60 Days** : recherche jusqu’à 60 jours à partir du moment où la conversion a eu lieu.
* **90 Days** : recherche jusqu’à 90 jours à partir du moment où la conversion a eu lieu.
* **Session** : recherche en amont jusqu’au début de la session au cours de laquelle une conversion s’est produite. Les intervalles de recherche en amont des sessions respectent le [délai d’expiration de session](/help/data-views/create-dataview.md#session-settings) modifié dans une vue de données.
* **Personne (Intervalle de création de rapports)** : recherche toutes les visites en amont jusqu’au premier du mois de la période en cours. Par exemple, si la période du rapport est du 15 au 30 septembre, la période de recherche en amont des personnes est du 1er au 30 septembre. Si vous utilisez cet intervalle de recherche en amont, vous pouvez parfois constater que les éléments de dimension sont attribués aux dates en dehors de votre créneau de rapport.
* **Durée personnalisée :** Permet de définir une période de recherche arrière personnalisée à partir de laquelle une conversion s’est produite. Vous pouvez spécifier le nombre de minutes, heures, jours, semaines, mois ou trimestres. Par exemple, si une conversion a eu lieu le 20 février, un intervalle de recherche en amont de cinq jours évalue tous les points de contact de dimension du 15 au 20 février dans le modèle d’attribution.

## Exemple d’attribution {#attribution-example}

Examinez l’exemple suivant :

1. Le 15 septembre, une personne arrive sur votre site par le biais d’une annonce de référencement payant, puis la quitte.
1. Le 18 septembre, la personne arrive de nouveau sur votre site par le biais d&#39;un lien sur les médias sociaux qu&#39;elle a reçu d&#39;un ami. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
1. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre intervalle de recherche en amont et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples :

* En utilisant **Première touche** et un **intervalle de recherche en amont des sessions**, l’attribution ne prend en compte que la troisième visite. Entre le courrier électronique et l’affichage, le courrier électronique était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $.

* À l’aide de **Première touche** et d’un **intervalle de recherche en amont des personnes**, l’attribution examine les trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $.

* En utilisant **linear** et un **intervalle de recherche en amont de session**, le crédit est divisé entre le courrier électronique et l’affichage. Ces deux canaux reçoivent chacun un crédit de 25 $.
En utilisant **linear** et un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat.

* En utilisant **En forme de J** et un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage.

   * Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.
   * Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.

* À l’aide de **Décroissance temporelle** et d’un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, le courrier électronique et l’affichage. Utilisation de la demi-vie de sept jours par défaut :

   * Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`
   * Intervalle de zéro jour entre le point de contact du courrier électronique et la conversion. `2^(-0/7) = 1`
   * Intervalle de six jours entre le point de contact social et la conversion. `2^(-6/7) = 0.552`
   * Intervalle de neuf jours entre le point de contact du référencement payant et la conversion. `2^(-9/7) = 0.41`
   * La normalisation de ces valeurs entraîne les résultats suivants :

      * Affichage : 33,8 %, gain de 16,88 $
      * Courrier électronique : 33,8 %, gain de 16,88 $
      * Réseaux sociaux : 18,6 %, gain de 9,32 $
      * Référencement payant : 13,8 %, gain de 6,92 $

Les événements de conversion qui comportent généralement des nombres entiers sont divisés si le crédit appartient à plusieurs canaux. Par exemple, si deux canaux contribuent à une commande à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de cet ordre. Ces mesures partielles sont additionnées pour toutes les personnes, puis arrondies à l’entier le plus proche pour la création de rapports.

