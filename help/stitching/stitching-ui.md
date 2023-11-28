---
title: Assemblage
description: Découvrez comment créer et gérer des jeux de données assemblés
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# Création et gestion de jeux de données assemblés

{{select-package}}

L’assemblage permet aux administrateurs de regrouper des identités sur des jeux de données disponibles dans Customer Journey Analytics. L’assemblage de jeux de données augmente la précision de la représentation d’un profil, ce qui se traduit par une meilleure analyse et un meilleur reporting.

Le processus de groupement vous permet de définir une **identifiant persistant** dans un jeu de données. Associez ensuite cet identifiant persistant pour une fenêtre de relecture spécifique (quotidienne, hebdomadaire) avec la plus grande précision. **identifiant transitoire** (personne ou identifiant authentifié) disponible pour ce jeu de données. Les identifiants de transition peuvent être des adresses électroniques, des numéros de téléphone, des identifiants CRM ou d’autres identités stockées dans le graphique. Voir [Présentation](overview.md) pour plus d’informations sur le groupement.

## Créer

Pour lancer le groupement, vous créez un ou plusieurs jeux de données assemblés. Pour créer un jeu de données assemblé :

1. Sélectionner **[!UICONTROL ** Assemblage **]** de **[!UICONTROL ** Data Management **]** dans la barre supérieure.

