---
title: Cas pratiques du secteur
description: Cas d’utilisation du secteur pour l’analyse guidée
source-git-commit: 9f176bc6bc12291dcdab80af50c32df7d8edf220
workflow-type: tm+mt
source-wordcount: '1442'
ht-degree: 3%

---

# Cas pratiques du secteur

Les cas d’utilisation des analyses guidées varient selon le secteur. Cette page fournit des exemples illustratifs de ce que les équipes produit peuvent accomplir avec les fonctionnalités d’analyse guidée et d’Adobe Product Analytics.

+++**Vente au détail**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Optimisation de l’application d’achat mobile** | De nombreux clients ont téléchargé notre application mobile, mais ne sont jamais revenus. Nous avons trouvé qu&#39;ils l&#39;utilisaient juste pour l&#39;offre initiale et nous avons réengagé ces clients inactifs. | **Augmentez le nombre de LTV des utilisateurs mobiles.** Mesurez et augmentez l’utilisation de l’application afin de développer une expérience utilisateur plus &quot;happy path&quot;. | [Principale vue de croissance des utilisateurs](types/active.md) <p/><p/> [Vue de la croissance nette](types/net-growth.md) |
| **Quantifier l’impact des nouvelles fonctionnalités de passage en caisse** | En tant qu&#39;épicerie en train de tester notre passage aux achats en ligne, nous pouvons rapidement mesurer l&#39;impact de nouvelles fonctionnalités de passage en caisse comme &quot;Avez-vous oublié le beurre ?&quot; des recommandations de produits ou de nouvelles méthodes de paiement, telles que la collecte côté ville. | **Augmentez les taux de conversion.** Mesurez l’impact sur l’entreprise au lieu de simplement utiliser les fonctionnalités. | [Vue d’impact des versions](types/release.md) <p/><p/> [Première utilisation](types/first-use.md) |
| **Réduction du taux d’adhésion** | Nous avons découvert des points de friction dans les parcours client qui provoquent la perte de clientèle. Cela nous a donné l&#39;occasion d&#39;examiner les programmes d&#39;adhésion et d&#39;analyser les comportements et les signaux des membres à risque. | **Réduisez le taux de perte de clientèle.** Identifier les moyens de favoriser et d’entretenir les relations avec les clients afin d’éviter l’attrition et de réduire le taux d’attrition. | [Principale vue de croissance des utilisateurs](types/active.md) <p/><p/> [Vue Friction](types/friction.md) |
| **Rechercher les parcours de vente inefficaces** | Nous avons découvert des inefficacités dans le parcours de nos associés de vente en magasin, où ils ont été retirés aux clients. Nous avons ajusté leur processus, ce qui a donné aux clients une expérience d’achat plus agréable en magasin. | **Améliorez la réponse des ventes.** Améliorez les parcours internes afin de réduire les processus inefficaces, ce qui se traduit par des expériences client positives. | [Vue Friction](types/friction.md) |

{style="table-layout:auto"}

![Vue Friction pour la vente au détail](assets/retail-funnel-friction.png)

![Affichage de l’utilisation pour la vente au détail](assets/retail-trends-usage.png)

+++

+++**Services financiers**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouvelles fonctionnalités** | Nous avons récemment déployé les virements bancaires avec Zelle, et nous devions comprendre l&#39;impact de la nouvelle fonctionnalité sur la finalisation des virements. Maintenant que nous voyons comment les clients réagissent, l’équipe marketing peut le déployer. | **Augmentez les taux de conversion.** Mesurez l’impact des nouvelles fonctionnalités sur les conversions de transfert. | [Vue d’impact des versions](types/release.md) <p/><p/> [Première utilisation](types/first-use.md) |
| **Défaut des appels au centre d’appels** | Notre processus de demande mobile en 5 étapes conduisait les appels vers le centre d&#39;appels. Nous avons rapidement analysé cela, créé une audience et envoyé un email à ces clients afin qu&#39;ils puissent comprendre leur expérience.&quot; | **Isolez la friction dans l&#39;expérience.** Améliorez les parcours &quot;happy path&quot; et réduisez les appels. | [Vue Friction](types/friction.md) <p/><p/> [Vue Tendances des conversions](types/conversion-trends.md) |
| **Réduction du taux de perte de clientèle** | Nous savons que les clients qui se connectent à l’application mobile bancaire avec une fréquence mensuelle restent des clients plus longtemps. Lorsque nous visualisons la croissance de nos utilisateurs d’applications, nous pouvons identifier les personnes à risque et créer une stratégie de retour arrière. | **Réduisez le taux de perte de clientèle.** Maintenir le niveau des clients tout en dépensant pour acquérir de nouveaux clients réels. | [Principale vue de croissance des utilisateurs](types/active.md) <p/><p/> [Vue de la croissance nette](types/net-growth.md) |
| **Nouvelles fonctionnalités recommandées** | Les retraits numériques ont diminué au fil du temps au lieu d&#39;appeler un conseiller financier. Nous aimerions optimiser le processus numérique, et les tendances des données nous aident à prioriser les optimisations avec un comité de pilotage. | **Créez une feuille de route axée sur les données.** Tirez parti des données pour planifier et mettre en oeuvre des optimisations. | [Affichage des tendances d’utilisation](types/usage.md) |

