---
title: Choix de la méthode de migration des Customer Journey Analytics
description: Découvrez les avantages et les inconvénients des méthodes de migration possibles lors de la migration vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 5%

---

# Étape 2 : Choix de la méthode de migration des Customer Journey Analytics

+++Les informations de cette page font partie d’un processus de migration plus vaste. Développez cette section pour voir où ces informations s’inscrivent dans le processus de migration. </br></br>Vous devez effectuer toutes les étapes de migration précédentes avant de continuer avec les informations de cette page.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page portent sur l’étape 2, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| <span class="preview">**Étape 2 : [Choisissez la méthode de migration](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise.</span> |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction de la méthode de migration choisie à l’étape 1. |
| **Étape 4 : [Planification du mappage des données au schéma XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont utilisées dans Adobe Experience Platform pour décrire la structure des données de manière cohérente et réutilisable. En définissant les données de manière cohérente sur l’ensemble des systèmes, il est plus simple de leur donner du sens et donc d’en tirer profit.<p>La plupart des méthodes de migration exigent que vous créiez un nouveau schéma XDM ou que vous mappiez votre schéma Adobe Analytics existant avec XDM à l’aide du mappage de flux de données.</p> |
| **Étape 5 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 6 : [Planification de l’intégration des utilisateurs](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Donnez à vos utilisateurs suffisamment de temps (3 à 6 mois) pour se familiariser avec les différences clés d’Analysis Workspace dans Customer Journey Analytics. |
| **Étape 7 : [Port de l’utilisation de l’API de création de rapports](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API de création de rapports du Customer Journey Analytics est au même format, mais utilise un point de terminaison différent. Transférez l’utilisation de l’API de création de rapports d’Adobe Analytics vers l’API de création de rapports du Customer Journey Analytics. |
| **Étape 8 : [Remplacement des flux de données et du Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Choisissez comment utiliser les options d’exportation disponibles dans Customer Journey Analytics pour remplacer les flux de données et les fonctionnalités de Data Warehouse que vous utilisiez dans Adobe Analytics. |
| **Étape 9 : [Migration de projets et de composants](/help/getting-started/cja-migration/cja-migration-projects.md)** | La zone de migration Composant d’Adobe Analytics vous permet de migrer les projets et leurs composants associés d’Adobe Analytics vers Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Après avoir décidé de migrer vers Customer Journey Analytics, vous devez déterminer la méthode de migration optimale pour votre organisation.

La méthode que vous choisissez pour migrer d’Adobe Analytics vers Customer Journey Analytics dépend des facteurs suivants :

* Votre mise en oeuvre Adobe Analytics existante

* Vos objectifs pour le futur

Utilisez les sections suivantes pour déterminer la méthode de migration de Customer Journey Analytics qui correspond le mieux à la mise en oeuvre actuelle et aux objectifs futurs de votre entreprise :

## Présentation des méthodes de migration

Il existe différentes méthodes de migration pour migrer d’Adobe Analytics vers Customer Journey Analytics.

En règle générale, chaque méthode de migration diffère dans le niveau d’effort requis pour exécuter la migration, ainsi que dans la viabilité à long terme atteinte une fois la migration terminée.

Le tableau suivant répertorie chaque méthode de migration, son niveau d’effort et sa viabilité à long terme :

| Méthode de migration | Niveau d&#39;effort | Viabilité à long terme |
|---------|----------|---------|
| **Nouvelle mise en oeuvre du SDK Web**</br> Vous pouvez effectuer une nouvelle mise en oeuvre du SDK Web Adobe Experience Platform pour commencer à envoyer des données à Adobe Experience Platform Edge Network <!-- what is the correct branding -->. <p>Pour les entreprises qui ne disposent pas encore du SDK Web, cette méthode de migration est peut-être la plus simple à obtenir des données à l’Edge Network (nécessitant le moins d’étapes), mais tout le travail est déjà effectué, comme la création du schéma XDM.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Création d’un schéma XDM pour votre organisation</li><li>Mise en oeuvre du SDK Web</li><li>Envoyer des données à Platform</li></ol> | Élevé | Élevé |
| **Migration de votre mise en oeuvre Adobe Analytics pour utiliser le SDK Web**</br> Si votre mise en oeuvre Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez la migrer pour utiliser le SDK Web Adobe Experience Platform afin de commencer à envoyer les données à l’Edge Network avant de les envoyer à l’Customer Journey Analytics. <!-- what else? --><p>Il s’agit de la méthode la plus simple et la plus fluide pour obtenir des données vers l’Edge Network ; elle nécessite davantage d’étapes, mais offre une transition plus méthodique avec des jalons plus tangibles.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Déplacez votre mise en oeuvre Adobe Analytics existante vers le SDK Web et validez que tout fonctionne là-bas.</li><li>Créez un schéma XDM pour votre entreprise à mesure que vous en aurez le temps.</li><li>Utilisez le mappage de flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li><li>Envoyer des données à Platform</li></ol> | Modérer | Élevé |
| **Configuration de votre mise en oeuvre SDK Web Adobe Analytics existante pour envoyer des données à Customer Journey Analytics**</br> Si votre mise en oeuvre Adobe Analytics utilise déjà le SDK Web, vous pouvez commencer à envoyer des données à Customer Journey Analytics.<p>Avant d’envoyer des données à Customer Journey Analytics, pensez à mettre à jour votre schéma Adobe Analytics en fonction des besoins spécifiques de votre entreprise et de toute autre application Platform que vous utiliserez.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Commencez à envoyer des données à Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Facultatif) Créez un schéma XDM pour votre entreprise à mesure que vous en aurez le temps.</li><li>Utilisez le mappage de flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li></ol> | Faible | Élevé |
| **Connecteur source Analytics**</br> Si votre mise en oeuvre Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez commencer à envoyer des données vers une vue de données dans Customer Journey Analytics.<p>Il s’agit de la méthode la plus simple pour obtenir des données vers Customer Journey Analytics, mais elle est la méthode la moins viable à long terme.</p> | Faible | Faible |

{style="table-layout:auto"}

Utilisez le diagramme suivant pour visualiser l’emplacement de chaque méthode de migration sur le spectre en termes de niveau d’effort, ainsi que la viabilité à long terme de chacune d’elles :

![Méthodes de migration cja](assets/cja-migration-methods.png)

## Évaluer les méthodes de migration disponibles en fonction de votre implémentation Adobe Analytics actuelle

Toutes les méthodes de migration ne sont pas disponibles pour chaque type d’implémentation Adobe Analytics.

Utilisez les informations ci-dessous comme instructions générales pour vous aider à comprendre la méthode de migration la plus appropriée pour votre entreprise.

Contactez votre représentant d’Adobe si vous avez besoin de conseils, de conseils ou d’assistance plus précis.

| Implémentation d’Adobe Analytics | Méthodes de migration disponibles |
|---------|----------|
| AppMeasurement | <ul><li>Nouvelle mise en oeuvre du SDK Web</li><li>Migration d’Adobe Analytics vers le SDK Web</li><li>Connecteur source Analytics</li></ul> |
| Extension Adobe Analytics | <ul><li>Nouvelle mise en oeuvre du SDK Web</li><li>Migration d’Adobe Analytics vers le SDK Web</li><li>Connecteur source Analytics</li></ul> |
| SDK Web | <ul><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Peser les avantages et les inconvénients des méthodes de migration à votre disposition

Les avantages et les inconvénients d’une méthode de migration donnée varient en fonction de votre mise en oeuvre Adobe Analytics existante.

Avant d’utiliser les informations ci-dessous pour déterminer la méthode de migration qui vous convient, passez en revue les informations de la section [Présentation des méthodes de migration](#understand-migration-methods) si vous ne l&#39;avez pas déjà fait.

### AppMeasurement et extension Adobe Analytics

Le tableau suivant montre les méthodes de migration disponibles pour les organisations qui ont implémenté Adobe Analytics avec AppMeasurement ou l’extension Adobe Analytics :

| Méthode de migration | Avantages | Inconvénients |
|---------|----------|---------|
| **Nouvelle mise en oeuvre du SDK Web** | <ul><li>Utilise un schéma XDM, un schéma flexible pour définir tous les champs dont vous avez besoin.</li><li>Ne dépend pas de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li><li>Pas de problème de limite de caractères (100 caractères pour les props)</li><li>Rapports et disponibilité des données très performants car Adobe Experience Platform est conçu pour fonctionner [cas pratiques de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>À l’épreuve du temps (recevra toutes les dernières fonctionnalités)</li><li>Consolidation des balises pour la collecte de données Adobe Experience Cloud entre d’autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>[Identifiants d’appareils propriétaires](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) pour une meilleure précision de l’identification des visiteurs</li></ul> | <ul><li>Méthode de migration la plus chronophage et la plus exigeante<p>Doit recréer le schéma complet dans XDM avant de pouvoir commencer à implémenter le SDK Web</p></li></ul> |
| **Migration d’Adobe Analytics vers le SDK Web** | <ul><li>Conserve les règles et les éléments de données déjà configurés dans votre mise en oeuvre Adobe Analytics.</li><li>Permet de passer au SDK Web sans affecter les rapports Adobe Analytics existants.</li><li>Permet de créer un schéma XDM pour votre entreprise ultérieurement.</br>Ne nécessite pas le groupe Champ d’événement d’expérience Adobe Analytics dans Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Ne dépend pas de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li><li>Pas de problème de limite de caractères (100 caractères pour les props)</li><li>Rapports et disponibilité des données très performants car Adobe Experience Platform est conçu pour fonctionner [cas pratiques de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>À l’épreuve du temps (recevra toutes les dernières fonctionnalités)</li><li>Consolidation des balises pour la collecte de données Adobe Experience Cloud entre d’autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>[Identifiants d’appareils propriétaires](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) pour une meilleure précision de l’identification des visiteurs</li></ul> | <ul><li>Doit se conformer à un schéma XDM à un moment donné, à l’aide du mappage de flux de données.</li><li>Entraîne une certaine dette technique. Par exemple, le code d’AppMeasurement hérité ou d’extension Analytics peut rester. </li></ul> |
| **Connecteur source Analytics** | <ul><li>Méthode de migration la moins longue et la plus exigeante. <p>Les données sont rapidement transférées vers Customer Journey Analytics avec un investissement minimal.</p></li></ul> | <ul><li>Les données ne sont pas envoyées à l’Edge Network et ne peuvent pas être partagées avec d’autres applications Adobe Experience Platform ; elles sont limitées au Customer Journey Analytics uniquement.<li>Difficulté à passer au SDK Web à l’avenir</li><li>Utilise le groupe de champs Événement d’expérience Analytics dans votre schéma.</br>Ce groupe de champs ajoute de nombreux événements Adobe Analytics inutiles dans votre schéma de Customer Journey Analytics.  Cela peut entraîner un schéma plus complexe et encombré que ce qui est nécessaire à Customer Journey Analytics.</li><li>Niveau le plus élevé de [latence](/help/admin/guardrails.md#latencies) toutes les méthodes d’implémentation ;</li></ul> |

{style="table-layout:auto"}

### SDK Web

Le tableau suivant montre les méthodes de migration disponibles pour les organisations qui ont implémenté Adobe Analytics avec le SDK Web :

| Méthode de migration | Avantages | Inconvénients |
|---------|----------|---------|
| **Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Customer Journey Analytics** | Il s’agit de la méthode de migration privilégiée si votre mise en oeuvre Adobe Analytics utilise déjà le SDK Web. <p>Lorsque vous utilisez cette méthode d’implémentation, vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou vous pouvez effectuer une mise à jour vers le schéma XDM pour mieux vous aligner sur les besoins de votre entreprise lorsque vous commencez à utiliser d’autres applications Platform.</p><p>**Utilisation du schéma Adobe Analytics**</p><p>L’utilisation du schéma Adobe Analytics offre les avantages suivants :</p><ul><li>Facilité de migration<p>Si vous envoyez déjà des données à Adobe Analytics avec le SDK Web de Adobe Experience Platform, vous pouvez ajouter un service supplémentaire à votre flux de données pour envoyer des données à Adobe Experience Platform (qui peut ensuite être utilisé dans votre configuration de Customer Journey Analytics).</p></li></ul><p>L’utilisation du schéma Adobe Analytics présente les inconvénients suivants :</p><ul><li>Bien que l’utilisation du schéma Adobe Analytics ne vous limite pas en termes de la manière dont il peut être utilisé avec d’autres applications Platform, elle génère un schéma plus complexe qu’il ne pourrait l’être autrement. En effet, le schéma Adobe Analytics contient de nombreux objets spécifiques à Adobe Analytics qui ne seront probablement pas utilisés par votre organisation.<p>Lorsque des modifications du schéma sont requises, vous devez passer en revue des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></li></ul><p>**Utilisation du schéma XDM**</p><p>La mise à jour du schéma XDM offre les avantages suivants :</p><ul><li>Schéma rationalisé adapté aux besoins de votre entreprise et aux applications Platform spécifiques que vous utilisez.</li><p>Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></ul><p>La mise à jour du schéma XDM présente les inconvénients suivants :</p><ul><li>La mise à jour de votre schéma est un processus chronophage qui est nécessaire avant de commencer à envoyer des données à Customer Journey Analytics.</li></ul> | Aucun |

{style="table-layout:auto"}

## Ensuite, envoyez les données à Adobe Experience Platform.

Après avoir utilisé les informations ci-dessus pour choisir une méthode de migration, apprenez à [envoyer des données à Adobe Experience Platform ;](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) selon la méthode de migration choisie.