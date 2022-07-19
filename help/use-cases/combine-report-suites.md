---
title: 'Combinaison de suites de rapports avec différents schémas '
description: Découvrez comment utiliser la préparation de données pour combiner des suites de rapports avec différents schémas
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: ht
source-wordcount: '1335'
ht-degree: 100%

---

# Combinaison de suites de rapports avec différents schémas 

Le [connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) injecte les données des suites de rapports d’Adobe Analytics dans Adobe Experience Platform (AEP) pour qu’elles soient utilisées par les applications AEP telles que Real-time Customer Data Platform et Customer Journey Analytics (CJA). Chaque suite de rapports importée dans AEP est configurée en tant que flux de données de connexion source individuel, et chaque flux de données intègre le lac de données AEP sous forme de jeu de données. Le connecteur source Analytics crée un jeu de données par suite de rapports.

Les clients CJA utilisent des [connexions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr) pour injecter des jeux de données provenant du lac de données AEP dans Analysis Workspace de CJA. Cependant, les différences de schémas entre les suites de rapports apparaissant lors de la combinaison de suites de rapports au sein d’une connexion doivent être résolues à l’aide de la fonctionnalité [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) d’AEP. L’objectif est de s’assurer que la signification des variables Adobe Analytics comme les props et les eVars reste cohérente dans CJA.

## Les différences de schémas entre les suites de rapports posent problème.

Supposons que votre société souhaite importer les données de deux suites de rapports différentes dans AEP pour être utilisées par CJA et que les schémas des deux suites de rapports présentent des différences :

| Suite de rapports A | Suite de rapports B |
| --- | --- |
| eVar1 = terme de recherche | eVar1 = unité opérationnelle |
| eVar2 = catégorie de clients | eVar2 = terme de recherche |

Par souci de simplicité, supposons qu’il s’agisse des seules eVars définies pour les deux suites de rapports.

Supposons également que vous réalisiez les actions suivantes :

- Création d’une connexion source Analytics (sans utiliser la fonction de préparation des données) qui ingère la **suite de rapports A** dans le lac de données AEP sous la forme **jeu de données A**.
- Création d’une connexion source Analytics (sans utiliser la fonction de préparation des données) qui ingère la **suite de rapports B** dans le lac de données AEP sous la forme **jeu de données B**.
- Création d’une [connexion CJA](/help/connections/create-connection.md) appelée **Toutes les suites de rapports** qui combine les jeux de données A et B.
- Création d’une [vue de données CJA](/help/data-views/create-dataview.md) appelée **Vue globale** qui repose sur la connexion Toutes les suites de rapports.

Sans utiliser la fonctionnalité de préparation des données pour résoudre les différences de schéma entre les jeux de données A et B, les eVars de la vue de données Vue globale mélangeront les valeurs :

| Vue de données Vue globale dans CJA |
| --- |
| eVar1 => mélange de termes de recherche et d’unités opérationnelles |
| eVar2 => mélange de catégories de clients et de termes de recherche |

Cette situation génère des rapports dénués de sens pour l’eVar1 et l’eVar2 :

- les champs d’eVar mélangent des valeurs aux significations sémantiques différentes.
- Les termes de recherche sont répartis entre l’eVar1 et l’eVar2.
- Il n’est pas possible d’utiliser différents modèles d’attribution pour chaque terme de recherche, chaque unité opérationnelle et chaque catégorie de clients.

## Utilisation de la fonctionnalité de préparation de données d’AEP pour résoudre les différences de schémas entre les suites de rapports

La fonctionnalité Préparation des données d’Experience Platform est intégrée au connecteur source Analytics et peut être utilisée pour résoudre les différences de schéma décrites dans le scénario ci-dessus. Cela se traduit par des eVars à la signification cohérente dans la vue de données CJA. (Les conventions d’appellation utilisées ci-dessous peuvent être personnalisées selon vos besoins.)

1. Avant de créer les flux de données de connexion source pour les suites de rapports A et B, [créez un nouveau schéma](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr) dans AEP (nous l’appellerons **Schéma unifié** dans notre exemple.) Ajoutez les éléments suivants au schéma :

   | « Schéma unifié » |
   | --- |
   | Classe **XDM ExperienceEvent** |
   | Groupe de champs **Modèle d’événement d’expérience Adobe Analytics** |

1. Ajoutez un autre groupe de champs au schéma ou [créez un groupe de champs personnalisé](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=fr#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) et ajoutez-le au schéma. Nous créerons un nouveau groupe de champs et l’appellerons **Champs unifiés**. Nous ajouterons ensuite les champs suivants au nouveau groupe de champs :

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

1. Créez maintenant une connexion **Toutes les suites de rapports** pour CJA, en combinant les jeux de données A et B.

1. Créez une vue de données **Vue globale** dans CJA. Ignorez les champs eVar d’origine et incluez uniquement les champs du groupe de champs Champs unifiés.

   Vue de données **Vue globale** dans CJA :

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

1. Créez un schéma dans AEP. Ajoutez les éléments suivants au schéma :

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

1. Créez une connexion CJA qui combine les jeux de données A et B.

1. Créez une vue de données dans CJA à l’aide de la connexion CJA que vous venez de créer. Ignorez les champs eVar d’origine et incluez uniquement les champs du groupe de champs Informations de clients.

   Vue de données dans CJA :

   | Champ source | Inclure dans la vue de données ? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Non |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Non |
   | _\&lt;path>_.Customer_category | Oui |

## Préparation des données et ID de composant

Comme décrit ci-dessus, la préparation de données vous permet de mapper différents champs dans plusieurs suites de rapports Adobe Analytics. Ceci est très utile dans CJA lorsque vous souhaitez combiner des données provenant de plusieurs jeux de données et former une seule connexion CJA. Cependant, si vous avez l’intention de conserver les suites de rapports dans des connexions CJA distinctes mais que vous souhaitez utiliser un ensemble de rapports dans ces connexions et vues de données, vous pouvez modifier l’ID de composant sous-jacent dans CJA afin de rendre les rapports compatibles même si les schémas sont différents. Consultez les [Paramètres de composant](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=fr) pour en savoir plus.

La modification de l’ID de composant est une fonction unique à CJA qui n’a aucune incidence sur les données du connecteur source Analytics envoyées au profil client en temps réel et à RTCDP.
