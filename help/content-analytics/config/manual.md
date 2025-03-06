---
title: Configuration manuelle de Content Analytics
description: Configuration manuelle de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
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

1. Vous devez suivre le [ flux de publication ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Ce n’est que lorsque vous avez publié la bibliothèque pour la propriété de balise contenant votre configuration Content Analytics que les données Content Analytics sont collectées pour les domaines, expériences et ressources que vous avez configurés.

1. Vous devez [installer](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) le code incorporé dans l’élément `<head>` des pages de votre environnement de développement, d’évaluation ou de publication, soumis à l’analyse de contenu.


## Désactiver

Pour désactiver la collecte des données d’analyse de contenu :

1. Supprimez le [code intégré](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) dans l’élément `<head>` des pages de votre environnement de développement, d’évaluation ou de production, sous réserve de l’analyse de contenu.
1. [Supprimez](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la propriété de balise associée pour votre configuration Content Analytics.



## Modifier

En règle générale, vous devez utiliser l’assistant de configuration [guidé](guided.md) pour apporter des modifications à votre implémentation.

Vous pouvez également utiliser l’extension [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Tag associée à votre configuration Content Analytics pour apporter des modifications aux artefacts suivants :

* [Sandbox et flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Vous devez vérifier que le sandbox et le flux de données que vous configurez dans l’extension Adobe Content Analytics sont déjà configurés pour Content Analytics à l’aide de la [configuration guidée](guided.md) à une étape antérieure. Cette configuration garantit que tous les artefacts requis sont disponibles.<br/><br/>Vous devez également vérifier que vos mises à jour pour le sandbox ou les flux de données n’interfèrent pas avec une autre configuration Content Analytics configurée pour utiliser le même sandbox ou les mêmes flux de données.
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

Si vous avez besoin d’un contrôle de version de vos expériences Content Analytics, vous devez ajouter une fonction de `adobe.getContentExperienceVersion` globale sur les pages que vous considérez comme des expériences à analyser.

La fonction `adobe.getContentExperienceVersion` doit renvoyer une chaîne comme valeur, qui peut correspondre à tout ce que vous choisissez pour identifier la version. La version est ajoutée à l’URL de l’Experience ID.

Si la fonction n’est pas présente ou si aucune valeur n’est renvoyée par la fonction , la valeur `NoVersion` est utilisée par défaut.

### Exemple

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
