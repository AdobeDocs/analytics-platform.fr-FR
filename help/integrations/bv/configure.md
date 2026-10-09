---
title: Configuration de l’intégration entrante Brand Visibility
description: Découvrez comment configurer l’intégration de Brand Visibility à Customer Journey Analytics
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fbbb3ffb1b0d1d5361b594e81c260dab25f44338
workflow-type: tm+mt
source-wordcount: '1783'
ht-degree: 0%
---
# Installation et configuration de l’intégration entrante

Cet article présente les [conditions préalables](#prerequisites), [responsabilités](#responsibilities), [étapes de vérification](#verification), [étapes de dépannage](#troubleshoot) et [critères d’achèvement](#completion-criteria) pour configurer l’intégration entrante de Brand Visibility avec Customer Journey Analytics.

## Conditions préalables

Tenez compte des conditions préalables suivantes avant d’activer l’intégration entrante. Et utilisez la procédure de vérification pour vérifier

### Transfert de journal BYOCDN

Les journaux d’accès au réseau CDN doivent être transférés et reçus par Adobe Brand Visibility pour chaque site de Visibilité des marques de données avant que le connecteur source de Visibilité des marques de données puisse être viable.

Cette exigence s’applique à chaque site de Visibilité des marques. Une configuration de réseau CDN ou un flux de journaux pour un site, un domaine ou un sous-domaine ne couvre que ce site, sauf si Adobe confirme cette couverture pour un autre site.

Vérifiez avec Adobe les deux parties de la remise :

1. Vous avez configuré le réseau CDN ou le pipeline de journal approprié pour transférer les journaux d’accès requis vers la destination Amazon S3 fournie par Adobe.
1. Adobe a confirmé que les journaux sont reçus et détectés pour le site approprié.

Le transfert de journal BYOCDN fournit les données de requête CDN côté serveur utilisées pour l’analyse du trafic des agents automatisés. Les données ne dépendent pas des balises JavaScript exécutées dans un navigateur. L’élément requis
Le flux de journal du réseau CDN s’assure que le jeu de données de résumé en aval contient les données de trafic agentic de Brand Visibility prévues. Pour plus d’informations, consultez la [référence du transfert de journal BYOCDN](https://experienceleague.adobe.com/fr/docs/brand-visibility/using/log-forwarding/log-forwarding-overview).

### Informations requises

Vérifiez que vous disposez de valeurs pour tous les détails requis répertoriés dans le tableau ci-dessous pour chaque site de Visibilité des marques.

| Valeur requise | Vérification ou notes |
|---|---|
| Site ou domaine de visibilité des marques | Confirmez le site couvert par le transfert du journal CDN. |
| Fournisseur de réseau CDN | Identifiez le réseau CDN qui dessert le site. |
| Statut du transfert du journal CDN | La preuve que les journaux du site sont transférés et détectés par la Visibilité des marques. |
| Confirmation de préparation à la visibilité des marques | Vérifiez auprès de l’équipe du compte Adobe que vous êtes prêt avant d’activer et de planifier le connecteur. |
| Organisation IMS | Utilisez l’organisation IMS exacte associée à Brand Visibility, Experience Platform. |
| Sandbox | Utilisez le nom exact du sandbox désigné pour l’intégration entrante. |
| Connexion | Identifiez la connexion au Parcours du client qui doit inclure le jeu de données. |
| Vue de données | Identifiez une vue de données Customer Journey Analytics nouvelle ou existante qui doit inclure les composants. |
| Administrateur ou propriétaire | Indiquez le nom ou l’équipe du contact de configuration. |

Avant qu’Adobe ne planifie le connecteur géré, votre équipe de compte Adobe doit confirmer que le site est prêt pour l’intégration entrante. Les communications de diffusion s’appellent validation de la Visibilité des marques ou confirmation de préparation du site. La planification du connecteur géré est une exigence de service géré et non une action de libre-service du client.

### Sandbox

Le connecteur géré doit créer le jeu de données dans le sandbox AEP nommé spécifique désigné par le client au sein de l’organisation IMS.

Confirmez ce qui suit :

* Organisation IMS
* Sandbox Target Experience Platform

Le sandbox AEP cible est le même sandbox nommé utilisé par la connexion Customer Journey Analytics correspondante ou les connexions qui incluent le jeu de données.

Le client peut ajouter le jeu de données à la connexion CJA appropriée uniquement après qu’Adobe a confirmé que le jeu de données géré a été créé.

### Jeu de données de résumé

L’intégration entrante fournit un jeu de données de résumé agrégé dans Experience Platform qui contient des informations de requête CDN côté serveur associées à LLM, aux robots et à automated-agent
le trafic.

Brand Visibility utilise les journaux d’accès CDN pour identifier les requêtes provenant des robots et des agents automatisés. Ce trafic ne déclenche pas les balises JavaScript du navigateur et n’est donc pas capturé par le biais d’une implémentation Web Analytics conventionnelle.

Pour obtenir une description détaillée de l’intégration entrante, de la structure du jeu de données et des champs disponibles, voir [&#x200B; à propos du jeu de données &#x200B;](#about-the-dataset).

Le connecteur géré crée le jeu de données de résumé dans Experience Platform en utilisant :

* La classe **[!UICONTROL Mesures récapitulatives XDM]**
* Le groupe de champs **[!UICONTROL Résumé des requêtes CDN]**
* Champs organisés sous un objet **[!UICONTROL cdn]**

Le connecteur crée le jeu de données pour chaque site Brand Visibility, en utilisant le modèle de dénomination suivant : <code>Jeu de données Adobe Brand Visibility (ABV) - _baseUrl sans schéma_</code>. <br/>Par exemple, `Adobe Brand Visibility (ABV) Dataset - example.com` pour la <https://example.com> du site.

Les jeux de données créés avant l’adoption de cette convention de nommage affichent le modèle précédent <code>LLM Optimization (LLMO) Dataset - _baseUrl sans schéma_</code>.
Dans tous les cas, les clients doivent confirmer le nom ou l’identifiant exact du jeu de données avec leur équipe de compte Adobe après leur création.

Le jeu de données est constitué de données de synthèse agrégées. Lors de l’analyse du volume de requêtes dans Customer Journey Analytics, utilisez la mesure **[!UICONTROL Nombre de requêtes CDN]** fournie plutôt que de compter les lignes du jeu de données.

Vérifiez les champs disponibles dans le schéma du jeu de données créé pour le site de Visibilité des marques spécifique. Pour planifier la configuration de la vue de données, passez en revue les champs.

## Responsabilités

Adobe gère le connecteur entrant et, une fois les conditions préalables confirmées :

* Active le connecteur géré ABV → AEP.
* Crée le jeu de données récapitulatif pour chaque site ABV configuré.
* Termine le jeu de données dans le sandbox AEP fourni par le client.
* Fournit au client le nom ou l’identifiant du jeu de données à des fins de vérification.

Vos responsabilités en tant que client sont les suivantes :

* Pour vous assurer que les journaux CDN sont transférés à et reçus par Brand Visibility pour chaque site Brand Visibility.
* Pour fournir l’organisation IMS appropriée et le sandbox Experience Platform nommé.
* Pour sélectionner la connexion Customer Journey Analytics qui doit inclure le jeu de données.
* Pour ajouter le jeu de données à cette connexion.
* Pour sélectionner les champs à exposer en tant que composants dans la vue de données Customer Journey Analytics appropriée.
* Vérifier que les dimensions et mesures obtenues prennent en charge l’analyse prévue.

>[!IMPORTANT]
>
>Le connecteur géré s’arrête intentionnellement après la création et le remplissage du jeu de données Experience Platform. Adobe ne modifie pas vos connexions Customer Journey Analytics ni vos vues de données.

Le jeu de données n’est pas disponible pour l’analyse Customer Journey Analytics tant que vous ne l’avez pas ajouté à une connexion. Les données
n’est pas disponible pour les utilisateurs par le biais d’une vue de données tant que les champs pertinents n’ont pas été ajoutés à cette vue de données.

## Vérification

Procédez comme suit pour vérifier l’intégration entrante :

1. Confirmation de la préparation du site ABV et du journal CDN

   Pour chaque site ABV :

   * Confirmez le site ou le domaine exact couvert par la demande.
   * Confirmez le fournisseur de réseau CDN.
   * Vérifiez que le réseau CDN ou le pipeline du journal transfère les journaux d’accès requis.
   * Vérifiez que Brand Visibility reçoit ou détecte des journaux pour ce site.
   * Obtenez d’Adobe la confirmation de préparation à la Visibilité des marques de données du site.

   N’utilisez pas une instruction générale indiquant que « les journaux CDN sont activés », sauf si la confirmation couvre le site ABV spécifique.

1. Vérifier le jeu de données géré dans Experience Platform

   Une fois qu’Adobe a confirmé que le connecteur géré a créé le jeu de données :
   1. Connectez-vous à **&#x200B;**.
   1. Sélectionnez le sandbox nommé fourni lors de la réception dans la liste des sandbox.
   1. Recherchez le nom ou l’identifiant du jeu de données fourni par Adobe dans **[!UICONTROL Jeux de données]**.
   1. Vérifiez que le jeu de données est associé au site de Visibilité des marques attendu.
   1. Enregistrez le **[!UICONTROL Identifiant du jeu de données]** et le **[!UICONTROL Schéma]** lié.
   1. Passez en revue le nombre d’enregistrements du jeu de données, les dernières informations d’ingestion et les données d’exemple disponibles lorsque cela est autorisé.
   1. Ouvrez le schéma lié et vérifiez la structure XDM attendue :
      * Classe : **[!UICONTROL mesures récapitulatives XDM]**
      * Groupe de champs : **[!UICONTROL Résumé des requêtes CDN]**
      * Objet : **[!UICONTROL cdn]**
      * Dimensions et mesures attendues, telles que **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL requests]** et **[!UICONTROL timeToFirstByte]**.

1. Ajouter le jeu de données à une connexion

   Votre administrateur Customer Journey Analytics doit ajouter le jeu de données géré à la connexion prévue :

   1. Connectez-vous à Customer Journey Analytics.
   1. [Créer une connexion ou modifier la connexion existante prévue](/help/connections/create-connection.md). Vérifiez que la connexion utilise le même sandbox Experience Platform dans lequel le jeu de données géré a été créé.
   1. Recherchez le jeu de données à l’aide du nom ou de l’identifiant du jeu de données fourni par Adobe.
   1. Ajoutez le jeu de données à la connexion.
   1. Configurez les paramètres du jeu de données en fonction de la conception Customer Journey Analytics du client.
   1. Enregistrez la connexion.
   1. Pour confirmer que le jeu de données est inclus et que l’ingestion est en cours, passez en revue les détails de la connexion.

1. Configurer ou mettre à jour la vue de données

   Une fois que le jeu de données fait partie de la connexion :
   1. Connectez-vous à Customer Journey Analytics.
   1. [Créez une vue de données ou modifiez la vue de données](/help/data-views/create-dataview.md) associée au cas d’utilisation de création de rapports prévu.
   1. Sélectionnez la connexion qui contient le jeu de données Managed Brand Visibility.
   1. Ajoutez les champs de schéma requis en tant que dimensions ou mesures.
   1. Renseignez les champs nécessaires à l&#39;analyse planifiée, par exemple :
      * **[!UICONTROL Type de robot]**
      * **[!UICONTROL Fournisseur CDN]**
      * **[!UICONTROL URL]**
      * **[!UICONTROL Hôte]**
      * **[!UICONTROL Statut HTTP]**
      * **[!UICONTROL Nombre de requêtes]**
      * **[!UICONTROL Temps jusqu’au premier octet]**
   1. Enregistrez la vue de données.
   1. Validez les champs dans Analysis Workspace ou le workflow de création de rapports sélectionné par le client.

1. Validation du résultat de bout en bout

   Utilisez une période de création de rapports récente et vérifiez que :

   * Le site de Visibilité des marques attendu est représenté.
   * Les valeurs attendues du fournisseur de réseau CDN et de l’hôte sont présentes.
   * Le trafic des robots ou des agents automatisés est représenté.
   * Les dimensions URL et État HTTP contiennent les valeurs attendues.
   * Le nombre de requêtes CDN et les mesures de performances sont disponibles.
   * Le jeu de données est inclus dans la connexion prévue.
   * Les champs obligatoires sont exposés dans la vue de données prévue.

Le temps exact nécessaire à la disponibilité des données dépend de l’ingestion gérée et du workflow de traitement Customer Journey Analytics. Votre équipe de compte Adobe doit indiquer toutes les attentes en matière de traitement applicables à votre demande.

## Résoudre des problèmes

Consultez ci-dessous les mesures à prendre en cas de problème :

* Le jeu de données n’apparaît pas dans AEP.

  Vérifiez que :

  * L’organisation IMS est correcte.
  * Le sandbox Experience Platform sélectionné est correct.
  * Adobe a confirmé que le connecteur géré a été activé.
  * Le nom ou l’identifiant du jeu de données fourni par Adobe a été utilisé.
  * Le jeu de données a été créé pour le site Brand Visibility approprié.

* Le jeu de données existe mais ne contient aucune donnée attendue.

  Vérifiez que :
  * Les journaux CDN sont transférés pour le site de Visibilité des marques exact.
  * ABV a confirmé que les journaux sont reçus ou détectés.
  * Le site ou le domaine dans la configuration du réseau CDN correspond au site de la Visibilité des marques.
  * Le connecteur géré a été activé après la confirmation de la préparation du journal CDN.
  * La période sélectionnée inclut la période postérieure au début de l’ingestion du journal.


* Le jeu de données existe dans Experience Platform mais n’est pas disponible dans Customer Journey Analytics.

  Vérifiez que :
  * La connexion Customer Journey Analytics utilise le même sandbox Experience Platform nommé.
  * Le jeu de données a été explicitement ajouté à la connexion.
  * L’administrateur Customer Journey Analytics dispose des autorisations requises.
  * La connexion a été enregistrée après l’ajout du jeu de données.

* Le jeu de données se trouve dans la connexion mais les champs ne sont pas disponibles pour la création de rapports.

  Vérifiez que :
  * La vue de données sélectionne la connexion Customer Journey Analytics appropriée.
  * Les champs de schéma attendus ont été ajoutés en tant que composants de la vue de données.
  * Les champs ont été placés dans la section **[!UICONTROL Dimensions]** ou **[!UICONTROL Mesures]** prévue.
  * La vue de données a été enregistrée après l’ajout des composants.
  * Le schéma du jeu de données correspond à la structure attendue du groupe de champs **[!UICONTROL Résumé des requêtes CDN]**.


## Critères d’achèvement


L’intégration entrante est prête pour la configuration de Customer Journey Analytics côté client lorsque toutes les conditions suivantes sont confirmées :

* Les journaux CDN sont transférés à et reçus par Visibilité des marques pour chaque site ABV demandé.
* Adobe a confirmé que le site est prêt pour le connecteur géré.
* L’organisation IMS a été fournie.
* La sandbox Experience Platform cible exacte a été fournie.
* Adobe a créé le jeu de données de résumé par site dans ce sandbox.
* Vous avez vérifié le jeu de données et son schéma XDM.
* Vous avez ajouté le jeu de données à la connexion CJA prévue.
* Vous avez configuré les composants de vue de données CJA appropriés.

