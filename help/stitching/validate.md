---
title: Valider l’assemblage
description: Découvrez comment valider le groupement.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
source-git-commit: 391adbe67a4c76f3eb2a8bfcfbb733b2d980cafe
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---

# Valider le groupement

L’objectif du [groupement d’identités](/help/stitching/overview.md) (ou simplement du groupement) est d’améliorer l’adéquation d’un jeu de données d’événement pour l’analyse cross-canal. Cette élévation est atteinte lorsque toutes les lignes de données du jeu de données contiennent l’ordre d’identité le plus élevé souhaité disponible. Cette élévation permet d’effectuer les opérations suivantes :

* Créez des rapports centrés sur la personne, sans exclure les personnes anonymes.
* Connectez plusieurs appareils à une seule personne.
* Connecter une personne sur plusieurs canaux.

Cet article décrit des méthodes d’analyse pour mesurer l’élévation sur un ou plusieurs jeux de données assemblés nouvellement créés et pour garantir que l’assemblage offre ces avantages.

Les méthodes d’analyse impliquent des [paramètres des composants de vue de données](/help/data-views/component-settings/overview.md) qui sont généralement accessibles aux administrateurs. Les méthodes nécessitent également que les analystes, qui travaillent dans un projet Analysis Workspace, créent des mesures calculées et des visualisations.

Bien que ces méthodes d’analyse puissent être utilisées pour le groupement basé sur les champs et le groupement basé sur les graphiques, certains éléments peuvent ne pas être présents dans le jeu de données, en particulier dans un scénario de groupement basé sur les graphiques. Ces éléments manquants peuvent rendre difficile le calcul de l’effet élévateur directement dans Analysis Workspace.

