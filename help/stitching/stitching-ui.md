---
title: Groupement
description: Découvrez comment créer et gérer des jeux de données groupés
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Créer et gérer des jeux de données groupés

{{select-package}}

L’assemblage permet aux administrateurs d’assembler des identités sur les jeux de données disponibles dans Customer Journey Analytics. L’assemblage de jeux de données augmente la précision de la représentation d’un profil, ce qui se traduit par une meilleure analyse et un meilleur compte rendu des performances.

Le processus d’assemblage vous permet de définir un **identifiant persistant** existant dans un jeu de données. Combinez ensuite cet identifiant persistant pour une fenêtre de relecture spécifiée (quotidienne, hebdomadaire) avec l’**identifiant transitoire** (identifiant de personne ou authentifié) disponible le plus précis pour ce jeu de données. Parmi les exemples d’identifiants transitoires figurent l’adresse e-mail, le numéro de téléphone, l’identifiant CRM ou d’autres identités stockées dans le graphique. Voir [Aperçu](overview.md) pour plus d’informations sur le groupement.

## Créer

Pour lancer le groupement, vous créez un ou plusieurs jeux de données groupés. Pour créer un jeu de données groupé :

1. Sélectionnez **[!UICONTROL ** Assemblage **]** dans **[!UICONTROL ** Gestion des données **]** dans la barre supérieure.

