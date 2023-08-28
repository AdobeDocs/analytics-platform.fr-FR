---
title: Cas pratiques du secteur
description: Cas d’utilisation du secteur pour l’analyse guidée
feature: Guided Analysis
keywords: analytics du produit
source-git-commit: 4aed07568d345770183d18041a762adc441e6bc3
workflow-type: tm+mt
source-wordcount: '1483'
ht-degree: 2%

---

# Cas pratiques du secteur

Les cas d’utilisation des analyses guidées varient selon le secteur d’activité. Cette page fournit des exemples illustratifs de ce que les équipes produit peuvent accomplir avec les fonctionnalités d’analyse guidée et d’Adobe Product Analytics.

+++**Vente au détail**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Optimisation de l’application d’achat mobile** | De nombreux clients ont téléchargé l’application mobile d’une entreprise, mais ne sont jamais revenus. La société constate que les clients l’utilisent uniquement pour l’offre initiale. Ils ont réengagé ces clients endormis. | **Augmentez le nombre de LTV des utilisateurs mobiles.** Mesurez et augmentez l’utilisation de l’application afin de développer une expérience utilisateur plus &quot;happy path&quot;. | [Vue de croissance des utilisateurs actifs](types/active.md)<br>[Vue de la croissance nette](types/net-growth.md) |
| **Quantifier l’impact des nouvelles fonctionnalités de passage en caisse** | Une épicerie passe des tests pour faire des achats en ligne. Ils mesurent rapidement l’impact des nouvelles fonctionnalités de passage en caisse, telles que les recommandations de produits ou le passage en caisse. | **Augmentez les taux de conversion.** Mesurez l’impact sur l’entreprise au lieu de simplement utiliser les fonctionnalités. | [Vue d’impact des versions](types/release.md)<br>[Première utilisation vue](types/first-use.md) |
| **Réduction du taux d’adhésion** | Une organisation détecte les points de friction dans les parcours client qui provoquent la perte de clientèle. Il leur permet de passer en revue les programmes d’adhésion et d’analyser les comportements des membres à risque. | **Réduire le taux de perte de clientèle.** Identifier les moyens de favoriser et d’entretenir les relations avec les clients afin d’éviter l’attrition et de réduire le taux d’attrition. | [Vue de croissance des utilisateurs actifs](types/active.md)<br>[Vue Friction](types/friction.md) |
| **Rechercher les parcours de vente inefficaces** | Une organisation détecte les inefficacités dans le parcours des associés de vente en magasin où ils sont retirés des clients. Ils adaptent leur processus, ce qui donne aux clients une expérience d’achat plus agréable en magasin. | **Améliorez la réponse des ventes.** Réduisez les processus inefficaces, qui se traduisent par de meilleurs parcours internes et une expérience client positive. | [Vue Friction](types/friction.md) |

{style="table-layout:auto"}

![Vue Friction pour la vente au détail](assets/retail-funnel-friction.png)

![Vue Utilisation pour la vente au détail](assets/retail-trends-usage.png)

+++

+++**Services financiers**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouvelles fonctionnalités** | Une institution financière déploie les transferts bancaires avec Zelle et veut comprendre l&#39;impact de la nouvelle fonctionnalité sur la conclusion des transferts. L’analyse guidée leur permet de voir comment les clients réagissent afin que l’équipe marketing puisse la déployer. | **Augmentez les taux de conversion.** Mesurez l’impact des nouvelles fonctionnalités sur les conversions de transfert. | [Vue d’impact des versions](types/release.md)<br>[Première utilisation vue](types/first-use.md) |
| **Défaut des appels au centre d’appels** | Une analyse guidée révèle que le processus de demande mobile en cinq étapes d’une organisation entraîne les appels vers son centre d’appels. Ils créent une audience et envoient un email à ces clients afin de mieux comprendre leur expérience. | **Isolez la friction dans l&#39;expérience.** Améliorez les parcours &quot;happy path&quot; et réduisez les appels. | [Vue Friction](types/friction.md)<br>[Affichage des tendances de conversion](types/conversion-trends.md) |
| **Réduction du taux de perte de clientèle** | Une organisation apprend que les clients qui se connectent à l’application mobile bancaire à fréquence mensuelle restent des clients plus longtemps. L’analyse guidée leur permet d’identifier les personnes à risque et de créer une stratégie de retour arrière. | **Réduire le taux de perte de clientèle.** Maintenir le niveau des clients tout en dépensant pour acquérir de nouveaux clients réels. | [Vue de croissance des utilisateurs actifs](types/active.md)<br>[Vue de la croissance nette](types/net-growth.md) |
| **Nouvelles fonctionnalités recommandées** | Une organisation remarque que les retraits numériques ont diminué au cours des derniers mois. Le nombre d&#39;appels à un conseiller financier a augmenté. L’analyse guidée permet à l’entreprise de hiérarchiser les optimisations des processus numériques avec un comité de pilotage. | **Créez une feuille de route axée sur les données.** Utilisez les données pour planifier et mettre en oeuvre des optimisations. | [Affichage des tendances d’utilisation](types/usage.md) |

