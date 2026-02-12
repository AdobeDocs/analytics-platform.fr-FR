---
title: Mapper les données Analytics de plusieurs organisations IMS
description: Découvrez comment demander à mapper des données de suites de rapports provenant de plusieurs organisations IMS sources aux suites de rapports et, finalement, aux jeux de données dans une organisation IMS de destination.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: 888420e8cd11cd447fec99257b213669edd345c1
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 1%

---

# Mapping des données Cross-IMS

Cet article explique comment mapper les données des suites de rapports de plusieurs organisations IMS à des suites de rapports, et finalement à des jeux de données, dans une seule organisation IMS.

Par défaut, le connecteur source Analytics ingère les données des suites de rapports Adobe Analytics au sein d’une seule organisation. Le *mappage de données Cross-IMS* est une fonctionnalité permettant de mapper les données Analytics de plusieurs organisations IMS et fournit une solution à cette limitation. La procédure d’activation de cette fonctionnalité est décrite dans cet article.


## Scénario

Les privilèges d’accès sont attribués à plusieurs organisations IMS et vous disposez de données Analytics dans plusieurs suites de rapports de ces organisations IMS. Cette configuration peut être le résultat de :

* acquisitions ou fusions
* exigences de structure organisationnelle
* contraintes de déploiement régional

Par défaut, vous ne pouvez pas créer de rapports sur la combinaison de données provenant de plusieurs suites de rapports réparties entre plusieurs organisations IMS dans Customer Journey Analytics. La raison de cette limitation est que l’ingestion de données à partir d’Adobe Analytics dans Experience Platform par le biais du connecteur source Analytics ne prend en charge que l’ingestion de données appartenant à une seule organisation IMS. L’organisation IMS pour laquelle vous disposez d’autorisations et que vous utilisez pour vous connecter à Adobe Analytics, Experience Platform et Customer Journey Analytics.

Grâce à la fonctionnalité *Mappage de données entre services IMS*, vous pouvez demander à Adobe de mapper les données. Cette fonctionnalité utilise le connecteur source Analytics pour mapper les données des suites de rapports qui se trouvent dans plusieurs organisations IMS *source* aux suites de rapports (et finalement aux jeux de données) qui font partie d’une organisation IMS *destination*. Par exemple :

