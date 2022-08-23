---
description: Découvrez comment analyser les résultats des tests A/B dans le panneau d’expérimentation CJA.
title: Panneau d’expérience
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 15ef6bfc1d6600b3795310c208ad46c6f6b52254
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 5%

---

# Panneau d’expérience

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de [tests limités](/help/release-notes/releases.md).

Le **[!UICONTROL Expérience]** permet aux analystes de comparer différentes variations d’expérience utilisateur, de marketing ou de messagerie afin de déterminer quelle est la meilleure source d’un résultat spécifique. Vous pouvez évaluer l’effet élévateur et le degré de confiance de toute expérience A/B à partir de n’importe quelle plateforme d’expérimentation (en ligne, hors ligne, à partir de solutions d’Adobe, de Adobe Journey Optimizer et même de données BYO (apportez-vous).

>[!IMPORTANT]
>
>À ce stade, [Adobe Analytics pour Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=fr) (A4T) données importées dans Adobe Experience Platform via le connecteur source Analytics **cannot** sont analysées dans la variable [!UICONTROL Expérience] du panneau. Nous attendons une résolution de ce problème en 2023.

## Contrôle d’accès

Le panneau Expérience est disponible pour tous les utilisateurs de Customer Journey Analytics (CJA). Aucun droit d’administrateur ou autre autorisation n’est requis. Toutefois, la configuration (étapes 1 et 2 ci-dessous) nécessite des actions que seuls les administrateurs peuvent effectuer.

## Étape 1 : Créer une connexion à un ou plusieurs jeux de données d’expérience

Une fois que les données de l’expérience ont été [ingéré](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=fr) dans Adobe Experience Platform, [créer une connexion dans CJA ;](/help/connections/create-connection.md) à un ou plusieurs jeux de données d’expérience.

## Étape 2 : Ajout d’étiquettes contextuelles dans les vues de données

Dans les paramètres des vues de données CJA, les administrateurs peuvent ajouter [libellés de contexte](/help/data-views/component-settings/overview.md) à une dimension ou à une mesure et à des services CJA comme [!UICONTROL Expérience] peuvent utiliser ces libellés à des fins pratiques. Deux libellés prédéfinis sont utilisés pour le panneau Expérience :

* [!UICONTROL Expérience]
* [!UICONTROL Variante]

Dans votre vue de données contenant des données d’expérimentation, sélectionnez deux dimensions, l’une avec les données d’expérimentation et l’autre avec les données de variante. Puis étiquetez ces dimensions avec la variable **[!UICONTROL Expérience]** et le **[!UICONTROL Variante]** libellés.

![libellé du contexte](assets/context-label.png)

Sans ces étiquettes, le panneau Expérience ne fonctionne pas, puisqu’il n’y aura aucune expérience à utiliser.

## Étape 3 : Configuration du panneau Expérience

1. Dans CJA Workspace, faites glisser le panneau Expérimentation dans un projet.

![test panel](assets/experiment.png)

>[!IMPORTANT]
>Si la configuration nécessaire dans les vues de données CJA n’a pas été effectuée, vous recevrez un message à cet effet avant de pouvoir continuer.

1. Configurez les paramètres d’entrée du panneau.

   | Paramètre | Définition |
   | --- | --- |
   | **[!UICONTROL Expérience]** | Ensemble de variations d’une expérience qui ont été exposées aux utilisateurs finaux afin de déterminer la meilleure expérience à conserver perpétuellement. Une expérience est composée de deux variantes ou plus, dont l’une est considérée comme la variante témoin. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec la variable  **[!UICONTROL Expérience]** libellé dans les vues de données et l’équivalent de 3 mois de données d’expérience. |
   | **[!UICONTROL Variante de contrôle]** | L’une des deux modifications ou plus de l’expérience d’un utilisateur final qui sont comparées dans le but d’identifier la meilleure alternative. Une variante doit être sélectionnée comme contrôle, et une seule variante peut être considérée comme la variante de contrôle. Ce paramètre est prérenseigné avec les dimensions qui ont été étiquetées avec la variable  **[!UICONTROL Variante]** dans les vues de données. Ce paramètre récupère les données de variante associées à cette expérience. |
   | **[!UICONTROL Mesures de succès]** | Mesure ou mesure avec laquelle un utilisateur compare des variantes. La variante ayant le résultat le plus souhaitable pour la mesure de conversion (la plus élevée ou la plus faible) est déclarée &quot;variante la plus performante&quot; d’une expérience. Vous pouvez ajouter jusqu’à 5 mesures. |
   | **[!UICONTROL Mesure de normalisation]** | La base ([!UICONTROL Personnes], [!UICONTROL Sessions]ou [!UICONTROL Événements]) sur laquelle un test sera exécuté. Par exemple, un test peut comparer les taux de conversion de plusieurs variantes où **[!UICONTROL Taux de conversion]** est calculé comme **[!UICONTROL Conversions par session]** ou **[!UICONTROL Conversions par personne]**. |
   | **[!UICONTROL Période]** | La période est automatiquement définie, en fonction du premier accès reçu dans CJA pour l’expérience sélectionnée. Si nécessaire, vous pouvez limiter ou étendre la période à une période plus spécifique. |

1. Cliquez sur **[!UICONTROL Créer]**.

## Étape 4 : Interprétation de la sortie du panneau

Le panneau Expérience renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de vos expériences. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés. Vous pouvez à tout moment modifier le panneau en cliquant sur le crayon de modification en haut à droite.

Vous obtenez également un résumé textuel qui indique si l’expérience est concluante ou non et résume le résultat. La conclusion repose sur la signification statistique. (Voir la &quot;méthodologie statistique&quot; ci-dessous.) Vous pouvez afficher des nombres de synthèse pour la variante la plus performante avec l’effet élévateur et le degré de confiance les plus élevés.

>[!NOTE]
>
>L’effet élévateur et le degré de confiance sont également [fonctions de mesures calculées avancées](/help/components/calc-metrics/cm-adv-functions.md) dans CJA, afin que vous puissiez créer vos propres mesures d’effet élévateur et de confiance.

![sortie d’expérience](assets/exp-output1.png)

Pour chaque mesure de succès sélectionnée, un tableau à structure libre et une tendance de taux de conversion sont affichés :

![sortie d’expérience](assets/exp-output2.png)

Le [!UICONTROL Ligne] Le graphique vous donne la variable [!UICONTROL Contrôle] versus [!UICONTROL Variante de contrôle] performance :

![sortie d’expérience](assets/exp-output3.png)

>[!NOTE]
>
>Ce panneau ne prend actuellement pas en charge l’analyse des tests A/A.

## Méthodologie statistique de l&#39;Adobe

Afin de fournir une inférence statistique facile à interpréter et sûre, l&#39;Adobe a adopté une méthodologie statistique fondée sur des [À Tout Moment De Séquences De Confiance Valides](https://doi.org/10.48550/arXiv.2103.06476).

Une séquence de confiance est une analogie &quot;séquentielle&quot; d’un intervalle de confiance. Pour comprendre ce qu’est une séquence de confiance, imaginez répéter vos expériences cent fois et calculer une estimation de la mesure commerciale moyenne (par exemple, le taux d’ouverture d’un email) et de la séquence de confiance à 95 % qui lui est associée pour *chaque nouvel utilisateur* qui entre dans l&#39;expérience. Une séquence de confiance de 95 % inclura la valeur &quot;true&quot; de la mesure commerciale dans 95 des 100 expériences que vous avez exécutées. (Un intervalle de confiance de 95 % ne pouvait être calculé qu&#39;une seule fois par expérience afin de garantir la même couverture de 95 % ; pas avec chaque nouvel utilisateur). Les séquences de confiance vous permettent donc de surveiller en permanence les expériences, sans augmenter les taux d’erreur Faux positif, c’est-à-dire qu’elles permettent de &quot;regarder&quot; les résultats.

### Interprétation des résultats

1. **L&#39;expérience est concluante**: Chaque fois que vous consultez le rapport d’expérimentation, Adobe analyse les données accumulées jusqu’à présent dans l’expérience et déclare une expérience comme &quot;concluante&quot; lorsque la confiance valide dépasse un seuil de 95 % pour *au moins un* des variantes (avec une correction Bonferonni appliquée lorsqu&#39;il y a plus de deux bras, afin de corriger pour plusieurs tests d&#39;hypothèse).

2. **Variante la plus performante**: Lorsqu’une expérience est déclarée concluante, la variante ayant le taux de conversion le plus élevé est étiquetée comme &quot;variante la plus performante&quot;. Notez que cette variante doit être la variante de référence ou de contrôle, ou l’une des variantes qui dépasse les 95 % chaque fois que le seuil de confiance valide (avec des corrections Bonferonni appliquées).

3. **Taux de conversion**: Le taux de conversion qui s’affiche est un ratio de la valeur de la mesure de succès par rapport à la valeur de la mesure de normalisation. Notez que cette valeur peut parfois être supérieure à 1, si la mesure n’est pas binaire (1 ou 0 pour chaque unité de l’expérience).

4. **Effet élévateur**: Le résumé du rapport d’expérience affiche l’effet élévateur sur la ligne de base, qui est une mesure de l’amélioration en pourcentage du taux de conversion d’une variante donnée par rapport à la ligne de base. Défini précisément, il s’agit de la différence de performance entre une variante donnée et la ligne de base, divisée par les performances de la ligne de base, exprimée en pourcentage.

5. **Confiance**: La fiabilité en tout temps qui s’affiche est une mesure probabiliste de l’ampleur des preuves qu’une variante donnée est identique à la variante témoin. Une confiance plus élevée indique moins de preuves que la variante de contrôle et la variante de non-contrôle ont des résultats égaux. Plus précisément, la confiance affichée est une probabilité (exprimée en pourcentage) que nous aurions observée une différence plus faible dans les taux de conversion entre une variante donnée et le contrôle, si en réalité il n’y a aucune différence dans les taux de conversion réels sous-jacents. En termes de *p*-values, la confiance affichée est 1 - *p*-value.

Notez toutefois qu’une description complète des résultats doit tenir compte de toutes les preuves disponibles (c’est-à-dire la conception de l’expérience, la taille des échantillons, les taux de conversion, le degré de confiance, etc.), et pas seulement de la déclaration concluante ou non. Même lorsqu’un résultat n’est pas encore &quot;concluant&quot;, il peut encore y avoir des preuves convaincantes pour qu’une variante soit différente d’une autre (par exemple, les intervalles de confiance sont presque sans chevauchement). Idéalement, la prise de décision doit être fondée sur toutes les données statistiques, interprétées sur un spectre continu.
