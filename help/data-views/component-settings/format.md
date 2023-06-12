---
title: 'Paramètres des composants : mise en forme'
description: Configurez la mise en forme dʼune mesure.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: a3fea05ac95407c7f3bee723a267ae0bc03d334a
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 32%

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
| **[!UICONTROL Devise]** | Permet de déterminer la devise dans laquelle la mesure doit s’afficher. Voir [Devise](#currency) plus de détails. |
| **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Permet de définir si une tendance à la hausse de cette mesure est bonne (verte) ou mauvaise (rouge). |
| **[!UICONTROL Valeur « true »]** et **[!UICONTROL valeur « false »]** | Visible uniquement sur les types de données du schéma booléen. Permet de personnaliser le libellé de lʼélément de dimension pour les valeurs `true` et `false`. |

{style="table-layout:auto"}


## Devise

Lorsque vous sélectionnez **[!UICONTROL Devise]** comme la propriété [!UICONTROL Format] pour une mesure, vous pouvez déterminer comment afficher et convertir des devises.

### Afficher la devise

Pour afficher une devise pour une mesure :

1. Saisissez le nombre de **[!UICONTROL Nombre de décimales]**.

2. Sélectionnez une devise dans le **[!UICONTROL Afficher la devise dans]** liste.


### Convertir et afficher la devise

[!BADGE Nouvelle fonctionnalité]{type=Positive}

{{release-limited-testing-section}}

Pour activer la conversion d’une devise pour une mesure :

- Configurez votre connexion CJA pour qu’elle contienne au moins un jeu de données d’événement contenant une dimension de code de devise pour chaque événement contenant une mesure de devise. Cette dimension de code de devise utilise un code de devise alphabétique conforme à la variable [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard pour représenter les devises. Par exemple USD pour $, EUR pour €, GBP pour £.

- Vous avez (éventuellement) appliqué la variable [!UICONTROL Code de devise] libellé contextuel à une ou plusieurs dimensions qui définissent des codes de devise disponibles dans votre jeu de données.

  Pour appliquer la variable [!UICONTROL Code de devise] libellé contextuel, dans la propriété [!UICONTROL Composants] de votre vue de données :

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. Sélectionnez la dimension de l’un de vos jeux de données contenant les codes de devise. Par exemple : [!UICONTROL Code de devise].

   2. Sélectionner **[!UICONTROL Code de devise]** de la [!UICONTROL Étiquettes contextuelles] liste.

  Répétez ces étapes si vous disposez d’autres dimensions contenant des codes de devise à utiliser pour la conversion de devise.

>[!NOTE]
>
>La mesure que vous sélectionnez pour la conversion de devise doit être de type numérique (Double, Long, Entier, Court, Octet).


Pour définir comment convertir et afficher une devise pour une mesure :

1. Saisissez le nombre de **[!UICONTROL Nombre de décimales]**.

2. Sélectionner **[!UICONTROL Conversion de devise]**.

3. Selon le libellé de contexte appliqué, la dimension appropriée de la variable **[!UICONTROL Dimension Code de devise]** La liste est automatiquement sélectionnée. Vous pouvez sélectionner toute autre dimension, y compris les dimensions auxquelles vous avez en outre appliqué le libellé contextuel Code de devise .

4. Sélectionnez une devise dans le **[!UICONTROL Convertir et afficher la devise dans]** liste.

### Questions fréquentes 

+++ Comment la conversion de devise est-elle exécutée ?

Au moment du rapport, la valeur de la mesure et le code de devise d’origine sont convertis en USD, puis convertis dans la devise configurée pour l’affichage. Pour cette conversion, les taux de change de la devise quotidienne sont utilisés, applicables à la période de l’événement.

+++

