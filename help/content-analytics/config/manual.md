---
title: Configuration de Content Analytics
description: Comment configurer Content Analytics manuellement
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a593221a9eb81d747777aedb323fd44a32c470be
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 64%

---

# Configuration de Content Analytics

Cet article décrit les actions manuelles requises pour démarrer ou arrêter la collecte de données d’une configuration Content Analytics ou pour modifier votre implémentation Content Analytics.

Les actions de configuration manuelles suivantes sont disponibles :

## Démarrer la collecte de données

Pour démarrer la collecte de données pour une configuration Content Analytics implémentée, procédez comme suit :

1. Suivez le [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"}. Publiez la bibliothèque pour les propriétés de balises contenant votre configuration Content Analytics.

1. En fonction des canaux que vous avez configurés :

   * Pour **web** : [installez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/environments/environments#installation) le code incorporé dans l’élément `<head>` des pages dans votre environnement de développement, d’évaluation ou de publication, sous réserve de Content Analytics.
   * Pour **mobile** : consultez le guide d’extension [Adobe Content Analytics spécifique à une solution](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) dans la [documentation d’Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) sur la configuration et l’instrumentation de votre application mobile pour Content Analytics.

## Arrêter la collecte de données

Pour arrêter la collecte de données pour une configuration Content Analytics implémentée, en fonction des canaux que vous avez configurés :

* Pour **web** :

   1. Supprimez le [code intégré](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/environments/environments) dans l’élément `<head>` des pages de votre environnement de développement, d’évaluation ou de production, dans le cadre de Content Analytics.
   1. Supprimez la propriété de balises web associée à votre configuration Content Analytics.

* Pour **mobile** :

   1. Supprimez l’extension [](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) de votre application.
   1. Supprimez la propriété de balises mobiles associée à votre configuration Content Analytics.

Suivez le [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"} pour appliquer les modifications.


## Modifier la collecte de données

Vous pouvez apporter des modifications mineures à une configuration implémentée à l’aide de l’[assistant de configuration guidée](guided.md). Par exemple, modifiez la vue de données ou activez ou désactivez des expériences.


### Web

Vous utilisez l’extension web [](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Tags associée à votre configuration Content Analytics pour apporter des modifications aux artefacts suivants :

* [Sandbox et train de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Vérifiez que le sandbox et le train de données que vous configurez dans l’extension Adobe Content Analytics sont déjà configurés pour Content Analytics à l’aide de la [configuration guidée](guided.md) à une étape antérieure. Cette configuration garantit que tous les artefacts requis sont disponibles.<br/><br/>Vérifiez également que les mises à jour du sandbox ou des trains de données n’interfèrent pas avec une autre configuration Content Analytics qui utilise le même sandbox ou les mêmes trains de données.
  >

* [Capture et définition de l’expérience](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Vous pouvez activer ou désactiver des expériences et modifier les combinaisons d’expressions régulières et de paramètres de requête afin de déterminer comment s’effectue le rendu du contenu sur votre site web.

* [Segmentation des événements](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Vous pouvez modifier les expressions régulières pour modifier la manière dont vous segmentez les pages et les ressources.


Après avoir apporté des modifications à l’extension web Adobe Content Analytics, utilisez le [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"} pour commencer à collecter des données.


### Mobile

Vous utilisez l’[extension mobile ](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) dans la propriété Tags associée à votre configuration Content Analytics pour apporter des modifications supplémentaires.

Après avoir apporté des modifications à l’extension web Adobe Content Analytics, utilisez le [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"} pour commencer à collecter des données.


## Contrôle de version

>[!NOTE]
>
>Cette section s’applique uniquement à Content Analytics pour le canal web.


Si vous souhaitez collecter des expériences Content Analytics, pensez à implémenter le contrôle de version pour vous assurer que les nouvelles expériences (modifications apportées à votre page web) sont correctement collectées.

Pour implémenter le contrôle de version, ajoutez une fonction `adobe.getContentExperienceVersion` globale sur les pages que vous considérez comme des expériences que vous souhaitez analyser.

La fonction `adobe.getContentExperienceVersion` doit renvoyer une chaîne en tant que valeur, qui peut être ce que vous voulez, pour identifier la version. La version est ajoutée à l’[URL d’ID d’expérience](/help/content-analytics/report/components.md#experience-metadata).

Si la fonction est absente ou qu’elle ne renvoie aucune valeur, la valeur `NoVersion` est utilisée par défaut.

### Exemple

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

>[!MORELIKETHIS]
>
>[Configuration guidée](guided.md)
>[Vue d’ensemble de la publication des balises de collecte de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview)
>
