---
title: Configuration manuelle de Content Analytics
description: Configuration manuelle de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---

# Configuration manuelle de Content Analytics

>[!WARNING]
>
>Cet article est un avant-projet non officiel d’une version finale à venir et fait partie de la documentation de Content Analytics. Tout le contenu est sujet à modification et aucune obligation légale quelle qu&#39;elle soit ne peut être dérivée de la version actuelle de cet article.
>

{{release-limited-testing}}

Cet article décrit les actions manuelles requises pour activer ou désactiver une configuration Content Analytics ou pour modifier votre implémentation Content Analytics.

Les actions de configuration manuelles suivantes sont disponibles :

## Activer

Pour activer une nouvelle configuration ou des modifications apportées à une configuration existante :

1. Vous devez suivre le [ flux de publication ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Publiez la bibliothèque pour la propriété Tags contenant votre configuration Content Analytics. Ce n’est qu’à ce moment que les données Content Analytics sont collectées pour les domaines, expériences et ressources que vous avez configurés.

1. Vous devez [installer](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) le code incorporé dans l’élément `<head>` des pages dans votre environnement de développement, d’évaluation ou de publication, sous réserve de Content Analytics.


## Désactiver

Pour désactiver la collecte des données d’analyse de contenu :

1. Supprimez le [code incorporé](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) dans l’élément `<head>` des pages de votre environnement de développement, d’évaluation ou de production, sous réserve de Content Analytics.
1. [Supprimez](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la propriété Balises associée à votre configuration Content Analytics.



## Modifier

Vous pouvez apporter des modifications mineures à une configuration implémentée à l’aide de l’[assistant de configuration guidé](guided.md). Par exemple, modifiez la vue de données.

Vous utilisez l’extension [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Tags associée à votre configuration Content Analytics pour apporter des modifications aux artefacts suivants :

* [Sandbox et flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Vérifiez que le sandbox et le flux de données que vous configurez dans l’extension Adobe Content Analytics sont déjà configurés pour Content Analytics à l’aide de la [configuration guidée](guided.md) à un stade antérieur. Cette configuration garantit que tous les artefacts requis sont disponibles.<br/><br/>Vérifiez également que les mises à jour du sandbox ou des flux de données n’interfèrent pas avec une autre configuration Content Analytics configurée pour utiliser le même sandbox ou les mêmes flux de données.
  >

* [Filtrage des événements](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Vous pouvez modifier les expressions régulières pour modifier la manière dont vous filtrez les pages et les ressources.


Après avoir apporté des modifications à l’extension Adobe Content Analytics, assurez-vous d’utiliser le [flux de publication](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} pour activer les modifications.



>[!MORELIKETHIS]
>
>[Configuration guidée](guided.md)
>[Présentation de la publication des balises de collecte de données](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Contrôle de version

Si vous avez besoin du contrôle de version de vos expériences Content Analytics, vous devez ajouter une fonction de `adobe.getContentExperienceVersion` globale sur les pages que vous prenez en compte pour les expériences que vous souhaitez analyser.

La fonction `adobe.getContentExperienceVersion` doit renvoyer une chaîne en tant que valeur, qui peut correspondre à tout ce que vous choisissez, pour identifier la version. La version est ajoutée à l’URL [Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Si la fonction n’est pas présente ou si aucune valeur n’est renvoyée par la fonction , la valeur `NoVersion` est utilisée par défaut.

### Exemple

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
