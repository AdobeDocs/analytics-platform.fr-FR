---
title: Exporter des rapports depuis Report Builder
description: Décrit comment exporter des données de Report Builder vers des destinations sécurisées
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 9505f21748b3d94b2398f898e5399d095ccec260
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 39%

---


# Planifier des classeurs en exportant vers des destinations cloud

Vous pouvez exporter des classeurs Customer Journey Analytics de Report Builder vers des fournisseurs cloud tels que Google, Azure et Amazon.

[Les avantages de l’exportation des rapports de Report Builder vers le cloud](#advantages-of-exporting-to-the-cloud) incluent la possibilité d’utiliser des rapports dans des outils tiers ou de les combiner avec des données externes.

Avant d’exporter des classeurs de Report Builder vers une destination cloud, assurez-vous que vos blocs de données, votre environnement et vos autorisations répondent aux [ exigences d’exportation ](#export-requirements).

## Comprendre le processus d’exportation

Procédez comme suit lors de l’exportation de classeurs de Report Builder vers le cloud :

1. [Configurer un compte cloud](/help/components/exports/cloud-export-accounts.md)

1. [Configurer un emplacement sur le compte](/help/components/exports/cloud-export-locations.md)

1. [Exporter un rapport depuis Report Builder](#export-a-report-from-report-builder)

1. Accédez aux données dans votre compte cloud et [Gérer les exportations dans Adobe](/help/components/exports/manage-exports.md)

![Processus d’exportation décrit aux étapes 1 à 4.](assets/report-builder-export-process.png)

## Exporter un rapport depuis Report Builder {#export-from-report-builder}

>[!NOTE]
>
>Avant d’exporter des données comme décrit dans cette section, découvrez [le processus d’exportation](#understand-the-export-process) dans la section ci-dessus.

Pour exporter des rapports depuis Report Builder :

1. Si ce n’est pas déjà fait, configurez un compte et un emplacement d’export, comme décrit dans la section [Configurer des comptes d’export cloud](/help/components/exports/cloud-export-accounts.md).

1. Dans la feuille de calcul Excel qui contient les données à exporter, ouvrez le panneau de droite **[!UICONTROL Adobe Report Builder]**.

1. Sélectionnez [!UICONTROL **Planifier**].

<!-- add screenshot -->

1. Dans l’onglet **[!UICONTROL Classeurs]**, sélectionnez l’icône plus pour créer un planning

   ![Onglet Plannings de Report Builder](assets/report-builder-schedule-cloud.png)

   Ou

   Pour exporter le classeur selon un planning que vous avez déjà créé, sélectionnez le planning dans la liste des plannings, puis sélectionnez **[!UICONTROL Envoyer selon le planning]**.

1. Dans le panneau de droite [!UICONTROL **Adobe Report Builder**], spécifiez les informations suivantes pour continuer à créer un planning :

   | Nom du champ | Fonction |
   |---------|----------|
   | **[!UICONTROL Fichier]** | Affiche le fichier du classeur actuellement sélectionné pour l&#39;exportation. Sélectionnez l’icône du classeur ![TableSelect](/help/assets/icons/TableSelect.svg) en regard du nom de fichier pour choisir le classeur actif s’il n’est pas déjà sélectionné. |
   | **[!UICONTROL Nom de fichier]** <!--should be File name --> | Permet de modifier le nom de fichier avant d’exporter le classeur.<p>Par défaut, le nom de fichier du classeur correspond au nom du classeur</p> |
   | **[!UICONTROL Type de fichier]** | Choisissez le type de fichier pour le fichier exporté. Vous pouvez choisir Excel, PDF ou CSV. <p>Lorsque vous sélectionnez **[!UICONTROL CSV]**, gardez à l’esprit que le classeur planifié est envoyé en tant que pièce jointe au format ZIP. Certaines administrations de messagerie d&#39;entreprise peuvent bloquer les e-mails contenant des pièces jointes au format ZIP. Un avertissement s’affiche en conséquence.</p> |
   | **[!UICONTROL Ajouter un horodatage au nom du fichier]** | Sélectionnez cette option pour ajouter un horodatage au nom du fichier afin d’identifier la date à laquelle le classeur a été mis à jour. Un horodatage est utile pour savoir quelle version d’un classeur a été envoyée à une date spécifique. Lorsque cette option est sélectionnée, vous pouvez choisir entre : |
   | **[!UICONTROL Aperçu du nom de fichier]** <!--should be File name preview --> | Affiche un aperçu de l’apparence du nom du fichier après l’exportation. |
   | **[!UICONTROL Protéger le classeur par mot de passe]** | Indiquez un mot de passe pour protéger le fichier exporté afin que seules les personnes disposant du mot de passe puissent y accéder. <p>Les mots de passe doivent comporter au moins 8 caractères, au moins 1 chiffre et 1 caractère spécial (par exemple `!`, `@`, `#` et `$`).</p> |
   | **[!UICONTROL Adresse électronique]** | Sélectionnez cette option pour envoyer le fichier à une adresse e-mail spécifique. Pour plus d’informations, consultez [Planification de classeurs par partage via e-mail](/help/report-builder/schedule-reportbuilder.md). |
   | **[!UICONTROL Autres diffusions]** | Sélectionnez cette option pour envoyer le fichier à un compte cloud, puis utilisez les menus déroulants **[!UICONTROL Compte]** et **[!UICONTROL Emplacement]** décrits ci-dessous pour sélectionner le compte et l’emplacement. |
   | **[!UICONTROL Compte]** | Sélectionnez le compte d’export dans le cloud où vous souhaitez que les données soient envoyées. <p>Si vous n’avez pas encore configuré de compte cloud à utiliser, vous pouvez également configurer un nouveau compte :<ol><li>Sélectionnez [!UICONTROL **Ajouter un compte**], puis spécifiez les informations suivantes :<ul><li>[!UICONTROL **Nom du compte d’emplacement**] : spécifiez un nom pour le compte d’emplacement. Ce nom apparaît lors de la création d’un emplacement. </li><li>[!UICONTROL **Description de compte d’emplacement**] : fournissez une brève description du compte pour le différencier des autres comptes du même type de compte.</li><li>**[!UICONTROL Rendre le compte disponible pour tous les utilisateurs de votre organisation]** : sélectionnez cette option pour permettre à d’autres utilisateurs de votre organisation d’utiliser le compte. Tenez compte des points suivants lors du partage de comptes :<ul><li>Les comptes que vous partagez ne peuvent pas être annulés.</li><li>Les comptes partagés ne peuvent être modifiés que par le propriétaire du compte.</li><li>Tout le monde peut créer un emplacement pour le compte partagé.</li></ul></li><li>[!UICONTROL **Type de compte**] : sélectionnez le type de compte cloud vers lequel vous exportez. Les types de compte disponibles sont ARN de rôle Amazon S3, Google Cloud Platform, Azure SAS et Azure RBAC.</li></ul><li>Pour terminer la configuration de votre compte, sélectionnez le lien ci-dessous, correspondant au [!UICONTROL **type de compte**] sélectionné :<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[RBAC Azure](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li></ul></ol> |
   | **[!UICONTROL Emplacement]** | Sélectionnez l’emplacement sur le compte où vous souhaitez que les données d’export soient envoyées.<p>Si vous n’avez pas encore configuré l’emplacement que vous souhaitez utiliser sur le compte que vous avez sélectionné, vous pouvez configurer un nouvel emplacement :<ol><li>Sélectionnez [!UICONTROL **Ajouter un emplacement**], puis spécifiez les informations suivantes : <ul><li>[!UICONTROL **Nom**] : nom de l’emplacement.</li><li>[!UICONTROL **Description**] : fournissez une brève description de l’emplacement pour le différencier des autres emplacements sur le compte compte.</li><li>**[!UICONTROL Rendre l’emplacement disponible pour tous les utilisateurs de votre organisation]** : sélectionnez cette option pour permettre à d’autres utilisateurs de votre organisation d’utiliser l’emplacement. Tenez compte des points suivants lors du partage de comptes :<ul><li>Les emplacements partagés ne peuvent pas être annulés.</li><li>Les emplacements partagés ne peuvent être modifiés que par le propriétaire du compte.</li><li>Les emplacements ne peuvent être partagés que si le compte auquel l’emplacement est associé est également partagé.</li></ul></li><li>[!UICONTROL **Compte d’emplacement**] : sélectionnez le compte sur lequel vous souhaitez créer l’emplacement.</li></ul><li>Pour terminer la configuration de votre emplacement, sélectionnez le lien ci-dessous, qui correspond au type de compte que vous avez sélectionné dans le champ [!UICONTROL **Compte d’emplacement**] :<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[RBAC Azure](/help/components/exports/cloud-export-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL Afficher les options de planification]** | Sélectionnez cette option pour afficher des options supplémentaires pour planifier l’exportation. Ne sélectionnez pas cette option si vous souhaitez envoyer l’exportation une seule fois. Lorsque cette option est désélectionnée, l’exportation est lancée immédiatement. |
   | **[!UICONTROL À partir du]** | Jour et heure auxquels l’export planifié doit commencer. <p>Cette option n’est disponible que lors du choix d’une fréquence d’export planifié.</p> |
   | **[!UICONTROL Se terminant le]** | Jour et heure d’expiration de l’export planifié. L’export planifié ne s’exécute plus après la date et l’heure que vous avez définies. <p>Cette option n’est disponible que lors du choix d’une fréquence d’export planifié.</p> |
   | **[!UICONTROL Fréquence]** | Vous pouvez choisir une fréquence horaire, quotidienne, hebdomadaire, mensuelle ou annuelle pour un jour spécifique. Par exemple, vous pouvez configurer une planification pour envoyer le classeur le premier dimanche soir du mois afin que vos destinataires voient l’e-mail dans leur boîte de réception à la première heure le lundi matin. |

   {style="table-layout:auto"}

1. Sélectionnez [!UICONTROL **Envoyer selon le calendrier**] pour exporter le classeur.

   Les données sont envoyées au compte cloud que vous avez spécifié à la fréquence que vous avez spécifiée.

1. (Facultatif) Après avoir créé l’export, que vous ayez choisi de l’envoyer maintenant ou selon un planning défini, vous pouvez l’afficher et le gérer sur la [page Exports](/help/components/exports/manage-exports.md) et l’afficher dans les [journaux d’export](/help/components/exports/manage-export-logs.md).</p>

## Gérer des exports

Une fois les données exportées à partir d’Analysis Workspace, vous pouvez modifier, exporter à nouveau, dupliquer, baliser ou supprimer des exports existants, comme décrit dans la section [Gérer les exports](/help/components/exports/manage-exports.md).

## Avantages de l’export vers le cloud {#advantages}

L’export de données Customer Journey Analytics vers le cloud vous permet d’effectuer les opérations suivantes :

* Exportez vers un emplacement partagé, tel que Google Cloud Platform, Microsoft Azure et Amazon S3.

* Stockez de grandes quantités de données historiques.

  Ce type de données peut être utilisé pour détecter des tendances à long terme afin d’obtenir des renseignements commerciaux (informatique décisionnelle) et, au bout du compte, conduire à une meilleure prise de décisions commerciales.

* Incluez les mesures calculées dans les données Customer Journey Analytics exportées.

* Structure la sortie des données en tant que valeurs concaténées.

* Exporter une fois ou selon un planning.

* Exportez des fichiers au format Excel, PDF ou CSV.

* Exportez les blocs de données qui incluent plusieurs dimensions.

## Exigences d’export {#export-requirements}

### Configuration minimale requise

Assurez-vous que vos blocs de données, votre environnement et vos autorisations répondent aux exigences suivantes :

* **Blocs de données :** tous les blocs de données doivent inclure au moins un composant dans une colonne, une ligne ou une valeur.

* **Environnement :** assurez-vous que les [adresses IP](/help/technotes/ip-addresses.md) et [domaines](/help/technotes/domains.md) utilisés par Customer Journey Analytics sont autorisés via le pare-feu de leur entreprise.

* **Autorisations :** dans Adobe Admin Console, un profil de produit disposant de l’autorisation [!UICONTROL **Export de tableau complet**] doit être affecté aux utilisateurs et utilisatrices pour pouvoir exporter des tableaux complets. Pour plus d’informations sur l’attribution d’une autorisation à un profil de produits dans Admin Console, consultez [Autorisation Customer Journey Analytics dans Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Les utilisateurs dotés du rôle [Administrateur de produit](/help/technotes/access-control.md#product-admin-role) ont toujours accès aux rapports d’exportation de Report Builder. **(Cela s’applique-t-il à Report Builder???)**



