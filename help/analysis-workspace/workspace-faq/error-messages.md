---
description: Liste des messages d’erreur dans Analysis Workspace et ses composants connexes
title: Messages d’erreur
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 78%

---


# Messages d’erreur

Vous pouvez rencontrer des erreurs lors de l’interaction avec Analysis Workspace qui influenceront également les performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

| Message d’erreur | Quelle en est la raison ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL Une erreur système s’est produite. Veuillez consigner une demande du service d’assistance clientèle sous **[!UICONTROL Aide > Envoyer le ticket d’assistance]** et incluez votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Erreur 500 : Échec du chargement de la page] | Problèmes avec votre réseau local, tels que société [paramètres de pare-feu](https://docs.adobe.com/content/help/fr-FR/analytics/technotes/ip-addresses.translate.html), sont un facteur contribuant à cette erreur. En outre, l&#39;Adobe peut rencontrer un problème qui doit être résolu. | Essayez de vous reconnecter après plusieurs minutes. Si le problème persiste, envoyez le code d’ID d’instance EIM au service à la clientèle. |
| [!UICONTROL L’un des segments ou la recherche dans cette visualisation contient une recherche de texte qui a renvoyé trop de résultats.] | Les critères de segment ou le filtre de rapport sont trop étendus. | Affinez vos critères de recherche de texte et réessayez. |
| [!UICONTROL Établissement de rapports inhabituellement lourd pour la suite de rapports. Réessayez ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée. |
| [!UICONTROL La requête est trop complexe.] | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les dépassements de délai en raison de la taille de la requête, du nombre trop élevé d’éléments correspondants dans un segment ou un filtre de recherche, du nombre trop élevé de mesures incluses, des combinaisons de dimensions et de mesures incompatibles, etc. | Simplifiez votre requête en supprimant certaines colonnes ou lignes du tableau ou en divisant le tableau en plusieurs requêtes distinctes. |
| [!UICONTROL Actuellement, cette dimension ne prend pas en charge les modèles d’attribution autres que ceux par défaut.] | L’attribution autre que l’attribution par défaut n’est pas prise en charge pour la dimension que vous utilisez. | Remplacez la dimension de votre tableau par une dimension compatible avec [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |