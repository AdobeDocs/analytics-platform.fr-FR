---
description: Découvrir les messages d’erreur et comment résoudre les problèmes dans Adobe Analysis Workspace
title: Erreurs courantes et résolution des problèmes dans Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Erreurs et résolution des problèmes

Vous pouvez rencontrer des erreurs lorsque vous interagissez avec Analysis Workspace qui peuvent affecter ses fonctionnalités ou ses performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

## Messages d’erreur

Certains messages d’erreur courants peuvent s’afficher lorsque vous utilisez Analysis Workspace :

| Message d’erreur | Pourquoi l’erreur se produit-elle ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL La vue de données fait l’objet de rapports exceptionnellement lourds. Veuillez réessayer ultérieurement.] | Votre organisation tente d’exécuter trop de requêtes simultanées sur une vue de données spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs et utilisatrices qui effectuent simultanément des demandes de création de rapports. | Répartissez vos requêtes et vos plannings pour la vue de données de manière plus uniforme tout au long de la journée.<p>Les administrateurs et les administratrices peuvent utiliser le [Gestionnaire des activités de rapport pour identifier et annuler des requêtes](/help/reporting-activity-manager/reporting-activity-overview.md) qui consomment de la capacité de création de rapports.</p> |
| [!UICONTROL Ce rapport est trop complexe. Veuillez consulter les bonnes pratiques pour créer des rapports Analysis Workspace.] | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les expirations de délai en raison de la complexité de la requête. | Simplifiez votre requête. Par exemple, raccourcissez la période, simplifiez les critères de filtrage ou supprimez certaines colonnes ou lignes de votre tableau. Vous pouvez également envisager de diviser le tableau en plusieurs requêtes distinctes. |
| [!UICONTROL La vue des données dépasse actuellement sa capacité de reporting. Veuillez simplifier la demande ou réessayer plus tard.] | Votre organisation tente d’exécuter trop de requêtes simultanées sur une vue de données spécifique. Les facteurs à l’origine de cette erreur sont les requêtes API, les projets planifiés, et les utilisateurs et les utilisatrices qui effectuent simultanément des demandes de création de rapports. | Répartissez vos requêtes et vos plannings pour la vue de données de manière plus uniforme tout au long de la journée. |
| [!UICONTROL Une erreur système s’est produite. Veuillez soumettre un ticket à l’assistance clientèle sous **[!UICONTROL Aide > Envoyer le ticket d’assistance]** en incluant votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Erreur 500 : Échec du chargement de la page] | Les problèmes liés à votre réseau local, tels que les [paramètres du pare-feu](/help/technotes/ip-addresses.md) de la société, sont un facteur contribuant à cette erreur. En outre, Adobe peut rencontrer un problème qui doit être résolu. | Essayez de vous reconnecter après quelques minutes. Si le problème persiste, envoyez le code d’ID d’instance EIM à l’assistance clientèle. |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |


## Résolution des problèmes

Lorsque vous utilisez Analysis Workspace, vous pouvez utiliser les informations ci-dessous pour résoudre certains problèmes courants.

| Problème | Comment résoudre le problème |
|---|---|
| Lorsque je glisse et dépose une mesure, un message indique *Données non valides*. | Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte. |
| Lorsque je glisse et dépose une mesure, je ne vois aucune donnée, seulement des zéros. | Si vous avez réussi à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :<ul><li>Si vous avez appliqué un filtre dans votre rapport, il se peut que les critères de filtre ne correspondent à aucune donnée. Essayez de supprimer le filtre ou d’ajuster la définition du filtre.</li><li>Vérifiez la période dans le coin supérieur droit et pour vous assurer qu’elle est définie sur la valeur souhaitée.</li><li>Accédez à votre site Web et utilisez [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) pour vérifier que la collecte des données s’effectue.</li></ul> |
