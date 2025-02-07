---
description: Découvrez comment analyser les résultats des tests A/B dans le panneau Expérimentation du Customer Journey Analytics.
title: Panneau Expérimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: dbf0ef92069778f6c805fa4315864b2c2c4a6622
workflow-type: tm+mt
source-wordcount: '2183'
ht-degree: 20%

---

# Panneau Expérimentation {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="Expérimentation"
>abstract="Créez un panneau pour comparer des variantes d’expérience utilisateur, de marketing ou de messages. Et de déterminer quelle variante est la meilleure pour obtenir un résultat spécifique."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="Expérimentation"
>abstract="Comparez différentes expériences utilisateur, variantes de marketing ou de messagerie pour déterminer le meilleur moyen d’obtenir un résultat spécifique.<br/><br/>**Paramètres **<br/>**Expérience** : expérience analysée.<br>**Variante de contrôle** : variante de contrôle pour l’expérience sélectionnée.<br/>**Mesure de succès** : jusqu’à 5 mesures de succès standard (non calculées) pour analyser l’expérience.<br/>**Mesure de normalisation** : personnes, sessions ou événements. Cette mesure (également appelée méthodologie de comptage) devient le dénominateur du calcul de l’effet élévateur. Elle affecte également la manière dont les données sont agrégées avant l’application du calcul du degré de confiance."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Cet article présente le panneau Expérimentation dans_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Voir [Panneau Analytics for Target](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) pour plus d’informations sur l’analyse des activités et des expériences Adobe Target dans_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._

>[!ENDSHADEBOX]


Le panneau **[!UICONTROL Expérimentation]** permet aux analystes de comparer différentes expériences utilisateur, variantes de marketing ou de messagerie afin de déterminer la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation : en ligne, hors ligne, à partir de solutions d’Adobe telles que Target ou Journey Optimizer, et même de données BYO (apportez vos propres données).

En savoir plus sur l’[intégration entre Adobe Customer Journey Analytics et Adobe Target](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja).

## Contrôle d’accès {#access}

Le panneau Expérimentation est disponible pour tous les utilisateurs du Customer Journey Analytics. Aucun droit d’administrateur ou autre autorisation n’est requis. Toutefois, les conditions préalables exigent des actions que seuls les administrateurs peuvent effectuer.

## Fonctions dans les mesures calculées

Deux fonctions avancées sont disponibles : Effet élévateur et Degré de confiance. Pour plus d’informations, voir [Référence - fonctions avancées](/help/components/calc-metrics/cm-adv-functions.md).

## Conditions préalables

Pour utiliser le panneau d’expérimentation, veillez à respecter les conditions préalables suivantes :

### Créer une connexion aux jeux de données d’expérience

Le schéma de données recommandé consiste à placer les données de l’expérience dans un tableau [Object](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) qui contient les données d’expérience et de variante dans deux dimensions distinctes. Les deux dimensions doivent se trouver dans un tableau d’objets **unique**. Si vos données d’expérience se trouvent dans une seule dimension (avec des données d’expérience et de variante dans une chaîne délimitée), le paramètre [sous-chaîne](/help/data-views/component-settings/substring.md) dans les vues de données vous permet de diviser la dimension en deux pour l’utiliser dans le panneau.


Une fois les données d’expérience [ingérées](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) dans Adobe Experience Platform, [créez une connexion en Customer Journey Analytics ](/help/connections/create-connection.md) à un ou plusieurs jeux de données d’expérience.

### Ajouter des libellés de contexte dans les vues de données

