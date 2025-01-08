---
title: Clés gérées par le client ou la cliente
description: Découvrez comment configurer des clés gérées par le client pour Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 15%

---

# Clés gérées par le client ou la cliente

Adobe Customer Journey Analytics offre la possibilité aux clients [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) et Privacy &amp; Security Shield d’utiliser des clés gérées par le client (CMK) pour les données de Customer Journey Analytics. Notez que ce processus est distinct de la configuration de la CMK Adobe Experience Platform [](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). Les clés gérées par le client ne sont disponibles que pour les organisations qui ont acheté l’offre de module complémentaire [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/fr/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield).

## Configurer des clés gérées par le client pour Customer Journey Analytics sur Azure

Pour configurer la fonction CMK pour le Customer Journey Analytics s’exécutant sur Azure, procédez comme suit :

1. Assurez-vous que vous avez le droit d’utiliser la fonction CMK d’Adobe Customer Journey Analytics et que votre organisation utilise Adobe Experience Platform s’exécutant sur Azure. Vous pouvez vérifier ces droits en contactant votre équipe de compte d’Adobe.
1. Vérifiez dans Azure que vous êtes un administrateur disposant d’un rôle privilégié tel qu’administrateur d’application, administrateur d’applications cloud ou administrateur global. Voir [Rôles intégrés Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference) pour plus d’informations.
1. Créez un coffre de clés Azure Key Vault à utiliser uniquement avec Customer Journey Analytics. Consultez la [documentation du coffre de clés Azure Microsoft](https://learn.microsoft.com/fr-fr/azure/key-vault/general/) pour plus d’informations.
1. Accordez à l’application Adobe Azure l’accès à votre clé dans le coffre de clés. Pour plus d’informations](https://learn.microsoft.com/fr-fr/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault) voir [ Configuration des clés gérées par le client pour un compte existant . L&#39;ID d&#39;application d&#39;Adobe est :

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Créez un ticket d’assistance clientèle Adobe demandant la configuration du CMK. Incluez l’URI Azure dans votre ticket. L’URI se trouve dans le champ **Identifiant de clé** de votre clé Azure :

   ![Champs d’identifiant de clé affichant l’URI pour https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. L’assistance clientèle d’Adobe confirme l’achèvement de l’application CMK sur les données de votre Customer Journey Analytics.

Toutes les données utilisées par Platform sont chiffrées en transit et au repos pour garantir leur sécurité, avec ou sans clés gérées par le client. Pour plus d’informations sur le chiffrement de Adobe Experience Platform, voir [Chiffrement des données dans Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption).

## Configuration des clés gérées par le client pour Customer Journey Analytics sur Amazon Web Services

>[!AVAILABILITY]
>
>Cette section s’applique aux implémentations d’Experience Platform s’exécutant sur Amazon Web Services (AWS). Un Experience Platform s’exécutant sur AWS est actuellement disponible pour un nombre limité de clients. Pour en savoir plus sur l’infrastructure Experience Platform prise en charge, consultez la présentation multi-cloud de [Experience Platform ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud).

Si votre entreprise utilise Adobe Experience Platform s’exécutant sur Amazon Web Services, la fonction CMK est déjà configurée pour vous. Aucune configuration supplémentaire n’est nécessaire.
