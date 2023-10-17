---
title: 'Paramètres des composants : mise en forme'
description: Configurez la mise en forme dʼune mesure.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 6945026bd452e1dabe90812f8d056f19aac71490
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 30%

---

# Paramètres des composants : mise en forme

La mise en forme vous permet de déterminer le mode dʼaffichage dʼune mesure donnée.

![Paramètres de mise en forme](../assets/format-settings.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Format]** | Permet de définir la mise en forme dʼune mesure, telle que la valeur décimale, la durée, le pourcentage ou la devise. |
| **[!UICONTROL Nombre de décimales]** | Non visible sur les types de données du schéma entier. Permet de définir le nombre de décimales quʼune mesure affiche. |
| **[!UICONTROL Date]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Date et heure]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Devise]** | Permet de déterminer la devise dans laquelle la mesure doit s’afficher. Voir [Devise](#currency) pour plus d’informations. |
| **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Permet de définir si une tendance à la hausse de cette mesure est bonne (verte) ou mauvaise (rouge). |
| **[!UICONTROL Valeur « true »]** et **[!UICONTROL valeur « false »]** | Visible uniquement sur les types de données du schéma booléen. Permet de personnaliser le libellé de lʼélément de dimension pour les valeurs `true` et `false`. |

{style="table-layout:auto"}

## Devise

Lorsque vous sélectionnez **[!UICONTROL Devise]** comme la propriété [!UICONTROL Format] pour une mesure, vous pouvez déterminer comment afficher et convertir des devises.

### Afficher la devise

Pour afficher une devise pour une mesure :

1. Saisissez le nombre de **[!UICONTROL Décimales]**.

1. Sélectionnez une devise dans le **[!UICONTROL Afficher la devise dans]** liste.


### Convertir et afficher la devise

Pour activer la conversion d’une devise pour une ou plusieurs mesures :

- Configurez votre connexion de Customer Journey Analytics pour qu’elle contienne au moins un jeu de données d’événement contenant une dimension de code de devise pour chaque événement contenant une mesure de devise. Cette dimension de code de devise utilise un code de devise alphabétique conforme au [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard pour représenter les devises. Ces valeurs doivent être en majuscules, telles que USD pour $, EUR pour €, GBP pour £.

   1. Sélectionnez la dimension de l’un de vos jeux de données contenant les codes de devise. Par exemple : [!UICONTROL Code de devise].

   1. Sélectionner **[!UICONTROL Code de devise]** dans la liste des dimensions.

- Répétez ces étapes si vous disposez d’autres dimensions contenant des codes de devise à utiliser pour la conversion de devise.

>[!NOTE]
>
>La mesure que vous sélectionnez pour la conversion de devise doit être de type numérique (Double, Long, Entier, Court, Octet).


Pour définir comment convertir et afficher une devise pour une mesure :

1. Saisissez le nombre de **[!UICONTROL Décimales]**.

1. Sélectionner **[!UICONTROL Conversion de devise]**.

1. Sélectionnez la dimension appropriée dans la liste des dimensions contenant le champ de code de devise.

1. Sélectionnez une devise dans le **[!UICONTROL Convertir et afficher la devise dans]** liste.

### Questions fréquentes 

+++ Comment la conversion de devise est-elle exécutée ?

Au moment du rapport, la valeur de la mesure et le code de devise d’origine sont convertis en USD, puis convertis dans la devise configurée pour l’affichage. Pour cette conversion, les taux de change de la devise quotidienne sont utilisés, applicables à la période de l’événement.

+++


+++ Jusqu’où les taux de conversion quotidiens sont-ils maintenus ?

Les taux de conversion quotidiens sont maintenus au cours des quatre dernières années ?

+++


+++ Que se passe-t-il si je n’ai pas de champ de code de devise dans mon schéma de données actuel ?

Il existe plusieurs options pour créer un champ de code de devise, notamment la préparation de données, le Distiller de données et les champs dérivés. La préparation des données est idéale pour les nouvelles mises en oeuvre, car elle ne sera proposée que sur une base continue. Selon la configuration d’une entreprise, Data Distiller et les champs dérivés peuvent être utilisés pour accéder historiquement aux valeurs de code de devise.

+++

