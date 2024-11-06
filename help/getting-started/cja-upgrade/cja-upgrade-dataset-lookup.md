---
title: Création d’un schéma pour Customer Journey Analytics
description: Découvrez le chemin recommandé lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Création de jeux de données de recherche pour classer les données dans Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Tout comme les données de classification dans Adobe Analytics, les jeux de données de recherche sont la méthode de classification des données dans Customer Journey Analytics.

Lors de l’utilisation du connecteur source Analytics, certains jeux de données de recherche standard sont automatiquement appliqués au moment du rapport. Pour plus d’informations, voir [Ajout de recherches standard à vos jeux de données](/help/connections/standard-lookups.md).

Pour classer les données avec une nouvelle implémentation du SDK Web Experience Platform, vous devez créer un jeu de données de recherche pour chaque dimension qui contient des données que vous souhaitez classer.

Pour créer des jeux de données de recherche à utiliser dans Customer Journey Analytics :

1. Dans AEP, créez un schéma. Il s’agit d’un nouveau schéma spécifique aux jeux de données de recherche. Vous ne pouvez pas utiliser un schéma existant.

1. Vous devez créer une classe de schéma destinée aux recherches.

1. Créez un jeu de données de recherche à partir de celui-ci.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
