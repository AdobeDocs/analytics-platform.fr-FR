---
title: Configuration de Content Analytics
description: Comment configurer Content Analytics manuellement
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: ht
source-wordcount: '640'
ht-degree: 100%

---

# Configuration de Content Analytics

Cet article décrit les actions manuelles requises pour démarrer ou arrêter la collecte de données d’une configuration Content Analytics ou pour modifier votre implémentation Content Analytics.

Les actions de configuration manuelles suivantes sont disponibles :

## Démarrer la collecte de données

Pour démarrer la collecte de données pour une configuration Content Analytics implémentée, procédez comme suit :

1. Suivez le [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"}. Publiez la bibliothèque pour la propriété Balises contenant votre configuration Content Analytics.

1. [Installez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/environments/environments#installation) le code incorporé dans l’élément `<head>` des pages dans votre environnement de développement, d’évaluation ou de publication, dans le cadre de Content Analytics.


## Arrêter la collecte de données

Pour arrêter la collecte de données pour une configuration Content Analytics implémentée, procédez comme suit :

1. Supprimez le [code incorporé](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/environments/environments) dans l’élément `<head>` des pages de votre environnement de développement, d’évaluation ou de production, dans le cadre de Content Analytics.
1. [Supprimez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview) la propriété Balises associée à votre configuration Content Analytics.



## Modifier la collecte de données

Vous pouvez apporter des modifications mineures à une configuration implémentée à l’aide de l’[assistant de configuration guidée](guided.md). Par exemple, modifiez la vue de données ou activez ou désactivez des expériences.

Utilisez l’[extension Adobe Content Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview) dans la propriété Balises associée à votre configuration Content Analytics pour apporter des modifications aux artefacts suivants :

* [Sandbox et train de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Vérifiez que le sandbox et le train de données que vous configurez dans l’extension Adobe Content Analytics sont déjà configurés pour Content Analytics à l’aide de la [configuration guidée](guided.md) à une étape antérieure. Cette configuration garantit que tous les artefacts requis sont disponibles.<br/><br/>Vérifiez également que les mises à jour du sandbox ou des trains de données n’interfèrent pas avec une autre configuration Content Analytics qui utilise le même sandbox ou les mêmes trains de données.
  >

* [Capture et définition de l’expérience](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Vous pouvez activer ou désactiver des expériences et modifier les combinaisons d’expressions régulières et de paramètres de requête afin de déterminer comment s’effectue le rendu du contenu sur votre site web.

* [Segmentation d’événement](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Vous pouvez modifier les expressions régulières pour modifier la manière dont vous segmentez les pages et les ressources.


Après avoir apporté des modifications dans l’extension Adobe Content Analytics, veillez à utiliser le [flux de publication](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview){target="_blank"} pour démarrer la collecte de données en fonction des modifications apportées.



>[!MORELIKETHIS]
>
>[Configuration guidée](guided.md)
>>[Vue d’ensemble de la publication des balises de collecte de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview)
>


## Contrôle de version

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

## Identités

Content Analytics gère les identités de la manière suivante :

* L’ECID est automatiquement renseigné dans la partie `identityMap` du schéma Content Analytics.
* Si vous avez besoin d’autres valeurs d’identité dans le `identityMap`, vous devez définir ces valeurs dans le rappel `onBeforeEventSend` dans l’extension Web SDK.
* Le groupement basé sur les champs n’est pas pris en charge, car le schéma est détenu par le système. Vous ne pouvez donc pas ajouter un autre champ au schéma pour prendre en charge le groupement basé sur les champs.


Pour vous assurer que les données d’identité Content Analytics et les données d’identité des données du SDK Web Adobe Experience Platform sont correctement regroupées au niveau du champ, vous devez apporter des modifications au rappel [onBeforeEventSend](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"} du SDK Web.

1. Accédez à la propriété **[!UICONTROL Balises]** qui contient l’extension du SDK Web Adobe Experience Platform et l’extension Adobe Content Analytics.
1. Sélectionnez ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensions]**.
1. Sélectionnez l’extension **[!UICONTROL SDK Web Adobe Experience Platform]**.
1. Sélectionnez **[!UICONTROL Configurer]**.
1. Dans la section **[!UICONTROL Instances SDK]**, faites défiler l’écran jusqu’à **[!UICONTROL Collecte de données]** - Rappel **[!UICONTROL OnBeforeEventSend]**.

   ![Rappel OnBeforeEventSend](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Sélectionnez **[!UICONTROL &lt;/> Fournir le code du rappel OnBeforeEventSend]**.
1. Ajoutez le code suivant :

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Rappel OnBeforeEventSend](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer le code.
1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer l’extension.
1. [Publiez](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/publish/overview) les mises à jour de la propriété Balises.





