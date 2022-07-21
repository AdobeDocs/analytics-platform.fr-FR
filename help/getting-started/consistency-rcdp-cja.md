---
description: Explique les facteurs qui influencent la cohérence des mesures entre Real-time Customer Data Platform (plateforme de données clients en temps réel) et CJA.
title: Cohérence des mesures entre la plateforme CDP en temps réel et CJA
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---


# Cohérence des mesures entre la plateforme CDP en temps réel et CJA

Dans les scénarios réels, la cohérence des mesures entre Real-time Customer Data Platform (plateforme de données clients en temps réel) et Customer Journey Analytics (CJA) ne peut pas être garantie. Ce document explique pourquoi.

## CJA n’utilise pas encore le graphique d’identités

La CDP et CJA ne partagent pas la même définition d&#39;une personne aujourd&#39;hui. CJA n’utilise pas encore [Graphique d’identités](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=fr) pour informer sa définition d&#39;une personne. La plateforme des données clients en temps réel repose entièrement sur les informations du graphique d’identités pour créer un profil fusionné.

CJA utilise une méthode appelée [Groupement basé sur les champs](/help/connections/cca/overview.md) qui extrait les identifiants des jeux de données du lac de données et applique une logique personnalisée pour les lier. Dans un futur intermédiaire, CJA devrait commencer à utiliser [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) exporte vers le lac de données, permettant une notion commune de l’identité entre la plateforme de données clients en temps réel et CJA.

>[!IMPORTANT]
>
>Faire de Adobe Experience Platform Identity Service la source d’identité de vérité pour toutes les applications Adobe Experience Platform ne rend pas automatiquement les mesures cohérentes entre les applications. Lisez la suite pour en savoir plus.

## Flexibilité des données d’application

Experience Platform n’applique pas d’application stricte pour conserver les données entre Real-time Customer Profile et Data Lake identiques. Certains cas d’utilisation fonctionnent avec les données dans [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (activation), tandis que d’autres dépendent de la fonction [lac de données](https://business.adobe.com/blog/basics/data-lake) (service de création de rapports et de requêtes).

Les clients CDP en temps réel ne disposent généralement pas de 100 % des données du lac de données Adobe Experience Platform allant dans Profile. Il s’agit d’une opération de conception : les clients doivent activer spécifiquement les données du lac pour Profile. CJA permet aux analystes de données de sélectionner librement les données qu’ils souhaitent importer pour analyse à partir du lac de données, indépendamment de ce qui est activé pour la plateforme de données clients en temps réel.

## Modificateurs spécifiques à l’application

CJA permet une modification complète des données au moment de la requête, par exemple la combinaison de champs, la division des champs entre eux et d’autres manipulations telles que les conversions de devises, la déduplication des valeurs, la sessionisation et le filtrage au niveau des lignes. Ces fonctionnalités ne sont pas disponibles pour la plateforme de données clients.

De même, la plateforme CDP en temps réel s’applique [stratégies de fusion](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) pour déterminer quelles données seront hiérarchisées et quelles données seront combinées afin de créer une vue unifiée d’une personne. Ces configurations s’inscrivent fermement dans la logique de chaque application et ne sont pas partagées.

## Comportement en lecture et en écriture

La plateforme des données clients en temps réel nécessite la combinaison de profils en temps réel à l’aide du dernier graphique d’identifiants.

* La plateforme CDP en temps réel est conçue pour assembler des informations de profil en temps réel en vue de l’activation.

* Il peut prendre en charge en temps réel toutes les modifications apportées aux identifiants définis pour un utilisateur donné.

* L’intervalle de recherche en amont est contrôlé par la définition de segment.

CJA nécessite que les données soient assemblées au moment de l’écriture à l’aide des exportations ID Graph.

* CJA applique des étapes de prétraitement complexes telles que l’indexation, le partage et le regroupement avant que les données ne soient prêtes à être analysées.

* L’identifiant de personne pour un utilisateur donné est une entrée essentielle pour les étapes de prétraitement ; le changement de l’identifiant de personne par la suite a un coût de retraitement important.

* L’intervalle de recherche en amont est contrôlé au niveau de l’application.

## Différences entre la durée de vie et l’ingestion des données

Même si les jeux de données de la plateforme de données clients en temps réel et de CJA sont identiques, la plateforme de données clients en temps réel ne peut conserver qu’une fenêtre d’historique très limitée. En revanche, CJA a probablement des années de données. En outre:

* Les clients CJA et CDP en temps réel peuvent définir des fenêtres de conservation personnalisées pour les données, indépendamment les uns des autres.

* La plateforme CDP en temps réel et CJA ont une logique différente pour l’ingestion de données. CJA ignore les enregistrements sans ID de personne ou horodatage et a des limites strictes au nombre d’enregistrements qu’un seul profil/personne peut avoir.

* Les clients de la plateforme de données clients en temps réel disposent de 7 jours d’accès aux données du lac, principalement pour faciliter l’intégration des données dans leur profil et pour les requêtes ad hoc.

* Il n’existe pas de TTL pour les données du lac pour les clients de CJA. Toutefois, les utilisateurs de CJA peuvent eux-mêmes définir une fenêtre de rétention personnalisée dans CJA lors de la création d’une connexion.

* Le magasin de profils dans la plateforme de données clients en temps réel permet d’utiliser des TTL configurables par le client. Les clients peuvent modifier ce délai d’activation pour qu’il reste dans les limites de leurs droits de licence.

## Différences dans le traitement en vertu du RGPD (Règlement général sur la protection des données)

La logique de traitement des données pour le RGPD et l’hygiène des données dans la plateforme CDP en temps réel et le lac de données est très différente. Nous travaillons à une approche unique.

## Différences dans la latence d’ingestion des données

La création de rapports CJA inclut une certaine latence avant que les données ne soient disponibles pour la création de rapports ou d’audiences. La plateforme CDP en temps réel traite les données par le biais de différents systèmes présentant une latence différente.