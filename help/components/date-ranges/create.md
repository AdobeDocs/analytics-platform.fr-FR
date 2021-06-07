---
title: Création d’une plage de dates
description: Créez une période à utiliser dans les rapports.
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 8%

---

# Création d’une plage de dates

>[!NOTE]
>
>Vous consultez la documentation d’Analysis Workspace pour Customer Journey Analytics. L’ensemble de ses fonctionnalités diffère légèrement de celui d’[Analysis Workspace dans la version Adobe Analytics traditionnelle](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer une plage de dates personnalisée à l’aide de l’une des deux méthodes suivantes :

* Directement dans un projet d’espace de travail en cliquant sur le bouton &quot;`+`&quot; en regard de la liste des composants de période sur la gauche.
* Dans le gestionnaire de période

Pour créer une période dans le gestionnaire de périodes :

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Accédez à [!UICONTROL Composants] > [!UICONTROL Périodes].
1. Cliquez sur le bouton [!UICONTROL Ajouter] pour ouvrir la fenêtre modale qui crée une plage de dates.

## Création d’une fenêtre modale de période

La fenêtre modale comporte quatre champs que vous pouvez modifier :

* **Période** : La période que vous souhaitez pour ce composant.
* **Titre** : Nom que vous souhaitez donner à ce composant. Le titre est utilisé dans les projets Workspace.
* **Description** : La description que vous souhaitez pour ce composant. La description s’affiche lorsque vous cliquez sur l’icône ![i](../assets/i.png).
* **Balises** : Utilisez les balises pour organiser vos périodes. Une période peut appartenir à plusieurs balises.

## Sélection d’une période

Lorsque vous cliquez sur la période dans la fenêtre modale, plusieurs options s’offrent à vous :

* **Calendrier** : Sélectionnez les dates de début et de fin.
* **Utiliser des dates roulantes** : Cochez cette case si vous souhaitez que la période change au fil du temps. Ne cochez pas cette case si vous souhaitez que votre période reste statique.
* **Sélectionner un paramètre prédéfini** : Utilisez cette liste déroulante si vous souhaitez une plage de dates personnalisée basée sur une plage qui Adobe les offres par défaut. Lorsque vous sélectionnez un paramètre prédéfini, vous pouvez personnaliser davantage la période en fonction de vos besoins. Cela n’affecte pas le paramètre prédéfini que Adobe propose.

## Plages de dates variables

Si vous souhaitez une plage de dates variable, vous pouvez personnaliser le moment où elle s’affiche. Vous pouvez contrôler le moment où les dates de début et de fin roulent indépendamment les unes des autres.

* **Lorsque la date commence** : Choisissez si la date commence au début d’une période, à la fin d’une période ou utilisez un jour fixe.
* **La période à utiliser** : Sélectionnez la fréquence à laquelle la période s’étend. Vous pouvez le faire rouler chaque jour, chaque semaine, chaque mois, chaque trimestre ou chaque année.
* **Décalage** : Sélectionnez le décalage de la période. Vous pouvez ajouter ou soustraire des jours, semaines, mois, trimestres ou années.

## Exemples de dates roulantes

Certaines périodes peuvent s’avérer utiles dans certains rapports.

Année à jour :

```text
Start: Start of current year
End: End of current day
```

Jeudi dernier à jeudi :

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Exercice financier (par exemple, si un exercice commence en décembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
