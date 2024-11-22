---
title: Architecte de votre schéma à utiliser avec Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 7%

---

# Architecte de votre schéma à utiliser avec Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Adobe recommande de créer un schéma de modèle de données d’expérience (XDM) lors de la mise à niveau vers Customer Journey Analytics. Un schéma XDM permet de disposer d’un schéma rationalisé adapté aux besoins de votre entreprise et aux applications Platform spécifiques que vous utilisez. Lorsque des modifications du schéma sont requises, il n’est pas nécessaire de parcourir des milliers de champs inutilisés pour trouver le champ qui nécessite une mise à jour.

Consultez les sections suivantes lorsque vous commencez à concevoir votre schéma XDM.

## Éviter les restrictions Adobe Analytics dans votre schéma XDM

L’architecture sous-jacente de Customer Journey Analytics offre beaucoup plus de flexibilité qu’Adobe Analytics. La création d’un nouveau schéma XDM est un moyen clé de déverrouiller cette flexibilité. Lorsque vous effectuez une mise à niveau vers Customer Journey Analytics, veillez à éviter de transférer des restrictions Adobe Analytics inutiles dans votre schéma.

| Architecture des données Adobe Analytics | Architecture du schéma XDM |
|---------|----------|
| Des mesures individuelles sont ajoutées à l’architecture de données Analytics.<br/>Par exemple, dans Adobe Analytics, vous avez un eVar différent pour chaque événement. | Créez des mesures individuelles dans la vue de données plutôt que dans le schéma XDM. Cela vous offre davantage de flexibilité si vous devez apporter des modifications ultérieurement.<br/>Par exemple, en Customer Journey Analytics, vous avez un seul événement dans le schéma et vous utilisez créer des événements dans la vue de données. |
| Les props et les eVars sont nécessaires pour créer des variables personnalisées. | B2 |
| A3 | B3 |

## Identifier votre équipe de données et les autres parties prenantes au sein de votre organisation


## Tenir compte des autres applications Adobe Experience Platform utilisées dans votre entreprise



1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
