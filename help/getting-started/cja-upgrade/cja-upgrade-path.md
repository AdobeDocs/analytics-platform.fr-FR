---
title: Choisir votre chemin de mise à niveau de Customer Journey Analytics
description: Découvrez les avantages et les inconvénients des chemins de mise à niveau possibles lors de la mise à niveau vers Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '2981'
ht-degree: 98%

---

# Étape 2 : choisir votre chemin de mise à niveau

+++Développez cette section pour voir la place des informations de cette page dans un processus de mise à niveau plus large. Vérifiez que toutes les étapes de mise à niveau précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de mise à niveau précédentes.

Les informations de cette page couvrent l’Étape 2 de la mise à niveau, comme indiqué dans le tableau ci-dessous :

| Tâche de mise à niveau | Détails |
|---------|----------|
| **Étape 1 : [commencer avec la mise à niveau](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Découvrez les avantages de la mise à niveau vers Customer Journey Analytics et le processus de mise à niveau de base. |
| <span class="preview">**Étape 2 : choisir le chemin de mise à niveau**</span> | <span class="preview">Différentes méthodes sont disponibles pour la mise à niveau vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre organisation, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre organisation.</span> |
| **Étape 3 : [envoyer les données à Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de mise à niveau que vous avez choisi à l’Étape 2. |
| **Étape 4 : [conserver les données historiques](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La plupart des organisations doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour cela. |
| **Étape 5 : [exécuter des tâches d’implémentation supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de mise à niveau, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux mises à niveau à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches comprennent les éléments suivants :</p><ul><li>Importer d’autres données dans Experience Platform</li><li>Créer des connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Créer des vues de données</li><li>Porter l’utilisation de l’API de création de rapports</li><li>Prendre en compte les flux de données et Data Warehouse</li><li>Migrer des projets et des composants</li><li>Planifier l’intégration des utilisateurs et utilisatrices</li></ul> <p>Pour plus d’informations, voir [Commencer avec Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Les informations de cette page sont progressivement remplacées par des informations de mise à niveau plus complètes suivantes : <ul><li>**Étapes recommandées pour la mise à niveau**<p>Pour plus d’informations, consultez [Chemin recommandé pour la mise à niveau à partir d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guide de mise à niveau de Customer Journey Analytics**<p>Un nouveau guide est disponible pour générer dynamiquement des étapes de mise à niveau adaptées à votre entreprise et à vos circonstances.</p><p>Pour accéder au guide à partir de Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Espace de travail]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.</p></li></ul>


Après avoir décidé de mettre à niveau vers Customer Journey Analytics, vous devez déterminer le chemin de mise à niveau optimal pour votre organisation.

Le chemin que vous choisissez pour mettre à niveau d’Adobe Analytics vers Customer Journey Analytics dépend des facteurs suivants :

* Votre implémentation Adobe Analytics existante

* Vos objectifs pour l’avenir

Utilisez les informations de cette page pour déterminer le chemin de mise à niveau de Customer Journey Analytics qui correspond le mieux à l’implémentation actuelle et aux objectifs futurs de votre organisation.

Pour déterminer le chemin de mise à niveau optimal pour votre organisation, les sections suivantes doivent être lues de manière séquentielle :

1. Tout d’abord, [comprendre les chemins de mise à niveau disponibles](#understand-upgrade-paths).

1. Ensuite, [déterminer les chemins de mise à niveau disponibles pour vous](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Enfin, [évaluer les avantages et les inconvénients de chaque chemin de mise à niveau](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you).

## Comprendre les chemins de mise à niveau

Plusieurs chemins sont disponibles pour la mise à niveau d’Adobe Analytics vers Customer Journey Analytics.

En règle générale, chaque chemin de mise à niveau varie en fonction du niveau d’effort requis pour exécuter la mise à niveau, ainsi que de la viabilité à long terme atteinte une fois la mise à niveau terminée.

Le tableau suivant répertorie chaque chemin de mise à niveau, son niveau d’effort et sa viabilité à long terme :

| Chemin de mise à niveau | Niveau d’effort | Viabilité à long terme |
|---------|----------|---------|
| **Nouvelle implémentation du SDK web Experience Platform avec le connecteur source Analytics**</br> Vous pouvez commencer à utiliser Customer Journey Analytics en effectuant une nouvelle implémentation du SDK web Experience Platform. Vous pouvez ainsi commencer à envoyer des données à Adobe Experience Platform Edge Network et Customer Journey Analytics. En outre, vous utilisez le connecteur source Analytics pour importer des données historiques dans Customer Journey Analytics.<p>Pour les entreprises qui n’utilisent pas encore le SDK web, ce chemin de mise à niveau est peut-être le plus simple pour envoyer des données vers Edge Network, car il nécessite le moins d’étapes. Cependant, étant donné que tout le travail est effectué en amont (comme la création du schéma XDM), il nécessite un effort initial plus important.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Créez un schéma XDM pour votre organisation.</li><li>Implémentez le SDK web.</li><li>Envoyez des données à Platform.</li><li>Configurez un connecteur source Adobe Analytics.</br>Le connecteur source Analytics est utilisé pour importer les données Adobe Analytics historiques dans Customer Journey Analytics.<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | Élevé | Élevé |
| **Nouvelle implémentation du SDK web Experience Platform**</br> Vous pouvez commencer à utiliser Customer Journey Analytics en effectuant une nouvelle implémentation du SDK web Experience Platform. Vous pouvez ainsi commencer à envoyer des données à Adobe Experience Platform Edge Network et Customer Journey Analytics. <p>Pour les entreprises qui n’utilisent pas encore le SDK web, ce chemin de mise à niveau est peut-être le plus simple pour envoyer des données vers Edge Network, car il nécessite le moins d’étapes. Cependant, étant donné que tout le travail est effectué en amont (comme la création du schéma XDM), il nécessite un effort initial plus important.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Créez un schéma XDM pour votre organisation.</li><li>Implémentez le SDK web.</li><li>Envoyez des données à Platform.</li></ol> | Élevé | Élevé |
| **Migration de votre implémentation Adobe Analytics pour utiliser le SDK web**</br> Si votre implémentation Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez la migrer pour utiliser le SDK web Adobe Experience Platform afin de commencer à envoyer des données à Edge Network et Adobe Analytics, avant de les envoyer à Customer Journey Analytics.<p>Pour les entreprises qui n’utilisent pas encore le SDK web, il s’agit de la méthode la plus simple et la plus fluide pour envoyer des données vers Edge Network. Elle nécessite davantage d’étapes, mais offre une transition plus méthodique d’Adobe Analytics vers Customer Journey Analytics, avec des jalons plus tangibles.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Déplacez votre implémentation Adobe Analytics existante vers le SDK web et vérifiez que tout fonctionne dans Adobe Analytics.</li><li>Créez un schéma XDM pour votre entreprise lorsque vous en avez le temps.</li><li>Utilisez le mappage de train de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li><li>Envoyez des données à Platform.</li></ol> | Modéré | Élevé |
| **Configurer votre implémentation existante du SDK web Adobe Analytics**</br> Si votre implémentation Adobe Analytics utilise déjà le SDK web Adobe Experience Platform, vous pouvez commencer à envoyer des données à Platform en configurant un train de données. Ou, si vous envoyez déjà des données à Platform, vous devez simplement créer une connexion entre les jeux de données Platform et Customer Journey Analytics.<p>Avant d’envoyer des données à Platform pour les utiliser dans Customer Journey Analytics, pensez à mettre à jour votre schéma Adobe Analytics en fonction des besoins spécifiques de votre entreprise et de toute autre application Platform que vous utilisez.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Commencez à envoyer des données à Platform.<p>Si vous envoyez déjà des données à Platform avec votre implémentation Adobe Analytics, cette étape n’est pas obligatoire. Il vous suffit de créer une connexion entre les jeux de données Platform et Customer Journey Analytics, comme décrit plus loin dans ce processus.</p></li><li>(Facultatif) Créez un schéma XDM pour votre entreprise lorsque vous en avez le temps.</li><li>(Le cas échéant) Si vous avez créé un schéma XDM, utilisez le mappage de train de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li></ol> | Faible | Élevé |
| **Utiliser le connecteur source Analytics**</br> Si votre implémentation Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez commencer à envoyer des données vers une vue de données dans Customer Journey Analytics.<p>Il s’agit de la méthode la plus simple pour obtenir des données pour Customer Journey Analytics, mais elle est la méthode la moins viable à long terme.</p> <p>**Note :** ce chemin de mise à niveau peut être utilisé indépendamment. Cependant, pour de meilleurs résultats, nous vous recommandons d’utiliser ce chemin de mise à niveau conjointement avec une nouvelle implémentation du SDK web Experience Platform. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | Faible | Faible |

{style="table-layout:auto"}

Utilisez le diagramme suivant pour vous aider à visualiser où chaque chemin de mise à niveau se situe sur le spectre en termes de niveau d’effort et de viabilité à long terme :

![Chemins de mise à niveau CJA](assets/cja-upgrade-path-chart.png)

## Évaluer les chemins de mise à niveau disponibles en fonction de votre implémentation Adobe Analytics actuelle

Tous les chemins de mise à niveau ne sont pas disponibles pour chaque type d’implémentation Adobe Analytics.

Utilisez les informations ci-dessous pour vous aider à déterminer le chemin de mise à niveau le plus approprié pour votre organisation.

Contactez votre représentant ou représentante Adobe si vous avez besoin d’assistance ou de conseils plus précis.

| Implémentation existante dʼAdobe Analytics | Chemins de mise à niveau disponibles |
|---------|----------|
| AppMeasurement | <ul><li>Nouvelle implémentation du SDK web Experience Platform</li><li>Migrer Adobe Analytics vers le SDK web</li><li>Connecteur source Analytics</li><li>(Recommandé) Nouvelle implémentation du SDK web Experience Platform avec le connecteur source Analytics</li></ul> |
| Extension Adobe Analytics | <ul><li>Nouvelle implémentation du SDK web Experience Platform</li><li>Migrer Adobe Analytics vers le SDK web</li><li>Connecteur source Analytics</li><li>(Recommandé) Nouvelle implémentation du SDK web Experience Platform avec le connecteur source Analytics</li></ul> |
| SDK web | <ul><li>Configurer l’implémentation du SDK web Adobe Analytics pour envoyer des données à Platform</li><li>(Recommandé) Nouvelle implémentation du SDK web Experience Platform avec le connecteur source Analytics</li></ul> |

{style="table-layout:auto"}

## Peser les avantages et les inconvénients des chemins de mise à niveau disponibles pour vous

Les avantages et les inconvénients d’un chemin de mise à niveau donné varient en fonction de votre implémentation Adobe Analytics existante.

Avant d’utiliser les informations ci-dessous pour déterminer quel chemin de mise à niveau vous convient, passez en revue les informations de la section [Comprendre les chemins de mise à niveau](#understand-migration-methods) si vous ne l’avez pas déjà fait.

>[!NOTE]
>
>Bien que chacun des chemins de mise à niveau décrits dans les sections suivantes puisse être utilisé indépendamment, Adobe recommande une approche de mise à niveau en deux phases lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics, quelle que soit votre implémentation Adobe Analytics actuelle : **le connecteur source Adobe Analytics** et une **nouvelle implémentation du SDK web Experience Platform**.
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### Pour les implémentations Adobe Analytics utilisant : AppMeasurement et l’extension Adobe Analytics

Vous trouverez ci-dessous les chemins de mise à niveau disponibles pour les organisations qui ont implémenté Adobe Analytics avec AppMeasurement ou l’extension Adobe Analytics. Développez chaque section pour afficher les avantages et les inconvénients de chaque chemin de mise à niveau.

#### Chemins de mise à niveau

+++Nouvelle implémentation du SDK web Experience Platform

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul></li><li>**À l’épreuve du temps** : les futures mises à jour d’implémentation sont plus simples.</li></ul> | <ul><li>**Nécessite une nouvelle implémentation à partir de zéro** : l’obligation d’effectuer une nouvelle implémentation à partir de zéro suppose les inconvénients suivants : </li><ul><li>**Coûteux en temps** : il s’agit du chemin de mise à niveau le plus coûteux en temps et le plus exigeant, car il nécessite de recommencer avec une nouvelle implémentation.</li><li>**Nécessite la recréation du schéma complet dans XDM** : pour pouvoir commencer à implémenter le SDK web, vous devez recréer le schéma complet dans XDM.</li><li>**Nécessite de recréer des règles et des éléments de données** : pour pouvoir commencer à implémenter le SDK web, vous devez recréer toutes les conditions de règle et tous les éléments de données de votre implémentation Adobe Analytics.</li></ul><li>**Ne prend pas en compte la conservation des données historiques :** Adobe recommande d’utiliser le connecteur source Analytics conjointement avec une nouvelle implémentation du SDK web Experience Platform afin de conserver les données historiques après la mise à niveau vers Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**Ne tient pas compte de la comparaison des données de votre implémentation d’origine avec celles de votre nouvelle implémentation :** Adobe recommande d’utiliser le connecteur source Analytics conjointement avec une nouvelle implémentation du SDK web Experience Platform afin de comparer les données après la mise à niveau vers Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++Migration d’Adobe Analytics vers Experience Platform Web SDK

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation sans affecter vos rapports Adobe Analytics existants.</li><li>**Permet de créer ultérieurement un schéma XDM pour votre organisation** : vous pouvez migrer votre implémentation Adobe Analytics existante pour utiliser le SDK web et vérifier que tout fonctionne dans Adobe Analytics, puis créer le schéma XDM. Cette flexibilité permet une mise à niveau vers Customer Journey Analytics plus méthodique et réfléchie.</li></ul> | <ul><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet de données soit une entrée dans l’outil de mappage de train de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li><li>**Dette technique** : cette approche utilisant une forme modifiée de votre implémentation existante, il peut être plus difficile de suivre la logique d’implémentation et d’effectuer des modifications ultérieurement, le cas échéant. </li></ul> |

{style="table-layout:auto"}

+++

+++Utiliser le connecteur source Analytics

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>Chemin de mise à niveau le moins coûteux en temps et le moins exigeant. <p>Les données sont rapidement transférées vers Customer Journey Analytics avec un investissement minimal.</p></li></ul> | <ul><li>**Les données ne sont pas envoyées à Edge Network** : <p>Les inconvénients sont les suivants :</p><ul><li>Niveau le plus élevé de [latence](/help/technotes/guardrails.md#latencies) dans les rapports de tous les chemins de mise à niveau ; non optimisé pour les cas d’utilisation de personnalisation en temps réel.</li><li>Les données ne peuvent pas être partagées avec d’autres applications Adobe Experience Platform ; elles sont limitées à Customer Journey Analytics uniquement.</li><li>Dépend de la nomenclature Adobe Analytics (prop, eVar, événement, etc.).</li></ul><li>**Difficulté à migrer vers le SDK web à l’avenir** : à terme, vous souhaiterez probablement accéder aux avantages offerts par le SDK web d’Experience Platform. Pour commencer à utiliser le SDK web Experience Platform, vous devez effectuer une nouvelle implémentation.</li><li>**Utilise le groupe de champs Événement d’expérience Analytics dans votre schéma** : ce groupe de champs ajoute de nombreux événements Adobe Analytics inutiles dans votre schéma de Customer Journey Analytics.  Cela peut générer un schéma plus complexe et encombré que ce qui est nécessaire à Customer Journey Analytics.</li></ul><p>En raison de ces inconvénients, Adobe recommande d’utiliser le connecteur source Analytics conjointement avec une nouvelle implémentation du SDK web Experience Platform. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### Pour les implémentations d’Adobe Analytics à l’aide de : SDK web

Le chemin de mise à niveau suivant est disponible pour les organisations qui ont implémenté Adobe Analytics avec le SDK web Experience Platform.

Lors du choix de ce chemin de mise à niveau, vous devez également choisir votre schéma.

#### Chemin de mise à niveau

+++Configurer l’implémentation du SDK web Adobe Analytics pour envoyer des données à Platform

| Avantages | Inconvénients |
|----------|---------|
| Il s’agit du chemin de mise à niveau préféré si votre implémentation Adobe Analytics utilise déjà le SDK web.<ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation sans affecter vos rapports Adobe Analytics existants.</li><li>**Permet d’utiliser un schéma XDM** : vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou de créer un schéma XDM et de mapper des champs dans l’objet de données à votre schéma XDM. Les [schémas XDM](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home#xdm-schemas) sont flexibles et permettent de définir les champs dont vous avez besoin, et uniquement ceux qui sont pertinents pour vous. <p>Voir « Utiliser votre propre schéma XDM » ci-dessous pour plus d’informations sur les avantages de l’utilisation de votre propre schéma XDM.</p></li><li>**Conserve les règles et les éléments de données** : bien que de nouvelles actions de règle soient nécessaires, vous pouvez réutiliser vos éléments de données et conditions de règle existants avec des modifications minimales.</li><li>**À l’épreuve du temps** : si vous choisissez d’utiliser votre propre schéma XDM, les futures mises à jour d’implémentation sont plus simples.</li></ul> | Aucun |

{style="table-layout:auto"}

+++

#### Choisir votre schéma

Si vous choisissez le chemin de mise à niveau qui vous permet de configurer l’implémentation du SDK web d’Adobe Analytics pour envoyer des données à Customer Journey Analytics, vous pouvez choisir le schéma que vous souhaitez utiliser.

Vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou de le mettre à jour vers votre propre schéma XDM, afin de mieux vous aligner sur les besoins de votre entreprise lorsque vous commencez à utiliser d’autres services Platform.

+++Utilisation du schéma Adobe Analytics avec l’implémentation d’Adobe Analytics Web SDK

| Avantages | Inconvénients |
|----------|---------|
| <p>L’utilisation du schéma Adobe Analytics offre les avantages suivants :</p><ul><li>Facilité de mise à niveau<p>Si vous envoyez déjà des données à Adobe Analytics avec le SDK web d’Adobe Experience Platform, vous pouvez ajouter un service supplémentaire à votre flux de données pour envoyer des données à Adobe Experience Platform (qui peuvent ensuite être utilisées dans votre configuration de Customer Journey Analytics).</p></li></ul> | <p>L’utilisation du schéma Adobe Analytics présente les inconvénients suivants :</p><ul><li>Bien que l’utilisation du schéma Adobe Analytics ne vous limite pas en termes d’utilisation avec d’autres applications Platform, elle génère un schéma plus complexe que nécessaire. En effet, le schéma Adobe Analytics contient de nombreux objets spécifiques à Adobe Analytics qui ne seront probablement pas utilisés par votre organisation.<p>Lorsque des modifications du schéma sont requises, vous devez passer en revue des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></li></ul> |

+++

+++Utiliser votre propre schéma XDM avec l’implémentation Adobe Analytics Web SDK

| Avantages | Inconvénients |
|----------|---------|
| <ul><p>La mise à jour de votre propre schéma XDM offre les avantages suivants :</p><ul><li>Schéma rationalisé adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.</li><p>Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></ul> | <p>La mise à jour de votre propre schéma XDM présente les inconvénients suivants :</p><ul><li>La mise à jour de votre schéma est un processus coûteux en temps, nécessaire avant de commencer à envoyer des données à Platform.</li></ul> |

+++

## Ensuite, envoyez les données à Adobe Experience Platform.

Après avoir utilisé les informations ci-dessus pour choisir un chemin de mise à niveau, apprenez à [envoyer des données à Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) selon le chemin de mise à niveau que vous avez choisi.
