---
title: Utiliser le connecteur source Analytics exclusivement pour effectuer la mise à niveau vers Customer Journey Analytics
description: Découvrez comment créer les champs de mappage et de connecteur source Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 27%

---

# Utiliser le connecteur source Analytics exclusivement pour effectuer la mise à niveau vers Customer Journey Analytics

>[!NOTE]
> 
>Utilisez les informations de cette page pour répondre aux questions de la [liste de contrôle de mise à niveau des Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Bien que cela ne soit pas recommandé, vous pouvez utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics. Toutefois, en raison des inconvénients inhérents à ce type de mise à niveau, Adobe recommande d’utiliser le connecteur source Analytics conjointement avec une nouvelle mise en oeuvre du SDK Web Experience Platform. Pour plus d’informations sur ce chemin de mise à niveau recommandé, voir [Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Utilisez les informations suivantes pour comprendre les avantages et les inconvénients de l’utilisation exclusive du connecteur source :

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>Chemin de mise à niveau le moins long et le plus exigeant. <p>Les données sont migrées rapidement et facilement vers Customer Journey Analytics.</p></li></ul> | <ul><li>**Les données ne sont pas envoyées à Edge Network** : <p>Les inconvénients sont les suivants :</p><ul><li>Niveau le plus élevé de [latence](/help/technotes/guardrails.md#latencies) dans les rapports sur tous les chemins de mise à niveau ; non optimisé pour les cas d’utilisation de la personnalisation en temps réel.</li><li>Les données ne peuvent pas être partagées avec d’autres applications Adobe Experience Platform ; elles sont limitées à Customer Journey Analytics uniquement.</li><li>Dépend de la nomenclature Adobe Analytics (prop, eVar, événement, etc.).</li></ul><li>**Difficile de passer au SDK Web à l’avenir** : vous voudrez éventuellement accéder aux avantages fournis par le SDK Web Experience Platform. Pour commencer à utiliser le SDK Web Experience Platform, vous devez effectuer une nouvelle mise en oeuvre.</li><li>**Utilise le groupe de champs Événement d’expérience Analytics dans votre schéma** : ce groupe de champs ajoute de nombreux événements Adobe Analytics inutiles dans votre schéma de Customer Journey Analytics.  Cela peut générer un schéma plus complexe et encombré que ce qui est nécessaire à Customer Journey Analytics.</li><li>**Nécessite des licences pour Adobe Analytics et Customer Journey Analytics** : l’utilisation du connecteur source Analytics nécessite que vous payiez pour Adobe Analytics et Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

