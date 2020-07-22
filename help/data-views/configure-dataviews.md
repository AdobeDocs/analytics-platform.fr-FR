---
title: Configuration d’attribution et de vues de données
description: Décrit comment créer une vue de données à un jeu de données de plateforme dans Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 96%

---


# Paramètres de composant et d’attribution

Les eVars, les props et les événements comme l’entend habituellement Adobe Analytics n’existent plus dans Customer Journey Analytics. Vous disposez à la place d’un nombre illimité d’éléments de schéma (dimensions, mesures, champs de liste). Tous les paramètres d’attribution que vous appliquiez aux eVars et aux props pendant le processus de collecte de données sont maintenant appliqués au moment de la requête, également appelé traitement de la période de rapport.

Cliquez [ici](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html) pour une présentation vidéo.

Gardez cela à l’esprit avant d’appliquer les paramètres d’attribution :

* Dans l’interface utilisateur des vues de données, vous spécifiez l’attribution par défaut. **Remarque** : À une date ultérieure, vous pourrez remplacer ces paramètres dans les projets Workspace. Toutefois, cette fonctionnalité n’est pas disponible actuellement.

* Les paramètres d’attribution dans Customer Journey Analytics sont non destructifs et rétroactifs. En d’autres termes, vous ne pouvez pas endommager irrémédiablement vos jeux de données dans Customer Journey Analytics. Even if you accidentally delete something, you can always go back to [!UICONTROL Experience Platform] and bring the dataset back in. (Gardez à l’esprit, cependant, que la réintroduction du jeu de données entraînera des coûts supplémentaires.)

* Si vous souhaitez qu’une dimension ait le même « comportement » qu’une eVar (variable de conversion) traditionnelle, vous devez la configurer avec l’attribution « Visite Dernière touche » par défaut.

* Si vous souhaitez qu’une dimension ait le même « comportement » qu’une prop (variable de trafic) traditionnelle, vous devez la configurer avec l’attribution « Même touche » par défaut.

* Si vous souhaitez qu’une mesure ait le même « comportement » qu’une mesure par défaut, vous ne devez rien modifier.

* Les paramètres d’attribution des mesures remplacent les paramètres d’attribution des dimensions.

## Définition des paramètres de composant et d’attribution

Après avoir [défini et enregistré les paramètres de vue de données](/help/data-views/create-dataview.md) et ajouté des composants, vous pouvez spécifier les paramètres d’attribution si vous le souhaitez. Vous pouvez spécifier des paramètres d’attribution/d’expiration/de recherche pour les dimensions et les mesures. Si, par exemple, vous souhaitez que l’attribution d’une dimension soit conservée, il est probable que vous souhaitiez définir un délai d’expiration personnalisé. Par exemple, si vous souhaitez qu’une dimension « Code de suivi » (une variable de campagne) soit définie sur l’attribution « Dernière touche » pour qu’elle persiste pendant une semaine, ajoutez une expiration personnalisée d’une semaine.

>[!IMPORTANT]
>Vous pouvez choisir de ne pas définir d’attribution/d’expiration. Dans ce cas, les dimensions se comportent comme des props (modèle d’attribution « Même touche »). Les mesures sans paramètre d’attribution héritent des paramètres de la dimension à laquelle cette mesure est appliquée.

![](assets/edit-component.png)

1. Spécifiez les paramètres de composant et d’attribution pour les dimensions et les mesures. Pour plus d’informations sur les paramètres individuels, voir ci-dessous.

1. Click **[!UICONTROL Save]** to save your data view.


### Paramètre du composant

Vous pouvez modifier le nom de la mesure ou de la dimension pour qu’il soit plus convivial. Notez que le nom sous-jacent ne change pas, uniquement le nom d’affichage.

### Modèle d’attribution

Le modèle décrit la distribution des conversions pour les événements dans un groupe. Par exemple, Première touche ou Dernière touche. Détermine la manière dont parcours Customer Journey Analytics attribue le crédit d’un événement de succès si une variable reçoit plusieurs valeurs avant l’événement.

