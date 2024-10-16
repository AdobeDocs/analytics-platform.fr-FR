---
description: Découvrez comment analyser les résultats des tests A/B dans le panneau Expérience du Customer Journey Analytics .
title: Panneau Expérimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 3e2d92003f8b89a20edfcfb8358854c7fbd15577
workflow-type: tm+mt
source-wordcount: '2144'
ht-degree: 16%

---

# Panneau Expérimentation {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_experimentation_button"
>title="Expérimentation"
>abstract="Créez un panneau pour comparer différentes expériences utilisateur, variations de marketing ou de messagerie. Et de déterminer quelle variation est la meilleure pour déterminer un résultat spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_experimentation_panel"
>title="Expérimentation"
>abstract="Comparez différentes expériences utilisateur, variantes de marketing ou de messagerie pour déterminer le meilleur moyen d’obtenir un résultat spécifique. <br/><br/>**Parameters **<br/>**Experiment** : expérience analysée.<br>**Variante de contrôle** : variante de contrôle pour l’expérience sélectionnée.<br/>**Mesure de succès** : jusqu’à 5 mesures de succès standard (non calculées) pour analyser l’expérience.<br/>**Mesure de normalisation** : personnes, sessions ou événements. Cette mesure (également appelée méthodologie de comptage) devient le dénominateur du calcul de l’effet élévateur. Cette mesure affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance."

<!-- markdownlint-enable MD034 -->



Le panneau **[!UICONTROL Expérience]** permet aux analystes de comparer différentes expériences utilisateur, variations de marketing ou de messagerie afin de déterminer quelle est la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation : en ligne, hors ligne, à partir de solutions d’Adobe telles que Target ou Journey Optimizer, et même de données BYO (apportez-vous).

En savoir plus sur l’ [intégration entre Adobe Customer Journey Analytics et Adobe Target](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja).

## Contrôle d’accès {#access}

Le panneau Expérience est disponible pour tous les utilisateurs de Customer Journey Analytics. Aucun droit d’administrateur ou autre autorisation n’est requis. Toutefois, les conditions préalables nécessitent des actions que seuls les administrateurs peuvent effectuer.

## Fonctions dans les mesures calculées

Deux fonctions avancées sont disponibles : effet élévateur et degré de confiance. Pour plus d’informations, voir [Référence - fonctions avancées](/help/components/calc-metrics/cm-adv-functions.md).

## Conditions préalables

Pour utiliser le panneau d’expérimentation, assurez-vous de respecter les conditions préalables suivantes :

### Création d’une connexion à des jeux de données d’expérience

Le schéma de données recommandé est que les données d’expérimentation se trouvent dans un [tableau d’objets](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) qui contient les données d’expérience et de variante dans deux dimensions distinctes. Les deux dimensions doivent se trouver dans un tableau d’objets **single**. Si vos données d’expérimentation se trouvent dans une seule dimension (avec les données d’expérience et de variante dans une chaîne délimitée), vous pouvez utiliser le paramètre [substring](/help/data-views/component-settings/substring.md) dans les vues de données pour diviser la dimension en deux à utiliser dans le panneau.


Une fois vos données d’expérimentation [ ingérées ](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) dans Adobe Experience Platform, [ créez une connexion en Customer Journey Analytics](/help/connections/create-connection.md) à un ou plusieurs jeux de données d’expérience.

### Ajout d’étiquettes contextuelles dans les vues de données