{style="table-layout:auto"}

![Vue de fragment pour les services financiers](assets/fsi-funnel-friction.png)

![Affichage de l’utilisation pour les services financiers](assets/fsi-trends-usage.png)

![Vue active pour les services financiers](assets/fsi-user-growth-active.png)

+++

+++**Voyage et hébergement**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouvelles fonctionnalités de flux de réservation** | Une entreprise utilise l’analyse guidée pour afficher rapidement l’impact d’une nouvelle fonction d’étape de réservation sur les taux de conversion. Ils identifient la partie de l’expérience avec les plus gros gains. | **Augmentez les tarifs des réservations.** Mesurez l’impact sur l’entreprise au lieu de simplement utiliser les fonctionnalités. | [Vue d’impact des versions](types/release.md)<br>[Vue Friction](types/friction.md) |
| **Optimisation de l’expérience des applications mobiles** | Une entreprise comprend rapidement et facilement les utilisateurs mensuels actifs de l’application au fil du temps et identifie l’impact positif par version. | **Augmentez les MTA.** Mesurez et augmentez l’utilisation de l’application, ce qui correspond au bonheur des clients. | [Vue de croissance des utilisateurs actifs](types/active.md)<br>[Vue de la croissance nette](types/net-growth.md) |
| **Trouver des frictions dans le flux d&#39;archivage mobile** | En voyant où les personnes réussissent ou abandonnent le processus d’archivage mobile attendu, une entreprise peut facilement identifier les zones à optimiser l’expérience. | **Augmentez le CSAT et réduisez les IROP.** La suppression de la friction entraîne une expérience de &quot;jour de voyage&quot; plus transparente. | [Vue Friction](types/friction.md)<br>[Affichage des tendances de conversion](types/conversion-trends.md) |
| **Défaut des appels au centre d’appels** | L’affichage de l’expérience utilisateur dans une vue entonnoir indique un utilisateur pour lequel les visiteurs affrontent des frictions, ce qui entraîne un volume coûteux de centre d’appels. Les prochaines étapes sur lesquelles se concentrer sont claires. | **Réduisez l’utilisation du centre d’appel.** Obtenez plus d’expériences utilisateur de &quot;chemin d’accès heureux&quot; et réduisez les appels coûteux. | [Vue Friction](types/friction.md)<br>[Affichage des tendances de conversion](types/conversion-trends.md) |

{style="table-layout:auto"}

