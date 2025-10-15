---
title: Clés gérées par le client ou la cliente
description: Découvrez comment configurer des clés gérées par le client ou la cliente pour Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: cdc8d889a05c55d2f4765d0837023d007a5a230d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 91%

---

# Clés gérées par le client ou la cliente

Adobe Customer Journey Analytics offre la possibilité aux clientes et clients [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) et Privacy &amp; Security Shield d’utiliser des clés gérées par le client ou la cliente (CMK) pour les données Customer Journey Analytics. Notez que ce processus est distinct de la [configuration CMK Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Les clés gérées par le client ou la cliente ne sont actuellement disponibles que pour les organisations qui ont acheté l’offre de module complémentaire [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/fr/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield).

## Configurer les clés gérées par le client ou la cliente pour Customer Journey Analytics sur Azure

Pour configurer la fonction CMK pour Customer Journey Analytics s’exécutant sur Azure, procédez comme suit :

1. Assurez-vous que vous avez le droit d’utiliser la fonction CMK d’Adobe Customer Journey Analytics et que votre organisation utilise Adobe Experience Platform s’exécutant sur Azure. Vous pouvez vérifier ces droits en contactant votre équipe Adobe en charge des comptes.
1. Vérifiez dans Azure que vous êtes un administrateur disposant d’un rôle privilégié tel qu’administrateur d’application, administrateur d’applications cloud ou administrateur global. Consultez [Rôles intégrés Microsoft Entra](https://learn.microsoft.com/fr-fr/entra/identity/role-based-access-control/permissions-reference) pour plus d’informations.
1. Créez un coffre de clés Azure Key Vault à utiliser uniquement avec Customer Journey Analytics. Consultez la [documentation du coffre de clés Microsoft Azure](https://learn.microsoft.com/fr-fr/azure/key-vault/general/) pour plus d’informations.
1. Accordez à l’application Adobe Azure l’accès à votre clé dans le coffre de clés. Pour ce faire, utilisez l’une des méthodes suivantes :
   * Octroyez des autorisations via le consentement d’autorisation via l’URL suivante : [https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&redirect_uri=https://experience.adobe.com&scope=user.read](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&redirect_uri=https://experience.adobe.com&scope=user.read)

   * Suivez les instructions de la section [Configurer les clés gérées par le client pour un compte existant](https://learn.microsoft.com/fr-fr/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault). L’ID de l’application Adobe est :

     **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Créez un ticket d’assistance clientèle Adobe demandant la configuration du CMK. Incluez l’URI Azure dans votre ticket. L’URI se trouve dans le champ **Identificateur de clé** de votre clé Azure :

   ![Champs d’identifiant de clé affichant l’URI pour https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. L’assistance clientèle Adobe confirme l’achèvement de l’application CMK sur vos données Customer Journey Analytics.

Toutes les données utilisées par Platform sont chiffrées en transit et au repos pour garantir leur sécurité, avec ou sans clés gérées par le client ou la cliente. Pour plus d’informations sur le chiffrement d’Adobe Experience Platform, consultez [Chiffrement des données dans Adobe Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/governance-privacy-security/encryption).

## Configurer les clés gérées par le client ou la cliente pour Customer Journey Analytics sur Amazon Web Services

>[!AVAILABILITY]
>
>Cette section s’applique aux implémentations d’Experience Platform s’exécutant sur Amazon Web Services (AWS). Experience Platform s’exécutant sur AWS est actuellement disponible pour un nombre limité de clientes et clients. Pour en savoir plus sur l’infrastructure Experience Platform prise en charge, consultez la [vue d’ensemble multi-cloud d’Experience Platform](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/multi-cloud).

Si votre entreprise utilise Adobe Experience Platform s’exécutant sur Amazon Web Services, la fonction CMK est déjà configurée pour vous. Aucune configuration supplémentaire n’est nécessaire.