2. Dans l’écran [!UICONTROL Jeux de données groupés], sélectionnez **[!UICONTROL ** Créer un jeu de données groupé&#x200B;**]**.

   Une boîte de dialogue vous expliquant vos responsabilités s’affiche.

3. Sélectionnez **[!UICONTROL ** Continuer **]** si vous acceptez ces responsabilités.

   >[!NOTE]
   >
   >    Si vous sélectionnez **[!UICONTROL ** Annuler **]**, vous ne pouvez pas créer de jeu de données groupé.

4. À l’écran [!UICONTROL Jeux de données groupés > Jeu de données groupé sans titre] :

   1. Définissez un **[!UICONTROL ** Nom du jeu de données **]** et (facultatif) **[!UICONTROL ** Description **]**,

   2. Sélectionnez la sandbox dans la liste **[!UICONTROL ** Sandbox **]** où le jeu de données d’événement est stocké.

      ![Écran de création initiale](./assets/create-initial.png)

   3. Sélectionnez le bouton **[!UICONTROL ** Sélectionner le jeu de données source **]**.

      Dans la fenêtre contextuelle [!UICONTROL Sélectionner un jeu de données à grouper] :

      ![Sélectionner un jeu de données](./assets/select-one-dataset.png)

      - Sélectionnez un jeu de données, puis sélectionnez **[!UICONTROL ** Sélectionner **]** pour continuer.

   4. Sélectionnez un identifiant persistant dans la liste **[!UICONTROL ** ID persistant **]**.

   5. Sélectionnez un identifiant transitoire dans la liste **[!UICONTROL ** ID transitoire **]**.

      Vous remarquerez qu’un panneau d’aperçu s’affiche pour calculer les taux de saturation (nombre de fois qu’il existe une valeur pour chacun des identifiants spécifiés par rapport au nombre d’événements) pour les sept derniers jours. Une fois les calculs terminés, le panneau affiche les couleurs pour déterminer si les conditions minimales de groupement sont remplies (vert) ou non (rouge).

      ![Créer un jeu de données groupé avec des taux de staturation](./assets/create-before-experimenting.png)

      Les conditions minimales sont les suivantes :

      - saturation persistante des identifiants : taux >= 95 %

      - saturation transitoire des identifiants : taux >= 5%

        Si les conditions minimales sont remplies, vous pouvez tester les valeurs d’échantillon.

      - Sélectionnez **[!UICONTROL ** Créer des ID de démonstration groupés **]**.

        Dans la boîte de dialogue [!UICONTROL Expérimenter avec des valeurs d’échantillon], un tableau s’affiche avec des valeurs d’exemple pour [!UICONTROL horodatage], [!UICONTROL ID persistant], [!UICONTROL ID temporaire], [!UICONTROL ID groupé (actif)], [!UICONTROL ID groupé (relecture d’un jour)] et [!UICONTROL ID groupé (relecture de sept jours)].

             ![Essayez avec des exemples de valeurs](./assets/experiment-sample-values.png)
            
            1.  Saisissez une valeur pour l’ID persistant **[!UICONTROL **]**.
            
            2.  Sélectionnez **[!UICONTROL **Actualiser les ID groupés**]** pour voir l’effet du processus de groupement sur les données du jeu de données.3 
            
            .  Sélectionnez **[!UICONTROL **Fermer**]** lorsque vous avez terminé d’expérimenter avec les valeurs d’échantillons.
        

        De retour dans l’écran [!UICONTROL Jeux de données groupés > _Nom du jeu de données_] :

   6. Sélectionnez une option pour la fréquence et la période de retraitement des données historiques dans la liste **[!UICONTROL ** Fenêtre de relecture **]**.

      Vous pouvez choisir entre la valeur par défaut **[!UICONTROL ** Jour précédent, quotidien **]** ou **[!UICONTROL ** Sept jours précédents, hebdomadaire **]**.

   7. Sélectionnez une valeur dans la liste **[!UICONTROL ** Nombre moyen d’événements quotidiens **]**.

   8. Saisissez une valeur (entre `0` et `12`) en **[!UICONTROL ** Nombre de mois pour le renvoi **]**.

   9. Sélectionnez **[!UICONTROL ** Enregistrer **]** pour enregistrer le jeu de données groupé et lancer le groupement.

## Afficher le statut

Vous pouvez afficher le statut du groupement dans la liste [!UICONTROL Jeux de données groupés].

- Sélectionnez **[!UICONTROL ** Assemblage **]** dans **[!UICONTROL ** Gestion des données **]** dans la barre supérieure.

  Une liste de jeux de données groupés, chacun identifié avec [!UICONTROL Sandbox], [!UICONTROL jeu de données Source], [!UICONTROL Statut], [!UICONTROL Statut de renvoi], [!UICONTROL Propriétaire] et [!UICONTROL Date de création], s’affiche.

  ![Présentation des jeux de données groupés](./assets/overview-stitched-datasetts.png)

  Les valeurs possibles pour [!UICONTROL Status] sont les suivantes :

  | Valeur | Explication |
  |-----|-----|
  | **[!UICONTROL ** En file d’attente **]** | La demande est reçue et traitée bientôt. |
  | **[!UICONTROL ** Création **]** en cours | Des ressources et un jeu de données nouvellement groupé sont en cours de création. |
  | **[!UICONTROL ** Groupement en cours **]** | Des ressources et un jeu de données groupé existent et le groupement est en cours |
  | **[!UICONTROL ** Erreur **]** | Il y a un problème de groupement. Peut-être qu’un schéma a changé entre le jeu de données source et le jeu de données groupé, que le volume quotidien est trop grand, ou... (_**plus d’informations ici...**_) |

  >[!INFO]
  >
  >    Chaque fois qu’un statut est modifié, une notification est envoyée avec le message **[!UICONTROL ** Jeu de données groupé _nom du jeu de données_ est remplacé par le statut _nom du statut _**]**.


  Le [!UICONTROL statut de renvoi] peut avoir les valeurs suivantes : 0 %, 25 %, 50 %, 75 % ou 100 %.

  Vous pouvez sélectionner l’icône d’information pour afficher une fenêtre contextuelle contenant plus de détails sur le jeu de données groupé sélectionné.


## Supprimer

>[!NOTE]
>
>Vous pouvez uniquement supprimer les jeux de données dont le statut est [!UICONTROL Groupement en cours], [!UICONTROL Erreur] ou [!UICONTROL En file d’attente].


Pour supprimer un seul jeu de données groupé :

- Sélectionnez **[!UICONTROL **...**]** pour le jeu de données groupé et sélectionnez **[!UICONTROL ** Supprimer **]** dans le menu.

  ![Supprimer un jeu de données groupé](./assets/delete-stitched-dataset.png)

Pour supprimer plusieurs données groupées :

- Sélectionnez plusieurs jeux de données groupés à l’aide de la case à cocher au début de chaque jeu de données répertorié.

- Sélectionnez **[!UICONTROL **...**]** dans l’un des jeux de données groupés sélectionnés et sélectionnez **[!UICONTROL ** Supprimer **]** dans le menu.