{style="table-layout:auto"}

![Vue de fragment pour les services financiers](assets/fsi-funnel-friction.png)

![Affichage de l’utilisation pour les services financiers](assets/fsi-trends-usage.png)

![Principale vue pour les services financiers](assets/fsi-user-growth-active.png)

+++

+++**Voyage et hébergement**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouvelles fonctionnalités de flux de réservation** | Nous avons rapidement analysé l’impact d’une nouvelle fonction d’étape de réservation sur les taux de conversion et identifié la partie de l’expérience présentant les plus gros gains. | **Augmentez les tarifs des réservations.** Mesurez l’impact sur l’entreprise au lieu de simplement utiliser les fonctionnalités. | [Vue d’impact des versions](types/release.md) <p/><p/> [Vue Friction](types/friction.md) |
| **Optimisation de l’expérience des applications mobiles** | Nous avons pu comprendre rapidement et facilement nos utilisateurs mensuels principaux d’applications (MAU) au fil du temps et identifier l’impact positif par version. | **Augmentez les MTA.** Mesurez et augmentez l’utilisation de l’application, ce qui correspond au bonheur des clients. | [Principale vue de croissance des utilisateurs](types/active.md) <p/><p/> [Vue de la croissance nette](types/net-growth.md) |
| **Trouver des frictions dans le flux d&#39;archivage mobile** | En voyant où les personnes réussissent ou abandonnent le processus d’archivage mobile attendu, nous pouvons facilement identifier les zones à optimiser l’expérience. | **Augmentez le CSAT et réduisez les IROP.** La suppression de la friction entraîne une expérience de &quot;jour de voyage&quot; plus transparente. | [Vue Friction](types/friction.md) <p/><p/> [Vue Tendances des conversions](types/conversion-trends.md) |
| **Défaut des appels au centre d’appels** | En voyant mon expérience utilisateur dans une vue entonnoir, je me suis rendu compte que nos utilisateurs étaient en conflit, ce qui entraînait un volume coûteux de centre d’appels. Nous savions où nous concentrer ensuite. | **Réduire l’utilisation du centre d’appels.** Obtenez plus d’expériences utilisateur de &quot;chemin d’accès heureux&quot; et réduisez les appels coûteux. | [Vue Friction](types/friction.md) <p/><p/> [Vue Tendances des conversions](types/conversion-trends.md) |

{style="table-layout:auto"}

