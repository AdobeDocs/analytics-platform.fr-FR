---
description: FAQ sur Workspace
title: Questions fréquentes
translation-type: tm+mt
source-git-commit: 3dc9d0d0a1f65a4205120895c35aa508f080c25d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 87%

---


# Questions fréquentes

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

| Question | Réponse |
|--- |--- |
| Quelles sont les conditions préalables à l’utilisation d’Analysis Workspace ? | L’utilisation d’Analysis Workspace nécessite une mise en oeuvre Customer Journey Analytics opérationnelle. Assurez-vous que votre entreprise envoie des données à Adobe Experience Platform avant d’utiliser l’outil. |
| Quelles sont les exigences en matière d’administration et d’accès concernant Analysis Workspace ? | Voir [Configuration requise pour l’administration](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| L’utilisation d’Analysis Workspace aura-t-elle une incidence sur la collecte des données ? | Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition. Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou sur cmd+Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur *[!UICONTROL Projet] > [!UICONTROL Nouveau]* dans le menu supérieur gauche. |
| Comment mettre en œuvre Analysis Workspace ? | Aucune mise en œuvre spéciale n’est requise. Analysis Workspace est disponible pour tous les Customer Journey Analytics de sociétés. Cependant, des autorisations standard pour le contenu (tels que les composants du projet) s’appliquent, ainsi que pour le traitement et le partage de projets. Voir [Administration et exigences d’accès](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Comment optimiser les performances d’Analysis Workspace ? | Voir [Optimisation des performances](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Résolution des problèmes

**Lorsque je fais glisser une mesure sur l’écran, un message indique « Données incorrectes ».**

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

**Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée à proprement dit, seulement des zéros.**

Si vous êtes parvenu à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :

* Vérifiez deux fois la suite de rapports et assurez-vous qu’elle contient des données.
* Si vous avez appliqué un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la période dans le coin supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site Web et utilisez [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr-FR) pour vérifier que la collecte des données s’effectue.