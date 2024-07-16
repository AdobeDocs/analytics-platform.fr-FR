---
description: Découvrez les messages d’erreur d’Adobe Analysis Workspace et de ses composants connexes.
title: Messages d’erreur courants dans Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 61%

---

# Messages d’erreur courants

Vous pouvez rencontrer des erreurs lors de l’interaction avec Analysis Workspace qui influenceront également les performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

| Message d’erreur | Quelle en est la raison ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL La vue de données fait l’objet de rapports exceptionnellement lourds. Veuillez réessayer ultérieurement.] | Votre entreprise tente d’exécuter trop de requêtes simultanées sur une vue de données spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la vue de données de manière plus uniforme tout au long de la journée.<p>Les administrateurs peuvent utiliser le [Gestionnaire d’activités de création de rapports pour identifier et annuler les requêtes](/help/reporting-activity-manager/reporting-activity-overview.md) qui consomment la capacité de création de rapports.</p> |
| [!UICONTROL Ce rapport est trop complexe. Veuillez consulter les bonnes pratiques pour créer des rapports Analysis Workspace.] | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les dépassements de délai en raison de la complexité de la requête. | Simplifiez votre requête en raccourcissant la période, en simplifiant les critères de filtrage ou en supprimant certaines colonnes ou lignes du tableau. Vous pouvez également diviser le tableau en requêtes distinctes. |
| [!UICONTROL La vue des données dépasse actuellement sa capacité de reporting. Veuillez simplifier la demande ou réessayer plus tard.] | Votre entreprise tente d’exécuter trop de requêtes simultanées sur une vue de données spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés et les utilisateurs simultanés qui effectuent des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la vue de données de manière plus uniforme tout au long de la journée. |
| [!UICONTROL Une erreur système s’est produite. Veuillez soumettre un ticket à l’assistance clientèle sous **[!UICONTROL Aide > Envoyer le ticket d’assistance]** en incluant votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Erreur 500 : Échec du chargement de la page] | Les problèmes liés à votre réseau local, tels que les [paramètres du pare-feu](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=fr) de la société, sont un facteur contribuant à cette erreur. En outre, Adobe peut rencontrer un problème qui doit être résolu. | Essayez de vous reconnecter après quelques minutes. Si le problème persiste, envoyez le code d’ID d’instance EIM à l’assistance clientèle. |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |
