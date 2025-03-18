---
title: Comprendre les options de prise en charge du SDK Web lors de la mise à niveau vers Customer Journey Analytics
description: Découvrez les options d’implémentation de Web SDK lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 54%

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

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implémenter le SDK Web pour la propriété donnée"
>abstract="Sélectionnez le type d’implémentation souhaité dans le guide de mise à niveau pour obtenir des instructions plus détaillées."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Ajouter la bibliothèque du SDK Web à votre système de gestion de balises tiers"
>abstract="Contactez l’équipe d’administration de votre système de gestion de balises pour ajouter la bibliothèque du SDK web à votre site.<br><br>Le temps d’exécution de cette tâche dépend en grande partie de la réactivité de la personne responsable de votre système de gestion des balises. L’ajout de la bibliothèque du SDK web peut être regroupé avec la logique d’implémentation associée et l’opération peut être déployée pendant les cycles de publication standard de votre organisation."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Le processus recommandé de mise à niveau d’Adobe Analytics vers Customer Journey Analytics est une nouvelle implémentation d’Experience Platform Web SDK, qui est la méthode de collecte de données préférée pour Customer Journey Analytics.

Il existe trois manières prises en charge d’utiliser Adobe Experience Platform Web SDK :

* [Extension de balise Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension) : Adobe recommande d’utiliser cette méthode. Installez une balise de chargement sur votre site, puis utilisez l’interface utilisateur de la collecte de données de Adobe Experience Platform pour configurer votre implémentation.

* [Bibliothèque JavaScript Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) : référencez un fichier de bibliothèque hébergé sur un réseau CDN ou hébergez le fichier de bibliothèque à l’aide de votre propre infrastructure. Effectuez des appels à la bibliothèque dans le code de votre site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm) : installez le SDK Web sur votre site à l’aide du gestionnaire de packages NPM.

Pour plus d’informations, consultez [Présentation de l’installation de Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) dans le Guide d’Experience Platform Web SDK.
