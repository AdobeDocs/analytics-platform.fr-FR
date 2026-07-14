---
title: Rapports de consentement et cas d’utilisation de filtrage
description: Explorez les cas d’utilisation de création de rapports sur l’appartenance à une politique de consentement des visiteurs et de filtrage des visiteurs non consentants au moment de l’ingestion dans Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 585
ht-degree: 0%

---

# Rapports de consentement et cas d’utilisation de filtrage

La création de rapports et le filtrage sur le consentement vous permettent de créer des rapports sur l’appartenance à une politique de consentement des visiteurs et, éventuellement, d’exclure les visiteurs non consentants avant que leurs données ne pénètrent dans Customer Journey Analytics. Pour plus d’informations, voir [Présentation des rapports et du filtrage de consentement](/help/connections/consent-reporting-filtering/consent-overview.md).

Cet article décrit des exemples de cas d’utilisation. Avant de les passer en revue, familiarisez-vous avec les points à prendre en compte ci-dessous, car ils affectent les résultats que vous voyez dans vos rapports.

## Considérations relatives aux rapports

* **Le filtrage s’applique au niveau de la connexion** : lorsque vous activez le filtrage, toutes les vues de données sous la connexion configurée héritent du même comportement. Vous ne pouvez pas filtrer une vue de données sous une connexion différemment d’une autre.

* **Le filtrage utilise la logique d’inclusion** : les données d’un visiteur ne sont ingérées que si celui-ci correspond à toutes les politiques de consentement qui s’appliquent aux actions marketing activées. Un visiteur ne disposant d’aucune politique applicable est exclu.

* **Les données exclues ne peuvent pas être récupérées** : comme le filtrage se produit au moment de l’ingestion, les données exclues ne sont pas stockées dans Customer Journey Analytics. La modification ultérieure de votre configuration ne récupère pas les données exclues pour les dates antérieures.

* **L’appartenance à la politique de consentement provient du jeu de données Profil** : les rapports reflètent l’appartenance à la politique de consentement présente dans le champ `consentPoliciesIDMap` du jeu de données Profil. Un visiteur doit avoir un événement correspondant dans la connexion pour apparaître dans les rapports.

## Exemples de cas d’utilisation

### Cas d’utilisation 1 : rapport sur le consentement sans filtrer les données

Avant de décider de filtrer ou non, déterminez le nombre de visiteurs qui correspondent à chaque politique de consentement pour répondre à des questions telles que :

* _« Combien de nos visiteurs ont consenti à l’utilisation d’Analytics ?«_
* _« Quelles politiques de consentement ont la couverture la plus importante et la moins étendue pour nos visiteurs ? »_

**Flux de configuration :**

1. Créez une configuration et sélectionnez le sandbox, le jeu de données de profil et la connexion contenant vos données d’appartenance à la politique de consentement.

1. Laissez le filtre **[!UICONTROL Analytics]** et **[!UICONTROL Science des données]** désactivé.

1. Dans Analysis Workspace, créez un tableau à structure libre avec la dimension **[!UICONTROL Nom de la politique]** et la mesure **[!UICONTROL Visiteurs avec consentement]** pour afficher la couverture par politique.

Utilisez ces informations pour décider s’il faut activer le filtrage et pour quelles actions marketing.

### Cas d’utilisation 2 : exclure les visiteurs non consentants de la création de rapports Analytics

Assurez-vous que les rapports standard incluent uniquement les visiteurs qui ont consenti à l’utilisation d’Analytics pour répondre à des questions telles que :

* _« Comment notre audience se comporte-t-elle lorsque nous créons des rapports uniquement sur les visiteurs consentants ?«_
* _« Pouvons-nous nous assurer que les données de visiteurs non consentants n’entrent jamais dans nos rapports d’analyse ? »_

**Flux de configuration :**

1. Créez ou modifiez une configuration pour la connexion qui alimente vos rapports d’analyse.

1. Activez le bouton (bascule) Filtrage **[!UICONTROL Analytics]**.

1. Confirmez la configuration. À partir de maintenant, Customer Journey Analytics n’ingère les données d’un visiteur que si celui-ci correspond à toutes les politiques de consentement qui s’appliquent à l’action marketing Analytics.

Comme le filtrage se produit au moment de l’ingestion, les rapports en aval, les exportations et les API reflètent automatiquement uniquement les visiteurs consentants, sans que des modifications au moment du rapport ne soient nécessaires.

### Cas d’utilisation 3 : filtrer les cas d’utilisation d’analyse et de science des données indépendamment

Appliquez différentes exigences de consentement aux rapports standard et aux cas d’utilisation de science des données pour répondre à des questions telles que :

* _« Pouvons-nous inclure un plus grand nombre de visiteurs dans les analyses tout en appliquant un consentement plus strict pour l’apprentissage automatique ? »_

**Flux de configuration :**

1. Créez ou modifiez une configuration pour la connexion appropriée.

1. Activez le bouton (bascule) **[!UICONTROL Analytics]**, le bouton (bascule) **[!UICONTROL Science des données]** ou les deux, selon les exigences de consentement pour chaque cas d’utilisation.

1. Confirmez la configuration. Customer Journey Analytics évalue indépendamment les politiques de consentement qui s’appliquent à chaque action marketing activée.

Utilisez cette approche lorsque votre entreprise applique différentes exigences de consentement à différentes catégories d’utilisation des données.