Dans les paramètres des vues de données du Customer Journey Analytics, les administrateurs peuvent ajouter des [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure et les services de Customer Journey Analytics tels que le panneau [!UICONTROL Expérimentation] peuvent utiliser ces libellés à leurs fins. Deux libellés prédéfinis sont utilisés pour le panneau Expérimentation :

* [!UICONTROL Expérience d’expérimentation]
* [!UICONTROL Variante d’expérimentation]

Dans votre vue de données contenant des données d’expérimentation, sélectionnez deux dimensions, l’une avec les données d’expérimentation et l’autre avec les données de variante. Étiquetez ensuite ces dimensions avec les étiquettes **[!UICONTROL Expérience d’expérience]** et **[!UICONTROL Variante d’expérience]** .

![ Options d’étiquette contextuelle pour la variation de l’expérience et de l’expérience.](assets/context-label.png)

Sans ces libellés, le panneau Expérience ne fonctionnera pas, puisqu’il n’y aura aucune expérience à utiliser.

## Sélectionnez l’option  

Pour utiliser un panneau **[!UICONTROL Expérimentation]** :

1. Créez un panneau **[!UICONTROL Expérimentation]**. Pour plus d’informations sur la création d’un panneau, voir [Création d’un panneau](panels.md#create-a-panel).


1. Spécifiez la [entrée](#panel-input) pour le panneau.

1. Observez la [sortie](#panel-output) pour le panneau.

   >[!IMPORTANT]
   >
   >Si la configuration nécessaire dans les vues de données du Customer Journey Analytics n&#39;a pas été effectuée, vous recevez ce message avant de pouvoir continuer : [!UICONTROL Configurez les dimensions de l&#39;expérience et des variantes dans les vues de données].
   >

### Entrée de panneau

Pour utiliser le panneau d’expérience :

1. Configurez les paramètres d’entrée du panneau :

   ![ Le panneau d’expérimentation glissé dans un projet.](assets/experiment-input.png)

   | Paramètre | Définition |
   | --- | --- |
   | **[!UICONTROL Période]** | La période du panneau Expérimentation est automatiquement définie, en fonction du premier événement reçu en Customer Journey Analytics pour l’expérience sélectionnée. Si nécessaire, vous pouvez limiter ou étendre la période à des délais plus spécifiques. |
   | **[!UICONTROL Expérience]** | Ensemble de variations d’une expérience qui ont été exposées aux utilisateurs finaux afin de déterminer la meilleure expérience à conserver perpétuellement. Une expérience est composée de deux variantes ou plus, dont l’une est considérée comme la variante de contrôle. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec l’étiquette **[!UICONTROL Experience]** dans les vues de données et l’équivalent de 3 mois de données d’expérimentation. |
   | **[!UICONTROL Variante de contrôle]** | Une, deux ou plusieurs modifications de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. Une variante doit être sélectionnée comme contrôle, et une seule variante peut être considérée comme la variante de contrôle. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec le libellé **[!UICONTROL Variant]** dans les vues de données. Ce paramètre récupère les données de variante associées à cette expérience. |
   | **[!UICONTROL Mesures de succès]** | Mesure ou mesures avec lesquelles un utilisateur compare des variantes. La variante ayant le résultat le plus souhaitable pour la mesure de conversion (la plus élevée ou la plus faible) est déclarée la *variante la plus performante* d’une expérience. Vous pouvez ajouter jusqu’à 5 mesures. |
   | **[!UICONTROL Mesure de normalisation]** | Base ([!UICONTROL People], [!UICONTROL Sessions] ou [!UICONTROL Events]) sur laquelle s’exécute un test. Par exemple, un test peut comparer les taux de conversion de plusieurs variations où le **[!UICONTROL taux de conversion]** est calculé comme page vue. |
   | **[!UICONTROL Inclure les limites supérieures/inférieures de la confiance]** | Activez cette option pour afficher les limites supérieure et inférieure des niveaux de confiance. |


1. Sélectionnez la **[!UICONTROL Version]**.

### Sortie de panneau

Le panneau Expérimentation renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de vos expériences. Dans la partie supérieure du panneau, des visualisations [synthèse des changements](../visualizations/summary-number-change.md) sont fournies pour vous rappeler les paramètres du panneau que vous avez sélectionnés. Vous pouvez à tout moment modifier le panneau en sélectionnant le crayon de modification en haut à droite.

Vous obtenez également un résumé textuel qui indique si l’expérience est concluante ou non et résume le résultat. La conclusion repose sur la signification statistique (voir la [méthodologie statistique](#adobes-statistical-methodology)). Vous pouvez afficher des nombres de synthèse pour la variante la plus performante avec l’effet élévateur et le degré de confiance les plus élevés.

Pour chaque mesure de succès que vous avez sélectionnée, une visualisation [tableau à structure libre](../visualizations/freeform-table/freeform-table.md) et une visualisation de taux de conversion [ligne](../visualizations/line.md) s’affichent.

![ La sortie de l’expérience présentant un tableau à structure libre et une tendance de taux de conversion.](assets/experiment-output.png)


>[!NOTE]
>
>Ce panneau ne prend actuellement pas en charge l’analyse des tests A/A.

#### Interprétation des résultats

1. **L’expérience est concluante** : chaque fois que vous affichez le rapport d’expérimentation, les données accumulées dans l’expérience jusqu’à présent sont analysées. L’analyse déclare qu’une expérience est concluante lorsque le degré de confiance valide *à tout moment* dépasse un seuil de 95 % pour *au moins un* des variantes. Avec plus de deux bras, une correction Benjamini-Hochberg est appliquée pour corriger les tests d&#39;hypothèse multiples.

2. **Variante la plus performante** : lorsqu’une expérience est déclarée concluante, la variante ayant le taux de conversion le plus élevé est étiquetée comme variante la plus performante. Notez que cette variante doit être la variante de référence ou de contrôle, ou l’une des variantes qui dépasse le seuil de confiance valide de 95 % *à tout moment* (avec des corrections Benjamini-Hochberg appliquées).

3. **Taux de conversion** : le taux de conversion qui s’affiche est un ratio de la valeur de la mesure de succès la valeur de la mesure de normalisation de la valeur de la mesure de. Notez que cette valeur peut être supérieure à 1, si la mesure n’est pas binaire (1 ou 0 pour chaque unité de l’expérience).

4. **Effet élévateur** : le résumé du rapport d’expérience affiche l’effet élévateur sur la ligne de base, qui est une mesure de l’amélioration en pourcentage du taux de conversion d’une variante donnée par rapport à la ligne de base. Défini précisément, il s’agit de la différence de performance entre une variante donnée et la ligne de base, divisée par les performances de la ligne de base, exprimée en pourcentage.

5. **Degré de confiance** : la confiance valide affichée à tout moment est une mesure probabiliste de la quantité de preuves qu’une variante donnée est identique à la variante de contrôle. Un degré de confiance plus élevé indique moins de preuves relatives à l’hypothèse que la variante de contrôle et la variante de non-contrôle ont des performances similaires. Le degré de confiance est une probabilité (exprimée en pourcentage) que vous auriez observé une différence plus faible des taux de conversion entre une variante donnée et le contrôle. Bien qu’en réalité, il n’y ait aucune différence entre les taux de conversion sous-jacents réels. En termes de *p*-valeurs, la confiance affichée est 1 - *p*-valeur.

>[!NOTE]
>
>Une description complète des résultats doit tenir compte de toutes les preuves disponibles (par exemple, la conception de l’expérience, la taille des échantillons, les taux de conversion, le degré de confiance, etc.), et pas seulement de la déclaration concluante ou non. Même lorsqu’un résultat n’est pas encore concluant, il peut encore y avoir des preuves convaincantes pour qu’une variante soit différente d’une autre (par exemple, les intervalles de confiance sont presque sans chevauchement). Idéalement, toutes les données statistiques, interprétées sur un spectre continu, devraient éclairer la prise de décision.

## Méthodologie statistique d’Adobe {#statistics}

Afin de fournir une inférence statistique facile à interpréter et sûre, Adobe a adopté une méthodologie statistique fondée sur des [Séquences de confiance valides à tout moment](https://arxiv.org/abs/2103.06476).

Une séquence de confiance est un *séquentiel* analogique d’un intervalle de confiance. Pour comprendre ce qu&#39;est une séquence de confiance, imaginez que vous répétez vos expériences cent fois. Et calculez une estimation de la mesure commerciale moyenne (par exemple, le taux d’ouverture d’un email) et de sa séquence de confiance de 95 % associée pour *chaque nouvel utilisateur* qui entre dans l’expérience.

Une séquence de confiance de 95 % inclut la valeur &quot;true&quot; de la mesure d’entreprise dans 95 des 100 expériences que vous avez exécutées. (Un intervalle de confiance de 95 % ne pouvait être calculé qu’une seule fois par expérience pour offrir la même garantie de couverture de 95 % ; pas pour chaque nouvel utilisateur). Les séquences de confiance vous permettent donc de surveiller les expériences en continu, sans augmenter les taux d’erreur de faux positifs, c’est-à-dire qu’elles permettent de &quot;regarder&quot; les résultats.

## Interprétation des dimensions non randomisées {#non-randomized}

Customer Journey Analytics permet aux analystes de sélectionner n’importe quelle dimension comme expérience. Mais comment interpréter une analyse où la dimension choisie comme expérience n&#39;est pas pour laquelle des personnes sont aléatoires ?

Prenons l’exemple d’une publicité qu’une personne voit. Il peut être intéressant de mesurer la modification de certaines mesures (par exemple, les recettes moyennes) si vous décidez d’afficher les personnes *ad B* au lieu de *ad A*. L’effet causal de l’affichage de la publicité B, au lieu de la publicité A, est d’une importance centrale pour arriver à la décision marketing. Cet effet de cause à effet peut être mesuré comme le revenu moyen sur l’ensemble de la population, si vous avez remplacé le statu quo de l’affichage et A par la stratégie alternative d’affichage de la publicité B.

Les tests A/B sont l&#39;étalon-or de l&#39;industrie pour mesurer objectivement les effets de telles interventions. La raison essentielle pour laquelle un test A/B donne lieu à une estimation du lien de cause à effet est la randomisation des personnes qui reçoivent l’une des variantes possibles.

Maintenant, considérez une dimension qui n&#39;est pas atteinte par l&#39;organisation aléatoire, par exemple, l&#39;état américain de la personne. Les personnes viennent principalement de deux Etats, New York et la Californie. Les recettes moyennes des ventes d&#39;une marque de vêtements d&#39;hiver peuvent être différentes dans les deux états en raison des différences de conditions météorologiques régionales. Dans une telle situation, la météo peut être le véritable facteur de la vente des vêtements d&#39;hiver, et non le fait que les états géographiques des personnes sont différents.

Le panneau d’expérimentation du Customer Journey Analytics vous permet d’analyser les données sous la forme d’une différence de revenus moyenne par état de la personne. Dans une telle situation, la production n&#39;a pas d&#39;interprétation causale. Cependant, une telle analyse peut encore être intéressante. Il donne une estimation (ainsi que des mesures d’incertitude) de la différence de revenus moyens par les Etats de la personne.  Cette valeur est également appelée *Tests d’hypothèse statistiques*. Le résultat de cette analyse peut être intéressant, mais pas nécessairement exploitable. Tout simplement parce que vous n’avez pas effectué d’organisation aléatoire et que vous ne pouvez parfois pas randomiser les personnes selon l’une des valeurs possibles de la dimension.

L’illustration suivante présente un contraste entre ces situations :

![Diagramme présentant les données d’observation et l’expérience aléatoire.](assets/randomize.png)

Lorsque vous voulez mesurer l&#39;impact de l&#39;intervention X sur le résultat Y, il est possible que la cause réelle des deux soit le facteur de confusion C. Si les données ne sont pas obtenues en randomisant les personnes sur X, l&#39;impact est plus difficile à mesurer, et l&#39;analyse tient explicitement compte de C. La randomisation rompt la dépendance de X sur C, ce qui nous permet de mesurer l&#39;effet de X sur Y sans avoir à nous soucier d&#39;autres variables.

## Utiliser les mesures calculées dans l’expérimentation {#use-in-experimentation}

>[!NOTE]
>
>Pour les organisations qui utilisent Customer Journey Analytics et Adobe Journey Optimizer, les informations de cette section s’appliquent également aux fonctionnalités d’expérimentation de Journey Optimizer.

Toutes les mesures calculées ne sont pas compatibles avec le panneau Expérience .

Les mesures calculées qui incluent l’une des mesures ou constantes suivantes ne sont pas compatibles avec le panneau d’expérimentation :

* Mesures de base d’un [jeu de données récapitulatif](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/summary-data)
* Mesures de base divisées entre elles ou multipliées ensemble (par exemple, `Revenue`/`Orders`)
* Constantes ajoutées ou soustraites à une mesure de base (par exemple, `Revenue+50`)
* L’une des mesures de base suivantes :
   * Personnes

Les mesures calculées qui ne sont pas compatibles avec le panneau d’expérimentation ont la valeur [!UICONTROL **Partout en Customer Journey Analytics (hors expérimentation)**] dans le champ [!UICONTROL **Compatibilité des produits**] lors de la création de la mesure calculée. Pour plus d’informations sur la création d’une mesure calculée, voir [Création de mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Utilisation des mesures calculées dans le panneau Expérience

Reportez-vous à cet article de blog pour plus d’informations sur [l’utilisation de mesures calculées dans le panneau d’expérimentation](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
