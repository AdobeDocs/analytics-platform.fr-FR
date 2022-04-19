---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 70ca04d647645d6ba69f07110f0deced03bd0a77
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# Notes de mise à jour du Customer Journey Analytics actuel (CJA) (avril 2022)

>[!NOTE]
>
>Cette page contient des informations de version préliminaire qui peuvent être modifiées.

**Dernière mise à jour**: 19 avril 2022

## Principales fonctionnalités

| Fonctionnalité | Description | [Date ciblée](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Sous-chaînes de Dimension | Fournit plusieurs méthodes pour extraire la partie souhaitée d’une chaîne à utiliser comme éléments de dimension. Cette fonctionnalité vous permet également de traiter une dimension de chaîne comme un tableau si la chaîne contient des valeurs délimitées. [En savoir plus](../data-views/component-settings/substring.md) | 20 avril 2022 |
| Préparation de données pour Analytics Source Connector | Le [Connecteur source Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=fr) est désormais intégré à la fonction [Préparation de données](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) fonctionnalités fournies par Adobe Experience Platform. Les clients Adobe Real-time Customer Data Platform (RTCDP), CJA et Adobe Journey Optimizer (AJO) peuvent désormais étendre le groupe de champs Analytics avec des groupes de champs supplémentaires. Ils peuvent également utiliser plus de 100 opérateurs de préparation de données pour enrichir les données Analytics lors de l’ingestion dans Adobe Experience Platform (AEP). Les clients RTCDP peuvent désormais activer plusieurs suites de rapports compatibles avec la préparation de données pour Profile.<p>Les clients CJA qui ingèrent plusieurs suites de rapports via Analytics Source Connector ont désormais un moyen de démêler les différences de colonnes entre les suites de rapports. Par exemple, si &quot;Terme de recherche&quot; est stocké dans `eVar1` dans une suite de rapports et dans `eVar2` dans une autre suite de rapports, vous pouvez étendre le groupe de champs Analytics à l’aide d’une nouvelle colonne qui fusionne les valeurs des deux eVars. | 27 avril 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/release-notes/doc-changes.md)
