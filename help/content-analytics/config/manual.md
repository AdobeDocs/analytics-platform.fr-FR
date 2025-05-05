---
title: Configuration de Content Analytics
description: Comment configurer Content Analytics manuellement
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 5%

---

# Configuration de Content Analytics

Cet article décrit les actions manuelles requises pour démarrer ou arrêter la collecte de données d’une configuration Content Analytics ou pour modifier votre implémentation Content Analytics.

Les actions de configuration manuelles suivantes sont disponibles :

## Démarrer la collecte de données

Pour démarrer la collecte de données pour une configuration Content Analytics implémentée, procédez comme suit :

1. Suivez le [ flux de publication ](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"}. Publiez la bibliothèque pour la propriété Tags contenant votre configuration Content Analytics.

1. [Installez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/environments/environments#installation) le code incorporé dans l’élément `<head>` des pages dans votre environnement de développement, d’évaluation ou de publication, sous réserve de Content Analytics.


## Arrêter la collecte de données

Pour arrêter la collecte de données pour une configuration Content Analytics implémentée, procédez comme suit :

1. Supprimez le [code incorporé](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/environments/environments) dans l’élément `<head>` des pages de votre environnement de développement, d’évaluation ou de production, sous réserve de Content Analytics.
1. [Supprimez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview) la propriété Balises associée à votre configuration Content Analytics.



## Modifier la collecte de données

Vous pouvez apporter des modifications mineures à une configuration implémentée à l’aide de l’[assistant de configuration guidé](guided.md). Par exemple, modifiez la vue de données ou activez ou désactivez des expériences.

Vous utilisez l’extension [Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Tags associée à votre configuration Content Analytics pour apporter des modifications aux artefacts suivants :

* [Sandbox et flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Vérifiez que le sandbox et le flux de données que vous configurez dans l’extension Adobe Content Analytics sont déjà configurés pour Content Analytics à l’aide de la [configuration guidée](guided.md) à un stade antérieur. Cette configuration garantit que tous les artefacts requis sont disponibles.<br/><br/>Vérifiez également que les mises à jour du sandbox ou des flux de données n’interfèrent pas avec une autre configuration Content Analytics configurée pour utiliser le même sandbox ou les mêmes flux de données.
  >

* [Capture et définition de l’expérience](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Vous pouvez activer ou désactiver des expériences et modifier les combinaisons d’expressions régulières et de paramètres de requête afin de déterminer comment le contenu est rendu sur votre site web.

* [Segmentation des événements](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Vous pouvez modifier les expressions régulières pour modifier la manière dont vous segmentez les pages et les ressources.


Après avoir apporté des modifications à l’extension Adobe Content Analytics, veillez à utiliser [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"} pour commencer la collecte de données en fonction des modifications apportées.



>[!MORELIKETHIS]
>
>[Configuration guidée](guided.md)
>[Présentation de la publication des balises de collecte de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview)
>


## Contrôle de version

Si vous souhaitez collecter des expériences Content Analytics, vous devez envisager d’implémenter le contrôle de version pour vous assurer que les nouvelles expériences (modifications apportées à votre page web) sont correctement collectées.

Pour implémenter le contrôle de version, vous ajoutez une fonction de `adobe.getContentExperienceVersion` globale sur les pages que vous prenez en compte pour les expériences que vous souhaitez analyser.

La fonction `adobe.getContentExperienceVersion` doit renvoyer une chaîne en tant que valeur, qui peut correspondre à tout ce que vous choisissez, pour identifier la version. La version est ajoutée à l’URL [Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Si la fonction n’est pas présente ou si aucune valeur n’est renvoyée par la fonction , la valeur `NoVersion` est utilisée par défaut.

### Exemple

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
