---
title: Création d’une plage de dates
description: Créez une période à utiliser dans le compte rendu des performances.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 6%

---

# Création d’une plage de dates


N’importe qui peut créer une période personnalisée. Vous pouvez créer une période de la manière suivante :

![Créer une annotation](assets/create-date-range.png)

* ?? Dans l’interface principale, sélectionnez **[!UICONTROL Composants]** et sélectionnez **[!UICONTROL Période]**. Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL ****] dans le [[!UICONTROL gestionnaire de plage de dates]](/help/components/date-ranges/manage.md).
* ?? Dans un projet Workspace, dans le menu contextuel d’une visualisation, sélectionnez **[!UICONTROL Période personnalisée jusqu’à cette période]**.
* ?? Dans un projet Workspace, sélectionnez **[!UICONTROL Components]** dans le menu, puis **[!UICONTROL Créer une plage de dates]**
* ?? Dans un projet Workspace, utilisez le raccourci **[!UICONTROL ctrl+maj+d]** (Windows) ou **[!UICONTROL shift+commande+d]** (macOS).
* ?? Dans un projet Workspace, dans le panneau de gauche Composants, sélectionnez ![Ajouter](/help/assets/icons/Add.svg) dans ![Calendrier](/help/assets/icons/Calendar.svg) **Plages de dates**.

Pour définir l’annotation, utilisez le [[!UICONTROL créateur de plages de dates]](#annotation-builder) :

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Créateur de plages de dates {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_dateranges_endtime"
>title="Heure de fin"
>abstract="Les heures de fin comprennent toujours 59 secondes."

<!-- markdownlint-enable MD034 -->




La boîte de dialogue **[!UICONTROL Nouvelle plage de dates]** ou **[!UICONTROL Modifier la plage de dates]** est utilisée pour créer ou modifier des plages de dates existantes.

![Fenêtre de détails des annotations présentant les champs et options décrits dans la section suivante.](assets/edit-date-range.png)


1. Spécifiez un **[!UICONTROL titre]** pour la période. Par exemple, **[!UICONTROL Trimestriel]**.
1. Vous pouvez éventuellement spécifier une **[!UICONTROL description]**.
1. Organisez le filtre en créant ou en appliquant une ou plusieurs **[!UICONTROL balises]**. Commencez à saisir pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTER]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une balise. |
1. Sélectionnez une **[!UICONTROL plage de dates]** en sélectionnant d’abord la date de début, puis la date de fin.
Vous pouvez également sélectionner un **[!UICONTROL paramètre prédéfini]** dans le menu déroulant [!UICONTROL *Sélectionner un paramètre prédéfini*] .

1. Si vous le souhaitez, sélectionnez **[!UICONTROL Afficher les paramètres avancés]** pour :

   * Spécifiez les **[!UICONTROL Heure de début]** et **[!UICONTROL Heure de fin]** autres que le `12:00 AM` par défaut (`0:00`) et `11:59 PM` (`23:59`). Les heures de fin comprennent toujours 59 secondes. Pour une période qui s’étend sur plusieurs jours, l’heure de début s’applique au premier jour de la période et l’heure de fin s’applique au dernier jour de la période. Utilisez **[!UICONTROL (Réinitialiser les valeurs temporelles)]** pour réinitialiser les heures de début et de fin par défaut.
   * **[!UICONTROL Utiliser des dates roulantes]**. Si cette option est activée, les plages de dates prédéfinies telles que **[!UICONTROL 7 derniers jours complets]** sont mises à jour dynamiquement en tant que date et heure actuelles. Si cette option est désactivée, ces paramètres prédéfinis ne sont pas mis à jour une fois appliqués.

     Vous pouvez sélectionner le texte entre crochets (par exemple **[!UICONTROL démarrage fixe - roulement trimestriel]**) pour étendre le panneau et spécifier les détails pour **[!UICONTROL Début]** et **[!UICONTROL Fin]**.

     ![Dates roulantes](assets/rolliing-dates.png)

      1. Sélectionnez **[!UICONTROL Début de]**, **[!UICONTROL Fin de]** ou **[!UICONTROL Jour fixe]**.
      1. Lorsque vous avez sélectionné **[!UICONTROL Début de]** ou **[!UICONTROL Fin de]**, vous pouvez créer une expression complète. Par exemple : **[!UICONTROL Fin de]** **[!UICONTROL trimestre actuel]** **[!UICONTROL moins]** `20` **[!UICONTROL jours]**. Sélectionnez la valeur appropriée pour chaque partie de l’expression.
         * Sélectionnez une valeur pour la valeur actuelle. Par exemple, **[!UICONTROL trimestre actuel]**.
         * Sélectionnez une valeur pour un calcul supplémentaire. Par exemple, **[!UICONTROL moins]**.
         * Lorsque vous avez spécifié un calcul supplémentaire, indiquez une valeur. Par exemple : `20`.
         * Lorsque vous avez spécifié un calcul supplémentaire, sélectionnez la période à utiliser pour le calcul. Par exemple, **[!UICONTROL days]**.

     Sélectionnez **[!UICONTROL Masquer les détails]** pour masquer les détails du calcul des dates roulantes.

1. Sélectionner :
   * **[!UICONTROL Enregistrer]** pour enregistrer la période.
   * **[!UICONTROL Enregistrer sous]** pour enregistrer une copie de la période.
   * **[!UICONTROL Annuler]** pour annuler toute modification apportée à la période ou annuler la création d’une nouvelle période.


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