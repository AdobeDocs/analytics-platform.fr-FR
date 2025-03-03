---
title: Comprendre les options de prise en charge du SDK Web lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez les options d’implémentation de Web SDK lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 43%

---

# Comprendre les options de prise en charge du SDK Web lors de la mise à niveau vers Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Bibliothèque JavaScript Web SDK (alloy.js)"
>abstract="Incluez la bibliothèque Web SDK (alloy.js) sur chaque page de votre site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extension de balises du SDK Web"
>abstract="(Recommandé) Si vous n’utilisez pas encore de balises, installez le chargeur de balises sur votre site. Si vous utilisez déjà des balises, vous pouvez ajouter l’extension Web SDK à votre propriété de balise. Cette option inclut les implémentations à l’aide de balises dans les systèmes de collecte de données Adobe Experience Platform et de gestion des balises tiers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Package NPM"
>abstract="Utilisez l’API de collecte de données pour envoyer directement des données à un flux de données. Les types non authentifiés (client à serveur) et authentifiés (serveur à serveur) sont pris en charge."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Le processus recommandé de mise à niveau d’Adobe Analytics vers Customer Journey Analytics est une nouvelle implémentation d’Experience Platform Web SDK, qui est la méthode de collecte de données préférée pour Customer Journey Analytics.

Il existe trois manières prises en charge d’utiliser Adobe Experience Platform Web SDK :

* [Extension de balise Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension) : Adobe recommande d’utiliser cette méthode. Installez une balise de chargement sur votre site, puis utilisez l’interface utilisateur de la collecte de données de Adobe Experience Platform pour configurer votre implémentation.

* [Bibliothèque JavaScript Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) : référencez un fichier de bibliothèque hébergé sur un réseau CDN ou hébergez le fichier de bibliothèque à l’aide de votre propre infrastructure. Effectuez des appels à la bibliothèque dans le code de votre site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm) : installez le SDK Web sur votre site à l’aide du gestionnaire de packages NPM.

Pour plus d’informations, consultez [Présentation de l’installation de Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) dans le Guide d’Experience Platform Web SDK.



