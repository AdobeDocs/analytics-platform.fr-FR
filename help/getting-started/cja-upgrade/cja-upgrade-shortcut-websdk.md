---
title: Raccourci de mise à niveau Migration d’une mise en oeuvre d’AppMeasurement ou d’extension Analytics pour utiliser le SDK Web
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 56%

---

# Raccourci de mise à niveau : migration d’une implémentation d’extension AppMeasurement ou Analytics pour utiliser le SDK web {#shortcut-migrate-websdk}

>[!NOTE]
>
>Cette documentation doit être utilisée dans le cadre du [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrer votre implémentation Analytics pour utiliser le SDK web"
>abstract="Au lieu d’envoyer des données par le biais d’un objet XDM, vous pouvez envoyer toutes vos variables au format AppMeasurement par le biais de l’objet de données. Ce raccourci vous permet de continuer à utiliser votre logique AppMeasurement pour envoyer des données à Platform."

<!-- markdownlint-enable MD034 -->

Lors de la mise à niveau vers Customer Journey Analytics, Adobe [ recommande une nouvelle mise en oeuvre du SDK Web Experience Platform ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Cependant, en fonction de plusieurs facteurs, tels que la chronologie et les contraintes de ressources, les étapes de mise à niveau recommandées peuvent ne pas être pratiques pour votre entreprise.

Si votre mise en oeuvre Adobe Analytics est AppMeasurement ou l’extension Analytics, un raccourci de mise à niveau est disponible. Il vous permet de migrer votre mise en oeuvre Adobe Analytics afin d’utiliser le SDK Web Adobe Experience Platform pour commencer à envoyer des données à Edge Network et Adobe Analytics, avant de les envoyer à Customer Journey Analytics.

## Avantages et inconvénients

Tenez compte des avantages et des inconvénients suivants du raccourci de mise à niveau pour migrer la mise en oeuvre de votre extension AppMeasurement ou Analytics afin d’utiliser le SDK Web :

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>**Fournit tous les avantages de l’hébergement des données dans Experience Edge Network** : <p>Les avantages sont les suivants :</p><ul><li>Rapports et disponibilité des données hautement performants, grâce à Adobe Experience Platform conçu pour optimiser les [cas d’utilisation de personnalisation en temps réel](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=fr)</li><li>Consolidation de l’implémentation de la collecte de données Adobe Experience Cloud avec les autres produits Experience Cloud (AJO, RTCDP, etc.)</li><li>Pas de dépendance à la nomenclature Adobe Analytics (prop, eVar, événement, etc.)</li></ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite quelques modifications d’implémentation, l’implémentation ne part pas de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation sans affecter vos rapports Adobe Analytics existants.</li><li>**Permet de créer ultérieurement un schéma XDM pour votre organisation** : vous pouvez migrer votre implémentation Adobe Analytics existante pour utiliser le SDK web et vérifier que tout fonctionne dans Adobe Analytics, puis créer le schéma XDM. Cette flexibilité permet une mise à niveau plus méthodique et plus réfléchie vers Customer Journey Analytics.</li></ul> | <ul><li>**Nécessite un mappage pour l’envoi de données à Platform** : lorsque votre organisation est prête à utiliser Customer Journey Analytics, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet de données soit une entrée dans l’outil de mappage de train de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui évite toute modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li><li>**Dette technique** : cette approche utilisant une forme modifiée de votre implémentation existante, il peut être plus difficile de suivre la logique d’implémentation et d’effectuer des modifications ultérieurement, le cas échéant. </li></ul> |

{style="table-layout:auto"}

## Étapes de base

Si vous décidez d’utiliser le raccourci de mise à niveau pour migrer votre mise en oeuvre d’AppMeasurement ou d’extension Analytics afin d’utiliser le SDK Web, une nouvelle étape est ajoutée aux étapes générées dynamiquement pour votre organisation dans le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Les étapes de base de la migration d’une mise en oeuvre d’AppMeasurement ou d’extension Analytics pour utiliser le SDK Web sont les suivantes :

1. Commencez à envoyer des données à Platform.

   Si vous envoyez déjà des données à Platform avec votre implémentation Adobe Analytics, cette étape n’est pas requise. Vous devez simplement créer une connexion entre les jeux de données Platform et Customer Journey Analytics, comme décrit plus loin dans ce processus.

1. (Facultatif) Créez un schéma XDM pour votre entreprise lorsque vous en avez le temps.

1. (Le cas échéant) Si vous avez créé un schéma XDM, utilisez le mappage de train de données pour mapper tous les champs de l’objet de données à votre schéma XDM.
