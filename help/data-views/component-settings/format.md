---
title: 'Paramètres des composants : mise en forme'
description: Configurez la mise en forme dʼune mesure.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# Paramètres des composants : mise en forme {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="Mise en forme"
>abstract="Permet de déterminer l’affichage d’un composant lorsqu’il est utilisé dans des rapports."

<!-- markdownlint-enable MD034 -->


Le format vous permet de déterminer l’affichage d’un composant donné lorsqu’il est utilisé dans des rapports.

## Configuration des paramètres de format pour un composant

Vous pouvez déterminer l’affichage d’un composant donné en ajustant ses paramètres de format.

1. Dans Customer Journey Analytics, sélectionnez l’onglet [!UICONTROL **Vues de données**].

1. Sélectionnez la vue de données contenant le composant dont vous souhaitez configurer le paramètre de mise en forme.

1. Sélectionnez l’onglet [!UICONTROL **Composants**].

1. Sélectionnez le composant à configurer, puis développez la section [!UICONTROL **Format**] sur le côté droit de la page.

   ![Paramètres de mise en forme](../assets/format-settings.png)

1. Indiquez les informations suivantes :

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Format]** | Permet de spécifier la mise en forme d’un composant en tant que Décimale, Heure, Pourcentage ou Devise. |
   | **[!UICONTROL Décimal]** | Non visible sur les types de données du schéma entier. Permet de spécifier le nombre de décimales affichées par un composant. |
   | **[!UICONTROL Date]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date et heure]** | Permet de déterminer comment le champ de date et heure doit s’afficher lorsqu’il est utilisé comme dimension dans un rapport. [En savoir plus](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Devise]** | Permet de déterminer la devise dans laquelle vous souhaitez que le composant s’affiche. <p>Si vous analysez des données globales dans lesquelles les transactions sont effectuées dans différentes devises, reportez-vous à la section [Utiliser la conversion de devise](#use-currency-conversion).</p> |
   | **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Permet de spécifier si une tendance à la hausse de ce composant est bonne (verte) ou mauvaise (rouge). |
   | **[!UICONTROL Valeur « true »]** et **[!UICONTROL valeur « false »]** | Visible uniquement sur les types de données du schéma booléen. Permet de personnaliser le libellé de lʼélément de dimension pour les valeurs `true` et `false`. |

   {style="table-layout:auto"}

## Utilisation de la conversion de devise {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="Conversion des devises"
>abstract="Sélectionnez une dimension de code de devise pour configurer et afficher la devise dans le type choisi."

<!-- markdownlint-enable MD034 -->

La conversion de devises dans Customer Journey Analytics peut être extrêmement précieuse pour les entreprises qui opèrent à l’international. En éliminant la complexité de la conversion manuelle des devises, la conversion des devises dans Customer Journey Analytics apporte uniformité et clarté aux données financières. La conversion de devises effectue le suivi des taux de change historiques quotidiens et maintient ces taux quotidiens pendant une période de 4 ans.

Par exemple, si une entreprise de commerce électronique opère aux États-Unis, au Royaume-Uni et dans l’UE, les données de vente peuvent être automatiquement converties en dollars américains (USD), ce qui facilite la comparaison et la compréhension holistique des performances.

>[!NOTE]
>
>Avant de commencer à configurer une mesure pour la conversion des devises, tenez compte des points suivants :
>
>* La mesure sélectionnée pour la conversion des devises doit être de type numérique (Double, Long, Entier, Court, Octet).
>* Configurez votre connexion Customer Journey Analytics pour contenir au moins un jeu de données d’événement contenant une dimension de code de devise pour chaque événement contenant une mesure de devise. Cette dimension de code de devise utilise un code de devise alphabétique conforme à la norme [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) pour la représentation des devises. Ces valeurs doivent être en majuscules, par exemple USD pour $, EUR pour €, GBP pour £.

Pour déterminer comment les devises sont affichées et converties pour une mesure donnée, procédez comme suit :

1. Commencez à configurer la mesure pour laquelle vous souhaitez utiliser la devise comme mise en forme, comme décrit ci-dessus, dans [Configurer les paramètres de mise en forme pour une mesure](#configure-format-settings-for-a-metric).

1. Une fois la mesure sélectionnée, effectuez les sélections suivantes dans la section [!UICONTROL **Mise en forme**] sur le côté droit de la page :

   * Dans le champ [!UICONTROL **Mise en forme**], sélectionnez [!UICONTROL **Devise**].

   * Dans le champ [!UICONTROL **Nombre de décimales**], choisissez le nombre de décimales affichées par la mesure.

     Cette option n’est disponible que si la mesure est de type numérique « Double ».

   * Sélectionnez l’option [!UICONTROL **Convertir la devise**].

   * Dans le champ [!UICONTROL **Sélectionner la dimension du code de devise**], sélectionnez la dimension qui représente la devise à partir de laquelle vous convertissez (la devise sur laquelle vos données sont basées). Par exemple, sélectionnez une dimension appelée [!UICONTROL **Code de devise**].

     Si votre schéma de données actuel ne comporte pas de dimension contenant un champ de code de devise, vous pouvez créer un champ de code de devise à l’aide de [Préparation de données](https://experienceleague.adobe.com/fr/docs/experience-platform/data-prep/home), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=fr) ou [Champs dérivés](/help/data-views/derived-fields/derived-fields.md). La préparation des données ne convient que pour les nouvelles implémentations, car elle ne concerne que les opérations ultérieures. Selon la configuration d’une organisation, Data Distiller et les champs dérivés peuvent être utilisés pour accéder aux valeurs de code de devise de manière historique.

   * Dans le champ [!UICONTROL **Convertir et afficher la devise en**], choisissez la devise dans laquelle vous souhaitez que les données soient converties.

1. Répétez ces étapes si vous souhaitez appliquer une conversion de devise à des mesures supplémentaires.



### Questions fréquentes 

+++ Comment s’exécute la conversion de devise ?

Au moment du rapport, la valeur de la mesure et le code de devise d’origine sont convertis en USD, puis dans la devise configurée pour l’affichage. Pour cette conversion, les taux de change quotidiens sont utilisés, applicables pour l’heure de l’événement.

+++

