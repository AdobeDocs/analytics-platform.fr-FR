---
title: Clés gérées par le client
description: Découvrez comment configurer les clés gérées par le client pour CJA.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
source-git-commit: bb6e4dcc1c917fcfb565430232e3c5562f63fd1a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 100%

---

# Clés gérées par le client

Customer Journey Analytics (CJA) fournit l’option pour les clients de [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) et de Privacy &amp; Security Shield pour utiliser une clé Azure gérée par le client (CMK) à appliquer à vos données CJA.  Notez que ce processus est distinct de la [configuration de la CMK Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=fr).

>[!NOTE]
>
>Les clés gérées par le client ne sont actuellement disponibles que pour les organisations qui ont acheté l’offre de module complémentaire [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den).

## Configurer CMK pour CJA

Pour configurer CMK pour CJA, procédez comme suit :

1. Assurez-vous auprès de l’équipe chargée de votre compte Adobe que vous avez bien accès à Adobe CJA CMK.
1. Vérifiez dans Azure que vous êtes un administrateur disposant d’un rôle privilégié tel qu’administrateur d’application, administrateur d’applications cloud ou administrateur global. [En savoir plus sur Microsoft](https://learn.microsoft.com/fr-fr/azure/active-directory/roles/permissions-reference)
1. Créez un coffre de clés Azure Key Vault à utiliser uniquement avec CJA. [En savoir plus sur Microsoft](https://learn.microsoft.com/fr-fr/azure/key-vault/general/)
1. Accordez à l’application Adobe Azure l’accès à votre clé dans le coffre de clés. Il s’agit de l’ID de l’application Adobe : 251e3919-1940-4296-bb8b-6b9a5e8a4805. [En savoir plus sur Microsoft](https://learn.microsoft.com/fr-fr/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Créez un ticket d’assistance clientèle Adobe demandant la configuration du CMK. Incluez l’URI Azure dans votre ticket. L’URI se trouve dans le champ **Identificateur de clé** de votre clé Azure.

   ![](assets/key-identifier.png)

1. L’assistance clientèle Adobe confirmera l’achèvement de l’application CMK sur vos données CJA.

Toutes les données utilisées par Platform sont chiffrées en transit et au repos pour garantir la sécurité de vos données, avec ou sans CMK. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=fr) sur le chiffrement Adobe Experience Platform.
