---
title: Créer des périodes
description: Créez une période à utiliser dans le compte rendu des performances.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 97%

---

# Créer des périodes


Tout le monde peut créer une période personnalisée. Pour créer une période, procédez comme suit :

![Création d’une annotation](assets/create-date-range.png)

* **A** - Dans l’interface principale, sélectionnez **[!UICONTROL Composants]**, puis **[!UICONTROL Période]**. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** dans le [[!UICONTROL gestionnaire de périodes]](/help/components/date-ranges/manage.md).
* **B** - Dans un projet Workspace, dans le menu contextuel d’une visualisation, sélectionnez **[!UICONTROL Période personnalisée à cette période]**.
* **C** - Dans un projet Workspace, sélectionnez **[!UICONTROL Composants]** dans le menu, puis **[!UICONTROL Créer une période]**.
* **D** - Dans un projet Workspace, utilisez le raccourci **[!UICONTROL Ctrl+Maj+D]** (Windows) ou **[!UICONTROL Shift+Commande+D]** (macOS).
* **E** - Dans un projet Workspace, dans le panneau de gauche Composants, sélectionnez ![Ajouter](/help/assets/icons/Add.svg), puis ![Calendrier](/help/assets/icons/Calendar.svg) **Périodes**.
* **F** - Dans une visualisation prise en charge, comme une visualisation en ligne, dans le menu contextuel d’un point de données, sélectionnez **[!UICONTROL Annoter la sélection]**.

Pour définir la période, utilisez le [[!UICONTROL Créateur de périodes]](#annotation-builder) :

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Créateur de période {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="Heure de fin"
>abstract="Les heures de fin comprennent toujours 59 secondes."

<!-- markdownlint-enable MD034 -->




La boîte de dialogue **[!UICONTROL Nouvelle période]** ou **[!UICONTROL Modifier la période]** permet de créer des périodes ou de modifier des périodes existantes.

![Fenêtre de détails des annotations présentant les champs et options décrits dans la section suivante.](assets/edit-date-range.png)


1. Spécifiez un **[!UICONTROL titre]** pour cette période. Par exemple, **[!UICONTROL Trimestriel]**.
1. Vous pouvez éventuellement spécifier une **[!UICONTROL Description]**.
1. Organisez le segment en créant ou en appliquant une ou plusieurs **[!UICONTROL Balises]**. Commencez à saisir du texte pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTRÉE]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une balise. |
1. Sélectionnez une **[!UICONTROL Période]** en sélectionnant d’abord la date de début, puis la date de fin.
Vous pouvez également sélectionner un **[!UICONTROL paramètre prédéfini]** dans le menu déroulant [!UICONTROL *Sélectionner un paramètre prédéfini*].

1. Vous pouvez également sélectionner **[!UICONTROL Afficher les paramètres avancés]** pour :

   * Spécifier une **[!UICONTROL heure de départ]** et une **[!UICONTROL heure de fin]** différentes de celles par défaut, à savoir `12:00 AM` (`0:00`) et `11:59 PM` (`23:59`). Les heures de fin comprennent toujours 59 secondes. Pour une période qui s’étend sur plusieurs jours, l’heure de début s’applique au premier jour de la période et l’heure de fin s’applique au dernier jour de la période. Utilisez **[!UICONTROL (Réinitialiser les heures)]** pour réinitialiser les heures de début et de fin à leurs valeurs par défaut.
   * **[!UICONTROL Utilisation de dates glissantes]**. Si cette option est activée, les périodes prédéfinies telles que **[!UICONTROL 7 derniers jours complets]** se mettent dynamiquement à jour en fonction de l’évolution de la date et de l’heure actuelles. Si cette option est désactivée, ces paramètres prédéfinis ne sont pas mis à jour une fois appliqués.

     Vous pouvez sélectionner le texte entre parenthèses (par exemple : **[!UICONTROL début fixe - dates glissantes chaque trimestre]**) pour étendre le panneau et spécifier des détails pour **[!UICONTROL Début]** et **[!UICONTROL Fin]**.

     ![Dates glissantes](assets/rolliing-dates.png)

      1. Sélectionnez **[!UICONTROL Début de]**, **[!UICONTROL Fin de]** ou **[!UICONTROL Jour fixe]**.
      1. Lorsque vous avez sélectionné **[!UICONTROL Début de]** ou **[!UICONTROL Fin de]**, vous pouvez créer une expression complète. Par exemple : **[!UICONTROL Fin de]** **[!UICONTROL trimestre en cours]** **[!UICONTROL moins]** `20` **[!UICONTROL jours]**. Sélectionnez la valeur appropriée pour chaque partie de l’expression.
         * Sélectionnez une valeur pour la période actuelle. Par exemple, **[!UICONTROL trimestre en cours]**.
         * Sélectionnez une valeur pour le calcul supplémentaire. Par exemple, **[!UICONTROL moins]**.
         * Lorsque vous avez spécifié un calcul supplémentaire, indiquez une valeur. Par exemple : `20`.
         * Lorsque vous avez spécifié un calcul supplémentaire, sélectionnez la période à utiliser pour le calcul. Par exemple, **[!UICONTROL jours]**.

     Sélectionnez **[!UICONTROL Masquer les détails]** pour masquer les détails du calcul des dates glissantes.

1. Sélectionner :
   * **[!UICONTROL Enregistrer]** pour enregistrer la période.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie de la période.
   * **[!UICONTROL Annuler]** pour annuler toute modification apportée à la période ou annuler la création d’une période.


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->
