---
source-git-commit: 59bb2c89c964f5b843897c40c38b11ada46f990a
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---
# Combinaison de règles de rapports ayant des schémas différents

## Présentation

Le [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) fournit un moyen d’importer les données de suite de rapports d’Adobe Analytics dans Adobe Experience Platform pour les applications AEP telles que RTCDP et CJA. Chaque suite de rapports importée dans AEP est configurée en tant que flux de données de connexion source individuel, et chaque flux de données est associé à un jeu de données dans le lac de données AEP. (Le connecteur source Analytics crée un jeu de données par suite de rapports.)

Les clients CJA utilisent [connexions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr) pour intégrer des jeux de données du lac de données AEP dans Analysis Workspace de CJA. *Toutefois, lors de la combinaison de suites de rapports au sein d’une connexion, les différences de schémas entre les suites de rapports doivent être résolues à l’aide des [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr) afin de garantir que les variables Adobe Analytics telles que les props et les eVars ont une signification cohérente dans CJA.*

## En quoi les différences de schémas entre les suites de rapports posent problème

Supposons que votre entreprise souhaite importer des données de deux suites de rapports différentes dans AEP pour les utiliser par CJA et que les schémas des deux suites de rapports aient des différences :

| Suite de rapports A | Suite de rapports B |
| --- | --- |
| eVar1 => Terme de recherche | eVar1 => Unité opérationnelle |
| eVar2 => Catégorie de clients | eVar2 => Terme recherché |

Par souci de simplicité, nous vous indiquerons qu’il s’agit des seules eVars définies pour les deux suites de rapports.

En outre, supposons que vous réalisiez les actions suivantes :

- Création d’une connexion source Analytics (sans utilisation de la préparation des données) qui ingère **Suite de rapports A** dans le lac de données AEP sous la forme **Jeu de données A**.
- Création d’une connexion source Analytics (sans utilisation de la préparation des données) qui ingère **Suite de rapports B** dans le lac de données AEP sous la forme **Jeu de données B**.
- Créez une connexion CJA appelée **Toutes les suites de rapports** qui combine le jeu de données A et le jeu de données B.
- Créez une vue de données CJA appelée **Vue globale** qui repose sur la connexion Toutes les suites de rapports.

Sans l’utilisation de Data Prep pour résoudre les différences de schéma entre le jeu de données A et le jeu de données B, les eVars de la vue de données globale contiendront un mélange de valeurs :

| Vue des données de la vue globale dans CJA |
| --- |
| eVar1 => mélange de termes de recherche et d’unités opérationnelles |
| eVar 2 => mélange de catégories de clients et de termes de recherche |

Cette situation aura pour résultat des rapports dénués de sens pour l&#39;eVar1 et l&#39;eVar2 :

- Les champs d’eVar contiendront un mélange de valeurs ayant des significations sémantiques différentes.
- Les termes de recherche seront distribués entre l’eVar1 et l’eVar2.
- Il ne sera pas possible d’utiliser différents modèles d’attribution pour chacun des termes de recherche, des unités opérationnelles et des catégories de clients.

## Utilisation de la préparation de données AEP pour résoudre les différences de schémas entre les suites de rapports à utiliser dans CJA

La fonctionnalité de préparation des données d’AEP est intégrée au connecteur source Analytics et peut être utilisée pour résoudre les différences de schéma décrites dans le scénario ci-dessus, ce qui entraîne des eVars avec des significations cohérentes dans la vue de données CJA. Vous trouverez ci-dessous une description de la manière dont cela pourrait être accompli. Les conventions d’appellation utilisées ci-dessous peuvent être personnalisées selon vos besoins.

Avant de créer les flux de données de connexion source pour la suite de rapports A et la suite de rapports B, créez un groupe de champs personnalisé dans AEP (nous l’appellerons **Champs unifiés** dans notre exemple) qui contient les champs suivants :

| Groupe de champs personnalisés &quot;Champs unifiés&quot;  |
| --- |
| Terme de recherche |
| Unité opérationnelle |
| Catégorie de clients |

Créez un nouveau schéma dans AEP (nous l’appellerons **Schéma unifié** dans notre exemple.) Ajoutez les groupes de champs suivants au schéma :

| Groupes de champs pour &quot;Schéma unifié&quot; |
| --- |
| Événement d’expérience XDM |
| Modèle d’événement d’expérience Adobe Analytics |
| Champs unifiés |

Lors de la création du flux de données de connexion source pour **Suite de rapports A**, sélectionnez **Schéma unifié** à utiliser dans le flux de données. Ajoutez des mappages personnalisés comme suit :

| Suite de rapports : champ source | Champ de destination du groupe de champs Champs unifiés |
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
| \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

Remarque : Le chemin d’accès XDM pour vos champs de destination dépend de la manière dont vous configurez votre groupe de champs personnalisé.

