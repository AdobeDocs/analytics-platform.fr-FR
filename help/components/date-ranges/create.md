---
title: Création d’une plage de dates
description: Créez une plage de dates à utiliser dans le rapports.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---


# Création d’une plage de dates

>[!NOTE]
>
>Vous consultez la documentation de l’Analysis Workspace à Customer Journey Analytics. Son ensemble de fonctionnalités diffère légèrement de celui des [Analysis Workspace dans le Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/home.html)traditionnel de Adobe. [En savoir plus...](/help/getting-started/cja-aa.md)

Vous pouvez créer une plage de dates personnalisée en utilisant l’une des deux méthodes suivantes :

* Directement dans un projet d&#39;espace de travail en cliquant sur le bouton &quot;`+`&quot; en regard de la liste des composants de plage de dates sur la gauche
* Dans le gestionnaire de plage de dates

Pour créer une plage de dates dans le gestionnaire de plages de dates :

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Accédez à [!UICONTROL Composants] > [!UICONTROL Périodes].
1. Cliquez sur le bouton [!UICONTROL Ajouter] pour ouvrir la fenêtre modale qui crée une plage de dates.

## Créer une fenêtre modale de plage de dates

La fenêtre modale comprend quatre champs que vous pouvez modifier :

* **Période**: Plage de dates que vous souhaitez pour ce composant.
* **Titre**: Nom de ce composant. Le titre est utilisé dans les projets d’espace de travail.
* **Description**: Description de ce composant. La description s’affiche lorsque vous cliquez sur l’icône ![i](../assets/i.png) .
* **Balises**: Utilisez des balises pour organiser vos plages de dates. Une plage de dates peut appartenir à plusieurs balises.

## Sélection d’une plage de dates

Lorsque vous cliquez sur la plage de dates dans la fenêtre modale, vous disposez de plusieurs options :

* **Calendrier**: Sélectionnez le début et la date de fin.
* **Utiliser des dates** roulantes : Cochez cette case si vous souhaitez que la plage de dates change au fil du temps. Ne cochez pas cette case si vous souhaitez que la plage de dates reste statique.
* **Sélectionner un paramètre prédéfini**: Utilisez cette liste déroulante si vous souhaitez une plage de dates personnalisée basée sur une plage qui, par défaut, offre Adobe. Lorsque vous sélectionnez un paramètre prédéfini, vous pouvez personnaliser davantage la plage de dates en fonction de vos besoins. Il n’affecte pas le paramètre prédéfini que Adobe offre.

## Plages de dates flottantes

Si vous souhaitez une plage de dates variable, vous pouvez la personnaliser lorsqu’elle est lancée. Vous pouvez contrôler quand les dates de début et de fin se roulent indépendamment les unes des autres.

* **Lorsque la date début**: Choisissez si la date est début au début d’une période, à la fin d’une période ou utilisez un jour fixe.
* **Période à utiliser**: Choisissez la fréquence de roulement de la plage de dates. Vous pouvez le faire rouler chaque jour, chaque semaine, chaque mois, chaque trimestre ou chaque année.
* **Décalage**: Choisissez le décalage de la plage de dates. Vous pouvez ajouter ou soustraire des jours, semaines, mois, trimestres ou années.

## Exemples de dates flottantes

Certaines plages de dates peuvent s’avérer utiles dans certains rapports.

Année à jour :

```text
Start: Start of current year
End: End of current day
```

Jeudi dernier à ce jeudi :

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Exercice (par exemple, si un exercice financier se début en décembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
