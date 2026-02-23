---
title: Validation De L’Assemblage D’Identités Dans Customer Journey Analytics
description: Découvrez comment valider la combinaison d’identités dans Customer Journey Analytics. Mesurez les taux d’authentification et d’identification avant et après l’assemblage.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 0%

---

# Valider le groupement

L’objectif du [groupement d’identités](/help/stitching/overview.md) (ou simplement du groupement) est d’améliorer l’adéquation d’un jeu de données d’événement pour l’analyse cross-canal. Cette élévation est atteinte lorsque toutes les lignes de données du jeu de données contiennent l’identité d’ordre le plus élevé disponible. Cette élévation permet d’effectuer les opérations suivantes :

* Créez des rapports centrés sur la personne, sans exclure les personnes anonymes.
* Connectez plusieurs appareils à une seule personne.
* Connecter une personne sur plusieurs canaux.

Cet article décrit des méthodes d’analyse pour mesurer l’élévation d’un ou de plusieurs jeux de données groupés nouvellement créés et pour garantir que le groupement offre ces avantages.

Les méthodes d’analyse impliquent des [paramètres des composants de vue de données](/help/data-views/component-settings/overview.md) qui sont généralement accessibles aux administrateurs. Les méthodes nécessitent également que les analystes, qui travaillent dans un projet Analysis Workspace, créent des mesures calculées et des visualisations.

Bien que ces méthodes d’analyse puissent être utilisées pour le groupement basé sur les champs et le groupement basé sur les graphiques, certains éléments peuvent ne pas être présents dans le jeu de données, en particulier dans un scénario de groupement basé sur les graphiques. Ces éléments manquants peuvent rendre difficile le calcul de l’effet élévateur directement dans Analysis Workspace.

