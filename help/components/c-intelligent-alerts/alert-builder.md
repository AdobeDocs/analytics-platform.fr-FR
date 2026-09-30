---
description: Découvrez comment créer des alertes dans Analysis Workspace.
title: Créer des alertes
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
TQID: https://experienceleague.adobe.com/DALPpXgGDOoMJT8kv5xsDmZWapk4rDXhQmtTTvV0-TA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
    internal-label: Calendar
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
    internal-label: Alerts
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 4f3c4a214bb9676ced6fe3c9627c969413013790
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 62%
---
# Créer des alertes {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularité temporelle"
>abstract="La granularité temporelle indique la fréquence de vérification de l’alerte."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_delay"
>title="Délai"
>abstract="Les alertes se déclenchent au moment de la granularité que vous sélectionnez après ce délai. Les données provenant de vos connexions peuvent arriver avec différentes latences, entre 1 et 24 heures. Le délai par défaut se déclenche 9 heures après chaque fenêtre d’alerte."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>L’utilisation d’alertes avec détection des anomalies (également appelées _Alertes intelligentes_) n’est disponible que pour les organisations qui disposent d’un package Customer Journey Analytics Prime ou Ultimate.

Les alertes dans Customer Journey Analytics envoient un avertissement en fonction de pourcentages ou de points de données spécifiques modifiés. Selon votre package Customer Journey Analytics, vous pouvez également déclencher les alertes en fonction des seuils d’anomalie.

Pour des informations plus détaillées sur les alertes, consultez [Vue d’ensemble des alertes](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Pour créer une alerte, procédez comme suit :

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. Dans Customer Journey Analytics, sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Alertes]**. Dans le [Gestionnaire d’alertes](alert-manager.md), sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** pour créer une alerte ou sélectionnez l’une des alertes répertoriées pour modifier une alerte existante.

1. Dans Analysis Workspace, sélectionnez un ou plusieurs éléments de ligne dans un tableau à structure libre, puis sélectionnez **[!UICONTROL Créer une alerte à partir de la sélection]** dans le menu contextuel. Cette action préremplit instantanément le créateur d’alertes pour créer une alerte avec les mesures et segments corrects.

