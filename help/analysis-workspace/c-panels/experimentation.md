---
description: Découvrez comment analyser les résultats des tests A/B dans le panneau Expérience du Customer Journey Analytics .
title: Panneau Expérimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 68289e274c8ea985b6d07bca228f5e6654e05aa4
workflow-type: tm+mt
source-wordcount: '1889'
ht-degree: 58%

---

# Panneau Expérimentation

Le panneau **[!UICONTROL Expérimentation]** permet aux analystes de comparer des variantes d’expérience utilisateur, de marketing ou de messagerie afin de déterminer la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation, en ligne, hors ligne, à partir de solutions d’Adobe, d’Adobe Journey Optimizer et même de données BYO (apportez vos propres données).

En savoir plus sur les [Intégration entre Adobe Customer Journey Analytics et Adobe Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja4t/cja4t).

## Contrôle d’accès {#access}

Le panneau Expérience est disponible pour tous les utilisateurs de Customer Journey Analytics. Aucun droit d’administrateur ou autre autorisation n’est requis. Toutefois, la configuration (étapes 1 et 2 ci-dessous) nécessite des actions que seuls les administrateurs peuvent effectuer.

## Nouvelles fonctions dans les mesures calculées {#functions}

Deux nouvelles fonctions avancées ont été ajoutées : [!UICONTROL Effet élévateur] et [!UICONTROL Degré de confiance]. Pour plus d’informations, voir [Référence - fonctions avancées](/help/components/calc-metrics/cm-adv-functions.md).

## Étape 1 : Créer une connexion à un ou plusieurs jeux de données d’expérience {#connection}

Le schéma de données recommandé consiste à placer les données de l’expérience dans un [tableau d’objets](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html) qui contient les données d’expérience et de variante dans deux dimensions distinctes. Les deux dimensions doivent se trouver dans une **single** tableau d’objets. Si vos données d’expérience se trouvent dans une seule dimension avec des données d’expérience et de variante dans une chaîne délimitée, le paramètre [Sous-chaîne](/help/data-views/component-settings/substring.md) dans les vues de données vous permet de les diviser en deux pour les utiliser dans le panneau.

Une fois les données de l’expérience envoyées [ingéré](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=fr) dans Adobe Experience Platform, [créer une connexion en Customer Journey Analytics](/help/connections/create-connection.md) à un ou plusieurs jeux de données d’expérience.

## Étape 2 : Ajouter des libellés de contexte dans les vues de données {#context-labels}

