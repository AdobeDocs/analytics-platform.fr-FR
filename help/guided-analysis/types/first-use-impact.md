---
title: Analyse d’impact de la première utilisation
description: Mesurez l’impact de la première utilisation des fonctionnalités sur les indicateurs clés.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 6%

---

# [!UICONTROL Première utilisation de l’analyse] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_firstuseimpact_button"
>title="Impact de la première utilisation"
>abstract="Mesurez l’impact de la première utilisation des fonctionnalités sur les indicateurs clés."

<!-- markdownlint-enable MD034 -->

L&#39;analyse ![Première utilisation](/help/assets/icons/FirstUse.svg) **** montre la comparaison des indicateurs clés effectués avant et après qu&#39;un utilisateur utilise une fonctionnalité de produit pour la première fois. L’axe horizontal de ce rapport est un intervalle de temps relatif avant et après l’événement, tandis que l’axe vertical mesure les indicateurs clés souhaités. Une barre verticale située au milieu du graphique représente le jour 0 lorsqu’une fonction est utilisée pour la première fois par un utilisateur donné. Comme les utilisateurs n’adoptent pas toujours les fonctionnalités le même jour et que vos déploiements peuvent éventuellement se produire sur plusieurs jours, le jour 0 peut signifier quelque chose de différent pour chaque utilisateur.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)


## Cas d’utilisation

Voici quelques cas pratiques de cette analyse :

* **Nouvelle analyse des fonctionnalités** : si vous lancez une nouvelle fonctionnalité dans votre produit, vous pouvez comparer les performances des indicateurs clés avant et après l’exposition initiale de ces utilisateurs à cette nouvelle fonctionnalité.
* **Déploiements par phases** : dans la mesure où l’analyse recherche la première utilisation de la fonctionnalité plutôt qu’une date fixe, cette analyse s’avère utile si vous mettez en phase le déploiement de vos fonctionnalités au fil du temps.
* **Nouvelle analyse de version de produit** : si vous lancez une nouvelle version de votre produit, vous pouvez comparer les indicateurs clés effectués avant et après l’exposition initiale des utilisateurs à cette nouvelle version. Sélectionnez &quot;any event&quot; comme événement de première utilisation et filtrez-le sur votre propriété Version Number.
* **Améliorations des fonctionnalités existantes** : si vous apportez des améliorations à une fonctionnalité existante de votre produit, vous pouvez comparer les performances des indicateurs clés avant et après l’exposition initiale de ces utilisateurs à ces nouvelles améliorations. Vous pouvez effectuer cette analyse d’une ou de plusieurs façons en fonction de l’instrumentation de votre fonction.
   * Sélectionnez un événement représentant l’amélioration comme événement de première utilisation.
   * Sélectionnez la date à laquelle les modifications ont commencé à se déployer.
   * Segmenter l’analyse avec le groupe de personnes exposées aux améliorations
* **Efficacité de la campagne** : lorsqu’un utilisateur clique à travers une campagne donnée, vous pouvez comparer les indicateurs clés effectués avant et après l’interaction de l’utilisateur avec cette campagne.

## Interface

Voir [Interface](../overview.md#interface) pour un aperçu de l’interface d’analyse guidée. Les paramètres suivants sont spécifiques à cette analyse :

### Rail de requête

Le rail de requête vous permet de configurer les composants suivants :

* **[!UICONTROL Vue]** : basculez entre cette analyse et la [version](release-impact.md).
* **[!UICONTROL Indicateurs clés]** : événements que vous souhaitez mesurer par utilisateur. Chaque indicateur de clé sélectionné est représenté sous la forme d’une ligne colorée. Une ligne représentant l’événement est ajoutée au tableau. Vous pouvez inclure jusqu’à trois événements.
* **[!UICONTROL Compté comme]** : méthode de comptage que vous souhaitez appliquer aux événements sélectionnés. Les options incluent [!UICONTROL Événements par utilisateur], [!UICONTROL Événements], [!UICONTROL Sessions] et [!UICONTROL Utilisateurs].
* **[!UICONTROL Facteurs]** : cette analyse comporte deux facteurs :
   * **[!UICONTROL Date]** : date à laquelle vous souhaitez commencer à rechercher le premier événement d’utilisation qui s’est produit.
   * **[!UICONTROL Événement]** : événement dont vous souhaitez rechercher la première utilisation, pour centrer l’analyse.
* **[!UICONTROL Segments]** : segment que vous souhaitez mesurer. Le segment sélectionné filtre vos données afin de se concentrer uniquement sur les individus qui correspondent à vos critères de segment. Un seul segment est pris en charge pour cette analyse.

### Paramètres du graphique

L’analyse [!UICONTROL Première utilisation de l’impact] offre les paramètres de graphique suivants, qui peuvent être ajustés dans le menu au-dessus du graphique :

* **[!UICONTROL Type de graphique]** : type de visualisation que vous souhaitez utiliser. Les options comprennent Ligne.

### Période

Les sélections de dates dans l’analyse [!UICONTROL Première utilisation] fonctionnent différemment des autres analyses, car l’analyse se base sur la date spécifiée dans le rail de requête. Les options disponibles sont les suivantes :

* **[!UICONTROL Intervalle]** : granularité de date selon laquelle vous souhaitez afficher les données de tendance. Les options valides sont les suivantes : [!UICONTROL Quotidien], [!UICONTROL Hebdomadaire], [!UICONTROL Mensuel] et [!UICONTROL Trimestriel]. La modification de l’intervalle affecte les options disponibles pour les périodes Avant et Après.
* **[!UICONTROL Avant et après la période]** : durée d’analyse avant et après le premier événement d’utilisation spécifié dans le rail de requête. Les options disponibles dépendent de la sélection [!UICONTROL Intervalle] .

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
