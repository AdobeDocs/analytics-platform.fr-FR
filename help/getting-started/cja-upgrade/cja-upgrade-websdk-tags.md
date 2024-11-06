---
title: Utilisation des balises pour implémenter le SDK web pour Customer Journey Analytics
description: Découvrez comment utiliser les balises pour implémenter le SDK web pour Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# Utilisation des balises pour implémenter le SDK web pour Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement une fois toutes les étapes de mise à niveau précédentes effectuées. Vous pouvez suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement pour votre organisation avec le [questionnaire de mise à niveau Adobe Analytics vers Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Une fois que vous avez terminé les étapes de cette page, continuez à suivre les étapes de mise à niveau recommandées ou les étapes de mise à niveau générées dynamiquement.

Vous pouvez utiliser la fonction Balises de Adobe Experience Platform pour implémenter du code sur votre site afin de collecter des données. Cette solution de gestion des balises vous permet de déployer le code parallèlement à d’autres exigences de balisage. Les balises offrent une intégration transparente avec Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

## Créer une balise

1. Dans le rail de gauche de l’interface utilisateur d’Adobe Experience Platform, sélectionnez **[!UICONTROL Balises]** sous [!UICONTROL COLLECTE DE DONNÉES].

2. Sélectionnez **[!UICONTROL Nouvelle propriété]**.

   Nommez la balise, sélectionnez **[!UICONTROL Web]** et saisissez un nom de domaine. Sélectionnez **[!UICONTROL Enregistrer]** pour continuer.

   ![Créer une propriété](assets/create-property.png)

## Configurer la balise

Après avoir créé la balise, vous devez la configurer avec les extensions correctes et configurer les éléments de données et les règles en fonction de la manière dont vous souhaitez effectuer le suivi de votre site et envoyer des données à Adobe Experience Platform.

Sélectionnez la balise que vous venez de créer dans la liste de [!UICONTROL Propriétés de balise] pour l’ouvrir.


### **Extensions**

Pour vous assurer que vous pouvez envoyer des données à Adobe Experience Platform (via votre flux de données), ajoutez l’extension SDK Web Adobe Platform à votre balise.

Créer et configurer l’extension du SDK Web Adobe Experience Platform :

1. Sélectionnez **[!UICONTROL Extensions]** dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Catalogue]** dans la barre supérieure.

1. Recherchez ou accédez à l’extension du SDK Web Adobe Experience Platform, puis sélectionnez **[!UICONTROL Installer]** pour l’installer.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Sélectionnez la sandbox et le flux de données créé précédemment pour l’[!UICONTROL Environnement de production], (facultatif) l’[!UICONTROL Environnement d’évaluation] et l’[!UICONTROL Environnement de développement].

   ![Configuration de l’extension du SDK Web AEP](assets/aepwebsk-extension-datastreams.png)

   Sélectionnez **[!UICONTROL Enregistrer]**.

Consultez [Configurer l’extension du SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html) pour plus d’informations.

Le SDK Web inclut nativement le [!UICONTROL service Adobe Experience Cloud ID], de sorte que vous n’avez pas besoin d’ajouter l’extension du service d’ID à votre balise.

### **Éléments de données**

Les éléments de données sont les blocs de construction de votre dictionnaire de données (ou mappage de données). Utilisez des éléments de données pour recueillir, organiser et diffuser des données dans les technologies marketing et publicitaires. Vous configurez des éléments de données dans la balise qui peuvent être lus à partir de la couche de données et être utilisés pour diffuser des données dans Adobe Experience Platform.

Il existe différents types d’éléments de données. Vous devez d’abord configurer un élément de données pour capturer le nom de page que les personnes consultent sur votre site.

Définir un élément de données de nom de page :

1. Sélectionnez **[!UICONTROL Éléments de données]** dans le rail de gauche.

2. Sélectionnez **[!UICONTROL Ajouter un élément de données]**.

