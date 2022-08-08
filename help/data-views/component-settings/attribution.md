---
title: 'Paramètres des composants : attribution'
description: Permet de définir lʼattribution par défaut dʼune mesure.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%

---

# Paramètres des composants : attribution

Lʼattribution vous permet de définir un modèle dʼattribution par défaut pour une mesure. Vous pouvez remplacer le modèle dʼattribution dʼune mesure donnée lorsque vous travaillez dans Analysis Workspace.

![Attribution](../assets/attribution-settings.png)

| Paramètre | Description/Cas d’utilisation |
| --- | --- |
| [!UICONTROL Définir l’attribution] | Active un modèle dʼattribution par défaut lorsque cette mesure est utilisée. Cette valeur par défaut peut être remplacée dans un [!UICONTROL tableau à structure libre] ou dans une mesure calculée. |
| [!UICONTROL Modèle d’attribution] | Permet de définir le [modèle dʼattribution](/help/analysis-workspace/attribution/models.md) par défaut à utiliser. La valeur par défaut est [!UICONTROL Dernière touche]. Les options sont les suivantes : Dernière touche, Première touche, Linéaire, Participation, Même touche, En U, Courbe en J, J inversé, Dégradation dans le temps, Personnalisé et Algorithmique. Certaines de ces options créent des champs supplémentaires à remplir (par exemple, Personnalisé ou Dégradation dans le temps). Vous pouvez créer plusieurs mesures à lʼaide du même champ, ce qui signifie que vous pouvez avoir une mesure Chiffre dʼaffaires définie sur [!UICONTROL Dernière touche] et une mesure Chiffre dʼaffaires définie sur [!UICONTROL Première touche], mais basées sur le même champ Chiffre dʼaffaires dans le schéma. |
| [!UICONTROL Intervalle de recherche en amont] | Permet de spécifier un intervalle de recherche en amont par défaut pour une mesure. Les options sont les suivantes : [!UICONTROL Personne] (intervalle du compte rendu des performances), [!UICONTROL Session] et [!UICONTROL Personnalisé]. Lorsque lʼoption [!UICONTROL Personnalisé] est sélectionnée, nous vous offrons également la possibilité de sélectionner nʼimporte quel nombre de jours/semaines/mois, etc. (jusquʼà 90 jours), à lʼinstar dʼ[!UICONTROL Attribution IQ]. Vous pouvez avoir plusieurs mesures à lʼaide du même champ de schéma, mais chacune dispose dʼun intervalle de recherche en amont distinct. |

{style=&quot;table-layout:auto&quot;}
