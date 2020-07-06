---
description: FAQ sur Workspace
title: Questions fréquentes et résolution des problèmes dans Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 56%

---


# Questions fréquentes

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

| Question | Réponse |
|--- |--- |
| Quelles sont les conditions préalables à l’utilisation de l’Analysis Workspace ? | L’utilisation de l’Analysis Workspace nécessite une mise en oeuvre Customer Journey Analytics opérationnelle. Assurez-vous que votre entreprise envoie les données à l’Adobe Experience Platform avant d’utiliser l’outil. |
| Quelles sont les exigences en matière d’administration et d’accès concernant Analysis Workspace ? | Voir [Configuration requise pour l’administration](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| L’utilisation de l’Analysis Workspace aura-t-elle une incidence sur la collecte des données ? | Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition. Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou sur cmd+Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur *[!UICONTROL Projet] > [!UICONTROL Nouveau]* dans le menu supérieur gauche. |
| Comment mettre en œuvre Analysis Workspace ? | Aucune mise en œuvre spéciale n’est requise. Analysis Workspace est disponible pour toutes les sociétés Customer Journey Analytics. Cependant, des autorisations standard pour le contenu (tels que les composants du projet) s’appliquent, ainsi que pour le traitement et le partage de projets. Voir [ Administration et exigences d’accès](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Comment optimiser les performances d’Analysis Workspace ? | Voir [ Optimisation des performances](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Résolution des problèmes

**Lorsque je fais glisser une mesure sur l’écran, un message indique « Données incorrectes ».**

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

**Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée à proprement dit, seulement des zéros.**

Si vous avez créé avec succès un rapport d&#39;espace de travail mais qu&#39;il n&#39;y a aucune donnée, vous pouvez vérifier quelques éléments :

* Le Doublon vérifie la suite de rapports et s’assure qu’elle contient des données.
* Si vous avez appliqué un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la plage de dates dans le coin supérieur droit et assurez-vous qu’elle est définie sur une valeur à laquelle vous vous attendez.
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/fr-FR/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.