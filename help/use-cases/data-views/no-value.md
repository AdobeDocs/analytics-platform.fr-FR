---
title: Gestion de l’absence de valeur dans les rapports Customer Journey Analytics
description: Découvrez quand les entrées **[!UICONTROL Aucune valeur]** dans les rapports Customer Journey Analytics sont attendues et quand elles signalent un problème de collecte de données qui nécessite une attention particulière.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: bc1e610ccf13ca831f40b2819a4665fe8ea21b7b
workflow-type: tm+mt
source-wordcount: '1936'
ht-degree: 0%
---

# Comment gérer Aucune valeur

Lorsque vous utilisez Customer Journey Analytics, la rencontre d’entrées **[!UICONTROL Aucune valeur]** dans les rapports et les tableaux de bord soulève des questions importantes sur la qualité des données, les méthodes de collecte et la précision des rapports. Ces instances doivent être surveillées de près, car elles révèlent des lacunes cachées dans la collecte de données. Le défi consiste à distinguer deux scénarios : lorsque les entrées **[!UICONTROL Aucune valeur]** doivent être étudiées par les fournisseurs de sources de données, et lorsque les entrées **[!UICONTROL Aucune valeur]** reflètent le flux naturel de données dans Customer Journey Analytics. Il est essentiel de comprendre cette distinction pour maintenir l’efficacité des opérations d’analyse. Ce guide vous aide à prendre des décisions éclairées sur les aspects **[!UICONTROL Aucune valeur]** dans votre implémentation de Customer Journey Analytics.

## Comprendre l’absence de valeur

**[!UICONTROL Aucune valeur]** s’affiche lorsqu’une dimension ne possède pas de valeur correspondante pour un événement qui contient autrement une mesure. L’affichage de la mention **[!UICONTROL Aucune valeur]** dans un rapport ne pose pas toujours problème. Dans de nombreux cas, il reflète la structure attendue de votre jeu de données.

Les éléments Dimension peuvent être classés dans l’une des trois catégories suivantes :

* **Attendu [!UICONTROL Aucune valeur]** : résultat naturel du déplacement des utilisateurs dans vos données, par exemple des visiteurs qui ne se sont pas encore connectés ou des dimensions qui ne s’appliquent pas à chaque événement
* **Problématique [!UICONTROL Aucune valeur]** : résultat d’un échec de collecte de données ou d’une erreur d’implémentation, où une valeur existe mais est manquante
* **Valeur valide** : la dimension a capturé une valeur avec succès

Le diagramme suivant montre comment Customer Journey Analytics atteint chacune de ces catégories au fur et à mesure que les données passent de votre source à Adobe Experience Platform.

Le diagramme de flux illustre la manière dont les évaluations Customer Journey Analytics se concentrent sur les données entrantes en vérifiant d’abord la présence de valeurs, puis en déterminant si les valeurs manquantes sont attendues ou problématiques. Cette évaluation claire aide les administrateurs et les analystes à distinguer les cas **[!UICONTROL aucune valeur]** nécessitant une enquête à la source de ceux correspondant à des opérations normales.

![Flux de décision affichant les données source passant par Adobe Experience Platform dans Customer Journey Analytics, qui vérifie si une valeur de dimension est présente, puis si une valeur manquante correspond à un scénario attendu, ce qui entraîne une valeur Non naturelle, une valeur Non problématique ou une valeur valide](assets/no-value-flow.svg)

## Lorsqu’aucune valeur n’est attendue

Voici les raisons courantes et attendues pour lesquelles **[!UICONTROL Aucune valeur]** apparaît dans un rapport :

* Une dimension s’applique uniquement à des scénarios spécifiques, tels que la source du trafic ou le type d’appareil
* Aucun identifiant n’a encore été attribué à un nouveau visiteur
* Un visiteur est en état de pré-connexion et n’a pas fourni d’informations d’utilisateur
* Une fonctionnalité ou une interaction de produit ne s’applique pas à un parcours utilisateur particulier
* Un scénario sur plusieurs appareils ne transporte pas de valeurs de dimension sur plusieurs appareils

Dans ces cas, la mention **[!UICONTROL Aucune valeur]** indique où se trouve un utilisateur dans son parcours d’authentification, lors du passage d’un statut non identifié à un statut identifié, comme illustré ci-dessous.

