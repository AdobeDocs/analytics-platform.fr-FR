---
title: Combinaison de suites de rapports avec différents schémas
description: Découvrez comment utiliser la préparation de données pour combiner des suites de rapports avec différents schémas
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 57%

---

# Combinaison de suites de rapports avec différents schémas 

Le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) apporte des données de suite de rapports d’Adobe Analytics dans Adobe Experience Platform pour une utilisation par les applications Adobe Experience Platform, telles que Real-time Customer Data Platform et Customer Journey Analytics (Customer Journey Analytics). Chaque suite de rapports intégrée à Adobe Experience Platform est configurée en tant que flux de données de connexion source individuel et chaque flux de données est associé à un jeu de données dans le lac de données Adobe Experience Platform. Le connecteur source Analytics crée un jeu de données par suite de rapports.

Les clients Customer Journey Analytics utilisent [connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr) pour intégrer des jeux de données du lac de données Adobe Experience Platform dans Customer Journey Analytics Analysis Workspace. Cependant, lors de la combinaison de suites de rapports au sein d’une connexion, les différences de schémas entre les suites de rapports doivent être résolues à l’aide de la fonctionnalité Adobe Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html). L’objectif est de s’assurer que les variables Adobe Analytics telles que les props et les eVars ont une signification cohérente dans Customer Journey Analytics.

## Les différences de schémas entre les suites de rapports posent problème.

Supposons que votre société souhaite importer les données de deux suites de rapports différentes dans Adobe Experience Platform pour les utiliser par Customer Journey Analytics et que les schémas des deux suites de rapports présentent des différences :

| Suite de rapports A | Suite de rapports B |
| --- | --- |
| eVar1 = terme de recherche | eVar1 = unité opérationnelle |
| eVar2 = catégorie de clients | eVar2 = terme de recherche |

Par souci de simplicité, supposons qu’il s’agisse des seules eVars définies pour les deux suites de rapports.

Supposons également que vous réalisiez les actions suivantes :

- Créez une connexion source Analytics (sans utiliser de préparation de données) qui ingère **Report Suite A** dans le lac de données Adobe Experience Platform en tant que **jeu de données A**.
- Créez une connexion source Analytics (sans utiliser de préparation de données) qui ingère **Report Suite B** dans le lac de données Adobe Experience Platform en tant que **jeu de données B**.
- Créez une [connexion de Customer Journey Analytics](/help/connections/create-connection.md) appelée **Toutes les suites de rapports** qui combine le jeu de données A et le jeu de données B.
- Créez une [ vue de données de Customer Journey Analytics ](/help/data-views/create-dataview.md) appelée **vue globale** basée sur la connexion Toutes les suites de rapports.

Sans utiliser la fonctionnalité de préparation des données pour résoudre les différences de schéma entre les jeux de données A et B, les eVars de la vue de données Vue globale mélangeront les valeurs :

| Vue globale des données dans Customer Journey Analytics |
| --- |
| eVar1 => mélange de termes de recherche et d’unités opérationnelles |
| eVar2 => mélange de catégories de clients et de termes de recherche |

Cette situation génère des rapports dénués de sens pour l’eVar1 et l’eVar2 :

- les champs d’eVar mélangent des valeurs aux significations sémantiques différentes.
- Les termes de recherche sont répartis entre l’eVar1 et l’eVar2.
- Il n’est pas possible d’utiliser différents modèles d’attribution pour chaque terme de recherche, chaque unité opérationnelle et chaque catégorie de clients.

## Utilisation de Adobe Experience Platform Data Prep pour résoudre les différences de schémas entre les suites de rapports

La fonctionnalité de préparation des données Experience Platform est intégrée au connecteur source Analytics et peut être utilisée pour résoudre les différences de schéma décrites dans le scénario ci-dessus. Cela se traduit par des eVars ayant des significations cohérentes dans la vue de données du Customer Journey Analytics. (Les conventions d’appellation utilisées ci-dessous peuvent être personnalisées selon vos besoins.)

1. Avant de créer les flux de données de connexion source pour la suite de rapports A et la suite de rapports B, [Créez un nouveau schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr) dans Adobe Experience Platform (nous l’appellerons **Schéma unifié** dans notre exemple). Ajoutez les éléments suivants au schéma :

   | « Schéma unifié » |
   | --- |
   | Classe **XDM ExperienceEvent** |
   | Groupe de champs **Modèle d’événement d’expérience Adobe Analytics** |

1. Ajoutez un autre groupe de champs au schéma ou [créez un groupe de champs personnalisé](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) et ajoutez-le au schéma. Nous créerons un nouveau groupe de champs et l’appellerons **Champs unifiés**. Nous ajouterons ensuite les champs suivants au nouveau groupe de champs :

   | Groupe de champs personnalisés « Champs unifiés »  |
   | --- |
   | Terme de recherche |
   | Unité opérationnelle |
   | Catégorie de clients |

1. Créez le flux de données de connexion source pour la **suite de rapports A** en sélectionnant le **Schéma unifié** à utiliser dans le flux de données. Ajoutez des mappages personnalisés au flux de données comme suit :

   | Champ source de la suite de rapports A | Champ de destination du groupe de champs Champs unifiés |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >Le chemin d’accès XDM pour vos champs de destination dépend de la structure de votre groupe de champs personnalisés.

