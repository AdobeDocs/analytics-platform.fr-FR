---
description: Comment spécifier des dates et des périodes, ou sélectionner un paramètre prédéfini.
title: Calendrier et périodes - Aperçu
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
role: User
source-git-commit: 47b7747b37f82e4d75d5272ce1d8d37f4e497bb5
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 75%

---

# Calendrier et périodes - Aperçu

Avec le calendrier, vous pouvez spécifier des dates et des plages de dates, ou sélectionner un paramètre prédéfini. Les périodes correspondent à un type de composant que vous pouvez utiliser dans les projets Workspace. Elles vous permettent d’afficher les tendances des données au fil du temps ou de déterminer à quel moment les événements se produisent le plus. Les plages de dates sont codées par couleur en violet. Les périodes personnalisées vous permettent de personnaliser les dates affichées dans les projets Workspace.

Les sélections du calendrier s’appliquent par défaut au panneau seulement, mais vous pouvez aussi les appliquer à l’ensemble des panneaux. Lorsque vous cliquez sur une période dans Workspace, l’interface affiche le mois civil en cours et le mois civil précédent. Vous pouvez ajuster ces deux calendriers en cliquant sur les flèches droite et gauche dans chaque coin supérieur respectif.

![Calendrier affichant octobre 2022 et novembre 2022 avec sélection du 1er au 30 novembre.](assets/aw_calendar2.png){width="60%"}

Le premier clic sur un calendrier démarre une sélection de période. Le deuxième clic termine une sélection de période, qui devient surlignée. Si la touche `Shift` est enfoncée (ou si un clic droit est utilisé), elle est ajoutée à la période actuellement sélectionnée.

Vous pouvez également faire glisser des dates (et des dimensions temporelles) dans un projet Workspace. Sélectionnez des jours, des semaines, des mois ou des années spécifiques ou encore une date variable.

[Utilisation des périodes et des calendriers dans Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=fr) (4:07)

| Paramètre | Description |
| --- | --- |
| Jours sélectionnés | Jours/semaines/mois/années sélectionné(e)s |
| Utiliser les dates flottantes | Grâce aux dates de déploiement, vous pouvez générer un rapport dynamique qui recherche une période donnée, en amont ou en aval, en fonction de la date d’exécution du rapport. Si, par exemple, vous souhaitez générer en décembre un rapport sur toutes les commandes passées le mois dernier (d’après le champ Date de création), les commandes passées en novembre seront incluses dans le rapport. Si vous exécutez ce même rapport en janvier, vous verrez les commandes passées en décembre.<ul><li>**[!UICONTROL Aperçu de la date]** : indique la période englobée par le calendrier variable.</li><li>**[!UICONTROL Début]** : choisissez parmi aujourd’hui, semaine en cours, mois en cours, trimestre en cours et année en cours.</li><li>**[!UICONTROL Fin]** : choisissez parmi aujourd’hui, semaine en cours, mois en cours, trimestre en cours et année en cours.</li></ul>Pour consulter un exemple, suivez [ce lien](/help/components/date-ranges/custom-date-ranges.md). |
| Période | Permet de sélectionner une période prédéfinie. Par défaut : 30 derniers jours. **[!UICONTROL Cette semaine, ce mois, ce trimestre ou cette année (aujourd’hui non inclus)]** vous permet de choisir parmi des périodes qui n’incluent pas de données de la journée partielle d’aujourd’hui. |
| Appliquer à tous les panneaux | Permet de modifier la période sélectionnée pour le panneau en cours ainsi que pour tous les autres panneaux du projet. |
| Appliquer | Applique la période à ce panneau seulement. |

## À propos des périodes relatives du panneau {#relative-panel-dates}

Si vous travaillez dans un espace de travail, vous pouvez créer des composants de période par rapport au calendrier du panneau. Trois cas d’utilisation courants où les dates relatives du panneau prennent effet sont les graphiques combinés, le résumé des mesures clés et les périodes de tableau à structure libre.

Pour utiliser des périodes relatives du panneau

1. Sélectionnez l’onglet **Workspace**.
1. Sélectionnez **Projet vierge**.
1. Ajoutez des dimensions, des mesures et des filtres à partir du rail de gauche.
1. Cliquez sur le champ Période du panneau pour activer/désactiver le paramètre de période relative du panneau.
1. Sélectionnez **Créer des composants de période par rapport au calendrier du panneau**.
   * Sélectionnez l’option pour créer des composants de période par rapport au calendrier du panneau.
Si des dates relatives sont sélectionnées, les dates flottantes sont basées sur la date de début du calendrier du panneau au lieu de celle d’aujourd’hui.
   * Si cette option n’est pas sélectionnée, les dates flottantes seront basées sur la date d’aujourd’hui.

   ![Calendrier avec Rendre les composants de période par rapport au calendrier du panneau sélectionné](assets/relative-date-selected.png){width="60%"}

1. Cliquez sur **Appliquer**.
Les dates relatives s’affichent dans le coin supérieur droit.

   ![Tableau à structure libre avec dates relatives surlignées et affichage le mois dernier en surbrillance. ](assets/relative-date-range1.png)

## Instructions relatives aux périodes relatives de panneau {#guidelines}

Gardez à l’esprit les instructions suivantes lorsque vous utilisez des périodes relatives de panneau.

### Formules et périodes relatives {#formula-relative-dates}

Si des dates relatives sont sélectionnées, toutes les formules de date utiliseront la date de début du panneau comme point de départ.

### Calendriers personnalisés et périodes relatives {#custom-calendar-formulas}

Lorsque vous utilisez un calendrier personnalisé basé sur une semaine et que vous ajoutez des mois ou des années, la formule calcule le décalage du jour au cours de la période donnée. La date réelle peut être différente en raison du décalage. La formule sélectionne un jour qui se trouve au même endroit que le calendrier personnalisé. Par exemple, le troisième vendredi de la troisième semaine dans un calendrier personnalisé.

### À propos des filtres qui utilisent des dates roulantes et des plages de dates relatives de panneaux {#segments-relative-dates}

Si vous créez un filtre ou utilisez un filtre avec une date variable, par exemple les 7 derniers jours ou les 2 dernières semaines, et que vous cliquez sur l’aperçu du filtre, la date variable commencera à partir de *Aujourd’hui* au lieu de la date de début du panneau. Par conséquent, l’aperçu du filtre ne correspond pas lorsque vous utilisez réellement le filtre dans le tableau. L’aperçu est impacté, pas le filtre lui-même.

## Instructions relatives aux périodes et aux aperçus de panneau {#guidelines-panel-dates}

* À compter de la version de février, les aperçus de composants et de données seront basés sur la période du panneau et non sur les 90 derniers jours.
* Tous les composants répertoriés dans le rail de gauche seront disponibles en fonction de la période du panneau.
* Tous les aperçus de date dans le filtre et les créateurs de mesures calculées seront basés sur la période du panneau (sauf si vous y accédez à partir des gestionnaires de composants, qui n’ont pas de panneau associé, ils seront toujours basés sur les 90 derniers jours).
* Tous les aperçus de données affichent des données ou des composants en fonction de la période du panneau.