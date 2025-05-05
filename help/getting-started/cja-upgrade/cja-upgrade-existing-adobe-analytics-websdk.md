---
title: Configurer votre implémentation du SDK Web d’Adobe Analytics existante pour envoyer des données à Platform
description: Découvrez comment configurer votre implémentation Adobe Analytics Web SDK existante
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 59%

---

# Configurer votre implémentation du SDK Web d’Adobe Analytics existante pour envoyer des données à Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Supprimer Adobe Analytics en tant que service du flux de données"
>abstract="Lorsque les données du SDK Web sont entièrement fonctionnelles, contactez votre administrateur ou administratrice Platform pour supprimer Adobe Analytics en tant que service du flux de données. Avant de procéder, assurez-vous que vos utilisateurs et utilisatrices ont effectué une transition, d’Adobe Analytics vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Si votre mise en œuvre Adobe Analytics utilise déjà le SDK web Adobe Experience Platform, vous pouvez commencer à envoyer des données à Platform en configurant un flux de données. Ou, si vous envoyez déjà des données à Platform, vous devez simplement créer une connexion entre les jeux de données Platform et Customer Journey Analytics.


## Avantages et inconvénients

Tenez compte des avantages et des inconvénients suivants de la configuration de votre implémentation Adobe Analytics Web SDK existante pour envoyer des données à Platform :

| Avantages | Inconvénients |
|----------|---------|
| Il s’agit du chemin de mise à niveau préféré si votre implémentation Adobe Analytics utilise déjà le SDK Web.<ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation sans affecter vos rapports Adobe Analytics existants.</li><li>**Permet d’utiliser un schéma XDM** : vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou de créer un schéma XDM et de mapper des champs dans l’objet de données à votre schéma XDM. Les [schémas XDM](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home#xdm-schemas) sont flexibles et permettent de définir les champs dont vous avez besoin, et uniquement ceux qui sont pertinents pour vous. <p>Voir « Utiliser votre propre schéma XDM » ci-dessous pour plus d’informations sur les avantages de l’utilisation de votre propre schéma XDM.</p></li><li>**Conserve les règles et les éléments de données** : bien que de nouvelles actions de règle soient nécessaires, vous pouvez réutiliser vos éléments de données et conditions de règle existants avec des modifications minimales.</li><li>**À l’épreuve du temps** : si vous choisissez d’utiliser votre propre schéma XDM, les futures mises à jour d’implémentation sont plus simples.</li></ul> | <ul><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet de données soit une entrée dans l’outil de mappage de train de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li><li>**Ajoute une complexité supplémentaire au fil du temps** : tout champ que vous ajouterez ultérieurement doit être mappé à XDM dans le flux de données.<p>Chaque fois qu’un nouveau champ est ajouté à votre implémentation, vous pouvez effectuer l’une des opérations suivantes :</p><ul><li>**Option 1 :** renseignez une nouvelle evar arbitraire ou une nouvelle prop dans l’objet de données, puis mappez-la au champ XDM souhaité.<p>Ce processus améliore la cohérence de l’implémentation côté client, mais il nécessite un mappage.</p></li><li>**Option 2 :** laissez l’objet de données en tant qu’implémentation héritée et commencez à renseigner uniquement l’objet XDM pour tous les nouveaux champs.<p>Ce processus ne nécessite pas de mappage, mais cela signifie que certaines de vos variables sont situées uniquement dans un objet de données, tandis que d’autres variables sont situées uniquement dans un objet XDM. Chaque fois que vous devez résoudre les problèmes d’implémentation, vous devez accéder à deux emplacements. Veillez à ce que vos workflows internes prennent en charge cette fonctionnalité.</p></li></ul> |

{style="table-layout:auto"}

## Procédure de mise en œuvre

1. Commencez à envoyer des données d’Edge Network vers Platform. Envoyez toutes vos variables au format AppMeasurement via l’objet de données.

   Pour plus d’informations, voir [Mappage des variables d’objet de données à Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

1. Choisissez votre schéma.

   Vous pouvez choisir d’utiliser votre schéma Adobe Analytics existant ou de créer un schéma XDM pour mieux vous aligner sur les besoins de votre entreprise lorsque vous commencez à utiliser d’autres services Platform.

   Adobe recommande de créer un schéma XDM. Pour plus d’informations, voir [Création d’un schéma personnalisé à utiliser avec votre implémentation de Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   +++Utilisation du schéma Adobe Analytics

   | Avantages | Inconvénients |
   |----------|---------|
   | <p>L’utilisation du schéma Adobe Analytics offre les avantages suivants :</p><ul><li>Facilité de mise à niveau<p>Si vous envoyez déjà des données à Adobe Analytics avec le SDK web d’Adobe Experience Platform, vous pouvez ajouter un service supplémentaire à votre flux de données pour envoyer des données à Adobe Experience Platform (qui peuvent ensuite être utilisées dans votre configuration de Customer Journey Analytics).</p></li></ul> | <p>L’utilisation du schéma Adobe Analytics présente les inconvénients suivants :</p><ul><li>Bien que l’utilisation du schéma Adobe Analytics ne vous limite pas en termes d’utilisation avec d’autres applications Platform, elle génère un schéma plus complexe que nécessaire. En effet, le schéma Adobe Analytics contient de nombreux objets spécifiques à Adobe Analytics qui ne seront probablement pas utilisés par votre organisation.<p>Lorsque des modifications du schéma sont requises, vous devez passer en revue des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></li></ul> |

   +++

   +++Créer un schéma XDM

   | Avantages | Inconvénients |
   |----------|---------|
   | <ul><p>La mise à jour de votre propre schéma XDM offre les avantages suivants :</p><ul><li>Schéma rationalisé adapté aux besoins de votre organisation et aux applications Platform spécifiques que vous utilisez.</li><p>Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.</p></ul> | <p>La mise à jour de votre propre schéma XDM présente les inconvénients suivants :</p><ul><li>La mise à jour de votre schéma est un processus long qui est nécessaire avant de commencer à envoyer des données à Platform.</li></ul> |

   +++

1. Utilisez le mappage des flux de données pour mapper tous les champs de l’objet de données à votre schéma XDM.

   Pour plus d’informations, consultez [Mappage](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) dans [Préparation des données pour la collecte de données](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) dans la documentation d’Experience Platform.

{{upgrade-final-step}}