1. Créez le flux de données de connexion source pour la **suite de rapports B** en sélectionnant de nouveau le **Schéma unifié** à utiliser dans le flux de données. Le workflow indiquera que deux champs entrent en conflit à cause de leur nom de descripteur. En effet, les descripteurs d’eVar1 et d’eVar2 dans la suite de rapports B diffèrent de ceux dans la suite de rapports A. Mais nous le savons déjà, et nous pouvons donc ignorer le conflit sans risque et utiliser des mappages personnalisés comme suit :

   | Champ source de la suite de rapports B | Champ de destination du groupe de champs Champs unifiés |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Créez maintenant une connexion **Toutes les suites de rapports** pour Customer Journey Analytics, en combinant le jeu de données A et le jeu de données B.

1. Créez une vue de données **vue globale** dans Customer Journey Analytics. Ignorez les champs eVar d’origine et incluez uniquement les champs du groupe de champs Champs unifiés.

   **Vue globale** vue de données en Customer Journey Analytics :

   | Champ source | Inclure dans la vue de données ? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | Non |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Non |
   | _\&lt;path>_.Search_term | Oui |
   | _\&lt;path>_.Customer_category  | Oui |
   | _\&lt;path>_.Business_unit | Oui |

Vous avez désormais mappé eVar1 et eVar2 depuis les suites de rapports sources à trois nouveaux champs. Notez qu’un autre avantage de l’utilisation des mappages de préparation de données est que les champs de destination reposent désormais sur des noms ayant une signification sémantique (terme de recherche, unité opérationnelle, catégorie client) qui remplacent les noms d’eVar moins significatifs (eVar1, eVar2).

>[!NOTE]
>
>Le groupe de champs personnalisés Champs unifiés et les mappages de champs associés peuvent être ajoutés à tout moment aux flux de données et aux jeux de données du connecteur source Analytics existants. Cependant, cet ajout n’aura une incidence que sur les données à venir.

## Plus que de simples suites de rapports

Les possibilités offertes par l’utilisation de la fonctionnalité de préparation des données pour combiner des jeux de données avec différents schémas vont au-delà des suites de rapports Analytics. Supposons que vous ayez deux jeux de données contenant les données suivantes :

| Jeu de données A = suite de rapports Analytics via le connecteur source Analytics |
| --- |
| `eVar1` => catégorie de clients |

| Jeu de données B = données du centre d’appel |
| --- |
| Some_field => catégorie de clients |

À l’aide de la préparation des données, vous pouvez combiner la catégorie de clients d’eVar 1 dans les données Analytics à la catégorie de clients du champ Some_field des données du centre d’appel. Voici une manière d’effectuer cette opération. Là encore, la convention d’appellation peut être modifiée selon vos besoins.

1. Créez un schéma dans Adobe Experience Platform. Ajoutez les éléments suivants au schéma :

   | « Schéma étendu » |
   | --- | 
   | Classe **Événement d’expérience XDM** |
   | Groupe de champs **Modèle d’événement d’expérience Adobe Analytics** |

1. Créez un nouveau groupe de champs et ajoutez-le au schéma. Ajoutez des champs au groupe de champs :

   | Groupe de champs personnalisés « Informations de clients »  |
   | --- |
   | Customer_category |

1. Créez le flux de données pour le **jeu de données A** en sélectionnant le **Schéma étendu** comme schéma. Ajoutez des mappages personnalisés au flux de données comme suit :

   | Champ source du jeu de données A | Champ de destination du groupe de champs Informations de clients |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Créez le flux de données pour le **jeu de données B** en sélectionnant de nouveau le **Schéma étendu** comme schéma. Ajoutez des mappages personnalisés au flux de données comme suit :

   | Champ source du jeu de données B | Champ de destination du groupe de champs Informations de clients |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. Créez une connexion de Customer Journey Analytics qui combine le jeu de données A et le jeu de données B.

1. Créez une vue de données dans Customer Journey Analytics à l’aide de la connexion de Customer Journey Analytics que vous venez de créer. Ignorez les champs eVar d’origine et incluez uniquement les champs du groupe de champs Informations de clients.

   Vue des données en Customer Journey Analytics :

   | Champ source | Inclure dans la vue de données ? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Non |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Non |
   | _\&lt;path>_.Customer_category | Oui |

## Préparation des données et ID de composant

Comme décrit ci-dessus, la préparation de données vous permet de mapper différents champs dans plusieurs suites de rapports Adobe Analytics. Cela s’avère utile dans Customer Journey Analytics lorsque vous souhaitez combiner des données provenant de plusieurs jeux de données en une seule connexion de Customer Journey Analytics. Cependant, si vous avez l’intention de conserver les suites de rapports dans des connexions de Customer Journey Analytics distinctes mais que vous souhaitez utiliser un jeu de rapports pour ces connexions et vues de données, la modification de l’identifiant de composant sous-jacent dans Customer Journey Analytics permet de rendre les rapports compatibles même si les schémas sont différents. Consultez les [Paramètres de composant](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html) pour en savoir plus.

La modification de l’identifiant du composant est une fonction réservée aux Customer Journey Analytics. Elle n’a aucune incidence sur les données du connecteur source Analytics qui sont envoyées à Real-time Customer Profile et à la plateforme de données clients en temps réel (RTCDP).
