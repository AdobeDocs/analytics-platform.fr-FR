---
title: Afficher les notes de mise à jour actuelles de Customer Journey Analytics
description: Dernières notes de mise à jour de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 100%

---

# Notes de mise à jour actuelles de Customer Journey Analytics

## Principales mises à jour

Options relatives à la [!UICONTROL persistance] pour les dimensions et mesures de liaison| Lors de la création ou de la modification d’une vue de données, vous pouvez lier la persistance d’une dimension à une autre dimension ou mesure. Ce concept est connu sous le nom de _marchandisage_ dans Reports &amp; Analytics et est désormais pris en charge dans CJA. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#binding-dimension)| 19 janvier 2022 |

## Autres mises à jour

| Fonctionnalité | Description | Date ciblée |
| ----------- | ---------- | ----- |
| Modèles d’attribution [!UICONTROL Premier connu] et [!UICONTROL Dernier connu] | Ces deux nouveaux modèles d’attribution prennent la première ou la dernière valeur observée pour une dimension dans une portée de persistance spécifiée (session, personne ou période personnalisée avec recherche arrière). Ils appliquent ensuite le modèle d’attribution à tous les événements de la portée spécifiée. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=fr#allocation-settings) | 19 janvier 2022 |
| [!UICONTROL PersonID] et [!UICONTROL Espace de noms PersonID] comme dimensions | Expose la variable `personID` (ou `customerID`, ou l’identifiant que vous utilisez pour fusionner des jeux de données dans une connexion) en tant que dimension dans les vues de données. Cette amélioration facilite l’inclusion de la variable `personID` comme dimension dans votre vue de données en l’extrayant de la connexion. [En savoir plus](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=fr#optional-standard-components) | 19 janvier 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Mises à jour de la documentation de Customer Journey Analytics](/help/doc-changes.md)
