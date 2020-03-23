---
title: Création d’une plage de dates
description: Créez une plage de dates à utiliser dans les .
translation-type: tm+mt
source-git-commit: 2452490cc2f147cfd87540a68be2d0c219d8744f

---


# Création d’une plage de dates

Vous pouvez créer une plage de dates personnalisée à l’aide de l’une des deux méthodes suivantes :

* Directement dans un projet d’espace de travail en cliquant sur le bouton &quot;`+`&quot; en regard du des composants de plage de dates sur la gauche
* Dans le gestionnaire de plage de dates

Pour créer une plage de dates dans le gestionnaire de plages de dates :

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Accédez à [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Cliquez sur le [!UICONTROL Add] bouton pour ouvrir la fenêtre modale qui crée une plage de dates.

## Créer une fenêtre modale de plage de dates

La fenêtre modale comporte quatre champs que vous pouvez modifier :

* **Période**: Plage de dates que vous souhaitez pour ce composant.
* **Titre**: Nom de ce composant. Le titre est utilisé dans les projets d’espace de travail.
* **Description**: Description de ce composant. La description s’affiche lorsque vous cliquez sur l’icône ![i](../assets/i.png) .
* **Balises**: Utilisez des balises pour organiser vos plages de dates. Une plage de dates peut appartenir à plusieurs balises.

## Sélection d’une plage de dates

Lorsque vous cliquez sur la plage de dates dans la fenêtre modale, vous disposez de plusieurs options :

* **Calendrier**: Sélectionnez le  de et la date de fin.
* **Utiliser des dates** roulantes : Cochez cette case si vous souhaitez que la plage de dates change au fil du temps. Ne cochez pas cette case si vous souhaitez que votre plage de dates reste statique.
* **Sélectionner un paramètre prédéfini**: Utilisez cette liste déroulante si vous souhaitez une plage de dates personnalisée basée sur une plage que  Adobe  par défaut. Lorsque vous sélectionnez un paramètre prédéfini, vous pouvez personnaliser davantage la plage de dates en fonction de vos besoins. Elle n’affecte pas le paramètre prédéfini  par Adobe .

## Plages de dates flottantes

Si vous souhaitez une plage de dates flottante, vous pouvez la personnaliser lorsqu’elle s’affiche. Vous pouvez contrôler le moment où les dates de  et de fin se déroulent indépendamment les unes des autres.

* **Lorsque la date**: Choisissez si le de dates  au début d’une période, à la fin d’une période ou utilise un jour fixe.
* **Période à utiliser**: Choisissez la fréquence à laquelle la plage de dates se déroule. Vous pouvez le faire rouler tous les jours, toutes les semaines, tous les mois, tous les trimestres ou tous les ans.
* **Décalage**: Choisissez le décalage de la période. Vous pouvez ajouter ou soustraire des jours, des semaines, des mois, des trimestres ou des années.

## Exemples de dates flottantes

Certaines plages de dates peuvent s’avérer utiles dans certains rapports.

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

Exercice financier (par exemple, si un exercice  en décembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
