---
title: 'Paramètres des composants : attribution'
description: Permet de définir lʼattribution par défaut dʼune mesure.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: ht
source-wordcount: '847'
ht-degree: 100%

---

# Paramètres des composants : attribution {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Attribution"
>abstract="Configurez le modèle d’attribution par défaut appliqué à une mesure dans les rapports."

<!-- markdownlint-enable MD034 -->


L’attribution vous donne la possibilité de personnaliser la façon dont les éléments de dimension reçoivent du crédit pour les événements de succès.

![Fenêtre Vues de données mettant en surbrillance l’option Définir l’attribution](../assets/attribution-settings.png)

Par exemple :

1. Une personne sur votre site clique sur un lien de référencement payant vers l’une de vos pages de produits. La personne ajoute le produit au panier, mais ne l’achète pas.
2. Le lendemain, elle voit un message d’une personne de son entourage sur les médias sociaux. Elle clique sur le lien, puis effectue l’achat.

Dans certains rapports, vous voudrez peut-être attribuer la commande au référencement payant. Dans d’autres rapports, vous voudrez peut-être attribuer la commande à Social. Attribution vous permet de contrôler cet aspect des rapports.

## Définir le modèle d’attribution par défaut d’un composant

Vous pouvez définir un modèle d’attribution par défaut pour une mesure donnée en mettant à jour le paramètre de la mesure dans la vue de données. Cela remplace le modèle d’attribution de la mesure chaque fois qu’il est utilisé dans Analysis Workspace.

>[!NOTE]
>
>Tenez compte des points suivants lors de l’activation de l’attribution sur une mesure :
>
>* **Lors de l’utilisation du composant dans un rapport avec *une seule dimension* :** l’attribution du composant ignore le modèle d’attribution lorsqu’un modèle d’attribution différent du modèle par défaut est utilisé.
>
>* **Lors de l’utilisation du composant dans un rapport avec *plusieurs dimensions* :** l’attribution du composant conserve le modèle d’attribution lorsqu’un modèle d’attribution différent du modèle par défaut est utilisé.
>
>   Plusieurs dimensions sont disponibles uniquement lors de l’[export de données vers le cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Pour plus d’informations sur l’attribution, consultez [Paramètres des composants de persistance](/help/data-views/component-settings/persistence.md).

Pour mettre à jour le modèle d’attribution par défaut d’un composant, procédez comme suit :

1. Accédez à la vue de données contenant le composant dont vous souhaitez mettre à jour le modèle d’attribution par défaut.

1. Sélectionnez le composant, puis développez la section Attribution sur le côté droit de l’écran.

   ![Fenêtre Vues de données mettant en surbrillance l’option Définir l’attribution](../assets/attribution-settings.png)

1. Sélectionnez [!UICONTROL **Définir l’attribution**], puis sélectionnez le modèle d’attribution dans le menu déroulant [!UICONTROL **Modèle d’attribution**].

   Consultez [Modèles d’attribution](#attribution-models) pour en savoir plus sur chaque modèle d’attribution.

1. Sélectionnez [!UICONTROL **Enregistrer et continuer**].

>[!TIP]
>
>Si votre entreprise exige qu’une mesure comporte plusieurs paramètres d’attribution, vous pouvez effectuer l’une des opérations suivantes :
>
> * Copiez la mesure dans la vue de données avec chaque paramètre d’attribution souhaité. Vous pouvez inclure la même mesure plusieurs fois dans une vue de données, ce qui donne à chaque mesure un paramètre différent. Assurez-vous d’étiqueter correctement chaque mesure afin que les analystes comprennent la différence entre ces mesures lors de la génération des rapports.
>
> * Remplacez la mesure dans Analysis Workspace. Dans les [Paramètres de colonne](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) d’une mesure, sélectionnez **[!UICONTROL Utiliser un modèle d’attribution différent du modèle par défaut]** pour modifier le modèle d’attribution et l’intervalle de recherche en amont de la mesure pour ce rapport spécifique.

## Modèles d’attribution {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modèle"
>abstract="Sélectionnez un modèle d’attribution pour la mesure."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Intervalle de recherche en amont

{{attribution-lookback-window}}



## Exemple d’attribution {#attribution-example}

Examinez l’exemple suivant :

1. Le 15 septembre, une personne arrive sur votre site par le biais d’une annonce de référencement payant, puis le quitte.
1. Le 18 septembre, la personne arrive de nouveau sur votre site par le biais d’un lien sur les médias sociaux qu’une personne de son entourage lui a envoyé. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
1. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre intervalle de recherche en amont et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples :

* À l’aide de **Première touche** et d’un **intervalle de recherche en amont des sessions**, l’attribution ne s’intéresse qu’à la troisième visite. Entre l’e-mail et l’affichage, l’e-mail était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $.

* À l’aide de **Première touche** et d’un **intervalle de recherche en amont des personnes**, l’attribution s’intéresse aux trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $.

* À l’aide de **linéaire** et d’un **intervalle de recherche en amont des sessions**, le crédit est divisé entre l’e-mail et l’affichage. Ces deux canaux reçoivent chacun un crédit pour 25 $.
À l’aide de **linéaire** et d’un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, l’e-mail et l’affichage. Chaque canal reçoit un crédit pour 12,50 $ pour cet achat.

* À l’aide du modèle **En forme de J** et d’un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, l’e-mail et l’affichage.

   * Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.
   * Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.

* À l’aide de **Atténuation temporelle** et d’un **intervalle de recherche en amont des personnes**, le crédit est divisé entre le référencement payant, les réseaux sociaux, l’e-mail et l’affichage. Utilisation de la demi-vie de sept jours par défaut :

   * Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`
   * Intervalle de zéro jour entre le point de contact de l’e-mail et la conversion. `2^(-0/7) = 1`
   * Intervalle de six jours entre le point de contact de réseaux sociaux et la conversion. `2^(-6/7) = 0.552`
   * Intervalle de neuf jours entre le point de contact du référencement payant et la conversion. `2^(-9/7) = 0.41`
   * La normalisation de ces valeurs entraîne les résultats suivants :

      * Affichage : 33,8 %, gain de 16,88 $
      * Courrier électronique : 33,8 %, gain de 16,88 $
      * Réseaux sociaux : 18,6 %, gain de 9,32 $
      * Référencement payant : 13,8 %, gain de 6,92 $

Les événements de conversion qui comportent généralement des nombres entiers sont divisés si le crédit revient à plusieurs canaux. Par exemple, si deux canaux contribuent à un événement personnalisé à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de cette commande. Ces mesures partielles sont additionnées pour toutes les personnes, puis arrondies à l’entier le plus proche à des fins de création de rapports.


