---
title: Comment configurer les paramètres pour Report Builder dans CJA
description: Décrit comment définir le mode hors ligne, la langue, la date et les paramètres de dépannage.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
source-git-commit: 4afd011561e6351e7d4da2dc6a2263ca835f0b08
workflow-type: ht
source-wordcount: '256'
ht-degree: 100%

---

# Paramètres de Report Builder

Utilisez le volet **Paramètres** pour configurer les paramètres au niveau de l’application, tels que la langue affichée par l’interface utilisateur ou si vous souhaitez travailler ou non en mode hors ligne. Les paramètres sont appliqués immédiatement et ils sont définis pour toutes les sessions suivantes jusqu’à ce qu’ils soient modifiés.

Pour modifier les paramètres de Report Builder

1. Cliquez sur l’icône **Paramètres**.

1. Apportez des modifications au mode hors ligne, sélectionnez une langue ou activez les paramètres du journal de dépannage.

1. Cliquez sur **Appliquer**.

   ![](./assets/image38.png)

## Mode hors ligne

Lors de la création et de la modification d’un bloc de données en mode hors ligne, les données ne sont pas récupérées. Au lieu de cela, des données de simulation sont utilisées afin que vous puissiez rapidement créer et éditer un bloc de données sans attendre l’exécution de la requête. Lorsque vous êtes de retour en ligne, la commande *Actualiser le bloc de données* ou *Actualiser tous les blocs de données* actualise les blocs de données que vous avez créés avec des données réelles.

Pour activer le mode hors ligne

1. Cliquez sur l’icône **Paramètres**.

1. Sélectionnez **Activation du mode hors ligne**.

1. Saisissez un nombre entier positif dans le champ **Afficher les données de mesure sous**.

1. Cliquez sur **Appliquer**.

## Langue

Vous pouvez choisir la langue de l’interface utilisateur de Report Builder. Toutes les langues Adobe Analytics prises en charge sont disponibles.

Pour sélectionner la langue utilisée dans l’interface utilisateur de Report Builder

1. Cliquez sur Paramètres.

1. Sélectionnez une langue dans le menu déroulant **Langue**.

   ![](./assets/image39.png)

1. Cliquez sur **Appliquer.**

## Résolution des problèmes

Utilisez le paramètre de dépannage pour consigner toutes les données client/serveur dans un fichier local. Utilisez cette option pour résoudre les tickets d’assistance.

Pour activer l’option Dépannage, sélectionnez **Enregistrer la requête Report Builder dans le fichier local**.
