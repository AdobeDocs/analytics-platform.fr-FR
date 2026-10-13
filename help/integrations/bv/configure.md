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
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '2118'
ht-degree: 0%
---
# Installation et configuration de l’intégration entrante

Cet article présente les [conditions préalables](#prerequisites), [responsabilités](#responsibilities), [étapes de vérification](#verification), [étapes de dépannage](#troubleshoot) et [critères d’achèvement](#completion-criteria) pour configurer l’intégration entrante de Brand Visibility avec Customer Journey Analytics.

## Conditions préalables

Tenez compte des conditions préalables suivantes avant d’activer l’intégration entrante. Utilisez la [procédure de vérification](#verification) ci-dessous pour confirmer chaque condition préalable.

### Transfert de journal BYOCDN

Les journaux d’accès au réseau CDN doivent être transférés et reçus par Adobe Brand Visibility pour chaque site de Visibilité des marques de données avant que le connecteur source de Visibilité des marques de données puisse être viable.

Cette exigence s’applique à chaque site de Visibilité des marques. Une configuration de réseau CDN ou un flux de journaux pour un site, un domaine ou un sous-domaine ne couvre que ce site.

Confirmez les deux parties de la remise :

1. Vous avez configuré le réseau CDN ou le pipeline de journal approprié pour transférer les journaux d’accès requis vers la destination Amazon S3 fournie par Adobe.
1. Brand Visibility reçoit et détecte les journaux du site approprié. Le site peut ensuite être sélectionné dans la source Adobe Brand Visibility d’Experience Platform.

Le transfert de journal BYOCDN fournit les données de requête CDN côté serveur utilisées pour l’analyse du trafic des agents automatisés. Les données ne dépendent pas des balises JavaScript exécutées dans un navigateur. L’élément requis
Le flux de journal du réseau CDN s’assure que le jeu de données de résumé en aval contient les données de trafic agentic de Brand Visibility prévues. Pour plus d’informations, consultez la [référence du transfert de journal BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview).

### Informations requises

Vérifiez que vous disposez de valeurs pour tous les détails requis répertoriés dans le tableau ci-dessous pour chaque site de Visibilité des marques.

| Valeur requise | Vérification ou notes |
|---|---|
| Site ou domaine de visibilité des marques | Confirmez le site couvert par le transfert du journal CDN. |
| Fournisseur de réseau CDN | Identifiez le réseau CDN qui dessert le site. |
| Statut du transfert du journal CDN | La preuve que les journaux du site sont transférés et détectés par la Visibilité des marques. |
| Site disponible dans la source de Visibilité des marques | Vérifiez que le site est disponible pour sélection dans la source de Visibilité des marques. Un site est disponible en fonction de la disponibilité des journaux CDN analysés dans Brand Visibility. |
| Organisation IMS | Utilisez l’organisation IMS exacte associée à Brand Visibility, Experience Platform. |
| Sandbox | Utilisez le nom exact du sandbox désigné pour l’intégration entrante. |
| Connexion | Identifiez la connexion au Parcours du client qui doit inclure le jeu de données. |
| Vue de données | Identifiez une vue de données Customer Journey Analytics nouvelle ou existante qui doit inclure les composants. |
| Administrateur ou propriétaire | Indiquez le nom ou l’équipe du contact de configuration. |

Vérifiez que chaque site est disponible à la sélection dans la source Adobe Brand Visibility avant de continuer.

### Sandbox

Vous pouvez ajouter le jeu de données à la connexion CJA une fois que le jeu de données aura apparu dans **[!UICONTROL Jeux de données]** dans cette sandbox.

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

La source de Visibilité des marques crée le jeu de données de résumé dans Experience Platform en utilisant :

* La classe **[!UICONTROL Mesures récapitulatives XDM]**
* Le groupe de champs **[!UICONTROL Résumé des requêtes CDN]**
* Champs organisés sous un objet **[!UICONTROL cdn]**

Le connecteur crée le jeu de données pour chaque site Brand Visibility, en utilisant le modèle de dénomination suivant : <code>Jeu de données Adobe Brand Visibility (ABV) - _baseUrl sans schéma_</code>. <br/>Par exemple, `Adobe Brand Visibility (ABV) Dataset - example.com` pour la <https://example.com> du site.

Les jeux de données créés avant l’adoption de cette convention de nommage affichent le modèle précédent <code>LLM Optimization (LLMO) Dataset - _baseUrl sans schéma_</code>.

Recherchez le jeu de données dans **[!UICONTROL Jeux de données]** dans le sandbox où vous avez créé le flux de données.

Le jeu de données est constitué de données de synthèse agrégées. Lors de l’analyse du volume de requêtes dans Customer Journey Analytics, utilisez la mesure **[!UICONTROL Nombre de requêtes CDN]** fournie plutôt que de compter les lignes du jeu de données.

Vérifiez les champs disponibles dans le schéma du jeu de données créé pour le site de Visibilité des marques spécifique. Pour planifier la configuration de la vue de données, passez en revue les champs.

## Responsabilités

Après avoir activé la source de Visibilité des marques, Visibilité des marques :

* Fournit le jeu de données de résumé pour le site que vous avez sélectionné.
* Renvoie le jeu de données dans le sandbox où vous avez créé le flux de données.

Vos responsabilités en tant que client sont les suivantes :

* Pour vous assurer que les journaux CDN sont transférés à et reçus par Brand Visibility pour chaque site Brand Visibility.
* Pour activer la source de Visibilité des marques dans le bon sandbox, vérifiez que votre site est disponible et sélectionnez-le.
* Pour sélectionner la connexion Customer Journey Analytics qui doit inclure le jeu de données.
* Pour ajouter le jeu de données à cette connexion.
* Pour sélectionner les champs à exposer en tant que composants dans la vue de données Customer Journey Analytics appropriée.
* Vérifier que les dimensions et mesures obtenues prennent en charge l’analyse prévue.

>[!IMPORTANT]
>
>Le connecteur géré s’arrête intentionnellement après la création et le remplissage du jeu de données Experience Platform. Adobe ne modifie pas vos connexions Customer Journey Analytics ni vos vues de données.

Le jeu de données n’est pas disponible pour l’analyse Customer Journey Analytics tant que vous ne l’avez pas ajouté à une connexion. Les données
n’est pas disponible pour les utilisateurs par le biais d’une vue de données tant que les champs pertinents n’ont pas été ajoutés à cette vue de données.

Pour activer la source :

1. Dans Experience Platform, sélectionnez le sandbox dans lequel vous souhaitez placer le jeu de données. Un site ne peut être alloué qu’une seule fois. Assurez-vous donc que ce sandbox est celui que vous souhaitez.
1. Accédez à **[!UICONTROL Sources]**, puis **[!UICONTROL Catalogue]** et enfin aux applications Adobe. Sur la carte **&#x200B;**, sélectionnez **[!UICONTROL Configurer]** la première fois. Ensuite, la carte affiche **[!UICONTROL Ajouter des données]**.

   ![Sélectionner la Visibilité des marques à partir des sources](assets/aep-sources-select-bv.png)

1. Sélectionnez **[!UICONTROL Ajouter des données]**.

   ![Ajouter des données à la source de Visibilité des marques &#x200B;](assets/aep-sources-bv-add-data.png)

1. À l’étape ➊ **[!UICONTROL Sélectionner des données]** :

   1. Sélectionnez le site dans le tableau **[!UICONTROL Nom du site]**. Une fois qu’un site a été alloué à un flux de données, vous ne pouvez plus sélectionner le site dans ce sandbox ou dans un autre.

      ![Étape 1 de la configuration de la source de Visibilité des marques &#x200B;](assets/bv-source-step-1.png)

   1. Sélectionnez **[!UICONTROL Suivant]**.

1. À l’étape ➋ **[!UICONTROL Détails du flux de données]** :

   1. Saisissez un **[!UICONTROL Nom du flux de données]** et un **[!UICONTROL Description]** facultatif. Vous pouvez également vous abonner aux alertes **[!UICONTROL Début de l’exécution du flux de données des sources]**, **[!UICONTROL Succès de l’exécution du flux de données des sources]** et **[!UICONTROL Échec de l’exécution du flux de données des sources]**.

      ![Étape 2 de la configuration de la source Brand Visibulity](assets/bv-source-step-2.png)

   1. Sélectionnez **[!UICONTROL Suivant]**.

1. À l’étape ➌ **[!UICONTROL Révision]** :

   1. Vérifiez la connexion et l’affectation du jeu de données.

      ![Étape 3 de la configuration de la source de Visibilité des marques &#x200B;](assets/bv-source-step-3.png)

   1. sélectionnez **[!UICONTROL Terminer]**.

Le jeu de données est affecté automatiquement et aucun mappage de champ n’est requis.

>[!IMPORTANT]
>
>Un site ne peut être alloué qu’une seule fois. Pour utiliser le site dans un autre sandbox, supprimez le flux de données auquel le site est affecté. La suppression du flux de données a un impact sur toute connexion Customer Journey Analytics ou vue de données qui repose sur les données de cette source.
>


## Vérification

Procédez comme suit pour vérifier l’intégration entrante :

1. Confirmez la préparation du site ABV et du journal CDN.

   Pour chaque site ABV :

   * Confirmez le site ou le domaine exact couvert par le transfert du journal CDN.
   * Vérifiez que le site est disponible pour sélection dans la source de Visibilité des marques d’Experience Platform. Un site est disponible en fonction de la disponibilité des journaux CDN analysés dans Brand Visibility.
   * Ne continuez pas sur une instruction générale selon laquelle « les journaux CDN sont activés ». Poursuivez lorsque le site ABV spécifique peut être sélectionné.
   * Vérifiez que Brand Visibility reçoit ou détecte des journaux pour ce site.
   * Obtenez d’Adobe la confirmation de préparation à la Visibilité des marques de données du site.

1. Vérifiez le jeu de données dans Experience Platform.

   Après avoir créé le flux de données :
   1. Connectez-vous à **&#x200B;**.
   1. Sélectionnez le sandbox dans lequel vous avez créé le flux de données.
   1. Recherchez le jeu de données de votre site Brand Visibility dans **[!UICONTROL Jeux de données]**.
   1. Vérifiez que le jeu de données est associé au site de Visibilité des marques attendu.
   1. Enregistrez le **[!UICONTROL Identifiant du jeu de données]** et le **[!UICONTROL Schéma]** lié.
   1. Passez en revue le nombre d’enregistrements du jeu de données, les dernières informations d’ingestion et les données d’exemple disponibles lorsque cela est autorisé.
   1. Ouvrez le schéma lié et vérifiez la structure XDM attendue :
      * Classe : **[!UICONTROL mesures récapitulatives XDM]**
      * Groupe de champs : **[!UICONTROL Résumé des requêtes CDN]**
      * Objet : **[!UICONTROL cdn]**
      * Dimensions et mesures attendues, telles que **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL requests]** et **[!UICONTROL timeToFirstByte]**.

1. Ajouter le jeu de données à une connexion

   Votre administrateur Customer Journey Analytics doit ajouter le jeu de données à la connexion prévue :

   1. Connectez-vous à Customer Journey Analytics.
   1. [Créer une connexion ou modifier la connexion existante prévue](/help/connections/create-connection.md). Vérifiez que la connexion utilise le même sandbox Experience Platform dans lequel le jeu de données a été créé.
   1. Recherchez le jeu de données par nom ou par identifiant de jeu de données.
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
      * **[!UICONTROL Type de robot CDN]**
      * **[!UICONTROL Fournisseur CDN]**
      * **[!UICONTROL URL CDN]**
      * **[!UICONTROL Hôte CDN]**
      * **[!UICONTROL Statut HTTP du réseau CDN]**
      * **[!UICONTROL Nombre de requêtes CDN]**
      * **[!UICONTROL Temps moyen jusqu’au premier octet du réseau CDN]**
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

Le temps exact nécessaire à la disponibilité des données dépend du workflow d’ingestion et de traitement Customer Journey Analytics.

## Résoudre des problèmes

Examinez les étapes suivantes si des problèmes se produisent :

* Le jeu de données n’apparaît pas dans AEP.

  Vérifiez que :

  * L’organisation IMS est correcte.
  * Le sandbox Experience Platform sélectionné est correct.
  * La source a été activée après le fonctionnement du transfert du journal CDN.
  * Le nom ou l’identifiant du jeu de données fourni par Adobe a été utilisé.
  * Le jeu de données a été créé pour le site Brand Visibility approprié.

* Le jeu de données existe mais ne contient aucune donnée attendue.

  Vérifiez que :
  * Les journaux CDN sont transférés pour le site de Visibilité des marques exact.
  * Brand Visibility reçoit ou détecte des journaux pour le site.
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

* Le site ne figure pas dans la liste.

  Vérifiez que :

  * Un site peut être sélectionné en fonction de la disponibilité des journaux CDN analysés dans Brand Visibility.
  * Le transfert du journal CDN est configuré et fonctionne pour le site.

* Impossible de sélectionner le site.

  Notez qu’une fois qu’un site est alloué à un flux de données, il ne peut plus être sélectionné dans ce sandbox ou dans un autre. Pour utiliser le site dans un autre sandbox, supprimez le flux de données auquel le site est affecté. Le site peut ensuite être sélectionné à nouveau. La suppression du flux de données a un impact sur toute connexion Customer Journey Analytics ou vue de données qui repose sur les données de cette source.

* Le flux de données affiche le statut En échec .

  Utilisez le tableau de bord **[!UICONTROL Surveillance]**. La présentation de **[!UICONTROL Sources]** indique qu’un flux de données source qui échoue en continu pendant 30 jours est automatiquement désactivé.


## Critères d’achèvement


L’intégration entrante est prête pour la configuration de Customer Journey Analytics côté client lorsque toutes les conditions suivantes sont confirmées :

* Les journaux CDN sont transférés à et reçus par Visibilité des marques pour chaque site ABV demandé.
* Chaque site de Visibilité des marques peut être sélectionné dans la source Adobe Brand Visibility.
* Vous avez activé la source Adobe Brand Visibility dans le sandbox prévu.
* Le jeu de données de résumé par site apparaît dans ce sandbox.
* Vous avez vérifié le jeu de données et son schéma XDM.
* Vous avez ajouté le jeu de données à la connexion CJA prévue.
* Vous avez configuré les composants de vue de données CJA appropriés.

