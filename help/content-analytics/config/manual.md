---
title: Configuration manuelle de Content Analytics
description: Configuration manuelle de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

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

Pour activer une nouvelle configuration ou les modifications apportées à une configuration existante, vous devez [publier](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} la propriété de balise associée. Ce n’est que lorsque vous publiez votre propriété de balise Content Analytics que les données Content Analytics sont collectées pour les domaines, l’expérience et les ressources que vous avez configurés.


## Désactiver

Pour désactiver la collecte des données d’analyse de contenu, [dépubliez](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} la propriété de balise associée pour votre configuration d’analyse de contenu.



## Modifier

En règle générale, vous devez utiliser l’assistant de configuration [guidé](guided.md) pour apporter des modifications à votre implémentation.

Vous pouvez également utiliser l’extension Adobe Content Analytics dans la propriété de balise associée à votre configuration Content Analytics pour apporter des modifications aux artefacts suivants :

* [Sandbox et flux de données](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Vous devez vérifier que le sandbox et le flux de données que vous configurez dans l’extension Adobe Content Analytics sont déjà configurés pour Content Analytics à l’aide de la [configuration guidée](guided.md) à une étape antérieure. Cette configuration garantit que tous les artefacts requis sont disponibles.<br/><br/>Vous devez également vérifier que vos mises à jour pour le sandbox ou les flux de données n’interfèrent pas avec une autre configuration Content Analytics configurée pour utiliser le même sandbox ou les mêmes flux de données.
  >

* [Filtrage des événements](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  Vous pouvez modifier les expressions régulières pour modifier la manière dont vous filtrez les pages et les ressources.


Après avoir apporté des modifications à l’extension Adobe Content Analytics, assurez-vous de les [activer](#activate).



>[!MORELIKETHIS]
>
>[Configuration guidée](guided.md)
>[Présentation de la publication des balises de collecte de données](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>