2. Dans le [!UICONTROL Jeux de données groupés] écran, sélectionnez **[!UICONTROL ** Créer un jeu de données assemblé&#x200B;**]**.

   Une boîte de dialogue vous explique vos responsabilités.

3. Sélectionner **[!UICONTROL ** Continuer **]** si vous acceptez ces responsabilités.

   >[!NOTE]
   >
   >    Si vous sélectionnez **[!UICONTROL ** Annuler **]**, vous ne pouvez pas créer de jeu de données assemblé.

4. Dans le [!UICONTROL Jeux de données assemblés > Jeu de données assemblé sans titre] écran :

   1. Définition d’une **[!UICONTROL ** Nom du jeu de données **]** et (facultatif) **[!UICONTROL ** Description **]**,

   2. Sélectionnez l’environnement de test dans la **[!UICONTROL ** Sandbox **]** liste de l’emplacement de stockage du jeu de données d’événement.

      ![Écran de création initial](./assets/create-initial.png)

   3. Sélectionnez la variable **[!UICONTROL ** Sélectionner le jeu de données source **]** bouton .

      Dans le [!UICONTROL Sélectionner un jeu de données à assembler] fenêtre contextuelle :

      ![Sélectionner un jeu de données](./assets/select-one-dataset.png)

      - Sélectionnez un jeu de données, puis **[!UICONTROL ** Sélectionner **]** pour continuer.

   4. Sélectionnez un identifiant persistant dans la variable **[!UICONTROL ** Identifiant persistant **]** liste.

   5. Sélectionnez un identifiant transitoire dans la variable **[!UICONTROL ** Identifiant transitoire **]** liste.

      Un panneau d’aperçu s’affiche pour calculer les taux de saturation (nombre de fois où il existe une valeur pour chacun des identifiants spécifiés par rapport au nombre d’événements) pendant les sept derniers jours. Une fois le calcul terminé, le panneau se visualise avec des couleurs si les conditions minimales de groupement sont remplies (vert) ou non (rouge).

      ![Créer un jeu de données assemblé avec des taux de staturation](./assets/create-before-experimenting.png)

      Les conditions minimales sont les suivantes :

      - saturation de l&#39;identifiant persistant : rate >= 95%

      - saturation de l’identifiant transitoire : rate >= 5%

        Si les conditions minimales sont remplies, vous pouvez tester des valeurs d’exemple.

      - Sélectionner **[!UICONTROL ** Création d’identifiants assemblés pour la démonstration **]**.

        Dans le [!UICONTROL Expérience avec des exemples de valeurs] , un tableau s’affiche avec un exemple de valeur pour [!UICONTROL timestamp], [!UICONTROL Identifiant persistant], [!UICONTROL Identifiant transitoire], [!UICONTROL Identifiant assemblé (en direct)], [!UICONTROL Identifiant assemblé (relecture d’un jour)], et [!UICONTROL Identifiant assemblé (relecture sur 7 jours)].

            ![Expérimenter avec des valeurs d’échantillon](./assets/experiment-sample-values.png)
            
            1.  Saisissez une valeur pour le **[!UICONTROL **Identifiant persistant**]**.
            
            2.  Sélectionner **[!UICONTROL **Actualisation des identifiants assemblés**]** pour voir l’effet du processus de groupement sur les données du jeu de données.
            
            3.  Sélectionner **[!UICONTROL **Close**]** lorsque vous avez terminé de tester les valeurs d’exemple.
        

        De retour dans le [!UICONTROL Jeux de données assemblés > _Nom du jeu de données_] écran :

   6. Sélectionnez une option pour la fréquence et la période de réinitialisation des données historiques à partir du **[!UICONTROL ** Fenêtre de relecture **]** liste.

      Vous pouvez choisir entre la valeur par défaut. **[!UICONTROL ** Jour précédent, quotidien **]** ou **[!UICONTROL ** 7 jours précédents, hebdomadaire **]**.

   7. Sélectionnez une valeur dans la variable **[!UICONTROL ** Nombre moyen d’événements quotidiens **]** liste.

   8. Saisissez une valeur (entre `0` et `12`) dans **[!UICONTROL ** Nombre de mois à renvoyer **]**.

   9. Sélectionner **[!UICONTROL ** Enregistrer **]** pour enregistrer votre jeu de données assemblé et lancer le groupement.

## Afficher le statut

Vous pouvez afficher l’état du groupement dans le [!UICONTROL Jeux de données groupés] liste.

- Sélectionner **[!UICONTROL ** Assemblage **]** de **[!UICONTROL ** Data Management **]** dans la barre supérieure.

  Vous voyez une liste de jeux de données assemblés, chacun identifié avec [!UICONTROL Sandbox], [!UICONTROL Jeu de données source], [!UICONTROL État], [!UICONTROL État de renvoi], [!UICONTROL Propriétaire], et [!UICONTROL Date de création].

  ![Présentation des jeux de données assemblés](./assets/overview-stitched-datasetts.png)

  Valeurs possibles pour [!UICONTROL État] sont :

  | Valeur | Explication |
  |-----|-----|
  | **[!UICONTROL ** En file d’attente **]** | La demande est reçue et traitée bientôt. |
  | **[!UICONTROL ** En cours de création **]** | Les ressources et le jeu de données nouvellement assemblé sont en cours de création. |
  | **[!UICONTROL ** Groupement en cours **]** | Il existe des ressources et un jeu de données assemblé et le groupement est en cours. |
  | **[!UICONTROL ** Erreur **]** | Le groupement pose problème. Peut-être qu’un schéma a changé entre le jeu de données source et le jeu de données assemblé, le volume quotidien est trop important ou... (_**besoin de plus d&#39;informations ici...**_) |

  >[!INFO]
  >
  >    Lorsqu&#39;un état change, une notification est envoyée avec le message **[!UICONTROL ** Jeu de données assemblé _nom du jeu de données_ a été modifié en état _nom de l’état _**]**.


  La variable [!UICONTROL État de renvoi] peuvent avoir les valeurs suivantes : 0 %, 25 %, 50 %, 75 % ou 100 %.

  Vous pouvez sélectionner l’icône d’information pour afficher une fenêtre contextuelle contenant plus de détails sur le jeu de données assemblé sélectionné.


## Supprimer

>[!NOTE]
>
>Vous pouvez uniquement supprimer les jeux de données dont l’état est le suivant : [!UICONTROL Assemblage en cours], [!UICONTROL Erreur], ou [!UICONTROL En file d&#39;attente].


Pour supprimer un seul jeu de données assemblé :

- Sélectionner **[!UICONTROL **..**]** pour le jeu de données assemblé et sélectionnez **[!UICONTROL ** Supprimer **]** dans le menu.

  ![Suppression d’un jeu de données associé](./assets/delete-stitched-dataset.png)

Pour supprimer plusieurs données regroupées :

- Sélectionnez plusieurs jeux de données assemblés à l’aide de la case à cocher au début de chaque jeu de données répertorié.

- Sélectionner **[!UICONTROL **..**]** dans l’un des jeux de données assemblés sélectionnés et sélectionnez **[!UICONTROL ** Supprimer **]** dans le menu.
