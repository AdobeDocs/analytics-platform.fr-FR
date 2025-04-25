---
title: Configuration des paramètres de Report Builder dans Customer Journey Analytics
description: Décrit comment définir le mode hors ligne, la langue, la date et les paramètres de dépannage.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 29%

---

# Paramètres de Report Builder

Utilisez le volet **Paramètres** pour configurer les paramètres au niveau de l’application, tels que la langue affichée par l’interface utilisateur ou si vous souhaitez travailler ou non en mode hors ligne. Les paramètres sont appliqués immédiatement et ils sont définis pour toutes les sessions suivantes jusqu’à ce qu’ils soient modifiés.

Pour modifier les paramètres de Report Builder

1. Sélectionnez l’icône **Paramètres**.

1. Apportez des modifications à [activer ou désactiver le mode hors ligne](#off-line-mode), [sélectionner une langue](#language) ou [activer le dépannage](#troubleshooting).

1. Sélectionnez **[!UICONTROL Appliquer]**.

   ![Volet de période Report Builder affichant le bouton Annuler et appliquer.](./assets/report-builder-settings.png){zoomable="yes"}

## Mode hors ligne

Lorsque vous créez et modifiez un bloc de données en mode hors ligne, les données ne sont pas récupérées. Au lieu de cela, des données de simulation sont utilisées afin que vous puissiez travailler rapidement sans attendre que la requête s’exécute. Lorsque vous êtes de retour en ligne, sélectionnez ![Actualiser](/help/assets/icons/Refresh.svg) **[!UICONTROL Actualiser le bloc de données]** ou ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Actualiser tous les blocs de données]** pour actualiser les blocs de données avec les données réelles.

Pour activer le mode hors ligne

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg).

1. Activez le bouton (bascule) **[!UICONTROL Activer le mode hors ligne]**.

1. Saisissez un entier positif dans le champ **[!UICONTROL Afficher les données de mesure]**.

1. Sélectionnez **[!UICONTROL Appliquer]**.


## Langue

Vous pouvez choisir la langue de l’interface de Report Builder. Toutes les langues Customer Journey Analytics prises en charge sont disponibles.

Pour sélectionner la langue utilisée dans l’interface de Report Builder :

1. Sélectionnez une langue dans le menu déroulant **[!UICONTROL Langue]**.

1. Sélectionnez **Appliquer.**

## Résolution des problèmes

Le paramètre **[!UICONTROL Journaux de dépannage]** consigne toutes les données client/serveur dans un fichier local. Utilisez cette option pour résoudre les tickets d’assistance.

Pour activer les journaux de dépannage, cochez la case **[!UICONTROL Enregistrer la requête Report Builder dans le fichier local]**.
