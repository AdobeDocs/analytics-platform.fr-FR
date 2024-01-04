---
title: 'Paramètres des composants : mise en forme'
description: Configurez la mise en forme dʼune mesure.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 19%

---

# Paramètres des composants : mise en forme

Le format vous permet de déterminer l’affichage d’une mesure donnée lorsqu’elle est utilisée dans des rapports.

## Configuration des paramètres de format d’une mesure

Vous pouvez déterminer le mode d’affichage d’une mesure donnée en ajustant ses paramètres de format.

1. Dans Customer Journey Analytics, sélectionnez la variable [!UICONTROL **Vues des données**] .

1. Sélectionnez la vue de données contenant le composant dont vous souhaitez configurer le paramètre de format.

1. Sélectionnez l’onglet [!UICONTROL **Composants**].

1. Sélectionnez le composant que vous souhaitez configurer, puis développez la [!UICONTROL **Format**] sur le côté droit de la page.

   ![Paramètres de mise en forme](../assets/format-settings.png)

1. Indiquez les informations suivantes :

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Format]** | Permet de définir la mise en forme dʼune mesure, telle que la valeur décimale, la durée, le pourcentage ou la devise. |
   | **[!UICONTROL Décimal]** | Non visible sur les types de données du schéma entier. Permet de définir le nombre de décimales quʼune mesure affiche. |
   | **[!UICONTROL Date]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date et heure]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Devise]** | Permet de déterminer la devise dans laquelle la mesure doit s’afficher. <p>Si vous analysez des données globales dans lesquelles des transactions se produisent dans des devises différentes, reportez-vous à la section  [Utiliser la conversion de devise](#use-currency-conversion).</p> |
   | **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Permet de définir si une tendance à la hausse de cette mesure est bonne (verte) ou mauvaise (rouge). |
   | **[!UICONTROL Valeur « true »]** et **[!UICONTROL valeur « false »]** | Visible uniquement sur les types de données du schéma booléen. Permet de personnaliser le libellé de lʼélément de dimension pour les valeurs `true` et `false`. |

   {style="table-layout:auto"}

## Utiliser la conversion de devise

La conversion de devises en Customer Journey Analytics peut s’avérer extrêmement précieuse pour les entreprises opérant à l’échelle internationale. En supprimant les complexités de la conversion manuelle de devises, la conversion de devises en Customer Journey Analytics apporte uniformité et clarté aux données financières. La conversion de devise effectue le suivi des taux de change historiques quotidiens et maintient ces taux quotidiens sur une période de 4 ans.

Par exemple, si une entreprise d’e-commerce opère aux États-Unis, au Royaume-Uni et dans l’UE, les données de vente peuvent être automatiquement converties en USD, ce qui permet une comparaison facile et une compréhension holistique des performances.

>[!NOTE]
>
>Avant de commencer à configurer une mesure pour la conversion de devise, tenez compte des points suivants :
>
>* La mesure que vous sélectionnez pour la conversion de devise doit être de type numérique (Double, Long, Entier, Court, Octet).
>* Configurez votre connexion de Customer Journey Analytics pour qu’elle contienne au moins un jeu de données d’événement contenant une dimension de code de devise pour chaque événement contenant une mesure de devise. Cette dimension de code de devise utilise un code de devise alphabétique conforme au [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard pour représenter les devises. Ces valeurs doivent être en majuscules, telles que USD pour $, EUR pour €, GBP pour £.

Pour déterminer le mode d’affichage et de conversion des devises pour une mesure donnée :

1. Commencez à configurer la mesure pour laquelle vous souhaitez utiliser la devise comme format, comme décrit ci-dessus, dans [Configuration des paramètres de format d’une mesure](#configure-format-settings-for-a-metric).

1. Lorsque la mesure est sélectionnée, effectuez les sélections suivantes dans la variable [!UICONTROL **Format**] sur le côté droit de la page :

   * Dans le [!UICONTROL **Format**] champ, sélectionnez [!UICONTROL **Devise**].

   * Dans le [!UICONTROL **Décimales**] , choisissez le nombre de décimales que la mesure affiche.

     Cette option est disponible uniquement si la mesure possède un type numérique &quot;Double&quot;.

   * Sélectionnez la variable [!UICONTROL **Convertir une devise**] .

   * Dans le [!UICONTROL **Sélection de la dimension Code de devise**] , sélectionnez la dimension qui représente la devise à partir de laquelle vous effectuez la conversion (la devise sur laquelle vos données sont basées). Par exemple, sélectionnez une dimension appelée [!UICONTROL **Code de devise**].

     Si votre schéma de données actuel ne contient pas de dimension contenant un champ de code de devise, vous pouvez créer un champ de code de devise à l’aide de la commande [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=fr), [Distiller de données](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html), ou [Champs dérivés](/help/data-views/derived-fields/derived-fields.md). La préparation des données ne convient qu’aux nouvelles mises en oeuvre, car elle ne s’effectue qu’à partir d’une base de données. Selon la configuration d’une entreprise, Data Distiller et les champs dérivés peuvent être utilisés pour accéder historiquement aux valeurs de code de devise.

   * Dans le [!UICONTROL **Convertir et afficher la devise dans**] , choisissez la devise dans laquelle vous souhaitez que les données soient converties.

1. Répétez ces étapes si vous souhaitez appliquer une conversion de devise à des mesures supplémentaires.



### Questions fréquentes 

+++ Comment la conversion de devise est-elle exécutée ?

Au moment du rapport, la valeur de la mesure et le code de devise d’origine sont convertis en USD, puis convertis dans la devise configurée pour l’affichage. Pour cette conversion, les taux de change de la devise quotidienne sont utilisés, applicables à la période de l’événement.

+++