3. Dans la boîte de dialogue [!UICONTROL Créer un élément de données] :

   - Nommez l’élément de données, par exemple `Page Name`.

   - Sélectionnez **[!UICONTROL Principal]** dans la liste [!UICONTROL Extension].

   - Sélectionnez **[!UICONTROL Informations sur la page]** dans la liste [!UICONTROL Type d’élément de données].

   - Sélectionnez **[!UICONTROL Titre]** dans la liste [!UICONTROL Attribut].

     ![Créer un élément de données à l’aide des informations sur la page](assets/create-dataelement-1.png)

     Vous auriez également pu utiliser la valeur d’une variable de la couche de données, par exemple `pageName` et le type d’élément de données [!UICONTROL Variable JavaScript] pour définir l’élément de données.

     ![Créer un élément de données à l’aide d’une variable JavaScript](assets/create-dataelement-2.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.

Vous devez maintenant configurer un élément de données faisant référence à Experience Cloud ID qui est automatiquement fourni par le SDK Web Adobe Experience Platform et disponible via l’extension du service Experience Cloud ID.

Définir un élément de données ECID :

1. Sélectionnez **[!UICONTROL Éléments de données]** dans le rail de gauche.

2. Sélectionnez **[!UICONTROL Ajouter un élément de données]**.

3. Dans la boîte de dialogue [!UICONTROL Créer un élément de données] :

   - Nommez l’élément de données, par exemple `ECID`.

   - Sélectionnez **[!UICONTROL Service Experience Cloud ID]** dans la liste [!UICONTROL Extension].

   - Sélectionnez **[!UICONTROL ECID]** dans la liste [!UICONTROL Type d’élément de données].

     ![Élément de données ECID](assets/ecid-dataelement.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.

Enfin, vous devez maintenant mapper l’un des éléments de données spécifiques au schéma que vous avez défini précédemment. Vous définissez un autre élément de données qui fournit une représentation du schéma XDM.

Définir un élément de données d’objet XDM :

1. Sélectionnez **[!UICONTROL Éléments de données]** dans le rail de gauche.

2. Sélectionnez **[!UICONTROL Ajouter un élément de données]**.

3. Dans la boîte de dialogue [!UICONTROL Créer un élément de données] :

   - Nommez l’élément de données, par exemple `XDM - Page View`.

   - Sélectionnez **[!UICONTROL SDK Web Adobe Experience Platform]** dans la liste [!UICONTROL Extension].

   - Sélectionnez **[!UICONTROL Objet XDM]** dans la liste [!UICONTROL Type d’élément de données].

   - Sélectionnez la sandbox dans la liste [!UICONTROL Sandbox].

   - Sélectionnez le schéma dans la liste [!UICONTROL Schéma].

   - Mappez l’attribut `identification > core > ecid`, défini dans le schéma sur l’élément de données ECID. Sélectionnez l’icône de cylindre pour choisir facilement l’élément de données ECID dans la liste d’éléments de données.

     ![Choisir un élément de données ECID](assets/pick-ecid-dataelement.png)

     ![Mapper l’élément de données ECID](assets/map-ecid.png)


   - Mappez l’attribut `web > webPageDetails > name`, défini dans le schéma sur l’élément de données Nom de page.

     ![Mapper l’élément de données Nom de page](assets/map-pagename.png)

   - Sélectionnez **[!UICONTROL Enregistrer]**.


### **Règles**

Dans Adobe Experience Platform, les balises suivent un système basé sur des règles. Elles recherchent les interactions utilisateur et les données associées. Lorsque les critères définis dans votre règle sont satisfaits, la règle déclenche l’extension, le script ou le code côté client que vous avez identifié. Vous pouvez utiliser des règles pour envoyer des données (comme un objet XDM) dans Adobe Experience Platform à l’aide de l’extension du SDK Web Adobe Experience Platform.

Définir une règle :

1. Sélectionnez **[!UICONTROL Règles]** dans le rail de gauche.

1. Sélectionnez **[!UICONTROL Créer une règle]**.

1. Dans la boîte de dialogue [!UICONTROL Créer une règle] :

   - Nommez la règle, par exemple `Page View`.

   - Sélectionnez **[!UICONTROL + Ajouter]** sous [!UICONTROL Événements].

   - Dans la boîte de dialogue [!UICONTROL Configuration d’événement] :

      - Sélectionnez **[!UICONTROL Principal]** dans la liste [!UICONTROL Extension].

      - Sélectionnez **[!UICONTROL Fenêtre chargée]** dans la liste [!UICONTROL Type d’événement].

        ![Règle - Configuration d’événement](assets/event-windowloaded-pageview.png)

      - Sélectionnez **[!UICONTROL Conserver les modifications]**.



   - Sélectionnez **[!UICONTROL + Ajouter]** sous [!UICONTROL Actions].

   - Dans la boîte de dialogue [!UICONTROL Configuration d’action] :

      - Sélectionnez **[!UICONTROL SDK Web Adobe Experience Platform]** dans la liste [!UICONTROL Extension].

      - Sélectionnez **[!UICONTROL Événement d’envoi]** dans la liste [!UICONTROL Type d’action].

      - Sélectionnez **[!UICONTROL web.webpagedetails.pageViews]** dans la liste [!UICONTROL Type].

      - Sélectionnez l’icône de cylindre en regard de [!UICONTROL Données XDM] et sélectionnez **[!UICONTROL XDM - Page vue]** dans la liste des éléments de données.

     ![Règle - Configuration de l’action](assets/action-pageview-xdm.png)

      - Sélectionnez **[!UICONTROL Conserver les modifications]**.

   - La règle doit se présenter comme suit :

     ![Créer une règle](assets/rule-pageview.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

L’exemple ci-dessus est juste un exemple de définition d’une règle qui envoie des données XDM, contenant des valeurs d’autres éléments de données, à Adobe Experience Platform.

Vous pouvez utiliser des règles de différentes manières dans la balise pour manipuler des variables (à l’aide des éléments de données).

Consultez les [Règles](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=fr) pour plus d’informations.

## Créer et publier la balise

Après avoir défini des éléments de données et des règles, vous devez créer et publier votre balise. Lorsque vous créez une version de bibliothèque, vous devez l’affecter à un environnement. Les extensions, règles et éléments de données de la version sont ensuite compilés et placés dans l’environnement attribué. Chaque environnement fournit un code incorporé unique qui vous permet d’intégrer la version qui lui est assignée dans votre site.

Créer et publier la balise :

1. Sélectionnez **[!UICONTROL Flux de publication]** dans le rail de gauche.

2. Sélectionnez **[!UICONTROL Sélectionner une bibliothèque de travail]**, puis **[!UICONTROL Ajouter une bibliothèque…]**.

3. Dans la boîte de dialogue [!UICONTROL Créer une bibliothèque] :

   - Nommez la bibliothèque.

   - Sélectionnez **[!UICONTROL Développement (développement)]** dans la liste [!UICONTROL Environnement].

   - Sélectionnez **[!UICONTROL + Ajouter toutes les ressources modifiées]**.

     ![Publier - Créer une bibliothèque](assets/create-library-aep.png)

   - Sélectionnez **[!UICONTROL Enregistrer et créer pour le développement]**.

   Votre balise est enregistrée et créée pour votre environnement de développement. Un point vert indique que la balise a été créée avec succès dans l’environnement de développement.

4. Vous pouvez sélectionner **[!UICONTROL …]** pour recréer la bibliothèque ou la déplacer vers un environnement d’évaluation ou de production.

   ![Publier - Créer une bibliothèque](assets/build-library.png)

Les balises Adobe Experience Platform prennent en charge les processus de publication simples à complexes qui doivent s’adapter au déploiement du SDK Web Adobe Experience Platform.

Consultez [Présentation de la publication](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr) pour plus d’informations.


## Récupérer le code de balise

Enfin, vous devez installer la balise sur le site Web dont vous souhaitez effectuer le suivi, ce qui implique de placer le code dans la balise d’en-tête du modèle de votre site Web.

Obtenir le code qui fait référence à la balise :

1. Sélectionnez **[!UICONTROL Environnements]** dans le rail de gauche.

1. Dans la liste des environnements, sélectionnez le bouton d’installation (boîte) approprié.

   Dans la boîte de dialogue [!UICONTROL Instructions d’installation Web], sélectionnez le bouton Copier en regard du code de script qui doit se présenter comme suit :

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Environnement](assets/environment.png)

1. Sélectionnez **[!UICONTROL Fermer]**.

   Au lieu du code de l’environnement de développement, vous auriez pu sélectionner un autre environnement (évaluation, production) en fonction du stade auquel vous vous trouvez dans le processus de déploiement du SDK Web Adobe Experience Platform.

   Consultez [Environnements](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=fr) pour plus d’informations.

1. Continuez à suivre les [étapes de mise à niveau recommandées](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou les [ étapes de mise à niveau générées dynamiquement](https://gigazelle.github.io/cja-ttv/).
