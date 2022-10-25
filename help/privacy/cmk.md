---
title: Clés gérées par le client
description: Découvrez comment configurer les clés gérées par le client pour CJA.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
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

Pour configurer CMK pour CJA, procédez comme suit :

1. Assurez-vous que vous êtes autorisé à utiliser le CMK en vérifiant auprès de votre équipe Compte d’Adobe.
1. Créez un Key Vault Azure à utiliser uniquement avec CJA.
1. Associez votre valeur de clé Azure à l’application Azure CJA CMK (lien à suivre).
1. Créez un ticket d’Adobe à l’assistance clientèle demandant la configuration du CMK. Incluez l’URI Azure dans votre ticket.
1. L’assistance clientèle d’Adobe confirmera l’achèvement de l’application CMK sur vos données CJA.