L’interface [Créateur d’alertes](#alert-builder) s’affiche.


## Créateur d’alertes

L’interface du créateur d’alertes est familière avec celle que vous utilisez lorsque vous créez des segments ou des mesures calculées dans Customer Journey Analytics :

![Interface du créateur d’alertes](assets/alert-builder.png)

Spécifiez les informations suivantes dans le créateur d’alertes pour une alerte :

| Élément | Description |
|---------|----------|
| **[!UICONTROL Titre]** | Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures. |
| **[!UICONTROL Description (facultatif)]** | Spécifiez une description de l’alerte. |
| **[!UICONTROL Granularité temporelle]** | Sélectionnez la fréquence à laquelle vous souhaitez que la mesure soit vérifiée :<ul><li>**[!UICONTROL Par heure]**<p>Customer Journey Analytics prend en charge différents types de données. Toutefois, toutes les données pouvant être incluses dans une alerte ne sont pas adaptées à une alerte horaire. Pour plus d’informations, voir [Les alertes horaires peuvent s’avérer impossibles pour certains types de données](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#hourly-alerts-can-be-impractical-for-certain-types-of-data).</p></li><li>**[!UICONTROL Quotidien]**</li><li>**[!UICONTROL Hebdomadaire]**</li><li>**[!UICONTROL Mensuel]**<p>La granularité mensuelle n’est pas prise en charge pour les vues de données avec un [calendrier personnalisé](/help/data-views/create-dataview.md#calendar).<!--true?--></p></li></ul> |
| **[!UICONTROL Destinataires]** | Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse e-mail brute ou à un numéro de téléphone.<p><b>Important</b> : le numéro de téléphone doit être précédé d’un `+` et d’un [indicatif de pays](https://countrycode.org/).</p><p>L’e-mail qu’un utilisateur ou une utilisatrice reçoit après une alerte :</p><p>![E-mail d’alerte](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Date d’expiration]** | Définissez la date et l’heure d’expiration de l’alerte. |
| **[!UICONTROL Délai]** | Le temps nécessaire pour que les données soient complètes et disponibles pour faire l’objet de rapports dans Customer Journey Analytics varie selon l’entreprise, allant généralement de 3 à 9 heures après l’heure de l’événement de données. Pour que les alertes soient précises, les données d’événement d’une plage d’événements donnée doivent être complètes, ce qui signifie qu’Adobe ne reçoit plus de données d’événement pour la plage d’événements spécifiée.<p>Pour tenir compte de ce délai d’ingestion, les alertes sont envoyées avec un délai par défaut de 9 heures.</p><p>Les alertes sont diffusées à la fin du délai, que toutes les données de la plage d’événements soient arrivées ou non. Les données qui arrivent après le délai ne sont pas incluses dans l’alerte.</p><p>Vous pouvez régler le délai par défaut de 9 heures sur une valeur comprise entre 0 et 24 heures. Toutefois, si vous réduisez le délai en dessous de 9 heures, cela peut signifier que vous signalez des données incomplètes, ce qui entraîne des informations d’alerte inexactes.</p><p>Tenez compte de ce qui suit lors de la configuration du paramètre de délai :</p><ul><li>**Comprendre la disponibilité et l’exhaustivité des données** : les données par lots ne sont ingérées dans un jeu de données Experience Platform qu’après une période de 3 à 9 heures. Pour que les alertes soient exactes, l’ingestion des données doit être terminée et toutes les données par lot disponibles dans le jeu de données.</li><li>**Déterminer le temps nécessaire pour que vos données soient complètes et disponibles dans le jeu de données** : les délais d’ingestion des données varient selon l’organisation. Assurez-vous que le délai que vous choisissez pour la diffusion des alertes est identique ou inférieur au temps nécessaire pour que les données par lot soient disponibles dans le jeu de données Platform<!--add link? -->.</li><p>**Conseil :** le moyen le plus précis de connaître le temps nécessaire pour que toutes les données par lot soient terminées et ingérées dans le jeu de données Experience Platform est de consulter les ingénieurs de données de votre organisation.</p><p>Vous pouvez également obtenir une idée générale du temps nécessaire à la diffusion par lots dans votre organisation pour être disponible dans le jeu de données Platform. Créez le tableau à structure libre suivant dans Analysis Workspace :</p><ol><li>Dans un tableau à structure libre d’Analysis Workspace, ajoutez une mesure [!UICONTROL **Événements**] et une dimension [!UICONTROL **Jour**].</li><li>Répartissez la dimension [!UICONTROL **Jour**] à l’aide d’une dimension [!UICONTROL **Heures**].<p>Les heures qui ne contiennent aucune donnée affichent 0.</p></li></ol><li>**Tenir compte des erreurs dans vos calculs** : si vous réduisez le délai par défaut, configurez le délai au moins sur une heure de plus que le temps nécessaire à votre organisation pour que l’ingestion des données soit complète. Par exemple, si l’ingestion de vos données prend 3 heures avant d’être terminée, vous devez définir le délai sur 4 heures.</li></ul><p>Pour plus d’informations, consultez la section [Les délais d’ingestion des données varient](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary) dans l’article [Comparaison des fonctionnalités d’alertes : Customer Journey Analytics et Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Envoyer une alerte lorsque]** | [!UICONTROL **L’une de ces mesures déclenche**] : <ol><li>Effectuez un glisser-déposer des mesures (y compris des mesures calculées) afin de créer des déclencheurs pour l’alerte.<p>Un message *composants incompatibles* s’affiche si toutes les mesures, dimensions ou segments de l’alerte ne sont pas compatibles avec la suite de rapports actuellement sélectionnée.</p><p>Déterminez le seuil (en cas d’anomalie) que la mesure doit dépasser ou la valeur (en cas de modification ci-dessus, ci-dessous, égale ou en pourcentage) à utiliser avant de définir une alerte.</li><li>Sélectionnez l’une des conditions suivantes :<ul><li>il existe une anomalie</li><li>l’anomalie est supérieure à celle prévue</li><li>l’anomalie est inférieure à celle prévue</li><li>est supérieur ou égal</li><li>est inférieur ou égal</li><li>change de</li></ul></li><li>Sélectionnez une valeur de seuil ou saisissez-en une.</li></ol>[!UICONTROL **Avec tous ces filtres**] : faites glisser et déposez des segments ou des dimensions pour ajouter des filtres sur l’alerte. Par exemple, ajoutez un segment *Appareils mobiles uniquement* afin de signifier que la règle se déclenche uniquement pour les appareils mobiles. Vous pouvez ajouter des filtres supplémentaires à l’aide d’une instruction ET. Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.</p><p>Consultez [Alertes - cas d’utilisation](alerts-use-cases.md) pour des exemples de cas d’utilisation.</p> |
| **[!UICONTROL Aperçu]** | Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte est déclenchée en fonction d’une expérience antérieure.<p>Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours.</p><p>Si vous trouvez que trop d’alertes sont déclenchées, réglez le seuil dans [Gérer les alertes](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
