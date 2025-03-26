---
title: Collecter des ID de session de mesures quantiques dans Customer Journey Analytics
description: Modifiez votre implémentation pour inclure des ID de session afin de pouvoir les analyser dans Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: ae88ab16e85bd1274990f8c4d04771398293fe09
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Collecter des ID de session de mesures quantiques dans Customer Journey Analytics

Certains cas d’utilisation, tels que [lier des relectures de session Quantum Metric](tie-session-replays.md) ou [utiliser des cartes thermiques Quantum Metric](heatmap.md) nécessitent que vous modifiiez votre implémentation pour collecter l’identifiant de session Quantum Metric. Cette page décrit le processus à suivre pour importer ces données dans votre implémentation existante.

## Conditions préalables :

Ces étapes supposent que vous utilisiez les balises dans la collecte de données Adobe Experience Platform. Vous pouvez adapter ces méthodes de collecte de données vers une implémentation manuelle de Web SDK si votre entreprise n’utilise pas de balises.

Pour plus d’informations, consultez la documentation de l’[extension de balise Quantum Metric](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

## Étape 1 : capturer l’ID de session de mesure quantique à l’aide de l’extension de balises de mesure quantique

Pour ajouter l’identifiant de session Quantum Metric aux données envoyées à Adobe Experience Platform, procédez comme suit.

1. Utilisez l’extension Quantum Metric dans l’interface utilisateur des balises pour envoyer des données à Quantum Metric.
1. Créez quatre éléments de données :
   1. Un qui capture l’ID de session de Quantum Metric à partir du cookie de Quantum Metric nommé `QuantumMetricSessionID`
   1. Un qui extrait l’ID de session de Quantum Metric à partir de `localStorage`. Parfois, cet élément de données se charge plus rapidement que le cookie défini dans l’autre élément de données.
   1. Utilisez l’assistant d’élément de données ou un JavaScript personnalisé pour extraire le nœud de `s` de l’élément de données `localStorage`.
   1. Une qui utilise la logique pour rechercher d’abord l’élément de données de cookie et le renvoyer à un chemin d’objet XDM s’il est trouvé. Si non défini, essayez de rechercher l’élément de données de l’objet `localStorage` extrait.
1. Envoyez l’élément de données d’identifiant de session Quantum Metric final à l’objet XDM envoyé dans chaque événement.

>[!NOTE]
>Parfois, le SDK Web fonctionne plus rapidement que le code de mesure quantique. Dans ce cas, l’ID de session est envoyé à l’accès suivant. Si un visiteur rebondit, l’ID de session n’est pas collecté dans ces instances.

## Étape 2 : confirmer les champs du jeu de données inclus

Vérifiez que les jeux de données de votre connexion possèdent désormais l’ID de session de mesure quantique dans le jeu de données souhaité.

## Étape 3 : ajouter un ID de session de mesure quantique en tant que dimension disponible

Modifiez la vue de données existante pour ajouter l’ID de session en tant que dimension disponible dans Customer Journey Analytics.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com).
1. Accédez à Customer Journey Analytics, puis sélectionnez **[!UICONTROL Vues de données]** dans le menu supérieur.
1. Sélectionnez la vue de données existante souhaitée.
1. Recherchez la liste du champ d’ID de session de mesure quantique sur la gauche, puis faites-la glisser vers la zone des dimensions au centre.
1. Dans le volet de droite, définissez le paramètre [persistance](/help/data-views/component-settings/persistence.md) sur « Session ».
1. Cliquez sur **[!UICONTROL Enregistrer]**.


