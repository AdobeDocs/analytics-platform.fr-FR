---
description: Adobe fournit diverses mesures calculées que vous pouvez utiliser. Cette page répertorie ces mesures et leurs utilisations prévues.
title: Mesures calculées par défaut
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 60%

---

# Mesures calculées par défaut

Customer Journey Analytics fournit diverses mesures calculées pour couvrir les cas d’utilisation les plus courants. Ces mesures calculées sont disponibles par défaut dans Analysis Workspace.

Vous trouverez ci-dessous une liste de chaque mesure calculée fournie par Adobe, avec sa fonction prévue et la formule sous-jacente utilisée pour le calcul :

>[!NOTE]
>
>Outre les mesures calculées par défaut décrites sur cette page, vous pouvez ajouter des mesures calculées supplémentaires à une vue de données.
>
>Vous pouvez :
> * Ajout de mesures calculées par défaut pour les médias en flux continu, comme décrit dans la section [Mesures calculées](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Créez des mesures calculées personnalisées à partir de mesures existantes, comme décrit dans la section [Mesures calculées ou calculées avancées (dérivées)](/help/components/calc-metrics/cm-adv-functions.md).



| Nom de la mesure calculée | Fonction | Formule |
|---------|----------|---------|
| Taux de rebond | Le rapport entre les visites qui contenait exactement un événement et le nombre de visites sur cette page. Cela peut vous aider à comprendre les éléments de dimension présentant le taux de rebond le plus élevé ou à afficher le taux de rebond total agrégé de votre site au fil du temps. | `[Bounces] / [Entries]` |
| Recettes / Visiteur | Le montant moyen des revenus générés par chaque personne individuelle visitant le site. | `[Revenue] / [Unique Visitors]` |
| Commandes / Visiteur | Nombre moyen de commandes ou de transactions générées par chaque visiteur et visiteuse du site | `[Orders] / [Unique Visitors]` |
| Recettes / Visites | Montant moyen du revenu généré par une seule visite sur le site. | `[Revenue] / [Visits]` |
| Recettes / Commande | Montant moyen des revenus générés par chaque transaction ou commande effectuée sur le site. | `[Revenue] / [Orders]` |
| Commandes / Visites | Pourcentage de visites sur le site qui ont abouti à une transaction. | `[Orders] / [Visits]` |
| Pages vues / Visites | Le nombre moyen de pages vues par un utilisateur ou une utilisatrice au cours d’une seule visite sur le site. | `[Page Views] / [Visits]` |
| Visites / Visiteur | Nombre moyen de visites qu’un visiteur ou une visiteuse unique effectue sur le site. | `[Visits] / [Unique Visitors]` |
| Actualisations / Pages vues | Le pourcentage de pages vues ayant entraîné un rechargement ou une actualisation de la page. | `[Reloads] / [Page Views]` |
| Taux de rebond moyen | Fonction | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Aide à la commande | Le nombre de fois qu’un canal ou une source a contribué au parcours d’un client ou d’une cliente vers l’achat, mais n’a pas abouti à l’achat final. | `[Orders (Visit Participation)] - [Orders]` |
| Taux de sortie | Pourcentage de visiteurs et visiteuses qui quittent le site après avoir consulté une page particulière. | `[Exits] / [Visits]` |
| Taux d’entrée | Le pourcentage de visiteurs et visiteuses qui sont entrés sur le site sur une page donnée, par rapport au nombre total de sessions sur le site. | `[Entries] / [Visits]` |
| Durée moyenne du site | Temps moyen qu’un visiteur ou une visiteuse passe sur le site avant de le quitter. | `[Average Time Spent on Site (Seconds)]` |
| Durée de la visite/de l’utilisateur (état) | Durée pendant laquelle le visiteur moyen ou la visiteuse moyenne passe dans un état particulier sur le site | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Utilisateurs (mobile) | Nombre total d’utilisateurs et d’utilisatrices d’une application mobile | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Utilisateurs de l’application | Nombre total d’utilisateurs et d’utilisatrices d’une application mobile | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Vues d’état | Nombre de vues des différents états ou écrans de l’application | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Actions | Nombre total d’actions entreprises dans l’application | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Clics sur les liens d’acquisition | Nombre de fois où les personnes cliquent sur un lien conçu pour générer du trafic vers le site. | `[Campaign Click-throughs]` |
| Vitesse de la page | Nombre de pages vues supplémentaires générées par un élément de contenu. Cela peut vous aider à déterminer quel contenu génère un engagement supplémentaire. | `[Page Views] / [Visits]` |
| Taux de conversion | Le pourcentage de visiteurs et visiteuses qui ont effectué l’action souhaitée (un achat, par exemple). | `[Orders] / [Visits]` |
| Durée de session moyenne (mobile) | Temps moyen passé par les visiteurs et visiteuses sur le site au cours d’une seule session. | Vide |
| Couverture Experience Cloud ID | Pourcentage de visiteurs et de visiteuses qui disposent d’un ID Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Vitesse du contenu | Vitesse à laquelle le nouveau contenu est créé et publié sur le site et la rapidité avec laquelle il génère de l’interaction client. | `[Page Views] / [Visits]` |
| Visiteurs uniques ITP 2.1 / Visiteurs uniques | Pourcentage de visiteurs et visiteuses uniques utilisant un navigateur affecté par les limitations de cookies ITP 2.1. En d’autres termes, il s’agit des clients et clientes qui n’utilisent pas une implémentation CNAME. (Cela s’applique aux personnes qui définissent des cookies via JavaScript côté client.) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Visiteurs uniques / Visiteurs uniques revenant après 7 jours | Le pourcentage de visiteurs et visiteuses uniques qui reviennent après une période de 7 jours ou plus. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Pages vues / Visiteur unique | Nombre moyen de pages vues pour chaque visiteur ou visiteuse unique sur le site. | `[Page Views] / [Unique Visitors]` |
| Visites/Visiteurs et visiteuses | Nombre moyen de visites qu’un visiteur ou une visiteuse unique effectue sur le site . | `[Visits] / [Unique Visitors]` |
| Nombre estimé de visiteurs uniques (ITP 2.1) | Pour les visiteurs ITP (utilisateurs sur les navigateurs Safari), divisez les visiteurs uniques par 2 ou moins. Cette mesure calculée suppose que vous définissez des cookies à l’aide de code JavaScript côté client (sans utiliser d’implémentation CNAME). Les mises en oeuvre qui définissent des cookies à l’aide de JavaScript côté client ont été affectées à partir d’ITP 2.1. Voir [Prévention intelligente du suivi](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) pour plus d’informations. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Pages vues/Nombre estimé de visiteurs uniques (ITP 2.1) | Nombre moyen de pages vues pour le nombre estimé de visiteurs et visiteuses uniques (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
