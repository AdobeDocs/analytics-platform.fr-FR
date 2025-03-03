---
title: Utiliser exclusivement le connecteur source Analytics pour effectuer la mise à niveau vers Customer Journey Analytics
description: Découvrez comment créer le connecteur source Analytics et mapper les champs.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 26%

---

# Alternative de mise à niveau : utilisez uniquement le connecteur source Analytics pour effectuer la mise à niveau vers Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Utiliser exclusivement le connecteur source Analytics"
>abstract="(Non recommandé) Vous pouvez utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics. <br><br>Cette option permet de gagner du temps d’implémentation en envoyant rapidement des données à Customer Journey Analytics. Elle présente toutefois diverses lacunes, telles qu’une latence plus élevée et la difficulté à quitter Adobe Analytics à l’avenir."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Bien que cela ne soit pas recommandé, vous pouvez utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics. Cependant, en raison des inconvénients inhérents à ce type de mise à niveau, Adobe recommande d’utiliser le connecteur source Analytics conjointement avec une nouvelle mise en œuvre d’Experience Platform Web SDK. Pour plus d’informations sur ce chemin de mise à niveau recommandé, voir [ Chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Utilisez les informations du tableau ci-dessous pour comprendre les avantages et les inconvénients de l’utilisation exclusive du connecteur source lors de la mise à niveau vers Customer Journey Analytics.

Si vous décidez d’utiliser le connecteur source Analytics comme seul chemin d’implémentation pour Customer Journey Analytics, suivez les étapes d’implémentation décrites dans la section [ Ingérer et utiliser des données à l’aide des connecteurs source ](/help/data-ingestion/sources.md).

| Avantages | Inconvénients |
|----------|---------|
| <ul><li>Chemin de mise à niveau le moins long et le plus exigeant. <p>Les données sont migrées vers Customer Journey Analytics rapidement et facilement.</p></li></ul> | <ul><li>**Les données ne sont pas envoyées à Edge Network** : <p>Les inconvénients sont les suivants :</p><ul><li>Niveau de [latence](/help/technotes/guardrails.md#latencies) le plus élevé dans les rapports pour tous les chemins de mise à niveau. Non optimisé pour les cas d’utilisation de la personnalisation en temps réel.</li><li>Les données ne peuvent pas être partagées avec d’autres applications Adobe Experience Platform ; elles sont limitées à Customer Journey Analytics uniquement.</li><li>Dépend de la nomenclature Adobe Analytics (prop, eVar, événement, etc.).</li></ul><li>**Difficile de migrer vers le Web SDK à l’avenir** : à terme, vous souhaiterez probablement accéder aux avantages offerts par le Web SDK d’Experience Platform. Pour commencer à utiliser Experience Platform Web SDK, vous devez effectuer une nouvelle mise en œuvre.</li><li>**Utilise le groupe de champs Événement d’expérience Analytics dans votre schéma** : ce groupe de champs ajoute de nombreux événements Adobe Analytics inutiles dans votre schéma de Customer Journey Analytics.  Cela peut générer un schéma plus complexe et encombré que ce qui est nécessaire à Customer Journey Analytics.</li><li>**Nécessite des licences pour Adobe Analytics et Customer Journey Analytics** : l’utilisation du connecteur source Analytics nécessite que vous payiez pour Adobe Analytics et Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}
