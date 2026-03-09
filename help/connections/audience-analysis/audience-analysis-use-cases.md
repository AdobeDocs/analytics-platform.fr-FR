---
title: Cas D’Utilisation De L’Analyse De L’Audience
description: Découvrez les cas d’utilisation de l’analyse d’audience.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
exl-id: 4f465e71-f1b5-4f38-a1db-645550856849
source-git-commit: d14163794fd4d31b29bfc6f55622d839b67ab3d7
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Cas d’utilisation de l’analyse de l’audience {#analyze-audiences-use-cases}

L’analyse de l’audience permet la création de rapports sur les données d’appartenance à une audience Experience Platform dans Customer Journey Analytics. Pour ce faire, les configurations sont gérées via l’assistant de configurations de l’analyse de l’audience, qui vous aide à déterminer le jeu de données de profil que vous ingérez, ainsi que d’autres paramètres et détails de configuration. (Pour obtenir des informations de présentation plus détaillées, voir [Présentation de l’analyse de l’audience](/help/connections/audience-analysis/audience-analysis-overview.md). )

Ce document comprend des exemples de cas d’utilisation qui mettent en évidence la valeur fournie par Audience Analysis. Avant de passer en revue les cas d’utilisation, familiarisez-vous d’abord avec les considérations relatives aux rapports ci-dessous. Il est important de garder ces considérations à l’esprit lorsque vous passez en revue vos cas d’utilisation, car elles peuvent avoir un impact sur la sortie finale de vos rapports.

## Considérations relatives aux rapports

La version initiale de l’analyse de l’audience jette les bases du traitement et de l’ingestion des audiences Experience Platform dans Customer Journey Analytics. Lors de la réalisation de votre analyse, il est important de tenir compte de plusieurs facteurs qui peuvent influencer vos résultats dans l’ensemble des projets Workspace :

* **Les données d’appartenance à l’audience sont exactes uniquement pour la journée précédente (« hier »)** : les données d’appartenance à l’audience contiendront toujours le dernier jeu de données d’instantané de profil généré par le service de profil unifié. Ce jeu de données de profil est un instantané quotidien et n’est précis que pour le jour précédent (« hier »), avec une régénération et un retraitement automatiques chaque nuit. Les dimensions Audience sont disponibles pour les rapports et les répartitions, et non pour reconstruire les états historiques de l’audience.

   * Exemple : quelle que soit la fenêtre temporelle de création de rapports choisie, l’audience devant faire l’objet d’un rapport CJA respectera toujours l’état d’appartenance à l’audience présent dans le dernier instantané de profil ingéré (« hier »).

      * Par exemple, l’élargissement de la période de création de rapports aux « 30 derniers jours » inclura davantage d’événements et donnera l’impression que la taille de l’audience change. Cependant, la composition du profil de l’audience correspondra toujours à l’instantané d’hier, quelle que soit la fenêtre temporelle choisie.

* **Les dimensions doivent avoir un événement correspondant à inclure** : les dimensions Analyse de l’audience ne peuvent être analysées que si des événements correspondants existent dans CJA. Si un comportement, un canal ou un moment du cycle de vie n’est pas représenté comme un événement dans la connexion CJA, il ne peut pas être analysé.

   * Exemple : une audience utilisée pour cibler des personnes avec une annonce publicitaire inclut beaucoup plus de personnes dans l’audience RTCDP que dans l’audience CJA. En effet, l’audience CJA est limitée aux personnes qui ont eu un événement dans CJA pendant la période de rapport.

* **La résolution d’identité repose uniquement sur un espace de noms unique** : la résolution d’identité dépend entièrement de l’espace de noms d’identité sélectionné dans le cadre de la configuration de l’analyse de l’audience. L’analyse sera limitée audit espace de noms d’identité, et les événements qui s’y trouvent ne seront pas disponibles pour les rapports d’analyse d’audience.

   * Exemple : pour un jeu de données d’événement assemblé qui combine CRM et ECID et pour lequel la configuration Analyse de l’audience utilise l’identifiant CRM, seules les lignes contenant un identifiant CRM seront reconnues comme faisant partie de l’audience à signaler dans CJA. Par conséquent, la taille de l’audience résultante peut être plus petite que prévu.

## Exemples de cas d’utilisation

### Cas d’utilisation 1

Comprenez comment une audience spécifique se comporte dans un canal donné (par exemple, le web ou l’application) pour répondre à des questions telles que :

* _« Que font les membres des prospects à forte valeur ajoutée sur le site en ce moment (pages, fonctionnalités, entonnoirs) ? »_

* _« Quelles campagnes et quel contenu sur-indexent cette audience par rapport à tous les autres ? »_

#### Flux de configuration

1. Configurez l’analyse de l’audience dans CJA pour un espace de noms d’identité unique (par exemple, ECID ou CRM_ID) et une vue de données web.

   * Les données d’appartenance à l’audience seront ainsi automatiquement ingérées dans la connexion choisie via l’exportation quotidienne d’instantanés de profil

   * Il est recommandé de sélectionner l’espace de noms d’identité qui, selon vous, a la plus couverture dans votre jeu de données d’événement

1. Créez vos projets Workspace pour :

   * Ventilez le nom de l’audience par page, produit, campagne, appareil, etc.

   * Comparez l’audience à une non-audience (ou à une autre audience) sur des mesures telles que les sessions, le taux de conversion, le chiffre d’affaires par personne.

1. Utilisez les informations générées pour affiner les stratégies d’optimisation des canaux (par exemple, les règles de ciblage, le réglage du contenu ou des offres).

#### Considérations relatives à la résolution des identités

| Cas d’utilisation | Question commerciale principale | Prise en compte de la résolution d’identité | Organisations à authentification élevée ou à espace de noms unique (événements dont l’ID de personne est déjà inférieur à 1, par exemple connexion /CRM) | Organisations fragmentées / à plusieurs espaces de noms (événements sous ECID + CRM + autres). |
|---------|----------|---------|---------|---------|
| Exploration approfondie du comportement de l’audience à l’état actuel | _« Que fait l’audience X dans le canal Y en ce moment ? » (pages, entonnoirs, contenu, offres)_ | Les événements et les profils doivent partager un espace de noms d’identité cohérent dans la configuration de connexion et d’analyse d’audience CJA pour une couverture optimale. | La plupart des activités sont déjà liées à un identifiant de connexion/CRM, de sorte que les audiences d’AEP se rejoignent proprement aux données comportementales dans CJA. <p>Vous obtenez une vue claire de ce que chaque audience fait dans un canal donné avec un minimum d’écarts de rapports attendus.</p> | Même lorsqu’il est joint à un jeu de données assemblé, le compte rendu des performances est toujours limité à l’espace de noms d’identité unique choisi dans la configuration. <p>Si certains clients existent sous d’autres ID, leur comportement n’est pas inclus, ce qui peut entraîner une vue partielle pendant la création de rapports.</p> |

### Cas d’utilisation 2

Aidez les professionnels du marketing ou les concepteurs de parcours à comprendre quelles audiences se chevauchent, afin qu’ils puissent dédupliquer les expériences et éviter les collisions d’offres entre les campagnes :

* _« À quel point y a-t-il aujourd’hui des chevauchements entre les membres du programme de fidélité, les personnes qui abandonnent leur panier et la forte propension à la perte de clientèle_ »

* _« Quelles audiences sont les plus susceptibles d’entrer en conflit avec des offres promotionnelles de grande valeur cette semaine ? »_

#### Flux de configuration

1. Configurez l’analyse de l’audience dans CJA pour un espace de noms d’identité unique aligné sur l’activation RTCDP/AJO (par exemple, CRM_ID si les parcours sont basés sur les personnes).

   * Les données d’appartenance à l’audience seront ainsi automatiquement ingérées dans la connexion choisie par le biais d’une exportation quotidienne d’instantanés de profil.

   * Vous pouvez l’utiliser pour enrichir une vue de données existante qui alimente déjà les rapports d’engagement et de conversion clés.

1. Utilisez le modèle de présentation de l’analyse des audiences prêt à l’emploi et les visualisations de chevauchement :

   * Exécutez les intersections d’audience et les vues de sur/sous-indexation (par exemple, % des personnes ayant abandonné leur panier qui se trouvent également dans Loyalty Gold).

   * Les tranches se chevauchent par dimensions principales (par exemple, type d’appareil, intérêt du produit) pour comprendre où les conflits sont les plus importants.

1. Utilisez les informations pour affiner les aspects critiques, tels que :

   * Règles de conflit d’offres ou règles d’action marketing dans RTCDP et AJO.

   * Amélioration de l’audience (par exemple, en durcissant les définitions de cible lorsque le chevauchement est trop élevé).

#### Considérations relatives à la résolution des identités

| Cas d’utilisation | Question commerciale principale | Prise en compte de la résolution d’identité | Organisations à authentification élevée ou à espace de noms unique (événements dont l’ID de personne est déjà inférieur à 1, par exemple connexion /CRM) | Organisations fragmentées / à plusieurs espaces de noms (événements sous ECID + CRM + autres). |
|---------|----------|---------|---------|---------|
| Détection des chevauchements d’audiences et des collisions | _« Quelles audiences se chevauchent aujourd’hui pour éviter les collisions d’offres ? »_ | Le chevauchement est calculé uniquement pour les audiences utilisant le même ID de personne et ayant la même activité dans la connexion CJA. | Comme la plupart des activités sont déjà liées à un seul identifiant de connexion/CRM, cela devrait fournir un mappage de chevauchement fiable entre les audiences. <p>Les graphiques de chevauchement donnent une image fiable des audiences en conflit et des endroits où appliquer des suppressions ou des règles de priorité.</p> | Si des parties du parcours sont associées à d’autres identifiants (navigation anonyme uniquement avec ECID, identifiants de centre d’appel, par exemple), ces événements n’apparaîtront pas dans l’analyse de chevauchement. <p>Des personnes peuvent toujours exister dans plusieurs espaces de noms.</p><p>Le chevauchement sera basé sur l’espace de noms d’identité inclus dans la configuration. Si certains profils se répartissent toujours entre les identifiants, le chevauchement peut sous-signaler les collisions vraies.</p> |

### Cas d’utilisation 3

Comprenez le comportement des clients qui ont récemment quitté une audience clé et ce qu’ils ont fait autour de cette sortie, pour répondre à des questions telles que :

* _« Qui vient de quitter un public clé, et qu&#39;ont-ils fait pour sortir ? »_

* _« Que s’est-il passé juste avant de quitter ? (erreurs, faible engagement, modifications de prix). »_

#### Flux de configuration

1. Configurez l’analyse de l’audience dans CJA pour un espace de noms d’identité unique (par exemple, CRM_ID ou identifiant de connexion) et les vues de données pertinentes (web, application, CRM, etc.).

   * Les données d’appartenance à l’audience sont ainsi automatiquement ingérées dans la connexion choisie par le biais d’une exportation quotidienne d’instantanés de profil.

   * Il est recommandé de sélectionner l’espace de noms d’identité qui, selon vous, a la plus couverture dans votre jeu de données d’événement.

1. Dans le modèle Analyse de l’audience / Présentation de l’audience (fixe à _hier_), utilisez :

   * Membres actuels : qui est toujours dans l’audience

   * Audience sortie : qui est parti hier

1. Créez vos projets Workspace pour :

   * Filtrez les profils qui ont quitté Audience X hier, puis regardez :

      * Leur comportement menant à la sortie (dernières sessions, erreurs, exposition aux prix/offres, mix de canaux).

      * Leur comportement après la sortie (ont-ils changé de produit, rétrogradé, sont-ils devenus inactifs ?)

   * Répartissez cette cohorte sortante par région, appareil, tenure, niveau de valeur pour trouver des poches à fort impact.

1. Utilisez les informations pour les mises à jour de parcours et les configurations d’audiences de reconquête dans RTCDP ou AJO.

#### Considérations relatives à la résolution des identités

| Cas d’utilisation | Question commerciale principale | Prise en compte de la résolution d’identité | Organisations à authentification élevée ou à espace de noms unique (événements dont l’ID de personne est déjà inférieur à 1, par exemple connexion /CRM) | Organisations fragmentées / à plusieurs espaces de noms (événements sous ECID + CRM + autres). |
|---------|----------|---------|---------|---------|
| Audiences quittées - analyse de l’attrition | _« Qui vient de quitter un public clé ? »_ <p>_« Qu&#39;ont-ils fait à la sortie ? »_</p> | La sortie de l’audience est suivie à l’ID de personne utilisé pour la configuration de la connexion et de l’audience. | Les sorties mesurées sur un identifiant de connexion/CRM stable tendent à refléter un véritable changement de comportement. <p>Lorsqu’une personne laisse une audience sur cet identifiant, cela signifie généralement un changement réel (perte de clientèle, rétrogradation, inactivité).</p><p>Vous pouvez analyser leur comportement récent pour affiner les parcours et reconquérir les offres en toute confiance.</p> | Les sorties ne sont visibles que lorsque les profils et les événements partagent l’identifiant configuré ; elles nécessitent donc une interprétation attentive.<p>Utilisez les cohortes sorties comme un indice ou un signal fort, mais il est recommandé de vérifier avec d’autres points de données avant de prendre des décisions critiques.</p> |
