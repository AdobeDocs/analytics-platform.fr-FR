---
description: En savoir plus sur le type de mesure et l’attribution
title: Type de mesure et attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 40%

---

# Type de mesure et attribution

Vous pouvez configurer le type de mesure et le [modèle d’attribution](#attribution-models) pour une mesure dans une définition de mesure calculée.

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans le composant de mesure.
1. Dans la boîte de dialogue contextuelle :

   ![ Type de mesure et attribution ](assets/cm-type-alloc.png)

   * Spécifiez le **[!UICONTROL Type de mesure]** :

     | Type de mesure | Définition |
     |---|---|
     | **[!UICONTROL Standard]** | Si une formule se compose d’une seule mesure standard, elle affiche des données identiques à son équivalent de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque élément de ligne. <p>Par exemple, la mention ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Commandes]** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** divise les commandes de cet élément de ligne spécifique par le nombre de sessions correspondantes. |
     | **[!UICONTROL Total général]** | Utilisez **[!UICONTROL Total général]** pour la période de création des rapports dans chaque élément de ligne. Si une formule se compose d’une seule mesure Total général , la mesure calculée affiche le même nombre Total général sur chaque élément de ligne. Les mesures de total général sont utiles lorsque vous souhaitez créer des mesures calculées qui se comparent aux données totales. <p>Par exemple, la mention ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Commandes]** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Nombre total de sessions]** indique la proportion de commandes par rapport à toutes les sessions, et pas seulement par rapport à l’élément de ligne spécifique. Dans cet exemple, vous spécifiez **[!UICONTROL Total général]** pour la mesure ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** dans votre mesure calculée, qui la transformera automatiquement en ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Nombre total de sessions]**. |

   * Spécifiez **[!UICONTROL Attribution]**.

      1. Vous pouvez effectuer l’une des actions suivantes :

         * Désactivez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]** pour utiliser le modèle d’attribution de colonne par défaut, à savoir Dernière touche, avec un intervalle de recherche en amont de 30 jours.
         * Activez **[!UICONTROL Utiliser un modèle d’attribution autre que celui par défaut]**. Dans la boîte de dialogue **[!UICONTROL Modèle d’attribution de colonne]** :

            * Sélectionnez un **[!UICONTROL Modèle]** parmi les modèles d’attribution.
            * Sélectionnez un **[!UICONTROL Intervalle de recherche en amont]**. Si vous sélectionnez **[!UICONTROL Heure personnalisée]**, vous pouvez définir la période en **[!UICONTROL minute(s)]** jusqu’à **[!UICONTROL trimestre(s)]**. Voir [ Intervalle de recherche en amont ](#lookback-window) pour plus d’informations

      1. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer le modèle d’attribution autre que celui par défaut. Sélectionnez Annuler pour annuler.

     Si vous avez déjà défini un modèle d’attribution autre que celui par défaut, sélectionnez **[!UICONTROL Modifier]** pour modifier la sélection.

Voir [Exemple](#example) pour un exemple d’utilisation d’un modèle d’attribution et d’un intervalle de recherche en amont.


## Attribution {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Activez un modèle d’attribution autre que celui par défaut pour la mesure sélectionnée."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modèle"
>abstract="Sélectionnez un modèle d’attribution pour la mesure."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Dernière touche"
>abstract="100 % du crédit est attribué à la dernière valeur de dimension vue par un visiteur ou une visiteuse."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Première touche"
>abstract="100 % du crédit est attribué à la première valeur de dimension vue par un visiteur ou une visiteuse."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linéaire"
>abstract="Le crédit est réparti uniformément sur toutes les valeurs de dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participation"
>abstract="Crédit 100 % à chaque valeur de dimension vue par un visiteur ou une visiteuse.<br/>Les totaux des colonnes sont surestimés."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Même touche"
>abstract="Le crédit est attribué uniquement aux valeurs de dimension survenant sur le même événement que la conversion."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="En forme de U"
>abstract="40 % du crédit à la première valeur de dimension, 40 % à la dernière, 20 % partagés par le milieu."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="En forme de J"
>abstract="60 % du crédit à la dernière valeur de dimension, 20 % à la première, 20 % partagés par le milieu."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="En forme de J inversé"
>abstract="60 % du crédit à la première valeur de dimension, 20 % à la dernière, 20 % partagés par le milieu."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Décroissance temporelle"
>abstract="Les valeurs de dimension les plus proches dans le temps d’une conversion obtiennent le plus de crédit."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personnalisé"
>abstract="Définissez votre propre pondération d’attribution basée sur la position."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmique"
>abstract="Le crédit est déterminé dynamiquement à l’aide d’un algorithme statistique."

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### Intervalle de recherche en amont {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervalle de recherche en amont"
>abstract="Ce paramètre détermine la fenêtre d’attribution des données qui sera appliquée à chaque conversion."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### Exemple d’attribution {#attribution-example}

Examinez l’exemple suivant :

1. Le 15 septembre, une personne arrive sur votre site par le biais d’une publicité de référencement payant, puis quitte.
1. Le 18 septembre, la personne revient sur votre site via un lien de réseau social qu’elle a reçu d’un ami. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
1. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre intervalle de recherche en amont et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples :

* En utilisant **première touche** et un **intervalle de recherche en amont de session**, l’attribution ne s’intéresse qu’à la troisième visite. Entre le courrier électronique et l’affichage, le courrier électronique était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $.

* À l’aide de **première touche** et d’un **intervalle de recherche en amont personne**, l’attribution examine les trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $.

* En utilisant **linéaire** et un **intervalle de recherche en amont de session**, le crédit est divisé entre l’e-mail et l’affichage. Ces deux chaînes ont chacune un crédit de 25 $.
En utilisant **linéaire** et un **intervalle de recherche en amont personne**, le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat.

* En utilisant la **en forme de J** et un **intervalle de recherche en amont personne**, le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage.

   * Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.
   * Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.

* À l’aide de **Dégradation dans le temps** et d’un **intervalle de recherche en amont**, le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage. Utilisation de la demi-vie de sept jours par défaut :

   * Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`
   * Intervalle de zéro jour entre le point de contact de l’e-mail et la conversion. `2^(-0/7) = 1`
   * Intervalle de six jours entre le point de contact social et la conversion. `2^(-6/7) = 0.552`
   * Intervalle de neuf jours entre le point de contact de référencement payant et la conversion. `2^(-9/7) = 0.41`
   * La normalisation de ces valeurs entraîne les résultats suivants :

      * Affichage : 33,8 %, gain de 16,88 $
      * Courrier électronique : 33,8 %, gain de 16,88 $
      * Réseaux sociaux : 18,6 %, gain de 9,32 $
      * Référencement payant : 13,8 %, gain de 6,92 $

Les événements de conversion qui comportent généralement des nombres entiers sont divisés si le crédit appartient à plusieurs canaux. Par exemple, si deux canaux contribuent à un ordre à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de cet ordre. Ces mesures partielles sont additionnées pour toutes les personnes, puis arrondies à l’entier le plus proche pour la création de rapports.


>[!MORELIKETHIS]
>
>[Paramètres des composants : attribution](/help/data-views/component-settings/attribution.md)
>[Mesure de participation ](participation-metric.md)
>