| Icône de l’interface utilisateur | Modèle d’attribution | Définition | Conditions d’utilisation |
| --- | --- | --- | --- |
| ![Dernière touche](assets/last_touch1.png) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. | Le modèle d’attribution le plus élémentaire et le plus courant. Il est fréquemment utilisé pour les conversions avec un cycle de traitement court. Le modèle Dernière touche est couramment utilisé par les équipes qui gèrent le marketing de moteur de recherche ou qui analysent les mots-clés de recherche interne. |
| ![Première touche](assets/first_touch.png) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont d’attribution. | Un autre modèle d’attribution commun utile pour l’analyse des canaux marketing destinés à accroître la notoriété de la marque ou à favoriser l’acquisition client. Il est fréquemment utilisé par les équipes Display ou Marketing social, mais est également utile pour évaluer l’efficacité des recommandations de produits sur site. |
| ![Même touche](assets/same_touch.png) | Même touche | Attribue un crédit de 100 % à l’accès même où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même accès qu’une conversion, il est placé sous « Aucun ». | Un modèle utile pour évaluer le contenu ou l’expérience client qui a été présenté immédiatement au moment de la conversion. Les équipes produit ou de conception utilisent souvent ce modèle pour évaluer l’efficacité d’une page où a lieu une conversion. |
| ![Linéaire](assets/linear.png) | Linéaire | Attribue le même crédit à chaque point de contact visible menant à une conversion. | Utile pour les conversions avec des cycles de traitement plus longs ou des expériences client qui nécessitent un engagement plus fréquent et plus constant de la part des clients. Il est souvent utilisé par des équipes qui mesurent l’efficacité des notifications d’applications mobiles ou avec des produits sur abonnement. |
| ![En forme de U](assets/u_shaped.png) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est attribué aux deux. | Un modèle conseillé à ceux qui valorisent les interactions qui ont introduit ou fermé une conversion, mais qui veulent tout de même reconnaître les interactions d’assistance. L’attribution En forme de U est souvent utilisée par des équipes qui adoptent une approche plus équilibrée, mais qui veulent accorder plus de crédit aux canaux ayant trouvé ou mis fin à une conversion. |
| ![En forme de J](assets/j_shaped.png) | En forme de J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la dernière interaction et 25 % à la première. | Ce modèle est conseillé à ceux qui donnent la priorité aux outils de recherche et de fermeture, mais qui souhaitent se concentrer sur les interactions de fermeture. L’attribution En forme de J est souvent utilisée par des équipes qui adoptent une approche plus équilibrée et qui veulent accorder plus de crédit aux canaux ayant mis fin à une conversion. |
| ![En forme de J inversé](assets/inverse_j.png) | En forme de J inversé | Attribue un crédit de 60 % au premier point de contact, de 20 % au dernier point de contact et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la première interaction et 25 % à la première. | Ce modèle est idéal pour ceux qui donnent la priorité aux outils de recherche et de fermeture, mais qui souhaitent se concentrer sur les interactions de recherche. L’attribution En forme de J inversé est utilisée par des équipes qui adoptent une approche plus équilibrée et qui veulent accorder plus de crédit aux canaux ayant déclenché une conversion. |
| ![Personnalisé](assets/custom.png) | Personnalisé | Permet de spécifier les pondérations à attribuer aux premiers points de contact, aux derniers points de contact et à tous les points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne totalisent pas 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les premiers et derniers points de contact sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. | Ce modèle est parfait pour ceux qui souhaitent un contrôle total sur leur modèle d’attribution et qui ont des besoins spécifiques que d’autres modèles d’attribution ne remplissent pas. |
| ![Décroissance temporelle](assets/time_decay.png) | Décroissance temporelle | Suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de sept jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2`<sup>`(-t/halflife)`</sup>, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont alors normalisés à 100 %. | L’idéal pour les équipes qui exécutent régulièrement de la publicité vidéo ou qui font du marketing pour des événements avec une date prédéterminée. Plus une conversion se produit après un événement marketing, plus faible sera le crédit attribué. |
| ![Participation](assets/participation.png) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Le nombre total de conversions est gonflé par rapport aux autres modèles d’attribution. La participation déduplique les canaux qui sont vus à plusieurs reprises. | Excellent pour comprendre la fréquence à laquelle les clients sont exposés à une interaction donnée. Les sociétés de médias utilisent fréquemment ce modèle pour calculer la vitesse du contenu. Les sociétés de vente au détail utilisent souvent ce modèle pour comprendre les parties de leur site qui sont essentielles à la conversion. |

### Expiration

Indique une période, ou un événement, après laquelle l’élément de dimension expire (ne reçoit plus de crédit pour les événements de réussite). Vous pouvez définir l’expiration de l’attribution au niveau de la session, de la personne ou de la personnalisation.

| Paramètre | Définition |
|---|---|
| Session | Anciennement connu sous le nom de niveau « Visite ». Les événements de conversion situés au-delà de la page vue ou de la session ne sont pas associés à la dimension ou la mesure. |
| Personne (Intervalle de rapport) | Anciennement connu sous le nom de niveau « Visiteur ». Les événements de conversion non liés à cette personne ne sont pas associés à la dimension ou à la mesure. |
| Temps personnalisé | Spécifie les minutes, heures, jours, mois ou trimestres personnalisés. Les événements de conversion situés au-delà de la période spécifiée ne sont pas associés à la dimension ou la mesure. |

Pour plus d’informations, voir le [document Attribution IQ](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/panels/attribution/attribution.translate.html).

### Intervalle de recherche en amont

Un intervalle de recherche en amont est la durée pendant laquelle une conversion doit faire une recherche en amont pour inclure des points de contact. Les modèles d’attribution qui accordent plus de crédit aux premières interactions voient des différences plus importantes lors de l’affichage de différents intervalles de recherche en amont.

* **Session :** recherche en amont jusqu’au début d’une session au cours de laquelle une conversion s’est produite. Les intervalles de recherche en amont des sessions sont étroits, car ils ne recherchent pas au-delà de la session. Les intervalles de recherche en amont des sessions respectent la définition de session modifiée dans les vues de données.
* **Personne (Intervalle de rapport) :** recherche toutes les sessions en amont jusqu’au 1er du mois de la période en cours. Les intervalles de recherche en amont des personnes sont larges, car ils peuvent porter sur plusieurs sessions. Par exemple, si la période du rapport s’étend du 15 au 30 septembre, la période de recherche en amont des personnes est du 1er au 30 septembre.
