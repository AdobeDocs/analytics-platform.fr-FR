---
title: Pourquoi les données GA4 et Customer Journey Analytics sont différentes
description: Découvrez pourquoi les données entre GA4 et Customer Journey Analytics peuvent différer et comment auditer les incohérences.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# Pourquoi les données GA4 et Customer Journey Analytics sont différentes

Il est normal que GA4 et Customer Journey Analytics signalent des nombres différents pour la même période et la même mesure apparente. Différentes méthodes de collecte de données, définitions de mesures, modèles d’identité et règles de session contribuent tous aux écarts. Cette page explique les sources de différence les plus courantes et fournit des conseils pour auditer les écarts inexpliqués.

## Sessions engagées

GA4 considère une session comme **engagée** si elle a duré 10 secondes ou plus, si elle a inclus au moins un événement clé ou si elle a eu 2 pages vues ou plus. Cette définition unique sous-tend plusieurs mesures GA4, notamment le taux d’engagement, le taux de rebond et le seuil d’engagement derrière les utilisateurs et utilisatrices actifs.

Customer Journey Analytics ne comporte aucune mesure ou dimension de session engagée intégrée ; vous définissez l’engagement en fonction de votre entreprise. Adobe recommande de créer un segment qui recueille vos critères d’engagement et de réutiliser ce segment là où l’engagement compte. Votre administrateur peut également convertir cette définition en mesure dans la vue de données afin qu’elle soit disponible pour tous.

Lorsque vous formulez vos propres critères, choisissez les signaux qui indiquent véritablement la valeur de votre site. Trois éléments de base communs à l’engagement :

* **Durée** : durée de session minimale, par exemple 10 secondes ou plus
* **Profondeur** : nombre minimal d’événements ou de pages vues, par exemple 2 ou plus
* **Action** : présence d’une conversion ou d’un événement clé, tel qu’une inscription ou un achat

Vous pouvez les combiner avec `OR` afin qu’une session soit considérée comme engagée si elle répond à n’importe quelle condition (comme le fait GA4) ou les combiner avec `AND` pour une exigence plus stricte. Si votre objectif est la parité avec GA4, commencez à partir de ses valeurs par défaut et effectuez les réglages à partir de là.

### Taux d’engagement

Une fois que vous disposez d’une définition de sessions engagées, le taux d’engagement est la part des sessions qui ont été engagées. Pour la créer en tant que mesure calculée :

1. Dans Analysis Workspace, sélectionnez l’icône **[!UICONTROL +]** près de la liste des mesures pour ouvrir le créateur de mesures calculées.
2. Nommez-le « Taux d’engagement » et définissez le format sur **[!UICONTROL Pourcentage]**.
3. Définissez la formule comme segment des sessions engagées divisé par **[!UICONTROL Sessions]**.
4. Sélectionnez **[!UICONTROL Enregistrer]**.

### Taux de rebond

Dans GA4, un rebond est l’inverse d’une session engagée ; le taux de rebond de GA4 est donc égal à `1 - Engagement Rate`. Créez-le dans Customer Journey Analytics sous la forme d’une deuxième mesure calculée à l’aide de cette formule.

Customer Journey Analytics fournit également une mesure intégrée **[!UICONTROL Taux de rebond]**, mais sa définition par défaut diffère : il comptabilise les sessions au cours desquelles un seul événement a été enregistré, ce qui est directionnellement opposé à la définition de GA4 pour de nombreux sites. La comparaison du taux de rebond de GA4 à la mesure par défaut [!UICONTROL Taux de rebond] plutôt qu’à votre calcul de `1 - Engagement Rate`, génère des chiffres significativement différents.

>[!TIP]
>
>La définition de session dans Customer Journey Analytics peut être configurée par vue de données. Les définitions des bounces et des engagements peuvent être ajustées pour correspondre aux critères de GA4 (durée de 10 secondes, 2 pages vues ou plus, ou un événement clé) si cette parité est une exigence de création de rapports pour votre organisation.

## Sessions

GA4 et Customer Journey Analytics appliquent par défaut un délai d’inactivité de 30 minutes, et toutes deux maintiennent une session ouverte jusqu’à minuit et lors d’un changement de campagne en milieu de session. (Universal Analytics a réinitialisé les sessions dans ces deux cas de figure. Il s’agit donc d’une source fréquente de confusion, mais il ne s’agit pas de différences entre GA4 et Customer Journey Analytics.) Les règles qui diffèrent sont les suivantes :

| Composants de | GA4 | Customer Journey Analytics |
|---|---|---|
| Délai d’inactivité | Réglable à l’échelle de la propriété (30 minutes par défaut, jusqu’à 7 heures 55 minutes) | Configurable par vue de données |
| Événements de démarrage de session | `session_start` uniquement (automatique) | Configurable ; tout événement peut démarrer une session. |
| Événements de fin de session | Aucun | Configurable : tout événement peut mettre fin à une session. |

Comme la définition de session Customer Journey Analytics est configurable, le nombre de sessions dépend de la configuration de votre vue de données. La mise en correspondance du délai d’expiration et des événements de démarrage de session d’une vue de données avec votre propriété GA4 rapproche le nombre de sessions entre les plateformes.

## Personnes et utilisateurs actifs

