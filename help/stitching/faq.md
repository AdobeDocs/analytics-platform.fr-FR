---
title: FAQ sur l’assemblage
description: Questions fréquentes sur le groupement
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: c60c68e6065e877d0fa4a92dbfe8dd54a2dfb4fe
workflow-type: tm+mt
source-wordcount: '2046'
ht-degree: 26%

---

# Questions fréquentes

Voici quelques questions fréquentes sur le groupement :

## Déplacement sur plusieurs canaux

+++ Comment puis-je utiliser le groupement pour voir comment les gens passent d&#39;un canal à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Identifiant du jeu de données.

1. Connectez-vous à [Customer Journey Analytics](https://analytics.adobe.com) et créez un projet Workspace vierge.
2. Sélectionnez l’onglet **[!UICONTROL ** Visualisations **]** à gauche, puis faites glisser une visualisation **[!UICONTROL **&#x200B; Flux &#x200B;**]** vers la zone de travail à droite.
3. Sélectionnez l’onglet **[!UICONTROL ** Composants **]** à gauche, puis faites glisser la dimension **[!UICONTROL ** Identifiant du jeu de données **]** vers l’emplacement central intitulé **[!UICONTROL **&#x200B; Dimension ou Élément &#x200B;**]**.
4. Ce rapport de flux est interactif. Pour développer les flux sur les pages suivantes ou précédentes, sélectionnez l’une des valeurs. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

Si vous souhaitez renommer des éléments de dimension Identifiant du jeu de données, vous pouvez utiliser un jeu de données de recherche.

+++

## Replay

+++ Jusqu’à combien de temps en arrière l’assemblage des visiteurs rejoue-t-il ?

L’intervalle de recherche en amont pour la recomposition des données dépend de la fréquence de relecture des données souhaitée. Par exemple, si vous configurez le groupement pour lire les données une fois par semaine, l’intervalle de recherche en amont pour la recomposition des données est de sept jours. Si vous configurez le groupement pour la relecture quotidienne des données, l’intervalle de recherche en amont pour la recomposition des données est d’un jour.

+++

## Périphériques partagés

+++ Comment les appareils partagés sont-ils gérés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

L’identifiant transitoire a priorité sur l’identifiant persistant, de sorte que les appareils partagés sont considérés comme des personnes distinctes (même s’ils proviennent du même appareil).

Voir le cas d’utilisation [Appareils partagés](/help/use-cases/stitching/shared-devices.md) pour plus d’informations.

+++

## De nombreux identifiants persistants

+++ Comment le groupement gère-t-il les situations où une seule personne possède de nombreux identifiants persistants ?

Dans certains cas, un utilisateur individuel peut être associé à un grand nombre d’identifiants persistants. Par exemple, un individu efface fréquemment les cookies du navigateur ou utilise le mode privé/incognito du navigateur.

Pour le groupement basé sur les champs, le nombre d’identifiants persistants n’est pas pertinent en faveur de l’identifiant transitoire. Un seul utilisateur peut appartenir à un nombre illimité d’appareils sans que cela n’ait d’incidence sur la capacité de Customer Journey Analytics à regrouper les appareils.

Pour le groupement basé sur les graphiques, une seule personne peut avoir de nombreux identifiants persistants dans le graphique d’identité. Le groupement basé sur les graphiques utilise l’identifiant persistant en fonction de l’espace de noms spécifié. S’il existe d’autres identifiants persistants pour le même espace de noms, le premier identifiant persistant lexicographique est utilisé.

+++

## Processus de groupement

+++ Une fois que j’ai contacté mon équipe Adobe en charge des comptes pour obtenir les informations souhaitées, combien de temps faut-il pour que le jeu de données recomposées soit disponible ?

L’assemblage en direct est disponible environ une semaine après l’activation de l’assemblage par Adobe. La disponibilité du renvoi dépend de la quantité de données existantes. Les petits jeux de données (moins d’un million d’événements par jour) prennent généralement deux jours, tandis que les grands jeux de données (1 milliard d’événements par jour) peuvent prendre une semaine ou plus.

+++

## Analyse entre appareils et analyse cross-canal

+++ Quelle est la différence entre l’analyse entre appareils (une fonctionnalité d’Analytics classique) et l’analyse cross-canal ?

L’[analyse entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) est une fonctionnalité spécifique à Adobe Analytics traditionnel qui vous permet de comprendre le comportement des personnes sur plusieurs appareils. Elle offre deux workflows pour lier les données de l’appareil : l’assemblage basé sur les champs et le graphique d’appareil.

L’analyse cross-canal est un cas d’utilisation spécifique à Customer Journey Analytics qui vous permet de comprendre le comportement des personnes à la fois sur plusieurs appareils et plusieurs canaux. Il regroupe l’ID de personne d’un jeu de données, ce qui permet de combiner facilement ce jeu de données avec d’autres. Cette fonctionnalité s’exécute de la même manière que le groupement basé sur les champs d’analyses entre appareils. Toutefois, son implémentation est différente en raison de l’architecture des données qui diffère entre Analytics classique et Customer Journey Analytics. Voir les sections [&#x200B; Assemblage &#x200B;](overview.md) et le cas d’utilisation [&#x200B; Analyse cross-canal &#x200B;](../use-cases/cross-channel/cross-channel.md) pour plus d’informations.

+++

## Confidentialité

+++ Comment l’assemblage gère-t-il les demandes d’accès à des informations personnelles ?

Adobe gère les demandes d’accès à des informations personnelles conformément aux lois locales et internationales. Adobe propose [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour soumettre des demandes d’accès et de suppression de données. Ces demandes s’appliquent aussi bien aux jeux de données originaux qu’aux jeux de données recomposés.

>[!IMPORTANT]
>
>Le processus de désassemblage, dans le cadre des demandes d’accès à des informations personnelles, change début 2025. Le processus de désassemblage actuel réassemble les événements à l’aide de la dernière version des identités connues. Cette réaffectation d&#39;événements à une autre identité pourrait avoir des conséquences juridiques indésirables. Pour résoudre ces problèmes, à partir de 2025, le nouveau processus d’assemblage met à jour les événements qui font l’objet de la demande d’accès à des informations personnelles avec l’identifiant persistant.
> 

À titre d’illustration, imaginez les données suivantes pour les identités, les événements avant et après l’assemblage.

| Mappage d’identités | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Jeu de données d’événements | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Jeu de données groupé | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire | ID regroupé | Espace de noms groupé |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Processus actuel pour la demande d’accès à des informations personnelles**

Lorsqu’une demande d’accès à des informations personnelles est reçue pour un client avec CustID Bob, les lignes comportant des entrées barrées sont supprimées. D’autres événements sont regroupés à l’aide du mappage d’identités. Par exemple, le premier identifiant assemblé dans le jeu de données assemblé est mis à jour sur **Alex**.

| Mappage d’identités | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Jeu de données d’événements | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Jeu de données groupé | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire | ID regroupé | Espace de noms groupé |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Nouveau processus pour les demandes d&#39;accès à des informations personnelles**

Lorsqu’une demande d’accès à des informations personnelles est reçue pour un client avec CustID Bob, les lignes comportant des entrées barrées sont supprimées. D’autres événements sont regroupés à l’aide de l’identifiant persistant. Par exemple, le premier identifiant assemblé dans le jeu de données assemblé est mis à jour à **123**.

| Mappage d’identités | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Jeu de données d’événements | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Jeu de données groupé | Id | timestamp | identifiant persistant | espace de noms persistant | id transitoire | espace de noms transitoire | ID regroupé | Espace de noms groupé |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Valeurs d’ID persistantes vides

+++ Que se passe-t-il si le champ de lʼidentifiant persistant dʼun ou de plusieurs événements est vide ?

Si le champ ID persistant est vide sur un événement d’un jeu de données assemblé , l’ID assemblé de cet événement est déterminé de l’une des deux façons suivantes :

* Si le champ ID transitoire n’est pas vide, Customer Journey Analytics utilise la valeur de l’ID transitoire comme ID d’assemblage.
* Si le champ ID temporaire est vide, Customer Journey Analytics laisse également vide l’ID groupé. Dans ce cas, l’ID persistant, l’ID temporaire et l’ID groupé sont tous vides pour l’événement. Ces types d’événements sont ignorés de toute connexion Customer Journey Analytics utilisant le jeu de données assemblé là où l’ID assemblé a été choisi comme ID de personne.

+++


## Valeurs d’ID transitoires non définies

+++ Que se passe-t-il si le champ ID transitoire d’un ou plusieurs événements comporte des valeurs d’espace réservé, telles que `Undefined` ?

Attention à la « réduction d’une personne », qui se produit lorsque le groupement est appliqué aux données qui utilisent des valeurs d’espace réservé pour les ID temporaires. Dans l’exemple de tableau ci-dessous, les ID de personne non définis provenant d’un jeu de données provenant d’un système CRM sont renseignés avec la valeur « Non défini », ce qui entraîne une représentation incorrecte des personnes.

| Événement | Date et heure | ID persistant (ID de cookie) | ID temporaire (ID de connexion) | ID groupé (après relecture) |
|---|---|---|---|---|
| 1 | 12/05/2023 12:01 | 123 | - | **Cory** |
| 2 | 12/05/2023 12:02 | 123 | Cory | **Cory** |
| 3 | 12/05/2023 12:03 | 456 | Non défini | **Non défini** |
| 4 | 12/05/2023 12:04 | 456 | - | **Non défini** |
| 5 | 12/05/2023 12:05 | 789 | Non défini | **Non défini** |
| 6 | 12/05/2023 12:06 | 012 | Non défini | **Non défini** |
| 7 | 12/05/2023 12:07 | 012 | - | **Non défini** |
| 8 | 12/05/2023 12:03 | 789 | Non défini | **Non défini** |
| 9 | 12/05/2023 12:09 | 456 | - | **Non défini** |
| 10 | 12/05/2023 12:02 | 123 | - | **Cory** |
| | | appareils **4** | **2 people**:<br/>Events 1, 4, 7, 9, 10 dropped | **2 personnes**:<br/>Cory, Non authentifié (réduit à une seule personne) |

+++

## Comparaison des mesures

+++ Comment les mesures des jeux de données groupés Customer Journey Analytics se comparent-elles à des mesures similaires dans les jeux de données non groupés Customer Journey Analytics et avec Adobe Analytics ?

Certaines mesures de Customer Journey Analytics sont similaires à celles d’Analytics classique, mais d’autres sont différentes en fonction de ce que vous comparez. Le tableau ci-dessous compare plusieurs mesures courantes :

| **Données groupées de Customer Journey Analytics** | **Données non groupées de Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate avec CDA** |
| ----- | ----- | ----- | ----- |
| **Personnes** = nombre d’ID de personne distincts où l’ID groupé est choisi comme ID de personne. Le nombre de **Personnes** peut être plus ou moins élevé que les **Visiteurs uniques** dans Adobe Analytics traditionnel, en fonction du résultat du processus dʼassemblage. | **Personnes** = nombre d’ID de personne distincts en fonction de la colonne sélectionnée en tant qu’ID de personne. La mention **Personnes** dans les jeux de données du connecteur source Analytics est similaire à la mention **Visiteurs uniques** dans Adobe Analytics traditionnel si `endUserIDs._experience.aaid.id` est utilisé comme ID de personne dans Customer Journey Analytics. | **Visiteurs uniques** = nombre dʼidentifiants de visiteur distincts. Le nombre de **Visiteurs uniques** peut être différent du nombre d’**ECID** distincts. | Voir [Personnes](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=fr). |
| **Sessions** : définies en fonction des paramètres de session dans la vue de données Customer Journey Analytics. Le processus dʼassemblage peut combiner des sessions individuelles provenant de plusieurs appareils en une seule session. | **Sessions** : défini en fonction des paramètres de session spécifiés dans la vue de données Customer Journey Analytics. | **Visites** : voir [Visites](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=fr). | **Visites** : défini en fonction des paramètres de session réglés dans la [suite de rapports virtuelle CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=fr). |
| **Événements** = nombre de lignes dans les données groupées dans Customer Journey Analytics. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Notez toutefois que la FAQ ci-dessus concernant les lignes avec un ID persistant vide. | **Événements** = nombre de lignes dans les données non groupées dans Customer Journey Analytics. Cette mesure est généralement proche des **Occurrences** dans Adobe Analytics classique. Notez toutefois que si des événements dont l’ID de personne est vide dans les données désassemblées du lac de données Experience Platform, ces événements ne sont pas inclus dans Customer Journey Analytics. | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). | **Occurrences** : voir [Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=fr). |

D’autres mesures peuvent être similaires dans Customer Journey Analytics et Adobe Analytics. Par exemple, le nombre total d’Adobe Analytics [événements personnalisés](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=fr) compris entre 1 et 100 est comparable entre Adobe Analytics traditionnel et Customer Journey Analytics (assemblé ou désassemblé). [Les différences de fonctionnalités](/help/getting-started/aa-vs-cja/cja-aa.md)) telles que la déduplication des événements entre Customer Journey Analytics et Adobe Analytics peuvent entraîner des incohérences entre les deux produits.

+++

## Mappage d’identités

+++ Customer Journey Analytics peut-il utiliser les champs de carte des identités ?

Oui, Customer Journey Analytics peut utiliser les champs de carte des identités pour le groupement [basé sur les champs](/help/stitching/fbs.md#identitymap) et [basé sur les graphiques](/help/stitching/gbs.md#identitymap).

+++

## Basculer vers le groupement basé sur les graphiques

+++ Les données devront-elles être réingérées pour passer d’un groupement basé sur les champs à un groupement basé sur les graphiques ?

Les données n’ont pas besoin d’être réingérées dans Experience Platform, mais elles devront être reconfigurées dans Customer Journey Analytics. Procédez comme suit :

1. Configurez le nouveau jeu de données groupé basé sur des graphiques.
1. Configurez le nouveau jeu de données dans le cadre d’une nouvelle connexion dans Customer Journey Analytics.
1. Changer votre vue de données existante pour utiliser la nouvelle connexion (et, à ce titre, le nouveau jeu de données groupé basé sur des graphiques).
1. Supprimez l’ancienne connexion qui utilisait le jeu de données groupé basé sur les champs.

+++

## Perturbation des rapports

+++ Les rapports existants seraient-ils interrompus ?

Pas si vous suivez les étapes décrites ci-dessus. Sinon, veuillez demander une assistance supplémentaire à Adobe Consulting.

+++

## Activation d’un jeu de données pour Identity Service

+++ Comment activer un jeu de données pour Identity Service uniquement ? 

Vous devez vous assurer qu’un jeu de données est activé pour qu’Identity Service puisse l’utiliser dans un groupement basé sur des graphiques.

Il n’est pas nécessaire d’être titulaire d’une licence pour que Real-Time Customer Data Platform puisse utiliser le groupement basé sur les graphiques. L’assemblage basé sur des graphiques est basé sur un graphique d’identités disponible et non sur des profils clients en temps réel.

Pour activer un jeu de données pour Identity Service uniquement, envoyez une requête `POST` au point d’entrée `/datasets` qui utilise uniquement la balise `unifiedIdentity` . Par exemple :

```shell
curl -X POST \
  https://platform.adobe.io/data/foundation/catalog/dataSets \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
    "schemaRef": {
        "id": "https://ns.adobe.com/{TENANT_ID}/schemas/31670881463308a46f7d2cb09762715",
        "contentType": "application/vnd.adobe.xed-full-notext+json; version=1"
    },
    "tags": {
       "unifiedIdentity": ["enabled:true"]
    }
  }'
```

Toute utilisation de la balise `unifiedProfile` dans la requête, tant que vous ne disposez pas d’une licence pour le profil de données client en temps réel, renvoie une erreur.

Voir [Créer un jeu de données activé pour Profil et Identité](https://experienceleague.adobe.com/fr/docs/experience-platform/catalog/datasets/enable-for-profile#create-a-dataset-enabled-for-profile-and-identity) pour plus d’informations.

+++ 
