---
title: Groupement
description: Découvrez comment créer et gérer des jeux de données assemblés
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

# Créer et gérer de jeux de données groupés

{{select-package}}

L’assemblage permet aux administrateurs de regrouper des identités sur des jeux de données disponibles dans Customer Journey Analytics. L’assemblage de jeux de données augmente la précision de la représentation d’un profil, ce qui se traduit par une meilleure analyse et un meilleur reporting.

Le processus de groupement vous permet de définir un **identifiant persistant** existant dans un jeu de données. Ensuite, associez cet identifiant persistant pour une fenêtre de relecture spécifique (quotidienne, hebdomadaire) avec l’ **identifiant transitoire** (identifiant de personne ou authentifié) le plus précis disponible pour ce jeu de données. Les identifiants de transition peuvent être des adresses électroniques, des numéros de téléphone, des identifiants CRM ou d’autres identités stockées dans le graphique. Voir [Présentation](overview.md) pour plus d’informations sur le groupement.

## Créer

Pour lancer le groupement, vous créez un ou plusieurs jeux de données assemblés. Pour créer un jeu de données assemblé :

1. Sélectionnez **[!UICONTROL ** Assemblage **]** dans **[!UICONTROL **&#x200B; Data Management &#x200B;**]** sur la barre supérieure.

2. Dans l’écran [!UICONTROL Jeux de données assemblés], sélectionnez **[!UICONTROL **&#x200B; Créer un jeu de données assemblé&#x200B;**]**.

   Une boîte de dialogue vous explique vos responsabilités.

3. Sélectionnez **[!UICONTROL **&#x200B; Continuer &#x200B;**]** si vous acceptez ces responsabilités.

   >[!NOTE]
   >
   >    Si vous sélectionnez **[!UICONTROL **&#x200B; Annuler &#x200B;**]**, vous ne pouvez pas créer de jeu de données assemblé.

4. Dans l’écran [!UICONTROL Jeux de données assemblés > Jeu de données assemblé sans titre] :

   1. Définissez un **[!UICONTROL ** nom du jeu de données **]** et (facultatif) **[!UICONTROL **&#x200B; Description &#x200B;**]**,

   2. Sélectionnez l’environnement de test dans la liste **[!UICONTROL **&#x200B; Sandbox &#x200B;**]** où est stocké le jeu de données d’événement.

      ![Écran de création initial](./assets/create-initial.png)

   3. Sélectionnez le bouton **[!UICONTROL **&#x200B; Sélectionner le jeu de données source &#x200B;**]** .

      Dans la fenêtre contextuelle [!UICONTROL Sélectionner un jeu de données à assembler] :

      ![Sélectionner un jeu de données](./assets/select-one-dataset.png)

      - Sélectionnez un jeu de données et sélectionnez **[!UICONTROL **&#x200B; Sélectionner &#x200B;**]** pour continuer.

   4. Sélectionnez un identifiant persistant dans la liste **[!UICONTROL **&#x200B; ID persistant &#x200B;**]**.

   5. Sélectionnez un identifiant transitoire dans la liste **[!UICONTROL **&#x200B; ID transitoire &#x200B;**]**.

      Un panneau d’aperçu s’affiche pour calculer les taux de saturation (nombre de fois où il existe une valeur pour chacun des identifiants spécifiés par rapport au nombre d’événements) pendant les sept derniers jours. Une fois le calcul terminé, le panneau se visualise avec des couleurs si les conditions minimales de groupement sont remplies (vert) ou non (rouge).

      ![ Créez un jeu de données assemblé avec des taux d’staturation ](./assets/create-before-experimenting.png)

      Les conditions minimales sont les suivantes :

      - saturation de l&#39;identifiant persistant : rate >= 95%

      - saturation de l’identifiant transitoire : rate >= 5%

        Si les conditions minimales sont remplies, vous pouvez tester des valeurs d’exemple.

      - Sélectionnez **[!UICONTROL **&#x200B; Créer des ID assemblés de démonstration &#x200B;**]**.

        Dans la boîte de dialogue [!UICONTROL Expérience avec des exemples de valeurs], un tableau s’affiche avec un exemple de valeur pour [!UICONTROL timestamp], [!UICONTROL Persistent ID], [!UICONTROL Transient ID], [!UICONTROL Stitched ID (Live)], [!UICONTROL Stitched ID (1-day replay)] et [!UICONTROL &#x200B; (relecture sur 7 jours)].

             ![Expérience avec des exemples de valeurs](./assets/experiment-sample-values.png)
            
            1. Saisissez une valeur pour **[!UICONTROL **Persistent ID**]**.
            
            2. Sélectionnez **[!UICONTROL **Actualiser les identifiants assemblés**]** pour voir l’effet du processus de groupement sur les données du jeu de données.
            
            3. Sélectionnez **[!UICONTROL **Close**]** lorsque vous avez terminé de tester les valeurs d’exemples.
        

        De retour dans l’écran [!UICONTROL Jeux de données assemblés > _Nom du jeu de données_] :

   6. Sélectionnez une option pour la fréquence et la période de redémarrage des données historiques à partir de la liste **[!UICONTROL **&#x200B; Fenêtre de relecture &#x200B;**]** .

      Vous pouvez choisir entre la valeur par défaut **[!UICONTROL ** Jour précédent, quotidien **]** ou **[!UICONTROL **&#x200B; 7 jours précédents, hebdomadaire &#x200B;**]**.

   7. Sélectionnez une valeur dans la liste **[!UICONTROL **&#x200B; Nombre moyen d&#39;événements quotidiens &#x200B;**]**.

   8. Saisissez une valeur (entre `0` et `12`) dans **[!UICONTROL **&#x200B; Nombre de mois à renvoyer &#x200B;**]**.

   9. Sélectionnez **[!UICONTROL **&#x200B; Enregistrer &#x200B;**]** pour enregistrer votre jeu de données assemblé et lancer le groupement.

## Afficher le statut

Vous pouvez afficher l’état du groupement dans la liste [!UICONTROL Jeux de données assemblés] .

- Sélectionnez **[!UICONTROL ** Assemblage **]** dans **[!UICONTROL **&#x200B; Data Management &#x200B;**]** sur la barre supérieure.

  Vous voyez une liste de jeux de données assemblés, chacun identifié avec [!UICONTROL Sandbox], [!UICONTROL Jeu de données Source], [!UICONTROL Status], [!UICONTROL État de renvoi], [!UICONTROL Propriétaire] et [!UICONTROL Date de création].

  ![Présentation des jeux de données assemblés](./assets/overview-stitched-datasetts.png)

  Les valeurs possibles pour [!UICONTROL Status] sont les suivantes :

  | Valeur | Explication |
  |-----|-----|
  | **[!UICONTROL **&#x200B; En file d’attente &#x200B;**]** | La demande est reçue et traitée bientôt. |
  | **[!UICONTROL **&#x200B; Création &#x200B;**]** en cours | Les ressources et le jeu de données nouvellement assemblé sont en cours de création. |
  | **[!UICONTROL **&#x200B; Assemblage en cours &#x200B;**]** | Il existe des ressources et un jeu de données assemblé et le groupement est en cours. |
  | **[!UICONTROL **&#x200B; Erreur &#x200B;**] **&#x200B; | Le groupement pose problème. Peut-être qu’un schéma a changé entre le jeu de données source et le jeu de données assemblé, le volume quotidien est trop important ou... (_**&#x200B;vous avez besoin de plus d’informations ici...**_). |

  >[!INFO]
  >
  >    Chaque fois qu’un état change, une notification est envoyée avec le message **[!UICONTROL **&#x200B; Jeu de données assemblé _nom du jeu de données_ a changé en état _nom de l’état _**]**.


  L’ [!UICONTROL &#x200B; état de renvoi &#x200B;] peut avoir les valeurs suivantes : 0 %, 25 %, 50 %, 75 % ou 100 %.

  Vous pouvez sélectionner l’icône d’information pour afficher une fenêtre contextuelle contenant plus de détails sur le jeu de données assemblé sélectionné.


## Supprimer

>[!NOTE]
>
>Vous ne pouvez supprimer que les jeux de données dont l’état est [!UICONTROL Assemblage en cours], [!UICONTROL Erreur] ou [!UICONTROL En file d’attente].


Pour supprimer un seul jeu de données assemblé :

- Sélectionnez **[!UICONTROL **...**]** pour le jeu de données assemblé et sélectionnez **[!UICONTROL **&#x200B; Supprimer &#x200B;**]** dans le menu.

  ![Suppression d’un jeu de données assemblé](./assets/delete-stitched-dataset.png)

Pour supprimer plusieurs données regroupées :

- Sélectionnez plusieurs jeux de données assemblés à l’aide de la case à cocher au début de chaque jeu de données répertorié.

- Sélectionnez **[!UICONTROL **...**]** dans l’un des jeux de données assemblés sélectionnés et sélectionnez **[!UICONTROL **&#x200B; Supprimer &#x200B;**]** dans le menu.