>[!NOTE]
>
>L’assemblage (validation de) d’un ou de plusieurs jeux de données contribue finalement à une meilleure analyse et à de meilleures informations. Cependant, cet article ne traite pas de la valeur globale d’une configuration Customer Journey Analytics dans laquelle tous les jeux de données d’Experience Platform sont alignés sur le même espace de noms d’identité. Et que tous ces jeux de données sont joliment associés pour effectuer une analyse sur l’ensemble d’un parcours client.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Activation et validation du groupement](https://video.tv.adobe.com/v/3478120?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Cet article décrit comment valider le groupement [demandé via Adobe](/help/stitching/use-stitching.md) et implémenté à l’aide d’une colonne d’identité groupée ajoutée à un jeu de données groupé en double. Il est prévu que l’article soit bientôt mis à jour avec des détails sur la validation du groupement [activé via l’interface utilisateur de connexions](/help/stitching/use-stitching-ui.md).



## Conditions préalables relatives aux vues de données

Pour le plan de mesure de validation de l’assemblage, vous devez vous assurer que toutes les dimensions et mesures requises de votre jeu de données assemblé sont définies dans une vue de données. Vous devez vérifier que les champs `stitchedID.id` et `stitchedId.namespace.code` sont ajoutés en tant que dimensions. Bien que le jeu de données assemblé soit une copie exacte du jeu de données d’origine, le processus d’assemblage ajoute ces deux nouvelles colonnes au jeu de données :

* Utilisez `stitchedID.namespace.code` pour définir une dimension **[!UICONTROL Espace de noms groupé]**. Cette dimension contient l’espace de noms de l’identité à laquelle la ligne a été élevée, par exemple `Email`, `Phone`. Ou l’espace de noms vers lequel le processus de groupement revient, tel que `ECID`.
  ![Dimension d’espace de noms groupé](assets/stitchednamespace-dimension.png)

* Utilisez `stitchedID.id` pour définir une dimension **[!UICONTROL valeur d’ID groupé]**. Cette dimension contient la valeur brute de l’identité. Par exemple : e-mail haché, téléphone haché, ECID. Cette valeur est utilisée avec **[!UICONTROL Espace de noms groupé]**.
  ![Dimension d’ID groupé](assets/stitchedid-dimension.png)


En outre, vous devez ajouter deux mesures d’assemblage basées sur la présence de valeurs dans une dimension.

1. Utilisez le champ contenant l’ID de personne du jeu de données groupé pour configurer une mesure qui définit si un ID de personne est défini. Ajoutez cet ID de personne même si vous utilisez un groupement basé sur des graphiques, car l’ID de personne permet d’établir une référence. Si l’ID de personne n’est pas contenu dans le jeu de données, votre ligne de base est de 0 %.

   Dans l’exemple ci-dessous, `personalEmail.address` sert d’identité et est utilisé pour créer la mesure **[!UICONTROL _Email set]** .
   ![Mesure définie pour les e-mails](assets/emailset-metric.png)

1. Utilisez `stitchedID.namespae.code` champ pour créer une dimension **[!UICONTROL Espace de noms d’e-mail assemblé]**. Veillez à spécifier [Inclure/Exclure les valeurs dans les paramètres du composant](/help/data-views/component-settings/include-exclude-values.md) afin de ne prendre en compte que les valeurs de l’espace de noms vers lequel vous essayez d’élever des lignes de données.
   1. Sélectionnez **[!UICONTROL Définir les valeurs d’inclusion/exclusion]**.
   1. Sélectionnez **[!UICONTROL Si tous les critères sont remplis]** comme **[!UICONTROL Correspondance]**.
   1. Spécifiez **[!UICONTROL Est égal]** `email` comme **[!UICONTROL Critère]** pour sélectionner les événements qui ont été élevés dans l’espace de noms E-mail.

   ![Mesure Espace de noms groupé e e-mail](assets/emailstitchednamespace-metric.png)

## Dimensions assemblées

Une fois ces deux dimensions ajoutées à la vue de données, utilisez [tableaux à structure libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) dans Analysis Workspace pour vérifier les données de chaque dimension.

Dans le tableau **[!UICONTROL Dimension d’espace de noms groupé**], vous voyez généralement deux lignes pour chaque jeu de données. Une ligne qui représente le moment où le processus de groupement a dû utiliser la méthode de secours (ECID). L’autre ligne affiche les événements associés à l’espace de noms d’identité souhaité (e-mail).

Pour le tableau **[!UICONTROL dimension d’ID groupé**], vous voyez les valeurs brutes qui proviennent des événements. Dans ce tableau, vous constatez que les valeurs oscillent entre l’identifiant persistant et l’identifiant de personne souhaité.

![Vérifier les dimensions assemblées](assets/check-data-on-stitching.png)


## Rapports centrés sur l’appareil ou sur la personne

Lorsque vous créez une connexion, vous devez définir le champ ou l’identité utilisé pour l’ID de personne. Par exemple, sur un jeu de données web, si vous choisissez un identifiant d’appareil comme identifiant de personne, vous créez des rapports centrés sur l’appareil et vous perdez la possibilité de joindre ces données à d’autres canaux hors ligne. Si vous sélectionnez un champ ou une identité cross-canal, par exemple un e-mail, vous perdez tous les événements non authentifiés. Pour comprendre cet impact, vous devez déterminer quelle partie du trafic n’est pas authentifiée et quelle partie du trafic est authentifiée.

1. Créez une mesure calculée **[!UICONTROL Événements non authentifiés sur le total]**. Définissez la règle dans le créateur de règles comme suit :
   ![Total des événements non authentifiés](assets/calcmetric-unauthenticatedeventsovertotal.png)

1. Créez une mesure calculée **[!UICONTROL Taux d’authentification des e-mails]** basée sur la mesure **[!UICONTROL _Email définie]** que vous avez définie précédemment. Définissez la règle dans le créateur de règles comme suit :
   ![Taux d’authentification des emails](assets/calcmetric-emailauthenticationrate.png)

1. Utilisez la mesure calculée **[!UICONTROL Événements non authentifiés sur le total]** ainsi que la mesure calculée **[!UICONTROL Taux d’authentification des e-mails]** pour créer une visualisation [en anneau](/help/analysis-workspace/visualizations/donut.md). La visualisation affiche le nombre d’événements du jeu de données qui ne sont pas authentifiés et qui sont authentifiés.

   ![Détails d’identification](assets/identification-details.png)



## Taux d’identification de l’assemblage

Vous souhaitez mesurer les performances d’identification avant et après le groupement. Pour ce faire, créez trois mesures calculées supplémentaires :

1. Une mesure calculée **[!UICONTROL Taux d’authentification groupée]** qui calcule le nombre d’événements pour lesquels l’espace de noms groupé est défini sur l’identité souhaitée par rapport au nombre total d’événements. Lorsque vous avez configuré la vue de données, vous avez créé une mesure **[!UICONTROL Espace de noms d’e-mail assemblé]** qui incluait un filtre pour comptabiliser uniquement lorsqu’un événement a un espace de noms défini sur e-mail. La mesure calculée utilise cette mesure **[!UICONTROL Espace de noms d’e-mail assemblé]** pour fournir une indication du pourcentage des données qui possède l’identité souhaitée.
   ![Mesure calculée du taux d’authentification groupée](assets/calcmetric-stitchedauthenticationrate.png)

1. Une mesure calculée **[!UICONTROL Augmentation en pourcentage]** qui calcule la variation en pourcentage brute entre le taux d’identification actuel et le taux assemblé.
   ![Augmentation en pourcentage de la mesure calculée](assets/calcmetric-percentincrease.png)

1. Mesure calculée **[!UICONTROL Effet élévateur]** qui calcule l’effet élévateur entre le taux d’identification actuel et le taux d’identification assemblé.
   ![Augmentation de la mesure calculée](assets/calcmetric-lift.png)


## Conclusion

Si vous combinez toutes les données dans un tableau à structure libre Analysis Workspace, vous pouvez commencer à voir l’impact et la valeur de l’assemblage, notamment :

* Taux d’authentification actuel : base du nombre d’événements qui avaient déjà le bon ID de personne sur le nombre total d’événements.
* Taux d’authentification groupée : nouveau nombre d’événements disposant de l’ID de personne correct par rapport au nombre total d’événements.
* Augmentation en pourcentage : augmentation en pourcentage brut par rapport au taux d’authentification groupé, moins le taux d’authentification actuel de base.
* Effet élévateur : pourcentage de modification par rapport au taux d’authentification actuel de base.

![Performances d’identification](assets/identification-performance.png)

L’essentiel à retenir de cet article est que ce type de validation et d’analyse de groupement vous aide à :

* Fournissez une vue personnalisée complète de l’efficacité de l’authentification en comparant les taux actuels par rapport aux taux groupés.
* Activez la mesure claire de l’amélioration par le biais d’augmentations en pourcentage et de mesures d’effet élévateur.
* Aidez à identifier l’impact réel de l’implémentation du groupement sur l’authentification des utilisateurs.
* Créez un moyen normalisé de communiquer les performances d’authentification entre les équipes.
* Autorisez les décisions basées sur les données concernant la stratégie d’authentification et l’optimisation.

Ces mesures donnent aux parties prenantes une vue d’ensemble complète de la manière dont l’assemblage de Customer Journey Analytics affecte les taux de succès de l’authentification et les performances globales d’identification des personnes.