Dans les paramètres des vues de données du Customer Journey Analytics, les administrateurs peuvent ajouter des [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure et les services du Customer Journey Analytics tels que le panneau [!UICONTROL Expérimentation] peuvent utiliser ces libellés à leurs fins. Deux libellés prédéfinis sont utilisés pour le panneau Expérimentation :

* [!UICONTROL Expérience d’expérimentation]
* [!UICONTROL Variante d’expérimentation]

Dans votre vue de données contenant des données d’expérimentation, sélectionnez deux dimensions, l’une avec les données d’expérimentation et l’autre avec les données de variante. Puis étiquetez ces dimensions avec les libellés **[!UICONTROL Expérience d’expérimentation]** et **[!UICONTROL Variante d’expérimentation]**.

![Options de libellé de contexte pour l’expérimentation et la variante d’expérimentation.](assets/context-label.png)

Sans ces libellés, le panneau Expérience ne fonctionnera pas, puisqu’il n’y aura aucune expérience à utiliser.

## Utilisation

Pour utiliser un panneau **[!UICONTROL Expérimentation]**, procédez comme suit :

1. Créez un panneau **[!UICONTROL Expérimentation]**. Pour plus d’informations sur la création d’un panneau, consultez [Créer un panneau](panels.md#create-a-panel).


1. Spécifiez l’[entrée](#panel-input) du panneau.

1. Observez la [sortie](#panel-output) du panneau.

   >[!IMPORTANT]
   >
   >Si la configuration nécessaire dans les vues de données du Customer Journey Analytics n’a pas été effectuée, vous recevez le message suivant avant de pouvoir continuer : [!UICONTROL Veuillez configurer les dimensions de l’expérience et des variantes dans les vues de données].
   >

### Entrée du panneau

Pour utiliser le panneau Expérimentation :

1. Configurez les paramètres d’entrée du panneau :

   ![Panneau Expérimentation déplacé dans un projet.](assets/experiment-input.png)

   | Paramètre | Définition |
   | --- | --- |
   | **[!UICONTROL Période]** | La période du panneau Expérimentation est automatiquement définie, en fonction du premier événement reçu en Customer Journey Analytics pour l’expérience sélectionnée. Si nécessaire, vous pouvez limiter ou étendre la période à des délais plus spécifiques. |
   | **[!UICONTROL Expérience]** | Ensemble de variations d’une expérience qui ont été présentées aux utilisateurs finaux afin de déterminer laquelle il est préférable de conserver à perpétuité. Une expérience est composée de deux variantes ou plus, dont l’une est considérée comme la variante de contrôle. Ce paramètre est prérempli avec les dimensions qui ont été étiquetées avec le libellé **[!UICONTROL Expérience]** dans les vues de données et l’équivalent de 3 mois de données d’expérimentation. |
   | **[!UICONTROL Variante de contrôle]** | Une, deux ou plusieurs modifications de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. Une variante doit être sélectionnée comme contrôle, et une seule variante peut être considérée comme la variante de contrôle. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec le libellé **[!UICONTROL Variante]** dans les vues de données. Ce paramètre récupère les données de variante associées à cette expérience. |
   | **[!UICONTROL Mesures de succès]** ➊ | Mesure ou mesures avec lesquelles un utilisateur compare des variantes. La variante ayant le résultat le plus souhaitable pour la mesure de conversion (la plus élevée ou la plus faible) est déclarée *variante la plus performante* d’une expérience. Vous pouvez ajouter jusqu’à 5 mesures. |
   | **[!UICONTROL Mesure de normalisation]** ➋ | La base ([!UICONTROL Personnes], [!UICONTROL Sessions] ou [!UICONTROL Événements]) sur laquelle un test s’exécute. Par exemple, un test peut comparer les taux de conversion de plusieurs variantes où le **[!UICONTROL Taux de conversion]** est calculé comme Page vue |
   | **[!UICONTROL Inclure les limites supérieure/inférieure de confiance]** | Activez cette option pour afficher les limites supérieure et inférieure des niveaux de confiance. |


1. Sélectionnez la **[!UICONTROL Version]**.

### Sortie du panneau

Le panneau Expérimentation renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de vos expériences. En haut du panneau, des visualisations [résumé des changements](../visualizations/summary-number-change.md) sont fournies pour vous rappeler les paramètres du panneau que vous avez sélectionnés. À tout moment, vous pouvez modifier le panneau en sélectionnant l’option Modifier le crayon en haut à droite.

Vous obtenez également un résumé textuel qui indique si l’expérience est concluante ou non et résume le résultat. La conclusion est basée sur la signification statistique (voir [Méthodologie statistique](#adobes-statistical-methodology).) Vous pouvez afficher des nombres de synthèse pour la variante la plus performante avec l’effet élévateur et le degré de confiance les plus élevés.

Pour chaque mesure de succès sélectionnée, une visualisation [tableau à structure libre](../visualizations/freeform-table/freeform-table.md) et un taux de conversion [ligne](../visualizations/line.md) s’affichent.

![Sortie de l’expérience affichant un tableau à structure libre et une tendance de taux de conversion.](assets/experiment-output.png)


>[!NOTE]
>
>Ce panneau ne prend actuellement pas en charge l’analyse des tests A/A.

#### Interprétation des résultats

1. **L’expérience est concluante** : chaque fois que vous consultez le rapport d’expérience, les données accumulées jusqu’à présent dans l’expérience sont analysées. L’analyse déclare une expérience concluante lorsque le degré de confiance valide *à tout moment* dépasse un seuil de 95 % pour *au moins l’une* des variantes. Avec plus de deux bras, une correction de Benjamini-Hochberg est appliquée pour corriger plusieurs tests d’hypothèse.

2. **Variante la plus performante** : lorsqu’une expérience est déclarée concluante, la variante ayant le taux de conversion le plus élevé est étiquetée comme variante la plus performante. Notez que cette variante doit être la variante de référence ou de contrôle, ou l’une des variantes qui dépasse le seuil de confiance valide de 95 % *à tout moment* (avec des corrections de Benjamini-Hochberg appliquées).

3. **Taux de conversion** : le taux de conversion qui s’affiche est un ratio de la valeur de la mesure de succès ➊ à la valeur de la mesure de normalisation ➋. Notez que cette valeur peut être supérieure à 1, si la mesure n’est pas binaire (1 ou 0 pour chaque unité de l’expérience)

4. **Effet élévateur** : la synthèse du rapport d’expérience affiche l’effet élévateur sur la ligne de base, qui est une mesure de l’amélioration en pourcentage du taux de conversion d’une variante donnée par rapport à la ligne de base. Défini précisément, il s’agit de la différence de performance entre une variante donnée et la ligne de base, divisée par les performances de la ligne de base, exprimée en pourcentage.

5. **Confiance** : le degré de confiance valide à tout moment qui s’affiche est une mesure probabiliste de l’ampleur des preuves qu’une variante donnée est identique à la variante de contrôle. Un degré de confiance plus élevé indique moins de preuves relatives à l’hypothèse que la variante de contrôle et la variante de non-contrôle ont des performances similaires. Le degré de confiance est une probabilité (exprimée en pourcentage) que vous auriez observé une différence plus faible dans les taux de conversion entre une variante donnée et le contrôle. Alors qu’en réalité, il n’y a aucune différence dans les taux de conversion réels sous-jacents. En termes de *p*-valeurs, la confiance affichée est 1 - *p*-valeur.

>[!NOTE]
>
>Une description complète des résultats doit tenir compte de toutes les preuves disponibles (par exemple, la conception de l’expérience, la taille des échantillons, les taux de conversion, le degré de confiance, etc.), et pas seulement de la déclaration de résultat concluant ou non concluant. Même lorsqu’un résultat n’est pas encore concluant, il peut encore y avoir des preuves convaincantes indiquant qu’une variante est différente d’une autre (par exemple, les intervalles de confiance sont presque sans chevauchement). Idéalement, toutes les preuves statistiques, interprétées sur un spectre continu, doivent éclairer la prise de décision.

## Méthodologie statistique d’Adobe {#statistics}

Afin de fournir une inférence statistique facile à interpréter et sûre, Adobe a adopté une méthodologie statistique fondée sur des [Séquences de confiance valides à tout moment](https://arxiv.org/abs/2103.06476).

Une séquence de confiance est une analogie *séquentielle* d’un intervalle de confiance. Pour comprendre ce qu’est une séquence de confiance, imaginez que vous répétiez vos expériences cent fois. Et calculez une estimation de la mesure commerciale moyenne (par exemple le taux d’ouverture d’un e-mail) et de la séquence de confiance à 95 % qui lui est associée pour *chaque nouvel utilisateur* qui entre dans l’expérience.

Une séquence de confiance à 95 % inclut la valeur « true » de la mesure commerciale dans 95 des 100 expériences que vous avez exécutées. (Un intervalle de confiance à 95 % ne pouvait être calculé qu’une seule fois par expérience pour offrir la même garantie de couverture de 95 % ; pas avec chaque nouvel utilisateur). Les séquences de confiance vous permettent donc de surveiller les expériences en continu, sans augmenter les taux d’erreurs faux positifs, c’est-à-dire qu’elles permettent de « Jeter un coup d’œil » sur les résultats.

## Interpréter les dimensions non randomisées {#non-randomized}

Customer Journey Analytics permet aux analystes de sélectionner n’importe quelle dimension comme expérience. Mais comment interpréter une analyse où la dimension choisie comme expérience n&#39;est pas une dimension pour laquelle les personnes sont randomisées ?

Prenons l’exemple d’une publicité qu’une personne voit. Il se peut que vous souhaitiez mesurer le changement dans certaines mesures (par exemple, le revenu moyen) si vous décidez d’afficher les personnes *ad B* au lieu de *ad A*. L’effet causal de l’affichage de la publicité B, au lieu de la publicité A, est d’une importance capitale pour la décision de commercialisation. Cet effet causal peut être mesuré comme le revenu moyen sur l&#39;ensemble de la population, si vous remplacez le statu quo de l&#39;affichage de l&#39;annonce A par la stratégie alternative d&#39;affichage de l&#39;annonce B.

Les tests A/B sont la référence dans l&#39;industrie pour mesurer objectivement les effets de telles interventions. La principale raison pour laquelle un test A/B donne lieu à une estimation causale est due à la randomisation des personnes pour recevoir l’un des variants possibles.

Maintenant, considérez une dimension qui n’est pas atteinte par la randomisation, par exemple, l’état américain de la personne. Les personnes viennent principalement de deux États, New York et la Californie. Le chiffre d&#39;affaires moyen des ventes d&#39;une marque de vêtements d&#39;hiver peut être différent dans les deux États en raison des différences dans la météo régionale. Dans une telle situation, la météo peut être le véritable facteur causal derrière les ventes de vêtements d&#39;hiver, et non le fait que les états géographiques des personnes sont différents.

Le panneau d’expérimentation dans Customer Journey Analytics vous permet d’analyser les données sous la forme d’une différence de chiffre d’affaires moyen par état des personnes. Dans un tel cas, la sortie n’a pas d’interprétation causale. Toutefois, une telle analyse peut encore présenter un intérêt. Il fournit une estimation (ainsi que des mesures d&#39;incertitude) de la différence entre les revenus moyens des personnes par les États.  Cette valeur est également appelée *Test statistique d’hypothèse*. Le résultat de cette analyse peut être intéressant, mais pas nécessairement exploitable. Tout simplement parce que vous n’avez pas randomisé et que vous ne pouvez parfois pas randomiser les personnes sur l’une des valeurs possibles de la dimension.

L’illustration suivante met en contraste ces situations :

![Diagramme présentant les données d’observation et l’expérience randomisée.](assets/randomize.png)

Lorsque vous voulez mesurer l&#39;impact de l&#39;intervention X sur le résultat Y, il est possible que la véritable cause des deux soit le facteur de confusion C. Si les données ne sont pas obtenues en randomisant les personnes sur X, l&#39;impact est plus difficile à mesurer, et l&#39;analyse rend compte explicitement de C. La randomisation rompt la dépendance de X sur C, ce qui nous permet de mesurer l&#39;effet de X sur Y sans avoir à nous soucier d&#39;autres variables.

## Utiliser les mesures calculées dans l’expérimentation {#use-in-experimentation}

>[!NOTE]
>
>Pour les organisations qui utilisent à la fois Customer Journey Analytics et Adobe Journey Optimizer, les informations de cette section s’appliquent également aux fonctionnalités d’expérimentation de Journey Optimizer.

Toutes les mesures calculées ne sont pas compatibles avec le panneau Expérimentation .

Les mesures calculées qui incluent l’une des mesures ou constantes suivantes ne sont pas compatibles avec le panneau Expérimentation :

* Mesures de base d’un [jeu de données de résumé](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/summary-data)
* Mesures de base divisées entre elles ou multipliées ensemble (par exemple, `Revenue`/`Orders`)
* Constantes ajoutées ou soustraites à une mesure de base (par exemple, `Revenue+50`)
* L’une des mesures de base suivantes :
   * Personnes

Les mesures calculées qui ne sont pas compatibles avec le panneau Expérimentation ont la valeur [!UICONTROL **Partout en Customer Journey Analytics (à l’exception de l’expérimentation)**] dans le champ [!UICONTROL **Compatibilité des produits**] lors de la création de la mesure calculée. Pour plus d’informations sur la création d’une mesure calculée, voir [Création de mesures](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Utilisation de mesures calculées dans le panneau Expérimentation

Consultez cet article de blog pour plus d’informations sur [l’utilisation de mesures calculées dans le panneau Expérimentation](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).

>[!MORELIKETHIS]
>[Maîtriser l’expérimentation Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
