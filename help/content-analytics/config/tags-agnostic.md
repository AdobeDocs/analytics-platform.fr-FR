---
title: Bibliothèque JavaScript Content Analytics
description: Découvrez comment configurer Content Analytics sans utiliser les balises de la collecte de données Experience Platform et utiliser plutôt la bibliothèque JavaScript Content Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 35abfb5b77384b16beaddab2554a7d48d10be012
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---


# Bibliothèque JavaScript Content Analytics

La bibliothèque JavaScript d’Adobe Content Analytics permet le suivi des événements liés au contenu sur les sites web en envoyant des données de contenu à Adobe Experience Platform via Experience Platform Edge Network. Utilisez cette bibliothèque lorsque vous souhaitez implémenter Content Analytics sans balises Adobe Experience Platform.

>[!NOTE]
>
>Cet article s’applique à Content Analytics pour le canal web.


>[!PREREQUISITES]
>
>* Adobe Experience Platform Web SDK (Alloy) doit être initialisé sur la page avant d’appeler `initializeContentLibrary`.
>* Terminez l’assistant de configuration guidée de Content Analytics pour vous guider tout au long des étapes requises pour configurer les conditions préalables à une configuration de Content Analytics.
>* Une fois la configuration guidée terminée, les paramètres JavaScript peuvent être utilisés.


## Installation

Vous pouvez installer la bibliothèque de deux manières :

### package npm

Utilisez `npm` pour installer la bibliothèque.

1. Sur la ligne de commande, utilisez :

   ```bash
   npm install @adobe/content-analytics
   ```

1. Importez la bibliothèque :

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### Balise de script (CDN)

Chargez la bibliothèque directement à partir du réseau CDN.

1. Initialisez la [bibliothèque JavaScript Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/install/library) et chargez le bundle Content Analytics :

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   où
   * `alloy/2.x.x` fait référence à la version que vous souhaitez utiliser de la bibliothèque [Web SDK JavaScript](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/js/install/library).
   * `content-analytics/1.x.x` fait référence à la version que vous souhaitez utiliser de la bibliothèque SDK Content Analytics.

2. La version autonome expose `window.contentAnalytics` comme fonction d’initialisation.


## Configuration du flux de données

L’option `datastreamId` est obligatoire et doit référencer un flux de données pour lequel le service Experience Platform est configuré avec un jeu de données d’événement d’expérience Content Analytics activé. Assurez-vous que le sandbox associé au flux de données n’est pas déjà associé à une autre configuration Content Analytics.

Vous pouvez fournir des identifiants de flux de données distincts par environnement :

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Capture et définition de l’expérience

Activez le suivi des expériences et contrôlez la manière dont les expériences sont identifiées sur votre site web. Les expériences sont définies en combinant une **expression régulière de domaine** avec des **paramètres de requête** facultatifs qui distinguent une expérience d’une autre dans les pages correspondantes.

| Option | Type | Par défaut | Description |
|--------|------|---------|-------------|
| `includeExperiences` | booléen | `false` | Activer le suivi de l’affichage des pages/expériences |
| `experienceConfigurations` | tableau | - | Définir des expériences par expression régulière de domaine et paramètres de requête |

Chaque entrée de `experienceConfigurations` accepte :

| Propriété | Type | Description |
|----------|------|-------------|
| `regEx` | string | Expression régulière du domaine mise en correspondance avec l’URL de la page (par exemple, `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | tableau | Noms de paramètres de requête dont les valeurs distinguent les expériences sur les pages correspondantes (par exemple, `["outdoors", "patio", "kitchen"]`) |

### Exemple

Consultez ci-dessous un exemple d’activation du suivi d’expérience avec des paramètres de requête et une expression régulière de domaine.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## Filtrage des événements

Contrôlez les URL de page et de ressource incluses dans la collecte de données à l’aide d’expressions régulières. Utilisez les exemples de modèles ci-dessous comme point de départ et validez les modèles avec un testeur d’expression régulière avant le déploiement.

| Option | Type | Par défaut | Description |
|--------|------|---------|-------------|
| `pageUrlQualifier` | chaîne (regex) | - | Effectue uniquement le suivi des pages dont l’URL correspond à ce modèle |
| `assetUrlQualifier` | chaîne (regex) | - | Effectue uniquement le suivi des ressources dont l’URL correspond à ce modèle |
| `excludeURLsFromTracking` | tableau | `[]` | Liste des chaînes URL à exclure du tracking |

### Exemple

Vous trouverez ci-dessous un exemple d’exclusion de pages de documentation de Content Analytics et de prise en compte uniquement des images de produit pour Content Analytics.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
