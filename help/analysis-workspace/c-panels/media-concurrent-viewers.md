---
title: Panneau Observateurs simultanés de médias
description: Comment utiliser et interpréter le panneau Observateurs simultanés de médias dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
source-git-commit: 9f1394df9b57707d57c701e997df8f4cd70c7baa
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 100%

---

# Panneau Observateurs simultanés de médias

Vous pouvez analyser les observateurs simultanés pour déterminer où s’est produit le pic d’accès simultanés ou l’endroit où des abandons ont eu lieu, ce qui permet de mieux comprendre la qualité du contenu et l’engagement des observateurs, et contribue également à résoudre les problèmes ou à planifier le volume ou l’échelle.

Dans Analysis Workspace, les observateurs simultanés représentent le nombre de visiteurs uniques qui visualisent vos flux de médias à un moment donné, quel que soit le nombre de sessions.

Le panneau Observateurs simultanés de médias permet d’analyser les observateurs simultanés au fil du temps. Il fournit également des informations détaillées sur le pic d’accès simultanés et la possibilité de ventiler et de comparer. Pour accéder au panneau Observateurs simultanés de médias, naviguez vers une suite de rapports dans laquelle les composants Media Analytics sont activés. Cliquez ensuite sur l’icône du panneau située à l’extrémité gauche et faites glisser le panneau dans votre projet Analysis Workspace.

Regardez cet aperçu vidéo de ce panneau :

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau Observateurs simultanés de médias à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois. <br> <br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute. <br> <br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou d’heure relatifs aux observateurs simultanés, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. Par défaut, le panneau affiche uniquement la valeur maximale, mais vous pouvez le modifier pour afficher la valeur minimale ou les deux valeurs.<br><br>Si vous utilisez des ventilations, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Ventilations de la série | Vous pouvez éventuellement ventiler votre visualisation par segments, dimensions, éléments de dimension ou périodes. <br><br>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les ventilations sont limitées à un seul niveau.<br><br>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.<br><br>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de ventilation de la série. |

### Affichage par défaut

![Affichage par défaut](assets/concurrent-viewers-default.png)


### Affichage de la ventilation de la série

![affichage de la ventilation de la série](assets/concurrent-viewers-series-breakdown.png)

## Sortie de panneau {#Output}

Le panneau Observateurs simultanés de médias renvoie un graphique en courbe et des synthèses de chiffres pour inclure des détails sur les valeurs maximales et/ou minimales d’observateurs simultanés. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, vous pouvez modifier et recréer le panneau en cliquant sur l’icône de modification en forme de crayon dans le coin supérieur droit.

Si vous avez sélectionné la ventilation des séries, une ligne du graphique en courbe et une synthèse des chiffres s’affichent pour chacune d’elles :

![sortie des observateurs simultanés](assets/concurrent-viewers-output.png)

### Source de données

La seule mesure qui peut être utilisée dans ce panneau est Observateurs simultanés :

| Mesure | Description |
|---|---|
| Nombre de viewers simultanés | Nombre de visiteurs uniques qui voient votre ou vos flux de médias à un moment précis, quel que soit le nombre de sessions.<br><br>Cette mesure est différente de celle des observateurs simultanés dans la section Rapports, qui utilise les sessions simultanées actives. L’utilisation de visiteurs uniques entraîne la suppression des « pics » indésirables aux limites de l’affichage (où les sessions se terminent et commencent en même temps). |

Un tableau à structure libre n’est pas disponible dans cet affichage. Pour afficher la source de données, vous pouvez faire un clic droit sur le graphique en courbes et télécharger le fichier au format .csv. Ce fichier inclut les ventilations de séries.


![sortie des observateurs simultanés](assets/concurrent-viewers-download-csv.png)

## Questions fréquentes {#FAQ}

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | Le tableau à structure libre n’est pas disponible dans cet affichage. Vous pouvez télécharger la source de données en effectuant un clic droit sur le graphique en courbes et en téléchargeant le fichier CSV. |
| Pourquoi ma granularité a-t-elle changé ? | La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à l’intégralité de la période.<br><br>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation. |
| Comment puis-je comparer les noms de vidéo, les segments, les types de contenu, etc. ? | Pour les comparer dans une visualisation unique, faites glisser des segments, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation des séries.<br><br>L’affichage est limité à 10 ventilations. Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux. |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les ventilations des séries en faisant glisser au moins 2 périodes. Ces périodes remplacent alors la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | Ce panneau permet uniquement la visualisation des lignes pour la série temporelle. |
| Puis-je exécuter la détection des anomalies ? | Non.  La détection des anomalies n’est pas disponible pour ce panneau. |
| Pourquoi utiliser des visiteurs uniques plutôt que des sessions actives ? | L’utilisation de visiteurs uniques permet de supprimer les pics indésirables aux limites de l’affichage (où les sessions se terminent et commencent simultanément). |
| Que signifie le fait d’avoir des observateurs simultanés avec une granularité supérieure à la minute ? | Avec une granularité supérieure à une minute, les observateurs simultanés représentent la somme des observateurs simultanés uniques pour toutes les minutes de cette période. Par exemple, les observateurs simultanés avec une granularité au niveau de l’heure représentent la somme des observateurs simultanés uniques pour toutes les minutes de cette heure. |
| Le panneau Espace de travail affiche-t-il les mêmes informations que le rapport sur les observateurs simultanés ? | Non.  Dans Analysis Workspace, les observateurs simultanés sont définis comme le nombre de visiteurs uniques qui visualisent votre flux de médias à un moment précis, quel que soit le nombre de sessions.<br><br>Cette mesure est différente de celle des observateurs simultanés dans la section Rapports, qui utilise les sessions simultanées actives. L’utilisation de visiteurs uniques entraîne la suppression des pics indésirables aux limites de l’affichage, où les sessions se terminent et commencent en même temps. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
