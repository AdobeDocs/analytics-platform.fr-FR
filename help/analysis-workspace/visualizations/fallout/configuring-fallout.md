---
description: Découvrez comment spécifier les points de contact pour créer une séquence d’abandons multidimensionnelle.
title: Configuration d’une visualisation Abandons
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 71%

---

# Configuration d’une visualisation Abandons

Vous pouvez spécifier les points de contact d’après lesquels créer une séquence d’abandons multidimensionnelle. En général, un point de contact est une page sur votre site. Ils ne se limitent toutefois pas à cela. Vous pouvez par exemple ajouter des événements, tels que des unités, ainsi que des personnes uniques et des visites récurrentes. Vous pouvez aussi ajouter des dimensions, telles qu’une catégorie, un type de navigateur ou un terme de recherche interne.

Il est possible en outre d’ajouter des filtres dans un point de contact. Par exemple, vous pourriez vouloir comparer des filtres, tels que les utilisateurs d’iOS et d’Android. Faites glisser les filtres souhaités en haut de l’abandon pour ajouter des informations sur ces filtres au rapport sur les abandons. Pour afficher seulement ces filtres, supprimez la ligne de base Toutes les visites.

Il n’existe aucune restriction quant au nombre d’étapes pouvant être ajoutées ou au nombre de dimensions utilisées.

Vous pouvez effectuer le cheminement sur les eVars, y compris les eVars de marchandisage et les [listVars](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=fr) (variables pouvant avoir plusieurs valeurs par événement, telles que les produits, les listVars, les eVars de marchandisage et les props de liste). Supposons par exemple qu’un visiteur consulte sur une page la séquence chaussures, chemise puis, sur la page suivante, la séquence chemise, chaussettes. Le prochain rapport de flux de produits généré à partir des chaussures portera sur chemise et chaussettes, SAUF chemise.

1. Faites glisser une visualisation [!UICONTROL Abandons] de la liste déroulante des visualisations dans un [!UICONTROL tableau à structure libre].

1. Faites glisser la dimension Page dans le tableau à structure libre puis, de là, faites glisser une page (dans ce cas, Home - JJEsquire) sur le champ **[!UICONTROL Ajouter un point de contact]** comme premier point de contact.

   ![](assets/fallout1.png)

   Passez la souris sur un point de contact pour afficher les abandons et d’autres informations sur ce niveau, telles que le nom du point de contact, le nombre de personnes à ce point, ainsi que le taux de succès de ce point de contact (et comparez-le à d’autres points de contact).

   Les nombres encadrés dans la partie grise de la barre correspondent aux abandons entre les points de contact (et non à l’ensemble des abandons à ce point). Le % point de contact présente les accès immédiats réussis de l’étape précédente à l’étape actuelle dans le rapport des abandons.

   Vous pouvez également ajouter une seule page au rapport des abandons, plutôt que la dimension entière. Cliquez sur la flèche droite (>) sur la dimension de page pour sélectionner la page à ajouter au rapport des abandons.

1. Continuez à ajouter des points de contact jusqu’à ce que votre séquence soit complète.

   Vous pouvez **combiner plusieurs points de contact** en les faisant glisser les uns sur les autres.

   >[!NOTE]
   >
   >Plusieurs filtres sont reliés par l’opérateur AND, mais plusieurs éléments, tels que des éléments de dimension et des mesures, sont reliés par l’opérateur OR.

   ![](assets/multiple_obj_touchpoint.png)

1. Vous pouvez également **contrainte les points de contact individuels à l’événement suivant ;** (par opposition à &quot;finalement&quot;) dans le chemin. Chaque point de contact est assorti d’un sélecteur avec les options « Chemin d’accès éventuel » et « Prochain accès », comme illustré ici :

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chemin d’accès éventuel </p> <p>(Par défaut) </p> </td> 
   <td colname="col2"> <p>Les visiteurs sont comptabilisés et finiront par accéder à la page suivante du chemin, mais pas nécessairement à l’événement suivant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prochain accès </p> </td> 
   <td colname="col2"> <p>Les visiteurs sont comptabilisés et accèdent à la page suivante du chemin d’accès à l’événement suivant. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paramètres d’abandon {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Paramètre | Description |
|--- |--- |
| Conteneur d’abandons <ul><li>Visite</li><li>Visiteur</li></ul> | Permet de basculer entre Visite et Visiteur afin d’analyser le cheminement de la personne. La valeur par défaut est Visiteur.  Ces paramètres vous aident à comprendre l’engagement des personnes au niveau de la personne (entre les visites) ou à contraindre l’analyse à une seule visite. |

Lorsque vous **cliquez avec le bouton droit de la souris sur un point de contact**, les options suivantes s’affichent :

| Option | Description |
|--- |--- |
| Point de contact de tendance | Consultez dans un graphique linéaire les données sur les tendances d’un point de contact, avec quelques données de détection des anomalies prédéfinies. |
| Point de contact de tendance (%) | Calcule la tendance du pourcentage total d’abandons. |
| Tendance tous points de contact (%) | Calcule la tendance de tous les pourcentages des points de contact de l’abandon (sauf « Toutes les visites » si inclus) sur le même graphique. |
| Ventiler les abandons à ce point de contact | Vérifiez ce que les personnes ont fait entre deux points de contact (ce point de contact et le point de contact suivant) si elles ont continué jusqu’au point de contact suivant. Un tableau à structure libre présentant les dimensions est ainsi créé. Vous pouvez y remplacer les dimensions et d’autres éléments qui le composent. |
| Ventiler les abandons à ce point de contact | Vérifiez quelles personnes qui n’ont pas franchi l’entonnoir l’ont fait immédiatement après l’étape sélectionnée. |
| Créer un filtre à partir du point de contact | Créez un nouveau filtre à partir du point de contact sélectionné. |
