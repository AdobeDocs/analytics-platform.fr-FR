---
title: Clés gérées par le client
description: Découvrez comment configurer les clés gérées par le client pour Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 66%

---

# Clés gérées par le client

Adobe Customer Journey Analytics fournit l’option pour [Bouclier de santé](https://www.adobe.com/trust/compliance/hipaa-ready.html) et les clients Privacy &amp; Security Shield pour utiliser une clé gérée par le client Azure (CMK) à appliquer à vos données de Customer Journey Analytics.  Notez que ce processus est distinct de la [configuration de la CMK Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=fr).

>[!NOTE]
>
>Les clés gérées par le client ne sont actuellement disponibles que pour les organisations qui ont acheté l’offre de module complémentaire [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html?lang=fr).

## Configuration de CMK pour Customer Journey Analytics

Pour configurer CMK pour Customer Journey Analytics, procédez comme suit :

1. Assurez-vous que vous êtes autorisé à utiliser Adobe Customer Journey Analytics CMK en vérifiant auprès de votre équipe de compte d’Adobe.
1. Vérifiez dans Azure que vous êtes un administrateur disposant d’un rôle privilégié tel qu’administrateur d’application, administrateur d’applications cloud ou administrateur global. [En savoir plus sur Microsoft](https://learn.microsoft.com/fr-fr/azure/active-directory/roles/permissions-reference)
1. Créez un Key Vault Azure à utiliser uniquement avec Customer Journey Analytics. [En savoir plus sur Microsoft](https://learn.microsoft.com/fr-fr/azure/key-vault/general/)
1. Accordez à l’application Adobe Azure l’accès à votre clé dans le coffre de clés. Il s’agit de l’ID de l’application Adobe : 251e3919-1940-4296-bb8b-6b9a5e8a4805. [En savoir plus sur Microsoft](https://learn.microsoft.com/fr-fr/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Créez un ticket d’assistance clientèle Adobe demandant la configuration du CMK. Incluez l’URI Azure dans votre ticket. L’URI se trouve dans le champ **Identificateur de clé** de votre clé Azure.

   ![](assets/key-identifier.png)

1. L’assistance clientèle d’Adobe confirme la fin de l’application CMK sur vos données de Customer Journey Analytics.

Toutes les données utilisées par Platform sont chiffrées en transit et au repos pour garantir la sécurité de vos données, avec ou sans CMK. [En savoir plus](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=fr) sur le chiffrement Adobe Experience Platform.
