---
title: Comprendre les options d’implémentation du SDK web lors de la mise à niveau vers Customer Journey Analytics
description: Découvrir les options d’implémentation du SDK web lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
autotag-review: '2026-05-19T08:21:32.040Z'
TQID: 'https://experienceleague.adobe.com/5mjQHmjaBfxAusSR3EuDykYxJzgaR6P9jiL3HH09Bns'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 100%

---

# Comprendre les options d’implémentation du SDK web lors de la mise à niveau vers Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Bibliothèque JavaScript du SDK web (alloy.js)"
>abstract="Incluez la bibliothèque du SDK web (alloy.js) sur chaque page de votre site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extension de balises du SDK Web"
>abstract="(Recommandé) Si vous n’utilisez pas encore de balises, installez la balise de chargement sur votre site. Si vous utilisez déjà des balises, vous pouvez ajouter l’extension SDK web à votre propriété de balise. Cette option inclut les implémentations utilisant des balises dans les systèmes de collecte de données Adobe Experience Platform et de gestion des balises tiers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Package NPM"
>abstract="Utilisez l’API de collecte de données pour envoyer directement des données à un train de données. Les types non authentifiés (client à serveur) et authentifiés (serveur à serveur) sont pris en charge."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implémenter le SDK Web pour la propriété donnée"
>abstract="Pour obtenir des instructions plus détaillées, sélectionnez le type d’implémentation souhaité dans le guide de mise à niveau."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Ajouter la bibliothèque du SDK Web à votre système de gestion de balises tiers"
>abstract="Contactez l’équipe d’administration de votre système de gestion de balises pour ajouter la bibliothèque du SDK web à votre site.<br><br>Le temps d’exécution de cette tâche dépend en grande partie de la réactivité de la personne responsable de votre système de gestion des balises. L’ajout de la bibliothèque du SDK web peut être regroupé avec la logique d’implémentation associée et l’opération peut être déployée pendant les cycles de publication standard de votre organisation."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Le processus recommandé de mise à niveau d’Adobe Analytics vers Customer Journey Analytics est une nouvelle implémentation du SDK web Experience Platform, qui est la méthode de collecte de données préférée pour Customer Journey Analytics.

Il existe trois manières prises en charge d’utiliser le SDK web Adobe Experience Platform :

* [Extension de balise SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/extension) : Adobe recommande d’utiliser cette méthode. Installez une balise de chargement sur votre site, puis utilisez l’interface d’utilisation de collecte de données d’Adobe Experience Platform pour configurer votre implémentation.

* [Bibliothèque JavaScript SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/library) : référencez un fichier de bibliothèque hébergé sur un réseau CDN ou hébergez le fichier de bibliothèque à l’aide de votre propre infrastructure. Effectuez des appels à la bibliothèque dans le code de votre site.

* [NPM](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/npm) : installez le SDK web sur votre site à l’aide du gestionnaire de modules NPM.

Pour plus d’informations, consultez [Vue d’ensemble de l’installation du SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/overview) dans le guide du SDK web Experience Platform.