parcours d’authentification de l’utilisateur affichant un utilisateur visitant le site et accédant à un statut de pré-connexion sans informations utilisateur disponibles, puis un événement de connexion qui renseigne les informations de l’utilisateur![&#128279;](assets/no-value-login-flow.svg)


## Lorsque Aucune valeur n’a besoin d’attention

Vérifiez les entrées **[!UICONTROL Aucune valeur]** lorsqu’elles résultent de l’une des opérations suivantes :

**Problèmes d’implémentation au niveau de la source de données :**

* Éléments de données manquants ou valeurs nulles
* Mappage de variables incorrect
* Couche de données mal configurée
* Échec de la collecte de données
* Incohérence entre les données entrantes et le schéma défini

**Problèmes de qualité des données :**

* Code de suivi endommagé
* Collecte de données incomplète
* Échecs d&#39;intégration
* Erreurs introduites lors de la transformation des données
* Perturbations dans le pipeline de données

## Gérer No value dans les paramètres de la vue de données

Les paramètres de vue de données vous permettent de contrôler l’affichage des éléments **[!UICONTROL Aucune valeur]** dans les rapports. Vous pouvez notamment renommer le libellé, afficher ou masquer les éléments par défaut et traiter **[!UICONTROL Aucune valeur]** comme une valeur de chaîne légitime. Pour obtenir la liste complète des paramètres et leur impact sur les distributions en pourcentage, le filtrage et la segmentation[&#128279;](/help/data-views/component-settings/no-value-options.md) consultez la section Paramètres du composant Aucune option de valeur).

Lors de la configuration de ces paramètres, évaluez vos exigences en matière de création de rapports et évaluez l’impact de la présence de **[!UICONTROL Aucune valeur]** sur votre analyse. Tenez compte à la fois des effets immédiats sur la visibilité des données et des impacts à long terme sur l’analyse des tendances et la cohérence des rapports. Des configurations bien choisies améliorent la clarté des données tout en préservant l’accessibilité et l’exploitabilité des informations commerciales, quelle que soit la manière dont les entrées **[!UICONTROL Aucune valeur]** apparaissent dans vos rapports. La configuration idéale équilibre la représentation des données avec les besoins analytiques pratiques, créant ainsi un environnement de création de rapports qui fournit des informations précises et significatives même lorsque **[!UICONTROL aucune valeur]** données n’est présente.

Le tableau suivant résume les différentes configurations disponibles.

<table>
<thead>
<tr>
<th>Catégorie</th>
<th>Paramètre</th>
<th>Ce qu'il fait</th>
<th>Impact</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="2">Afficher les options</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Peut être inclus ou exclu via la sélection de cases à cocher dans le filtre de recherche du tableau à structure libre.</td>
<td rowspan="2">Visibilité</td>
</tr>
<tr>
<td><img src="assets/dont-show-no-value-default.png"/></td>
</tr>
<tr>
<td rowspan="2">Dénomination personnalisée</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Affecte l’affichage des valeurs de dimension de reporting et potentiellement la consolidation des valeurs et l’agrégation des mesures.</td>
<td rowspan="2">Attribution d'un nom</td>
</tr>
<tr>
<td><img src="assets/show-unknown-as-value.png"/></td>
</tr>
<tr>
<td rowspan="3">Options de traitement</td>
<td><img src="assets/treat-no-value-as-value.png"/></td>
<td>S'applique uniquement aux dimensions non numériques.
Affecte à la fois l’attribution et l’option d’inclusion **[!UICONTROL No value]** dans le filtre de recherche de tableau à structure libre.</td>
<td>Gestion des valeurs et visibilité</td>
</tr>
<tr>
<td rowspan="2">Prise en charge des dimensions numériques :<br><img src="assets/dont-show-no-value-default.png"/><br/><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">Peut être inclus ou exclu via la sélection de cases à cocher dans le filtre de recherche du tableau à structure libre</td>
<td rowspan="2">Visibilité</td>
</tr>
<tr>
</tr>
</tbody>
</table>


### Si affiché, appeler « Aucune valeur »

Ce paramètre vous permet de personnaliser l’affichage des lignes **[!UICONTROL Aucune valeur]** dans les rapports. Vous pouvez saisir un nom personnalisé pour l’élément de dimension **[!UICONTROL Aucune valeur]** dans le champ de texte, fournissant ainsi un contexte plus significatif via **[!UICONTROL Si affiché, appelez « Aucune valeur »]**. L’utilisation de termes clairs et conviviaux pour l’entreprise au lieu de `No value` aide votre entreprise à mieux comprendre les valeurs des rapports. Bien que vous ne puissiez pas utiliser **[!UICONTROL Aucune valeur]** directement en tant que chaîne dans les segments, vous pouvez obtenir le même effet à l’aide de l’opérateur **[!UICONTROL n’existe pas]**.

Vous pouvez remplacer `No value` par des termes descriptifs tels que `Pre-login User` pour le statut d’authentification, `No Customer Tier` pour les clients sans niveau ou `No Tracked Marketing Channel` pour les sources marketing non identifiées. Cela crée des rapports plus intuitifs. `Pre-login User` indique clairement où se trouve un client dans son parcours, tandis que `No Customer Tier` fournit un contexte spécifique. N’oubliez pas que la description choisie s’applique à toutes les instances **[!UICONTROL Aucune valeur]** pour cette dimension. Sélectionnez donc des termes qui reflètent précisément tous les scénarios où les valeurs de dimension sont absentes.

### Ne pas afficher No value par défaut

Ce paramètre détermine s’il faut masquer les lignes **[!UICONTROL Aucune valeur]** par défaut dans les rapports. Lorsqu’elles sont activées, ces lignes sont initialement filtrées, mais peuvent toujours être affichées dans un tableau à structure libre si nécessaire en cochant des cases dans le filtre de recherche du tableau à structure libre. Notez que le masquage des lignes **[!UICONTROL Aucune valeur]** affecte la répartition en pourcentage des valeurs restantes, car les pourcentages sont recalculés en fonction des éléments visibles uniquement.

### Afficher No value par défaut

Ce paramètre contrôle si **[!UICONTROL Aucune valeur]** s’affiche par défaut dans les rapports. Lorsqu’elles sont activées, les entrées **[!UICONTROL Aucune valeur]** sont visibles, bien que les utilisateurs puissent les exclure à l’aide de la case à cocher du filtre de recherche du tableau à structure libre. L&#39;inclusion ou l&#39;exclusion de lignes **[!UICONTROL Aucune valeur]** affecte les répartitions en pourcentage, car les pourcentages sont calculés uniquement sur les éléments visibles.

### Traiter No value comme une valeur

Ce paramètre traite **[!UICONTROL Aucune valeur]** comme une valeur de chaîne (à l’exception des dimensions numériques), ce qui vous permet de personnaliser sa représentation en tant que valeur de dimension. Cette personnalisation affecte à la fois l’attribution et l’option **[!UICONTROL N’inclure aucune valeur]** dans le filtre de recherche du tableau à structure libre. Gardez à l’esprit que lorsque vous attribuez une valeur de chaîne personnalisée, toutes les valeurs correspondantes dans votre jeu de données sont consolidées sous la même valeur de chaîne de dimension.

Le paramètre **[!UICONTROL Traiter « Aucune valeur » comme valeur]** a un objectif différent de celui de l’affichage de **[!UICONTROL Aucune valeur]** par défaut. Bien que l’affichage par défaut ne contrôle que la visibilité, le fait de traiter comme une valeur modifie la façon logique dont Customer Journey Analytics gère ces entrées. Voici pourquoi cette distinction est importante :

* Il permet un contrôle plus granulaire du filtrage et de la segmentation, ce qui fait de **[!UICONTROL Aucune valeur]** une valeur de dimension distincte et exploitable.
* Il maintient une attribution et une représentation cohérentes dans l’ensemble de vos analyses en traitant **[!UICONTROL Aucune valeur]** comme une valeur de dimension légitime dans les modèles d’attribution et les visualisations.

Traitez **[!UICONTROL Aucune valeur]** comme une valeur lorsque :

* L’absence de données proprement dites est significative pour votre analyse (comme les états de pré-connexion ou le trafic non attribué).
* Vous devez créer des segments ou des mesures calculées qui ciblent ou excluent spécifiquement ces cas.

En revanche, l’affichage **[!UICONTROL Aucune valeur]** par défaut est plus adapté lorsque vous avez besoin d’une visibilité de base des données manquantes sans la complexité d’une logique et d’une attribution supplémentaires associées au fait de les traiter comme une valeur.

### Pas de prise en charge de valeurs pour les dimensions numériques

Pour les dimensions numériques, plusieurs options de configuration sont disponibles. Dans les paramètres des dimensions de la vue de données , vous pouvez configurer toutes les options **[!UICONTROL Aucune valeur]** à l’exception de **[!UICONTROL Traiter « Aucune valeur » comme valeur]**. Vous pouvez également gérer la sélection de la case à cocher **[!UICONTROL Inclure « Aucune valeur »]** pour les dimensions numériques dans le filtre de recherche du tableau à structure libre. Lors de la création de segments, vous pouvez utiliser les opérateurs **[!UICONTROL existe]** ou **[!UICONTROL n’existe pas]** avec des dimensions numériques.

### Aucune valeur et dimensions au niveau de l’article

Certaines dimensions s’appliquent au niveau de l’élément dans un tableau, plutôt qu’au niveau supérieur d’un événement. Par exemple, `productListItems.SKU` n’a une valeur que lorsqu’un élément de liste de produits existe pour cet événement. Cette différence dans le grain de données modifie le comportement de **[!UICONTROL Aucune valeur]**.

Pour une dimension de niveau supérieur standard, Customer Journey Analytics peut placer une mesure dans un compartiment **[!UICONTROL Aucune valeur]** chaque fois que cette dimension est manquante ou a une valeur nulle sur un événement qui comporte une mesure autrement. Une dimension au niveau de l’élément dépend de l’élément existant en premier lieu. Si un événement contient une mesure mais ne comporte pas d’éléments de liste de produits, Customer Journey Analytics ne dispose pas de ligne pour joindre cette mesure ou marquer les données comme **[!UICONTROL Aucune valeur]**.

Customer Journey Analytics ne crée pas d’espace réservé ni de ligne vide pour les tableaux manquants ou vides. Par conséquent, vous pouvez configurer correctement vos paramètres de vue de données **[!UICONTROL Aucune valeur]** et ne pas voir les entrées **[!UICONTROL Aucune valeur]** dans un rapport au niveau de l’élément, comme une répartition de SKU. Le nombre d’entrées manquant est une différence de granularité des données et non un problème de configuration. **[!UICONTROL Aucune valeur]** les paramètres régissent l’affichage des lignes existantes. Un tableau vide signifie qu’aucune ligne n’existe à ce niveau de granularité des données.

Lorsque les nombres au niveau de l’élément **[!UICONTROL Aucune valeur]** semblent inférieurs aux prévisions, vérifiez si les données manquantes du tableau expliquent l’écart avant de supposer que votre paramètre de vue de données doit être ajusté.

## Bonnes pratiques

Une fois que vous avez identifié des instances problématiques **[!UICONTROL sans valeur]**, vous devez développer et mettre en œuvre une stratégie de résolution. Cette correction peut être effectuée de deux manières :

* Ajuster les paramètres de l’option **[!UICONTROL Aucune valeur]** du composant Vue de données, ou
* Correction de problèmes au niveau de la source de collecte de données.

Choisissez votre approche avec soin, car chaque chemin a des implications différentes pour les correctifs rapides et la qualité des données à long terme. Votre implémentation suit un processus méthodique qui corrige les problèmes actuels tout en empêchant les problèmes futurs. Le succès dépend de la planification, de l&#39;exécution systématique et de la surveillance continue.

Voici les principales considérations stratégiques à prendre en compte dans votre plan de mesures correctives :

### Empêcher les problèmes liés à l’absence de valeur

* Valider les données avant leur traitement
* Définissez les valeurs de dimension par défaut le cas échéant (jamais pour un ID de personne).
* Documentez les scénarios où **[!UICONTROL Aucune valeur]** est attendue.
* Ajouter des contrôles qualité au point de collecte des données
* Surveiller la conformité à votre modèle de données
* Consigner les erreurs pendant la collecte de données
* Ajouter des tests automatisés pour votre implémentation
* Champs de schéma obligatoires où une valeur existe toujours

### Valider Aucune valeur dans vos rapports

* Créer des segments qui isolent les modèles **[!UICONTROL Aucune valeur]**
* Créer un tableau de bord d’assurance qualité qui surveille les tendances **[!UICONTROL aucune valeur]** au fil du temps
* Configurer des alertes qui effectuent le suivi des modifications du volume **[!UICONTROL Aucune valeur]**
* Générer des rapports automatisés qui mettent en évidence les modifications importantes des schémas
* Références croisées **[!UICONTROL Aucune valeur]** motifs sur les dimensions associées
* Effectuer des audits réguliers de la configuration de vos vues de données
* Tenir à jour un journal des modifications de votre stratégie **[!UICONTROL Aucune valeur]**
* Créer des procédures opérationnelles standard et des modèles de documentation pour les parties prenantes

## Conclusion

Toutes les entrées **[!UICONTROL Aucune valeur]** ne signalent pas un problème. L’interprétation correcte de la mention **[!UICONTROL Aucune valeur]** nécessite une compréhension de l’architecture de données de Adobe Experience Platform et Customer Journey Analytics, ainsi que de la manière dont les utilisateurs et utilisatrices se déplacent dans votre produit ou site. Plutôt que de tenter d’éliminer chaque instance de **[!UICONTROL Aucune valeur]**, établissez des règles documentées à l’échelle de l’organisation qui distinguent les attentes **[!UICONTROL Aucune valeur]** des problèmes **[!UICONTROL Aucune valeur]**, en vous appuyant sur vos propres parcours d’utilisation et dossiers commerciaux.

>[!MORELIKETHIS]
>
>[Le playbook complet pour la gestion de **[!UICONTROL Aucune valeur]** dans Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/the-complete-playbook-for-handling-no-value-in-adobe-cja-12769?profile.language=fr)