La mesure principale relative aux utilisateurs de GA4, **Utilisateurs actifs**, comptabilise les utilisateurs qui ont eu au moins une session engagée dans la période. La mesure **[!UICONTROL Personnes]** dans Customer Journey Analytics comptabilise les ID de personne uniques dans la période.

Attendez-vous à ce que ces mesures diffèrent pour plusieurs raisons :

* **Seuil d’engagement** : les utilisateurs actifs GA4 excluent les visiteurs qui n’ont eu aucune [session engagée](#engaged-sessions). La mesure [!UICONTROL Personnes] dans Customer Journey Analytics inclut tout le monde, quel que soit le niveau d’engagement.
* **[!UICONTROL Groupement]** : si le regroupement est activé, une personne ayant consulté à la fois à partir d’un appareil mobile et d’un bureau peut être comptabilisée comme une personne dans Customer Journey Analytics, mais comme deux utilisateurs dans GA4. L’assemblage rend généralement la mesure [!UICONTROL Personnes] inférieure aux utilisateurs GA4 sur les jeux de données assemblés.
* **Modèle d’identité** : GA4 utilise un modèle d’identité en cascade ; Customer Journey Analytics utilise l’ID de personne défini dans le jeu de données. Ces différences affectent le nombre de personnes indépendamment du groupement.

## Identité et groupement

GA4 utilise un modèle d’identité en cascade pour identifier les utilisateurs :

1. ID d’utilisateur (si défini par votre implémentation)
2. Signaux Google (si l’utilisateur est connecté à un compte Google avec la personnalisation activée)
3. Identifiant de l’appareil (identifiant client basé sur des cookies)

Dans la plupart des mises en œuvre, cet ID de personne est un ECID (Experience Cloud ID). La fonctionnalité facultative **[!UICONTROL Assemblage]** peut ensuite résoudre les identités entre appareils et entre canaux à l’aide de méthodes basées sur les champs ou sur des graphiques, ce qui permet d’associer une session d’application mobile et une session de navigateur de bureau à la même personne.

Comme la résolution des identités diffère entre les plateformes, les décomptes au niveau de l’utilisateur correspondent rarement exactement. Cette incohérence est attendue et n’indique pas de problème de qualité des données.

## Attribution

GA4 applique un modèle d’attribution de rapports configuré au niveau de la propriété (sous Admin), avec l’attribution pilotée par les données comme valeur par défaut. Comme Customer Journey Analytics, GA4 évalue ce modèle au moment du rapport. Par conséquent, sa modification met à jour les rapports historiques et futurs de manière rétroactive. Toutefois, dans GA4, le modèle s’applique à l’ensemble des propriétés et affecte uniquement les rapports d’événements clés qui utilisent des dimensions de trafic de portée événement (telles que Source, Medium et Campaign).

Customer Journey Analytics applique également l’attribution au moment du rapport, mais avec un contrôle plus granulaire. Vous pouvez le configurer à deux endroits :

* **Paramètres de vue de données** : un [modèle d’attribution](/help/data-views/component-settings/attribution.md) peut être défini sur n’importe quel composant de mesure de la vue de données, établissant la valeur par défaut de cette mesure dans tous les rapports. Aucun modèle d’attribution n’est appliqué par défaut. Vous pouvez configurer une vue de données pour contenir plusieurs copies de la même mesure, chacune utilisant un modèle d’attribution par défaut différent.
* **Remplacement au niveau du composant** : après avoir fait glisser une mesure dans un [!UICONTROL tableau à structure libre], cliquez avec le bouton droit sur son en-tête de colonne et sélectionnez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]** pour la remplacer pour cette instance. Vous pouvez également faire glisser plusieurs fois la même mesure dans le tableau, chacune d’elles utilisant un modèle d’attribution différent pour une comparaison directe côte à côte.

GA4 étant défini par défaut sur l’attribution pilotée par les données, alors que Customer Journey Analytics n’applique aucun modèle, sauf si vous en configurez un, les mesures de conversion et de canal sont susceptibles de différer jusqu’à ce que vous les alignez. La définition de GA4 sur un modèle de dernier clic et la configuration d’un modèle de dernière touche correspondant dans Customer Journey Analytics est le moyen le plus fiable d’établir une ligne de base similaire. Toute modification du modèle dans Customer Journey Analytics s’applique rétroactivement à toutes les données historiques sans retraitement.

## Incohérences d’audit

Lorsque les chiffres diffèrent plus que prévu, trois chemins d’audit sont disponibles :

* **** : l’outil de validation intégré au produit Adobe confirme que les événements XDM se déclenchent correctement, atteignent Edge Network et sont écrits dans les jeux de données Platform. Utilisez cet outil pour vérifier votre implémentation avant de comparer les numéros de rapport.
* **Prévisualisations des jeux de données** : dans l’interface utilisateur de Platform, vous pouvez prévisualiser les lignes brutes de n’importe quel jeu de données. Comparez-les à l’exportation DebugView ou BigQuery de GA4 pour vérifier la précision au niveau du champ.
* **** : en cas d’incohérences persistantes et inexpliquées, votre équipe de compte Adobe peut organiser un audit formel de la mise en œuvre avec un consultant Adobe.
* **Révision de l’ingestion** : si vous pensez que la différence provient de la manière dont les données GA ont été importées dans Platform plutôt que dans les définitions de rapports, consultez la configuration de l’ingestion dans [Migration des données depuis Google Analytics](/help/use-cases/third-party/ga/overview.md).
