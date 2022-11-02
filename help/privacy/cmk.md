---
title: Clés gérées par le client
description: Découvrez comment configurer les clés gérées par le client pour CJA.
source-git-commit: 903c1423c91b220524174fa900a9ec13cd2051c6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Clés gérées par le client

>[!NOTE]
>
>Cette fonctionnalité sera disponible en novembre 2022.

Customer Journey Analytics (CJA) fournit l’option pour [Bouclier de santé](https://www.adobe.com/trust/compliance/hipaa-ready.html) et les clients Privacy &amp; Security Shield pour utiliser une clé gérée par le client Azure (CMK) à appliquer à vos données CJA.  Notez que ce processus est distinct de [Configuration du Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Actuellement, les clés gérées par le client ne sont disponibles que pour les organisations qui ont acheté la variable [Bouclier de santé ou protection des données et protection](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) offre complémentaire.

## Configuration de CMK pour CJA

Pour configurer CMK pour CJA, procédez comme suit :

1. Assurez-vous que vous êtes autorisé à Adobe CJA CMK en vérifiant auprès de votre équipe de compte d’Adobe.
1. Assurez-vous que, dans Azure, vous êtes un administrateur disposant d’un rôle privilégié tel que l’administrateur d’application, l’administrateur d’applications cloud ou l’administrateur global. [En savoir plus sur Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Créez un Key Vault Azure à utiliser uniquement avec CJA. [En savoir plus sur Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Accordez à l’application Azure Adobe l’accès à votre clé dans le coffre-fort de clé. Il s’agit de l’ID de l’application d’Adobe : 251e3919-1940-4296-bb8b-6b9a5e8a4805. [En savoir plus sur Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Créez un ticket d’Adobe à l’assistance clientèle demandant la configuration du CMK. Incluez l’URI Azure dans votre ticket. L’URI se trouve dans la variable **Identifiant de clé** de votre clé Azure.

   ![](assets/key-identifier.png)

1. L’assistance clientèle d’Adobe confirmera la fin de l’application CMK sur vos données CJA.

Toutes les données utilisées par Platform sont chiffrées en transit et au repos pour garantir la sécurité de vos données, avec ou sans CMK. Pour plus d’informations sur le cryptage Adobe Experience Platform, [en savoir plus](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).