Lors de la création du flux de données de connexion source pour **Suite de rapports B**, sélectionnez à nouveau **Schéma unifié** à utiliser dans le flux de données. Le workflow affiche que deux champs ont un conflit de nom de descripteur. En effet, les descripteurs pour eVar1 et eVar2 sont différents dans la suite de rapports B par rapport à ceux de la suite de rapports A. Mais nous le savons déjà afin de pouvoir ignorer le conflit et utiliser des mappages personnalisés comme suit :

| Champ source de la suite de rapports B | Champ de destination du groupe de champs Champs unifiés |
|---|---|
| \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
| _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

Créez maintenant une **Toutes les suites de rapports** connexion pour CJA, en combinant le jeu de données A et le jeu de données B.

Créez un **Vue globale** vue de données dans CJA. Ignorez les champs d’eVar d’origine et incluez uniquement les champs du groupe de champs Champs unifiés .

Vue des données de la vue globale dans CJA :

| Champ source | Inclure dans la vue de données ? |
| --- | --- | 
| \_experience.analytics.customDimensions.eVars.eVar1 | Non |
| \_experience.analytics.customDimensions.eVars.eVar2 | Non |
| _\&lt;path>_.Search_term | Oui |
| _\&lt;path>_.Customer_category  | Oui |
| _\&lt;path>_.Business_unit | Oui |

Essentiellement, vous avez maintenant mappé eVar1 et eVar2 des suites de rapports sources à trois nouveaux champs. Notez qu’un autre avantage de l’utilisation des mappages de préparation de données est que les champs de destination sont désormais basés sur des noms sémantiquement significatifs (terme de recherche, unité opérationnelle, catégorie client) au lieu de noms d’eVar moins significatifs (eVar1, eVar2).

Remarque : Le groupe de champs personnalisés Champs unifiés et les mappages de champs associés peuvent être ajoutés à tout moment aux flux de données et aux jeux de données du connecteur source Analytics existants, mais cela aura un impact uniquement sur les données à venir.

## Plus que de simples suites de rapports

Les fonctionnalités de la préparation des données pour combiner des jeux de données avec différents schémas vont au-delà des suites de rapports Analytics. Supposons que vous ayez deux jeux de données contenant les données suivantes :

| Jeu de données A = suite de rapports Analytics via Analytics Source Connector |
| --- |
| eVar1 => Catégorie de client |

| Jeu de données B = Données du centre d’appel |
| --- |
| Some_field => Catégorie de clients |

À l’aide de la préparation des données, vous pouvez combiner la catégorie du client en eVar 1 dans les données Analytics avec la catégorie du client dans le champ Some_field des données du centre d’appel. Voici une façon de le faire. Là encore, la convention d’affectation des noms peut être modifiée selon vos besoins.

Créez un groupe de champs personnalisé :

| Groupe de champs personnalisés &quot;Informations client&quot;  |
| --- |
| Customer_category |

Créez un schéma dans AEP. Ajoutez les groupes de champs suivants au schéma :

| Groupes de champs pour le &quot;schéma étendu&quot; |
| --- | 
| Événement d’expérience XDM |
| Modèle d’événement d’expérience Adobe Analytics |
| Informations sur le client |

Lors de la création du flux de données pour **Jeu de données A**, sélectionnez **Schéma étendu** comme schéma. Ajoutez des mappages personnalisés comme suit :

| Jeu de données Champ source | Champ de destination du groupe de champs Informations client |
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

Lors de la création du flux de données pour **Jeu de données B**, sélectionnez à nouveau **Schéma étendu** comme schéma. Ajoutez des mappages personnalisés comme suit :

| Champ source du jeu de données B | Champ de destination du groupe de champs Informations client |
| --- | --- |
| _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

Créez une connexion CJA qui combine le jeu de données A et le jeu de données B. Créez une vue de données dans CJA, à l’aide de la connexion CJA que vous venez de créer. Ignorez les champs d’eVar d’origine et incluez uniquement les champs du groupe de champs Informations sur le client .

Vue des données dans CJA :

| Champ source | Inclure dans la vue de données ? |
|---|---|
| \_experience.analytics.customDimensions.eVars.eVar1 | Non |
| \_experience.analytics.customDimensions.eVars.eVar2 | Non |
| _\&lt;path>_.Customer_category | Oui |

## Préparation de données et ID de composant

Comme décrit ci-dessus, la préparation de données vous permet de mapper différents champs entre plusieurs suites de rapports Adobe Analytics. Ceci s’avère utile dans CJA lorsque vous souhaitez combiner des données provenant de plusieurs jeux de données en une seule connexion CJA. Cependant, si vous avez l’intention de conserver les suites de rapports dans des connexions CJA distinctes mais que vous souhaitez utiliser un jeu de rapports parmi ces connexions et vues de données, la modification de l’identifiant de composant sous-jacent dans CJA permet de rendre les rapports compatibles même si les schémas sont différents. Voir [Paramètres des composants](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) pour plus d’informations.

La modification de l’identifiant du composant est une fonction CJA uniquement qui n’a aucune incidence sur les données du connecteur source Analytics envoyé au profil unifié et à la plateforme de données régionale.
