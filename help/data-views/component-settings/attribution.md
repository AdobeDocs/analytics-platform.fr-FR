---
title: Paramètres du composant d’attribution
description: Permet de définir l’attribution par défaut d’une mesure.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 69%

---


# Paramètres du composant d’attribution

Attribution vous permet de définir un modèle d’attribution par défaut pour une mesure. Vous pouvez remplacer le modèle d’attribution d’une mesure donnée lorsque vous travaillez dans Analysis Workspace.

![Attribution](../assets/attribution-settings.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Définir l’attribution] | Active un modèle d’attribution par défaut lorsque cette mesure est utilisée. Cette valeur par défaut peut être remplacée dans un [!UICONTROL tableau à structure libre] ou dans une mesure calculée. |
| [!UICONTROL Modèle d’attribution] | Permet de spécifier le [modèle d’attribution par défaut](/help/analysis-workspace/attribution/models.md) à utiliser. La valeur par défaut est [!UICONTROL Dernière touche]. Les options sont les suivantes : Dernière touche, Première touche, Linéaire, Participation, Même touche, En U, Courbe en J, J inversé, Dégradation dans le temps, Personnalisé et Algorithmique. Certaines de ces options créent des champs supplémentaires à remplir (par exemple, Personnalisé ou Dégradation dans le temps). Vous pouvez créer plusieurs mesures à lʼaide du même champ, ce qui signifie que vous pouvez avoir une mesure Chiffre dʼaffaires définie sur [!UICONTROL Dernière touche] et une mesure Chiffre dʼaffaires définie sur [!UICONTROL Première touche], mais basées sur le même champ Chiffre dʼaffaires dans le schéma. |
| [!UICONTROL Intervalle de recherche en amont] | Permet de spécifier un intervalle de recherche en amont par défaut pour une mesure. Les options sont les suivantes : [!UICONTROL Personne] (intervalle du compte rendu des performances), [!UICONTROL Session] et [!UICONTROL Personnalisé]. Lorsque lʼoption [!UICONTROL Personnalisé] est sélectionnée, nous vous offrons également la possibilité de sélectionner nʼimporte quel nombre de jours/semaines/mois, etc. (jusquʼà 90 jours), à lʼinstar dʼ[!UICONTROL Attribution IQ]. Vous pouvez avoir plusieurs mesures à lʼaide du même champ de schéma, mais chacune dispose dʼun intervalle de recherche en amont distinct. |