>[!NOTE]
>
>L’assemblage (validation de) d’un ou de plusieurs jeux de données contribue finalement à une meilleure analyse et à de meilleures informations. Cependant, cet article ne traite pas de la valeur globale d’une configuration Customer Journey Analytics dans laquelle tous les jeux de données d’Experience Platform sont alignés sur le même espace de noms d’identité. Et que tous ces jeux de données sont joliment associés pour effectuer une analyse sur l’ensemble d’un parcours client.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Activation et validation du groupement](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics-learn/tutorials/visitor-id/stitching-enablement-and-validation){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



## Groupement dans la validation des connexions

Cette section explique comment valider le groupement que vous avez activé dans l’interface Connexions.

### Recommandations de connexion

Pour valider le groupement que vous avez activé dans l’interface Connexions, sélectionnez une période courte et représentative pour le **[!UICONTROL renvoi du jeu de données]**. Par exemple, une semaine.

Dans l’exemple ci-dessous, vous souhaitez assembler le jeu de données d’événement. Vous avez configuré une connexion de test dans laquelle vous ajoutez le jeu de données d’événement. Pour ce jeu de données, vous définissez l’**[!UICONTROL ECID]** **[!UICONTROL Espace de noms]** comme **[!UICONTROL ID persistant]** et **[!UICONTROL Adresse e-mail hachée du visiteur (directMarketing.hashedEmail)]** comme **[!UICONTROL ID de personne]**. Pour valider ce groupement, vous définissez un **[!UICONTROL renvoi de jeu de données]** pour une petite période (24 janvier 2026 - 10 février 2026). Utilisez cette petite fenêtre pour vérifier si le groupement fonctionne comme prévu.

![Configuration du groupement](/help/stitching/assets/stitching-config.png)

### Conditions préalables relatives aux vues de données

Pour la validation de l’assemblage, vous devez vous assurer que toutes les dimensions et mesures requises de votre jeu de données assemblé sont définies dans une vue de données. Créez une vue de données basée sur la connexion que vous avez définie précédemment. À l’étape **[!UICONTROL Composants]** de la configuration des vues de données, vous devez :

* Ajoutez **[!UICONTROL Espace de noms d’identité]** de **[!UICONTROL Mesures et dimensions]** en tant que dimension à la liste **[!UICONTROL Dimensions]**.

  ![Espace de noms d’identité](/help/stitching/assets/identity-namespace.png)


* Sélectionnez l’**[!UICONTROL identifiant d’adresse e-mail hachée du visiteur]** que vous avez défini comme ID de personne pour vos événements à partir des **[!UICONTROL champs de schéma]**. Ajoutez le champ en tant que dimension à la liste **[!UICONTROL Dimensions]** et en tant que mesure à la liste **[!UICONTROL Mesures]**. Modifiez le **[!UICONTROL Nom du composant]** pour la mesure à `Email set`.

  ![Identifiant de l&#39;email](/help/stitching/assets/email-identifier.png)

Veillez à enregistrer la vue de données.

### Créer un projet Workspace

Dans Workspace, créez un projet et utilisez un tableau à structure libre pour afficher la mesure **[!UICONTROL Ensemble d’e-mails]** pour la période que vous avez définie afin de tester votre configuration de groupement. Ce tableau à structure libre présente les événements qui possèdent une adresse e-mail avant l’assemblage.

![Tableau à structure libre de l’aperçu du groupement - Jeu d’e-mails](/help/stitching/assets/workspace-emailset.png)

Pour afficher les événements pour lesquels une adresse e-mail est définie après le processus de groupement, définissez une `Email stitched namespace` de mesure calculée. Cette mesure calculée examine les **[!UICONTROL événements]** qui ont un **[!UICONTROL espace de noms d’identité]** égal à l’espace de noms d’e-mail haché `email_lc_sha256`.

![Présentation de l’assemblage - Mesure calculée Espace de noms assemblé d’e-mail](/help/stitching/assets/cm-email-stitched-namespace.png)

Si vous ajoutez la nouvelle mesure calculée **[!UICONTROL Espace de noms assemblé d’e-mail]** au tableau à structure libre, vous constatez une augmentation du nombre d’événements qui disposent désormais d’une adresse e-mail après le processus d’assemblage.

![Assemblage du tableau à structure libre de l’aperçu - Ensemble d’e-mails et assemblage](/help/stitching/assets/workspace-emailset-stitched.png)

Vous obtiendrez des informations supplémentaires en définissant deux mesures calculées supplémentaires.

* **[!UICONTROL Taux d’authentification des emails]**. Cette mesure calculée détermine le taux d’authentification avant le processus de groupement.

  ![ Définition de la mesure calculée Taux d’authentification des e-mails ](/help/stitching/assets/cm-email-authentication-rate.png)

* **[!UICONTROL Taux d’authentification groupée]**. Cette mesure calculée détermine le taux d’authentification après le processus de groupement.

  ![Définition de la mesure calculée de taux d’authentification groupée](/help/stitching/assets/cm-stitched-authentication-rate.png)

Ajoutez ces deux mesures calculées supplémentaires à votre tableau à structure libre. Vous pouvez constater l’augmentation du nombre d’événements assemblés.

![Tableau à structure libre de l’aperçu du groupement - Authentifié](/help/stitching/assets/workspace-authenticated.png)

Pour plus d’informations, vous pouvez ajouter deux mesures calculées supplémentaires (**[!UICONTROL Augmentation en pourcentage]** et **[!UICONTROL Effet élévateur]**) à votre tableau à structure libre pour voir l’impact de votre configuration de groupement.

![Tableau à structure libre de l’aperçu du groupement - Effet élévateur authentifié](/help/stitching/assets/workspace-authenticated-lift.png)



## Validation de l’assemblage des demandes

Cette section explique comment valider le groupement que vous avez demandé à Adobe. Cette méthode est obsolète, mais il se peut que vous ayez toujours des jeux de données groupés à l’aide de cette méthode.

### Conditions préalables relatives aux vues de données

Pour le plan de mesure de validation de l’assemblage, vous devez vous assurer que toutes les dimensions et mesures requises de votre jeu de données assemblé sont définies dans une vue de données. Vérifiez que les champs `stitchedID.id` et `stitchedID.namespace.code` sont ajoutés en tant que dimensions. Bien que le jeu de données assemblé soit une copie exacte du jeu de données d’origine, le processus d’assemblage ajoute ces deux nouvelles colonnes au jeu de données :

* Utilisez `stitchedID.namespace.code` pour définir une dimension **[!UICONTROL Espace de noms groupé]**. Cette dimension contient l’espace de noms de l’identité auquel la ligne a été élevée, par exemple `Email` ou `Phone`. Ou l’espace de noms auquel le processus de groupement revient, tel que `ECID`.
  ![Dimension d’espace de noms groupé](/help/stitching/assets/stitchednamespace-dimension.png)

* Utilisez `stitchedID.id` pour définir une dimension **[!UICONTROL valeur d’ID groupé]**. Cette dimension contient la valeur brute de l’identité. Par exemple : e-mail haché, téléphone haché, ECID. Cette valeur est utilisée avec **[!UICONTROL Espace de noms groupé]**.
  ![Dimension d’ID groupé](/help/stitching/assets/stitchedid-dimension.png)


En outre, vous devez ajouter deux mesures d’assemblage basées sur la présence de valeurs dans une dimension.

1. Utilisez le champ contenant l’ID de personne du jeu de données groupé pour configurer une mesure qui définit si un ID de personne est défini. Ajoutez cet ID de personne même si vous utilisez un groupement basé sur des graphiques, car l’ID de personne permet d’établir une référence. Si l’ID de personne n’est pas contenu dans le jeu de données, votre ligne de base est de 0 %.

   Dans l’exemple ci-dessous, `personalEmail.address` sert d’identité et est utilisé pour créer la mesure **[!UICONTROL _Email set]** .
   ![Mesure définie pour les e-mails](/help/stitching/assets/emailset-metric.png)

1. Utilisez le champ `stitchedID.namespace.code` pour créer une mesure **[!UICONTROL Espace de noms d’e-mail assemblé]**. Veillez à spécifier [Inclure/Exclure les valeurs dans les paramètres du composant](/help/data-views/component-settings/include-exclude-values.md) afin de ne prendre en compte que les valeurs de l’espace de noms vers lequel vous essayez d’élever des lignes de données.
   1. Sélectionnez **[!UICONTROL Définir les valeurs d’inclusion/exclusion]**.
   1. Sélectionnez **[!UICONTROL Si tous les critères sont remplis]** comme **[!UICONTROL Correspondance]**.
   1. Spécifiez **[!UICONTROL Est égal]** `email` comme **[!UICONTROL Critère]** pour sélectionner les événements qui ont été élevés dans l’espace de noms E-mail.

   ![Mesure Espace de noms groupé d’e-mails](/help/stitching/assets/emailstitchednamespace-metric.png)

### Dimensions assemblées

Une fois ces deux dimensions ajoutées à la vue de données, utilisez [tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) dans Analysis Workspace pour vérifier les données de chaque dimension.

Dans le tableau des dimensions **[!UICONTROL Espace de noms groupé]**, vous voyez généralement deux lignes pour chaque jeu de données. Une ligne représente le moment où le processus de groupement a dû utiliser la méthode de secours (ECID). L’autre ligne affiche les événements associés à l’espace de noms d’identité souhaité (e-mail).

Dans le tableau des dimensions **[!UICONTROL valeur de l’ID groupé]**, vous voyez les valeurs brutes qui proviennent des événements. Dans ce tableau, vous constatez que les valeurs oscillent entre l’ID persistant et l’ID de personne souhaité.

![Vérifier les dimensions assemblées](/help/stitching/assets/check-data-on-stitching.png)


### Rapports axés sur les appareils ou les personnes

Lorsque vous créez une connexion, vous devez définir le champ ou l’identité utilisé pour l’ID de personne. Par exemple, sur un jeu de données web, si vous choisissez un identifiant d’appareil comme identifiant de personne, vous créez des rapports centrés sur l’appareil et vous perdez la possibilité de joindre ces données à d’autres canaux hors ligne. Si vous sélectionnez un champ ou une identité cross-canal, par exemple un e-mail, vous perdez tous les événements non authentifiés. Pour comprendre cet impact, vous devez déterminer quelle partie du trafic n’est pas authentifiée et quelle partie du trafic est authentifiée.

1. Créez une mesure calculée **[!UICONTROL Événements non authentifiés sur le total]**. Définissez la règle dans le créateur de règles, comme illustré ci-dessous :
   ![Total des événements non authentifiés](/help/stitching/assets/calcmetric-unauthenticatedeventsovertotal.png)

1. Créez une mesure calculée **[!UICONTROL Taux d’authentification des e-mails]** basée sur la mesure **[!UICONTROL _Email définie]** que vous avez définie précédemment. Définissez la règle dans le créateur de règles, comme illustré ci-dessous :
   ![Taux d’authentification des emails](/help/stitching/assets/calcmetric-emailauthenticationrate.png)

1. Utilisez la mesure calculée **[!UICONTROL Événements non authentifiés sur le total]** ainsi que la mesure calculée **[!UICONTROL Taux d’authentification des e-mails]** pour créer une visualisation [en anneau](/help/analysis-workspace/visualizations/donut.md). La visualisation affiche le nombre d’événements du jeu de données qui ne sont pas authentifiés et authentifiés.

   ![Détails d’identification](/help/stitching/assets/identification-details.png)



### Taux d’identification de l’assemblage

Vous souhaitez mesurer les performances d’identification avant et après le groupement. Pour ce faire, créez trois mesures calculées supplémentaires :

1. Une mesure calculée **[!UICONTROL Taux d’authentification groupée]** qui calcule le nombre d’événements pour lesquels l’espace de noms groupé est défini sur l’identité souhaitée par rapport au nombre total d’événements. Lorsque vous avez configuré la vue de données, vous avez créé une mesure **[!UICONTROL Espace de noms d’e-mail assemblé]** qui incluait un filtre pour comptabiliser uniquement lorsqu’un événement a un espace de noms défini sur e-mail. La mesure calculée utilise cette mesure **[!UICONTROL Espace de noms d’e-mail assemblé]** pour fournir une indication du pourcentage des données qui possède l’identité souhaitée.
   ![Mesure calculée du taux d’authentification groupée](/help/stitching/assets/calcmetric-stitchedauthenticationrate.png)

1. Une mesure calculée **[!UICONTROL Augmentation en pourcentage]** qui calcule la variation en pourcentage brute entre le taux d’identification actuel et le taux assemblé.
   ![Augmentation en pourcentage de la mesure calculée](/help/stitching/assets/calcmetric-percentincrease.png)

1. Mesure calculée **[!UICONTROL Effet élévateur]** qui calcule l’effet élévateur entre le taux d’identification actuel et le taux d’identification assemblé.
   ![Augmentation de la mesure calculée](/help/stitching/assets/calcmetric-lift.png)


### Conclusion

Si vous combinez toutes les données dans un tableau à structure libre Analysis Workspace, vous pouvez commencer à voir l’impact et la valeur du groupement, y compris :

* Taux d’authentification actuel : base du nombre d’événements qui avaient déjà le bon ID de personne sur le nombre total d’événements.
* Taux d’authentification groupée : nouveau nombre d’événements disposant de l’ID de personne correct par rapport au nombre total d’événements.
* Augmentation en pourcentage : augmentation en pourcentage brut par rapport au taux d’authentification groupé, moins le taux d’authentification actuel de base.
* Effet élévateur : pourcentage de modification par rapport au taux d’authentification actuel de base.

![Performances d’identification](/help/stitching/assets/identification-performance.png)


## Points essentiels à retenir

L’essentiel de cet article est que l’assemblage de la validation et de l’analyse vous aide à :

* Fournissez une vue personnalisée complète de l’efficacité de l’authentification en comparant les taux actuels par rapport aux taux groupés.
* Activez la mesure claire de l’amélioration par le biais d’augmentations en pourcentage et de mesures d’effet élévateur.
* Aidez à identifier l’impact réel de l’implémentation du groupement sur l’authentification des utilisateurs.
* Créez un moyen normalisé de communiquer les performances d’authentification entre les équipes.
* Autorisez les décisions basées sur les données concernant la stratégie d’authentification et l’optimisation.

Ces mesures donnent aux parties prenantes une vue d’ensemble complète de la manière dont l’assemblage de Customer Journey Analytics affecte les taux de succès de l’authentification et les performances globales d’identification des personnes.