![Vue de la friction pour le voyage et l&#39;hospitalité](assets/th-funnel-friction.png)

![Vue d’utilisation des voyages et de l’hospitalité](assets/th-trends-usage.png)

![Tendances des conversions pour les voyages et l’hospitalité](assets/th-funnel-conversion-trends.png)

+++

+++**Médias et divertissement**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Identifier le risque d’attrition** | Nous avons constaté un taux de rotation élevé de clients qui se sont inscrits pour notre plateforme pour assister à un événement saisonnier, puis ont été annulés dès la fin de l&#39;événement. L’identification rapide de ces utilisateurs nous permet d’afficher des recommandations qui les incitent à rester impliqués dans la plateforme. | **Conserver les abonnés heureux.** Recherchez le contenu qui engage un segment de croissance pour interagir avec les recommandations. | [Principale vue de croissance des utilisateurs](types/active.md) <p/><p/> [Vue de la croissance nette](types/net-growth.md) |
| **Trouver des opportunités de vente incitative** | Jey, à cause de la croissance de nos recettes, est en mesure de comprendre ce qui séduit le plus nos fans dans les applications lorsqu&#39;ils sont au stade. | **Augmenter les recettes accessoires.** Comprendre l’impact des offres in-app sur la conduite des achats. | [Première utilisation](types/first-use.md) <p/><p/> [Vue Friction](types/friction.md) |
| **Optimisation de l’expérience multi-appareils** | Je souhaite pouvoir analyser la manière dont mes abonnés interagissent avec plusieurs appareils/applications afin de comprendre les schémas de consommation de contenu et de déterminer où il serait préférable de leur recibler. | **Personnalisez l’expérience.** Identifiez le contenu le mieux adapté aux abonnés sur chaque appareil. | [Affichage des tendances d’utilisation](types/usage.md) |
| **Défaut des appels au centre d’appels** | J’ai pu identifier un problème en raison duquel notre fonction d’automatisation ne fonctionnait pas, ce qui a conduit des clients frustrés à appeler notre centre d’assistance pour annuler leur plan. | **Réduction des appels à l’assistance.** Créez une meilleure expérience client et réduisez les appels au service client. | [Vue Friction](types/friction.md) <p/><p/> [Vue Tendances des conversions](types/conversion-trends.md) |

{style="table-layout:auto"}

![Mode Friction pour les médias et le divertissement](assets/me-funnel-friction.png)

![Principale vue sur les médias et le divertissement](assets/me-user-growth-active.png)

![](assets/me-trends-usage.png)

+++

+++**Soins de santé**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Améliorer les résultats de santé des patients** | Je n&#39;avais pas une idée claire du nombre de participants au plan de bien-être par semaine qui ont simplement cessé de l&#39;utiliser. Nous avons maintenant des données pour concentrer nos efforts sur la croissance. | **Réduire les visites de médecins.** Utilisateurs latents rapidement identifiés pour le réengagement. | [Principales vues de croissance des utilisateurs](types/active.md) |
| **Amélioration de l’expérience du patient** | Avoir une visibilité directe sur le nombre de patients qui appelaient nos centres d&#39;appels pour un simple réinitialisation de mot de passe a renouvelé ma passion d&#39;être concentré au laser sur la réduction du coût global de service de notre entreprise et le renforcement de notre expérience de patient. | **Réduisez le coût global de la diffusion.** Créez une meilleure expérience du patient et réduisez les appels aux services du patient. | [Affichage des tendances d’utilisation](types/usage.md) <p/><p/> [Vue Friction](types/friction.md) |
| **Identification des actions cross-canal répétées par segment** | Je dois comprendre à quel point les membres éligibles à l&#39;assurance-maladie sont principaux avec l&#39;utilisation de leur plan pour leur fournir des messages spécifiques dans nos produits numériques. Les signaux de produit permettent de rendre notre marketing plus efficace. | **Personnalisez les choix d’inscription à Medicare.** Comparez les actions séquentielles courantes de mes membres les plus principaux. | [Vue Friction](types/friction.md) <p/><p/> [Principale vue de croissance des utilisateurs](types/active.md) |
| **Conserver les meilleurs talents du secteur** | Nos ressources d’analyse sont tellement limitées dans le temps. Je dois obtenir rapidement les données d’utilisation des produits dont j’ai besoin pour mes appels de mise à jour de gestion. | **Réduisez la charge de travail des analystes.** Obtenez des réponses plus rapidement. Création de rapports approchables pour le moment où j’en ai le plus besoin. | [Analyse guidée](overview.md) |

{style="table-layout:auto"}

![Vue Friction pour le système de santé](assets/healthcare-funnel-friction.png)

+++

+++**Haute technologie et B2B**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouvelles fonctionnalités** | Nous pourrions analyser la hausse de l’utilisation d’une nouvelle fonctionnalité de produit et déterminer les segments qui fonctionnaient le mieux. Cela nous a aidés à hiérarchiser les ressources que nous dépensons pour optimiser l’engagement des utilisateurs et renforcer notre partenariat avec le marketing. | **Définition des priorités basée sur les données.** Prendre des décisions éclairées sur l’allocation des ressources. | [Vue d’impact des versions](types/release.md) <p/><p/> [Première utilisation](types/first-use.md) |
| **Identifier les rôles qui sous-utilisent le produit** | Notre produit est conçu pour être utilisé par des ingénieurs, des responsables de produits et des responsables marketing. Les analyses ont montré que, alors que les PM et les marketeurs l&#39;utilisaient presque quotidiennement, le personnel de l&#39;ingénierie ne l&#39;avait en grande partie pas adoptée. | **Développer l’adoption des produits.** Identifiez rapidement le comportement des utilisateurs de différentes manières. | [Principale vue de croissance des utilisateurs](types/active.md) <p/><p/> [Vue de la croissance nette](types/net-growth.md) |
| **Suppression des points de friction dans le processus de conversion** | Les données utilisateur montraient qu’une exigence d’un numéro de bon de commande dans notre flux d’achat empêchait les utilisateurs qui préféraient acheter avec une carte de crédit d’exécuter leurs commandes. En rendant ce champ facultatif, les conversions augmentent. | **Améliorez l’expérience client.** Réduire le risque de perte de clientèle. | [Vue Friction](types/friction.md) <p/><p/> [Vue Tendances des conversions](types/conversion-trends.md) |
| **Déverrouiller l’analyse en libre-service** | Tenter d’accéder à des informations est difficile et nos utilisateurs ne sont pas formés à l’analyse. Ils doivent être en mesure d’obtenir des réponses et d’exploiter les mêmes données que celles utilisées par l’ensemble de l’organisation, ce qui conduit à des partenariats plus solides et permet de réelles décisions basées sur les données. | **Des partenariats plus étroits à l’échelle de l’organisation.** Donnez aux responsables de produits l’accès aux données précédemment cloisonnées. | [Analyse guidée](overview.md) |

{style="table-layout:auto"}

![Affichage de l’utilisation pour B2B](assets/b2b-trends-usage.png)

+++