Dans les paramètres des vues de données du Customer Journey Analytics, les administrateurs peuvent ajouter [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure et à des services Customer Journey Analytics tels que [!UICONTROL Expérience] peuvent utiliser ces libellés à des fins pratiques. Deux libellés prédéfinis sont utilisés pour le panneau Expérimentation :

* [!UICONTROL Expérience d’expérimentation]
* [!UICONTROL Variante d’expérimentation]

Dans votre vue de données contenant des données d’expérimentation, sélectionnez deux dimensions, l’une avec les données d’expérimentation et l’autre avec les données de variante. Puis étiquetez ces dimensions avec les libellés **[!UICONTROL Expérience]** et **[!UICONTROL Variante]**.

![Options d’étiquette contextuelle pour la variation de l’expérience et de l’expérience.](assets/context-label.png)

Sans ces libellés, le panneau Expérience ne fonctionnera pas, puisqu’il n’y aura aucune expérience à utiliser.

## Étape 3 : Configurer le panneau Expérience {#configure}

1. Dans Customer Journey Analytics Workspace, faites glisser le panneau Expérience vers un projet.

![Le panneau Expérience a été déplacé dans un projet.](assets/experiment.png)

>[!IMPORTANT]
>Si la configuration nécessaire dans les vues de données du Customer Journey Analytics n’est pas terminée, vous recevrez ce message avant de pouvoir poursuivre : &quot;[!UICONTROL Configurez les dimensions de l’expérience et des variantes dans les vues de données.]&quot;.

1. Configurer les paramètres d’entrée du panneau.

   | Paramètre | Définition |
   | --- | --- |
   | **[!UICONTROL Expérience]** | Un ensemble de variantes sur une expérience qui ont été proposées aux utilisateurs finaux afin de déterminer laquelle il est préférable de conserver à perpétuité. Une expérience est composée de deux variantes ou plus, dont l’une est considérée comme la variante de contrôle. Ce paramètre est pré-renseigné avec des dimensions qui ont été étiquetées avec le libellé **[!UICONTROL Expérience]** dans les vues de données et l’équivalent de 3 mois de données d’expérience. |
   | **[!UICONTROL Variante de contrôle]** | Une, deux ou plusieurs modifications de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. Une variante doit être sélectionnée comme contrôle, et une seule variante peut être considérée comme la variante de contrôle. Ce paramètre est pré-renseigné avec les dimensions qui ont été étiquetées avec le libellé  **[!UICONTROL Variante]** dans les vues de données. Ce paramètre récupère les données de variante associées à cette expérience. |
   | **[!UICONTROL Mesures de succès]** | Mesure ou mesures avec lesquelles un utilisateur compare des variantes. La variante ayant le résultat le plus souhaitable pour la mesure de conversion (la plus élevée ou la plus faible) est déclarée « variante la plus performante » d’une expérience. Vous pouvez ajouter jusqu’à 5 mesures. |
   | **[!UICONTROL Mesure de normalisation]** | La base ([!UICONTROL personnes], [!UICONTROL sessions] ou [!UICONTROL événements]) sur laquelle un test sera exécuté. Par exemple, un test peut comparer les taux de conversion de plusieurs variantes où le **[!UICONTROL Taux de conversion]** est calculé comme **[!UICONTROL Conversions par session]** ou **[!UICONTROL Conversions par personne]**. |
   | **[!UICONTROL Période]** | La période est automatiquement définie, en fonction du premier événement reçu en Customer Journey Analytics pour l’expérience sélectionnée. Si nécessaire, vous pouvez limiter ou étendre la période à des délais plus spécifiques. |

1. Cliquez sur **[!UICONTROL Créer]**.

## Étape 4 : Consulter la sortie du panneau {#view}

Le panneau Expérimentation renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de vos expériences. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés. À tout moment, vous pouvez modifier le panneau en cliquant sur l’icône de modification en forme de crayon dans le coin supérieur droit.

Vous obtenez également un résumé textuel qui indique si l’expérience est concluante ou non et résume le résultat. La conclusion repose sur la signification statistique. (Voir la « méthodologie statistique » ci-dessous.) Vous pouvez afficher des nombres de synthèse pour la variante la plus performante avec l’effet élévateur et le degré de confiance les plus élevés.

Pour chaque mesure de succès sélectionnée, un tableau à structure libre et une tendance de taux de conversion sont affichés :

![Le résultat de l’expérience montre un tableau à structure libre et une tendance de taux de conversion.](assets/exp-output1.png)

Le graphique [!UICONTROL Linéaire] vous donne la performance du [!UICONTROL Contrôle] au lieu de la performance de [!UICONTROL Variante de contrôle] :

![Sortie de graphique en courbes affichant les performances de contrôle et de variation de contrôle.](assets/exp-output2.png)

>[!NOTE]
>
>Ce panneau ne prend actuellement pas en charge l’analyse des tests A/A.

## Étape 5 : Interpréter les résultats {#interpret}

1. **L&#39;expérience est concluante**: chaque fois que vous consultez le rapport d’expérimentation, Adobe analyse les données accumulées jusqu’à présent dans l’expérience et déclare une expérience comme &quot;concluante&quot; lorsque le degré de confiance valide dépasse un seuil de 95 % pour *au moins un* des variantes (avec une correction Benjamini-Hochberg appliquée lorsqu&#39;il y a plus de deux bras, afin de corriger pour plusieurs tests d&#39;hypothèse).

2. **Variante la plus performante** : lorsqu’une expérience est déclarée concluante, la variante ayant le taux de conversion le plus élevé est étiquetée comme « variante la plus performante ». Notez que cette variante doit être la variante de référence ou de contrôle, ou l’une des variantes qui dépasse les 95 % chaque fois que le seuil de confiance valide (avec des corrections Benjamini-Hochberg appliquées).

3. **Taux de conversion** : le taux de conversion qui s’affiche est un ratio de la valeur de la mesure de succès par rapport à la valeur de la mesure de normalisation. Notez que cette valeur peut parfois être supérieure à 1, si la mesure n’est pas binaire (1 ou 0 pour chaque unité de l’expérience).

4. **Effet élévateur** : la synthèse du rapport d’expérience affiche l’effet élévateur sur la ligne de base, qui est une mesure de l’amélioration en pourcentage du taux de conversion d’une variante donnée par rapport à la ligne de base. Défini précisément, il s’agit de la différence de performance entre une variante donnée et la ligne de base, divisée par les performances de la ligne de base, exprimée en pourcentage.

5. **Confiance** : le degré de confiance valide en tout temps qui s’affiche est une mesure probabiliste de l’ampleur des preuves qu’une variante donnée est identique à la variante de contrôle. Un degré de confiance plus élevé indique moins de preuves relatives à l’hypothèse que la variante de contrôle et la variante de non-contrôle ont des performances similaires. Plus précisément, la confiance affichée est une probabilité (exprimée en pourcentage) que nous aurions observé une différence plus faible dans les taux de conversion entre une variante donnée et celle de contrôle, si en réalité il n’y a aucune différence dans les taux de conversion réels sous-jacents. En termes de *p*-valeurs, la confiance affichée est 1 - *p*-valeur.

>[!NOTE]
>
>Notez toutefois qu’une description complète des résultats doit tenir compte de toutes les preuves disponibles (c’est-à-dire la conception de l’expérience, la taille des échantillons, les taux de conversion, le degré de confiance, etc.), et pas seulement de la déclaration du caractère concluant ou non. Même lorsqu’un résultat n’est pas encore « concluant », il peut encore y avoir des preuves convaincantes indiquant qu’une variante est différente d’une autre (par exemple, les intervalles de confiance sont presque sans chevauchement). Idéalement, la prise de décision doit être fondée sur toutes les preuves statistiques, interprétées sur un spectre continu.

## Méthodologie statistique d’Adobe {#statistics}

Afin de fournir une inférence statistique facile à interpréter et sûre, Adobe a adopté une méthodologie statistique fondée sur des [Séquences de confiance valides à tout moment](https://doi.org/10.48550/arXiv.2103.06476).

Une séquence de confiance est une analogie « séquentielle » d’un intervalle de confiance. Pour comprendre ce qu’est une séquence de confiance, imaginez que vous répétiez vos expériences cent fois et calculiez une estimation de la mesure commerciale moyenne (par exemple, le taux d’ouverture d’un e-mail) et de la séquence de confiance à 95 % qui lui est associée pour *chaque nouvel utilisateur* qui entre dans l’expérience.

Une séquence de confiance à 95 % inclura la valeur « True » de la mesure commerciale dans 95 des 100 expériences que vous avez exécutées. (Un intervalle de confiance à 95 % ne pouvait être calculé qu’une seule fois par expérience afin de garantir la même couverture de 95 % ; pas avec chaque nouvel utilisateur). Les séquences de confiance vous permettent donc de surveiller en permanence les expériences, sans augmenter les taux d’erreurs Faux positif, c’est-à-dire qu’elles permettent de « Jeter un coup d’œil » sur les résultats.

## Interprétation des dimensions non randomisées {#non-randomized}

Customer Journey Analytics permet aux analystes de sélectionner n’importe quelle dimension comme &quot;expérience&quot;. Mais comment interpréter une analyse où la dimension choisie comme expérience n&#39;est pas pour laquelle des personnes sont aléatoires ?

Prenons l’exemple d’une publicité qu’une personne voit. Il peut être intéressant de mesurer le changement de certaines mesures (par exemple, les recettes moyennes) si vous décidez d’afficher les personnes &quot;publicité B&quot; au lieu de &quot;publicité A&quot;. L’effet causal de l’affichage de la publicité B au lieu de la publicité A est d’une importance centrale pour arriver à la décision marketing. Cet effet de cause à effet peut être mesuré comme le revenu moyen sur l’ensemble de la population, si nous remplaçons le statu quo de l’affichage et de la publicité A par la stratégie alternative de l’affichage de la publicité B.

Les tests A/B sont l&#39;étalon-or de l&#39;industrie pour mesurer objectivement les effets de telles interventions. La raison essentielle pour laquelle un test A/B donne lieu à une estimation du lien de cause à effet est la randomisation des personnes qui reçoivent l’une des variantes possibles.

Considérons maintenant une dimension qui n&#39;est pas atteinte par l&#39;organisation aléatoire, par exemple, l&#39;état américain de la personne. Disons que nos personnes viennent principalement de deux états, New York et Californie. Les recettes moyennes des ventes d&#39;une marque de vêtements d&#39;hiver peuvent être différentes dans les deux états en raison des différences de conditions météorologiques régionales. Dans une telle situation, la météo peut être le véritable facteur de la vente des vêtements d&#39;hiver, et non le fait que les états géographiques des personnes sont différents.

Le panneau d’expérimentation du Customer Journey Analytics vous permet d’analyser les données sous la forme d’une différence de revenus moyenne par état de la personne. Dans une telle situation, la production n&#39;a pas d&#39;interprétation causale. Cependant, une telle analyse peut encore être intéressante. Il donne une estimation (ainsi que des mesures d’incertitude) de la différence de revenus moyens par les Etats de la personne. On parle également de &quot;test d’hypothèse statistique&quot;. Le résultat de cette analyse peut être intéressant, mais pas nécessairement exploitable, puisque nous n’avons pas, et parfois nous ne pouvons pas, randomiser les personnes selon l’une des valeurs possibles de la dimension.

L’illustration suivante présente un contraste entre ces situations :

![Diagramme présentant les données d’observation et l’expérience aléatoire.](assets/randomize.png)

Lorsque vous voulez mesurer l&#39;impact de l&#39;intervention X sur le résultat Y, il est possible que la cause réelle des deux soit le facteur de confusion C. Si les données ne sont pas obtenues en randomisant les personnes sur X, l’impact est plus difficile à mesurer, et l’analyse tiendra explicitement compte de C. L’aléatoire rompt avec la dépendance de X sur C, ce qui nous permet de mesurer l’effet de X sur Y sans avoir à nous soucier d’autres variables.

## Utilisation des mesures calculées dans le panneau Expérience

Consultez cet article de blog pour plus d’informations sur [utilisation de mesures dérivées dans le panneau Expérience](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