| Illustration | Explication |
|---|---|
| ![Mappage des données entre plusieurs organisations IMS](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Ce mappage vous permet de créer des rapports sur les suites de rapports qui existent dans l’organisation IMS 1, l’organisation IMS 2 et l’organisation IMS 3 à partir d’une connexion dans Customer Journey Analytics configurée dans l’organisation IMS 3. |

{style="table-layout:fixed"}

## Utilisation

Pour configurer et activer la fonctionnalité *Mappage de données entre services IMS*, vous devez demander le mappage via votre gestionnaire de compte Adobe. Pour ce faire, procédez comme suit :

1. En tant qu’administrateur de l’organisation IMS de destination, demandez des e-mails d’approbation à l’administrateur de l’organisation IMS source pour laquelle vous souhaitez mapper les suites de rapports. Vous pouvez utiliser le texte suivant comme modèle d’e-mail pour demander l’approbation des administrateurs de l’organisation IMS source.

   | Exemple de modèle d’e-mail |
   | --- |
   | *Représentant de nom de société*, pour accorder à l’organisation de destination sélectionnée l’accès aux organisations IMS suivantes (liste des organisations IMS sources), nous devons nous assurer qu’un administrateur de chaque organisation IMS soumet son approbation pour autoriser l’accès à ses données. Nous nous assurons ainsi que les autorisations d’accès aux données de toute organisation IMS affectée sont respectées. Pour vous assurer que nous disposons des autorisations appropriées, demandez à un administrateur Adobe enregistré de chaque organisation d’administration de répondre à cet e-mail avec son nom et l’organisation IMS qu’il représente, en disant « J’approuve » pour indiquer qu’il approuve l’affichage des données de cette organisation IMS dans l’organisation de destination [liste de l’organisation IMS de destination]. Notez que cet administrateur doit être un administrateur enregistré dans le système Adobe en tant qu’administrateur pour cette organisation IMS. |

1. Envoyez un e-mail au gestionnaire de compte Adobe au nom de l’administrateur de l’organisation IMS de destination qui demande le mappage des suites de rapports de plusieurs organisations IMS sources à l’organisation IMS de destination. Joignez les e-mails d’approbation que vous avez reçus des administrateurs de l’organisation IMS source.

Une fois que le gestionnaire de compte Adobe reçoit l’e-mail avec la demande de mappage des données Analytics de plusieurs organisations, la demande est examinée dans Adobe. Le gestionnaire de compte Adobe vous contacte pour toute question supplémentaire, formation facultative et autres informations.

Une fois approuvé, le mappage demandé est créé et vous en êtes informé. Le nom de l’organisation IMS source est ajouté au nom de la suite de rapports dans la [liste des suites de rapports Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) dans Experience Platform.


## Restrictions

Les restrictions suivantes s’appliquent à la fonctionnalité *mappage de données entre services IMS* :

* Vous ne pouvez connecter une suite de rapports qu’une seule fois entre plusieurs organisations.
* Vous devez supprimer toutes les connexions pour une organisation IMS définie comme organisation IMS de destination dans un mappage avant de pouvoir demander la suppression du mappage.
* Les ECID ne sont pas compatibles entre les organisations IMS sources mappées et ne sont pas compatibles avec l’organisation IMS de destination.


## Considérations

Vous pouvez prendre en compte les rubriques suivantes avant de demander la fonctionnalité *mappage de données Cross-IMS* :

### Profils

Une fois la fonctionnalité de *mappage de données Cross-IMS* approuvée, vous pouvez ajouter des données à Experience Platform pour une ou plusieurs suites de rapports dans l’organisation IMS de destination. Pour ce faire, vous devez configurer le [ connecteur source Analytics ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics?lang=fr). Les jeux de données cibles sont ensuite créés dans Experience Platform. Dans le cadre de cette configuration et de ce processus, vous avez la possibilité d’envoyer des données de profil d’une ou de plusieurs suites de rapports au service Profil.

Estimez le nombre total de profils résultant de la configuration et du processus, comme indiqué ci-dessus. Assurez-vous que le nombre total se situe dans la limite du nombre de profils auxquels vous avez contractuellement droit pour l’organisation de destination. Appliquez [ règles et conditions de filtrage ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"} pour inclure ou exclure des données de manière sélective de l’ingestion vers le service Profil. Ou désactivez l’option permettant d’envoyer des données de profil au service Profil pour les suites de rapports pertinentes.


#### Groupement

Vous pouvez utiliser le groupement [basé sur les champs](/help/stitching/fbs.md) et [basé sur les graphiques](/help/stitching/gbs.md) sur les jeux de données cibles. Lorsque vous utilisez le groupement basé sur les graphiques sur un ou plusieurs de ces jeux de données cibles, veillez à respecter vos droits contractuels pour le nombre de profils, comme indiqué dans la section [Profils](#profiles).

Si vous ne disposez pas d’une licence pour le profil client en temps réel, mais que vous souhaitez toujours utiliser le groupement basé sur les graphiques sur un ou plusieurs jeux de données cibles, assurez-vous de n’activer le [service d’identités](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) que pour ces jeux de données cibles.


### Autorisations

Un utilisateur disposant des autorisations suffisantes pour configurer le connecteur source Analytics dans l’organisation IMS de destination peut ingérer des données Analytics à partir de n’importe quelle organisation IMS source mappée. Aucune autorisation n’est vérifiée pour cet utilisateur ou cette utilisatrice pour l’une des organisations IMS sources.

### Rapport sur les données

La fonction *Mappage de données entre services IMS* n’est qu’une première étape pour vous assurer que vous pouvez utiliser les données dans le cadre d’un Customer Journey Analytics [connexion](/help/connections/overview.md), d’une ou de plusieurs [vues de données](/help/data-views/data-views.md) et [projets d’espace de travail](/help/analysis-workspace/home.md). Vous devez examiner attentivement les données que vous avez désormais disponibles dans une organisation IMS. Tenez également compte de fonctionnalités telles que la préparation des données, les champs dérivés, les tables de recherche supplémentaires, etc. avant de pouvoir créer des rapports corrects sur ces données.