![Vue de la friction pour le voyage et l&#39;hospitalité](assets/th-funnel-friction.png)

![Vue d’utilisation des voyages et de l’hospitalité](assets/th-trends-usage.png)

![Tendances des conversions pour les voyages et l’hospitalité](assets/th-funnel-conversion-trends.png)

+++

+++**Médias et divertissement**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouveaux programmes ou séries** | Un service de diffusion en continu peut analyser l’effet sur l’audience après que les utilisateurs ont regardé une nouvelle série ou série d’émissions et mieux comprendre le contenu qui y résonne. | **Augmentez l’audience.** Trouvez le contenu qui a le plus grand impact sur l’audience. | [Première utilisation vue](types/first-use.md) |
| **Identifier le risque d’attrition** | Une entreprise enregistre un taux de rotation élevé de clients qui s’inscrivent à leur plateforme pour assister à un événement saisonnier et annuler immédiatement une fois l’événement terminé. L’identification rapide de ces utilisateurs leur permet d’afficher des recommandations qui incitent les clients à rester impliqués dans la plateforme. | **Conserver les abonnés heureux.** Recherchez le contenu qui engage un segment de croissance pour interagir avec les recommandations. | [Vue de croissance des utilisateurs actifs](types/active.md)<br>[Vue de la croissance nette](types/net-growth.md) |
| **Trouver des opportunités de vente incitative** | Pour accroître les recettes d’une entreprise, il est essentiel de comprendre les offres in-app les plus attrayantes pour les fans lorsqu’ils sont au stade. L’analyse guidée leur permet de déterminer exactement les offres les plus efficaces. | **Augmenter les recettes accessoires.** Comprendre l’impact des offres in-app sur la conduite des achats. | [Première utilisation vue](types/first-use.md)<br>[Vue Friction](types/friction.md) |
| **Optimisation de l’expérience multi-appareils** | Une entreprise souhaite analyser la manière dont les abonnés interagissent avec plusieurs appareils/applications. Ces connaissances leur permettent de comprendre les schémas de consommation de contenu et de déterminer où se recibler le mieux pour eux. | **Personnalisez l’expérience.** Identifiez le contenu le mieux adapté aux abonnés sur chaque appareil. | [Affichage des tendances d’utilisation](types/usage.md) |
| **Défaut des appels au centre d’appels** | Une organisation utilise l’analyse guidée pour identifier un problème en raison duquel l’automopay ne fonctionnait pas, ce qui a amené les clients frustrés à appeler leur centre d’assistance pour annuler leur plan. | **Réduction des appels à l’assistance.** Créez une meilleure expérience client et réduisez les appels au service client. | [Vue Friction](types/friction.md)<br>[Affichage des tendances de conversion](types/conversion-trends.md) |

{style="table-layout:auto"}

![Mode Friction pour les médias et le divertissement](assets/me-funnel-friction.png)

![Vue active pour les médias et le divertissement](assets/me-user-growth-active.png)

![](assets/me-trends-usage.png)

+++

+++**Soins de santé**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Améliorer les résultats de santé des patients** | Une organisation dispose des données pour concentrer ses efforts sur la croissance. Avant d&#39;utiliser l&#39;analyse guidée, ils ne comprenaient pas clairement combien de membres du plan de bien-être par semaine cessaient simplement de l&#39;utiliser. | **Réduire les visites de médecins.** Utilisateurs latents rapidement identifiés pour le réengagement. | [Vues de croissance des utilisateurs actifs](types/active.md) |
| **Amélioration de l’expérience du patient** | La visibilité sur le nombre de patients contactés par les centres d&#39;appels pour un simple mot de passe a permis de réinitialiser la passion d&#39;un analyste de se concentrer au laser sur le renforcement de l&#39;expérience de ses patients. | **Réduisez le coût global de la diffusion.** Créez une meilleure expérience du patient et réduisez les appels aux services du patient. | [Affichage des tendances d’utilisation](types/usage.md)<br>[Vue Friction](types/friction.md) |
| **Identification des actions cross-canal répétées par segment** | Une organisation veut comprendre l’activité des membres éligibles à Medicare avec l’utilisation de leur plan pour leur fournir des messages spécifiques dans leurs produits numériques. Les connaissances acquises grâce aux analyses guidées permettent de rendre le marketing plus efficace. | **Personnalisez les choix d’inscription à Medicare.** Comparez les actions séquentielles courantes des membres de mon plan le plus actif. | [Vue Friction](types/friction.md)<br>[Vue de croissance des utilisateurs actifs](types/active.md) |
| **Conserver les meilleurs talents du secteur** | Les ressources Analytics d’une organisation sont limitées pendant un certain temps. L’analyse guidée permet à l’entreprise d’obtenir rapidement les données d’utilisation des produits nécessaires aux appels de mise à jour de gestion. | **Réduisez la charge de travail des analystes.** Obtenez des réponses plus rapidement. Création de rapports approchables pour les cas les plus cruciaux. | [Analyse guidée](overview.md) |

{style="table-layout:auto"}

![Vue Friction pour le système de santé](assets/healthcare-funnel-friction.png)

+++

+++**Haute technologie et B2B**

| Cas d’utilisation | Exemple | Impact | Analyse |
| --- | --- | --- | --- |
| **Quantifier l’impact des nouvelles fonctionnalités** | Une entreprise peut analyser la hausse de l’utilisation d’une nouvelle fonction de produit et déterminer les segments qui fonctionnent le mieux. Cette analyse les aide à hiérarchiser les ressources à allouer afin d’optimiser l’engagement des utilisateurs et de renforcer leur partenariat avec le marketing. | **Définition des priorités basée sur les données.** Prendre des décisions éclairées sur l’allocation des ressources. | [Vue d’impact des versions](types/release.md)<br>[Première utilisation vue](types/first-use.md) |
| **Identifier les rôles qui sous-utilisent le produit** | Une organisation crée un produit à utiliser par des ingénieurs, des responsables de produits et du marketing. L’analyse guidée a montré que, bien que les chefs de produits et les spécialistes du marketing l’utilisent presque quotidiennement, le personnel de l’ingénierie ne l’adoptait pas dans la plupart des cas. | **Développer l’adoption des produits.** Identifiez rapidement le comportement des utilisateurs de différentes manières. | [Vue de croissance des utilisateurs actifs](types/active.md)<br>[Vue de la croissance nette](types/net-growth.md) |
| **Suppression des points de friction dans le processus de conversion** | L’exigence d’un numéro de bon de commande dans le flux d’achat empêche les utilisateurs qui préfèrent les cartes de crédit d’exécuter leurs commandes. Les conversions ont augmenté lorsque ce champ est devenu facultatif. | **Améliorer l’expérience client** Réduire le risque de perte de clientèle. | [Vue Friction](types/friction.md)<br>[Affichage des tendances de conversion](types/conversion-trends.md) |
| **Déverrouiller l’analyse en libre-service** | L’accès aux informations est un défi, et certains utilisateurs d’une entreprise ne sont pas formés à l’analyse. L’analyse guidée leur permet d’obtenir des réponses et d’exploiter les mêmes données que le reste de l’organisation, ce qui entraîne des partenariats plus solides et permet de prendre de vraies décisions fondées sur les données. | **Des partenariats plus étroits à l’échelle de l’organisation.** Donnez aux responsables de produits l’accès aux données précédemment cloisonnées. | [Analyse guidée](overview.md) |

{style="table-layout:auto"}

![Affichage de l’utilisation pour B2B](assets/b2b-trends-usage.png)

+++
