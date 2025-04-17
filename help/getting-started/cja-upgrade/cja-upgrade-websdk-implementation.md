---
title: Comprendre les options d’implémentation du SDK web lors de la mise à niveau vers Customer Journey Analytics
description: Découvrir les options d’implémentation du SDK web lors de la mise à niveau vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
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

* [NPM](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/npm) : installez le SDK web sur votre site à l’aide du gestionnaire de packages NPM.

Pour plus d’informations, consultez [Vue d’ensemble de l’installation du SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/install/overview) dans le guide du SDK web Experience Platform.
