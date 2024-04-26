---
title: Choix du chemin de migration des Customer Journey Analytics
description: Découvrez les avantages et les inconvénients des chemins de migration possibles lors de la migration vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 0%

---

# Étape 2 : Choix de votre chemin de migration

+++Développez cette section pour voir où les informations de cette page s’inscrivent dans le processus de migration plus vaste. Vérifiez que toutes les étapes de migration précédentes sont terminées.

Avant de poursuivre cette section, assurez-vous d’avoir effectué toutes les tâches de migration précédentes.

Les informations de cette page couvrent l’étape 2 de la migration, comme indiqué dans le tableau ci-dessous :

| Tâche de migration | Détails |
|---------|----------|
| **Étape 1 : [Prise en main de la migration](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Découvrez les avantages de la migration vers Adobe Analytics et le processus de migration de base. |
| <span class="preview">**Etape 2 : sélection du chemin de migration**</span> | <span class="preview">Différentes méthodes sont disponibles pour la migration vers Customer Journey Analytics. Choisissez la méthode qui convient le mieux à votre entreprise, en fonction de l’environnement Adobe Analytics actuel et des objectifs à long terme de votre entreprise.</span> |
| **Étape 3 : [Envoi de données à Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Le processus d’envoi de données à Adobe Experience Platform varie en fonction du chemin de migration que vous avez choisi à l’étape 2. |
| **Étape 4 : [Conserver les données historiques](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La plupart des entreprises doivent conserver leurs données Adobe Analytics historiques pendant un certain temps. Différentes options sont disponibles pour ce faire. |
| **Étape 5 : [Exécution de tâches de mise en oeuvre supplémentaires](/help/getting-started/cja-getting-started.md)** | À ce stade du processus de migration, vous devez effectuer diverses tâches avant que votre environnement de Customer Journey Analytics ne soit prêt à l’emploi.<p>Ces tâches supplémentaires s’appliquent aux migrations à partir d’Adobe Analytics, ainsi qu’aux nouvelles implémentations de Customer Journey Analytics.</p><p>Ces tâches incluent :</p><ul><li>Importation d’autres données dans Experience Platform</li><li>Création de connexions entre les jeux de données Platform et Customer Journey Analytics</li><li>Création de vues de données</li><li>Portage de l’utilisation de l’API de création de rapports</li><li>Prise en compte des flux de données et du Data Warehouse</li><li>Migration de projets et de composants</li><li>Planification de l’intégration des utilisateurs</li></ul> <p>Pour plus d’informations, voir [Prise en main du Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Après avoir décidé de migrer vers Customer Journey Analytics, vous devez déterminer le chemin de migration optimal pour votre organisation.

Le chemin que vous choisissez pour migrer d’Adobe Analytics vers Customer Journey Analytics dépend des facteurs suivants :

* Votre mise en oeuvre Adobe Analytics existante

* Vos objectifs pour le futur

Utilisez les informations de cette page pour déterminer le chemin de migration du Customer Journey Analytics qui correspond le mieux à la mise en oeuvre actuelle et aux objectifs futurs de votre entreprise.

Pour déterminer le chemin de migration optimal pour votre organisation, les sections suivantes doivent être lues de manière séquentielle :

1. Tout d’abord, [comprendre les chemins de migration disponibles ;](#understand-migration-methods).

1. Alors, [déterminer les chemins de migration disponibles ;](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Et enfin, [évaluer les avantages et les inconvénients de chaque chemin de migration ;](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Présentation des chemins de migration

Il existe différents chemins de migration pour la migration d’Adobe Analytics vers Customer Journey Analytics.

En règle générale, chaque chemin de migration varie en fonction du niveau d’effort requis pour exécuter la migration, ainsi que de la viabilité à long terme atteinte une fois la migration terminée.

Le tableau suivant répertorie chaque chemin de migration, son niveau d’effort et sa viabilité à long terme :

| Chemin de migration | Niveau d&#39;effort | Viabilité à long terme |
|---------|----------|---------|
| **Nouvelle mise en oeuvre du SDK Web Experience Platform**</br> Bien qu’il ne s’agisse pas techniquement d’une migration, vous pouvez commencer à utiliser Customer Journey Analytics en effectuant une nouvelle mise en oeuvre du SDK Web Experience Platform. Vous pouvez ainsi commencer à envoyer des données à Adobe Experience Platform Edge Network et Customer Journey Analytics. <p>Pour les entreprises qui ne disposent pas encore du SDK Web, ce chemin de migration est peut-être le plus simple pour obtenir des données vers l’Edge Network, car il nécessite le moins d’étapes. Cependant, étant donné que tout le travail est déjà effectué (comme la création du schéma XDM), il nécessite un effort initial plus important.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Créez un schéma XDM pour votre organisation.</li><li>Mettez en oeuvre le SDK Web.</li><li>Envoyez des données à Platform.</li></ol> | Élevé | Élevé |
| **Migration de votre mise en oeuvre Adobe Analytics pour utiliser le SDK Web**</br> Si votre mise en oeuvre Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez la migrer pour utiliser le SDK Web Adobe Experience Platform afin de commencer à envoyer des données à Edge Network et Adobe Analytics, avant de les envoyer à Customer Journey Analytics.<p>Pour les entreprises qui ne disposent pas encore du SDK Web, il s’agit de la méthode la plus simple et la plus fluide pour obtenir des données vers les Edge Network. Elle nécessite davantage d’étapes, mais offre une transition plus méthodique d’Adobe Analytics vers les Customer Journey Analytics, avec des jalons plus tangibles.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Déplacez votre mise en oeuvre Adobe Analytics existante vers le SDK Web et vérifiez que tout fonctionne dans Adobe Analytics.</li><li>Créez un schéma XDM pour votre entreprise à mesure que vous en aurez le temps.</li><li>Utilisez le mappage de flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li><li>Envoyez des données à Platform.</li></ol> | Modérer | Élevé |
| **Configuration de la mise en oeuvre existante du SDK Web d’Adobe Analytics**</br> Si votre mise en oeuvre Adobe Analytics utilise déjà le SDK Web de Adobe Experience Platform, vous pouvez commencer à envoyer des données à Customer Journey Analytics avec un effort minimal.<p>Avant d’envoyer des données à Customer Journey Analytics, pensez à mettre à jour votre schéma Adobe Analytics en fonction des besoins spécifiques de votre entreprise et de toute autre application Platform que vous utilisez.</p><p>Les étapes de base sont les suivantes :</p><ol><li>Commencez à envoyer des données à Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Facultatif) Créez un schéma XDM pour votre entreprise à mesure que vous en aurez le temps.</li><li>(Conditionnel) Si vous avez créé un schéma XDM, utilisez le mappage de flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.</li></ol> | Faible | Élevé |
| **Utilisation du connecteur source Analytics**</br> Si votre mise en oeuvre Adobe Analytics est AppMeasurement ou l’extension Analytics, vous pouvez commencer à envoyer des données vers une vue de données dans Customer Journey Analytics.<p>Il s’agit de la méthode la plus simple pour obtenir des données vers Customer Journey Analytics, mais elle est la méthode la moins viable à long terme.</p> | Faible | Faible |

{style="table-layout:auto"}

Utilisez le diagramme suivant pour vous aider à visualiser où chaque chemin de migration se situe sur le spectre en termes de niveau d’effort et de viabilité à long terme :

![Chemins de migration cja](assets/cja-migration-methods.png)

## Évaluation des chemins de migration disponibles en fonction de votre mise en oeuvre Adobe Analytics actuelle

Tous les chemins de migration ne sont pas disponibles pour chaque type de mise en oeuvre Adobe Analytics.

Utilisez les informations ci-dessous pour vous aider à déterminer le chemin de migration le plus approprié pour votre entreprise.

Contactez votre représentant d’Adobe si vous avez besoin de conseils, de conseils ou d’assistance plus précis.

| Implémentation Adobe Analytics existante | Chemins de migration disponibles |
|---------|----------|
| AppMeasurement | <ul><li>Nouvelle mise en oeuvre du SDK Web Experience Platform</li><li>Migration d’Adobe Analytics vers le SDK Web</li><li>Connecteur source Analytics</li></ul> |
| Extension Adobe Analytics | <ul><li>Nouvelle mise en oeuvre du SDK Web Experience Platform</li><li>Migration d’Adobe Analytics vers le SDK Web</li><li>Connecteur source Analytics</li></ul> |
| SDK Web | <ul><li>Configuration de l’implémentation du SDK Web Adobe Analytics pour envoyer des données à Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Peser les avantages et les inconvénients des chemins de migration disponibles

Les avantages et les inconvénients d’un chemin de migration donné varient en fonction de votre implémentation Adobe Analytics existante.

Avant d’utiliser les informations ci-dessous pour déterminer quel chemin de migration vous convient, passez en revue les informations de la section [Présentation des chemins de migration](#understand-migration-methods) si vous ne l&#39;avez pas déjà fait.

### Pour les mises en oeuvre Adobe Analytics utilisant : AppMeasurement et l’extension Adobe Analytics

Vous trouverez ci-dessous les chemins de migration disponibles pour les organisations qui ont implémenté Adobe Analytics avec AppMeasurement ou l’extension Adobe Analytics. Développez chaque section pour afficher les avantages et les inconvénients de chaque chemin de migration.

#### Chemins de migration

+++Nouvelle mise en oeuvre du SDK Web Experience Platform

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network**: <p>Ces avantages incluent :</p><ul><li>Rapports et disponibilité des données très performants car Adobe Experience Platform est conçu pour fonctionner [cas pratiques de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidation de la mise en oeuvre de la collecte de données Adobe Experience Cloud entre d’autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Ne pas dépendre de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul></li><li>**Futur**: les futures mises à jour de mise en oeuvre sont plus simples.</li></ul> | <ul><li>**Nécessite une nouvelle mise en oeuvre entièrement nouvelle**: l’obligation d’effectuer une nouvelle mise en oeuvre à partir de zéro signifie les inconvénients suivants : </li><ul><li>**Durée**: il s’agit du chemin de migration le plus long et le plus exigeant, car il nécessite de recommencer une nouvelle mise en oeuvre.</li><li>**Doit recréer le schéma complet dans XDM**: pour pouvoir commencer à implémenter le SDK Web, vous devez recréer le schéma complet dans XDM.</li><li>**Doit recréer des règles et des éléments de données**: pour pouvoir commencer à implémenter le SDK Web, vous devez recréer toutes les conditions de règle et tous les éléments de données de votre implémentation Adobe Analytics.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Migration d’Adobe Analytics vers le SDK Web Experience Platform

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network**: <p>Ces avantages incluent :</p><ul><li>Rapports et disponibilité des données très performants car Adobe Experience Platform est conçu pour fonctionner [cas pratiques de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidation de la mise en oeuvre de la collecte de données Adobe Experience Cloud entre d’autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Ne pas dépendre de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre mise en oeuvre existante**: bien que cette approche nécessite quelques modifications de mise en oeuvre, elle ne nécessite pas une mise en oeuvre entièrement nouvelle de toutes pièces. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation sans affecter vos rapports Adobe Analytics existants.</li><li>**Permet de créer un schéma XDM pour votre entreprise ultérieurement.**: vous pouvez migrer votre mise en oeuvre Adobe Analytics existante pour utiliser le SDK Web et vérifier que tout fonctionne dans Adobe Analytics, puis créer le schéma XDM. Cette flexibilité permet une migration plus méthodique et réfléchie.</li></ul> | <ul><li>**Nécessite un mapping pour envoyer des données à Platform**: lorsque votre entreprise est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet de données soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui n’implique pas d’effectuer des modifications de mise en oeuvre. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li><li>**Dette technique**: comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications ultérieurement, si nécessaire. </li></ul> |

{style="table-layout:auto"}

+++

+++Utilisation du connecteur source Analytics

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>Chemin de migration le moins long et le plus exigeant. <p>Les données sont rapidement transférées vers Customer Journey Analytics avec un investissement minimal.</p></li></ul> | <ul><li>**Les données ne sont pas envoyées à l’Edge Network**: <p>Cela entraîne les inconvénients suivants :</p><ul><li>Niveau le plus élevé de [latence](/help/admin/guardrails.md#latencies) dans les rapports de tous les chemins de migration ; non optimisé pour les cas d’utilisation de la personnalisation en temps réel.</li><li>Les données ne peuvent pas être partagées avec d’autres applications Adobe Experience Platform ; elles sont limitées à Customer Journey Analytics uniquement.</li><li>Dépend de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Difficulté à passer au SDK Web à l’avenir**: </li><li>**Utilise le groupe de champs Événement d’expérience Analytics dans votre schéma**: ce groupe de champs ajoute de nombreux événements Adobe Analytics inutiles dans votre schéma de Customer Journey Analytics.  Cela peut entraîner un schéma plus complexe et encombré que ce qui est nécessaire à Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

+++

### Pour les implémentations d’Adobe Analytics à l’aide de : SDK Web

Le chemin de migration suivant est disponible pour les organisations qui ont mis en oeuvre Adobe Analytics avec le SDK Web Experience Platform.

Lors du choix de ce chemin de migration, vous devez également choisir votre schéma.

#### Chemin de migration

+++Configuration de la mise en oeuvre du SDK Web Adobe Analytics pour envoyer des données à Customer Journey Analytics

| Avantages | Inconvénients |
|----------|---------|
| Il s’agit du chemin de migration préféré si votre mise en oeuvre Adobe Analytics utilise déjà le SDK Web.<ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network**: <p>Ces avantages incluent :</p><ul><li>Rapports et disponibilité des données très performants car Adobe Experience Platform est conçu pour fonctionner [cas pratiques de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidation de la mise en oeuvre de la collecte de données Adobe Experience Cloud entre d’autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Ne pas dépendre de la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre mise en oeuvre existante**: bien que cette approche nécessite quelques modifications de mise en oeuvre, elle ne nécessite pas une mise en oeuvre entièrement nouvelle de toutes pièces. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation sans affecter vos rapports Adobe Analytics existants.</li><li>**Permet d’utiliser un schéma XDM**: vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou de créer un schéma XDM et de mapper des champs dans l’objet de données à votre schéma XDM. [Schémas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) sont un schéma flexible permettant de définir les champs dont vous avez besoin et uniquement ceux pertinents. <p>Voir &quot;Utilisation de votre propre schéma XDM&quot; ci-dessous pour plus d’informations sur les avantages de l’utilisation de votre propre schéma XDM.</p></li><li>**Conserve les règles et les éléments de données**: bien qu’il nécessite de nouvelles actions de règle, vous pouvez réutiliser vos éléments de données et conditions de règle existants avec des modifications minimales.</li><li>**Futur**: si vous choisissez d’utiliser votre propre schéma XDM, les futures mises à jour de mise en oeuvre seront plus simples.</li></ul> | Aucun |

{style="table-layout:auto"}

+++

#### Choix du schéma

Si vous choisissez le chemin de migration qui vous permet de configurer l’implémentation du SDK Web d’Adobe Analytics pour envoyer des données à Customer Journey Analytics, vous pouvez choisir le schéma que vous souhaitez utiliser.

Vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou de le mettre à jour vers votre propre schéma XDM afin de mieux vous aligner sur les besoins de votre entreprise lorsque vous commencez à utiliser d’autres services Platform.

+++Utilisation du schéma Adobe Analytics avec l’implémentation du SDK Web Adobe Analytics

| Avantages | Inconvénients |
|----------|---------|
| <p>L’utilisation du schéma Adobe Analytics offre les avantages suivants :</p><ul><li>Facilité de migration<p>Si vous envoyez déjà des données à Adobe Analytics avec le SDK Web de Adobe Experience Platform, vous pouvez ajouter un service supplémentaire à votre flux de données pour envoyer des données à Adobe Experience Platform (qui peut ensuite être utilisé dans votre configuration de Customer Journey Analytics).</p></li></ul> | <p>L’utilisation du schéma Adobe Analytics présente les inconvénients suivants :</p><ul><li>Bien que l’utilisation du schéma Adobe Analytics ne vous limite pas en termes de la manière dont il peut être utilisé avec d’autres applications Platform, elle génère un schéma plus complexe qu’il ne pourrait l’être autrement. En effet, le schéma Adobe Analytics contient de nombreux objets spécifiques à Adobe Analytics qui ne seront probablement pas utilisés par votre organisation.<p>Lorsque des modifications du schéma sont requises, vous devez passer en revue des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></li></ul> |

+++

+++Utilisez votre propre schéma XDM avec l’implémentation du SDK Web d’Adobe Analytics.

| Avantages | Inconvénients |
|----------|---------|
| <ul><p>La mise à jour de votre propre schéma XDM offre les avantages suivants :</p><ul><li>Schéma rationalisé adapté aux besoins de votre entreprise et aux applications Platform spécifiques que vous utilisez.</li><p>Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></ul> | <p>La mise à jour de votre propre schéma XDM présente les inconvénients suivants :</p><ul><li>La mise à jour de votre schéma est un processus chronophage qui est nécessaire avant de commencer à envoyer des données à Customer Journey Analytics.</li></ul> |

+++

## Ensuite, envoyez les données à Adobe Experience Platform.

Après avoir utilisé les informations ci-dessus pour choisir un chemin de migration, apprenez à [envoyer des données à Adobe Experience Platform ;](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) selon le chemin de migration que vous avez choisi.
