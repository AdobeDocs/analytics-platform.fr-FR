---
title: 'Paramètres des composants : mise en forme'
description: Configurez la mise en forme dʼune mesure.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 23%

---

# Paramètres des composants : mise en forme {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_format"
>title="Format"
>abstract="Permet de déterminer l’affichage d’un composant lorsqu’il est utilisé dans des rapports."

<!-- markdownlint-enable MD034 -->


Le format vous permet de déterminer l’affichage d’une mesure donnée lorsqu’elle est utilisée dans des rapports.

## Configuration des paramètres de format d’une mesure

Vous pouvez déterminer le mode d’affichage d’une mesure donnée en ajustant ses paramètres de format.

1. Dans Customer Journey Analytics, sélectionnez l’onglet [!UICONTROL **Vues de données**] .

1. Sélectionnez la vue de données contenant le composant dont vous souhaitez configurer le paramètre de format.

1. Sélectionnez l’onglet [!UICONTROL **Composants**].

1. Sélectionnez le composant à configurer, puis développez la section [!UICONTROL **Format**] sur le côté droit de la page.

   ![Paramètres de mise en forme](../assets/format-settings.png)

1. Indiquez les informations suivantes :

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Format]** | Permet de définir la mise en forme dʼune mesure, telle que la valeur décimale, la durée, le pourcentage ou la devise. |
   | **[!UICONTROL Décimal]** | Non visible sur les types de données du schéma entier. Permet de définir le nombre de décimales quʼune mesure affiche. |
   | **[!UICONTROL Date]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date et heure]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Devise]** | Permet de déterminer la devise dans laquelle la mesure doit s’afficher. <p>Si vous analysez des données globales dans lesquelles des transactions se produisent dans différentes devises, reportez-vous à la section [Utiliser la conversion de devise](#use-currency-conversion).</p> |
   | **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Permet de définir si une tendance à la hausse de cette mesure est bonne (verte) ou mauvaise (rouge). |
   | **[!UICONTROL Valeur « true »]** et **[!UICONTROL valeur « false »]** | Visible uniquement sur les types de données du schéma booléen. Permet de personnaliser le libellé de lʼélément de dimension pour les valeurs `true` et `false`. |

   {style="table-layout:auto"}

## Utilisation de la conversion de devise {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_format_currencyconversion"
>title="Conversion des devises"
>abstract="Sélectionnez une dimension de code de devise pour configurer et afficher la devise dans le type choisi."

<!-- markdownlint-enable MD034 -->

La conversion de devises en Customer Journey Analytics peut s’avérer extrêmement précieuse pour les entreprises opérant à l’échelle internationale. En supprimant les complexités de la conversion manuelle de devises, la conversion de devises en Customer Journey Analytics apporte uniformité et clarté aux données financières. La conversion de devise effectue le suivi des taux d’exchange historiques quotidiens et maintient ces taux quotidiens sur une période de 4 ans.

Par exemple, si une entreprise d’e-commerce opère aux États-Unis, au Royaume-Uni et dans l’UE, les données de vente peuvent être automatiquement converties en USD, ce qui permet une comparaison facile et une compréhension holistique des performances.

>[!NOTE]
>
>Avant de commencer à configurer une mesure pour la conversion de devise, tenez compte des points suivants :
>
>* La mesure que vous sélectionnez pour la conversion de devise doit être de type numérique (Double, Long, Entier, Court, Octet).
>* Configurez votre connexion de Customer Journey Analytics pour qu’elle contienne au moins un jeu de données d’événement contenant une dimension de code de devise pour chaque événement contenant une mesure de devise. Cette dimension de code de devise utilise un code de devise alphabétique conforme à la norme [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) pour représenter les devises. Ces valeurs doivent être en majuscules, telles que USD pour $, EUR pour €, GBP pour £.

Pour déterminer le mode d’affichage et de conversion des devises pour une mesure donnée :

1. Commencez à configurer la mesure pour laquelle vous souhaitez utiliser la devise comme format, comme décrit ci-dessus, dans [Configuration des paramètres de format pour une mesure](#configure-format-settings-for-a-metric).

1. Une fois la mesure sélectionnée, effectuez les sélections suivantes dans la section [!UICONTROL **Format**] sur le côté droit de la page :

   * Dans le champ [!UICONTROL **Format**], sélectionnez [!UICONTROL **Devise**].

   * Dans le champ [!UICONTROL **Nombre de décimales**], choisissez le nombre de décimales que la mesure affiche.

     Cette option est disponible uniquement si la mesure possède un type numérique &quot;Double&quot;.

   * Sélectionnez l’option [!UICONTROL **Convertir la devise**] .

   * Dans le champ [!UICONTROL **Sélectionner la dimension de code de devise**], sélectionnez la dimension qui représente la devise à partir de laquelle vous effectuez la conversion (la devise sur laquelle reposent vos données). Par exemple, sélectionnez une dimension appelée [!UICONTROL **Code de devise**].

     Si votre schéma de données actuel ne contient pas de dimension contenant un champ de code de devise, vous pouvez créer un champ de code de devise à l’aide de [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) ou [Derived Fields](/help/data-views/derived-fields/derived-fields.md). La préparation des données ne convient qu’aux nouvelles mises en oeuvre, car elle ne s’effectue qu’à partir d’une base de données. Selon la configuration d’une entreprise, Data Distiller et les champs dérivés peuvent être utilisés pour accéder historiquement aux valeurs de code de devise.

   * Dans le champ [!UICONTROL **Convertir et afficher la devise dans**], sélectionnez la devise dans laquelle vous souhaitez convertir les données.

1. Répétez ces étapes si vous souhaitez appliquer une conversion de devise à des mesures supplémentaires.



### Questions fréquentes 

+++ Comment la conversion de devise est-elle exécutée ?

Au moment du rapport, la valeur de la mesure et le code de devise d’origine sont convertis en USD, puis convertis dans la devise configurée pour l’affichage. Pour cette conversion, les taux d’exchange de la devise quotidienne sont utilisés, applicables à la période de l’événement.

+++

