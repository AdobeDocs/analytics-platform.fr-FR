---
description: FAQ et conseils de dépannage pour les espaces de travail.
title: Questions fréquentes
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '379'
ht-degree: 100%

---

# Questions fréquentes

| Question | Réponse |
|--- |--- |
| **Quelles sont les conditions préalables à l’utilisation d’Analysis Workspace ?** | Pour pouvoir utiliser Analysis Workspace, une implémentation opérationnelle de Customer Journey Analytics est nécessaire. Assurez-vous que votre organisation envoie les données à Adobe Experience Platform avant d’utiliser l’outil. |
| **Quelles sont les exigences en matière d’administration et d’accès concernant Analysis Workspace ?** | Consultez la page [Exigences en matière d’administration](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **L’utilisation d’Analysis Workspace aura-t-elle une incidence sur la collecte de données ?** | Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition. Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl + Z (Windows) ou sur cmd + Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur *[!UICONTROL Projet] > [!UICONTROL Nouveau]* dans le menu supérieur gauche. |
| **Comment implémenter Analysis Workspace ?** | Aucune implémentation spéciale n’est requise. Analysis Workspace est disponible pour toutes les sociétés Customer Journey Analytics. Néanmoins, des autorisations standard d’accès au contenu (par exemple aux composants des projets) s’appliquent ainsi qu’au traitement et au partage des projets. Consultez la page [Exigences en matière d’administration et d’accès](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Comment optimiser les performances d’Analysis Workspace ?** | Consultez la page [Optimisation des performances](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Résolution des problèmes

**Lorsque je fais glisser une mesure sur l’écran, un message indique « Données incorrectes ».**

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

**Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée à proprement dit, seulement des zéros.**

Si vous êtes parvenu à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :

* Si vous avez appliqué un filtre dans votre rapport, il se peut que les critères de filtre ne correspondent à aucune donnée. Essayez de supprimer le filtre ou d’ajuster la définition du filtre.
* Vérifiez la période dans le coin supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site Web et utilisez [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) pour vérifier que la collecte des données s’effectue.
