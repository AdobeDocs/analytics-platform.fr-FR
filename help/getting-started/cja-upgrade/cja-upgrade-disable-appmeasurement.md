---
title: Ajouter le jeu de données du connecteur source Analytics à la connexion
description: Découvrez comment ajouter le jeu de données du connecteur source Analytics à la connexion
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 9%

---

# Désactiver la collecte de données d’AppMeasurement {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Désactiver la collecte de données d’AppMeasurement"
>abstract="Une fois les données Web SDK entièrement fonctionnelles, travaillez avec votre équipe de développement pour supprimer AppMeasurement.js de votre site web ou de votre propriété.<br><br>La suppression d’AppMeasurement d’un site web ne prend que quelques minutes, mais il faut du temps à votre équipe d’ingénieurs pour l’accomplir. Veillez toutefois à ce que vos utilisateurs Analytics utilisent Customer Journey Analytics et non Adobe Analytics ; ce processus d’annonce pour déplacer tout le monde peut prendre considérablement plus de temps si vous ne l’avez pas déjà fait."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou suivre les étapes de mise à niveau qui ont été générées dynamiquement pour votre organisation à l’aide du [questionnaire de mise à niveau d’Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois les étapes de cette page terminées, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

<!-- need to work on this -->

* **Balises :** désactivation de l’extension Adobe Analytics

* **AppMeasurment :** remplacer la bibliothèque AppMeasurement.js s=newobject
