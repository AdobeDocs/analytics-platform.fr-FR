---
description: Recevez des alertes lorsque les composants du projet atteignent certains seuils.
title: Créer des alertes
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 96%

---

# Créer des alertes {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularité temporelle"
>abstract="La granularité temporelle fait référence à la fréquence de vérification de l’alerte et à ce qui sera inclus."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un package Customer Journey Analytics Prime ou Ultimate.

Les alertes dans Customer Journey Analytics envoient un avertissement en fonction de pourcentages ou de points de données spécifiques modifiés. Selon votre package Customer Journey Analytics, vous pouvez également déclencher les alertes en fonction des seuils d’anomalie.

Pour plus d’informations sur les alertes, consultez [Vue d’ensemble des alertes](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Pour créer une alerte, procédez comme suit :

1. Dans Customer Journey Analytics, <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" -->, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Alertes]**. Dans le [Gestionnaire d’alertes](alert-manager.md), sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** pour créer une alerte ou sélectionnez l’une des alertes répertoriées pour modifier une alerte existante.

   L’interface [Créateur d’alertes](#alert-builder) s’affiche.

1. Sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer l’alerte. Sélectionnez **[!UICONTROL Enregistrer sous]** pour enregistrer une copie de l’alerte.


## Créateur d’alertes

Les utilisateurs et utilisatrices qui ont déjà créé des segments ou calculé des mesures dans Customer Journey Analytics ne seront pas dépaysés par l’interface du créateur d’alertes :

![Interface du créateur d’alertes](assets/alert-builder.png)

Spécifiez les informations suivantes dans le créateur d’alertes pour une alerte :

| Élément | Description |
|---------|----------|
| **[!UICONTROL Titre]** | Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures. |
| **[!UICONTROL Description (facultatif)]** | Spécifiez une description de l’alerte. |
| **[!UICONTROL Granularité temporelle]** | Spécifiez quand vérifier la mesure : chaque jour, chaque semaine ou chaque mois.<p><b>Note :</b> dans le créateur d’alertes, il n’est pas possible de sélectionner la granularité mensuelle pour les vues de données dotées d’un calendrier personnalisé.<!--true?--></p> |
| **[!UICONTROL Destinataires]** | Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse e-mail brute ou à un numéro de téléphone.<p><b>Important :</b> le numéro de téléphone doit être précédé d’un « + » et d’un [indicatif de pays](https://countrycode.org/).</p><p>L’e-mail qu’une personne reçoit une fois qu’une alerte a été déclenchée ressemble à ceci :</p><p>![E-mail d’alerte](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Date d’expiration]** | Définissez la date et l’heure d’expiration de l’alerte. |
| **[!UICONTROL Délai]** | Le temps nécessaire pour que les données soient complètes et disponibles pour faire l’objet de rapports dans Customer Journey Analytics varie selon l’entreprise, allant généralement de 3 à 9 heures après l’heure de l’événement de données. Pour que les alertes soient précises, les données d’événement d’une plage d’événements donnée doivent être complètes, ce qui signifie qu’Adobe ne reçoit plus de données d’événement pour la plage d’événements spécifiée.<p>Pour tenir compte de ce délai d’ingestion, les alertes sont envoyées avec un délai par défaut de 9 heures.</p><p>Vous pouvez régler le délai par défaut de 9 heures sur une valeur comprise entre 0 et 24 heures. Toutefois, si vous réduisez le délai en dessous de 9 heures, cela peut signifier que vous signalez des données incomplètes, ce qui entraîne des informations d’alerte inexactes.</p><p>Tenez compte de ce qui suit lors de la configuration du paramètre de délai :</p><ul><li>**Comprendre la disponibilité des données par rapport à l’exhaustivité des données** : bien que certaines données puissent être disponibles pour la création de rapports plus tôt, toutes les données par lot ne sont ingérées dans un jeu de données Platform qu’après une période de 3 à 9 heures. Pour que les alertes soient exactes, l’ingestion des données doit être terminée et toutes les données par lot disponibles dans le jeu de données.</li><li>**Déterminer le temps nécessaire pour que vos données soient complètes et disponibles dans le jeu de données** : les délais d’ingestion des données varient selon l’organisation. Assurez-vous que le délai que vous choisissez pour la diffusion des alertes est identique ou inférieur au temps nécessaire pour que les données par lot soient disponibles dans le jeu de données Platform<!--add link? -->.</li><p>**Conseil :** le moyen le plus précis de connaître le temps nécessaire pour que toutes les données par lot soient terminées et ingérées dans le jeu de données Platform est de consulter l’équipe d’ingénierie des données de votre organisation.</p><p>Vous pouvez également obtenir une idée générale du temps nécessaire à la diffusion par lots dans votre organisation pour être disponible dans le jeu de données Platform en créant le tableau à structure libre suivant dans Analysis Workspace :</p><ol><li>Dans un tableau à structure libre d’Analysis Workspace, ajoutez une mesure [!UICONTROL **Événements**] et une dimension [!UICONTROL **Jour**].</li><li>Répartissez la dimension [!UICONTROL **Jour**] à l’aide d’une dimension [!UICONTROL **Heures**].<p>Les heures qui ne contiennent aucune donnée affichent 0.</p></li></ol><li>**Tenir compte des erreurs dans vos calculs** : si vous réduisez le délai par défaut, nous vous recommandons de le configurer au moins sur une heure de plus que le temps nécessaire à votre organisation pour que l’ingestion des données soit complète. Par exemple, s’il y a un délai de 3 heures avant la fin de l’ingestion des données, vous devez définir le délai sur 4 heures.</li></ul><p>Pour plus d’informations, consultez [Les délais d’ingestion des données varient dans Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) dans l’article [Comparaison des fonctionnalités d’alertes : Customer Journey Analytics et Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Envoyer une alerte lorsque]** | [!UICONTROL **L’une de ces mesures déclenche**] : faites glisser et déposez les mesures (y compris les mesures calculées) ici pour créer des déclencheurs pour l’alerte.<p>Un message **« composants incompatibles »** s’affiche si certains composants (mesures/dimensions/segments) de l’alerte ne sont pas compatibles avec la vue de données actuellement sélectionnée.</p><p>Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :</p><ul><li>il existe une anomalie</li><li>l’anomalie est supérieure à celle prévue</li><li>l’anomalie est inférieure à celle prévue</li><li>est supérieur ou égal</li><li>est inférieur ou égal</li><li>change de</li><li>Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.</li></ul><p>[!UICONTROL **Avec tous ces filtres**] : faites glisser et déposez des segments ou des dimensions pour ajouter des filtres à l’alerte. Par exemple, l’ajout d’un segment *Appareils mobiles uniquement* signifie que la règle se déclenche uniquement pour les appareils mobiles. Vous pouvez ajouter des filtres supplémentaires à l’aide d’une instruction ET. Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.</p><p>Consultez [Alertes - cas d’utilisation](/help/components/c-intelligent-alerts/alerts-use-cases.md) pour des exemples de cas d’utilisation.</p> |
| **[!UICONTROL Aperçu]** | Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte sera déclenchée en fonction d’une expérience antérieure.<p>Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours.</p><p>Si vous trouvez que trop d’alertes sont déclenchées, réglez le seuil dans [Gérer les alertes](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
