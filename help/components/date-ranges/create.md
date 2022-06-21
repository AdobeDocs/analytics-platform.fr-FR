---
title: Création d’une plage de dates
description: Créez une période à utiliser dans le compte rendu des performances.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 100%

---

# Création d’une plage de dates

Vous pouvez créer une période personnalisée à lʼaide de lʼune des deux méthodes suivantes :

* Directement dans un projet Workspace en cliquant sur le bouton « `+` » en regard de la liste des composants de période sur la gauche.
* Dans le gestionnaire des périodes

Pour créer une période dans le gestionnaire des périodes :

1. Connectez-vous à [analytics.adobe.com](https://analytics.adobe.com) à lʼaide de vos identifiants Adobe ID.
1. Accédez à [!UICONTROL Composants] > [!UICONTROL Périodes].
1. Cliquez sur le bouton [!UICONTROL Ajouter] pour ouvrir la fenêtre modale de création de période.

## Création dʼune fenêtre modale de période

La fenêtre modale comporte quatre champs que vous pouvez modifier :

* **Période** : période que vous souhaitez pour ce composant.
* **Titre** : nom que vous souhaitez donner à ce composant. Le titre est utilisé dans les projets Workspace.
* **Description** : description que vous souhaitez pour ce composant. La description sʼaffiche lorsque vous cliquez sur lʼicône ![i](../assets/i.png).
* **Balises** : utilisez les balises pour organiser vos périodes. Une période peut être associée à plusieurs balises.

## Sélection dʼune période

Lorsque vous cliquez sur la période dans la fenêtre modale, plusieurs options sʼoffrent à vous :

* **Calendrier** : sélectionnez les dates de début et de fin.
* **Utiliser les dates flottantes** : cochez cette case si vous souhaitez que la période soit modifiée au fil du temps. Ne cochez pas cette case si vous souhaitez que votre période reste statique.
* **Sélectionner un paramètre prédéfini** : utilisez cette liste déroulante si vous souhaitez une période personnalisée basée sur une période proposée par défaut par Adobe. Lorsque vous sélectionnez un paramètre prédéfini, vous pouvez personnaliser davantage la période en fonction de vos besoins. Cela nʼaffecte pas le paramètre prédéfini proposé par Adobe.

## Périodes flottantes

Si vous souhaitez utiliser une période flottante, vous pouvez personnaliser sa date de début. Vous pouvez décider des dates de début et de fin indépendamment les unes des autres.

* **Au commencement de la date** : choisissez si la date commence au début ou à la fin dʼune période ou utilisez un jour fixe.
* **La période à utiliser** : sélectionnez la fréquence dʼexécution de la période. La période peut sʼexécuter tous les jours, toutes les semaines, tous les mois, tous les trimestres ou tous les ans.
* **Décalage** : sélectionnez le décalage de la période. Vous pouvez ajouter ou soustraire des jours, semaines, mois, trimestres ou années.

## Exemples de dates flottantes

Certaines périodes peuvent sʼavérer utiles dans certains rapports.

Depuis le début de lʼannée :

```text
Start: Start of current year
End: End of current day
```

De jeudi dernier à ce jeudi :

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Exercice financier (par exemple, si un exercice commence en décembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
